---
course: "The Mastery"
module: "Module 7: Ship: Production Database"
lesson: "Module 7: Ship: Production Database — Exam"
type: "course_quiz"
post_id: 105098124
space_id: 24191170
source: "https://the-faction.mn.co/posts/105098124"
updated: "2026-08-10T20:44:09Z"
---

# Module 7: Ship: Production Database — Exam

> Exam for **Module 7: Ship: Production Database** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What separates a production database from the same database in development?

- **A.** The engine version, since production platforms run hardened builds unavailable to developers
- **B.** The schema, since production structures are simplified for speed over flexibility
- **C.** Real users and real consequences: mistakes now cost trust, money, and possibly the business  ✅
- **D.** The pricing tier, since production is defined by the paid plan that hosts the system

> **Answer:** C

### Q2. Before launch, what must be true about how the app connects to the production database?

- **A.** It connects as the admin account, since launch week demands maximum permissions
- **B.** It uses a least-privilege account with credentials stored in protected configuration  ✅
- **C.** It connects through the founder's personal account, keeping accountability fully personal
- **D.** It holds one shared password with all environments, simplifying the launch runbook

> **Answer:** B

### Q3. What belongs in the pre-launch database checklist?

- **A.** A press kit, a launch post thread, and the pricing page, all verified against the live schema
- **B.** The AI agent's self-assessment, scoring its own build above the launch threshold
- **C.** A competitor teardown, confirming your schema has more tables than theirs does
- **D.** Backups verified by restore, monitoring live, access reviewed, and migrations repeatable  ✅

> **Answer:** D

### Q4. Launch day traffic is ten times the estimate. What preparation makes this survivable?

- **A.** Known headroom and a tested plan for the next step up, decided before it was urgent  ✅
- **B.** A refund policy, since compensating early users is cheaper than any capacity planning
- **C.** A waitlist page ready to deploy, converting the overload into marketing scarcity
- **D.** The AI agent on standby to rewrite slow queries live as they appear in the logs

> **Answer:** A

### Q5. Who should be able to run queries directly against production after launch?

- **A.** Every builder on the project, since launched apps need the fastest possible debugging
- **B.** Nobody, with all access permanently sealed the moment the first real user signs up
- **C.** A minimal, named set of people, with access logged and reviewed as roles change  ✅
- **D.** The AI agent alone, since automated access removes human error from production

> **Answer:** C

### Q6. What does database monitoring need to answer at any moment after launch?

- **A.** Which competitor features launched today, correlated against your own usage curves
- **B.** Whether users enjoy the app, inferred from the emotional tone of their stored content
- **C.** The exact revenue attributed per query, so each table's profitability can be ranked monthly
- **D.** Is it up, is it fast, is it filling, and is anything behaving unlike it did yesterday  ✅

> **Answer:** D

### Q7. The app went live and the AI still has standing write access to the production schema. What is the correct posture?

- **A.** Keep it, since the agent that built the schema is best placed to modify it freely
- **B.** Remove standing access; structural changes now go through the migration pipeline with review  ✅
- **C.** Downgrade it to nights and weekends, when structural mistakes affect fewer users
- **D.** Transfer the access to a second agent, so no single model holds the schema control

> **Answer:** B

### Q8. What makes an incident runbook trustworthy?

- **A.** It's been walked through in a drill, so the steps are known to work under pressure  ✅
- **B.** Its length, since thorough runbooks signal the seriousness of the whole operation to everyone
- **C.** Its author, since runbooks written by founders carry the authority that is needed
- **D.** Its storage location, since laminated physical copies survive every outage type

> **Answer:** A

### Q9. Two weeks post-launch, disk usage is growing four times faster than projected. What is the first move?

- **A.** Purchase a year of extra capacity now, locking in pricing before the growth compounds further
- **B.** Delete the oldest ten percent of rows, the standard correction for early overgrowth
- **C.** Celebrate, since storage growth is the most direct evidence of product-market fit
- **D.** Find out what is growing and why, since surprise growth often means a bug, not success  ✅

> **Answer:** D

### Q10. What is the correct relationship between the production schema and the migration history?

- **A.** Production's structure is exactly what the applied migrations produce, nothing more or less  ✅
- **B.** Production may drift ahead of migrations, as long as the differences are documented
- **C.** Migrations describe intent while production reflects reality, and they need not match
- **D.** The schema leads and migrations follow, written after changes to record what happened

> **Answer:** A

### Q11. A senior builder asks to \"quickly fix\" a production row by hand. What does the disciplined process require?

- **A.** Refusing all data fixes forever, since production rows are immutable once written
- **B.** A logged, reviewed change through proper channels, however small the edit appears  ✅
- **C.** Doing it at night with a screenshot taken before and after as informal documentation
- **D.** Having the AI make the same edit instead, since agent changes are inherently logged

> **Answer:** B

### Q12. What should happen to the development and staging databases at launch?

- **A.** Both are deleted, since parallel environments confuse the monitoring systems after go-live
- **B.** Both are promoted to replicas, converting test capacity into production resilience
- **C.** They continue as the places where every future change proves itself before production  ✅
- **D.** They're merged into production, consolidating three bills into one at launch time

> **Answer:** C

