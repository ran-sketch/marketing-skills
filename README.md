# Marketing Skills

A collection of 8 battle-tested marketing frameworks — built as Claude Code skills, readable as standalone playbooks.

Each skill is a structured Markdown file that defines *how* to do something well: what questions to ask, what patterns to avoid, and what good output actually looks like. No fluff, no theory — just executable frameworks.

---

## Skills

| Skill | What it does |
|---|---|
| **content-framework** | Hook → Retain → Reward system for any content. Covers monetization strategy, give:ask ratio, and Alex Hormozi's 7 content laws. |
| **hooks** | 100+ proven hook templates across 10 categories for video, social, and copy. |
| **post-antipatterns** | Quality gate for posts. Defines 6 anti-patterns to catch before anything ships. |
| **humanizer-main** | Strips AI writing patterns from text. Based on Wikipedia's Signs of AI Writing guide. |
| **email-structure** | 5-part anatomy for professional emails. Subject line through CTA. |
| **cold-outreach** | Full outbound system: list building, personalization, multi-touch sequencing. |
| **lead-magnets** | Hormozi 100M Leads framework. Free offers, trust funnels, and CTAs that convert. |
| **paid-ads** | 4-problem framework for paid advertising — platform, targeting, copy, and capture. |

---

## For Claude Code users

These are drop-in skills for Claude Code. Clone the repo and point Claude at it.

**1. Clone the repo**

```bash
git clone https://github.com/ran-sketch/marketing-skills.git
```

**2. Add the CLAUDE.md to your project**

Copy or symlink the `CLAUDE.md` into your working directory. It tells Claude how to use the skill system — when to load a skill, how to follow it, and how to improve it over time.

**3. Start using it**

Claude will automatically detect when a skill applies and load it before responding. For example:

- *"Write me a LinkedIn post about..."* → triggers `content-framework` + `post-antipatterns`
- *"Give me a hook for my video..."* → triggers `hooks`
- *"Make this sound less AI..."* → triggers `humanizer-main`
- *"Help me build a cold outreach sequence..."* → triggers `cold-outreach`

No configuration required beyond dropping the files in place.

---

## For marketers (no Claude Code needed)

Every skill is plain Markdown — open any `SKILL.md` directly and use it as a framework doc.

Recommended reading order:

1. `content-framework/SKILL.md` — the foundation everything else builds on
2. `post-antipatterns/SKILL.md` — learn what kills posts before they land
3. `hooks/SKILL.md` — stop the scroll
4. `humanizer-main/SKILL.md` — if you use AI to write, this removes the tells
5. `cold-outreach/SKILL.md` — full outbound system from list to close
6. `lead-magnets/SKILL.md` — build offers people actually want
7. `paid-ads/SKILL.md` — spend money that converts
8. `email-structure/SKILL.md` — emails that get read and acted on

---

## How the skill system works

Skills use a simple architecture:

- Each skill lives in its own folder: `skill-name/SKILL.md`
- The `CLAUDE.md` is the orchestration layer — it tells Claude when to load which skill
- Claude reads the skill, follows its steps, and updates it when it learns something new

The goal: push complexity into tested, reviewed instructions so Claude doesn't improvise formats or steps that are already defined.

---

## License

MIT
