# 🐱 Mihomo 定制化配置

<div align="center">

[![Stars](https://img.shields.io/github/stars/YOUR_USERNAME/YOUR_REPO?style=flat-square&logo=github&label=Stars&color=2ea44f)](https://github.com/YOUR_USERNAME/YOUR_REPO/stargazers)
[![Forks](https://img.shields.io/github/forks/YOUR_USERNAME/YOUR_REPO?style=flat-square&logo=github&label=Forks&color=181717)](https://github.com/YOUR_USERNAME/YOUR_REPO/network/members)
[![License](https://img.shields.io/github/license/YOUR_USERNAME/YOUR_REPO?style=flat-square&color=546e7a)](./LICENSE)

**完整版通用进阶配置 | 流媒体解锁 | 广告拦截 | AI服务分流 | 国内网站加速**

[📖 使用说明](./使用说明.md) • [🔧 优化说明](./优化说明.md) • [📋 审查报告](./审查报告.md)

</div>

---

## ✨ 特性

- ✅ **完整版全功能** - 26个策略组，覆盖各种使用场景
- ✅ **流媒体解锁** - Netflix、YouTube、Disney+、Emby 专属策略组
- ✅ **广告拦截** - 双重规则（Loyalsoldier + ACL4SSR）
- ✅ **AI 服务分流** - ChatGPT、Claude、Gemini 等独立策略
- ✅ **国内网站加速** - 抖音、小红书、B站等直连，秒开
- ✅ **自动测速** - 8个地区节点组，每5分钟自动选择最快节点
- ✅ **TUN 模式** - 系统级代理，接管所有流量

---

## 🚀 快速开始

### 1️⃣ 下载配置文件

```bash
# 克隆仓库
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO

# 或直接下载配置文件
wget https://raw.githubusercontent.com/YOUR_USERNAME/YOUR_REPO/main/Custom_Mihomo_Config.yaml
```

### 2️⃣ 填入订阅链接

编辑 `Custom_Mihomo_Config.yaml`，找到以下部分：

```yaml
proxy-providers:
  Subscribe1:
    url: "http://your-service-provider-url"  # ← 替换为你的订阅链接
```

### 3️⃣ 导入配置

- **Clash Verge/Clash Verge Rev**: 配置 → 导入配置 → 选择文件
- **ClashX Pro**: 配置 → 托管配置 → 本地文件
- **Clash Meta for Android**: 配置 → 从文件导入

### 4️⃣ 选择策略

推荐日常使用 `🔄 自动选择` 策略组，自动选择延迟最低的节点。

---

## 📊 配置概览

### 策略组分类

| 类型 | 数量 | 说明 |
|------|------|------|
| 🔄 自动选择 | 9个 | 8个地区节点组 + 全局自动 |
| ✋ 手动选择 | 15个 | 功能分流策略组 |
| ⚡ 故障转移 | 1个 | 自动故障切换 |
| 🔀 负载均衡 | 1个 | 流量分散 |

### 主要功能策略组

- **流媒体**: YouTube、Netflix、Disney+、Emby、国际媒体
- **AI服务**: OpenAI、Claude、Gemini等
- **社交平台**: Telegram、Twitter
- **常用服务**: Microsoft、Apple、Google、游戏平台

### 地区节点组（全部自动测速）

🇭🇰 香港 | 🇺🇸 美国 | 🇸🇬 新加坡 | 🇯🇵 日本 | 🇹🇼 台湾 | 🇰🇷 韩国 | 🇬🇧 英国 | 🇪🇺 欧盟

**测速参数**: 300秒间隔 / 50ms容差 / 懒加载

---

## 🎯 规则优先级

```
1. 广告拦截（Reject + Advertising）
2. 局域网直连（Private）
3. 国内服务直连（Douyin、BiliBili、WeChat、ChinaMedia、Download）← 优化重点
4. 国内域名直连（Direct）
5. 功能分流（AI、流媒体、社交、常用服务）
6. 国外代理（Proxy）
7. 国内IP直连（China + GEOIP,CN）← 双重保障
8. 兜底规则（MATCH）
```

### 🇨🇳 国内网站加速

**新增5个国内服务规则**，确保以下服务直连：

| 规则 | 覆盖服务 |
|------|---------|
| Douyin | 抖音、TikTok国内版 |
| BiliBili | 哔哩哔哩（含港澳台） |
| WeChat | 微信、QQ、腾讯服务 |
| ChinaMedia | 小红书、快手、知乎、微博等 |
| Download | 迅雷、网盘、BT/PT下载 |

**优化效果**：
- ✅ 抖音视频秒开
- ✅ 小红书图片瞬间加载
- ✅ B站视频流畅播放
- ✅ 微信视频通话低延迟

---

## 📋 规则来源

本配置使用以下优质规则源：

- [Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules) - 综合分流规则
- [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script) - 流媒体和服务规则
- [ACL4SSR](https://github.com/ACL4SSR/ACL4SSR) - 广告拦截规则
- [Repcz/Tool](https://github.com/Repcz/Tool) - AI服务和Emby规则

规则每 **24小时自动更新**，无需手动维护。

---

## 🛠️ 常见问题

### 1. 节点列表为空？

**解决**: 检查订阅链接是否正确填写，确认订阅链接可访问。

### 2. 国内网站加载慢？

**解决**: 本配置已优化国内规则优先级，应该不会出现此问题。如仍然慢，检查DNS设置。

### 3. TUN 模式无法启动？

**解决**: 
- Windows: 右键管理员身份运行客户端
- macOS: 系统设置中授予完全磁盘访问权限
- 或暂时关闭TUN模式（配置中改为 `enable: false`）

### 4. 部分网站无法访问？

**解决**: 在配置文件 `rules` 部分添加自定义规则：
```yaml
- DOMAIN-SUFFIX,example.com,DIRECT  # 强制直连
- DOMAIN-SUFFIX,example.com,🌍 国外流量  # 强制代理
```

更多问题请查看 [使用说明.md](./使用说明.md)

---

## 📂 文件说明

| 文件 | 说明 |
|------|------|
| `Custom_Mihomo_Config.yaml` | 主配置文件 |
| `使用说明.md` | 详细使用指南 |
| `优化说明.md` | 国内网站加速优化详情 |
| `审查报告.md` | 配置审查报告 |
| `LICENSE` | MIT 开源协议 |

---

## 🔄 更新日志

### v1.1 (2026-06-15) - 国内网站加速优化

**新增**:
- ✅ Douyin（抖音）规则
- ✅ BiliBili（哔哩哔哩）规则
- ✅ WeChat（微信）规则
- ✅ ChinaMedia（国内媒体）规则
- ✅ Download（下载服务）规则

**优化**:
- ✅ 调整规则优先级，国内服务规则提前
- ✅ 优化规则顺序，确保国内流量直连
- ✅ 修复国内网站（抖音、小红书）加载慢的问题

### v1.0 (2026-06-15) - 初始版本

**功能**:
- ✅ 完整版全功能配置
- ✅ 流媒体解锁
- ✅ 广告拦截
- ✅ AI服务分流
- ✅ TUN模式支持
- ✅ 自动测速策略

---

## 💡 使用建议

### 日常使用

- **策略组**: `🔄 自动选择`（自动选择最快节点）
- **流媒体**: 根据平台选择对应策略组
- **AI服务**: 使用 `🤖 AI 服务` 策略组
- **稳定性优先**: 选择 `⚡ 故障转移` 策略组

### 进阶优化

1. **性能优先**: 选择 `🔀 负载均衡`
2. **精确控制**: 选择 `🚀 手动切换` 并自选节点
3. **地区锁定**: 直接使用地区节点组（如 `🇭🇰 香港节点`）

---

## 📞 支持

- 查看 [使用说明.md](./使用说明.md) 了解详细配置
- 查看 [优化说明.md](./优化说明.md) 了解优化详情
- 提交 [Issue](https://github.com/YOUR_USERNAME/YOUR_REPO/issues) 反馈问题

---

## 📜 许可证

本项目采用 [MIT License](./LICENSE) 开源协议。

---

## 🙏 致谢

感谢以下项目的贡献：

- [HenryChiao/MIHOMO_YAMLS](https://github.com/HenryChiao/MIHOMO_YAMLS)
- [MetaCubeX/mihomo](https://github.com/MetaCubeX/mihomo)
- [Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)
- [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script)

---

## ⚠️ 免责声明

本项目仅供学习交流使用，请遵守当地法律法规。使用本配置产生的任何后果由使用者自行承担。

---

<div align="center">

**如果这个项目对你有帮助，请点亮右上角的 ⭐ Star 支持一下！**

Made with ❤️ by [YOUR_NAME]

</div>
