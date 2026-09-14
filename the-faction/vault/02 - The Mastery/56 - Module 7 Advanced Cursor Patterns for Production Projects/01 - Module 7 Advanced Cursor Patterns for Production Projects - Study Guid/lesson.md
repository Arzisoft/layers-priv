---
course: "The Mastery"
module: "Module 7: Advanced Cursor Patterns for Production Projects"
lesson: "Module 7: Advanced Cursor Patterns for Production Projects — Study Guide"
type: "course_lesson"
post_id: 107125942
space_id: 24191170
source: "https://the-faction.mn.co/posts/107125942"
updated: "2026-09-10T20:10:22Z"
---

# Module 7: Advanced Cursor Patterns for Production Projects — Study Guide

# Cursor Mastery

### T4 The Mastery | Module 7 Study Guide

## Module 7: Advanced Cursor Patterns for Production Projects

> Direct AI through real client work, with the patterns that hold up when the project is production and the deadline is not yours.

## Why This Matters

Everything so far scales down gracefully to small projects. This module is about scaling up: codebases with hundreds of files, refactors that touch dozens of them, quality standards a client is paying for, and the judgment to know when Cursor is the wrong tool for the job in front of you. This is where directing becomes production practice.

## Core Concepts

**Large codebases demand scoped direction.** No model holds a 500-file project in view at once. Production directing means working in deliberate scopes: one area, one contract, one pass, with explicit references anchoring each scope. The index finds things; your scoping keeps changes coherent.

**Refactoring at scale is planned, incremental, and verified.** A sweeping "modernize this codebase" instruction is how projects die. Production refactors run as a directed sequence: map what exists, plan the stages, execute one stage per pass, verify each stage before the next, commit between stages.

**AI-assisted review is a second pass, not a substitute.** Directing the AI to review changes (consistency, security-sensitive spots, missed edge cases, divergence from the rules file) catches real problems. It supplements your own diff reading; the builder remains the reviewer of record.

**Quality standards live in configuration plus verification.** Your rules file states the standards; linting enforces the mechanical ones; directed review checks the judgment ones; and tests, where they exist, verify behavior. Quality on production projects is a system, not a hope.

**Cursor is not always the tool.** Long fully-autonomous runs across large task lists favor Claude Code. Spreadsheet work, document production, and non-code deliverables belong in other tools. Visual design exploration belongs in design tools. Recognizing the wrong-tool moment is a mastery skill, not a betrayal of the tool.

## How It Works

**Large-codebase pattern:**

1. Direct a map once: areas, conventions, contracts. Save it as a context document in the repo.
1. Scope each session: "We are working only in the reporting area today." Reference the boundary files explicitly.
1. Cross-area changes get contract treatment: name both sides, change both sides, test the seam.

**Refactor-at-scale pattern:**

1. "Map every file that touches [the thing being refactored]. Do not change anything."
1. "Propose a staged refactor plan: stages, files per stage, risk per stage, and how we verify each stage."
1. Execute stage one only. Review diffs, run verification, commit.
1. Repeat per stage. Any stage that fails gets fixed or rolled back before the next begins.

**Review pattern:**

1. After a significant change: "Review these diffs against the rules file and the project's conventions. List issues by severity, no fixes yet."
1. Security-sensitive areas get a dedicated pass: "Review this change for security issues specifically: injection, authentication gaps, data exposure."
1. You read the diffs yourself regardless. The AI review is your second reviewer, not your replacement.

**Quality system:**

1. Rules file states standards (Module 4). 2. Linter and formatter enforce mechanics (Module 6). 3. Directed review checks judgment. 4. A smoke-test checklist per project: the five paths that must always work, run before every delivery.

## Directing AI

- **Mapping:** "Produce an architecture map of this codebase: areas, responsibilities, and the contracts between them. Output as markdown for the repo."
- **Staged planning:** "Plan the migration from [old] to [new] as stages. Each stage must leave the app working. Include a verification step per stage."
- **Severity-ranked review:** "Review this diff set. Report issues as blocker, should-fix, or nitpick. Cite file and line for each."
- **Standards check:** "Compare these changes against .cursorrules. List every divergence."
- **Wrong-tool check:** "Given this task list, which items suit an interactive Cursor session and which suit a long autonomous Claude Code run?"
- **Pre-delivery:** "Run through the smoke-test checklist in the repo and tell me what to verify manually in the browser."

## Common Mistakes

- **Directing sweeping changes in one pass.** The all-at-once refactor produces an all-at-once failure you cannot bisect.
- **Skipping the map on a codebase you inherited.** Every change is a guess about structure you never established.
- **No commits between stages.** Stage three fails and takes stages one and two down with it.
- **Treating AI review as approval.** The AI reviewed it, so it ships? You are the reviewer of record.
- **Quality by vibes.** No rules, no linting, no checklist: quality varies with your energy level, and clients notice.
- **Forcing Cursor onto non-code work.** The proposal document fought you for an hour because it wanted a document tool.

## Real-World Application

A builder inherits a client's aging 300-file app with a mandate: modernize the data layer without downtime. Week one: directed mapping, saved to the repo; a staged plan, seven stages, each leaving the app working. Weeks two through four: one stage at a time, diff review plus directed review per stage, commit per stage, smoke-test checklist before each client demo. Stage five breaks a report page; the seam test catches it before the client does, and the stage rolls back, gets re-planned smaller, and lands. The client sees a working app every single week. That is production directing: boring, staged, verified, and exactly what they are paying for.

## Decision Framework

- **New large codebase?** Map before any change.
- **Change touches many files?** Staged plan, one stage per pass, commit between.
- **Change touches auth, payments, or user data?** Dedicated security review pass.
- **Delivering to a client?** Smoke-test checklist, every time.
- **Task is long, mechanical, and well-specified?** Candidate for Claude Code autonomous run; review results in Cursor.
- **Task is not code?** Wrong tool. Documents, spreadsheets, and design go to their own tools.
- **Standard keeps slipping?** Fix the system: add the rule, add the lint, add the checklist line. Do not rely on remembering harder.

## Tool and Platform Notes

- Context documents (architecture maps, decision records, checklists) live in the repo as markdown; they compound across sessions and teammates.
- Cursor's diff review, rules, indexing, Git, and terminal are the same primitives from earlier modules; production patterns are those primitives under discipline.
- Claude Code excels at long autonomous runs over explicit task lists; hand off the mechanical sweeps, keep interactive judgment work in Cursor.
- Model choice matters more on production work: use the strongest model for planning, architecture, and review passes.

## Key Takeaways

- Scope every session on large codebases; map once, then work area by area.
- Refactors run staged, verified, and committed per stage; never all-at-once.
- Directed review is your second reviewer; you remain the reviewer of record.
- Quality is a system: rules, linting, directed review, and a smoke-test checklist.
- Know the wrong-tool moments: long autonomous runs to Claude Code, non-code work to its own tools.

## What's Next

This completes Cursor Mastery. You direct through the interface, across the codebase, with persistent configuration, through breakage, with a wired stack, at production scale. Take the exam, then carry these patterns into your next real build; they are designed to survive whatever Cursor renames next quarter.

## Exam Prep Notes

Focus on: scoped direction on large codebases, the staged-refactor sequence and why stages commit separately, directed review versus builder-as-reviewer, the four-part quality system, wrong-tool recognition including the Cursor versus Claude Code division, and pre-delivery verification. Scenarios describe production situations and ask which pattern, sequence, or tool the builder should choose.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107125942_
