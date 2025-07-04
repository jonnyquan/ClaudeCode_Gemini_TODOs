# BitAgent TODO Management System

## System Overview
This project adopts a structured, documentation-driven Markdown TODO management system, designed for efficient, traceable team collaboration and complex project development. All tasks are managed via documents, ensuring transparent progress, clear responsibilities, and complete historical traceability.

## Key Files
- `PROJECT_TODOS.md`: Main task list, grouped by priority and phase, reflecting real-time development progress.
- `TODO_CONVENTION.md`: Detailed task management and update conventions, with mandatory operational procedures.
- `TASK_TEMPLATE.md`: Standard task template, supporting multi-level task breakdown and standardized descriptions.
- `PROJECT_ROADMAP.md`: Project strategic roadmap, guiding task breakdown and priority alignment.
- `*_PLAN.md` / `*_PROGRESS.md`: Detailed planning and progress tracking documents for large tasks.

## TODO Workflow

### 1. Task Creation & Breakdown
- All new tasks must use the `TASK_TEMPLATE.md` format, including task ID, priority, status, assignee, and due date.
- Complex tasks should be broken down into multi-level subtasks, and large tasks can have dedicated `*_PLAN.md` (plan) and `*_PROGRESS.md` (progress) documents.

### 2. Task Status Management
- Mark as `in_progress` immediately when a task starts.
- Mark as `completed` immediately when a task finishes.
- Add new tasks to `PROJECT_TODOS.md` as soon as they are discovered.
- If a task is blocked, keep it as `in_progress` and create a new blocking reason task.

### 3. Real-Time Update Principles
- All task status changes must be updated **in real time** in `PROJECT_TODOS.md`.
- Progress on large tasks should also be updated in `*_PROGRESS.md` and cross-referenced in the main task list.
- Batch updates are prohibited; every progress change must be recorded.

### 4. Session & Collaboration Workflow
- At the start of each development session, read `PROJECT_TODOS.md` to align on current priorities.
- Update task status and log progress in `DEVELOPMENT_LOG.md` after major progress or at the end of each day.
- All collaborators must follow the conventions in `TODO_CONVENTION.md`.

## Quick Start

1. Copy the core files (see `TODO_SYSTEM_SETUP_GUIDE.md`) to your new project.
2. Clean up template tasks and customize the task list and roadmap as needed.
3. Strictly follow `TODO_CONVENTION.md` and `TASK_TEMPLATE.md` for creating, updating, and tracking tasks.
4. Use Markdown documents for task assignment, progress synchronization, and historical review.

## Advanced Usage
- Supports multi-phase sprints, cross-team collaboration, and hierarchical management of large projects.
- Can be integrated with automation scripts or tools to assist with task status synchronization and progress statistics.

## Reference Documents
- `TODO_CONVENTION.md`: Detailed operational conventions
- `TODO_SYSTEM_SETUP_GUIDE.md`: Migration and initialization guide
- `TASK_TEMPLATE.md`: Task template and hierarchy description
- `PROJECT_TODOS.md`: Current task overview

---

For further customization or automation integration, refer to `TODO_SYSTEM_SETUP_GUIDE.md`.
