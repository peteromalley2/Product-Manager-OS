# SchoolFit — Task Queue

---

## PRE-BUILD: Founder Tasks (Before Engineering Starts)
These require human input — can't be automated.

- [ ] Wife maps matching framework: tag 20-30 Sydney private schools across all child/family dimensions — Engineering can't start without this data
- [ ] Decide on initial school list scope (e.g. top 50 private schools by enrolment in Greater Sydney)
- [ ] Register schoolfit.com.au domain (or schoolfit.app)
- [ ] Create Stripe account
- [ ] Create Supabase account
- [ ] Create Vercel account

---

## Week 1: Build the Core Matching Engine

- [ ] Set up Next.js 14 project, Supabase, deploy skeleton to Vercel — Engineering — High
- [ ] Build school database schema (schools table with all matching dimensions/tags) — Engineering — High
- [ ] Seed database with wife's school data (20-30 schools) — Engineering — High
- [ ] Build the multi-step quiz UI (child profile + family preferences, 10-15 questions) — Engineering — High
- [ ] Build matching algorithm (weighted scoring against school tags) — Engineering — High
- [ ] Build results page (ranked school list with match scores + plain-English explanations) — Engineering — High
- [ ] Test end-to-end: quiz → results working without auth — Engineering — High

---

## Week 2: Make It Real

- [ ] Add Supabase auth (email + Google login) — Engineering — High
- [ ] Save quiz results to user profile so parents can return — Engineering — High
- [ ] Add Stripe one-time payment ($49) — gate full results behind paywall, show top 3 free — Engineering — High
- [ ] Build basic onboarding (what does a new user see first?) — Engineering — Medium
- [ ] Add email notification to founders when someone pays — Engineering — Medium
- [ ] Set up Sentry or similar error monitoring — Engineering — Low
- [ ] Share with 5 Sydney parents outside the founding team, collect feedback — Founder task

---

## Week 3: Make It Findable + Sellable

- [ ] Write landing page copy (hero, benefits, how it works, pricing, FAQ) — Marketing — High
- [ ] Build landing page — Engineering — High
- [ ] Add your wife's bio + credentials to the site (trust anchor) — Engineering — High
- [ ] Write welcome email (sent on signup) — Marketing — Medium
- [ ] Write post-purchase email (sent after $49 payment, with PDF download) — Marketing — Medium
- [ ] Write day-3 re-engagement email (for free users who didn't upgrade) — Marketing — Medium
- [ ] Publish first SEO article: "How to choose the right private school in Sydney" — Marketing — Medium
- [ ] Set up basic analytics (Posthog free tier) — Engineering — Low

---

## Week 4: Launch

- [ ] Write Twitter/X and LinkedIn launch post (wife posts as school advisor) — Marketing — High
- [ ] Post in 3-5 Sydney parenting Facebook groups (authentic, not spammy) — Marketing — High
- [ ] Submit to Product Hunt — Marketing — Medium
- [ ] Reach out to 10 Sydney parent bloggers/influencers for coverage — Marketing — Medium
- [ ] Write second SEO article: "Best private schools in Sydney's [top suburb] 2026" — Marketing — Medium
- [ ] DM 20 ideal customers in Facebook groups — Marketing — Medium

---

## Backlog (Post-Launch)

- [ ] Add school comparison table (side-by-side view of 2-3 shortlisted schools)
- [ ] PDF report generation (downloadable school match report)
- [ ] Add more schools (expand to 60-80 Sydney private schools)
- [ ] Subscription plan ($29/month) for families revisiting annually or comparing siblings
- [ ] "Ask the advisor" feature (wife answers 1 question per paid report)
- [ ] SEO articles: suburb-specific school guides (Mosman, Bondi, Chatswood, etc.)
- [ ] Expand to Melbourne (once Sydney is working)
- [ ] School open day calendar integration
- [ ] NAPLAN data integration (MySchool API)

---

## Completed

<!-- Agents will move completed tasks here with dates -->
