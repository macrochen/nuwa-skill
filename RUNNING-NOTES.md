# 运行注意事项

## 目录路径
- 本系统 Skill 主目录为 `<skills-root>/`（由 AGENTS.md 声明）
- SKILL.md 模板中提到的 `.claude/skills/` 在本系统不适用，创建目录时请用 AGENTS.md 中声明的路径

## Agent 文件写入失败处理
子 Agent 调用 `write_file` 时可能遗漏 `content` 参数，导致创建空文件。
**应对**：Agent 任务完成后，立即检查文件大小（`ls -la`），空文件需基于 Agent 返回的 summary 手动补充内容。

## Phase 5 双Agent精炼
Phase 5 是可选后置工序。在实际运行中，如果 Phase 4 质量自检全部通过且用户急于交付，可跳过 Phase 5 直接交付。
