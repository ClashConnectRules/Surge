# Steve's Surge Configuration

一个现代化的 Surge 配置文件，采用最新的配置标准和最佳实践。

## 📋 配置特点

### 🔧 技术特性

- **IPv6 支持**: 启用 IPv6 以获得更好的网络性能
- **加密 DNS**: 集成 DoH (DNS over HTTPS) 服务
- **智能分流**: 基于地区和服务的精确路由
- **广告拦截**: 内置广告和恶意网站过滤
- **性能优化**: 优化的规则顺序和测试参数

### 🌍 地区分组

- 🇭🇰 香港节点组
- 🇹🇼 台湾节点组
- 🇯🇵 日本节点组
- 🇸🇬 新加坡节点组
- 🇺🇸 美国节点组
- 🇬🇧 英国节点组
- 🇰🇷 韩国节点组

### 📱 服务分流

- **流媒体**: Netflix, Disney+, YouTube, TikTok, Bilibili
- **社交媒体**: Twitter/X, Telegram, Instagram, Facebook
- **AI 服务**: ChatGPT, Gemini, Claude 等
- **苹果服务**: App Store, Apple TV, Apple News
- **微软服务**: OneDrive, Microsoft 365, Bing
- **开发工具**: GitHub, Vercel, Sub-Store

## 🚀 快速开始

### 1. 下载配置

```bash
# 下载最新配置文件
curl -o Surge.conf https://raw.githubusercontent.com/ClashConnectRules/Surge/main/Surge.conf
```

或直接使用配置链接：

```
https://raw.githubusercontent.com/ClashConnectRules/Surge/main/Surge.conf
```

### 2. 配置订阅

编辑配置文件，找到以下行：

```
AllServer = select, policy-path=你的订阅链接, update-interval=0, ...
```

将 `你的订阅链接` 替换为你的机场订阅地址。

### 3. 导入 Surge

1. 打开 Surge 应用
2. 点击 "配置" → "从 URL 下载配置"
3. 输入配置文件地址或选择本地文件
4. 根据需要调整策略组设置

## ⚙️ 配置说明

### General 区域

- **测试 URL**: 使用 Cloudflare 等稳定服务进行连通性测试
- **GeoIP 数据库**: 使用 Hackl0us 维护的中国优化版本
- **DNS 服务器**: 组合使用阿里 DNS 和腾讯 DNS
- **加密 DNS**: 支持 DoH 查询以提高隐私性

### 代理组策略

- **NoAuto**: 手动选择模式
- **Automatic**: 自动测速选择最优节点
- **地区组**: 基于延迟自动选择对应地区最快节点
- **服务组**: 针对特定服务优化的策略组

### 规则优先级

1. **广告拦截**: 最高优先级，过滤广告和恶意内容
2. **AI 服务**: OpenAI、Google AI、Claude 等
3. **Apple 服务**: App Store、iCloud、Apple TV 等
4. **流媒体**: 按地区分流各种视频平台
5. **社交通讯**: Telegram、Twitter、WeChat 等
6. **全球加速**: 其他需要代理的国际服务
7. **中国直连**: 国内网站和服务直连

## 🔒 隐私与安全

- **广告拦截**: 内置多重广告过滤规则
- **恶意网站拦截**: 阻止已知的恶意域名
- **DNS 劫持防护**: 防止 DNS 污染
- **HTTPS 强制**: 自动将 HTTP 请求重定向到 HTTPS

## 📊 性能优化

- **规则顺序优化**: 按使用频率排序规则以减少匹配时间
- **域名集合**: 使用 DOMAIN-SET 提高域名匹配效率
- **智能测速**: 定期测试节点延迟自动选择最优路径
- **UDP 优化**: 针对游戏和语音通话优化 UDP 流量

## 🛠️ 自定义配置

### 添加自建节点

在 `[Proxy]` 区域添加你的自建节点：

```
🇰🇷 Korea_Snell = snell, 服务器地址, 端口, psk=密钥, version=4
```

### 修改策略组

根据需要调整各策略组的节点选择：

```
Netflix = select, 香港节点, 台湾节点, 新加坡节点
```

### 添加自定义规则

在相应区域添加特定域名或应用的分流规则：

```
DOMAIN-SUFFIX,example.com,Proxy
```

## 🔄 更新日志

### v2026.01 (2025-07-27)

- ✨ 全面重构配置文件结构
- 🆙 更新至最新 Surge 配置语法
- 🛡️ 增强广告拦截和隐私保护
- ⚡ 优化规则匹配性能
- 🌐 添加 IPv6 和加密 DNS 支持
- 📱 更新流媒体和服务分流规则

## 🤝 贡献

欢迎提交 Issue 和 Pull Request 来改进这个配置文件。

## 📄 许可证

本项目采用 MIT 许可证。

## ⚠️ 免责声明

本配置文件仅供学习和研究使用，请遵守当地法律法规。使用者需要自行承担使用风险。
