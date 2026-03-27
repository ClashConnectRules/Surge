# Surge 配置文件

<p align="center">
  <img src="https://img.shields.io/badge/Surge-5-orange?style=flat-square" alt="Surge">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License">
</p>

<p align="center">
  <b>高级 Surge 代理配置</b><br>
  <i>智能分流、广告拦截、流媒体解锁、AI 服务优化</i>
</p>

<p align="center">
  <a href="#-基础设置">基础</a> •
  <a href="#-dns-配置">DNS</a> •
  <a href="#-策略分组">分组</a> •
  <a href="#-规则优先级">规则</a> •
  <a href="#-安装">安装</a>
</p>

<p align="center">
  <b>🌐 Language / 语言切换</b><br>
  <a href="README_zh.md">🇨🇳 简体中文</a> | <a href="README.md">🇺🇸 English</a>
</p>

---

## 📥 下载

| 文件 | 链接 |
|:----:|:-----|
| **Surge.conf** | [下载](https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf) |

---

## ⚙️ 基础设置

| 设置项 | 值 | 说明 |
|:-------:|:-----:|:-----------|
| HTTP 端口 | `6152` | Wi-Fi 分享端口 |
| SOCKS5 端口 | `6153` | Wi-Fi 分享端口 |
| 控制器 | `6160` | API 控制端口 |
| 仪表板 | `6166` | Web 仪表板端口 |
| IPv6 | `false` | 默认禁用 |

---

## 🌐 DNS 配置

| 类型 | 服务器 | 提供商 |
|:----:|:------:|:--------:|
| 系统 | `223.5.5.5`, `223.6.6.6`, `119.29.29.29` | 国内 DNS |
| DoH | `https://doh.pub/dns-query` | DNSPod |
| DoH | `https://dns.alidns.com/dns-query` | 阿里云 |
| 劫持 | `8.8.8.8:53`, `8.8.4.4:53` | Google DNS |

---

## 🎯 策略分组

### 🚀 核心分组

| 分组 | 类型 | 描述 |
|:-----:|:----:|:-----------|
| `Mainland` | `select` | 中国大陆直连 |
| `NoAuto` | `select` | 主入口 |
| `Automatic` | `select` | 地区选择 |
| `AllServer` | `select` | 全部订阅节点 |
| `Proxy` | `select` | 代理策略 |

### 🌍 地区分组（自动测速）

| 分组 | 过滤 | 间隔 | 容差 |
|:-----:|:------:|:--------:|:---------:|
| `Hong Kong` 🇭🇰 | `港\|🇭🇰\|香港\|HK\|Hong` | 300s | 50ms |
| `Taiwan` 🇹🇼 | `台\|🇹🇼\|台湾\|TW\|Tai` | 300s | 50ms |
| `Japan` 🇯🇵 | `日\|🇯🇵\|日本\|JP\|Japan` | 300s | 50ms |
| `Singapore` 🇸🇬 | `坡\|🇸🇬\|新加坡\|狮城\|SG` | 300s | 50ms |
| `United States` 🇺🇸 | `美\|🇺🇸\|美国\|US\|States` | 300s | 50ms |
| `United Kingdom` 🇬🇧 | `🇬🇧\|英国\|英\|UK` | 300s | 50ms |
| `Korea` 🇰🇷 | `韩\|韩国\|Korea\|KR\|🇰🇷` | 300s | 50ms |
| `Other` | 排除以上 | 300s | 50ms |

### 📦 服务分组

| 分组 | 默认 | 用途 |
|:-----:|:-------:|:-------|
| `AI` | Automatic | ChatGPT、Claude、Bing AI |
| `Apple` | Mainland → HK → US | 苹果服务 |
| `Microsoft` | Mainland → HK → SG → US | 微软服务 |
| `OneDrive` | Mainland → HK → SG → US | 云存储 |
| `Telegram` | Automatic → SG → US → HK | 电报 |
| `X` | Automatic → HK → TW → SG → JP → US | Twitter/X |
| `WeChat` | Mainland → HK → SG → US | 微信 |
| `Netflix` | HK → TW → SG → JP → US | Netflix 流媒体 |
| `Disney+` | HK → SG | Disney+ 流媒体 |
| `YouTube` | Automatic → HK → TW → SG → JP → US | YouTube 流媒体 |
| `TikTok` | TW → SG → JP → US | TikTok 解锁 |
| `Bilibili` | Mainland → HK → TW | 哔哩哔哩（港台解锁） |
| `Speedtest` | Mainland → Auto → AllServer | 网速测试 |

---

## 📋 规则优先级

