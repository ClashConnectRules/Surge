# Surge Configuration

[中文版](./README_zh.md)

---

**Advanced Surge proxy configuration with intelligent routing, ad blocking, streaming unlock, and AI service optimization.**

---

## Quick Start

```
Download → Add Proxies → Enable MITM → Enjoy
```

## Download

| File | Link |
|:-----|:-----|
| **Surge.conf** | [Download](https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf) |

---

## Features

| Feature | Description |
|:--------|:-----------|
| 🧭 **Smart Routing** | Automatic traffic routing based on region and service |
| 🛡️ **Ad Blocking** | Integrated multi-source ad rules (Skk.moe, blackmatrix7) |
| 🎬 **Streaming Unlock** | Netflix, Disney+, YouTube, TikTok support |
| 🤖 **AI Services** | Optimized routing for ChatGPT, Bing AI, Claude |
| 🔒 **Privacy Protection** | Block tracking and privacy leaks |
| 🎛️ **Remote Management** | Web Dashboard + external controller |

---

## Policy Groups

### Core Policies

| Group | Type | Description |
|:-------|:------|:-----------|
| `Mainland` | select | China Direct |
| `Automatic` | select | Region Auto-Select |
| `Proxy` | select | Main Proxy Policy |

### Regional Groups

| Group | Type | Test |
|:-------|:------|:-----|
| `Hong Kong` 🇭🇰 | url-test | 50ms / 300s |
| `Taiwan` 🇹🇼 | url-test | 50ms / 300s |
| `Japan` 🇯🇵 | url-test | 50ms / 300s |
| `Singapore` 🇸🇬 | url-test | 50ms / 300s |
| `United States` 🇺🇸 | url-test | 50ms / 300s |
| `United Kingdom` 🇬🇧 | url-test | 50ms / 300s |
| `Korea` 🇰🇷 | url-test | 50ms / 300s |

### App Services

| Group | Services |
|:-------|:---------|
| `Apple` | Apple services |
| `AI` | ChatGPT, Bing AI, Claude |
| `Netflix` | Netflix streaming |
| `Disney+` | Disney+ streaming |
| `YouTube` | YouTube streaming |
| `TikTok` | TikTok unlock |

---

## Protocols

| Standard | Community |
|:---------|:----------|
| HTTP / HTTPS | Snell |
| SOCKS5 / SOCKS5-TLS | Shadowsocks |
| SSH | VMess |
| WireGuard | Trojan |
| | TUIC |
| | Hysteria 2 |
| | AnyTLS |

---

## Installation

### Manual Import

```
1. Download Surge.conf
2. Surge → Settings → Configuration
3. "Download from URL"
4. Paste URL → Confirm
```

### Replace File

```
1. Download Surge.conf
2. Replace in iCloud Surge folder
3. Restart Surge
```

---

## Configuration

### Add Proxy

```ini
# Shadowsocks
MySS = ss, 1.2.3.4, 8388, encrypt-method=aes-256-gcm, password=xxx

# VMess
MyVMess = vmess, 1.2.3.4, 443, username=uuid, ws=true, ws-path=/path

# Trojan
MyTrojan = trojan, example.com, 443, password=xxx
```

### Enable MITM

```
1. Install Surge CA certificate
2. Trust in system settings
3. Settings → MITM → Enable
```

---

## DNS

| Type | Server |
|:-----|:-------|
| Primary | 223.5.5.5, 223.6.6.6 |
| Secondary | 119.29.29.29 |
| DoH | doh.pub, dns.alidns.com |

---

## Rule Sources

- **blackmatrix7** - App routing rules
- **Skk.moe** - General routing and ad blocking
- **Semporia** - TikTok unlock
- **VirgilClyne** - ASN rules
- **zxfccmm4** - Unbreak rules

---

## Troubleshooting

| Issue | Solution |
|:-------|:---------|
| Cannot connect | Check proxy config, verify server |
| Streaming blocked | Use streaming-capable nodes |
| MITM fails | Install/trust CA certificate |
| Rules not working | Check rule order, view logs |

---

## Remote Control

| Service | Address |
|:--------|:--------|
| External Controller | `surge@0.0.0.0:6160` |
| HTTP API | `clashconnectrules@0.0.0.0:6166` |
| Web Dashboard | Enabled |

---

## Credits

- [Surge](https://nssurge.com)
- [blackmatrix7](https://github.com/blackmatrix7)
- [Skk.moe](https://github.com/Skk.moe)
- [lige47/QuanX-icon-rule](https://github.com/lige47/QuanX-icon-rule)

---

**MIT License**
