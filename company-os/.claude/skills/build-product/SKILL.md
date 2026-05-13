---
name: build-product
description: Tell the Engineering Agent exactly what to build. Skips all planning — just give it a feature description and it builds.
---

# /build-product

## What This Does

The most direct command in the system. Describe a feature, and the Engineering Agent builds it.

Usage:
```
/build-product [feature description]
```

Examples:
```
/build-product User can upload a CSV file and the app displays a chart
/build-product Add Stripe checkout for the $29/month plan
/build-product Fix the broken login redirect on mobile
/build-product Email the founder when a new user signs up
```

---

## Execution Instructions

### Step 1: Parse the Feature Request

Extract from the command:
- **What to build:** Core functionality
- **Who uses it:** Infer from company-profile if not stated
- **Success condition:** What does "done" look like?

If the request is ambiguous (under 5 words with no clear scope), ask ONE clarifying question before starting.

### Step 2: Read Codebase Context

Load:
- `company/company-profile.md` — tech stack is critical here
- Explore the existing codebase to understand current structure
- Identify relevant existing files (don't reinvent what exists)

### Step 3: Plan (briefly)

For any task > 30 mins, state the plan in 4-6 bullets before executing. No approval needed — just transparency.

```
📐 Implementation Plan
- [Step 1]
- [Step 2]
- [Step 3]
- Files I'll create/edit: [list]
Starting now...
```

For small tasks (< 30 mins), skip the plan and just build.

### Step 4: Build It

Load `agents/engineering-agent.md`. Operate as the Engineering Agent.

Write complete, working code. Create all necessary files.

### Step 5: Log and Update

Create log at `outputs/agent-runs/[YYYY-MM-DD]-engineering-[task-slug].md`

Add any follow-up work to `company/task-queue.md`.

### Step 6: Summary

```
✅ Built: [Feature Name]

What was created:
- [File 1] — [what it does]
- [File 2] — [what it does]

How to test:
[Step-by-step verification path]

Follow-up tasks added to queue:
- [Item 1]
- [Item 2]
```