### Q13. What is the production data's honest relationship to the business now?

- **A.** It is the business: losing it or leaking it is an existential event, and it must be treated so  ✅
- **B.** It is a byproduct: the code is the asset, and the data can always be regathered later
- **C.** It is a liability only: the correct strategy is storing as little as legally possible
- **D.** It is marketing material: its primary value is the growth metrics that it generates

> **Answer:** A

### Q14. An alert fires at 2 AM: connections saturated. What determines whether this is a crisis?

- **A.** Whether the founder is awake, since incident severity scales with leadership response
- **B.** The alert's color in the dashboard, since that encodes the vendor's severity assessment
- **C.** Whether it's a weekday, since weekend saturation resolves itself by Monday morning
- **D.** Preparation: whether a runbook, an on-call path, and headroom decisions already exist  ✅

> **Answer:** D

### Q15. How should secrets like the production database password be rotated?

- **A.** Never, since rotation is the leading cause of self-inflicted production outages
- **B.** Only after breaches, since precautionary rotation signals distrust of the team
- **C.** On a schedule and after departures or incidents, through a process the app tolerates  ✅
- **D.** Daily by an autonomous agent, with no human ever knowing the current live value at all

> **Answer:** C

### Q16. What proves the launch checklist item \"backups working\" was actually met?

- **A.** A restore performed into a separate environment with the app verified running against it  ✅
- **B.** The backup job's green status icon, checked on the morning of the launch itself
- **C.** The vendor's marketing page stating that all plans include automatic daily backups
- **D.** The presence of backup files in storage, confirmed by listing the storage bucket's contents

> **Answer:** A

### Q17. Post-launch, who decides whether a schema change is safe to ship?

- **A.** The AI agent that wrote it, since authorship carries the deepest context available
- **B.** The process: staging test, migration review, and rollback plan, not one person's confidence  ✅
- **C.** The loudest customer, since urgency from users overrides internal process by design
- **D.** The calendar, since changes shipped early in the week are safe by their definition

> **Answer:** B

### Q18. What is the operational meaning of \"the database is boring now\"?

- **A.** Growth has stalled, and the infrastructure budget should shift entirely to marketing
- **B.** The schema is frozen, and the product has stopped evolving at the data layer
- **C.** Monitoring has been turned down, since mature systems no longer need observation
- **D.** Predictable, monitored, backed up, and changed only through process: the goal state  ✅

> **Answer:** D

### Q19. A feature launch requires a new table and a backfill of two million rows. When does this work run?

- **A.** During the launch livestream, since visible engineering builds customer confidence
- **B.** Immediately when ready, since delaying any finished work is pure waste in every process
- **C.** Planned and batched at low traffic, tested on staging first, with progress observable  ✅
- **D.** Across one month of tiny nightly steps, since slow change is always the safest change

> **Answer:** C

### Q20. What turns a database incident into a company crisis?

- **A.** Its duration alone; any outage under one hour is operationally invisible to users
- **B.** Silence and improvisation: no communication, no runbook, and decisions made in panic  ✅
- **C.** The involvement of executives, which converts technical events into purely political ones
- **D.** Filing the postmortem late, since documentation timing defines incident severity

> **Answer:** B

### Q21. What belongs in a database postmortem after a production incident?

- **A.** What happened, why, how it was caught and fixed, and what change prevents a repeat  ✅
- **B.** The name of the person responsible, since accountability is the point of the document
- **C.** Proof the incident was unforeseeable, protecting the team from customer claims
- **D.** A cost comparison with competitors' outages, establishing the industry context

> **Answer:** A

### Q22. Six months in, what keeps the production database healthy rather than merely alive?

- **A.** Quarterly engine reinstalls, clearing the accumulated state that degrades systems
- **B.** Growth in table count, since expanding schemas indicate an actively maintained system
- **C.** Routine care: review slow queries, prune stale indexes, test restores, audit access  ✅
- **D.** Leaving it untouched, since every intervention is a new opportunity for failure

> **Answer:** C

### Q23. What is the right role for AI agents in production database operations long-term?

- **A.** Full ownership, since mature agents outperform humans across every operations task
- **B.** Powerful hands within guardrails: executing reviewed changes, never improvising on live data  ✅
- **C.** None, since production is precisely the environment where automation is inappropriate
- **D.** Observation only, reading dashboards and summarizing them for the humans who act

> **Answer:** B

### Q24. The business wants a risky data operation done today. What is the professional response pattern?

- **A.** Refuse until next quarter, since risk and urgency must never occupy the same week
- **B.** Comply immediately, since business urgency is the context that defines engineering
- **C.** Delegate the risk decision to the AI, since agents estimate the failure odds without any bias
- **D.** Name the risks, the safeguards, and the recovery path out loud, then decide it together  ✅

> **Answer:** D

### Q25. Which principle should govern how you ship and run a production database?

- **A.** Production is a promise: protect the data, rehearse the failures, and change only through process  ✅
- **B.** Production is a milestone: the discipline that got you to launch can relax once you arrive
- **C.** Production is the vendor's problem: managed platforms exist so builders can look away
- **D.** Production is a lab: real users are the most honest test environment you will ever get

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105098124_
