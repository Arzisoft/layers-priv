---
course: "The Mastery"
module: "Module 3: Multi-File Editing and Codebase Navigation"
lesson: "Module 3: Multi-File Editing and Codebase Navigation — Study Guide"
type: "course_lesson"
post_id: 107125806
space_id: 24191170
source: "https://the-faction.mn.co/posts/107125806"
updated: "2026-09-10T20:05:51Z"
---

# Module 3: Multi-File Editing and Codebase Navigation — Study Guide

# Cursor Mastery

### T4 The Mastery | Module 3 Study Guide

## Module 3: Multi-File Editing and Codebase Navigation

> Direct AI to make coherent changes across many files at once, and review them diff by diff before they land.

## Why This Matters

Real projects are not one file. A feature touches a page, an API route, a data model, and a style file, and the AI needs to see the right slice of all of them to change them coherently. Builders who control what the AI sees across a codebase ship consistent features; builders who do not get changes that work in one file and break in three others.

## Core Concepts

**Codebase awareness comes from the index.** When indexing is on, Cursor builds a searchable map of your project. Your instructions can then pull in relevant code the AI finds itself, not just files you manually attach. The index is why "add this to the checkout flow" can work without you naming every file.

**References beat descriptions.** Cursor lets you reference files, folders, and symbols directly in your message (the @ symbol is the long-standing pattern). "Update @cart.js to match how @checkout.js handles errors" is precise. "Update the cart file like the checkout one" forces the model to guess which files you mean.

**Coherence is your responsibility.** The AI edits what it sees. If a change should ripple to five files and the AI only saw three, two files are now inconsistent. Directing multi-file work means thinking about the blast radius of a change and making sure the whole radius is in view.

**Navigation is a directing skill too.** In a large project you will not know where everything lives. The AI does, if the index is on. Asking "where is X handled?" is faster than clicking through folders, and it teaches you the project as you build.

## How It Works

1. **Confirm indexing.** For any project bigger than a handful of files, check that codebase indexing is enabled and finished before heavy work.
1. **Reference explicitly when precision matters.** Attach or @-reference the files that must change and the files that define the pattern to follow.
1. **Let the index work when discovery matters.** For "find where orders get created and add a log entry there," let the AI search the codebase and report what it found before it edits.
1. **State the blast radius.** "This change affects the form component, the API route, and the validation module. Update all three consistently."
1. **Review diffs file by file.** Multi-file output arrives as a set of diffs. Read each one. Consistency errors hide in the file you skip.
1. **Verify the seams.** After accepting, run the app and exercise the paths where the changed files meet. Seams are where multi-file edits fail.

## Directing AI

- **Discovery first:** "Search this codebase and tell me every place user email addresses are read or written. List file and purpose. Do not change anything yet."
- **Pattern anchoring:** "Add a settings page. Follow the structure of @ProfilePage and register the route the same way the other pages are registered."
- **Explicit radius:** "Rename the field 'username' to 'handle' everywhere it appears: model, API, and every component that displays it. List the files you changed."
- **Coherence check:** "Review the last set of changes across all modified files. Are naming, error handling, and imports consistent with the rest of the project?"
- **Navigation:** "Walk me through how a request flows from the booking form to the database in this project. Name each file it passes through."

## Common Mistakes

- **Trusting memory over the index.** In long sessions the model's view drifts; re-reference files rather than assuming it still sees them accurately.
- **Underdescribing the radius.** You asked for the form change and forgot the API expects the old field name. Name every side of a contract you change.
- **Referencing nothing.** Generic descriptions of files force guesses, and the guess picks the wrong file in projects with similar names.
- **Reviewing only the biggest diff.** The one-line diff in a config file is the one that breaks production.
- **Editing five things in one giant instruction.** Batch related changes, but split unrelated ones into separate directed passes.
- **Skipping the seam test.** Each file works alone; the handoff between them is what you failed to run.

## Real-World Application

You take over a client's existing app: 200 files, no documentation. Day one, you direct: "Map this codebase. What are the main areas, what framework and conventions does it use, where does authentication happen?" Twenty minutes of directed exploration replaces a week of reading. The client wants phone numbers added to user profiles. You direct discovery ("every file that touches the user model"), get six files back, then direct the change across all six with the model file as the anchor. Diffs reviewed one by one, seams tested by creating a user end to end. The feature lands consistent on the first deploy because the whole radius was in view.

## Decision Framework

- **Do I know exactly which files change?** Reference them explicitly and direct the edit.
- **Do I not know where something lives?** Direct discovery first, edit second.
- **Is the change one file with no contract to anything else?** A simple scoped instruction is enough.
- **Does the change cross a contract (form to API, model to display)?** Name both sides and require consistency.
- **Is the project huge?** Work area by area; direct the AI to keep each pass scoped to one region and confirm boundaries.

## Tool and Platform Notes

- The @-reference pattern covers files, folders, and symbols; the exact menu of reference types grows across versions, so explore what @ offers in your current build.
- Indexing settings include ignore patterns; exclude build output and dependency folders so the index stays relevant.
- Cursor's diff review interface shows per-file accept/reject controls: use them, partial acceptance is normal.
- Claude Code handles the same multi-file work from the terminal and can be preferable for very large mechanical sweeps; Cursor's visual diff review is the advantage for changes you want to inspect closely.

## Key Takeaways

- The codebase index is what turns "the checkout flow" from a guess into a lookup.
- Reference files and symbols explicitly when precision matters; direct discovery when it does not.
- Every change has a blast radius; the AI edits only what it sees, so put the whole radius in view.
- Review multi-file output diff by diff and test the seams between changed files.
- Navigation questions to the AI are the fastest way to learn an unfamiliar project.

## What's Next

You can direct changes across a codebase. Module 4 makes that direction persistent: rules files and project configuration that shape AI behavior on every request without you repeating yourself.

## Exam Prep Notes

Focus on: what the index enables, explicit references versus descriptions, discovery-then-edit as a pattern, blast radius thinking, diff-by-diff review, seam testing, and when a huge project calls for scoped area-by-area passes. Scenarios will ask what a builder should direct first and what they failed to put in view.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107125806_
