---
name: memory-manager
description: "管理智能体记忆系统。Use when: 需要批量整理记忆、迁移记忆、清理过期记忆、生成对话摘要、检查记忆一致性。Memory maintenance and migration."
---

# 记忆管理技能

## 适用场景

- 对话结束时生成摘要
- 批量整理和清理记忆文件
- 迁移记忆到新项目
- 检查记忆文件的一致性和完整性

## 操作流程

### 生成对话摘要

1. 回顾当前对话的关键内容
2. 在 `memory/conversations/` 下创建 `YYYY-MM-DD.md`
3. 包含：主要话题、关键决策、待办事项

### 整理知识库

1. 读取 `memory/knowledge/` 下所有文件
2. 合并重复内容
3. 删除过期条目
4. 确保每个文件主题明确

### 迁移记忆

1. 复制整个 `memory/` 目录到目标项目
2. 修改 `memory/identity.md` 为新智能体身份
3. 在目标项目中配置 `.github/copilot-instructions.md` 引用记忆系统
4. 验证文件结构完整

### 检查一致性

1. 确认 `memory/identity.md` 存在且格式正确
2. 确认 `memory/user-profile.md` 存在且有内容
3. 确认各子目录存在
4. 检查日期格式是否统一为 `YYYY-MM-DD`

## 参考

- 记忆格式规范见 [memory instructions](../../instructions/memory.instructions.md)
- 记忆系统说明见 [memory README](../../../memory/README.md)
