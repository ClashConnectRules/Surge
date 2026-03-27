<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Surge Configuration Documentation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            line-height: 1.6;
            color: #333;
            background: #f5f7fa;
            padding: 20px;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 12px;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
            overflow: hidden;
        }
        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 40px;
            text-align: center;
        }
        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
        }
        .header p {
            opacity: 0.9;
            font-size: 1.1em;
        }
        .lang-switch {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-top: 20px;
        }
        .lang-btn {
            padding: 10px 24px;
            border: 2px solid rgba(255,255,255,0.3);
            background: rgba(255,255,255,0.1);
            color: white;
            border-radius: 25px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            transition: all 0.3s;
        }
        .lang-btn:hover {
            background: rgba(255,255,255,0.2);
        }
        .lang-btn.active {
            background: white;
            color: #667eea;
            border-color: white;
        }
        .content {
            padding: 40px;
        }
        .section {
            margin-bottom: 40px;
        }
        .section h2 {
            color: #667eea;
            font-size: 1.8em;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #e0e0e0;
        }
        .section h3 {
            color: #764ba2;
            font-size: 1.3em;
            margin: 20px 0 10px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }
        th {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: 600;
        }
        td {
            padding: 12px 15px;
            border-bottom: 1px solid #e0e0e0;
        }
        tr:hover {
            background: #f8f9fa;
        }
        code {
            background: #f4f4f4;
            padding: 2px 6px;
            border-radius: 4px;
            font-family: 'Monaco', 'Menlo', monospace;
            font-size: 0.9em;
        }
        pre {
            background: #2d2d2d;
            color: #f8f8f2;
            padding: 20px;
            border-radius: 8px;
            overflow-x: auto;
            margin: 15px 0;
        }
        pre code {
            background: transparent;
            color: inherit;
        }
        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }
        .feature-card {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #667eea;
        }
        .feature-card h4 {
            color: #667eea;
            margin-bottom: 10px;
        }
        .rule-list {
            list-style: none;
            padding: 0;
        }
        .rule-list li {
            padding: 10px 15px;
            margin: 5px 0;
            background: #f8f9fa;
            border-radius: 6px;
            border-left: 3px solid #667eea;
        }
        .badge {
            display: inline-block;
            padding: 4px 10px;
            background: #667eea;
            color: white;
            border-radius: 15px;
            font-size: 0.8em;
            margin-left: 8px;
        }
        .zh {
            display: none;
        }
        .en {
            display: block;
        }
        body.show-zh .en {
            display: none;
        }
        body.show-zh .zh {
            display: block;
        }
        .toc {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 30px;
        }
        .toc h3 {
            margin-top: 0;
            color: #667eea;
        }
        .toc ul {
            list-style: none;
            padding-left: 0;
        }
        .toc li {
            padding: 5px 0;
        }
        .toc a {
            color: #667eea;
            text-decoration: none;
        }
        .toc a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body class="show-en">
    <div class="container">
        <div class="header">
            <h1 class="en">Surge Configuration Documentation</h1>
            <h1 class="zh">Surge 配置文档</h1>
            <p class="en">Steve's Advanced Surge Proxy Configuration</p>
            <p class="zh">Steve 的高级 Surge 代理配置文件</p>
            <div class="lang-switch">
                <button class="lang-btn active" data-lang="en">English</button>
                <button class="lang-btn" data-lang="zh">中文</button>
            </div>
        </div>

        <div class="content">
            <!-- Table of Contents -->
            <div class="toc">
                <h3 class="en">Table of Contents</h3>
                <h3 class="zh">目录</h3>
                <ul>
                    <li><a href="#intro"><span class="en">Introduction</span><span class="zh">简介</span></a></li>
                    <li><a href="#features"><span class="en">Core Features</span><span class="zh">核心功能</span></a></li>
                    <li><a href="#structure"><span class="en">Configuration Structure</span><span class="zh">配置结构</span></a></li>
                    <li><a href="#general"><span class="en">General Settings</span><span class="zh">基础设置</span></a></li>
                    <li><a href="#proxy-group"><span class="en">Policy Groups</span><span class="zh">策略分组</span></a></li>
                    <li><a href="#rules"><span class="en">Routing Rules</span><span class="zh">分流规则</span></a></li>
                    <li><a href="#protocols"><span class="en">Supported Protocols</span><span class="zh">支持的协议</span></a></li>
                    <li><a href="#usage"><span class="en">Usage Instructions</span><span class="zh">使用说明</span></a></li>
                    <li><a href="#customization"><span class="en">Customization</span><span class="zh">自定义</span></a></li>
                    <li><a href="#troubleshooting"><span class="en">Troubleshooting</span><span class="zh">常见问题</span></a></li>
                </ul>
            </div>
    
            <!-- Introduction -->
            <div id="intro" class="section">
                <h2 class="en">Introduction</h2>
                <h2 class="zh">简介</h2>
                <p class="en">A fully-featured Surge proxy configuration file supporting multiple proxy protocols, intelligent traffic routing, ad blocking, streaming unlock, and more. The configuration uses bilingual Chinese-English comments for easy understanding and maintenance.</p>
                <p class="zh">这是一个功能完善的 Surge 代理配置文件，支持多种代理协议、智能分流、广告拦截、流媒体解锁等功能。配置采用中英双语注释，便于理解和维护。</p>
            </div>
    
            <!-- Core Features -->
            <div id="features" class="section">
                <h2 class="en">Core Features</h2>
                <h2 class="zh">核心功能</h2>
                <div class="feature-grid">
                    <div class="feature-card">
                        <h4 class="en">Smart Routing</h4>
                        <h4 class="zh">智能路由</h4>
                        <p class="en">Automatic traffic routing based on region and service</p>
                        <p class="zh">基于地区和服务的自动流量分流</p>
                    </div>
                    <div class="feature-card">
                        <h4 class="en">Ad Blocking</h4>
                        <h4 class="zh">广告拦截</h4>
                        <p class="en">Integrated multi-source ad rules to block ads and tracking</p>
                        <p class="zh">集成多源广告规则，有效拦截广告和追踪</p>
                    </div>
                    <div class="feature-card">
                        <h4 class="en">Streaming Unlock</h4>
                        <h4 class="zh">流媒体解锁</h4>
                        <p class="en">Support for Netflix, Disney+, YouTube, TikTok and more</p>
                        <p class="zh">支持 Netflix、Disney+、YouTube、TikTok 等主流流媒体</p>
                    </div>
                    <div class="feature-card">
                        <h4 class="en">AI Services</h4>
                        <h4 class="zh">AI 服务优化</h4>
                        <p class="en">Dedicated routing for ChatGPT, Bing AI and other AI services</p>
                        <p class="zh">针对 ChatGPT、Bing AI 等 AI 服务的专门路由</p>
                    </div>
                    <div class="feature-card">
                        <h4 class="en">Privacy Protection</h4>
                        <h4 class="zh">隐私保护</h4>
                        <p class="en">Protection against tracking and privacy leaks</p>
                        <p class="zh">防止追踪和隐私泄露</p>
                    </div>
                    <div class="feature-card">
                        <h4 class="en">Remote Management</h4>
                        <h4 class="zh">远程管理</h4>
                        <p class="en">Support for Web Dashboard and external controller</p>
                        <p class="zh">支持 Web Dashboard 和外部控制器</p>
                    </div>
                </div>
            </div>
    
            <!-- Configuration Structure -->
            <div id="structure" class="section">
                <h2 class="en">Configuration Structure</h2>
                <h2 class="zh">配置结构</h2>
                <pre><code>Steve.conf
