---
course: "The Vault"
module: "Module 6: Privacy Rights and Request Handling"
lesson: "Module 6: Privacy Rights and Request Handling — Study Guide"
type: "course_lesson"
post_id: 107139927
space_id: 24302166
source: "https://the-faction.mn.co/posts/107139927"
updated: "2026-09-10T19:54:11Z"
---

# Module 6: Privacy Rights and Request Handling — Study Guide

# Data Privacy Fundamentals

### T6 The Vault | Module 6 Study Guide

## Module 6: Privacy Rights and Request Handling

> Direct AI to build the deletion and export paths on day one, because a right you cannot execute is a right you do not have.

## Why This Matters

Privacy laws give people enforceable rights over their data, and every one of those rights eventually arrives as a request in an inbox: send me my data, delete me, correct this, stop that. Systems either can answer or cannot, and the difference was decided when they were built. This module turns rights from legal abstractions into capabilities you design in from the start.

## Core Concepts

**The core rights, in builder terms.** Access: give me a copy of my data and tell me how it is used. Deletion (erasure): remove my data, subject to real exceptions. Portability: give me my data in a machine-readable format I can take elsewhere. Correction (rectification): fix what is wrong. Objection and opt-out: stop processing for certain purposes, marketing above all, and under CCPA-style laws, stop selling or sharing my data. Names and edges vary by regime; the buildable shapes repeat.

**Rights have deadlines.** GDPR-style: about a month, extendable for complexity. CCPA-style: 45 days, similarly extendable. Deadlines turn rights handling into an operational process with a clock, not a someday task.

**You cannot service rights over data you cannot find.** The prerequisite for every right is knowing where personal data lives: which tables, which logs, which third-party services. The data-flow map from Module 5 and the classification from Module 2 are, together, the data map that makes rights handling possible.

**Deletion is the hard one.** Erasure must reach primary storage, caches, search indexes, and the vendors processing on your behalf, and it collides with legal retention duties (tax records, fraud evidence) and with backups. Real-world deletion usually means: delete or anonymize in live systems, propagate to processors, retain what law requires with a documented reason, and let backups age out on their disclosed schedule.

**Identity verification comes first.** Sending someone's data to the wrong person is a breach caused by your rights process. Verification should be proportionate: confirm control of the account or email on file, escalating only when stakes demand it, without weaponizing verification to dodge requests.

## How It Works

Designing the capability:

1. **Maintain the data map.** From Modules 2 and 5: every store, every field category, every processor. Rights handling is a query over this map.
1. **Build export.** A per-user export that gathers their data across stores into a readable copy (access) and a structured format like JSON or CSV (portability). One capability, two outputs.
1. **Build deletion with judgment encoded.** Per-user deletion that erases or anonymizes across stores, calls processor deletion APIs where they exist, skips legally retained records while logging the reason, and reports what it did.
1. **Build correction paths.** Profile self-service covers most rectification; an admin path covers the rest.
1. **Wire objection and opt-outs.** Marketing stop that reaches every sending system (Module 3's withdrawal, generalized); CCPA-style "do not sell or share" where applicable.
1. **Stand up the process.** An intake channel (email or form), a request log with dates and deadlines, verification steps, and a simple runbook: verify, execute, respond, record. Deadlines get tracked from day of receipt.

## Directing AI

- "Using this schema and processor list, generate the data map for rights handling: every location where a user's personal data can exist, keyed by user identifier."
- "Build a per-user export: JSON plus a human-readable summary, covering these tables and requesting exports from these processor APIs where available."
- "Build deletion for a user: anonymize orders older than the legal retention period instead of deleting, hard-delete these tables, call these processor deletion endpoints, and output a deletion report of actions taken and records retained with reasons."
- "Draft the rights-request runbook for the client's team: intake, verification steps, execution, response templates, and a request log format with deadline tracking."
- "Review this build and list every system a deletion request would need to touch, including caches, search indexes, analytics, and email tools. Flag any with no deletion path."

## Common Mistakes

- **Building the product, discovering the rights later.** The first real request becomes an archaeology project under a deadline.
- **Deletion that only touches the main table.** The user is gone from `users` and alive in logs, analytics, the email tool, and the search index.
- **Ignoring processors.** Your systems deleted; the vendors kept everything. Their deletion endpoints and processes are part of your capability.
- **Deleting what law requires you to keep.** Erasure has exceptions; encode them deliberately with logged reasons instead of choosing between over-deleting and refusing.
- **No verification, or hostile verification.** Handing data to an impostor is a breach; demanding notarized documents for a newsletter unsubscribe is obstruction. Proportionate is the word.
- **No log, no clock.** Requests handled ad hoc miss deadlines silently and leave no evidence of compliance when asked.

## Real-World Application

A client's subscription platform gets its first erasure request from an EU customer. Because rights were designed in, the process is boring: support verifies the requester controls the account email, opens the runbook, and triggers the deletion capability. Live records anonymize; invoices inside the tax retention window are kept and logged with the reason; the email platform and analytics processor deletion APIs are called; the deletion report is attached to the request log; a plain-language response goes out on day six of thirty, noting that backups expire on the platform's disclosed schedule. Total effort: under an hour. The alternate universe where none of this was built spends three weeks on the same request and still misses the search index.

## Decision Framework

- **New build?** Rights capabilities go in the data model now: export, deletion, correction, opt-outs.
- **Request arrived?** Verify proportionately, log with a deadline, execute from the runbook, respond in plain language, record everything.
- **Deletion versus retention duty?** Retain the specific records law requires, delete or anonymize the rest, document the reasoning; wording for edge cases goes to counsel.
- **Processor in the flow?** Their deletion and export capabilities were a selection criterion; use them, and flag vendors that have none.
- **Suspicious or ambiguous request?** Escalate verification proportionately; route legal edge cases (third parties requesting, disputes) to counsel.
- **Volume growing?** The manual runbook becomes a self-service portal; the DSAR Systems course downstream goes deep on exactly that.

## Tool and Platform Notes

- Major SaaS processors (email platforms, analytics, payment providers) expose deletion and export APIs or documented processes; check for them when selecting vendors, not after the first request.
- Platform backup policies determine what you can honestly say about backup deletion; disclose the schedule rather than promising the impossible.
- Search indexes and caches (and AI embeddings derived from user content) are stores too; include them in the data map.
- A simple request log (spreadsheet or small table: request, date, type, verification, actions, response date) satisfies the record-keeping need for most small clients.

## Key Takeaways

- Rights arrive as requests with deadlines; systems either can answer or cannot, by design.
- The data map (classification plus data flows) is the prerequisite for every right.
- Export serves access and portability; deletion must reach stores, processors, and exceptions with logged reasons.
- Verification is mandatory and proportionate; the process needs an intake, a log, and a clock.
- Design rights in at build time; retrofits happen under deadline pressure.

## What's Next

You can build every capability this course has named. Module 7 assembles them into a repeatable practice: privacy by design as your default posture, and privacy as something clients pay you for.

## Exam Prep Notes

Focus on: the core rights in buildable terms, the deadline reality, the data map as prerequisite, what complete deletion actually touches, retention exceptions and logging, proportionate verification, and the intake-log-runbook process. Scenarios will present requests and half-built systems and ask what is missing or what happens next.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107139927_
