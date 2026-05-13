---
name: run-engineering
description: Skip the orchestrator and go straight to the Engineering Agent. Use when you know you need a coding task done.
---

# /run-engineering

## What This Does

Bypasses the orchestrator and activates the Engineering Agent directly. Use this when you know what you want built and don't need the system to decide for you.

Can be used with or without a specific task:
- `/run-engineering` → Engineering Agent reads state and picks the best coding task
- `/run-engineering Build the user auth flow` → Engineering Agent executes that specific task

---

## Execution Instructions

### Step 1: Read Context

Load:
- `company/company-profile.md` — tech stack, product context
- `company/task-queue.md` — what's in the backlog
- Most recent engineering run from `outputs/agent-runs/` (if exists)

### Step 2: Determine the Task

**If a specific task was provided with the command:**
Use that task. Don't override or second-guess it.

**If no task was provided:**
- Scan `company/task-queue.md` for the top unfinished engineering task
- If none exists, generate the next logical engineering task based on the company's current stage

Announce the task before starting:
> "Building: [task title]. Starting now..."

### Step 3: Load and Activate Engineering Agent

Load `agents/engineering-agent.md`. Operate as the Engineering Agent.

Execute the task fully. Create/edit real files. Write working code.

### Step 4: Log and Update State

Create log at `outputs/agent-runs/[YYYY-MM-DD]-engineering-[task-slug].md`

Update `company/task-queue.md`:
- Mark task complete
- Add follow-up tasks

### Step 5: Summary

```
✅ Engineering Run Complete

Built: [What was created/changed]
Files: [List of created/modified files]
Test it: [How to verify it works]

Next engineering tasks:
1. [Next item]
2. [Next item]
```
