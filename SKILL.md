---
name: idea-hunt
version: "2.0.0"
description: |
  Find a painful, already-paid-for workflow that AI can now replace — then prove it with
  real willingness-to-pay before building. Inverts the usual "invent an idea" prompt:
  starts from evidence of pain, not imagination. Mines real complaints (last30days +
  review/gig sites), applies explicit kill-gates, forces a proof-of-wallet test, and runs
  survivors through office-hours before any build blueprint.
  Use when asked to "find a business idea", "what should I build", "is there an AI
  opportunity here", "find a painful problem AI can replace", or "validate this idea".
  Proactively invoke when the user is hunting for a new venture, side project, or
  micro-SaaS and wants rigor instead of a brainstorm dump.
argument-hint: 'idea-hunt legal intake for small firms | idea-hunt <niche or workflow> | idea-hunt (open-ended)'
allowed-tools: Bash, Read, Write, Edit, WebSearch, WebFetch, AskUserQuestion
user-invocable: true
license: MIT
metadata:
  type: reference
  companions:
    - office-hours   # demand-reality gate (six forcing questions)
    - last30days     # real-time pain evidence (Reddit/X/HN/YouTube, last 30 days)
---

# idea-hunt — find a painful workflow AI can replace, then prove people will pay

## Core thesis (read first)

> **Do not invent an idea. Find an existing, painful, already-paid-for workflow that AI can
> now do *as completed work* — and kill it fast if real money doesn't show up.**

The best AI businesses in 2026 are not new problems. They are **old problems whose cost
structure just changed.** The winning shape is **Service-as-Software**: instead of selling a
tool that helps a human do the work (per-seat SaaS), you sell the *finished outcome* the human
used to produce. Buyers are shifting from "we need 50 licenses" to "we need 5,000 tickets
handled / 200 listings written / 40 intakes qualified." Vertical AI agents are eating
horizontal SaaS precisely because they own the outcome, not the seat.

Someone is already paying — in money, hours, or dread — for a workflow AI now collapses. Your
job is to **locate that workflow with evidence and confirm willingness-to-pay**, not imagine
a product.

**Three signals a workflow is a real target:**
1. **Money already flows** (a *painkiller*, not a vitamin). People pay a tool, agency, VA,
   freelancer, or plugin to do this today. If nobody pays for today's bad solution, AI won't
   make them start. A business owner paying a freelancer ₹40k/mo for a task you can automate
   for ₹4k has *already told you the price*.
2. **The pain is repetitive, specific, and now.** It recurs weekly/daily and has a narrow
   owner ("clinic front desks", "Shopify stores > ₹5L/mo", "immigration paralegals").
3. **AI changes the unit economics for real.** The core task is language, extraction,
   classification, drafting, routing, or judgment that LLMs now do reliably — not "AI-washed"
   decoration over work that's actually offline, physical, or human-mandated.

If a candidate fails any of the three, **reject it and move on.** Rigor is what you throw away.

**The stat that governs this whole skill:** 42% of startups fail because there is *no market
need* (CB Insights) — the #1 cause, ahead of running out of cash. And 60–70% of AI "wrappers"
earn $0, with ~90% expected dead by end of 2026. This skill exists to make you fail those
ideas *on paper in an afternoon* instead of *in the market over six months.*

---

## The pipeline (do not skip stages)

```
STAGE 0   Frame the hunt        → pick the search surface
STAGE 1   Pain mining           → last30days + review/gig-site complaints (real verbatims)
STAGE 2   Candidate slate       → 5–8 workflows, each an existing-solution-being-replaced
STAGE 3   Kill-gate scoring     → apply the 6 gates; most candidates die here
STAGE 4   Demand-reality test   → office-hours' six questions + Mom Test discipline
STAGE 4.5 PROOF OF WALLET       → design the pre-sell that proves willingness-to-pay
STAGE 5   Pick ONE              → single highest-EV wedge, justified against rejects
STAGE 6   Build blueprint       → only now, the full execution plan
```

Never jump straight to STAGE 6. The whole point is that most ideas die at STAGE 3–4.5.

---

## STAGE 0 — Frame the hunt

Establish the search surface before mining. If the user gave a niche/workflow, use it. If
open-ended, ask (via AskUserQuestion) for **one** anchor — enough to aim, not to stall:

