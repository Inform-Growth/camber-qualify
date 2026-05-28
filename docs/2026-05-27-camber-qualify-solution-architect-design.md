# Camber Qualify — Camber Core Solution Architect Kit

**Date:** 2026-05-27
**Status:** Design approved, pending spec review
**Deliverable:** A new public GitHub repo, `Inform-Growth/camber-qualify`

## Overview

A public GitHub repo that a prospect runs inside their own AI assistant to get a
deep, free solution-architecture session for Camber Core. The AI takes on a
**Camber Core Solution Architect** persona: it researches the prospect's company,
proposes high-impact opportunities, and co-designs concrete Camber Core solutions
with diagrams — qualifying fit only lightly, as a byproduct of delivering real value.

This is the repo the existing `inform-website` `/qualify` page already advertises
(it currently shows three "Repo URL coming soon" placeholders).

### Inspiration

Modeled on a Personize "Solution Architect" demo prompt: a persona prompt that
points the AI at a skill on GitHub, has it research the user's company, then runs a
conversational, visual, deeply technical solution-design session — sharing
hypotheses in tables, asking numbered questions, and illustrating with diagrams.

### What changed from a pure qualification kit

The driving goal is **solution architecture, not qualification**. The AI spends its
effort researching and designing. Fit is a light read at the end, not a gated
verdict. The only firm "this may not be for you" is reserved for the two manifesto
red lines (labor replacement; walk-away install with no ongoing service), kept brief.

## Access model

No MCP server, no install required for v1. The prospect copies a master prompt from
the README, fills in their details, and pastes it into any AI with web access
(Claude, ChatGPT, Cursor). The AI fetches the public repo by URL to load its role
and the Camber Core knowledge base. The repo is also fully readable on GitHub.

## Repo location

- Org: `Inform-Growth` (same org as `inform-notes`)
- Name: `camber-qualify` (confirm at creation)
- Visibility: **public**

## Repo structure (mirrors personizeai/personize-skills)

```
camber-qualify/
  README.md                      # catalog + how-it-works + install + the master prompt (3 paths)
  LICENSE                        # Apache-2.0 (matches Personize)
  .gitignore
  docs/
    2026-05-27-camber-qualify-solution-architect-design.md   # this spec, seeded into the repo
  skills/
    camber-core-solution-architect/
      SKILL.md                   # full skill: persona, ACTIONS, differentiation test, resources, guardrails
      SKILL.web.md               # lighter web-fetch variant (what a pasted prompt points the AI to)
      web.config.json            # web-build exclude/rename config (matches Personize)
      reference/
        camber-core.md           # what Camber Core is (entity isolation, managed service, skills-as-IP, continuous fit, platform independence)
        who-its-for.md           # 4 ICP segments + "is this you" diagnostics + a not-a-fit pattern
        what-we-refuse.md        # the 5 refusals (also the red lines)
        tradeoffs.md             # what Camber Core is bad at / where engagements fail
        case-studies.md          # anonymized writeups
        manifesto-public.md      # outside-reader-calibrated thesis
        discover.md              # DISCOVER action framework (prospect research + numbered validation questions)
        propose.md               # PROPOSE action: opportunity tables, the differentiation test
        design.md                # DESIGN action: Mermaid architecture/data-flow patterns, roadmap shape
```

Mirrors the Personize layout: a repo `README` cataloging the skill, a `skills/<name>/`
folder with `SKILL.md` + `SKILL.web.md` + `web.config.json`, and deep `reference/`
docs that load on demand. Single source of truth: the SKILL references the
`reference/` docs for all Camber Core facts, so there is no duplicated prose.

## Master prompt (README)

A copy-paste block with clearly marked placeholders the prospect fills in, e.g.:

> Act as a Camber Core Solution Architect for **[Company]**. You are an experienced
> solution architect for Inform Growth's Camber Core... I am **[Name]**, **[Role]**
> at **[Company]** (**[company website]**). Evaluate for: **[departments/areas]**.
> First, read the Solution Architect skill to understand your role:
> `https://github.com/Inform-Growth/camber-qualify/blob/main/skills/camber-core-solution-architect/SKILL.md`
> Then research my company from our website and public sources before proposing anything.
> This is a conversation: share hypotheses in tables, ask me where I'm wrong using
> numbered options, and illustrate architectures with Mermaid diagrams. Go deep.

