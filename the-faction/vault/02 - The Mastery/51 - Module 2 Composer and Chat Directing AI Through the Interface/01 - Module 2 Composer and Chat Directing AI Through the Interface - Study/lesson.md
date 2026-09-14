---
course: "The Mastery"
module: "Module 2: Composer and Chat: Directing AI Through the Interface"
lesson: "Module 2: Composer and Chat: Directing AI Through the Interface — Study Guide"
type: "course_lesson"
post_id: 107125756
space_id: 24191170
source: "https://the-faction.mn.co/posts/107125756"
updated: "2026-09-10T20:05:09Z"
---

# Module 2: Composer and Chat: Directing AI Through the Interface — Study Guide

# Cursor Mastery

### T4 The Mastery | Module 2 Study Guide

## Module 2: Composer and Chat: Directing AI Through the Interface

> Direct AI through the interface built for the job, writing instructions as specifications instead of requests.

## Why This Matters

Cursor gives you more than one way to talk to the AI, and choosing the wrong mode for the job wastes time and produces worse results. Builders who understand what each mode is for, and what Cursor actually sends to the model, get clean multi-file builds where others get fragments and confusion.

## Core Concepts

**Chat is for thinking; Composer is for changing.** Chat (sometimes labeled "Ask" in recent versions) answers questions, explains code, and discusses approaches without touching your files. Composer (evolved into "Agent" mode in newer versions) plans and applies real changes across one or many files. Names shift between versions; the split between a discussion mode and a make-changes mode persists.

**Every message you send travels with context.** Cursor does not send only your words. It packages your instruction with relevant context: the active file, files you reference, selected code, and results from the codebase index. Understanding this is the difference between directing precisely and hoping.

**Instructions are specifications, not wishes.** "Make the login better" gives the model nothing. "Add validation to the login form: email format checked, password minimum 8 characters, inline error messages under each field" gives it a specification. The quality of what you get back tracks the quality of what you specify.

**Iteration is the normal rhythm.** First output is a draft. You review, you correct, you tighten. Builders who expect perfection in one shot get frustrated; builders who expect two or three directed passes ship.

## How It Works

**Using Chat:**

1. Open the chat panel and ask. Reference specific files or code so the answer is grounded in your project.
1. Use it for: "Explain what this function does," "Why would this error happen," "What are two ways to structure this feature, and the tradeoffs?"
1. Nothing changes on disk. Chat is your zero-risk mode for understanding and planning.

**Using Composer / Agent:**

1. Describe the outcome: what should exist when the AI is done, including files, behavior, and constraints.
1. The AI plans, produces changes, and presents them as diffs across the affected files.
1. Review the diffs. Accept what is right, reject or redirect what is not. Never blind-accept a multi-file change.
1. Run the result. Feed anything broken back in and iterate.

**Multi-step requests:** For anything with more than a couple of moving parts, direct the plan first: "Before changing anything, list the steps you will take and the files you will touch." Approve or adjust the plan, then say "proceed." This one habit prevents most runaway edits.

**The iteration loop:** direct, review, run, correct. Each correction should name what was wrong and what right looks like: "The error message shows above the field; move it below, styled like the other form hints."

## Directing AI

Instruction patterns that work in both modes:

- **Outcome plus constraints:** "Build a contact form that posts to /api/contact. Constraints: match the site's existing styles, validate on the client, show a success state without a page reload."
- **Plan-first for multi-step:** "Plan before acting. List steps and files, wait for my go."
- **Scoped correction:** "Only change the date formatting in dashboard. Do not touch anything else."
- **Grounded question (Chat):** "Looking at the checkout flow in this project, where would a discount code check belong, and why there?"
- **Contrast with Claude Code:** the instruction discipline is identical in both tools. Claude Code takes the same outcome-plus-constraints direction in a terminal and can run longer without check-ins. Cursor's advantage is that you watch the diffs land in a visual editor as you iterate.

## Common Mistakes

- **Using Composer for questions.** You wanted an explanation and got file edits. Ask in Chat when you do not want changes.
- **Using Chat when you want changes, then pasting code around by hand.** Composer applies changes for you; that is its job.
- **Vague instructions.** "Fix the styling" produces guesses. Name the element, the current behavior, and the desired behavior.
- **Skipping the plan on multi-step work.** The AI makes ten changes, three of them wrong, and untangling costs more than planning would have.
- **Blind-accepting diffs.** You are the reviewer. Accepting without reading is how mystery bugs enter a project.
- **Restarting the conversation instead of correcting.** A focused correction inside the same conversation keeps all the context you built.

## Real-World Application

A builder needs an admin dashboard page added to a client's app: a table of users, search, and a deactivate button. In Chat: "Looking at this codebase, how are existing pages structured and what conventions should a new admin page follow?" The answer maps the pattern. Then in Composer: "Add an admin users page following that structure. Table of users from /api/users, search box filtering by name and email, deactivate button per row calling /api/users/:id/deactivate with a confirmation prompt. Plan first." The plan lists four files. One correction ("put the route behind the existing auth check like the other admin routes"), then proceed. Diffs reviewed, accepted, run, shipped. Two modes, each doing its job.

## Decision Framework

- **Question, explanation, or approach comparison?** Chat.
- **Any change to any file?** Composer / Agent.
- **Multi-file or multi-step change?** Composer with plan-first.
- **Not sure what you want yet?** Chat to explore, then Composer to build what you settled on.
- **Long autonomous run across a big task list?** Consider Claude Code for the run, then Cursor to review and refine the results visually.

## Tool and Platform Notes

- Mode names have shifted across Cursor versions (Chat vs Ask, Composer vs Agent). Identify modes by what they do: one discusses, one changes files.
- Cursor shows context indicators for what is attached to your message; glance at them so you know what the model can see.
- Keyboard shortcuts exist for both modes and are worth learning from the current menu, since they occasionally change.
- Claude Code (Anthropic) accepts the same directing patterns in a terminal; skills you build here transfer directly.

## Key Takeaways

- Chat discusses without touching files; Composer plans and applies real changes.
- Cursor sends your words plus context: active files, references, and index results.
- Specify outcomes and constraints; vague instructions produce vague builds.
- Direct a plan before any multi-step change, then approve and proceed.
- Review every diff. Iteration is the rhythm; blind acceptance is the risk.

## What's Next

You can direct single conversations well. Module 3 scales that skill across a whole codebase: multi-file editing, referencing files and symbols, and keeping the AI's picture of a large project coherent.

## Exam Prep Notes

Focus on: which mode fits which task, what context travels with a message, the plan-first pattern for multi-step work, what makes an instruction a specification, the review-and-iterate loop, and how the same directing discipline maps to Claude Code. The exam presents builder scenarios and asks which mode or instruction pattern is right.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107125756_
