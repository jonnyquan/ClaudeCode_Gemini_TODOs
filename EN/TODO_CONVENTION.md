# TODO Management Convention

## Update Timing
1. **When a task starts** - Immediately mark as `in_progress`
2. **When a task is completed** - Immediately mark as `completed`
3. **When a new task is discovered** - Immediately add to the list
4. **When a task is blocked** - Keep as `in_progress` and create a new blocking task

## Update Principles
- **Real-time updates** - Do not batch update; update each task as soon as it changes
- **Update in two places** - Both in-memory TODOs and the persistent file
- **Every major progress** - Always update `PROJECT_TODOS.md`

## Large Task Management (`*_PLAN.md` & `*_PROGRESS.md`)
For any complex task that requires detailed breakdown (e.g., a multi-day sprint), we use a dual-file mode: `PLAN` and `PROGRESS`.

1.  **Create `*_PLAN.md`**:
    - **Purpose**: Define the task's **goals, scope, challenges, and detailed action steps**.
    - **Content**: Includes final goals, key challenges, detailed task breakdown (e.g., 5-day sprint plan), success criteria, etc.
    - **Status**: Once created, this file should remain relatively stable as the "blueprint" for action.

2.  **Create `*_PROGRESS.md`**:
    - **Purpose**: Track the **execution progress, status, and outputs** of the `PLAN` in real time.
    - **Content**: Includes task completion status (e.g., `✅ [SIM-001]`, `🚧 [SIM-002]`, `[ ] [SIM-003]`), completion rate analysis, encountered issues, technical debt, and real-time key metrics.
    - **Status**: This file is dynamic and should be updated immediately after each task status change.

3.  **Linking & Reference**:
    - In `PROJECT_TODOS.md`, the large task should be a single entry and link to its `*_PLAN.md` file.
      - *Example*: `- [ ] [SIM-000] Integrate Binance Testnet (see: SIM_TRADING_PLAN.md)`
    - `*_PLAN.md` and `*_PROGRESS.md` should link to each other at the top for quick navigation.

## Session Start Process
```bash
# 1. Read last TODO
cat PROJECT_TODOS.md

# 2. Restore to TodoWrite
# 3. Continue working
```

## Session End Process
```bash
# 1. Ensure all TODOs are saved
# 2. Update last modified time in PROJECT_TODOS.md
# 3. Commit to git (if needed)
```

## Trigger Words Convention
- "update TODO" - Immediately sync memory and file
- "save progress" - Export all current TODOs to file
- "restore TODO" - Load TODO list from file
- "view TODO" - Show current TODO status

## Auto Reminders
- After completing 3 tasks → Remind to save
- Session exceeds 30 minutes → Remind to update progress
- Switching major tasks → Auto-save checkpoint