```
 1. 🔧 规则修正        修复连接 → DIRECT
 2. 🚫 广告拦截        SKK 规则集 → REJECT
 3. 🔒 隐私保护        阻止追踪器
 4. 📱 国内应用        微信、网易云、B站、微博
 5. 🍎 Apple 服务      App Store、Apple News、Apple TV
 6. 🤖 AI 服务         OpenAI、Claude、Gemini、Bing
 7. 🎬 流媒体          Disney+、Netflix、TikTok、YouTube
 8. 🌏 地区解锁        US、EU、JP、KR、HK、TW 流媒体
 9. 💬 社交媒体        Twitter、Telegram、Facebook、Instagram
10. 🔧 其他国外服务    OneDrive、Microsoft、GitHub、Speedtest
11. 🇨🇳 国内规则       SKK + ChinaMax 规则集
12. 🌐 国外规则        CDN、Global 规则集
13. 🏠 本地网络        局域网 → DIRECT
14. 🎯 兜底规则        FINAL → NoAuto
```

---

## 🔌 支持的协议

| 标准协议 | 社区协议 |
|:---------|:----------|
| HTTP / HTTPS | Snell |
| SOCKS5 / SOCKS5-TLS | Shadowsocks |
| SSH | VMess |
| WireGuard | Trojan |
| | TUIC |
| | Hysteria 2 |
| | AnyTLS |

---

## ✨ 特殊功能

### 🔄 URL 重写

| 原地址 | 目标 | 类型 |
|:--------:|:------:|:----:|
| `google.cn` | `google.com` | 302 |
| `maps.google.cn` | `maps.google.com` | 302 |
| `taobao.com` | HTTPS | 302 |
| `jd.com` | HTTPS | 302 |
| `mi.com` | HTTPS | 302 |

### 🏠 Host 映射

| 服务 | DNS 服务器 | 描述 |
|:-------:|:----------:|:-----------|
| 淘宝/天猫/支付宝 | `223.5.5.5` | 阿里服务 |
| 京东/QQ/微信 | `119.28.28.28` | 腾讯服务 |
| 哔哩哔哩/网易 | `119.29.29.29` | 娱乐服务 |
| 小米 | `119.29.29.29` | 小米服务 |
| 路由器管理 | 系统 DNS | 本地设备 |

---

## 🚀 安装

### 方法一：手动导入

```
1. 下载 Surge.conf
2. Surge → 设置 → 配置
3. 「从 URL 下载」
4. 粘贴链接 → 确认
```

### 方法二：替换文件

```
1. 下载 Surge.conf
2. 替换 iCloud Surge 文件夹中的配置
3. 重启 Surge
```

### 配置订阅

```
AllServer = select, ..., policy-path=https://your-subscription-url
```

---

## ⚙️ 配置

### 添加代理服务器

编辑 `[Proxy]` 部分：

```ini
# Shadowsocks
MySS = ss, 1.2.3.4, 8388, encrypt-method=aes-256-gcm, password=xxx

# VMess
MyVMess = vmess, 1.2.3.4, 443, username=uuid, ws=true, ws-path=/path

# Trojan
MyTrojan = trojan, example.com, 443, password=xxx
```

### 启用 MITM

```
1. 安装 Surge CA 证书
2. 在系统设置中信任
3. 设置 → MITM → 开启
```

---

## 📚 规则来源

| 来源 | 描述 |
|:------:|:-----------|
| [blackmatrix7](https://github.com/blackmatrix7/ios_rule_script) | 跨平台规则 |
| [Skk.moe](https://ruleset.skk.moe) | SKK 规则集 |
| [VirgilClyne](https://github.com/VirgilClyne/GetSomeFries) | ASN 规则 |
| [Semporia](https://github.com/Semporia/TikTok-Unlock) | TikTok 解锁 |
| [zxfccmm4](https://github.com/zxfccmm4) | Unbreak 规则 |

---

## ⚠️ 注意事项

| 项目 | 描述 |
|:----:|:-----------|
| 🔗 订阅链接 | 需替换为您的订阅地址 |
| 🔄 规则更新 | 规则从在线源自动更新 |
| ⏱️ 测速设置 | 300s 间隔、3s 超时、50ms 容差 |
| 🔐 MITM 证书 | URL 重写需要安装证书 |
| 🔍 节点过滤 | 自动过滤包含"流量/重置/过期"关键词的节点 |

---

## 🎛️ 远程控制

| 服务 | 地址 |
|:--------|:--------|
| 外部控制器 | `surge@0.0.0.0:6160` |
| HTTP API | `clashconnectrules@0.0.0.0:6166` |
| Web 仪表板 | 已启用 |

---

## 🔧 常见问题

| 问题 | 解决方案 |
|:-------|:---------|
| 无法连接 | 检查代理配置，确认服务器在线 |
| 流媒体被阻断 | 使用支持流媒体的节点 |
| MITM 失效 | 安装/信任 CA 证书 |
| 规则不生效 | 检查规则顺序，查看日志 |

---

## 📄 致谢

- [Surge](https://nssurge.com)
- [blackmatrix7](https://github.com/blackmatrix7)
- [Skk.moe](https://github.com/Skk.moe)
- [lige47/QuanX-icon-rule](https://github.com/lige47/QuanX-icon-rule)

---

## 📄 许可证

**MIT**

---

<p align="center">
  <sub>用 ❤️ 打造更好的网络体验</sub>
</p>