- **A domain they know** (their job, an industry they've worked in, a hobby with money in it).
  Insider knowledge is the single biggest edge — it lets you see painful workflows and, later,
  gives you *distribution into a niche horizontal players won't target*.
- **A customer they can reach in 72h** (who do they already have access to?).
- **A constraint** (B2B vs B2C, budget, geography — e.g. India-first vs global).

Write the frame to `docs/idea-hunt-<slug>.md` (create `docs/` if needed). This file is the
running artifact for the whole hunt.

> Bias: **B2B and prosumer beats consumer** for cold-start-in-72h. Businesses pay fast, pay
> monthly, and feel workflow pain acutely. Consumers churn and won't pay a stranger.

---

## STAGE 1 — Pain mining (evidence, not imagination)

Goal: surface **verbatim complaints** and **proof of spend** about existing workflows/tools.
You want people saying "I hate that I still do this manually", "X is too expensive/clunky",
"I pay someone ₹__ to…". Founders who win *mine complaints*; they don't brainstorm.

Run these in parallel and log every hit into the artifact:

1. **`last30days`** on the domain and on incumbent tools — e.g.
   `last30days pain points [workflow]`, `last30days [incumbent tool] alternatives`,
   `last30days what [role] hate about their job`. This is the freshness engine: what people
   complain about *this month*, with engagement signal.
2. **Review-site feature-gap mining** (highest-signal source). Read **1–3 star reviews** on
   G2 / Capterra / App Store for incumbent tools. These are paying users telling you,
   unprompted, exactly where the current software fails. B2B categories (accounting, HR,
   legal-tech, healthcare admin) are especially rich.
3. **Follow the money = willingness to pay.** Search **Upwork / Fiverr** gigs for the task.
   A posted job is not a complaint — it is a **purchase order**: proof the pain is worth
   paying to fix *right now*. Note the going rate; that's your pricing anchor.
4. **Community lurking** — the subreddits / Slacks / Discords where the ICP already vents.

Capture per complaint cluster: the **workflow**, **who owns it**, **what they pay today**,
**the incumbent solution**, and the **verbatim pain**. Quote real language — the copy for the
eventual landing page is hiding in these quotes.

> If STAGE 1 finds no one paying for the current bad solution and no gig/spend evidence, stop
> and re-frame (STAGE 0). No existing spend = no wedge.

---

## STAGE 2 — Candidate slate (5–8 workflows)

Turn pain clusters into candidates. Each MUST be phrased as **replacing a specific existing
solution and selling the completed outcome** — not a new invention:

> "Replace [incumbent: agency / manual process / clunky tool / freelancer] for [narrow owner]
> with an AI system that *delivers [the finished outcome]*."

Bad candidate: "AI tool for marketing." (invented, vague, no incumbent, sells a tool)
Good candidate: "Replace the ₹15–40k/mo freelancer who writes + schedules Amazon listing copy
for Indian D2C sellers with a self-serve AI that ingests the SKU sheet and *delivers*
compliant, keyword-optimized listings." (incumbent = freelancer, owner = D2C seller, task =
drafting, sells the outcome, money already flows)

List all candidates in the artifact before scoring. Resist committing to one yet.

---

## STAGE 3 — Kill-gate scoring (most candidates die here)

Score every candidate against 6 gates. **Any hard-fail = rejected.** Do not rescue a favorite
by fudging a gate.

| # | Gate | Pass condition | Hard-fail if… |
|---|------|----------------|---------------|
| 1 | **Painkiller / existing spend** | Someone pays today (tool/agency/VA/freelancer/gig) | Nobody pays; it's a "nice-to-have" vitamin |
| 2 | **AI-native fit (completed work)** | Core task is language/extraction/classification/drafting/judgment LLMs do reliably, and you can sell the *outcome* | AI is decorative; real work is offline/physical/regulated-human |
| 3 | **Narrow, reachable owner** | You can name AND reach the exact buyer in one sentence, in 72h | Buyer is "everyone" / unreachable this week |
| 4 | **Urgency & recurrence** | Pain hits weekly+ and is felt now | Nice-to-have, annual, or "someday" pain |
| 5 | **Wedge is buildable** | MVP delivering real value ships in ≤72h with the stated stack | Needs data/integrations/licenses you can't get in 72h |
| 6 | **Durable moat path** | A named, compounding moat (below) | One-prompt wrapper any competitor clones in a weekend |

**Gate 6 — the durable moats that actually hold in 2026** (model access is NOT one of them):
- **Workflow depth** — you live inside the multi-step process, not a single prompt.
- **Proprietary data flywheel** — usage produces data a competitor can't get, making the
  product better over time (the model providers don't have the hospital's notes or the firm's
  case archive; you do because you sit in the workflow).
