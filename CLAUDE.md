# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

# Agent Instructions

> This file provides instructions for working in this skills-based workspace. Read it before creating, editing, or running any skill.

You operate within a 2-layer architecture that separates reusable instructions from task execution. Skills encode the "how" so you don't have to rediscover it every session.

## The 2-Layer Architecture

**Layer 1: Skills (How to do it)**
- Reusable instruction sets written in Markdown, live in skill folders (e.g. `hubspot-workflows/SKILL.md`)
- Define the steps, output formats, edge cases, and pointers to supporting scripts or references
- Written like instructions you'd give a capable employee who's done this before

**Layer 2: Orchestration (Decision making)**
- This is you. Your job: read the right skill, then execute.
- Before doing any task, check whether a skill exists for it. If one does, read it first and follow it.
- You don't improvise formats or steps that are already defined in a skill — you follow the skill, then improve it if you learn something new.

**Why this works:** ad-hoc improvisation compounds errors and produces inconsistent outputs. Skills push the complexity into tested, reviewed instructions. You focus on adapting those instructions to the specific input at hand.

---

## Operating Principles

**1. Check for a skill first — two-pass protocol**
Use the Skill Inventory table (already loaded in this file) as a zero-cost first filter. Do NOT open any skill file speculatively.

**Pass 1 — Confirm relevance (YAML only):** If the Skill Inventory suggests a match, read only the YAML frontmatter at the top of the candidate `SKILL.md` (the `---` block, ~10 lines). This costs ~50 tokens and tells you name + description. Stop here if it's not a match.

**Pass 2 — Full read:** Only if the YAML confirms the skill applies, read the full skill body and follow its instructions.

Never read multiple full skill files up front. Each full file costs hundreds of tokens — load only what you've confirmed you need. Only proceed without a skill if the Skill Inventory has no match.

**2. Self-anneal when things break**
- Read the error and understand what went wrong
- Fix the approach and retry (unless it involves paid API calls — check with the user first)
- Update the skill with what you learned (API quirks, edge cases, better patterns)
- Example: a HubSpot enrollment condition behaves unexpectedly → investigate why → identify the correct filter logic → update the skill's enrollment section with the finding

**3. Update skills as you learn**
Skills are living documents. When you discover a better approach, an API constraint, a common failure mode, or a more reliable output format — update the skill. Don't create or overwrite skills without asking unless explicitly told to. Skills are the instruction set and must be preserved and improved over time, not used once and discarded.

---

## Self-Annealing Loop

Errors are learning opportunities. When something breaks:
1. Fix the immediate problem
2. Identify the root cause
3. Update the relevant skill with the new knowledge
4. Verify the fix works
5. System is now stronger for next time

---

## File Organization

**Skill folders:**
- Each skill lives in its own folder: `skill-name/SKILL.md`
- Supporting files go in subfolders within the skill:
  - `scripts/` — executable helpers for deterministic/repetitive steps
  - `references/` — docs Claude loads on demand (API guides, field mappings, etc.)
  - `assets/` — templates, icons, or static files used in outputs

**Workspace files:**
- `evals/evals.json` — test prompts used to validate a skill's outputs
- `.env` — API keys and environment variables (never commit)

**Key principle:** `SKILL.md` stays focused and under 500 lines. Heavy reference material lives in `references/` and gets loaded only when needed. The skill body is always loaded when a skill fires — keep it lean.

---

## Skill Structure

Every `SKILL.md` must open with YAML frontmatter:

```yaml
---
name: skill-name
description: "What this skill does and when to use it. Include trigger phrases inline here — list more rather than fewer so the skill doesn't get skipped when it should apply."
---
```

**Important:** Always write `description` as a quoted single-line string. Multi-line or unquoted descriptions cause YAML parsing errors where inline labels (like `Use when:`) get misread as unsupported YAML attributes.

The body follows in Markdown: steps, output formats, examples, edge cases, and `references/` pointers.

**Writing rules:**
- Use imperative form: "Always validate the ID before writing" not "You might want to validate"
- Explain the *why* behind important rules — Claude follows intent better than bare commands
- Define output formats explicitly with templates when consistency matters
- For multi-domain skills, route to variant reference files rather than putting everything in the body:

```markdown
- For enrollment logic issues → read `references/enrollment.md`
- For sequence setup → read `references/sequences.md`
```

---

## Testing a Skill

After writing or updating a skill:
1. Write 2–3 realistic test prompts (what a real user would actually type)
2. Run them with the skill active
3. Evaluate outputs against the skill's defined format and quality bar
4. Iterate on the skill until outputs are consistent
5. For skills with objective outputs, save test cases to `evals/evals.json` for future regression checks

---

## Skill Inventory

These skills currently exist. When a user request matches a trigger, read that skill before producing any output.

| Skill | Folder | Triggers on |
|---|---|---|
| **content-framework** | `content-framework/` | Writing/improving posts, social content, emails, ads, hooks, content strategy, give:ask ratio, "what would Alex say" |
| **hooks** | `hooks/` | Opening lines, hooks, video intros, attention-grabbing openers |
| **humanizer-main** | `humanizer-main/` | Making AI writing sound human, removing AI patterns, rewriting robotic copy |
| **lead-magnets** | `lead-magnets/` | Creating or evaluating lead magnets, free offers, CTAs, trust funnels |
| **post-antipatterns** | `post-antipatterns/` | **Mandatory quality gate** — fires on every post creation or evaluation request |
| **cold-outreach** | `cold-outreach/` | Outbound machine, cold email/call, prospecting, list building, outreach sequences |
| **paid-ads** | `paid-ads/` | Paid advertising, ad copy, ad creative, targeting, landing pages, ad campaigns |
| **email-structure** | `email-structure/` | Write an email, draft an email, email structure, email copy, outreach email, follow-up email, email template, business email, format an email, review my email |

**Cross-skill rules:**
- `post-antipatterns` is always run when creating or evaluating any post — it calls `content-framework`, `lead-magnets`, and `hooks` internally, and `paid-ads` for ad content.
- When writing ad copy, run both `content-framework` (Hook/Retain/Reward) and `paid-ads` (Callout/Value/CTA) together.
- `lead-magnets` is the reference for what to send people toward after any CTA — both in posts and ads.

---

## Summary

You sit between human intent (skills) and task execution (your outputs + any scripts). Read the right skill, make decisions, produce consistent outputs, handle errors, and continuously improve the system.

Be pragmatic. Be reliable. Self-anneal.
