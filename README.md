# idea-hunt — Find a Painful Workflow AI Can Replace, Then Prove People Will Pay

> An open-source **Claude skill** (and portable prompt playbook) for **AI business idea discovery and validation**. It inverts the usual "invent an idea" brainstorm: it starts from *evidence of real pain*, mines what people already pay to fix, applies explicit kill-gates, forces a **proof-of-wallet** test, and only lets validated ideas reach a build plan.

**idea-hunt** is a rigorous, evidence-first framework for finding **AI-native business ideas** — the kind you can actually sell. Instead of generating generic "AI tool for X" slop, it helps you locate an **existing, already-paid-for workflow that AI can now do as completed work** (the *Service-as-Software* shift), then validates real willingness-to-pay *before* you write a line of code.

Built for founders, indie hackers, and solo builders using **Claude Code**, **Claude Desktop**, or any agent that supports the open skill format.

---

## What is idea-hunt?

**idea-hunt is a Claude skill that finds and validates AI business ideas by starting from real, evidence-backed customer pain instead of imagination.** It runs a 7-stage pipeline — frame → mine pain → build a candidate slate → apply kill-gates → test demand → prove willingness-to-pay → produce a build blueprint — so that most weak ideas die on paper in an afternoon rather than in the market over six months.

It is designed around one governing fact: **42% of startups fail because there is no market need** (CB Insights) and **60–70% of AI "wrappers" earn $0**. idea-hunt exists to fail those ideas *before* you build them.

---

## Why use it? (The problem it solves)

Most "AI startup idea" prompts ask a language model to invent something from a blank page. That produces vague, undefensible, me-too ideas nobody pays for. idea-hunt does the opposite:

- ❌ **Don't** invent an idea and hope demand exists.
- ✅ **Do** find a workflow people *already pay for* (a freelancer, an agency, a VA, a clunky tool) that AI now collapses — and confirm the money is real first.

If someone pays a freelancer ₹40,000/month for a task you can automate for ₹4,000, they have **already told you the price**. That is a painkiller. idea-hunt hunts for painkillers, not vitamins.

---

## How it works — the 7-stage pipeline

| Stage | What happens |
|-------|--------------|
| **0 · Frame** | Pick the search surface — a domain you know, a customer you can reach, a constraint. |
| **1 · Pain mining** | Surface real complaints: `last30days` + G2/Capterra 1–3★ feature-gap reviews + Upwork/Fiverr gigs (a posted gig is a *purchase order*). |
| **2 · Candidate slate** | Turn pain into 5–8 candidates, each phrased as *replacing a specific incumbent and selling the finished outcome*. |
| **3 · Kill-gates** | Score every candidate against 6 gates (painkiller, AI-native fit, reachable owner, urgency, buildability, durable moat). Any hard-fail = rejected. |
| **4 · Demand reality** | Run survivors through `office-hours`' six forcing questions + **The Mom Test** discipline. |
| **4.5 · Proof of wallet** | Design the smallest test that extracts *real* willingness-to-pay: pre-sale, deposit, smoke test, concierge-and-charge, or LOI. Cash > opinions. |
| **5 · Pick ONE** | Choose the single highest-EV wedge, defended against the rejected alternatives. |
| **6 · Build blueprint** | Only now: MVP scope, stack, trust system, incumbent-anchored pricing, honest cold-start GTM, automation architecture, kill-criteria, and a scaling roadmap. |

---

## Key concepts baked in

- **Service-as-Software** — sell *completed work*, not software seats. Vertical AI agents are eating horizontal SaaS because they own the outcome.
- **Painkiller vs. vitamin** — only pursue acute, already-funded pain.
- **The Mom Test** — ask about past behavior and actual spend; never pitch; never ask "would you use this?"
- **Proof of wallet** — a landing-page signup is interest; a deposit is demand.
- **Durable 2026 moats** — workflow depth, proprietary data flywheels, niche distribution, switching costs, compliance. Model access is *not* a moat.
- **Honest cold-start GTM** — first customers come from hand-to-hand outreach and communities, not day-1 ads.

---

## Installation

idea-hunt is a single self-contained `SKILL.md`. Install it wherever your agent loads skills:

### Claude Code / Claude Desktop
```bash
git clone https://github.com/ANVEAI/idea-hunt-skill.git
cp -r idea-hunt-skill ~/.claude/skills/idea-hunt
```

### Other agent runtimes
Copy the `SKILL.md` into your skills directory (e.g. `~/.agents/skills/`, `~/.codex/skills/`, or an `npx skills add` target). The skill is plain Markdown + YAML frontmatter with no build step.

---

## Usage

Invoke it by name or describe the task:

```
/idea-hunt legal intake automation for small immigration firms
/idea-hunt                      # open-ended — it will ask for an anchor
```

Natural-language triggers that activate it:
- "find a business idea"
- "what should I build?"
- "is there an AI opportunity here?"
- "find a painful problem AI can replace"
- "validate this idea"

Every hunt writes a running artifact to `docs/idea-hunt-<slug>.md` so the process is resumable and auditable.

### Companion skills (recommended, not required)
- **[last30days](https://github.com/mvanhorn/last30days-skill)** — powers Stage 1 pain mining with real, recent complaints across Reddit, X, YouTube, Hacker News, and more.
- **office-hours** — powers the Stage 4 demand-reality gate (YC-style six forcing questions).

idea-hunt still works without them — it falls back to `WebSearch` for pain mining and applies the office-hours questions inline — but they make it sharper.

---

## FAQ

**What is a Claude skill?**
A Claude skill is a Markdown file (`SKILL.md`) with YAML frontmatter that an AI agent loads to gain a specialized capability. idea-hunt is a skill that gives Claude a rigorous method for finding and validating AI business ideas.

**How is idea-hunt different from asking ChatGPT or Claude for startup ideas?**
A raw prompt invents ideas from imagination and rarely checks demand. idea-hunt starts from evidence of pain, forces explicit kill-gates, and requires a proof-of-wallet test before recommending anything — so it rejects most ideas instead of rationalizing the first one.

**Who is it for?**
Founders, indie hackers, solo builders, and micro-SaaS makers who want to find an AI-native business with real demand — especially those starting from zero audience and a small budget.

**Does it work for non-AI businesses?**
Yes. The pain-mining, kill-gate, and proof-of-wallet stages apply to any digital product. The AI-native lens (gate 2) simply prioritizes workflows where LLMs change the unit economics.

**Do I need to pay for anything?**
No. The skill is free and open-source (MIT). Companion skills may use optional API keys for richer research but are not required.

**What does "proof of wallet" mean?**
Extracting real willingness-to-pay before building — a pre-sale, deposit, paid pilot, smoke test with a real price, or signed letter of intent. It is the single strongest signal of demand and the direct antidote to the #1 startup failure mode (no market need).

---

## Contributing

Issues and pull requests are welcome. Good contributions: sharper kill-gates, new pain-mining sources, additional proof-of-wallet patterns, and real-world case studies of hunts that shipped. Keep the skill portable — a single `SKILL.md`, no build step.

## License

[MIT](./LICENSE) — free to use, modify, and distribute. Attribution appreciated.

---

*Keywords: AI business idea generator, AI startup idea validation, find SaaS ideas, micro-SaaS idea discovery, Service-as-Software, vertical AI agents, painkiller vs vitamin, The Mom Test, proof of wallet, pre-sell validation, Claude skill, Claude Code skill, AI opportunity finder, idea validation framework, indie hacker, solo founder.*
