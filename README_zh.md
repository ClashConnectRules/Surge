# Surge 配置文件

[English Version](./README.md)

> 高级 Surge 代理配置，支持智能分流、广告拦截、流媒体解锁和 AI 服务优化。

## 下载

| 链接 | 说明 |
|-----|------|
| [Surge.conf](https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf) | 主配置文件 |
| `surge:///install-config?url=https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf` | 一键导入（Safari） |

## 功能

| 功能 | 描述 |
|-----|------|
| **智能路由** | 基于地区和服务的自动流量分流 |
| **广告拦截** | 集成多源广告规则（Skk.moe、blackmatrix7） |
| **流媒体解锁** | 支持 Netflix、Disney+、YouTube、TikTok |
| **AI 服务** | 针对 ChatGPT、Bing AI、Claude 优化路由 |
| **隐私保护** | 阻止追踪和隐私泄露 |
| **远程管理** | Web Dashboard + 外部控制器 |

## 策略分组

| 分组 | 类型 | 描述 |
|-----|------|------|
| `Mainland` | select | 中国大陆直连 |
| `Automatic` | select | 地区自动选择 |
| `Proxy` | select | 主代理策略 |
| `Hong Kong` 🇭🇰 | url-test | 香港节点（50ms，300s） |
| `Taiwan` 🇹🇼 | url-test | 台湾节点（50ms，300s） |
| `Japan` 🇯🇵 | url-test | 日本节点（50ms，300s） |
| `Singapore` 🇸🇬 | url-test | 新加坡节点（50ms，300s） |
| `United States` 🇺🇸 | url-test | 美国节点（50ms，300s） |
| `United Kingdom` 🇬🇧 | url-test | 英国节点（50ms，300s） |
| `Korea` 🇰🇷 | url-test | 韩国节点（50ms，300s） |
| `Apple` | select | 苹果服务 |
| `AI` | select | ChatGPT、Bing AI |
| `Netflix` | select | Netflix 流媒体 |
| `Disney+` | select | Disney+ 流媒体 |
| `YouTube` | select | YouTube 流媒体 |
| `TikTok` | select | TikTok 解锁 |

## 支持的协议

**标准协议:** HTTP、HTTPS、SOCKS5、SOCKS5-TLS、SSH、WireGuard

**社区协议:** Snell、Shadowsocks、VMess、Trojan、TUIC、Hysteria 2、AnyTLS

## 安装

### 方法一：一键导入

复制到 Safari 打开：

```
surge:///install-config?url=https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf
```

### 方法二：手动导入

1. 下载 [Surge.conf](https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf)
2. 打开 Surge → 设置 → 配置
3. 点击「从 URL 下载」
5. 粘贴链接并确认

### 方法三：替换本地文件

1. 下载 [Surge.conf](https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf)
2. 替换 iCloud Surge 文件夹中的现有配置

## 配置

### 添加代理服务器

编辑 `[Proxy]` 部分：

```ini
# Shadowsocks
MySS = ss, 1.2.3.4, 8388, encrypt-method=aes-256-gcm, password=your-password

# VMess
MyVMess = vmess, 1.2.3.4, 443, username=your-uuid, ws=true, ws-path=/path

# Trojan
MyTrojan = trojan, example.com, 443, password=your-password
```

### 启用 MITM

1. 安装 Surge CA 证书
2. 在系统设置中信任证书
3. 设置 → MITM → 开启

## DNS 设置

| 类型 | 服务器 |
|-----|-------|
| 主 DNS | 223.5.5.5, 223.6.6.6 (阿里云) |
| 备用 DNS | 119.29.29.29 (腾讯) |
| DoH | doh.pub, dns.alidns.com |

## 规则来源

- **blackmatrix7** - 应用分流规则
- **Skk.moe** - 通用分流和广告拦截
- **Semporia** - TikTok 解锁
- **VirgilClyne** - ASN 规则
- **zxfccmm4** - Unbreak 规则

## 常见问题

| 问题 | 解决方案 |
|-----|---------|
| 无法连接 | 检查代理配置，确认服务器在线 |
| 流媒体被阻断 | 使用支持流媒体的节点 |
| MITM 失效 | 安装/信任 CA 证书，检查主机名 |
| 规则不生效 | 检查规则顺序，查看日志 |

## 远程控制

| 服务 | 地址 |
|-----|------|
| 外部控制器 | `surge@0.0.0.0:6160` |
| HTTP API | `clashconnectrules@0.0.0.0:6166` |
| Web Dashboard | 已启用 |

## 致谢

- [Surge](https://nssurge.com) - nssurge.com
- [规则贡献者](https://github.com/blackmatrix7) - blackmatrix7、Skk.moe、Semporia、VirgilClyne、zxfccmm4
- [图标](https://github.com/lige47/QuanX-icon-rule) - lige47/QuanX-icon-rule

## 许可证

MIT License
