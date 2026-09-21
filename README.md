# lab-report-workflow 📝

> **作者**：谢泓铎 · GIS实验室　　一句话定位：给实验主题和原始数据，按七阶段流水线产出格式规范、可提交的理工科实验报告。

一个面向 AI Agent（WorkBuddy / Claude 等）的可复用 Skill，把「写实验报告」从每次从头摸索变成一条固化的流水线：预习 → 原始数据 → 处理计算 → 图表 → 讨论 → 结论 → 排版，每一步写清输入、动作、输出与校验要点。

## ✨ 功能特性

| 特性 | 说明 |
|---|---|
| 七阶段流程固化 | 每阶段：输入 → 动作 → 输出 → 校验，四元组齐全 |
| 参数化占位符 | 实验名称/课程教师/日期/数据路径/篇幅/评分标准/模板位置/软件环境，8 个 `{{VAR}}` 填空即用 |
| 强制检查点 | 数据盘点、公式假设、中间结果、结论草稿、终稿排版——5 处停下来等用户确认 |
| 不编数据纪律 | 缺数据/缺文献一律挂「待确认清单」，禁止想象填充 |
| 流程与模板分离 | 换学校模板只动 `templates/`，增删环节只动 `references/workflow.md` |
| docx 交付规范 | 改前备份、图注规范、标题导航（outlineLvl）、批量替换防坑，实战经验内置 |

## 🚀 快速开始

把整个 `lab-report-workflow/` 目录放进 Agent 的技能目录（如 WorkBuddy 的 `~/.workbuddy/skills/`），即可被自动发现加载。

调用示例（对 Agent 说）：

```
帮我写实验报告，主题是「基于ArcGIS Pro的栅格数据空间分析」，
数据在 D:\exp\data\，篇幅 2500 字左右，学校模板在 D:\template\report.docx
```

Agent 会按流程推进，并在 5 个关键节点暂停等你确认。

## 🧑‍💻 使用流程

1. **参数确认** —— Agent 列出 8 个占位符的当前值，缺的标注「待补充」
2. **数据盘点（CP1）** —— 汇报数据源概况与处理方案，等你拍板
3. **假设与公式（CP2）** → **中间结果（CP3）** —— 计算过程透明可复算
4. **结论草稿（CP4）** —— 逐条过目定性措辞
5. **终稿排版（CP5）** —— 跑完自查清单再交付 docx + 备份

## 🗂️ 目录结构

```
lab-report-workflow/
├── SKILL.md                      # 触发场景、参数表、分步清单概览、docx 交付规范
├── references/
│   ├── workflow.md               # 七阶段详细规程（输入/动作/输出/校验）
│   ├── format_rules.md           # 有效数字、单位、误差分析、图表规范
│   └── checklist.md              # 交付前自查清单（数据/计算/图表/结构/文献/排版）
└── templates/
    └── report_template.md        # 报告正文骨架（占位符 + 默认排版规格）
```

## 🛠️ 技术栈

- **载体**：Markdown（Agent Skill 格式，含 frontmatter 触发描述）
- **适用实验类型**：通用理工科；内置 GIS/ArcGIS Pro 等软件操作类实验的截图与 docx 处理经验
- **产出**：Markdown 骨架 → Word（.docx）交付

## 📄 许可

[MIT License](LICENSE)

## 👤 作者

**谢泓铎** · GIS实验室

- GitHub: [@Bo55LIKE69](https://github.com/Bo55LIKE69)
- 仓库: [lab-report-workflow](https://github.com/Bo55LIKE69/lab-report-workflow)
