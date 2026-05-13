# Autonomous Company OS

Your AI that builds and markets your software company daily — without you managing every step.

Inspired by [Polsia](https://polsia.com/), built natively on Claude Code.

---

## What This Is

A multi-agent system that runs your software company autonomously. Every day, it:

1. Reads your company state (what's been built, what's working, what's queued)
2. Decides the single highest-leverage task — engineering or marketing
3. Executes it fully using specialized AI agents
4. Logs the output and updates your company state
5. Shows you what was done

You review. You redirect when needed. Everything else runs on autopilot.

---

## How It Compares to Polsia

| Feature | Polsia | This System |
|---------|--------|-------------|
| Autonomous daily tasks | Yes ($49/mo + 20% rev share) | Yes (free — your own Claude) |
| Engineering agent | Yes | Yes |
| Marketing agent | Yes | Yes |
| Company state tracking | Yes | Yes |
| Runs in your environment | No | Yes |
| You own your code/data | No | Yes |
| Customizable | Limited | Fully customizable |
| Revenue share | 20% | 0% |

---

## Quick Start

### 1. Navigate to this directory

```bash
cd company-os
claude
```

### 2. Set up your company

```
/company-setup
```

Claude will interview you (5 questions), generate or refine your company idea, and create your full company profile + 30-day task queue.

### 3. Run your first autonomous cycle

```
/run-daily
```

The orchestrator reads your company state, picks today's task, and executes it.

### 4. Run it again tomorrow

```
/run-daily
```

Same command, every day. Each run builds on the last.

---

## Commands

| Command | What it does |
|---------|-------------|
| `/company-setup` | Initialize a company (onboarding + idea generation) |
| `/run-daily` | Full autonomous daily cycle (orchestrator decides) |
| `/run-engineering` | Engineering agent only (skip orchestrator) |
| `/run-marketing` | Marketing agent only (skip orchestrator) |
| `/build-product [feature]` | Tell engineering agent exactly what to build |
| `/agent-status` | Company dashboard — metrics, queue, recent activity |

You can also just talk naturally:
- "What should we work on today?"
- "Build the user auth flow"
- "Write 5 tweets about our launch"
- "We got 10 signups — what should we focus on now?"

---

## Directory Structure

```
company-os/
├── CLAUDE.md                   # Master orchestrator instructions
├── README.md                   # This file
│
├── .claude/
│   └── skills/                 # Slash commands
│       ├── company-setup/      # Onboarding + idea generation
│       ├── run-daily/          # Full autonomous daily cycle
│       ├── run-engineering/    # Engineering agent direct access
│       ├── run-marketing/      # Marketing agent direct access
│       ├── build-product/      # Direct feature build
│       └── agent-status/       # Company dashboard
│
├── agents/                     # Specialist agent definitions
│   ├── orchestrator.md         # Strategic decision-maker
│   ├── engineering-agent.md    # Builds product, writes code
│   └── marketing-agent.md     # Creates content, drives growth
│
├── company/                    # Company state (updated by agents)
│   ├── company-profile.md      # Product, audience, tech stack
│   ├── task-queue.md           # What to work on next
│   ├── metrics.md              # Users, MRR, channel performance
│   └── decision-log.md         # Key decisions and rationale
│
└── outputs/
    └── agent-runs/             # Daily logs of what was done
```

---

## How the Daily Cycle Works

```
You: /run-daily
  ↓
Orchestrator reads:
  - company/company-profile.md
  - company/task-queue.md
  - company/metrics.md
  - outputs/agent-runs/ (last 3)
  ↓
Orchestrator decides:
  Stage? → Pre-launch / Traction / Growth
  Constraint? → Product / Users / Retention
  Best task? → Top queue item or generates new one
  Agent? → Engineering or Marketing
  ↓
Specialist agent executes:
  Engineering → writes code, creates files
  Marketing → researches, writes content
  ↓
Output logged to outputs/agent-runs/
Company state updated
Founder gets summary
```

---

## The 30-Day Arc

**Week 1:** Core product built and deployed (ugly, but real)

**Week 2:** Auth, persistence, basic onboarding

**Week 3:** Landing page, pricing, email sequence

**Week 4:** Launch — Product Hunt, Reddit, Twitter, outreach

By day 30, you should have a live product with real users. The system handles the execution. You handle the decisions it can't make.

---

## Customizing the System

Every component is a readable, editable markdown file.

**Change how the orchestrator prioritizes:** Edit `agents/orchestrator.md`

**Change the tech stack defaults:** Edit `agents/engineering-agent.md`

**Change marketing tone and channels:** Edit `agents/marketing-agent.md`

**Add a new skill:** Create `.claude/skills/[skill-name]/SKILL.md`

**Add context agents should always reference:** Add to `company/company-profile.md`

---

## Philosophy

This system follows one rule: **ship one meaningful thing per day.**

Not a hundred small things. Not a perfect thing. One real thing that moves the company forward.

Most solo founders fail not because they lack ideas, but because execution is hard alone. This system removes that bottleneck.
