# AGENTS.md instructions for E:\Items\paper_to_result

## 回答风格

1. 语言简洁、直接、信息优先；整体像人类技术专家解释问题，少铺垫、少套话、少修辞。
2. 优先在正文中把问题讲清楚；除非确有必要，否则不要追加“一句话总结”或类似总结性收尾。
3. “不是……而是……”只用于明确纠正、反驳用户前提；其他场景避免这种先否定再给结论的句式。
4. 不要机械使用固定结尾，如“如果你需要，我可以……”；仅在当前信息不足或下一步建议确有必要时再提出。
5. 不要自造概念、内部黑话、临时缩写；优先使用通用术语，必须引入新概念时只做一次简短解释。
6. 避免模板化表达、重复表述和无信息量过渡；能直接说清的，不要绕。

## 全局偏好

- MCP 工具和 Skill 自动调用：无需用户明确指示，根据需要自动调用 MCP 工具和 Skill。
- 如果使用了 MCP 或 Skill，只需在回答第一段简要说明本次使用了哪些 MCP/Skill，无需事先询问确认。

## 项目专用 Skill

### paper-insights-pro

本项目专用 Skill 路径：

```text
E:\Items\paper_to_result\skill\paper-insights-pro\SKILL.md
```

当用户在本项目中提供论文 PDF、论文名称、论文路径，或要求“总结”“笔记”“精读”“汇报”“PPT 大纲”“Marp Markdown”时，先读取并使用该本地 Skill。

如果用户提供 PPT 模板、历史 PPT，或以下目录存在模板文件，先按该 Skill 的流程提炼 PPT 风格，再生成论文汇报大纲或 Marp Markdown：

```text
E:\Items\paper_to_result\skill\paper-insights-pro\assets\PPT_template
```

生成论文汇报 PPT 或 Marp Markdown 时，必须优先截取或引用论文中的关键图表作为每页论据；无法提取图片时，要概括图表内容并标注原 Figure/Table 位置。每一页都必须添加备注，备注用于口头汇报，说明页面逻辑、图表读法和该页结论。

该 Skill 只用于本项目，不安装、不复制到全局 Skill 目录：

```text
C:\Users\leeko\.codex\skills
C:\Users\leeko\.agents\skills
```

如果全局 Skill 列表中没有 `paper-insights-pro`，这是预期行为；应通过上述项目本地路径读取。
