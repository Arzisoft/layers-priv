---
course: "The Foundation"
module: "Layer 13: Availability & Recovery"
lesson: "Layer 13: Availability & Recovery — Study Guide"
type: "course_lesson"
post_id: 102895615
space_id: 23777123
source: "https://the-faction.mn.co/posts/102895615"
updated: "2026-08-21T09:24:35Z"
---

# Layer 13: Availability & Recovery — Study Guide

## Layer 13: Availability & Recovery

Making Sure Your App Stays Up — and Bounces Back When It Doesn't

This is the study guide. Everything for Availability & Recovery is on this page — there's nothing to download.

## What This Study Guide Covers

This study guide covers Layer 13: Availability & Recovery—the final layer of the 13-Layer Tech Stack.

This is about making sure your app is always available for your users, and when something does go catastrophically wrong (and eventually it will), you can bring it back quickly. Think of it as the emergency plan for your entire tech stack.

You're not going to write disaster recovery scripts by hand. You're going to describe your availability requirements to your AI coding tool and let it set up monitoring, backups, and recovery procedures. Your job is to understand what uptime monitoring does (watches your app and alerts you when it goes down), what backup strategies protect you (copies of your data stored safely), and what a recovery plan looks like (step-by-step instructions for getting back online). That's what this certification proves.

This study guide walks you through the concepts, tools, and checkpoints you need to pass the Availability & Recovery certification exam.

## Why It Matters

Everything you've built across the other 12 layers—your frontend, your backend, your database, your authentication, your payments—none of it matters if your app is down. Availability is the foundation that everything else sits on. A feature that doesn't load is worse than a feature that doesn't exist, because it erodes trust every time it fails.

Here's what most vibecoders don't think about until it's too late: your database crashes and you realize you have no backup. Your hosting provider has an outage and your app is offline for eight hours. A bad deployment takes down your entire site and you don't know how to roll back.

These aren't hypothetical scenarios—they happen to real apps every day. This study guide teaches you how to prepare for them so that when the worst happens, you're ready to bounce back in minutes, not days.

## CERTIFICATION GOAL

You understand why availability matters, have basic uptime monitoring and backups set up, and know how to bring your app back online when something goes wrong.

## What You Need to Know

You don't need to build recovery systems from scratch. You need to understand what can go wrong, what protects you, and how to get back online when disaster strikes.

**Uptime monitoring (is your app alive?):** Uptime monitoring is a service that checks your app every minute (or every few seconds) to see if it responds. If your app goes down, you get a notification immediately—via text, email, or Slack. Without monitoring, you find out your app is down when a customer tells you. Services like UptimeRobot, Better Uptime, and Vercel's built-in checks handle this for free.

**Health checks:** A health check is a special URL in your app (usually /health or /api/health) that returns a simple "OK" when everything is working. Your monitoring service hits this URL regularly. If it stops returning "OK," the monitoring service knows something is broken and alerts you. Think of it as a heartbeat monitor for your app.

**Backup basics:** A backup is a copy of your data stored separately from your main database. If your database crashes, gets corrupted, or gets accidentally deleted, you restore from the backup. The two critical questions are: how often are backups created (every hour? every day?) and where are they stored (a different server, a different cloud provider, a different continent)?

**Recovery time (how fast can you bounce back?):** Recovery time is how long it takes to get your app back online after a failure. If your database crashes and you have a daily backup, your worst-case data loss is 24 hours of data. If you have hourly backups, it's one hour. Know your recovery time so you can set realistic expectations with your users.

**The vibecoder availability workflow:** Tell AI to set up uptime monitoring → AI configures a health check endpoint and connects a monitoring service → set up automated database backups → test your backup by restoring from it at least once → document your recovery steps so you know what to do when something breaks → sleep better.

## Your Toolkit

These tools keep watch when you can't and protect your data when things go wrong.

**UptimeRobot or Better Uptime (free tier):** Checks your app every minute and sends you a notification the moment it goes down. Set it up once and forget about it—it does the watching for you.

**Your platform's built-in backups:** Vercel, Railway, Supabase, and other platforms include automated database backups. Check that they're turned on, check how often they run, and verify you know how to restore from one.

**A recovery document:** A simple document (even a Google Doc) that lists exactly what to do when your app goes down: who to contact, how to check logs, how to restore from a backup, how to redeploy. Write it while you're calm so you have it when you're panicking.

## Certification Exam Topics

Every exam question is scenario-based. You'll face real situations and need to identify the right response. Here's what gets tested:

**Monitoring gap:** Your app has been down for three hours and you didn't know until a customer emailed you. What should you have set up to find out immediately?

**Health check purpose:** Your monitoring service says your app is "up" but users say pages won't load. Your health check only checks if the server responds. What's missing from the health check?

**Backup verification:** You set up daily database backups six months ago. Have you ever tested restoring from one? What's the risk if you haven't?

**Recovery time:** Your database crashes and your most recent backup is 23 hours old. How much data have you lost, and what would you change to reduce that loss?

