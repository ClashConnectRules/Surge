# Surge 配置文件

[English Version](./README.md)

---

**高级 Surge 代理配置，支持智能分流、广告拦截、流媒体解锁和 AI 服务优化。**

---

## 快速开始

```
下载配置 → 添加代理 → 启用 MITM → 完成
```

## 下载

| 文件 | 链接 |
|:-----|:-----|
| **Surge.conf** | [下载](https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf) |

---

## 功能

| 功能 | 描述 |
|:--------|:-----------|
| 🧭 **智能路由** | 基于地区和服务的自动流量分流 |
| 🛡️ **广告拦截** | 集成多源广告规则（Skk.moe、blackmatrix7） |
| 🎬 **流媒体解锁** | 支持 Netflix、Disney+、YouTube、TikTok |
| 🤖 **AI 服务** | 针对 ChatGPT、Bing AI、Claude 优化路由 |
| 🔒 **隐私保护** | 阻止追踪和隐私泄露 |
| 🎛️ **远程管理** | Web Dashboard + 外部控制器 |

---

## 策略分组

### 核心策略

| 分组 | 类型 | 描述 |
|:-------|:------|:-----------|
| `Mainland` | select | 中国大陆直连 |
| `Automatic` | select | 地区自动选择 |
| `Proxy` | select | 主代理策略 |

### 地区分组

| 分组 | 类型 | 测试 |
|:-------|:------|:-----|
| `Hong Kong` 🇭🇰 | url-test | 50ms / 300s |
| `Taiwan` 🇹🇼 | url-test | 50ms / 300s |
| `Japan` 🇯🇵 | url-test | 50ms / 300s |
| `Singapore` 🇸🇬 | url-test | 50ms / 300s |
| `United States` 🇺🇸 | url-test | 50ms / 300s |
| `United Kingdom` 🇬🇧 | url-test | 50ms / 300s |
| `Korea` 🇰🇷 | url-test | 50ms / 300s |

### 应用服务

| 分组 | 服务 |
|:-------|:---------|
| `Apple` | 苹果服务 |
| `AI` | ChatGPT、Bing AI、Claude |
| `Netflix` | Netflix 流媒体 |
| `Disney+` | Disney+ 流媒体 |
| `YouTube` | YouTube 流媒体 |
| `TikTok` | TikTok 解锁 |

---

## 支持协议

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

## 安装

### 手动导入

```
1. 下载 Surge.conf
2. Surge → 设置 → 配置
3. 「从 URL 下载」
4. 粘贴链接 → 确认
```

### 替换文件

```
1. 下载 Surge.conf
2. 替换 iCloud Surge 文件夹中的配置
3. 重启 Surge
```

---

## 配置

### 添加代理

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

## DNS 设置

| 类型 | 服务器 |
|:-----|:-------|
| 主 DNS | 223.5.5.5, 223.6.6.6 |
| 备用 DNS | 119.29.29.29 |
| DoH | doh.pub, dns.alidns.com |

---

## 规则来源

- **blackmatrix7** - 应用分流规则
- **Skk.moe** - 通用分流和广告拦截
- **Semporia** - TikTok 解锁
- **VirgilClyne** - ASN 规则
- **zxfccmm4** - Unbreak 规则

---

## 常见问题

| 问题 | 解决方案 |
|:-------|:---------|
| 无法连接 | 检查代理配置，确认服务器在线 |
| 流媒体被阻断 | 使用支持流媒体的节点 |
| MITM 失效 | 安装/信任 CA 证书 |
| 规则不生效 | 检查规则顺序，查看日志 |

---

## 远程控制

| 服务 | 地址 |
|:--------|:--------|
| 外部控制器 | `surge@0.0.0.0:6160` |
| HTTP API | `clashconnectrules@0.0.0.0:6166` |
| Web Dashboard | 已启用 |

---

## 致谢

- [Surge](https://nssurge.com)
- [blackmatrix7](https://github.com/blackmatrix7)
- [Skk.moe](https://github.com/Skk.moe)
- [lige47/QuanX-icon-rule](https://github.com/lige47/QuanX-icon-rule)

---

**MIT License**
