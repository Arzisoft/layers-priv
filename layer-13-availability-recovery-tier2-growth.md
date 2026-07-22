# Layer 13 of 13 — Availability & Recovery
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Making sure your app stays up and bounces back when it doesn't. At Tier 2, your app has paying
users who depend on it — downtime costs real money and trust. The challenge shifts from
knowing when your app is down to making it recover automatically, and proving your recovery
process actually works.

**Core goal:** You can implement automated failover, maintain tested runbooks, run recovery
drills, and design systems that recover from common failures without manual intervention.

---

## Key Concepts

**Automated failover** — A backup system automatically takes over when the primary system
fails. If your main database crashes, a standby database takes over within seconds and users
never notice. Most managed database services (Supabase, PlanetScale, AWS RDS) offer failover —
you just need to turn it on.

**Runbooks (your emergency playbook)** — A step-by-step guide for handling specific incidents.
"Database is down" has a runbook. "Deployment broke the app" has a runbook. "Third-party API is
failing" has a runbook. Each one lists exactly what to do, in order, so you're not making
decisions under stress. AI can help you write runbooks for every failure scenario you can
imagine.

**Recovery drills (testing your emergency plan)** — Intentionally simulating a failure and
practicing recovering from it: restore from a backup, trigger a failover, follow your runbook
step by step. If your recovery process has gaps, you want to find them during a drill, not
during a real outage at midnight.

**Redundancy (no single point of failure)** — A single point of failure is any one thing that,
if it breaks, takes down your entire app — one server, one database, one DNS provider.
Redundancy means having backups for every critical component so no single failure brings
everything down.

**Status pages (keeping users informed)** — When your app goes down, users need to know you're
aware and working on it. A status page (Statuspage.io, Instatus) shows your app's current
health publicly, so users check the status page instead of flooding your inbox.

---

## Toolkit (adds to Tier 1)

- **Managed database with failover (Supabase, PlanetScale, AWS RDS)** — automatically switches to a standby copy when the primary fails, no manual intervention required
- **Statuspage.io or Instatus** — public status pages that show app health and auto-update when monitoring detects an outage
- **Runbook templates** — ask AI to generate runbooks for common failure scenarios: database down, deployment failure, third-party service outage, DNS issues; review and keep them where the team can find them quickly
- **Backup testing schedule** — a recurring calendar reminder (monthly or quarterly) to actually restore from a backup and verify it works; an untested backup is a backup you hope works, not one you know works

---

## Certification Exam Topics

- **Failover verification** — You set up database failover six months ago. How do you know it will actually work when you need it? What should you do to find out?
- **Runbook coverage** — Your app depends on five critical services: database, authentication, payment processor, email service, and file storage. How many runbooks do you need and what should each one cover?
- **Recovery drill** — Walk through how you would simulate a database failure and test your recovery process without affecting real users.
- **Single point of failure** — Your app runs on one server with one database and uses one DNS provider. Identify the single points of failure and explain what redundancy you'd add for each.
- **Status page communication** — Your app has been down for 20 minutes. Users are tweeting about it. What should your status page say and how often should you update it?
- **Backup strategy** — Your app generates 10GB of new data per day. Design a backup strategy that balances data protection, storage costs, and recovery speed.
- **Automated recovery** — Your web server crashes at 3 AM. Without automated recovery, what happens? With it, what should happen, step by step?
- **Dependency failure** — A third-party payment API goes down. Your app can't process payments. What should your app do for users during the outage, and what does your runbook say?

---

## Common Pitfalls

- Not having uptime monitoring — the app is down for hours and you're the last to know; a free monitoring tool would have texted you in sixty seconds
- Having backups but never testing them — a backup you've never restored from is a backup you hope works, and hope is not a recovery strategy
- Storing backups in the same place as your data — if the server dies, the backup dies with it; backups belong on a different server, in a different region, ideally with a different provider
- No rollback plan for deployments — you ship a bad update and your only option is to fix it while the app is broken, instead of a one-click rollback
- Waiting for a real outage to test your recovery process — if the first time you follow your runbook is a real emergency, you discover its gaps at the worst possible time
- Not communicating with users during outages — silence makes users think you don't know or don't care

---

## Tier 2 Self-Assessment Checklist

- [ ] Do you have uptime monitoring that notifies you within minutes when your app goes down?
- [ ] Do you have automated database backups running, and do you know how often they run and where they're stored?
- [ ] Have you ever actually restored from a backup to prove it works?
- [ ] Do you have a written recovery plan, even a simple one, that lists what to do when your app goes down?
- [ ] If you deployed a bad update right now, could you roll back to the previous version in under five minutes?
- [ ] Do you know how much data you'd lose if your database crashed right now (based on your backup frequency)?
- [ ] If your app went down during business hours, do you have a way to communicate with affected users (a status page, email, or social media plan)?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's availability and recovery setup and check the following. For
each one, tell me pass or fail with a specific example:
Uptime monitoring: Is a monitoring service actively checking my app and
alerting me when it goes down, or could my app be offline right now without
anyone knowing?
Health checks: Does my app have a health check endpoint that verifies the app
and its dependencies (database, external APIs) are actually working, not just
that the server responds?
Database backups: Are automated backups running on a regular schedule, stored
in a different location from my primary database?
Backup testing: Has a backup been successfully restored at least once to
verify the backup process actually works?
Deployment rollback: Can I quickly roll back to the previous version of my
app if a deployment breaks something?
Recovery documentation: Is there a written recovery plan or runbook that
lists step-by-step instructions for common failure scenarios?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## What's Next

This is the final layer of the 13-Layer Tech Stack. Working through all 13 layers means a
complete understanding of everything that makes a production app work, from the frontend users
see to the recovery plan that keeps the app online when things go wrong.

The best way to prepare for this exam: audit your own app. Is uptime monitoring set up? Are
backups running? Have you ever restored from one? Do you have a recovery plan written down?
Every gap found and fixed is exactly what the exam tests.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
