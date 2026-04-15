---
description: "Use when: 读写记忆文件、更新用户偏好、记录知识、管理对话摘要、追踪任务。Memory management for the agent memory system."
applyTo: "memory/**"
---

# 记忆文件管理规范

## 读取规则

- 对话开始时，先读 `memory/identity.md` 和 `memory/user-profile.md`
- 有进行中的任务时，读 `memory/tasks/` 下相关文件
- 需要特定知识时，读 `memory/knowledge/` 下相关文件

## 写入规则

### 格式要求

每条记忆一行，格式：
```
- [YYYY-MM-DD] 具体内容
```

### 更新 user-profile.md

当用户表达偏好时，在对应分类下添加新条目：
```markdown
## 偏好
- [2026-04-15] 喜欢简洁的代码风格
```

### 创建知识文件

在 `memory/knowledge/` 下按主题创建：
```markdown
# Python 知识

## 常用库
- [2026-04-15] 用户常用 FastAPI 做后端

## 踩过的坑
- [2026-04-15] asyncio 在 Windows 上需要设置事件循环策略
```

### 创建对话摘要

在 `memory/conversations/` 下按日期创建：
```markdown
# 2026-04-15 对话摘要

## 主要话题
- 搭建了智能体记忆系统

## 关键决策
- 采用文件化记忆，方便迁移

## 待办事项
- 无
```

### 创建/更新任务

在 `memory/tasks/` 下按任务名创建：
```markdown
# 任务名称

## 状态：进行中

## 目标
- 具体目标描述

## 进展
- [2026-04-15] 完成了初始化

## 下一步
- 待定
```

## 低模型兼容提示

- 使用简单的 Markdown 结构
- 每个文件保持扁平，不超过 3 级标题
- 用列表而非表格
- 避免复杂的嵌套结构
