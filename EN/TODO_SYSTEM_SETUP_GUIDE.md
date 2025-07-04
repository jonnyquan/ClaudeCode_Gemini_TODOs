# TODO System Migration & Operation Guide

This document guides you on how to fully copy and apply the TODO task management system used in the BitAgent project to any new project.

## System Features

This is a Markdown-centric, structure-driven, and process-clear task management system. It enforces a "documentation first" approach, ensuring all work is traceable—especially suitable for teams needing rigorous tracking and asynchronous collaboration.

---

## Part 1: System Initialization

To start this TODO system in a new project, follow these steps:

### Step 1: Copy Core Files

You need to copy the following files and directories from the BitAgent project to your new project. These are the "minimum viable skeleton" of the system.

**Required files:**

1.  `PROJECT_TODOS.md` - *Tactical task board*
2.  `PROJECT_ROADMAP.md` - *Strategic roadmap*
3.  `TASK_TEMPLATE.md` - *Task creation template*
4.  `TODO_CONVENTION.md` - *TODO update rules*

In CLAUDE commands:
- Deeply understand the web code, summarize the vision into GEMINI.md
- Realign @PROJECT_TODOS.md and other TODO files according to the vision and SaasPRD.md
- Break down the task list according to XX goals

### Step 2: Clean Up & Customize

1.  **Clean `PROJECT_TODOS.md`**: Open `PROJECT_TODOS.md`, delete all old tasks, and leave only one or two initial tasks as format examples.
2.  **Clean `PROJECT_ROADMAP.md`**: Open `PROJECT_ROADMAP.md` and modify or rewrite the roadmap according to your new project's goals.
3.  **(Optional) Customize `TASK_TEMPLATE.md`**: Open `TASK_TEMPLATE.md` and modify task tags (e.g., `#frontend`, `#backend`, etc.) as needed for your new project.

---

## Part 2: Daily Operation Workflow

After initialization, follow this workflow to manage your project tasks.

### 1. View Current Tasks

- **At the start of each workday, the first thing is to open `PROJECT_TODOS.md`.**
- This file is your team's "single source of truth," showing which tasks are important and their current status.

### 2. Create New Tasks

1.  Open `TASK_TEMPLATE.md`.
2.  Copy the full "Standard Task Template".
3.  Paste it into the task list in `PROJECT_TODOS.md`.
4.  Fill in all fields, including task title, level, priority, assignee, etc.

### 3. Update Task Status

- When you start a task, immediately change its status from `🔴Todo` to `🟡In Progress`.
- When a task is completed, immediately change its status to `🟢Done`.
- **Principle: Real-time updates, update each as you finish.**

### 4. Handling Large & Complex Tasks

If a task is very complex and expected to take more than 3 days, **do not** break it down directly in `PROJECT_TODOS.md`. Instead, follow this "plan/progress separation" protocol:

1.  **Create dedicated files**:
    *   In the project root, create two new files for the task: `[TaskName]_PLAN.md` and `[TaskName]_PROGRESS.md`.
    *   *Example: For the task "Refactor User Authentication System", create `AUTH_REFACTOR_PLAN.md` and `AUTH_REFACTOR_PROGRESS.md`.*

2.  **Fill with templates**:
    *   Copy the content of `SIM_TRADING_PLAN.md` into your new `_PLAN.md` file and fill in the detailed action plan.
    *   Copy the content of `SIM_TRADING_PROGRESS.md` into your new `_PROGRESS.md` file for subsequent progress tracking.

3.  **Link the main task**:
    *   Go back to `PROJECT_TODOS.md`, change the original large task description to a one-line summary, and add a link to the `_PLAN.md` file.
    *   *Example: `- [ ] [L3] Refactor User Authentication System (see: AUTH_REFACTOR_PLAN.md)`*

4.  **Update progress in `_PROGRESS.md`**:
    *   For this large task, all daily, detailed progress updates should be recorded in the `_PROGRESS.md` file.
    *   When the entire large task is finally completed, update the main task status in `PROJECT_TODOS.md` to `🟢Done`.

---

By following the above steps, you can successfully deploy and efficiently run this powerful, documentation-centric TODO management system in any new project.
