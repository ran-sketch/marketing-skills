---
name: post-antipatterns
description: "Quality gate for all post creation and evaluation. Fires whenever the user asks to create a post, write a post, draft a LinkedIn post, make a post, build a post, review a post, evaluate a post, or check if a post is good. Defines 6 anti-patterns to detect and block, with cross-skill quality checks that must pass before any post is finalized."
---

# Post Anti-Patterns — Quality Gate

This skill is a mandatory pre-flight check. Run it before outputting or finalizing any post. A post that fails even one check does not ship — it gets fixed first.

---

## The 6 Anti-Patterns

### 1. Opinion Without Framework
**What it looks like:** A bold claim is made. More opinions are added to support it. Nothing is actionable.
**Test:** Can the reader do something different tomorrow because of this post? If no — it's an opinion, not a framework.
**Example of failure:** *"Most teams never get there because they fall into one of two traps."* — Traps are named and described, but no model, no steps, no structure is given to actually avoid them.

### 2. Narrative Without Takeaway
**What it looks like:** A story or scenario is described in detail. It ends. The reader nods along and forgets it by tomorrow.
**Test:** Strip the post to its last 2 sentences. Do those sentences contain a concrete, transferable thing the reader now knows or can do? If no — the narrative has no payload.
**Example of failure:** *"I've disagreed with plenty of executives. Respectfully, with a better option ready. And most of the time, they listen."* — Relatable story. Zero instruction on how to actually do this.

### 3. Vague Call to Action
**What it looks like:** The post ends with "ask yourself X" or "stop doing Y" — without telling the reader what to do instead.
**Test:** Does the CTA point the reader toward a specific next action, resource, or behavior? Rhetorical questions and vague imperatives don't count.
**Example of failure:** *"Get off the treadmill and ask two questions: What's the single most important thing to be done right now? And what's the simplest way to do it?"* — Two questions with no answers, no framework to answer them, no next step.

### 4. Philosophy Over Practicality
**What it looks like:** The post sounds insightful. The reader finishes and thinks "okay... so what?" It reads like a thought piece, not a resource.
**Test:** Would a practitioner find this useful mid-project, or only when they're already reflective and have spare time? If it only works in the second scenario — it's philosophy.
**Example of failure:** *"The best operators I know are what I'd call productively paranoid."* — Interesting framing. Completely undefined. No way to apply it.

### 5. No Conversion Mechanism
**What it looks like:** The post ends cold. No lead magnet, no link, no next step, no reason to engage beyond passive consumption.
**Test:** Does the post give the reader a clear path to get more value — a template, a resource, a follow-up, a DM prompt? If no — it's a dead end.
**Rule:** Every post should either (a) point to a lead magnet, (b) invite a specific response ("comment X if you want the template"), or (c) tee up a series with a reason to follow.

### 6. Reward Mismatch
**What it looks like:** The hook promises insight or a solution. The body delivers an anecdote. The ending delivers a platitude. The reader was promised a destination and got dropped in a parking lot.
**Test:** Does the ending deliver exactly what the hook implied? Map hook → body → ending. If the ending is a generic lesson rather than the specific answer the hook teased — it's a mismatch.
**Example of failure:** Hook: *"Really good RevOps is boring."* Implied promise: here's how to build a boring, reliable system. Delivery: two vague traps described, no system given.

---

## Quality Gate — Cross-Skill Checks

Before finalizing any post, run all applicable checks. If any fails, stop and fix before continuing.

### Check 1: Content Framework — Reward Score
Read `content-framework/SKILL.md`. Evaluate the Reward dimension.
- Does the post deliver full value that matches the hook promise?
- Is the reward a concrete framework, list of steps, template, or secret — not a vague lesson?
- **Pass:** Reader gets something specific and usable. **Fail:** Reader gets a platitude or a restatement of the hook.

### Check 2: Lead Magnets — CTA Check
Read `lead-magnets/SKILL.md`. Apply Hormozi's core rule: **Give away the secrets. Sell the implementation.**
- Does the post give away a real secret (not a vague observation)?
- Does the post end with a CTA that points toward implementation (a resource, tool, DM, or next step)?
- **Pass:** Secrets are shared. Path forward exists. **Fail:** Post is philosophical. Post ends cold.

