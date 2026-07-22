# Layer 13 of 13 — Availability & Recovery
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Making Sure Your App Stays Up — and Bounces Back When It Doesn't*

---

## What It Covers

Uptime monitoring, health checks, database backups, recovery time, deployment rollbacks, and the written recovery plan.

**Core goal:** You understand why availability matters, have basic uptime monitoring and backups set up, and know how to bring your app back online when something goes wrong.

This is the capstone layer — the emergency plan for your entire tech stack.

---

## Key Concepts

**Uptime monitoring** — A service that checks your app every minute. If it goes down, you're notified immediately via text/email/Slack. Without it, you find out from a customer complaint. Services: UptimeRobot, Better Uptime — both have free tiers. Set up before launch.

**Health checks** — A URL in your app (`/health` or `/api/health`) that returns "OK" when everything works. The monitoring service pings this. If it stops responding: alert fires. A health check that only pings the server (not the database, not external APIs) gives you false confidence.

**Backup basics** — A copy of your data stored separately from your main database. Two critical questions:
1. How often? (hourly vs daily — determines max data loss on failure)
2. Where? (must be on a different server, different region, ideally different cloud provider)

**Recovery time** — How long to get back online after a failure. If your most recent backup is 23 hours old and your database crashes: worst case, you lose 23 hours of data. Know your backup frequency; set expectations with users accordingly.

**Deployment rollback** — If a new deployment breaks things, you need to go back to the previous version in under 5 minutes. Vercel/Netlify: one-click rollback. EC2: keep previous release folder with a symlink swap pattern.

**The recovery document** — A written document (even a simple one) listing exactly what to do when your app goes down: who to contact, how to check logs, how to restore from backup, how to redeploy. Write it while calm. You'll need it when you're panicking.

**Test your backups** — A backup you've never restored from is one you hope works. Hope is not a recovery strategy. Restore from a backup at least once. Find the gaps while you're calm.

---

## Toolkit

- **UptimeRobot / Better Uptime (free)** — uptime monitoring, checks every minute
- **Platform built-in backups** — Vercel, Railway, Supabase, RDS all include automated backups; verify they're on
- **Rollback procedures** — platform one-click rollback or Git revert + redeploy
- **Recovery document** — Google Doc, Notion, or a RUNBOOK.md in your repo

---

## Common Pitfalls

- No uptime monitoring — app down for hours before anyone knows
- Backups set up but never tested — the first restore is during a live crisis
- Backups on the same server as the database — if the server dies, both go together
- No rollback plan for bad deployments
- Never running a recovery drill
- No user communication plan during outages (silence destroys trust)

---

## Tier 1 Self-Assessment Checklist

- [ ] Is uptime monitoring active and notifying you within minutes of downtime?
- [ ] Are automated database backups running on a known schedule?
- [ ] Do you know where backups are stored (and is it separate from the database server)?
- [ ] Have you ever actually restored from a backup to prove it works?
- [ ] Is there a written recovery plan you could follow at 2am?
- [ ] Can you roll back a bad deployment in under 5 minutes?
- [ ] Do you know how much data you'd lose if the database crashed right now?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's availability and recovery setup. Pass or fail with a specific example:
1. Uptime monitoring: Is a monitoring service actively checking the app and alerting on downtime?
2. Health checks: Does the app have a health endpoint that checks DB + external dependencies (not just server)?
3. Database backups: Are automated backups running on schedule, stored in a separate location?
4. Backup testing: Has a backup been successfully restored at least once?
5. Deployment rollback: Can the previous version be restored in under 5 minutes?
6. Recovery documentation: Is there a written runbook for common failure scenarios?

Give me a score out of 6 and the top 3 things to fix first.
```

---

## Certification Pathway (all 13 layers)

| Certification | Requirement |
|---|---|
| **Associate Builder** | Pass all 13 layers at Tier 1 |
| **Certified Builder** | Pass all 13 layers at Tier 1 + Tier 2 |
| **MADE Certified** | Pass all 39 tier exams + capstone project |

Each exam: 80% to pass. 24-hour cooldown before retake.