**Deployment rollback:** You deployed a new version and now the app is broken. What's the fastest way to get the previous working version back online?

**Data loss scenario:** You accidentally deleted a critical database table. You have no backups.

What are your options—and how do you prevent this from happening again?

**Monitoring setup:** You want to be notified within two minutes if your app goes down. What do you tell AI to set up?

**Backup storage:** Your database backup is stored on the same server as your database. Why is this a problem and where should backups be stored instead?

## Common Pitfalls

These are the mistakes vibecoders make most often with availability and recovery. They're the kind of mistakes you don't notice until the worst possible moment. Fix them while things are calm.

Not having uptime monitoring. Your app has been down for hours and you're the last person to know. A free monitoring tool would have texted you in sixty seconds.

Having backups but never testing them. A backup you've never restored from is a backup you hope works. Hope is not a recovery strategy. Test your restore process at least once.

Storing backups in the same place as your data. If the server dies, your backup dies with it.

Backups belong on a different server, in a different region, ideally with a different provider.

No rollback plan for deployments. You ship a bad update and your only option is to fix it while the app is broken. A one-click rollback to the previous version gets you back online in seconds.

Waiting for a real outage to test your recovery process. If the first time you follow your runbook is during a real emergency, you'll discover its gaps at the worst possible time. Run drills.

Not communicating with users during outages. Silence makes users think you don't know or don't care. A status page that says "we know and we're working on it" builds trust even during failures.

## Self-Assessment Checklist

Before you take the exam, run through these questions. Every "no" is something to work on.

Do you have uptime monitoring that notifies you within minutes when your app goes down?

Do you have automated database backups running—and do you know how often they run and where they're stored?

Have you ever actually restored from a backup to prove it works?

Do you have a written recovery plan—even a simple one—that lists what to do when your app goes down?

If you deployed a bad update right now, could you roll back to the previous version in under five minutes?

Do you know how much data you'd lose if your database crashed right now (based on your backup frequency)?

If your app went down during business hours, do you have a way to communicate with affected users (a status page, email, or social media plan)?

## AI Audit Prompt Template

Copy this prompt into your AI coding tool to get a quick health check on your availability and recovery setup. It checks the same things the certification exam covers.

> Review my app's availability and recovery setup and check the following. For each one, tell me pass or fail with a specific example:
>
>
>
> Uptime monitoring: Is a monitoring service actively checking my app and alerting me when it goes down, or could my app be offline right now without anyone knowing?
>
>
>
> Health checks: Does my app have a health check endpoint that verifies the app and its dependencies (database, external APIs) are actually working—not just that the server responds?
>
>
>
> Database backups: Are automated backups running on a regular schedule, stored in a different location from my primary database?
>
>
>
> Backup testing: Has a backup been successfully restored at least once to verify the backup process actually works?
>
>
>
> Deployment rollback: Can I quickly roll back to the previous version of my app if a deployment breaks something?
>
>
>
> Recovery documentation: Is there a written recovery plan or runbook that lists step-by-step instructions for common failure scenarios?
>
>
>
> Give me an overall score out of 6 and list the top 3 things to fix first.

## What’s Next

Congratulations—you've reached the final layer of the 13-Layer Tech Stack. If you've worked through all 13 layers, you now have a complete understanding of everything that makes a production app work: from the frontend your users see to the recovery plan that keeps you online when things go wrong. That's a real accomplishment.

The best way to prepare for this exam: audit your own app. Is uptime monitoring set up? Are backups running? Have you ever restored from one? Do you have a recovery plan written down? Every gap you find and fix is exactly what the exam tests. And once you pass, you'll have proven you can not only build with AI—you can build things that stay up and bounce back.

## Certification Pathway

Associate Builder: Pass all 13 layers at Tier 1 Certified Builder: Pass all 13 layers at Tier 1 + Tier 2 MADE Certified: Pass all 39 tier exams + capstone project Each exam requires 80% to pass. You can retake after a 24-hour cooldown. No rush—take the time to build something real first.

———