The README presents three paths matching the `/qualify` page:
1. **Claude Code / Claude Desktop** — install the skill, or paste the master prompt.
2. **ChatGPT / Cursor (web-enabled)** — paste the master prompt.
3. **Read on GitHub** — browse `content/` directly.

## SKILL.md design

Defines the persona and a five-phase conversation. Depth concentrates in Research
and Design.

1. **Research** — read the prospect's website (provided in the prompt) and public
   sources. Map structure (multi-entity? holding co / PE / agency / roll-up?),
   departments, tool stack, and likely manual/repetitive work. Summarize findings.
2. **Hypothesize** — table of opportunities ranked by impact, with an explicit
   "tell me where I'm wrong" before proceeding.
3. **Probe** — gather missing context directly from the prospect via numbered
   questions (not open-ended).
4. **Design (main event)** — 1–3 concrete Camber Core solutions across departments,
   each with a Mermaid architecture + data-flow diagram, sequenced into a rough
   roadmap. Deep and specific, never general.
5. **Light fit + next step** — brief honest read on fit; invite to continue with
   Jaron via Calendly (`https://calendly.com/jaron-informgrowth/30min`). Reserve a
   short, graceful "may not be a fit" only for the two red lines below.

### Resources the skill uses

- **The prospect's own website + public sources** — researched by the AI.
- **Direct input from the prospect** — gathered via numbered questions.
- **The repo's `content/` docs** — the Camber Core product knowledge to design against.

### Light qualification rubric (byproduct, not a gate)

- **Strong-fit signals:** sits above multiple entities (PE/VC, agency, healthcare/vet
  roll-up); wants governed single-org AI rollout; wants to amplify a team; values
  platform independence.
- **Red lines (brief, graceful redirect):** wants AI to replace headcount; wants a
  walk-away install with no ongoing service.
- **Camber-Core-alone note:** unusually static business → Camber Core without the
  managed service may suit better.

### Guardrails (load-bearing — messaging discipline)

The SKILL explicitly forbids surfacing internal mechanics, even when designing
solutions:
- No GitHub control-plane mechanics (which repo/branch/agent runs when).
- No shadow-operating / `report_issue` instrumentation at a technical level.
- No cross-client pattern-detection mechanics.
- Never use the phrase "Service-as-Software."
- No "fully automated" claims — reframe as responsive, SLA-backed, human-in-the-loop.

It designs at the public altitude the live site already uses: "managed AI
infrastructure, dedicated operator, internal agent fleet under human review,
drafts-only line."

## Content sourcing

`content/` docs are public-calibrated, derived from the live `inform-website` pages
and the public-safe portions of the manifesto / Camber Core managed-service notes.
The internal-only manifesto and managed-service-model notes are **not** copied
verbatim; only the externally-safe "say this" material is used.

- `camber-core.md` ← `inform-website` `camber-core.astro`
- `who-its-for.md` ← `inform-website` `who-its-for/*` + manifesto "Who we are for"
- `what-we-refuse.md` ← `inform-website` `what-we-refuse.astro`
- `case-studies.md` ← `inform-website` `src/content/case-studies/*`
- `manifesto-public.md` ← public-calibrated excerpt of the manifesto
- `tradeoffs.md` ← new, written from the "what it isn't" / refusals / continuous-fit material

## Out of scope (v1)

- No MCP server. (The `/qualify` page's MCP path can be added later; v1 uses the
  paste-the-prompt / read-the-repo model.)
- No lead capture or backend. Routing is the Calendly link + Jaron's email.
- No changes to the `inform-website` repo beyond (later, separately) filling in the
  three "Repo URL coming soon" placeholders on `/qualify`.

## Success criteria

- A prospect with no prior context can copy the README prompt, paste it into their
  AI, and get a researched, diagram-rich Camber Core solution design for their own
  company.
- The session is conversational (tables, numbered questions, "tell me where I'm
  wrong") and visual (Mermaid diagrams).
- No internal mechanics from the guardrails list ever appear in output.
- Good-fit sessions end with a clear invitation to book with Jaron; the two red-line
  cases get a brief, graceful redirect.
- The repo is readable and credible as a standalone artifact on GitHub.
