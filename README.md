# Camber Qualify

A public skill that turns your own AI assistant into a **Camber Core Solution Architect**.
Point your AI at this repo, tell it about your company, and it will research you, find
where managed AI infrastructure would have the biggest impact, and design a concrete
deployment — with diagrams, in a working session, no sales call required.

Built by [Inform Growth](https://informgrowth.com). **License:** Apache-2.0 — read it,
fork it, run it.

> **Camber Core** is managed AI infrastructure that unifies AI tooling across tools,
> teams, and entities. One isolated deployment per entity, principal-level access across
> all of them, institutional knowledge captured as skills, kept fit by a managed service.
> Learn more at [informgrowth.com](https://informgrowth.com).

---

## Quick start — the master prompt

Copy this, fill in the **[bracketed]** parts, and paste it into any AI assistant with
web access (Claude, ChatGPT, Cursor, …):

```text
Act as a Camber Core Solution Architect for [Company]. You are an experienced solution
architect for Inform Growth's Camber Core — managed AI infrastructure that unifies AI
tooling across tools, teams, and entities. Your goal is to identify the highest-impact
opportunities Camber Core could have for our business, and then design and sequence
them. Go deep — do not stay at a general level.

First, read the Solution Architect skill to understand your role:
https://github.com/Inform-Growth/camber-qualify/blob/main/skills/camber-core-solution-architect/SKILL.web.md

I am [Name], [Role] at [Company] ([company website]). Evaluate for: [departments/areas,
e.g. operations, marketing].

Then research my company from our website and other public sources before proposing
anything — understand who we are, our size, our structure, our tools, and what we likely
do by hand today. This is a conversation: at each step share your hypotheses in tables,
illustrate architectures and workflows with Mermaid diagrams, and ask me where you might
be wrong using numbered options before moving on.
```

That's it. The AI will run a discovery → propose → design → fit session and end with a
concrete next step.

---

## Three ways to use it

### 1. Claude Code / Claude Desktop (install as a skill)

Copy the skill folder into your skills directory and restart:

```bash
git clone https://github.com/Inform-Growth/camber-qualify.git
cp -r camber-qualify/skills/camber-core-solution-architect ~/.claude/skills/
```

Then just say: *"Act as a Camber Core Solution Architect for my company, [website]."*

### 2. ChatGPT / Cursor / any web-enabled AI (paste the prompt)

Use the **master prompt** above. The AI fetches the skill and reference docs by URL.

### 3. Read it on GitHub

Prefer to read first? Browse [`skills/camber-core-solution-architect/`](./skills/camber-core-solution-architect/)
— the [`SKILL.md`](./skills/camber-core-solution-architect/SKILL.md) and the
[`reference/`](./skills/camber-core-solution-architect/reference/) docs are the whole kit.

---

## What's inside

```
camber-qualify/
├── README.md                         # you are here
├── LICENSE                           # Apache-2.0
├── docs/                             # the design spec for this kit
└── skills/
    └── camber-core-solution-architect/
        ├── SKILL.md                  # full skill — persona, actions, guardrails
        ├── SKILL.web.md              # lighter variant for web-fetch / pasted prompts
        ├── web.config.json           # web-build config
        └── reference/
            ├── camber-core.md        # what Camber Core is (safe-altitude source of truth)
            ├── who-its-for.md        # ICP segments + "is this you" diagnostics
            ├── what-we-refuse.md     # the five commitments / red lines
            ├── tradeoffs.md          # what Camber Core is bad at
            ├── case-studies.md       # anonymized proof
            ├── manifesto-public.md   # the thesis, for outside readers
            ├── discover.md           # DISCOVER action framework
            ├── propose.md            # PROPOSE action framework
            └── design.md             # DESIGN action framework
```

## How the skill works

It loads the persona, then runs four non-sequential actions — **DISCOVER** (research you
first), **PROPOSE** (opportunity tables + a differentiation test), **DESIGN** (concrete
deployments with Mermaid diagrams + a roadmap), and **FIT** (an honest read and a routed
next step). It's built to be candid: if Camber Core isn't right for you, it says so.

## Talk to a human

If the session lands, book 30 minutes with **Jaron Sander**, founder of Inform Growth:

- 📅 [calendly.com/jaron-informgrowth/30min](https://calendly.com/jaron-informgrowth/30min)
- ✉️ [jaron@informgrowth.com](mailto:jaron@informgrowth.com)
