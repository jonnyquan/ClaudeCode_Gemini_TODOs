# BitAgent TODO 管理系统

## 系统简介
本项目采用结构化、文档驱动的 Markdown TODO 管理系统，适用于高效、可追踪的团队协作和复杂项目开发。所有任务均以文档为核心，确保进展透明、责任明确、历史可追溯。

## 主要文件说明
- `PROJECT_TODOS.md`：主任务清单，按优先级和阶段分组，实时反映当前开发进度。
- `TODO_CONVENTION.md`：任务管理与更新的详细规范，强制执行的操作流程。
- `TASK_TEMPLATE.md`：标准任务模板，支持多层级任务拆解与规范化描述。
- `PROJECT_ROADMAP.md`：项目战略路线图，指引任务拆解与优先级排序。
- `*_PLAN.md` / `*_PROGRESS.md`：大型任务的详细计划与进度追踪文档。

## TODO 使用流程

### 1. 任务创建与拆解
- 所有新任务必须使用 `TASK_TEMPLATE.md` 规范格式，包含任务ID、优先级、状态、负责人、截止日期等。
- 复杂任务需拆解为多级子任务，并可为大型任务单独建立 `*_PLAN.md`（计划）和 `*_PROGRESS.md`（进度）文档。

### 2. 任务状态管理
- 任务开始时，立即标记为 `in_progress`。
- 任务完成时，立即标记为 `completed`。
- 发现新任务，随时添加到 `PROJECT_TODOS.md`。
- 任务被阻塞时，保持 `in_progress` 并新建阻塞原因任务。

### 3. 实时更新原则
- 所有任务状态变更必须**实时**同步到 `PROJECT_TODOS.md`。
- 大型任务的进展需同步更新 `*_PROGRESS.md`，并与主任务清单互相引用。
- 禁止批量更新，确保每次进展都被记录。

### 4. 会话与协作流程
- 每次开发会话开始，先阅读 `PROJECT_TODOS.md`，对齐当前优先级。
- 重要进展或每日结束时，更新任务状态并记录于 `DEVELOPMENT_LOG.md`。
- 所有协作成员必须遵循 `TODO_CONVENTION.md` 规范。

## 快速上手

1. 复制核心文件（见 `TODO_SYSTEM_SETUP_GUIDE.md`）到新项目。
2. 清理模板任务，按实际需求定制任务清单和路线图。
3. 严格按照 `TODO_CONVENTION.md` 和 `TASK_TEMPLATE.md` 创建、更新和追踪任务。
4. 通过 Markdown 文档进行任务分配、进度同步和历史回溯。

## 进阶用法
- 支持多阶段冲刺、跨团队协作和大型项目的任务分层管理。
- 可结合自动化脚本或工具，辅助任务状态同步和进度统计。

## 参考文档
- `TODO_CONVENTION.md`：详细操作规范
- `TODO_SYSTEM_SETUP_GUIDE.md`：迁移与初始化指南
- `TASK_TEMPLATE.md`：任务模板与分级说明
- `PROJECT_TODOS.md`：当前任务总览

---

如需进一步定制或自动化集成，可参考 `TODO_SYSTEM_SETUP_GUIDE.md` 进行扩展。