- **Niche distribution** — you own a vertical horizontal players won't bother targeting.
- **Switching costs / integrations** — you're wired into their systems of record.
- **Compliance** — auditable HIPAA/SOC2/GDPR handling is itself a moat.
> Realistic caveat: for a solo cold-start, *speed of execution + distribution into your niche*
> is the day-1 "moat"; the data flywheel and switching costs are what you build toward. Favor
> **permanence** (being the obvious default in a niche) over a fragile technical moat.

Score each gate 0 (fail) / 1 (weak) / 2 (strong). Reject anything with a 0 or total < 8/12.
Write the scored table into the artifact and **explicitly list what you rejected and why** —
the rejections are as valuable as the pick.

> Anti-slop check: "ChatGPT with a system prompt and a login" hard-fails gate 6 unless there's
> a data/workflow moat. A wrapper is a feature, not a business — 90% of them are dead by end-2026.

---

## STAGE 4 — Demand-reality test (office-hours + Mom Test)

Take the 1–2 survivors and run them through **`office-hours`** (startup mode). Its six forcing
questions are the real filter:

1. **Demand reality** — is anyone *desperate* for this, or is it merely reasonable?
2. **Status quo** — what do they do today, and why is it painful *enough to switch*?
3. **Desperate specificity** — who is the one customer type that would buy tomorrow?
4. **Narrowest wedge** — the smallest thing you can sell that still delivers value?
5. **Observation** — have you *watched* this pain happen, or are you guessing?
6. **Future-fit** — does it ride a trend (AI cost curve, regulation, platform shift)?

