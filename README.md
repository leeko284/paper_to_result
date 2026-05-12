# paper_to_result

本仓库用于在 `E:\Items\paper_to_result` 项目内维护论文精读、笔记整理和论文汇报大纲生成的 Codex 本地 Skill。核心能力集中在 `paper-insights-pro`，面向论文 PDF、论文题目、论文路径和汇报材料生成任务。

## 功能范围

- 解析论文的问题、动机、贡献、方法、模型结构、公式、实验、指标、结论和局限。
- 按模板生成结构化论文笔记。
- 根据 PPT 模板或历史汇报提炼版式风格，再生成论文汇报大纲或 Marp Markdown。
- 生成 PPT/Marp 规划时，优先使用论文原始 Figure、Table、公式作为每页论据。
- 每页汇报内容必须包含 speaker notes，用于说明页面逻辑、图表读法和结论。

## 目录结构

```text
.
├── AGENTS.md
├── README.md
└── skill/
    └── paper-insights-pro/
        ├── SKILL.md
        ├── agents/
        │   └── openai.yaml
        ├── assets/
        │   └── PPT_template/
        │       └── .gitkeep
        └── references/
            ├── PaperNote_template.md
            └── ppt_style_checklist.md
```

## 使用方式

在本项目目录中使用 Codex 时，`AGENTS.md` 会约束工作流：

1. 用户提供论文 PDF、论文名称、论文路径，或要求“总结”“笔记”“精读”“汇报”“PPT 大纲”“Marp Markdown”时，先读取 `skill/paper-insights-pro/SKILL.md`。
2. 如果存在 PPT 模板或历史 PPT，先按 `references/ppt_style_checklist.md` 提炼风格，再生成汇报大纲。
3. 生成论文汇报 PPT 或 Marp Markdown 时，必须列出每页使用的 Figure/Table/公式证据，以及对应 speaker notes。

该 Skill 是项目本地 Skill，不需要安装或复制到全局 Skill 目录。

## Git 管理策略

纳入版本管理：

- `AGENTS.md`
- `README.md`
- `.gitignore`
- `skill/paper-insights-pro/SKILL.md`
- `skill/paper-insights-pro/agents/openai.yaml`
- `skill/paper-insights-pro/references/*.md`
- `skill/paper-insights-pro/assets/PPT_template/.gitkeep`

默认忽略：

- 论文原文 PDF。
- `output/`、`outputs/`、`reports/`、`artifacts/` 等生成结果。
- 从论文中提取的图片、页面渲染、预览图。
- 本地 PPT 模板实例、生成的 PPT/Word/Excel 文件。
- 虚拟环境、缓存、临时文件和本地配置。

这样仓库只保存可复用的 Skill 规则和模板骨架，不把本地论文材料、生成结果或可能涉及版权/隐私的文件推送到 GitHub。