├── [General]          <span class="zh"># 基础设置 / General Settings</span>
├── [Proxy]            <span class="zh"># 代理服务器 / Proxy Servers</span>
├── [Proxy Group]      <span class="zh"># 策略分组 / Policy Groups</span>
├── [Rule]             <span class="zh"># 分流规则 / Routing Rules</span>
├── [Host]             <span class="zh"># DNS 映射 / DNS Mapping</span>
├── [URL Rewrite]      <span class="zh"># URL 重写 / URL Rewrite</span>
├── [Header Rewrite]   <span class="zh"># 请求头修改 / Header Rewrite</span>
├── [MITM]             <span class="zh"># 中间人证书 / MITM Certificate</span>
└── [Script]           <span class="zh"># 脚本扩展 / Script Extensions</span></code></pre>
            </div>

            <!-- General Settings -->
            <div id="general" class="section">
                <h2 class="en">General Settings</h2>
                <h2 class="zh">基础设置</h2>
    
                <h3 class="en">Network Settings</h3>
                <h3 class="zh">网络设置</h3>
                <table>
                    <tr>
                        <th class="en">Setting</th>
                        <th class="zh">设置项</th>
                        <th class="en">Value</th>
                        <th class="zh">值</th>
                        <th class="en">Status</th>
                        <th class="zh">状态</th>
                    </tr>
                    <tr>
                        <td>IPv6</td>
                        <td></td>
                        <td>-</td>
                        <td></td>
                        <td><span class="badge">Disabled</span></td>
                    </tr>
                    <tr>
                        <td class="en">Wi-Fi Assist</td>
                        <td class="zh">Wi-Fi 助手</td>
                        <td>-</td>
                        <td></td>
                        <td><span class="badge" style="background:#28a745;">Enabled</span></td>
                    </tr>
                    <tr>
                        <td class="en">Hybrid Network</td>
                        <td class="zh">混合网络</td>
                        <td>-</td>
                        <td></td>
                        <td><span class="badge">Disabled</span></td>
                    </tr>
                </table>
    
                <h3 class="en">DNS Configuration</h3>
                <h3 class="zh">DNS 配置</h3>
                <table>
                    <tr>
                        <th class="en">Type</th>
                        <th class="zh">类型</th>
                        <th class="en">Server</th>
                        <th class="zh">服务器</th>
                    </tr>
                    <tr>
                        <td class="en">Primary DNS</td>
                        <td class="zh">主 DNS</td>
                        <td>223.5.5.5, 223.6.6.6 <span class="en">(Aliyun)</span><span class="zh">(阿里云)</span></td>
                    </tr>
                    <tr>
                        <td class="en">Secondary DNS</td>
                        <td class="zh">备用 DNS</td>
                        <td>119.29.29.29 <span class="en">(Tencent)</span><span class="zh">(腾讯)</span></td>
                    </tr>
                    <tr>
                        <td class="en">Encrypted DNS</td>
                        <td class="zh">加密 DNS</td>
                        <td>doh.pub, dns.alidns.com <span class="en">(DoH)</span></td>
                    </tr>
                </table>
    
                <h3 class="en">Remote Control</h3>
                <h3 class="zh">远程控制</h3>
                <table>
                    <tr>
                        <th class="en">Service</th>
                        <th class="zh">服务</th>
                        <th class="en">Address</th>
                        <th class="zh">地址</th>
                    </tr>
                    <tr>
                        <td class="en">External Controller</td>
                        <td class="zh">外部控制器</td>
                        <td><code>steve@0.0.0.0:6160</code></td>
                    </tr>
                    <tr>
                        <td>HTTP API</td>
                        <td></td>
                        <td><code>clashconnectrules@0.0.0.0:6166</code></td>
                    </tr>
                    <tr>
                        <td>Web Dashboard</td>
                        <td></td>
                        <td><span class="badge" style="background:#28a745;">Enabled</span></td>
                    </tr>
                </table>
            </div>
    
            <!-- Policy Groups -->
            <div id="proxy-group" class="section">
                <h2 class="en">Policy Groups</h2>
                <h2 class="zh">策略分组</h2>
    
                <h3 class="en">Core Policies</h3>
                <h3 class="zh">核心策略</h3>
                <table>
                    <tr>
                        <th class="en">Name</th>
                        <th class="zh">名称</th>
                        <th class="en">Type</th>
                        <th class="zh">类型</th>
                        <th class="en">Description</th>
                        <th class="zh">描述</th>
                    </tr>
                    <tr>
                        <td><code>Mainland</code></td>
                        <td></td>
                        <td>select</td>
                        <td></td>
                        <td class="en">Mainland China Direct</td>
                        <td class="zh">中国大陆直连</td>
                    </tr>
                    <tr>
                        <td><code>AllServer</code></td>
                        <td></td>
                        <td>select</td>
                        <td></td>
                        <td class="en">All servers (filter expired nodes)</td>
                        <td class="zh">全部服务器（过滤过期节点）</td>
                    </tr>
                    <tr>
                        <td><code>Automatic</code></td>
                        <td></td>
                        <td>select</td>
                        <td></td>
                        <td class="en">Region Auto-Select</td>
                        <td class="zh">地区自动选择</td>
                    </tr>
                    <tr>
                        <td><code>Proxy</code></td>
                        <td></td>
                        <td>select</td>
                        <td></td>
                        <td class="en">Main Proxy Policy</td>
                        <td class="zh">主代理策略</td>
                    </tr>
                    <tr>
                        <td><code>NoAuto</code></td>
                        <td></td>
                        <td>select</td>
                        <td></td>
                        <td class="en">Disable Auto-Select</td>
                        <td class="zh">禁用自动选择</td>
                    </tr>
                </table>
    
                <h3 class="en">Regional Groups</h3>
                <h3 class="zh">地区分组</h3>
                <table>
                    <tr>
                        <th class="en">Group</th>
                        <th class="zh">分组</th>
                        <th class="en">Test URL</th>
                        <th class="zh">测试 URL</th>
                        <th class="en">Tolerance / Interval</th>
                        <th class="zh">延迟容差 / 间隔</th>
                    </tr>
                    <tr>
                        <td><code>Hong Kong</code> 🇭🇰</td>
                        <td></td>
                        <td>Cloudflare</td>
                        <td></td>
                        <td>50ms / 300s</td>
                    </tr>
                    <tr>
                        <td><code>Taiwan</code> 🇹🇼</td>
                        <td></td>
                        <td>Cloudflare</td>
                        <td></td>
                        <td>50ms / 300s</td>
                    </tr>
                    <tr>
                        <td><code>Japan</code> 🇯🇵</td>
                        <td></td>
                        <td>Cloudflare</td>
                        <td></td>
                        <td>50ms / 300s</td>
                    </tr>
                    <tr>
                        <td><code>Singapore</code> 🇸🇬</td>
                        <td></td>
                        <td>Cloudflare</td>
                        <td></td>
                        <td>50ms / 300s</td>
                    </tr>
                    <tr>
                        <td><code>United States</code> 🇺🇸</td>
                        <td></td>
                        <td>Cloudflare</td>
                        <td></td>
                        <td>50ms / 300s</td>
                    </tr>
                    <tr>
                        <td><code>United Kingdom</code> 🇬🇧</td>
                        <td></td>
                        <td>Cloudflare</td>
                        <td></td>
                        <td>50ms / 300s</td>
                    </tr>
                    <tr>
                        <td><code>Korea</code> 🇰🇷</td>
                        <td></td>
                        <td>Cloudflare</td>
                        <td></td>
                        <td>50ms / 300s</td>
                    </tr>
                    <tr>
                        <td><code>Other</code></td>
                        <td></td>
                        <td>Cloudflare</td>
                        <td></td>
                        <td>50ms / 300s</td>
                    </tr>
                </table>
    
                <h3 class="en">App Service Policies</h3>
                <h3 class="zh">应用服务策略</h3>
                <table>
                    <tr>
                        <th class="en">App</th>
                        <th class="zh">应用</th>
                        <th class="en">Policy</th>
                        <th class="zh">策略</th>
                        <th class="en">Notes</th>
                        <th class="zh">说明</th>
                    </tr>
                    <tr>
                        <td>Apple</td>
                        <td></td>
                        <td><small>Mainland → HK → US</small></td>
                        <td></td>
                        <td class="en">Apple services smart routing</td>
                        <td class="zh">苹果服务智能分流</td>
                    </tr>
                    <tr>
                        <td>AI</td>
                        <td></td>
                        <td><small>Auto → US → JP → SG</small></td>
                        <td></td>
                        <td class="en">ChatGPT, Bing AI, etc.</td>
                        <td class="zh">ChatGPT、Bing AI 等</td>
                    </tr>
                    <tr>
                        <td>Microsoft</td>
                        <td></td>
                        <td><small>Mainland → HK → SG → US</small></td>
                        <td></td>
                        <td class="en">Microsoft services</td>
                        <td class="zh">微软全家桶</td>
                    </tr>
                    <tr>
                        <td>Telegram</td>
                        <td></td>
                        <td><small>Auto → SG → US → HK</small></td>
                        <td></td>
                        <td class="en">Telegram messaging</td>
                        <td class="zh">电报消息</td>
                    </tr>
                    <tr>
                        <td>WeChat</td>
                        <td></td>
                        <td><small>Mainland → HK → SG → US</small></td>
                        <td></td>
                        <td>WeChat / 微信</td>
                    </tr>
                    <tr>
                        <td>X (Twitter)</td>
                        <td></td>
                        <td><small>Auto → HK → TW → SG → JP → US</small></td>
                        <td></td>
                        <td class="en">Social media</td>
                        <td class="zh">社交媒体</td>
                    </tr>
                    <tr>
                        <td>Netflix</td>
                        <td></td>
                        <td><small>HK → TW → SG → JP → US</small></td>
                        <td></td>
                        <td class="en">Streaming</td>
                        <td class="zh">流媒体</td>
                    </tr>
                    <tr>
                        <td>Disney+</td>
                        <td></td>
                        <td><small>HK → SG</small></td>
                        <td></td>
                        <td class="en">Streaming</td>
                        <td class="zh">流媒体</td>
                    </tr>
                    <tr>
                        <td>YouTube</td>
                        <td></td>
                        <td><small>Auto → HK → TW → SG → JP → US</small></td>
                        <td></td>
                        <td class="en">Video platform</td>
                        <td class="zh">视频平台</td>
                    </tr>
                    <tr>
                        <td>TikTok</td>
                        <td></td>
                        <td><small>TW → SG → JP → US</small></td>
                        <td></td>
                        <td class="en">Short video</td>
                        <td class="zh">短视频</td>
                    </tr>
                    <tr>
                        <td>Bilibili</td>
                        <td></td>
                        <td><small>Mainland → HK → TW</small></td>
                        <td></td>
                        <td>Bilibili / 哔哩哔哩</td>
                    </tr>
                    <tr>
                        <td>Speedtest</td>
                        <td></td>
                        <td><small>Mainland → Auto → AllServer</small></td>
                        <td></td>
                        <td class="en">Speed test</td>
                        <td class="zh">网速测试</td>
                    </tr>
                </table>
            </div>
    
            <!-- Routing Rules -->
            <div id="rules" class="section">
                <h2 class="en">Routing Rules</h2>
                <h2 class="zh">分流规则</h2>
                <p class="en">Rules are sorted by priority. Earlier rules have higher priority.</p>
                <p class="zh">规则按优先级排序，越靠前优先级越高。</p>
    
                <ul class="rule-list">
                    <li><span class="en">Unbreak Rules</span><span class="zh">规则修正</span> <code>→ DIRECT</code></li>
                    <li><span class="en">Ad Blocking</span><span class="zh">广告拦截</span> <code>→ REJECT</code></li>
                    <li><span class="en">Privacy Protection</span><span class="zh">隐私保护</span> <code>→ REJECT / DIRECT</code></li>
                    <li><span class="en">Mainland Apps</span><span class="zh">国内应用</span> <code>→ WeChat / Bilibili / Mainland</code></li>
                    <li><span class="en">Apple Services</span><span class="zh">Apple 服务</span> <code>→ DIRECT / Apple / US</code></li>
                    <li><span class="en">AI Services</span><span class="zh">AI 服务</span> <code>→ AI</code></li>
                    <li><span class="en">Intl Streaming</span><span class="zh">国外流媒体</span> <code>→ Disney+ / Netflix / TikTok / YouTube</code></li>
                    <li><span class="en">Regional Streaming</span><span class="zh">地区流媒体解锁</span> <code>→ US / UK / JP / KR / HK / TW</code></li>
                    <li><span class="en">Social Media</span><span class="zh">国外社交媒体</span> <code>→ X / Telegram / Automatic</code></li>
                    <li><span class="en">Other Services</span><span class="zh">其他国外服务</span> <code>→ Automatic / Specific Policy</code></li>
                    <li><span class="en">Mainland China</span><span class="zh">国内规则</span> <code>→ Mainland</code></li>
                    <li><span class="en">Global</span><span class="zh">国外规则</span> <code>→ Automatic</code></li>
                    <li><span class="en">Network Optimization</span><span class="zh">网络优化</span> <code>→ REJECT-NO-DROP / DIRECT</code></li>
                    <li><span class="en">LAN</span><span class="zh">本地网络</span> <code>→ DIRECT</code></li>
                    <li><span class="en">Final Rule</span><span class="zh">兜底规则</span> <code>→ NoAuto</code></li>
                </ul>
            </div>
    
            <!-- Supported Protocols -->
            <div id="protocols" class="section">
                <h2 class="en">Supported Proxy Protocols</h2>
                <h2 class="zh">支持的代理协议</h2>
    
                <h3 class="en">Standard Protocols</h3>
                <h3 class="zh">标准协议</h3>
                <table>
                    <tr>
                        <th class="en">Protocol</th>
                        <th class="zh">协议</th>
                        <th class="en">Description</th>
                        <th class="zh">描述</th>
                    </tr>
                    <tr><td>HTTP / HTTPS</td><td></td><td class="en">Standard HTTP proxy</td><td class="zh">标准 HTTP 代理</td></tr>
                    <tr><td>SOCKS5 / SOCKS5-TLS</td><td></td><td class="en">SOCKS5 with/without TLS</td><td class="zh">带/不带 TLS 的 SOCKS5</td></tr>
                    <tr><td>SSH</td><td></td><td class="en">SSH tunnel</td><td class="zh">SSH 隧道</td></tr>
                    <tr><td>WireGuard</td><td></td><td class="en">Layer 3 VPN</td><td class="zh">三层 VPN</td></tr>
                </table>
    
                <h3 class="en">Community Protocols</h3>
                <h3 class="zh">社区协议</h3>
                <table>
                    <tr>
                        <th class="en">Protocol</th>
                        <th class="zh">协议</th>
                        <th class="en">Description</th>
                        <th class="zh">描述</th>
                    </tr>
                    <tr><td>Snell</td><td></td><td class="en">High-performance proxy</td><td class="zh">高性能代理</td></tr>
                    <tr><td>Shadowsocks</td><td></td><td class="en">Popular proxy protocol</td><td class="zh">流行的代理协议</td></tr>
                    <tr><td>VMess</td><td></td><td class="en">V2Ray protocol</td><td class="zh">V2Ray 协议</td></tr>
                    <tr><td>Trojan</td><td></td><td class="en">Trojan protocol</td><td class="zh">Trojan 协议</td></tr>
                    <tr><td>TUIC</td><td></td><td class="en">TUIC protocol</td><td class="zh">TUIC 协议</td></tr>
                    <tr><td>Hysteria 2</td><td></td><td class="en">Hysteria v2 protocol</td><td class="zh">Hysteria v2 协议</td></tr>
                    <tr><td>AnyTLS</td><td></td><td class="en">AnyTLS protocol</td><td class="zh">AnyTLS 协议</td></tr>
                </table>
            </div>
    
            <!-- Usage Instructions -->
            <div id="usage" class="section">
                <h2 class="en">Usage Instructions</h2>
                <h2 class="zh">使用说明</h2>
    
                <h3 class="en">Installation Steps</h3>
                <h3 class="zh">安装步骤</h3>
                <ol>
                    <li>
                        <p class="en"><strong>Download Configuration</strong> - Place <code>Steve.conf</code> in the Surge configuration directory.</p>
                        <p class="zh"><strong>下载配置</strong> - 将 <code>Steve.conf</code> 放置到 Surge 配置目录。</p>
                    </li>
                    <li>
                        <p class="en"><strong>Configure Proxy Servers</strong> - Add your proxy servers in the [Proxy] section. See supported protocols above.</p>
                        <p class="zh"><strong>配置代理服务器</strong> - 在 [Proxy] 部分添加你的代理服务器。支持的协议见上方文档。</p>
                    </li>
                    <li>
                        <p class="en"><strong>Enable MITM</strong> - Install and trust the Surge CA certificate. Go to Settings → MITM → Enable.</p>
                        <p class="zh"><strong>启用 MITM</strong> - 安装并信任 Surge CA 证书。设置 → MITM → 开启。</p>
                    </li>
                    <li>
                        <p class="en"><strong>Update Subscription</strong> - If using external subscription, set update interval. Recommended: 300-600 seconds.</p>
                        <p class="zh"><strong>更新订阅</strong> - 如使用外部订阅，设置更新间隔。建议间隔: 300-600 秒。</p>
                    </li>
                </ol>
    
                <h3 class="en">Update Rules</h3>
                <h3 class="zh">更新规则</h3>
                <p class="en">Most rules use online sources and update automatically.</p>
                <p class="zh">大部分规则使用在线源，会自动更新。</p>
                <p class="en"><strong>Manual update:</strong> Surge Dashboard → Scripts → Run, or restart Surge.</p>
                <p class="zh"><strong>手动更新:</strong> Surge Dashboard → 脚本 → 运行，或重启 Surge。</p>
            </div>
    
            <!-- Customization -->
            <div id="customization" class="section">
                <h2 class="en">Customization</h2>
                <h2 class="zh">自定义</h2>
    
                <h3 class="en">Add Custom Rules</h3>
                <h3 class="zh">添加自定义规则</h3>
                <p class="en">Add in [Rule] section:</p>
                <p class="zh">在 [Rule] 部分添加:</p>
                <pre><code><span class="en"># Domain Rule</span><span class="zh"># 域名规则</span>