### Check 3: Hooks — Strength Check
Read `hooks/SKILL.md`. Evaluate the opening hook.
- Does the hook use at least 2 components (Recency, Relevance, Celebrity, Proximity, Conflict, Unusual, Ongoing)?
- Is it from a strong category (Contrarian, Problem/Pain, Curiosity) rather than a neutral observation?
- **Pass:** Hook creates genuine tension or curiosity. **Fail:** Hook is a soft observation that doesn't demand continued reading.

### Check 4 (ads only): Paid Ads — Ad Structure Check
**Run this check only when the content is a paid ad.** Read `paid-ads/SKILL.md`. Evaluate all three components:
- **Callout:** Does the first 5 seconds contain a verbal or visual callout that speaks directly to the ICP and repels everyone else?
- **Value:** Does the ad use at least one What/Who/When angle (dream outcome, nightmare, speed, ease, status, time consequences)?
- **CTA:** Is there exactly one action being asked for, and is it frictionless?
- **Pass:** All three components are present and functional. **Fail:** Any component is missing or generic.

---

## Annotated Bad Examples

### Example 1 — "Really good RevOps is boring"

> Really good RevOps is boring. No fires. No heroics. Just a system that runs.

**Hook:** Contrarian — works. But single-component. Missing Conflict or Ongoing to deepen the pull. [Partial pass]

> Most teams never get there because they fall into one of two traps.

**Retain setup:** Uses list structure — good. But "two traps" promises a model. What follows is description, not a model.

> Trap one: addiction to reactivity. [...] Trap two: building for the whiteboard instead of the field.

**Anti-pattern 1 — Opinion Without Framework:** Two traps named and described with vivid language. No diagnostic tool, no framework to escape them, no criteria to identify which trap you're in.

> The best operators I know are what I'd call productively paranoid.

**Anti-pattern 4 — Philosophy Over Practicality:** Interesting label. Zero definition. Impossible to apply.

> Get off the treadmill and ask two questions: What's the single most important thing...? And what's the simplest way to do it?

**Anti-pattern 3 — Vague CTA:** Two questions with no answers. No framework for answering them. No next step.
**Anti-pattern 5 — No Conversion Mechanism:** Post ends. No lead magnet, no link, no follow-up path.
**Anti-pattern 6 — Reward Mismatch:** Hook promised a boring, reliable system. Delivery: two vibes and two unanswered questions.

**Cross-skill verdict:** Fails Check 1 (Reward), Fails Check 2 (no CTA, no secrets given), Partial fail Check 3 (weak hook components).

---

### Example 2 — "The worst thing you can build in RevOps"

> The worst thing you can build in RevOps is something you know is wrong.

**Hook:** Contrarian, Conflict — two components. Solid. [Pass]

> It starts the same way every time. An exec asks for something specific. You know it's a bad idea. But you build it anyway.

**Retain:** Story structure — engages. But the story is the entire content. There's no model being built.

> Leaders with big personalities and strong opinions don't actually want you to nod along. They want someone who will tell them when they're headed in the wrong direction.

**Anti-pattern 1 — Opinion Without Framework:** True observation. Still just an opinion. How do you push back? What words do you use? What's the framework for "respectful disagreement with a better option ready"?

> I've disagreed with plenty of executives. Respectfully, with a better option ready.

**Anti-pattern 2 — Narrative Without Takeaway:** Relatable. But "have a better option ready" is not instruction — it's a description of what happened. No script, no model, no framework.

> Stop building things you know aren't right.

**Anti-pattern 3 — Vague CTA:** Imperative without instruction. How? When? What's the actual process?
**Anti-pattern 5 — No Conversion Mechanism:** Post ends cold. Nothing to click, respond to, or follow up on.

**Cross-skill verdict:** Fails Check 1 (Reward), Fails Check 2 (no CTA, no secrets), Passes Check 3 (hook is strong).

---

## The Fix Protocol

When a post fails any check:

1. **Identify the weakest dimension** — which of the 6 anti-patterns applies? Which cross-skill check failed hardest?
2. **Apply the relevant skill:**
   - Reward failure → `content-framework/SKILL.md` — rewrite the ending to deliver a real framework, steps, or secret
   - CTA failure → `lead-magnets/SKILL.md` — add a lead magnet pointer or response prompt
   - Hook failure → `hooks/SKILL.md` — upgrade the opening line using a stronger category and more components
   - Ad structure failure → `paid-ads/SKILL.md` — rebuild the callout, value angle, or CTA using the Callout/Value/CTA framework
3. **Re-run the quality gate** — all applicable checks must pass before the post is output
4. **Do not ship a post that passes some checks but fails others.** All applicable checks are required — there are no partial passes.
