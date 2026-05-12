---
name: company-setup
description: Initialize a new company or reset the current one. Runs the onboarding interview and generates the company profile, initial task queue, and first 30-day plan.
---

# /company-setup

## What This Does

Sets up your autonomous company. Either generates a new product idea from your background, or refines an idea you already have. Creates all the company state files the autonomous system needs to start running.

Run this once when starting a new company. Re-run to pivot or reset.

---

## Execution Instructions

### Step 1: Check for existing company

Read `company/company-profile.md`. If it's already filled out (not a blank template), ask:

> "I see you already have [Company Name] set up. Do you want to:
> 1. Start fresh with a new company idea
> 2. Update/pivot the current company
> 3. Cancel and keep things as-is"

If blank or missing, proceed to Step 2.

---

### Step 2: Founder Interview

Ask these questions one at a time (conversational, not a form):

**Q1:** "What's your background? What field do you work in, or what do you know really well?"

**Q2:** "What's a recurring frustration you have — either at work, or in your personal life — where you've thought 'there should be a better way to do this'?"

**Q3:** "How would you rate your coding ability?"
- A) None — I can describe what I want but can't write code
- B) Some — I can read and tweak code but not build from scratch
- C) Strong — I can build full-stack apps independently

**Q4:** "How much time can you realistically commit per week to this?"
- A) 1-3 hours (mostly review what the AI built)
- B) 4-10 hours (I'll be involved in key decisions daily)
- C) 10+ hours (I want to build alongside the AI)

**Q5:** "Do you have a specific product idea already? If yes, describe it in 1-2 sentences. If no, I'll generate one based on what you've told me."

---

### Step 3: Idea Generation or Refinement

**If they have an idea:** Analyze it against these criteria:
- Is the problem specific enough? (avoid "help with productivity" — aim for "help freelancers track billable hours without switching apps")
- Is there a clear monetization path? (SaaS subscription, usage-based, or one-time payment)
- Can one person execute an MVP in 2-4 weeks?
- Is there a reachable audience? (online communities, subreddits, Twitter niches)

Provide feedback and refine together. Push back on ideas that are too broad or too complex.

**If they don't have an idea:** Generate 3 options based on their answers. For each idea include:
- **Name:** Working title
- **The problem:** 1 sentence, specific pain point
- **The product:** 1 sentence, what it does
- **Who pays for it:** Specific person (e.g., "freelance designers who invoice clients")
- **How it makes money:** Pricing model and rough price point
- **Why now:** Why this is worth building today

Ask them to pick one, or combine elements from multiple.

---

### Step 4: Generate Company Profile

Create `company/company-profile.md` with all fields filled out (not template — real content):

```markdown
# [Company Name] — Company Profile

## The Product
**One-liner:** [What it does in 10 words or less]
**Problem:** [The specific pain being solved]
**Solution:** [How the product solves it]
**Unique angle:** [Why this is different/better than what exists]

## Target Customer
**Who:** [Specific person — job title, context, pain level]
**Where they hang out:** [Subreddits, Twitter communities, Slack groups, newsletters]
**What they currently use:** [Existing tools or workarounds]
**What they'd pay:** [Price point and willingness to pay]

## Product Scope (MVP)
**Core feature:** [The ONE thing the MVP does]
**Out of scope (v1):** [Things explicitly NOT in the first version]
**Definition of MVP:** [How we'll know the MVP is done]

## Tech Stack
**Frontend:** [Framework + styling]
**Backend:** [API layer / server]
**Database:** [DB + auth]
**Hosting:** [Where it deploys]
**Payments:** [If applicable]
**Email:** [If applicable]

## Business Model
**Pricing:** [Free tier / paid tier structure]
**Revenue target (month 3):** [Realistic MRR goal]
**Revenue target (month 12):** [Ambitious but possible MRR goal]

## Marketing Channels
**Primary:** [Main channel to focus on]
**Secondary:** [Backup or supplementary channel]
**Tone/voice:** [How the brand communicates]

## Current Status
**Stage:** Pre-launch
**Users:** 0
**MRR:** $0
**Last updated:** [Date]
```

---

### Step 5: Generate Initial Task Queue

Create `company/task-queue.md` with a 30-day execution plan:

```markdown
# Task Queue

## Week 1: Build the Core
- [ ] Set up project repo and deploy skeleton app
- [ ] Build [core feature] end-to-end (no auth yet)
- [ ] Share URL with 3 people, collect feedback
- [ ] Fix top 2 issues from feedback

## Week 2: Make it Real
- [ ] Add user authentication
- [ ] Add data persistence
- [ ] Build basic onboarding (what does a new user do first?)
- [ ] Set up error monitoring (Sentry)

## Week 3: Make it Findable + Sellable
- [ ] Write landing page copy
- [ ] Build landing page
- [ ] Add pricing page with Stripe integration
- [ ] Set up email sequence (welcome + day 3 + day 7)
- [ ] Publish first SEO blog post

## Week 4: Launch
- [ ] Submit to Product Hunt
- [ ] Post on relevant subreddits
- [ ] Post Twitter/X thread about building this
- [ ] DM 20 ideal customers
- [ ] Get first 10 signups

## Backlog (after launch)
- [ ] [Feature request from early users]
- [ ] [SEO article on [primary keyword]]
- [ ] [Case study with first real user]
```

---

### Step 6: Initialize Other State Files

Create blank-but-structured versions of:
- `company/metrics.md` — with current state (all zeros)
- `company/decision-log.md` — with first decision logged: "Decided to build [company name]"

---

### Step 7: Launch Briefing

Show the founder:

```
✅ [Company Name] is ready to run.

Your company:
[One-liner]

Target customer:
[Specific person description]

First task:
[First item in the week 1 queue]

Run `/run-daily` to let the system take it from here.
Or run `/build-product` to start building the core feature right now.
```
