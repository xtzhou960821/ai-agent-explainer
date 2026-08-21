# AI Agent 工作原理 · 一份视觉化指南

> 以可视化的方式理解 AI Agent 如何感知、推理、行动与学习——从大模型到自主智能体，逐层拆解其工作原理。

📖 **在线预览：<https://xtzhou960821.github.io/ai-agent-explainer/>**

单文件、零依赖的静态网页指南，用直觉化的图表、代码示例与 FAQ，把"Agent = Model + Harness"这件事讲清楚。

---

## ✨ 页面内容

| 章节 | 内容 |
|------|------|
| 工作原理（How It Works） | 感知 → 推理 → 行动 → 学习 的自主循环四阶段 |
| 六大组件 | 核心大模型、记忆系统、工具调用、规划引擎、安全与约束、反馈回路 |
| 执行流程 | 一次任务从输入到输出的完整 pipeline |
| Harness | Agent 运行的"舞台"与管家：循环编排、工具注册、状态管理、权限、重试、可观测 |
| 常用框架 | LangGraph、Google ADK、OpenAI Agents SDK、CrewAI、AutoGen、LlamaIndex、SmolAgents、Pydantic AI、Semantic Kernel，含 LangGraph / ADK 可运行代码示例与一图对比 |
| DeepSeek Harness | 2026 年爆火的开源 Agent 运行时：一切皆插件、模型可替换、与 Claude Code / Codex 的区别 |
| 进阶实践 | 评测（轨迹、回归任务、判定方式）与安全（间接注入、工具越权、白名单 + 人工审批） |
| FAQ | 14 个常见问题：Agent 与聊天机器人的区别、框架怎么选、多 Agent 是否更好、能否上生产等 |

## 🎨 设计与交互

- **设计系统**：Modern Dark / AI Purple —— 深色底 + 紫罗兰霓虹光晕，Space Grotesk + DM Sans 字体
- **动效**：滚动渐显（IntersectionObserver）、FAQ 手风琴、移动端汉堡菜单、hero 区一只发光的鲸鱼缓缓游过（尊重 `prefers-reduced-motion`）
- **无障碍**：焦点可见轮廓、`aria-expanded` / `aria-controls`、无 JS 降级（noscript 样式自动展开全部内容）

## 🚀 本地运行

页面是纯静态单文件，无需构建：

```bash
# 方式一：直接双击/浏览器打开
open index.html

# 方式二：起一个本地静态服务器（推荐，字体与路径行为更接近线上）
python3 -m http.server 8000
# 然后访问 http://localhost:8000
```

## 📦 部署（GitHub Pages）

仓库已启用 GitHub Pages（`Settings → Pages`，Source 选择 `Deploy from a branch` → `main` / root）。

推送 `main` 后约 1～2 分钟自动构建上线：

```
https://<用户名>.github.io/ai-agent-explainer/
```

> 注意：访问时路径不能省略 `/ai-agent-explainer/`，用户级站点（不带路径）未配置，会返回 404。

## 📁 项目结构

```
├── index.html                  # 整站（样式、结构、脚本全在这一文件里）
├── design-system/ai-agent/     # 设计系统主文件（配色 / 字体 / 规范）
├── docs/superpowers/specs/     # 设计规格文档
└── README.md
```

## 🔧 技术栈

- 原生 HTML + CSS + 少量原生 JavaScript（无框架、无构建步骤）
- Google Fonts（Space Grotesk / DM Sans）
- SVG 内联图形（图标、流程示意图、鲸鱼动效）