**Apply Mom Test discipline to any user/customer conversation you plan:**
- Ask about **past behavior and actual spend**, never about a hypothetical future ("Would you
  use this?" is worthless — people lie to be nice).
- **Don't pitch the idea.** The moment you pitch, honest exploration turns into polite praise.
- Good questions: "Walk me through the last time you did X." "What do you use today?" "What
  did that cost you / who do you pay?" "What happens if you don't fix it?"

A candidate that can't answer #1 and #5 with real evidence is not validated — send it back to
STAGE 1 or kill it. office-hours saves a design doc; fold it into the artifact.

---

## STAGE 4.5 — PROOF OF WALLET (the gate everyone skips — don't)

Opinions are not demand. Before writing production code, design the **smallest test that
extracts real willingness-to-pay.** Pick the strongest one the situation allows:

- **Pre-sale / deposit** — take money (or a refundable deposit / paid pilot / annual-upfront
  founder's-rate) *before* the product exists. Cash is the only unfakeable signal.
- **Smoke test** — a landing page with a real price and a "Buy / Start" button that captures
  intent (and ideally a card). Measure click-to-checkout, not "signups."
- **Concierge / manual-first** — deliver the outcome by hand for the first 3–5 customers
  (you + AI in the loop) and *charge for it*. This proves demand AND writes your automation
  spec from real cases before you build software.
- **Letter of intent** — for higher-ACV B2B, a signed "we'll pay ₹X/mo when you ship Y."

Define the **pass bar up front**, e.g. "3 paying pilots or ₹X collected from 30 qualified
conversations." Miss the bar → the wedge is wrong; return to STAGE 1. Hit it → proceed. This
one stage is the direct antidote to the 42%-no-market-need failure mode.

---

## STAGE 5 — Pick ONE

Choose the **single highest expected-value wedge.** State plainly:
- Why this one beats the other survivors (EV ≈ pain intensity × reachability × build-ability ×
  moat × proven willingness-to-pay).
- The three closest alternatives and the specific reason each was rejected.
- The **narrowest possible v1** — one customer type, one workflow, one outcome.

Do not present a menu. One recommendation, defended.

---

## STAGE 6 — Build blueprint (only for the survivor)

Now — and only now — generate the execution plan. Decision-grade, not a 44-item wall.

1. **Wedge & UVP** — one sentence each. Lead with the *outcome sold*, not the feature list.
2. **ICP & where to reach them in 72h** — name the exact community / list / channel.
3. **MVP scope** — the thinnest thing that delivers the outcome. Concierge-first is allowed
   and often smarter (your STAGE 4.5 manual cases *are* the spec). Cut everything else.
4. **Stack** — pragmatic (Lovable/Bolt/Next + Supabase + Razorpay/Stripe + n8n + an LLM API).
   Use `codex` / rapid-prototyper for the build.
5. **Trust system for a zero-reputation stranger** — interactive demo, free trial OR
   money-back guarantee, transparent pricing, founder attention for the first customers,
   turn STAGE 4.5 pilots into the first testimonials/case studies.
6. **Pricing — anchor to the human/incumbent cost you replace, not to a race-to-₹99:**
   - Price against what they pay today (the ₹40k freelancer, the agency retainer, the salary).
     Salesforce's Agentforce prices at ~$2/conversation explicitly *vs* the $30–50 human cost —
     copy that logic.
   - Prefer **outcome- or usage-based, or hybrid** (a predictable base + per-outcome/credit
     charge). Hybrid is the dominant 2026 structure; pure per-seat is dying for AI products
     because it charges most exactly when the product deflects the most work.
   - Keep it recurring and high-margin.
7. **Go-to-market, honestly sequenced** (first customers almost never come from ads/SEO):
   - **Hours 0–72:** *hand-to-hand.* Direct outreach to 50–100 exact-ICP people with a
     3-sentence message naming their specific pain (expect ~15–25% reply when the pain is
     real). Community selling (give value ~2 weeks before pitching). A launch-platform /
     directory listing (Product Hunt). **This is where the first rupee comes from.**
   - **After first signal:** Meta/Google ads to *scale what already converts.* Warn the user:
     ad accounts, pixels, and review cycles rarely produce paying customers inside 72h from a
     cold start — treat paid as the week-2 lever, not the day-1 one.
8. **Automation architecture** — what runs without the founder (onboarding, fulfillment,
   billing, support, follow-up). Map each to a tool. The goal is ≥95%-automated over time.
9. **Metrics & kill-criteria for the business itself** — define up front the signal that says
   "double down" vs "kill it" (e.g. "0 paying customers after 30 qualified conversations =
   wrong wedge, restart at STAGE 1").
10. **Scaling roadmap** — first paying customer → ₹5k MRR → ₹50k MRR → ₹5L MRR, naming the
    constraint that changes at each step (and where the data flywheel / switching-cost moat
    starts to compound).

---

## Operating rules

- **Evidence over eloquence.** Every demand claim traces to a STAGE 1 verbatim, a paid gig, or
  a STAGE 4.5 dollar. No unsupported "people would love this."
- **Cash > opinions.** A landing-page signup is interest; a deposit is demand. Weight them
  accordingly.
- **Reject freely.** Killing 7 candidates and shipping 1 *paid-validated* wedge is success.
  Rationalizing the first idea is failure.
- **Sell the outcome, not the seat.** If it can't be framed as completed work, rethink it.
- **Honest timelines.** Don't promise ads-from-zero revenue in 72h. Name the real cold-start
  channel (hand-to-hand).
- **Productize or don't recommend.** If it can't become ≥95%-automated software, it fails
  unless the user explicitly wants a service — and even then, concierge is a *bridge to*
  software, not the destination.
- **One artifact.** Keep everything in `docs/idea-hunt-<slug>.md` so the hunt is resumable and
  auditable.

## Companion skills

- **`last30days`** — STAGE 1 pain mining. Real complaints, last 30 days, with engagement signal.
- **`office-hours`** — STAGE 4 demand-reality gate. Run survivors through the six questions.
- After a wedge clears STAGE 4.5, hand off to `codex` / rapid-prototyper for the STAGE 6 build.

---
<!--
Changelog
2.0.0 — Research-grounded rewrite. Added: Service-as-Software framing (sell completed work,
        not seats); STAGE 4.5 Proof of Wallet (pre-sell before build — antidote to the 42%
        no-market-need failure mode); Mom Test discipline in STAGE 4; painkiller-vs-vitamin
        sharpening of gate 1; specific 2026 durable moats + wrapper-death reality in gate 6;
        review-site feature-gap + Upwork-gig-as-purchase-order mining in STAGE 1; incumbent-cost
        anchoring + outcome/hybrid pricing in STAGE 6. Sources: a16z/Bessemer vertical-AI &
        Service-as-Software theses; Rob Fitzpatrick "The Mom Test"; CB Insights startup post-
        mortems (42% no market need); 2026 AI-pricing surveys (per-seat decline, outcome/hybrid
        rise); AI-wrapper revenue distribution reports; micro-SaaS first-customer channel studies.
1.0.0 — Initial version: invert "invent an idea" into evidence-first hunt with kill-gates,
        last30days + office-hours gating, honest cold-start GTM.
-->
