---
name: run-daily
description: Run the full autonomous daily cycle. The orchestrator reads company state, picks today's highest-leverage task, routes it to the right specialist agent, executes it, and logs the output.
---

# /run-daily

## What This Does

This is the core engine of the Autonomous Company OS. One command triggers a full autonomous work cycle:

1. Orchestrator reads company state and recent history
2. Decides the single highest-leverage task for today
3. Routes to Engineering or Marketing agent
4. Agent executes the task fully
5. Output is logged and company state is updated
6. Founder gets a clean summary

Run this once a day to operate your company on autopilot.

---

## Execution Instructions

### Step 1: Load Company State

Read all of these before doing anything else:
- `company/company-profile.md`
- `company/task-queue.md`
- `company/metrics.md`
- `company/decision-log.md`
- List files in `outputs/agent-runs/` — read the 3 most recent

If `company/company-profile.md` is empty or missing, stop and say:
> "No company set up yet. Run `/company-setup` first to initialize your company."

---

### Step 2: Activate Orchestrator Agent

Load `agents/orchestrator.md` and operate as the Orchestrator.

Run through the orchestrator's decision framework:

**Diagnose the stage:**
- Pre-launch: No working product yet → Engineering every day
- Pre-traction: Product live, < 50 users → Mostly engineering, some marketing
- Traction: 50+ users → Mix based on biggest constraint

**Review recent work (from agent-run logs):**
- What was done in the last 3 runs?
- What follow-up tasks were flagged?
- Any blockers that were surfaced?

**Select today's task:**
- Check task-queue.md for the top queued item
- If it's still relevant → pick it
- If something more urgent exists → create a new task and explain why
- If queue is empty → generate the next logical task based on stage + recent work

**Announce the decision before executing:**

```
📋 Today's Plan

Stage: [Pre-launch / Pre-traction / Traction / Growth]
Agent: [Engineering | Marketing]
Task: [Specific task title]
Why: [1 sentence — why this is the right thing today]

Starting now...
```

---

### Step 3: Execute with Specialist Agent

Load the appropriate agent definition:
- Engineering task → load `agents/engineering-agent.md`, operate as Engineering Agent
- Marketing task → load `agents/marketing-agent.md`, operate as Marketing Agent

Execute the task fully per the agent's instructions. Don't stop partway through. Don't produce a plan and wait for approval — execute.

**Engineering tasks:** Create/edit actual files in the product codebase. Write working code.

**Marketing tasks:** Produce complete, publish-ready content. Run web searches for research.

---

### Step 4: Log the Run

Create a log file at:
`outputs/agent-runs/[YYYY-MM-DD]-[engineering|marketing]-[task-slug].md`

Use the output log format from the agent definition.

Get today's date with: `date +%Y-%m-%d`

---

### Step 5: Update Company State

After execution:

**Update `company/task-queue.md`:**
- Mark today's task as completed: `- [x] [Task] — Done [date]`
- Add any follow-up tasks the agent identified

**Update `company/metrics.md`:**
- If a milestone was reached (first deploy, first piece of content, etc.), note it
- Update the "Last run" field

**Update `company/decision-log.md`** if any significant decisions were made:
- Format: `[Date] — [Decision] — [Rationale]`

---

### Step 6: Show Founder Summary

```
✅ Daily Run Complete — [Date]

**What was done:**
[1-2 sentences describing what was built or created]

**Output:**
[Link to / description of the specific file(s) created or changed]

**What's next (top 3 queue items):**
1. [Next task]
2. [Next task]
3. [Next task]

**Needs your input:**
[Any blockers or decisions requiring founder judgment — "None" if clean]
```

---

## Common Patterns

### If blockers are found during execution:
Don't silently stop. Surface the blocker clearly:
> "Blocked: To build [X], I need [Y]. Options: 1) [approach A], 2) [approach B]. Which do you prefer?"

### If the task is larger than one day's work:
Do as much as possible. Log what was completed. Break the remaining work into follow-up tasks in the queue. Never say "I'll do this next time" without adding it to the queue.

### If a better opportunity is spotted mid-task:
Complete the current task first. Then add the new opportunity to the queue with a note: "High priority — spotted during [date] run."

### If today has already been run:
> "Today's run already completed ([time]). The next run is scheduled for tomorrow. Want to run an extra task now? If so, which agent: Engineering or Marketing?"
