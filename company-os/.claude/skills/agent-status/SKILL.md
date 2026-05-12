---
name: agent-status
description: Show the current state of your company. What's been done, what's queued, current metrics, and recent agent activity.
---

# /agent-status

## What This Does

Shows you a complete snapshot of where your company stands right now. Like a company dashboard, but in plain English.

Run this any time to get oriented — especially if you haven't opened the workspace in a few days.

---

## Execution Instructions

### Step 1: Read All State Files

Load:
- `company/company-profile.md`
- `company/task-queue.md`
- `company/metrics.md`
- `company/decision-log.md`
- List `outputs/agent-runs/` directory — read the 5 most recent logs

### Step 2: Render the Dashboard

Output a structured status report:

---

```
🏢 [COMPANY NAME] — Status Report
[Current Date]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📊 METRICS
Users: [number]
MRR: $[amount]
Stage: [Pre-launch / Pre-traction / Traction / Growth]
Days running: [X days since setup]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

✅ RECENTLY COMPLETED
[Date] — [What was done] ([Engineering/Marketing])
[Date] — [What was done] ([Engineering/Marketing])
[Date] — [What was done] ([Engineering/Marketing])

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📋 TASK QUEUE (next 5)
1. [Task] — [Engineering/Marketing]
2. [Task] — [Engineering/Marketing]
3. [Task] — [Engineering/Marketing]
4. [Task] — [Engineering/Marketing]
5. [Task] — [Engineering/Marketing]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🔑 KEY DECISIONS
[Most recent 3 decisions from decision-log.md]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

⚡ RECOMMENDED NEXT ACTION
[Based on stage and queue: what to run next and why]

Run `/run-daily` to execute autonomously
Run `/run-engineering [task]` to build something specific
Run `/run-marketing [task]` to create content
```

---

### Step 3: Surface Any Issues

After the dashboard, flag:

- If task queue is empty → "Queue is empty. Run `/run-daily` and I'll generate new tasks."
- If last run was > 3 days ago → "Last run was [X days ago]. Momentum slows without daily progress."
- If a blocker was logged → "Outstanding blocker: [blocker description]. This needs your input."
- If metrics haven't moved in 7+ days → "Metrics stagnant. Today's focus should be [highest-leverage unlock]."
