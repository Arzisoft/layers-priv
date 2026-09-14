---
course: "The Mastery"
module: "Module 4: Rules, Context Files, and Project Configuration"
lesson: "Module 4: Rules, Context Files, and Project Configuration — Study Guide"
type: "course_lesson"
post_id: 107125844
space_id: 24191170
source: "https://the-faction.mn.co/posts/107125844"
updated: "2026-09-10T20:06:53Z"
---

# Module 4: Rules, Context Files, and Project Configuration — Study Guide

# Cursor Mastery

### T4 The Mastery | Module 4 Study Guide

## Module 4: Rules, Context Files, and Project Configuration

> Direct AI to stay consistent across every session by configuring the rules and context it reads before it writes anything.

## Why This Matters

Anything you find yourself telling the AI twice belongs in a rules file. Rules turn your standards into standing instructions that ride along with every request, so the tenth session behaves like the first and a teammate's Cursor behaves like yours. This is how builders get consistency without repeating themselves.

## Core Concepts

**Rules are standing instructions.** A rules file (the .cursorrules file at the project root is the long-standing pattern; newer versions add a rules directory with multiple scoped files) contains instructions Cursor includes with your requests automatically. Stack choices, naming conventions, boundaries, tone: written once, applied always.

**Project rules beat session memory.** Conversations end; rules persist. If the AI must always use your existing component library, never touch the payments module without being asked, and write comments in plain English, those instructions should not depend on you remembering to say them.

**Rules are for the durable, not the momentary.** "We use PostgreSQL, all dates in UTC" is a rule. "Center that button" is a request. Rules files loaded with one-off instructions become noise that dilutes the instructions that matter.

**Rules travel with the repo.** Committed to the project, rules configure every builder's AI the same way. This is team configuration: shared standards enforced at the directing layer, not in a wiki nobody reads.

**Context files extend the same idea.** Beyond rules, you can keep project context documents (architecture notes, domain glossaries, decision records) in the repo and reference them in requests. Rules shape behavior; context files supply knowledge.

## How It Works

1. **Create the rules file.** Add .cursorrules at the project root (or use the rules directory in current versions; check settings for which your version supports). Plain text instructions, written like you would say them.
1. **Start with the big four:** the stack ("This is a Next.js app with Tailwind and Supabase"), the conventions ("components in /components, one per file, named exports"), the boundaries ("never modify /lib/payments without being explicitly asked"), and the style ("prefer simple readable solutions over clever ones; explain changes in plain language").
1. **Add rules when you repeat yourself.** Every repeated correction is a candidate. Corrected the AI twice about date handling? That is a rule now.
1. **Keep it short and specific.** A focused page outperforms a rambling manifesto. Every line should change behavior; delete lines that do not.
1. **Commit it.** Rules belong in version control so the whole team's AI follows the same standards.
1. **Maintain it.** When the stack or conventions change, update the rules the same day. Stale rules actively steer the AI wrong.

## Directing AI

- **Bootstrap:** "Analyze this codebase and draft a .cursorrules file covering the stack, the conventions you observe, and sensible boundaries. I will edit it."
- **Distill from corrections:** "Here are three corrections I have given you this week: [paste]. Turn them into concise rules for the rules file."
- **Audit:** "Read the current rules file. Which rules are vague, contradictory, or no longer match the codebase?"
- **Scope check:** "Given these rules, tell me what you will and will not do when I ask you to modify the checkout." Confirm the boundaries actually bind.
- Note for builders using both tools: Claude Code reads its own standing-instruction file (CLAUDE.md). Same principle, different filename; keep the contents aligned so both tools follow the same standards.

## Common Mistakes

- **No rules file at all.** Every session restarts your standards from zero, and consistency depends on your memory.
- **Novel-length rules.** The important instructions drown. Short and sharp wins.
- **One-off requests stored as rules.** "Make the header blue" is not a standard; it is clutter that confuses future requests.
- **Stale rules after a stack change.** The AI keeps writing for the database you migrated off last month.
- **Rules never committed.** Your AI is configured; your teammate's is feral. Same repo, different behavior.
- **Boundaries never tested.** You wrote "do not touch payments" and never verified the AI honors it before it mattered.

## Real-World Application

A two-builder team ships client sites. Their repo carries a rules file: the stack, the component conventions, a boundary around the billing module, and a rule that every new page must reuse the shared layout. A new client build starts; builder two directs "add a testimonials page" with no other instructions, and the output lands in the right folder, using the shared layout, matching conventions, because the rules rode along. A month later they migrate styling libraries; the rules file is updated in the same pull request, so neither builder's AI ever writes for the old library. Their consistency is not discipline; it is configuration.

## Decision Framework

- **Said it twice?** Rule.
- **True for this project always?** Rule.
- **True for this request only?** Request, not rule.
- **Must never happen without permission?** Boundary rule, and test that it binds.
- **Knowledge rather than instruction (architecture, domain terms)?** Context file, referenced when relevant, not crammed into rules.
- **Team standard?** Rule, committed to the repo, updated through pull requests like code.

## Tool and Platform Notes

- .cursorrules at project root is the widely supported pattern; recent Cursor versions add a rules directory supporting multiple files and scoping. Principles transfer; check docs.cursor.com for your version's format.
- Cursor also offers user-level rules (applying to you across all projects) in settings; keep personal preferences there, project standards in the repo.
- Context documents are ordinary markdown files in the repo; reference them in requests when their knowledge is relevant.
- Claude Code's CLAUDE.md serves the identical purpose in that tool; teams using both keep the two files consistent.

## Key Takeaways

- Rules are standing instructions that ride along with every request.
- Put the stack, conventions, boundaries, and style in rules; keep one-offs out.
- Short, specific rules outperform long manifestos.
- Commit rules to the repo so every builder's AI behaves the same.
- Update rules the day the project changes; stale rules steer the AI wrong.

## What's Next

Your project now directs the AI even when you are not typing. Module 5 turns to when things break: directing Cursor through debugging and error resolution without getting lost in loops.

## Exam Prep Notes

Focus on: what belongs in rules versus a single request, the big four rule categories, why rules get committed to the repo, the said-it-twice test, keeping rules current, boundaries and testing them, and how CLAUDE.md parallels .cursorrules. Scenarios will describe repeated behavior problems and ask which configuration fixes them.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107125844_
