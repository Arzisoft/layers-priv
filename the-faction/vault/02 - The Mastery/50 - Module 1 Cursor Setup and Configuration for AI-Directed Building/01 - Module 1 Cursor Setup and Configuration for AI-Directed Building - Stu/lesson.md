---
course: "The Mastery"
module: "Module 1: Cursor Setup and Configuration for AI-Directed Building"
lesson: "Module 1: Cursor Setup and Configuration for AI-Directed Building — Study Guide"
type: "course_lesson"
post_id: 107125632
space_id: 24191170
source: "https://the-faction.mn.co/posts/107125632"
updated: "2026-09-10T20:04:26Z"
---

# Module 1: Cursor Setup and Configuration for AI-Directed Building — Study Guide

# Cursor Mastery

### T4 The Mastery | Module 1 Study Guide

## Module 1: Cursor Setup and Configuration for AI-Directed Building

> Direct AI to build inside a properly configured environment, so every session starts with the right model, the right context, and settings that work for you instead of against you.

## Why This Matters

Cursor is one of the primary environments where builders direct AI to produce working software. A bad setup costs you every single session: wrong model, missing context, settings that fight you. Thirty minutes of deliberate configuration turns Cursor from a downloaded app into a production tool that does what you tell it.

## Core Concepts

**Cursor is a directing environment, not a typing environment.** Cursor is built on the same foundation as VS Code, but its purpose in your hands is different: you describe what you want, the AI produces it, and you review and steer. Every setup decision should serve that loop.

**The interface has four zones you need to know.** The editor (where produced files appear), the file explorer sidebar (your project's structure), the chat panel (where you talk to the AI), and the terminal (where things run). You will spend most of your time in the chat panel and the editor, in that order.

**The model connection is the engine.** Cursor routes your instructions to an AI model. Which model, and with what settings, determines the quality of everything you get back. Cursor ships with default model access through your account, and you can select among available models per conversation.

**Settings shape AI behavior before you type a word.** Codebase indexing, privacy mode, rules files, and model selection all change what the AI sees and how it responds. These are standing decisions, made once, that improve every future request.

**Versions change, principles do not.** Cursor updates frequently. Menu names move, panels get redesigned, features get renamed. Anchor on the principles: know your model, control your context, keep indexing on for real projects, and check settings after major updates. Those survive every release.

## How It Works

1. **Install.** Download Cursor from cursor.com and install it like any desktop app. On first launch it can import your VS Code settings and extensions if you have them; accept this if you are migrating, skip it for a clean start.
1. **Sign in and connect AI.** Create or sign into your Cursor account. This activates the AI features. In settings, find the models section and confirm which models are available and which is selected by default.
1. **Learn the layout.** Open the chat panel (the keyboard shortcut is worth memorizing; check the current one in the menu since shortcuts occasionally change between versions). Identify the editor, explorer, chat, and terminal zones.
1. **Open a real project folder.** Cursor works best when it can see your whole project. Always open the project folder, never a single loose file. This gives the AI the structure it needs.
1. **Turn on codebase indexing.** In settings, enable codebase indexing for your project. This lets Cursor build an index of your files so the AI can find relevant code when you reference the project.
1. **Set privacy mode deliberately.** If you work with client code or sensitive material, enable privacy mode so your code is not retained for training. Make this decision per project, on purpose, not by default accident.
1. **Confirm the terminal works.** Open the integrated terminal and run one command. If your project needs a runtime installed (Node, Python, or another), the AI can direct you through installing it: ask in chat.

## Directing AI

Your setup phase is itself a directing exercise. Useful prompts:

- "I just opened this project folder in Cursor. Look at the structure and tell me what this project is, what it needs to run, and whether anything looks misconfigured."
- "Direct me through connecting this project to [service]. List what you need from me at each step."
- "Review my Cursor setup for a production project: what settings should I confirm before I start building?"
- When something in the interface confuses you, ask Cursor itself: "Where do I find [feature] in the current version of Cursor?" The AI plus the official docs beat memorized menu paths that go stale.

Pattern to internalize: state your situation, state your goal, ask for the steps. You are directing configuration the same way you will direct building.

## Common Mistakes

- **Opening single files instead of the project folder.** The AI loses all project context and gives you generic answers.
- **Never checking which model is selected.** Different models have different strengths and costs; running the wrong one silently degrades every response.
- **Leaving indexing off on large projects.** The AI cannot reference what it cannot find, so answers ignore your actual code.
- **Ignoring privacy mode on client work.** Decide data handling before you paste a client's system into a chat.
- **Memorizing menus instead of principles.** A version update breaks your memorized path; it does not break "check model, check indexing, check rules."
- **Treating setup as one-time.** After major Cursor updates, spend two minutes confirming your settings survived.

## Real-World Application

You land a client project: a booking site that needs a payment flow added. You open the project folder in Cursor, enable indexing, switch on privacy mode because it is client code, and confirm your model selection. Before touching anything, you ask: "Analyze this codebase. What framework is it, how is it organized, and where does checkout currently happen?" The AI maps the project in one response. You now direct changes with full context instead of guessing, and the whole engagement moves faster because the ten-minute setup made every following instruction land on an informed model.

## Decision Framework

- **Import VS Code settings or start clean?** Import if you already work in VS Code daily; clean if Cursor is your first environment, so defaults stay predictable.
- **Privacy mode on or off?** On for client work and anything sensitive. Off is acceptable for your own experiments if you have no confidentiality concerns.
- **Which model?** Use the strongest available model for planning, architecture, and complex builds; a faster model is fine for small, mechanical edits. When unsure, favor the stronger model and adjust when speed matters more than depth.
- **Cursor or Claude Code for this project?** Cursor gives you a visual environment: files, diffs, and chat side by side, which suits builders who want to see everything. Claude Code runs in a terminal and excels at long autonomous task runs. Many builders use both; set up Cursor first as your daily environment.

## Tool and Platform Notes

- **Cursor** (cursor.com): the environment itself. Download the desktop app; it runs on Mac, Windows, and Linux.
- **VS Code compatibility:** Cursor is a fork of VS Code, so VS Code themes, keybindings, and most extensions carry over.
- **Model providers:** Cursor provides access to frontier models from multiple providers through your account; selection happens in settings and per conversation.
- **Claude Code:** Anthropic's terminal-based directing tool. Not a competitor to your Cursor setup so much as a second tool for long-running autonomous work. Later modules compare them where the choice matters.
- Cursor's official docs (docs.cursor.com) are the current source of truth when the interface shifts.

## Key Takeaways

- Open project folders, never loose files, so the AI sees structure.
- Know which model you are running; it silently determines output quality.
- Enable codebase indexing for any real project.
- Set privacy mode deliberately for client and sensitive work.
- Learn principles, not menu positions; Cursor updates frequently and principles survive.

## What's Next

Your environment is configured. Module 2 covers the two primary ways you direct AI inside it: Composer and Chat, and when each one is the right tool for the instruction you are about to give.

## Exam Prep Notes

Focus on: the purpose of each interface zone, why project folders beat single files, what codebase indexing does for the AI, when privacy mode matters, how to think about model selection, and which setup habits survive version changes. The exam tests judgment about configuration decisions, not memorized menu locations.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107125632_
