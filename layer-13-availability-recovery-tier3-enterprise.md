# Layer 13 of 13 — Availability & Recovery
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Making sure the app stays up, and bounces back when it doesn't. At Tier 3, the platform has
contractual uptime commitments. Downtime isn't just inconvenient, it triggers SLA penalties,
damages customer trust, and can cost significant revenue per minute. The job is designing the
system so that failure of any single component doesn't affect users, and when a major incident
happens, the response is coordinated and fast.

**Core goal:** You can architect multi-region redundancy, define and meet SLA commitments, run
chaos engineering experiments, and manage formal incident response processes for enterprise
platforms.

---

## Key Concepts

**SLAs and uptime commitments** — An SLA (Service Level Agreement) is a contractual promise
about how available the service will be. "99.9% uptime" means about 8.7 hours of downtime allowed
per year; "99.99%" allows only 52 minutes per year. SLAs have financial consequences: miss the
target and you owe credits or refunds. Every architectural decision at Tier 3 is about meeting the SLA.

**Multi-region redundancy** — Running the app in multiple geographic regions (US East, US West,
Europe) so that if an entire region goes offline, traffic automatically shifts to another region.
This is how major platforms survive data center outages. It's complex and expensive, but it's the
only way to hit very high uptime targets.

**Chaos engineering (breaking things on purpose)** — Intentionally breaking parts of the system
in production to verify that failover and recovery actually work. Netflix famously runs "Chaos
Monkey," which randomly kills servers to prove the system recovers. At Tier 3 you don't just hope
recovery works, you prove it by regularly breaking things.

**Incident response process** — A formal process defines roles (who leads the investigation, who
communicates with customers), severity levels (how bad is it), escalation paths (who gets called at
what severity), and post-incident reviews (what happened, why, and how to prevent it). This turns
emergencies from chaos into a coordinated procedure.

**Post-incident reviews (learning from failures)** — After every significant outage, run a
blameless review: what happened, what was the impact, what worked well in the response, what
didn't, and what changes prevent a recurrence. Called "blameless" because the goal is learning,
not finger-pointing. This is how enterprise teams turn failures into improvements.

---

## Toolkit (adds to Tier 2)

- **Multi-region cloud deployment (AWS, GCP, Azure)** — run the app across multiple geographic regions with automatic failover between them, so a regional outage doesn't take down the platform
- **Chaos engineering tools (Gremlin, Litmus)** — intentionally break parts of the system in controlled experiments to verify failover and recovery work under real conditions
- **PagerDuty with incident workflows** — enterprise incident management that assigns roles, coordinates response, manages escalations, and runs post-incident reviews, all in one system
- **Terraform or Pulumi for disaster recovery** — infrastructure-as-code tools that rebuild the entire platform from a configuration file; if everything fails, you can recreate the whole system from scratch

---

## Certification Exam Topics

- **SLA calculation** — Your platform promises 99.95% monthly uptime. You've had 15 minutes of downtime so far this month. How much downtime budget do you have left?
- **Multi-region failover** — Your primary region (US East) goes offline due to a cloud provider outage. Walk through what should happen automatically and what the user experience should be.
- **Chaos engineering design** — Design an experiment to test whether your database failover works. What do you break, how do you measure success, and what safeguards do you put in place?
- **Incident response roles** — A major outage occurs during business hours. Define the key roles in the incident response team and what each is responsible for during the first 30 minutes.
- **Post-incident review** — An outage lasted 45 minutes and affected 10,000 users. What should the review cover and what artifacts should it produce?
- **Disaster recovery testing** — Your DR plan says you can rebuild the platform in under 4 hours. How do you prove this without causing a real outage?
- **SLA breach prevention** — Halfway through the month you've used 80% of your downtime budget. What operational changes should you make for the rest of the month?
- **Recovery point objective** — Your RPO (maximum acceptable data loss) is 15 minutes. What backup frequency and replication strategy meets this requirement?

---

## Common Pitfalls

- Not having uptime monitoring — the app has been down for hours and you're the last to know; a free monitoring tool would have texted you in sixty seconds
- Having backups but never testing them — a backup you've never restored from is a backup you hope works, and hope is not a recovery strategy; test the restore at least once
- Storing backups in the same place as the data — if the server dies, the backup dies with it; backups belong on a different server, in a different region, ideally a different provider
- No rollback plan for deployments — you ship a bad update and your only option is to fix it while the app is broken; a one-click rollback gets you back online in seconds
- Waiting for a real outage to test recovery — if the first time you follow the runbook is during a real emergency, you discover its gaps at the worst possible time; run drills
- Not communicating with users during outages — silence makes users think you don't know or don't care; a status page that says "we know and we're working on it" builds trust even during failures

---

## Tier 3 Self-Assessment Checklist

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
Review my app's availability and recovery setup and check the following.
For each one, tell me pass or fail with a specific example:
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
Deployment rollback: Can I quickly roll back to the previous version of my app
if a deployment breaks something?
Recovery documentation: Is there a written recovery plan or runbook that lists
step-by-step instructions for common failure scenarios?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## What's Next

This is the final layer of the 13-Layer Tech Stack. Working through all 13 layers means a
complete understanding of everything that makes a production app work: from the frontend users
see to the recovery plan that keeps you online when things go wrong.

The best way to prepare for the exam: audit your own app. Is uptime monitoring set up? Are
backups running? Have you ever restored from one? Do you have a recovery plan written down? Every
gap you find and fix is exactly what the exam tests.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
