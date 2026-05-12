---
name: run-marketing
description: Skip the orchestrator and go straight to the Marketing Agent. Use when you need content, copy, or a campaign created now.
---

# /run-marketing

## What This Does

Bypasses the orchestrator and activates the Marketing Agent directly. Use this when you know you need marketing output — a blog post, Twitter thread, email sequence, landing page copy, etc.

Can be used with or without a specific task:
- `/run-marketing` → Marketing Agent picks the most impactful content to create
- `/run-marketing Write a Twitter thread about our launch` → Executes that specifically

---

## Execution Instructions

### Step 1: Read Context

Load:
- `company/company-profile.md` — product, audience, brand voice, channels
- `company/metrics.md` — what's working
- Recent marketing runs from `outputs/agent-runs/` — what's already been published

### Step 2: Determine the Task

**If a specific task was provided with the command:**
Use that task exactly.

**If no task was provided:**
Check what marketing work is queued in `company/task-queue.md`. If nothing queued, determine the most valuable marketing output based on company stage:
- Pre-launch → SEO article targeting primary keyword OR Twitter thread about building the product
- Pre-traction → Case study with an early user OR outreach templates for ideal customers
- Traction → SEO article OR email onboarding sequence improvement

Announce the task:
> "Creating: [content title/type]. Researching first, then writing..."

### Step 3: Research Phase

Before writing, use web search to:
1. Find top 3 competitor pieces on this topic
2. Identify content gaps they're missing
3. Check what keywords/questions people are searching
4. Look for any recent news or trend to reference

Note key findings in 3-5 bullets.

### Step 4: Load and Activate Marketing Agent

Load `agents/marketing-agent.md`. Operate as the Marketing Agent.

Create complete, publish-ready content. Not a draft with notes — final copy.

### Step 5: Log and Update State

Create log at `outputs/agent-runs/[YYYY-MM-DD]-marketing-[task-slug].md`

Update `company/task-queue.md`:
- Mark marketing task complete (if it was queued)
- Add follow-up tasks (track engagement, create related content)

### Step 6: Summary

```
✅ Marketing Run Complete

Created: [Content title and type]
Saved to: [File path]

Publishing notes:
- Platform: [Where to post]
- Best time: [When to publish]
- CTA link: [What URL to include]

Next marketing tasks:
1. [Next item]
2. [Next item]
```
