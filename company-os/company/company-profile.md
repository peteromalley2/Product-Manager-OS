# SchoolFit — Company Profile

## The Product
**One-liner:** Find the right Sydney private school for your child, not just the top-ranked one.
**Problem:** Sydney parents choosing private schools are overwhelmed by league tables, open days, and word-of-mouth — none of which account for whether the school actually fits their child's personality, learning style, and energy levels.
**Solution:** A matching tool that takes a child profile (personality, learning stage, energy, interests) + parent preferences (fees, location, specialisation) and returns a ranked, personalised school shortlist with match explanations — built on an expert framework developed by a qualified school selection advisor.
**Unique angle:** Every competitor shows the same spreadsheet of ATAR scores and fees. SchoolFit is the first tool that matches on the child, not just the school.

---

## Target Customer
**Who:** Sydney parents with children aged 3-12, actively researching private schools, overwhelmed by the volume of options and unsure how to evaluate "fit" beyond rankings and reputation.
**Example customer:** A Mosman or Balmain parent with a Year 2 child, starting to think seriously about Year 7 enrolment, who has been to 4 open days and still doesn't know how to compare schools beyond gut feel.
**Where they hang out:** Facebook groups (Sydney school mums groups, suburb-specific parenting groups), Reddit (r/sydney, r/AusFinance, r/Parenting), school-specific Facebook pages, Mumsnet AU, local council family pages, Instagram parenting accounts
**What they currently use:** School websites, MySchool.edu.au (NAPLAN data), word-of-mouth, open days, private school consultants ($2,000-5,000 for in-person advice)
**What they'd pay:** $29-49/month subscription or $79-99 one-time report. Price anchors against $2,000+ private consultants — this is the affordable, instant version.

---

## Product Scope (MVP)
**Core feature:** A guided child + family profile quiz (10-15 questions) that outputs a personalised ranked list of Sydney private schools with match scores and a short explanation of why each school fits (or doesn't).
**Out of scope (v1):**
- School comparison tables (add post-launch)
- Saved profiles / accounts (add in week 2)
- Mobile app
- Schools outside Sydney
- Public or Catholic systemic schools
- Enrolment application assistance
- Live chat with advisors

**Definition of MVP:** A parent can complete the quiz in under 5 minutes and receive a personalised shortlist of 5-8 schools with match scores and plain-English explanations. At least one parent outside the founding team has used it and said it was useful.

---

## The Matching Framework (Wife's IP)
This is the core of the product. Before engineering starts, map out:

**Child dimensions to capture:**
1. Energy level (calm/introverted ↔ high-energy/social)
2. Learning style (structured/academic ↔ exploratory/project-based)
3. Stage of development (advanced, on-track, needs support)
4. Social preference (small tight-knit ↔ large diverse community)
5. Interests/strengths (arts, sport, STEM, performance, outdoors)
6. Any additional needs (gifted, learning differences, EAL)

**Parent/family dimensions:**
1. Fee budget (under $15k / $15-25k / $25-40k / $40k+)
2. Location / commute tolerance (suburb-based radius)
3. Academic priority (top results vs. wellbeing vs. balance)
4. Co-curricular priorities (sport, arts, faith, etc.)
5. School size preference
6. Faith affiliation (Anglican, Catholic, non-denominational, secular)

**School tags (wife to populate for each school):**
Each Sydney private school gets tagged across all dimensions above — this is the database that powers matching.

---

## Tech Stack
**Frontend:** Next.js 14 (App Router) + Tailwind CSS
**Backend:** Next.js API routes
**Database:** Supabase (Postgres + Auth)
**Hosting:** Vercel
**Payments:** Stripe (one-time report purchase to start, subscription later)
**Email:** Resend

---

## Business Model
**Pricing:**
- Free: Complete the quiz, see top 3 matches (teaser)
- Paid: $49 one-time — full report with all matches, match scores, detailed school explanations, and a downloadable PDF
- Future: $29/month subscription for families comparing multiple children or revisiting annually

**Revenue target (month 3):** $2,000 (40 paid reports)
**Revenue target (month 12):** $10,000 MRR (mix of reports + early subscriptions)

---

## Marketing Channels
**Primary:** Facebook groups — Sydney parenting/school groups are highly active and recommendations travel fast. Wife posts authentically as a school advisor sharing useful content.
**Secondary:** SEO — "best private schools Sydney", "how to choose a private school Sydney", "[suburb] private schools" — long-tail, high-intent searches from parents mid-research.
**Tone/voice:** Warm, expert, non-judgemental. Sounds like advice from a knowledgeable friend who happens to know every school in Sydney. Never pushy. Never elitist.

---

## Founding Team Edge
- **You:** Product instincts, can direct the AI to build, understands SaaS metrics and customer problems
- **Your wife:** Credible school selection expert — her name and credentials on the site make it trustworthy in a way no competitor can easily replicate. She IS the brand.

---

## Current Status
**Stage:** Pre-launch
**Users:** 0
**MRR:** $0
**Product URL:** Not deployed yet
**Last updated:** 2026-05-12