Ready? Take the [Availability & Recovery Exam →](https://the-faction.mn.co/posts/the-foundation-layer-13-availability-recovery-exam)

---

## Discussion

**Awie Hoh** · 2026-07-01

> 13. AVAILABILITY & RECOVERY
> 
> PURPOSE
> 
> Availability keeps the app usable. Recovery brings it back safely after failure.
> 
> PRINCIPLE
> 
> The app must fail safely, alert quickly, recover predictably, and protect data during outages.
> 
> WHAT THIS SECTION OWNS
> 
> What happens after something breaks: backups and restore, rollback (the first move when core flows break, otherwise a fallback to a forward fix), the incident process, failing safe, and surviving a dependency outage. Failure capture and alerting are #12; health-check depth and graceful shutdown under load are #11; the deploy rollback mechanism is #5/#7 — all referenced here, used in anger.
> 
> RECOVERY TARGETS (define these first, or recovery can't be judged)
> 
> Two numbers drive every choice below:
> 
> - How long can the app be down? (recovery time)
> 
> - How much recent data can it afford to lose? (recovery point)
> 
> If the newest backup is 23 hours old, up to 23 hours of data may be lost. State both targets, then make backups, restore, and rollback actually meet them — more frequent backups or point-in-time recovery shrink data loss; a tested fast restore shrinks downtime.
> 
> EXTERNAL MONITORING
> 
> Don't wait for users to report outages — and don't rely only on monitoring that runs inside your own app, since a dead server can't report that it's dead. Use external uptime monitoring that checks the live app every 1–2 minutes from outside and alerts a responsible human within minutes via email, SMS, Slack, or an incident tool. (Error capture and alert fatigue are handled in #12.)
> 
> HEALTH CHECKS
> 
> A health check must prove more than "the server responds": critical pages load, the API responds, the database connects, auth works, storage is reachable, core flows aren't broken. A shallow check can say "up" while users can't use the app. Health checks must not expose secrets, private data, logs, or internals. (Depth shared with #11.)
> 
> CRITICAL FLOWS TO WATCH
> 
> Login, signup, dashboard load, checkout/payments, database access, storage access, API health, background jobs, webhooks, deployments, third-party services.
> 
> BACKUPS
> 
> Automated backups are required, covering database data and schema, storage metadata, migrations, RLS and storage policies, and critical configuration. Store them away from the live system — a separate region or provider — because a backup on the same server or region can fail with the thing it was meant to save.
> 
> RESTORE IS THE REAL TEST
> 
> A backup is not proven until it has been restored successfully. Test restores before an emergency. Backups that have run for six months but were never restored tell you nothing about whether recovery works.
> 
> ROLLBACK DECISION
> 
> When login, payments, private data, database integrity, or core flows are broken, the fastest safe move is to restore the previous working deployment — roll back first, get users safe, then fix the bad release. (Rollback mechanism in #5/#7.)
> 
> FAIL SAFE (Principle 6)
> 
> When the system is unsure, fail closed. Do not expose private data, skip permission checks, process payments twice, corrupt records, silently lose user work, or show false success. A broken feature shows a clear error, never a blank screen (#1).
> 
> DEPENDENCY OUTAGE PLAN
> 
> Know what the app depends on: hosting, database, storage, auth, payment, email, AI, DNS, and external APIs. For each, decide its failure behavior so one vendor's outage doesn't become yours: degrade gracefully where safe (email provider down → queue and retry, don't crash signup), and fail closed where safety demands it (payment result uncertain → never assume success). Every external call times out (#6); permanent failures dead-letter, not vanish (#6).
> 
> INCIDENT PROCESS
> 
> A simple flow: detect, stop the damage, restore service, check data integrity, communicate with affected users, document the cause, prevent recurrence.
> 
> USER COMMUNICATION
> 
> In a serious outage, silence damages trust. Have a status page, email, or support message ready that tells users what's broken, what's being done, and when the next update comes.
> 
> RUNBOOKS
> 
> Keep short, tested recovery steps for common failures: bad deployment / rollback, database restore, storage restore, failed migration, deleted data, secret leak (#5), payment outage, auth outage, high traffic (#11), provider outage. For deleted data with no backup, recovery is limited — check database logs, provider recovery tools, replicas, cached exports, or support; if none exist, the data may be gone for good. Prevent it with automated backups, tested restores, migration review, restricted production access, and deletion safeguards (#3).
> 
> AI WORKFLOW
> 
> Specify to AI: critical flows, external uptime monitoring, alert target, health-check depth, recovery-time and recovery-point targets, backup schedule and off-site location, restore-test requirement, rollback decision rule, dependency failure behavior, user-communication plan, and recovery test cases. Security and RLS must remain enforced after recovery.
> 
> SHIP GATE — do not ship unless all are true
> 
> ☐ Recovery-time and recovery-point targets stated, and the plan meets them
> 
> ☐ External uptime monitoring alerts a human within minutes
> 
> ☐ Health checks test real app function, not just "server responds"
> 
> ☐ Backups automated, complete, and stored off-site
> 
> ☐ A restore has actually been performed and verified
> 
> ☐ Rollback is fast; the rollback-first rule is clear
> 
> ☐ System fails closed when unsure; no blank screens, no false success
> 
> ☐ Each dependency has a defined failure behavior
> 
> ☐ Written incident process and tested runbooks exist
> 
> ☐ Security & RLS still enforced after any recovery

**Agbara Okenze** · 2026-08-18

> Am I a cheat? I feed the whole course to my Hermes-Agent and told it to create a globally reusable skills from the lessions knowladge and use the full skill set in future developments. I am lazy

  ↳ **Matt Murphy** · 2026-08-18

  > Not the first and certainly not the last.

  ↳ **Samy Faisal** · 2026-08-21

  > [Matt Murphy](https://the-faction.mn.co/members/39706849) You are extraordinary guy, what a very high value we are providing man!!!, god plies you.


---
_Source: https://the-faction.mn.co/posts/102895615_
