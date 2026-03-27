# Surge Configuration

[中文版](./README_zh.md)

> Advanced Surge proxy configuration with intelligent routing, ad blocking, streaming unlock, and AI service optimization.

## Download

| Link | Description |
|------|-------------|
| [Surge.conf](https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf) | Main configuration file |
| `surge:///install-config?url=https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf` | One-tap import (Safari) |

## Features

| Feature | Description |
|---------|-------------|
| **Smart Routing** | Automatic traffic routing based on region and service |
| **Ad Blocking** | Integrated multi-source ad rules (Skk.moe, blackmatrix7) |
| **Streaming Unlock** | Netflix, Disney+, YouTube, TikTok support |
| **AI Services** | Optimized routing for ChatGPT, Bing AI, Claude |
| **Privacy Protection** | Block tracking and privacy leaks |
| **Remote Management** | Web Dashboard + external controller |

## Policy Groups

| Group | Type | Description |
|-------|------|-------------|
| `Mainland` | select | China Direct |
| `Automatic` | select | Region Auto-Select |
| `Proxy` | select | Main Proxy Policy |
| `Hong Kong` 🇭🇰 | url-test | HK servers (50ms, 300s) |
| `Taiwan` 🇹🇼 | url-test | TW servers (50ms, 300s) |
| `Japan` 🇯🇵 | url-test | JP servers (50ms, 300s) |
| `Singapore` 🇸🇬 | url-test | SG servers (50ms, 300s) |
| `United States` 🇺🇸 | url-test | US servers (50ms, 300s) |
| `United Kingdom` 🇬🇧 | url-test | UK servers (50ms, 300s) |
| `Korea` 🇰🇷 | url-test | KR servers (50ms, 300s) |
| `Apple` | select | Apple services |
| `AI` | select | ChatGPT, Bing AI |
| `Netflix` | select | Netflix streaming |
| `Disney+` | select | Disney+ streaming |
| `YouTube` | select | YouTube streaming |
| `TikTok` | select | TikTok unlock |

## Supported Protocols

**Standard:** HTTP, HTTPS, SOCKS5, SOCKS5-TLS, SSH, WireGuard

**Community:** Snell, Shadowsocks, VMess, Trojan, TUIC, Hysteria 2, AnyTLS

## Installation

### Method 1: One-tap Import

Copy and open in Safari:

```
surge:///install-config?url=https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf
```

### Method 2: Manual Import

1. Download [Surge.conf](https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf)
2. Open Surge → Settings → Configuration
3. Tap "Download from URL"
5. Paste URL and confirm

### Method 3: Replace Local File

1. Download [Surge.conf](https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf)
2. Replace existing configuration in iCloud Surge folder

## Configuration

### Add Proxy Servers

Edit `[Proxy]` section:

```ini
# Shadowsocks
MySS = ss, 1.2.3.4, 8388, encrypt-method=aes-256-gcm, password=your-password

# VMess
MyVMess = vmess, 1.2.3.4, 443, username=your-uuid, ws=true, ws-path=/path

# Trojan
MyTrojan = trojan, example.com, 443, password=your-password
```

### Enable MITM

1. Install Surge CA certificate
2. Trust in system settings
3. Settings → MITM → Enable

## DNS Settings

| Type | Server |
|------|--------|
| Primary | 223.5.5.5, 223.6.6.6 (Aliyun) |
| Secondary | 119.29.29.29 (Tencent) |
| DoH | doh.pub, dns.alidns.com |

## Rule Sources

- **blackmatrix7** - App routing rules
- **Skk.moe** - General routing and ad blocking
- **Semporia** - TikTok unlock
- **VirgilClyne** - ASN rules
- **zxfccmm4** - Unbreak rules

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Cannot connect | Check proxy config, verify server online |
| Streaming blocked | Use nodes that support streaming |
| MITM fails | Install/trust CA certificate, check hostname |
| Rules not working | Check rule order, view logs |

## Remote Control

| Service | Address |
|---------|---------|
| External Controller | `surge@0.0.0.0:6160` |
| HTTP API | `clashconnectrules@0.0.0.0:6166` |
| Web Dashboard | Enabled |

## Credits

- [Surge](https://nssurge.com) - nssurge.com
- [Rule Contributors](https://github.com/blackmatrix7) - blackmatrix7, Skk.moe, Semporia, VirgilClyne, zxfccmm4
- [Icons](https://github.com/lige47/QuanX-icon-rule) - lige47/QuanX-icon-rule

## License

MIT License
