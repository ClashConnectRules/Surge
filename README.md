# Surge Configuration

<p align="center">
  <img src="https://img.shields.io/badge/Surge-5-orange?style=flat-square" alt="Surge">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License">
</p>

<p align="center">
  <b>Advanced Surge Proxy Configuration</b><br>
  <i>智能分流、广告拦截、流媒体解锁</i>
</p>

<p align="center">
  <a href="#-basic-settings">Basic</a> •
  <a href="#-dns-configuration">DNS</a> •
  <a href="#-proxy-groups">Groups</a> •
  <a href="#-rule-priority">Rules</a> •
  <a href="#-installation">Install</a>
</p>

<p align="center">
  <b>🌐 Language / 语言切换</b><br>
  <a href="README_zh.md">🇨🇳 简体中文</a> | <a href="README.md">🇺🇸 English</a>
</p>

---

## 💎 Recommended Providers

<p align="center">

| | Provider | Features | Sign Up |
|:-:|:--------:|:--------:|:-------:|
| 🌐 | **ZRJ** | Premium Routes · Fast Experience | [Register Now](https://www.hizrj.xyz/#/register?code=l9CHL5er) |

</p>

---

## 📥 Download

| File | Link |
|:----:|:-----|
| **Surge.conf** | [Download](https://raw.githubusercontent.com/ClashConnectRules/Surge/refs/heads/main/Surge.conf) |

---

## ⚙️ Basic Settings

| Setting | Value | Description |
|:-------:|:-----:|:-----------|
| HTTP Port | `6152` | Wi-Fi sharing port |
| SOCKS5 Port | `6153` | Wi-Fi sharing port |
| Controller | `6160` | API control port |
| Dashboard | `6166` | Web dashboard port |
| IPv6 | `false` | Disabled by default |

---

## 🌐 DNS Configuration

| Type | Server | Provider |
|:----:|:------:|:--------:|
| System | `223.5.5.5`, `223.6.6.6`, `119.29.29.29` | China DNS |
| DoH | `https://doh.pub/dns-query` | DNSPod |
| DoH | `https://dns.alidns.com/dns-query` | Alibaba |
| Hijack | `8.8.8.8:53`, `8.8.4.4:53` | Google DNS |

---

## 🎯 Proxy Groups

### 🚀 Core Groups

| Group | Type | Description |
|:-----:|:----:|:-----------|
| `Mainland` | `select` | China Direct |
| `NoAuto` | `select` | Main entry point |
| `Automatic` | `select` | Regional selection |
| `AllServer` | `select` | All subscription nodes |
| `Proxy` | `select` | Proxy policy |

### 🌍 Regional Groups (Auto URL-Test)

| Group | Filter | Interval | Tolerance |
|:-----:|:------:|:--------:|:---------:|
| `Hong Kong` 🇭🇰 | `港\|🇭🇰\|香港\|HK\|Hong` | 300s | 50ms |
| `Taiwan` 🇹🇼 | `台\|🇹🇼\|台湾\|TW\|Tai` | 300s | 50ms |
| `Japan` 🇯🇵 | `日\|🇯🇵\|日本\|JP\|Japan` | 300s | 50ms |
| `Singapore` 🇸🇬 | `坡\|🇸🇬\|新加坡\|狮城\|SG` | 300s | 50ms |
| `United States` 🇺🇸 | `美\|🇺🇸\|美国\|US\|States` | 300s | 50ms |
| `United Kingdom` 🇬🇧 | `🇬🇧\|英国\|英\|UK` | 300s | 50ms |
| `Korea` 🇰🇷 | `韩\|韩国\|Korea\|KR\|🇰🇷` | 300s | 50ms |
| `Other` | Exclude above | 300s | 50ms |

### 📦 Service Groups

| Group | Default | Purpose |
|:-----:|:-------:|:-------|
| `AI` | Automatic | ChatGPT, Claude, Bing AI |
| `Apple` | Mainland → HK → US | Apple services |
| `Microsoft` | Mainland → HK → SG → US | Microsoft services |
| `OneDrive` | Mainland → HK → SG → US | Cloud storage |
| `Telegram` | Automatic → SG → US → HK | Messaging |
| `X` | Automatic → HK → TW → SG → JP → US | Twitter/X |
| `WeChat` | Mainland → HK → SG → US | WeChat |
| `Netflix` | HK → TW → SG → JP → US | Netflix streaming |
| `Disney+` | HK → SG | Disney+ streaming |
| `YouTube` | Automatic → HK → TW → SG → JP → US | YouTube streaming |
| `TikTok` | TW → SG → JP → US | TikTok unlock |
| `Bilibili` | Mainland → HK → TW | Bilibili (HK/TW unlock) |
| `Speedtest` | Mainland → Auto → AllServer | Speed test |

---

## 📋 Rule Priority

```
 1. 🔧 Unbreak Rules    Fix broken connections → DIRECT
 2. 🚫 Ad Blocking      SKK Ruleset → REJECT
 3. 🔒 Privacy          Block trackers
 4. 📱 CN Apps          WeChat, NetEase, Bilibili, Weibo
 5. 🍎 Apple Services   App Store, Apple News, Apple TV
 6. 🤖 AI Services      OpenAI, Claude, Gemini, Bing
 7. 🎬 Streaming        Disney+, Netflix, TikTok, YouTube
 8. 🌏 Regional Unlock  US, EU, JP, KR, HK, TW streams
 9. 💬 Social Media     Twitter, Telegram, Facebook, Instagram
10. 🔧 Other Global     OneDrive, Microsoft, GitHub, Speedtest
11. 🇨🇳 CN Rules        SKK + ChinaMax ruleset
12. 🌐 Global Rules     CDN, Global ruleset
13. 🏠 LAN              Local network → DIRECT
14. 🎯 Final Rule       FINAL → NoAuto
```

---

## 🔌 Supported Protocols

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

## ✨ Special Features

### 🔄 URL Rewrite

| Original | Target | Type |
|:--------:|:------:|:----:|
| `google.cn` | `google.com` | 302 |
| `maps.google.cn` | `maps.google.com` | 302 |
| `taobao.com` | HTTPS | 302 |
| `jd.com` | HTTPS | 302 |
| `mi.com` | HTTPS | 302 |

### 🏠 Host Mapping

| Service | DNS Server | Description |
|:-------:|:----------:|:-----------|
| Taobao/Tmall/Alipay | `223.5.5.5` | Alibaba services |
| JD/QQ/WeChat | `119.28.28.28` | Tencent services |
| Bilibili/NetEase | `119.29.29.29` | Entertainment |
| Xiaomi | `119.29.29.29` | Xiaomi services |
| Router Admin | System DNS | Local devices |

---

## 🚀 Installation

### Method 1: Manual Import

```
1. Download Surge.conf
2. Surge → Settings → Configuration
3. "Download from URL"
4. Paste URL → Confirm
```

### Method 2: Replace File

```
1. Download Surge.conf
2. Replace in iCloud Surge folder
3. Restart Surge
```

### Configure Subscription

```
AllServer = select, ..., policy-path=https://your-subscription-url
```

---

## ⚙️ Configuration

### Add Proxy Servers

Edit `[Proxy]` section:

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

## 📚 Rule Sources

| Source | Description |
|:------:|:-----------|
| [blackmatrix7](https://github.com/blackmatrix7/ios_rule_script) | Cross-platform rules |
| [Skk.moe](https://ruleset.skk.moe) | SKK ruleset |
| [VirgilClyne](https://github.com/VirgilClyne/GetSomeFries) | ASN rules |
| [Semporia](https://github.com/Semporia/TikTok-Unlock) | TikTok unlock |
| [zxfccmm4](https://github.com/zxfccmm4) | Unbreak rules |

---

## ⚠️ Notes

| Item | Description |
|:----:|:-----------|
| 🔗 Subscription | Replace with your own subscription URL |
| 🔄 Rule Update | Rules auto-update from online sources |
| ⏱️ Speed Test | 300s interval, 3s timeout, 50ms tolerance |
| 🔐 MITM Cert | Required for URL rewrite |
| 🔍 Node Filter | Auto-filter nodes with "traffic/reset/expire" keywords |

---

## 🎛️ Remote Control

| Service | Address |
|:--------|:--------|
| External Controller | `surge@0.0.0.0:6160` |
| HTTP API | `clashconnectrules@0.0.0.0:6166` |
| Web Dashboard | Enabled |

---

## 🔧 Troubleshooting

| Issue | Solution |
|:-------|:---------|
| Cannot connect | Check proxy config, verify server |
| Streaming blocked | Use streaming-capable nodes |
| MITM fails | Install/trust CA certificate |
| Rules not working | Check rule order, view logs |

---

---

## 🎨 Custom Icons

Surge proxy groups support custom icons via the `icon-url` parameter. Follow this guide to personalize your icons.

### Icon Format

In the `[Proxy Group]` section, each group can specify an `icon-url`:

```ini
Telegram = select, Automatic, Singapore, "United States", icon-url=https://example.com/icon.png
```

Icons should be **PNG format**, recommended size **120×120 px**.

### Recommended Icon Packs

These community icon packs cover popular apps, streaming services, flags, and more:

**Qure Icon Pack**

| Icon Pack | Link |
|:---------:|:-----|
| Qure (Color·All) | [QureColor-All.json](https://raw.githubusercontent.com/Koolson/Qure/master/Other/QureColor-All.json) |
| Qure (Light·All) | [QureLight-All.json](https://raw.githubusercontent.com/Koolson/Qure/master/Other/QureLight-All.json) |
| Qure (Mini·All) | [Quremini.json](https://raw.githubusercontent.com/Koolson/Qure/master/Other/Quremini.json) |

**Orz-3 Icon Pack**

| Icon Pack | Link |
|:---------:|:-----|
| Orz-3 (Color A) | [miniColor.json](https://raw.githubusercontent.com/Orz-3/mini/master/miniColor.json) |
| Orz-3 (Color B) | [mini+.json](https://raw.githubusercontent.com/Orz-3/mini/master/mini+.json) |
| Orz-3 (Color C) | [mini.json](https://raw.githubusercontent.com/Orz-3/mini/master/mini.json) |
| Orz-3 (Color D) | [face.json](https://raw.githubusercontent.com/Orz-3/face/master/face.json) |

**Other Icon Packs**

| Icon Pack | Link |
|:---------:|:-----|
| tugepaopao (Color) | [Cute.json](https://raw.githubusercontent.com/tugepaopao/Image-Storage/master/other/Cute.json) |
| shindgewongxj (Color) | [iconset.json](https://raw.githubusercontent.com/shindgewongxj/WHATSINStash/main/icon/iconset.json) |
| Semporia (Color Hand-drawn) | [Semporia.json](https://raw.githubusercontent.com/Semporia/Hand-Painted-icon/master/Semporia.json) |
| Colorful Static Flags | [ColorfulStaticFlag.json](https://gitlab.com/lodepuly/iconlibrary/-/raw/main/Flag_icon/ColorfulStaticFlag.json) |
| TheMagic Icons | [TheRaw.json](https://raw.githubusercontent.com/Twoandz9/TheMagic-Icons/main/TheRaw.json) |

**ginibond Icon Series**

| Icon Pack | Link |
|:---------:|:-----|
| Airport Icons | [airport](https://raw.githubusercontent.com/ginibond/ginibond/main/Icons/airport/tubiao.json) |
| QQ Classic | [QQ_Classic](https://raw.githubusercontent.com/ginibond/ginibond/main/Icons/QQ_Classic/tubiao.json) |
| Cute Cartoon | [Cute_Cartoon](https://raw.githubusercontent.com/ginibond/ginibond/main/Icons/Cute_Cartoon/tubiao.json) |
| Contact | [contact](https://raw.githubusercontent.com/ginibond/ginibond/main/Icons/contact/tubiao.json) |
| Character | [character](https://raw.githubusercontent.com/ginibond/ginibond/main/Icons/character/tubiao.json) |
| RageBaby | [RageBaby](https://raw.githubusercontent.com/ginibond/ginibond/main/Icons/RageBaby/tubiao.json) |

### How to Add Icons

**Step 1: Find an icon pack**

Browse the icon pack's GitHub repository to find the PNG file you want.

**Step 2: Get the icon direct link**

The direct link format is:

```
https://raw.githubusercontent.com/<username>/<repo>/<branch>/<path>/<icon-name>.png
```

> **Tip:** If you get links from Loon icon import URLs, the format is:
> ```
> https://www.nsloon.com/openloon/import?iconset=https://raw.githubusercontent.com/...
> ```
> Remove the `https://www.nsloon.com/openloon/import?iconset=` prefix and keep only the `https://raw.githubusercontent.com/...` part.

**Step 3: Edit the config**

Open `Surge.conf`, find the target proxy group, and replace or add the `icon-url` parameter:

```ini
# Before
YouTube = select, Automatic, ..., icon-url=https://old-icon.png

# After
YouTube = select, Automatic, ..., icon-url=https://raw.githubusercontent.com/xxx/YouTube.png
```

**Step 4: Reload config**

Reload the configuration file in Surge for the new icons to take effect.

---

## 📄 Credits

- [Surge](https://nssurge.com)
- [blackmatrix7](https://github.com/blackmatrix7)
- [Skk.moe](https://github.com/Skk.moe)
- [lige47/QuanX-icon-rule](https://github.com/lige47/QuanX-icon-rule)

---

## 📄 License

**MIT**

---

<p align="center">
  <sub>Made with ❤️ for better internet experience</sub>
</p>
