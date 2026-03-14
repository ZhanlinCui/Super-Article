<p align="center">
  <img src="https://img.shields.io/badge/Super--Article-AI%20Writing%20Skills-blue?style=for-the-badge" alt="Super-Article" />
</p>

<h1 align="center">Super-Article</h1>
<p align="center">
  <strong>一站式 AI 公众号写作与发布 Skills</strong>
</p>
<p align="center">
  检索 → 写作 → 审稿 → 润色 → 配图 → 转 HTML → 草稿箱发布
</p>

<p align="center">
  <a href="#-快速开始">快速开始</a> •
  <a href="#-技能清单">技能清单</a> •
  <a href="#-安装方式">安装方式</a> •
  <a href="#-使用场景">使用场景</a> •
  <a href="#-环境配置">环境配置</a>
</p>

---

## ✨ 一句话介绍

**Super-Article** 是一套面向 [OpenCode](https://github.com/open-code-models/opencode)、[Claude Code](https://claude.ai) 等 AI 编码工具的 **Agent Skills**，让 AI 从主题到公众号草稿箱，全自动完成文章创作全流程。

## 🚀 快速开始

```bash
# 安装主写作技能（检索 + 初稿 + 审稿 + 润色）
npx skills add https://github.com/ZhanlinCui/Super-Article --skill wechat-writing

# 一条龙：写作 + 配图 + 转 HTML + 发草稿箱
npx skills add https://github.com/ZhanlinCui/Super-Article \
  --skill wechat-writing \
  --skill article-illustrator \
  --skill markdown2wechat \
  --skill wechat-publish
```

## 📦 技能清单

| 技能 | 能力 | 依赖 |
|------|------|------|
| **wechat-writing** | 检索资料、证据池、初稿、审稿、润色 | 无 |
| **article-illustrator** | 高完成度配图、统一风格、七牛云上传 | 生图 API |
| **markdown2wechat** | Markdown → 微信内联 HTML、7 套主题 | 无 |
| **wechat-publish** | 草稿箱上传、自动封面、正文图片处理 | 微信 API |

## 📥 安装方式

### 按需安装

```bash
# 只写文章（输出 Markdown）
npx skills add https://github.com/ZhanlinCui/Super-Article --skill wechat-writing

# 写文章 + 转公众号 HTML
npx skills add https://github.com/ZhanlinCui/Super-Article \
  --skill wechat-writing --skill markdown2wechat

# 完整链路（写作 + 配图 + HTML + 草稿箱）
npx skills add https://github.com/ZhanlinCui/Super-Article \
  --skill wechat-writing \
  --skill article-illustrator \
  --skill markdown2wechat \
  --skill wechat-publish
```

### 安装到指定 Agent

```bash
npx skills add https://github.com/ZhanlinCui/Super-Article --skill wechat-writing -a opencode
```

### 查看可用技能

```bash
npx skills add https://github.com/ZhanlinCui/Super-Article --list
```

## 🎯 使用场景

| 场景 | 推荐技能组合 |
|------|-------------|
| 只需 Markdown 成稿 | `wechat-writing` |
| 需要公众号排版 HTML | `wechat-writing` + `markdown2wechat` |
| 需要配图 | `wechat-writing` + `article-illustrator` |
| 一条龙到草稿箱 | 全部 4 个技能 |

## ⚙️ 环境配置

### 前置要求

- **Node.js** ≥ 16
- 支持 `SKILL.md` 的 Agent 工具（OpenCode / Claude Code 等）
- 配图/封面：建议安装 **Bun**
- 草稿箱发布：公网 IP 需加入公众号后台白名单

### 配置说明

| 技能 | 是否需要 .env |
|------|---------------|
| wechat-writing | 否 |
| markdown2wechat | 否 |
| article-illustrator | 是（生图 API；可选七牛云） |
| wechat-publish | 是（微信 AppID/Secret；可选生图） |

有 `.env.example` 的技能，复制后填入配置即可：

```bash
cp .env.example .env
```

### 常用环境变量

**微信草稿箱**：`WECHAT_APP_ID`、`WECHAT_APP_SECRET`  
**生图**：`IMAGE_PROVIDER` / `XIAOMI_API_KEY` / `GEMINI_API_KEY` / `OPENAI_API_KEY`  
**七牛云**：`QINIU_ACCESS_KEY`、`QINIU_SECRET_KEY`、`QINIU_BUCKET`、`QINIU_DOMAIN`

## 📁 项目结构

```
skills/
├── wechat-writing/      # 主写作
├── article-illustrator/ # 配图
├── markdown2wechat/     # Markdown → HTML
└── wechat-publish/      # 草稿箱发布
```

## 🔒 安全提示

- 勿提交 `.env` 及真实密钥
- 勿提交生成产物（文章、图片、HTML）
- 误提交密钥后请及时轮换

## 📄 License

MIT © [Super-Article](https://github.com/ZhanlinCui/Super-Article)

---

<p align="center">
  <sub>如果这个项目对你有帮助，欢迎 ⭐ Star 支持</sub>
</p>
