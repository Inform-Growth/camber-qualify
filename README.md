# Camber Qualify

A public skill that turns your own AI assistant into a **Camber Core Fit Guide**.
Tell your AI about yourself and your company, and it will research you, ask good questions,
and help you reach a clear answer — does Camber Core fit your business or not.
No pitch. No jargon. No sales call required.

Built by [Inform Growth](https://informgrowth.com). **License:** Apache-2.0 — read it,
fork it, run it.

> **Camber Core** is managed AI infrastructure. Control what your AI does. See how it
> is used. Own what it learns — across every entity you operate.
> Learn more at [informgrowth.com](https://informgrowth.com).

---

## Quick start — the master prompt

Copy this, fill in the **[bracketed]** parts, and paste it into any AI assistant with
web access (Claude, ChatGPT, Cursor, …):

```text
I want to figure out whether Camber Core — managed AI infrastructure from Inform Growth
— is the right fit for my business. Give me an honest answer, not a pitch. Use plain
language. Ask me good questions. Help me see clearly.

Read your instructions here first:
https://github.com/Inform-Growth/camber-qualify/blob/main/skills/camber-core-solution-architect/SKILL.web.md

I am [Name], [Role] at [Company] ([company website]).

Start by researching my company from our website and any public sources you can find.
Then open with a plain-language summary of what you found and ask if you have got it
right. From there, ask me what you need to know to give me an honest read.
```

That is it. The AI researches your company, calibrates to how you talk, asks targeted
questions, and drives to a clear verdict — fit, no fit, or fit with conditions.

---

## Three ways to use it

### 1. Claude Code / Claude Desktop (install as a skill)

Copy the skill folder into your skills directory and restart:

```bash
git clone https://github.com/Inform-Growth/camber-qualify.git
cp -r camber-qualify/skills/camber-core-solution-architect ~/.claude/skills/
```

Then say: *"Help me figure out if Camber Core fits my business. I am [name], [role] at [company website]."*

### 2. ChatGPT / Cursor / any web-enabled AI (paste the prompt)

Use the **master prompt** above. The AI fetches the skill instructions by URL.

### 3. Read it on GitHub

Prefer to read first? Browse [`skills/camber-core-solution-architect/`](./skills/camber-core-solution-architect/)
— the [`SKILL.web.md`](./skills/camber-core-solution-architect/SKILL.web.md) is the whole playbook.

---

## What's inside

```
camber-qualify/
├── README.md                         # you are here
├── LICENSE                           # Apache-2.0
├── docs/                             # the design spec for this kit
└── skills/
    └── camber-core-solution-architect/
        ├── SKILL.md                  # full skill for Claude Code / Claude Desktop
        ├── SKILL.web.md              # web-fetch variant — what the master prompt loads
        ├── web.config.json           # web-build config
        └── reference/
            ├── camber-core.md        # what Camber Core is
            ├── who-its-for.md        # ICP segments and fit signals
            ├── what-we-refuse.md     # the five commitments
            ├── tradeoffs.md          # what Camber Core is bad at
            ├── case-studies.md       # anonymized proof
            └── manifesto-public.md   # the thesis, for outside readers
```

## How the skill works

The guide researches your company first, then calibrates to your language and title.
It asks one question at a time, names your pain back to you in your own words, and
uses a plain-language metaphor to show what your operation looks like with and without
Camber Core. It ends with an honest verdict — strong fit, not a fit, or fit with
conditions — and a clear next step either way.

## Talk to a human

If the session lands, book 30 minutes with **Jaron Sander**, founder of Inform Growth:

- 📅 [calendly.com/jaron-informgrowth/30min](https://calendly.com/jaron-informgrowth/30min)
- ✉️ [jaron@informgrowth.com](mailto:jaron@informgrowth.com)
