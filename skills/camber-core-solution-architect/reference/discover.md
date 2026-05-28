# DISCOVER — the full framework

Goal: understand *this* company well enough to design for it. Research first, then
validate. Never interrogate.

## Phase 0 — Company Intelligence Brief (always start here)

Before asking the person anything, research from their website and public sources
(about page, careers/job postings, case studies, press, LinkedIn). Produce a short brief:

| Field | What to find | Why it matters |
|---|---|---|
| Profile | What they do, business model, rough size | Frames everything |
| **Entity structure** | Do they sit *above* multiple entities? How many? On separate stacks? | The single most important question — it determines the whole design |
| Ownership | PE/VC-backed? Holding co? Roll-up? Independent? | Maps to ICP pattern |
| Tool landscape | CRMs, ops/PM tools, analytics (infer from job posts) | Where sprawl and gaps live |
| AI footprint | Any AI usage today? Native tooling? | Where it makes sprawl worse |
| Manual work | What looks repetitive or report-heavy | Opportunity surface |

Then classify into a **Structure Pattern** (A–E, see `who-its-for.md`). State your
classification and your confidence so the person can correct it.

## Phase 1 — Validate, don't interrogate

Lead with what you found; confirm before going deeper. Always present questions as
**numbered options** the person can pick from. Examples:

> Based on your site, I think you're **Pattern A — a PE operator above ~6 portcos on
> separate stacks**. Before I go further, which is most true?
> 1. That's right — 6 portcos, all separate stacks.
> 2. Close, but it's more like [N], and some share a stack.
> 3. We're not PE — we're [agency / roll-up / single org].
> 4. Something else (tell me).

Other validation prompts (adapt, keep them numbered):
- Where are the biggest gaps *between* your systems today?
- What does your team do by hand that requires pulling context across entities?
- Where do consequential decisions stall waiting on someone to assemble a report?
- What's your AI footprint today — none, native tooling, or something custom?
- Is there a dedicated AI-infrastructure owner anywhere in the structure?

## Phase 2 — Situation profile

Before moving to PROPOSE, lock down:
- **Structure pattern** (A–E) and entity count.
- **Primary departments** in scope (ops, sales/RevOps, marketing, finance, CS, clinical…).
- **The principal(s)** who'd operate across entities, and who must stay scoped.
- **Red-line check:** any signal of headcount-reduction intent or walk-away-install
  expectations? Flag it now; handle it in FIT.

**Output:** Company Intelligence Brief + validated structure profile + a one-paragraph
"here's what I think the highest-impact area is, tell me where I'm wrong."
