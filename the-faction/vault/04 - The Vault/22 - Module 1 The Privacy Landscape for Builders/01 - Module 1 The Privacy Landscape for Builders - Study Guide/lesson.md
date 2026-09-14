---
course: "The Vault"
module: "Module 1: The Privacy Landscape for Builders"
lesson: "Module 1: The Privacy Landscape for Builders — Study Guide"
type: "course_lesson"
post_id: 107139910
space_id: 24302166
source: "https://the-faction.mn.co/posts/107139910"
updated: "2026-09-10T19:50:10Z"
---

# Module 1: The Privacy Landscape for Builders — Study Guide

# Data Privacy Fundamentals

### T6 The Vault | Module 1 Study Guide

## Module 1: The Privacy Landscape for Builders

> Direct AI to treat every build as a privacy decision, because every system that touches people's data already is one.

## Why This Matters

Every system you direct AI to build collects, stores, or moves data about people, which means every project you ship is a privacy decision whether you made it consciously or not. Builders who understand the privacy landscape win client trust, pass procurement reviews, and avoid the expensive rebuilds that follow privacy mistakes. Builders who ignore it ship liabilities.

**One thing before anything else: this course is not legal advice.** It teaches you what to build, which questions to ask, and when to bring in a lawyer. When a client's situation involves real legal exposure, regulated industries, or enforcement risk, a qualified privacy attorney makes the legal call. Your job is to build systems that make compliance possible and to recognize the moments that need counsel.

## Core Concepts

**Privacy is a builder's concern, not just a lawyer's.** Laws describe obligations; systems fulfill them. A deletion right means nothing if the system cannot actually delete. A consent requirement means nothing if the signup flow never asks. The gap between legal obligation and working software is exactly where builders live.

**The regulatory landscape is a patchwork with common DNA.** GDPR (the EU's General Data Protection Regulation) is the most influential privacy law in the world and reaches any business handling EU residents' data, wherever that business sits. CCPA and its successor CPRA cover California residents. Other US states have followed with their own laws, and countries like Brazil (LGPD) and Canada (PIPEDA) run their own regimes. The details differ; the core ideas repeat: know what data you hold, have a reason to hold it, tell people, protect it, and honor their rights over it.

**Privacy is a competitive advantage.** Enterprise clients send security and privacy questionnaires before signing. Consumers increasingly choose products they trust. A builder who can say "here is how this build handles personal data, and here is why" closes deals that a shrug loses. Privacy-competent builders are rarer than they should be, and clients pay for the difference.

**The cost of getting it wrong compounds.** GDPR fines can reach 4% of global annual revenue. US state enforcement is growing. But fines are the visible cost; the common ones are quieter: a breach that exposes data you never needed to collect, a lost enterprise deal over a failed questionnaire, a rebuild because rights handling was never designed in, a client relationship ended by an avoidable incident.

**You completed Compliance Foundations; this course goes deeper on one domain.** Compliance Foundations for Builders gave you the general frame: regulations as build requirements, scoping questions, and documentation habits. Data privacy is the domain where that frame gets the most use, and this course is the gateway to the deeper privacy chain that follows it.

## How It Works

1. **Identify whose data a build touches.** Users, customers, employees, end users of your client's product: each population may sit under different laws depending on where they live.
1. **Ask the two scoping questions early.** Where are the people whose data this system handles? What kind of data does it handle? The answers determine which regimes apply and how careful the build must be.
1. **Treat regulations as build requirements.** "GDPR applies" translates into concrete capabilities: consent capture, notice display, export, deletion, records. You will build these capabilities throughout this course.
1. **Know the escalation line.** You can build the mechanics. A lawyer decides contested questions: whether a legal basis holds, how a regulator would view a practice, what a contract must say. When the question is "is this legal?" rather than "how do I build this?", escalate.
1. **Document as you go.** What data, why, where it lives, who can reach it. This habit from Compliance Foundations becomes the backbone of every privacy capability in later modules.

## Directing AI

- "List the personal data this feature will collect, and for each item, why the feature needs it. Output as a table I can review with the client."
- "The users of this product are in the EU and the US. Summarize which privacy regimes likely apply and what build capabilities they imply. Flag anything that needs a lawyer's judgment."
- "Draft five privacy questions I should ask this client before scoping the build, in plain language."
- "Review this project plan and flag every point where personal data is collected, stored, or shared with a third party."
- Pattern: use AI to inventory, summarize, and flag; use lawyers to decide legal questions; use this course to know which is which.

## Common Mistakes

- **Treating privacy as a launch-week task.** Rights handling and consent bolted on late cost multiples of what designed-in versions cost.
- **Assuming small projects are exempt.** Most privacy laws scale obligations, not existence; a five-user tool handling health data can carry more risk than a big newsletter.
- **Playing lawyer.** Confidently telling a client "this is GDPR compliant" is a legal opinion you are not qualified to give. Say what you built and what it enables; let counsel bless it.
- **Ignoring geography.** Where users live determines which laws follow the data, and "we are a US company" does not exempt EU users' data.
- **Collecting first, justifying later.** Data grabbed without a purpose becomes pure liability: it can leak, and it cannot be defended.

## Real-World Application

A client asks for a coaching platform: signups, payment, session notes, progress tracking. Before directing a single build step, you ask where the users are (EU and UK included) and what data flows (names, emails, payments, and session notes that may contain health-adjacent details). That twenty-minute conversation reshapes the build: consent and notice at signup, a data inventory in the project docs, deletion capability designed into the data model, and a flag to the client that session notes may need legal review for sensitive-data handling. The client, who never thought about any of this, now sees you as the professional in the room. The build costs slightly more. The liability costs far less.

## Decision Framework

- **Does the build touch data about people?** Privacy applies. (It almost always does.)
- **Are users in the EU/UK?** Assume GDPR-grade requirements.
- **US users?** Check state laws, with California as the baseline assumption for consumer products.
- **Health, financial, kids', or other sensitive data?** Raise the care level and expect a lawyer touchpoint.
- **Is the question about how to build a capability?** This course. **Is it whether a practice is legal?** Counsel.
- **Client resists privacy scope?** Document your recommendation in writing and let them decide with eyes open.

## Tool and Platform Notes

- Official sources beat summaries: the EU's GDPR portal, the California AG's CCPA pages, and regulator guidance (like the UK ICO) are readable and current.
- Your AI can summarize regulations and draft inventories, but its knowledge has a date; verify current thresholds and rules against official sources for anything decision-grade.
- Cloud platforms (AWS, Google Cloud, Azure, Vercel, Supabase and peers) publish compliance documentation and offer data processing agreements; you will use these in Module 5.
- Compliance Foundations for Builders (#11) is the prerequisite frame for this course; revisit its scoping and documentation habits if they are not yet automatic.

## Key Takeaways

- Privacy obligations become real in systems, which makes privacy a builder's concern.
- The landscape is a patchwork (GDPR, CCPA/CPRA, state and national laws) with repeating core ideas.
- Privacy competence wins deals; privacy failures cost fines, breaches, rebuilds, and relationships.
- This course is not legal advice: build the mechanics, escalate legal judgment to counsel.
- Ask early: whose data, what data, where do they live.

## What's Next

Everything in privacy starts with one question: is this personal data? Module 2 gives you the working definitions and the classification skill every later module builds on.

## Exam Prep Notes

Focus on: why privacy is a builder's concern, what GDPR and CCPA are and roughly who they cover, privacy as competitive advantage, the categories of cost when privacy goes wrong, the builder-versus-lawyer division of labor, and the early scoping questions. Scenarios will test whether you route questions to building or to counsel correctly.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107139910_