DOMAIN,example.com,POLICY

<span class="en"># Keyword Rule</span><span class="zh"># 关键字规则</span>
DOMAIN-KEYWORD,keyword,POLICY

<span class="en"># Suffix Rule</span><span class="zh"># 后缀规则</span>
DOMAIN-SUFFIX,example.com,POLICY

<span class="en"># IP Rule</span><span class="zh"># IP 规则</span>
IP-CIDR,1.2.3.4/24,POLICY

<span class="en"># Rule Set</span><span class="zh"># 规则集</span>
RULE-SET,https://example.com/ruleset.conf,POLICY</code></pre>

                <h3 class="en">Add Custom Proxy</h3>
                <h3 class="zh">添加自定义代理</h3>
                <p class="en">Add in [Proxy] section:</p>
                <p class="zh">在 [Proxy] 部分添加:</p>
                <pre><code><span class="en"># Shadowsocks Example</span><span class="zh"># Shadowsocks 示例</span>
MySS = ss, 1.2.3.4, 8388, encrypt-method=aes-256-gcm, password=your-password

<span class="en"># VMess Example</span><span class="zh"># VMess 示例</span>
MyVMess = vmess, 1.2.3.4, 443, username=your-uuid, ws=true, ws-path=/path

<span class="en"># Trojan Example</span><span class="zh"># Trojan 示例</span>
MyTrojan = trojan, example.com, 443, password=your-password</code></pre>
            </div>

            <!-- Troubleshooting -->
            <div id="troubleshooting" class="section">
                <h2 class="en">Troubleshooting</h2>
                <h2 class="zh">常见问题</h2>
    
                <table>
                    <tr>
                        <th class="en">Problem</th>
                        <th class="zh">问题</th>
                        <th class="en">Solution</th>
                        <th class="zh">解决方法</th>
                    </tr>
                    <tr>
                        <td class="en">Cannot connect to proxy</td>
                        <td class="zh">无法连接代理</td>
                        <td>
                            <span class="en">1. Check proxy server configuration<br>2. Confirm proxy server is online<br>3. Check network connection</span>
                            <span class="zh">1. 检查代理服务器配置<br>2. 确认代理服务器在线<br>3. 检查网络连接</span>
                        </td>
                    </tr>
                    <tr>
                        <td class="en">Streaming not unlocked</td>
                        <td class="zh">流媒体无法解锁</td>
                        <td>
                            <span class="en">1. Ensure proxy node supports streaming<br>2. Try switching to regional policy<br>3. Clear app cache</span>
                            <span class="zh">1. 确保代理节点支持流媒体解锁<br>2. 尝试切换到对应地区的策略组<br>3. 清除应用缓存</span>
                        </td>
                    </tr>
                    <tr>
                        <td>MITM not working</td>
                        <td></td>
                        <td>
                            <span class="en">1. Confirm Surge CA certificate is installed and trusted<br>2. Check MitM hostname includes target domain<br>3. Restart Surge</span>
                            <span class="zh">1. 确认已安装并信任 Surge CA 证书<br>2. 检查 MitM 主机名是否包含目标域名<br>3. 重启 Surge</span>
                        </td>
                    </tr>
                    <tr>
                        <td class="en">Rules not working</td>
                        <td class="zh">规则不生效</td>
                        <td>
                            <span class="en">1. Check rule order (top to bottom priority)<br>2. Confirm rule syntax is correct<br>3. Check logs for match status</span>
                            <span class="zh">1. 检查规则顺序，优先级从上到下<br>2. 确认规则语法正确<br>3. 查看日志确认匹配情况</span>
                        </td>
                    </tr>
                </table>
            </div>
    
            <!-- Credits -->
            <div class="section">
                <h2 class="en">Credits</h2>
                <h2 class="zh">致谢</h2>
                <table>
                    <tr>
                        <th class="en">Project</th>
                        <th class="zh">项目</th>
                        <th class="en">Link</th>
                        <th class="zh">链接</th>
                    </tr>
                    <tr>
                        <td>Surge</td>
                        <td></td>
                        <td><a href="https://nssurge.com" target="_blank">nssurge.com</a></td>
                    </tr>
                    <tr>
                        <td class="en">Rule Sources</td>
                        <td class="zh">规则源</td>
                        <td>blackmatrix7, Skk.moe, Semporia, VirgilClyne, zxfccmm4</td>
                    </tr>
                    <tr>
                        <td class="en">Icons</td>
                        <td class="zh">图标</td>
                        <td><a href="https://github.com/lige47/QuanX-icon-rule" target="_blank">lige47/QuanX-icon-rule</a></td>
                    </tr>
                </table>
                <p class="en" style="margin-top: 20px; color: #666;"><strong>License:</strong> MIT License</p>
                <p class="zh" style="margin-top: 20px; color: #666;"><strong>许可证:</strong> MIT License</p>
                <p style="margin-top: 10px; color: #999;"><span class="en">Last Updated: March 27, 2026</span><span class="zh">最后更新: 2026年3月27日</span></p>
            </div>
        </div>
    </div>
    
    <script>
        // Language switcher
        const langButtons = document.querySelectorAll('.lang-btn');
    
        langButtons.forEach(btn => {
            btn.addEventListener('click', () => {
                const lang = btn.getAttribute('data-lang');
    
                // Update button states
                langButtons.forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
    
                // Update body class
                if (lang === 'zh') {
                    document.body.classList.remove('show-en');
                    document.body.classList.add('show-zh');
                } else {
                    document.body.classList.remove('show-zh');
                    document.body.classList.add('show-en');
                }
    
                // Save preference to localStorage
                localStorage.setItem('preferred-lang', lang);
            });
        });
    
        // Load saved language preference
        const savedLang = localStorage.getItem('preferred-lang');
        if (savedLang) {
            const targetBtn = document.querySelector(`.lang-btn[data-lang="${savedLang}"]`);
            if (targetBtn) {
                targetBtn.click();
            }
        }
    </script>
</body>
</html>