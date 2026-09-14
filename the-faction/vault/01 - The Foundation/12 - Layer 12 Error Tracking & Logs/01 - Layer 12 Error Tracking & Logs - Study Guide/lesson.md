---
course: "The Foundation"
module: "Layer 12: Error Tracking & Logs"
lesson: "Layer 12: Error Tracking & Logs — Study Guide"
type: "course_lesson"
post_id: 102895502
space_id: 23777123
source: "https://the-faction.mn.co/posts/102895502"
updated: "2026-08-10T17:50:13Z"
---

# Layer 12: Error Tracking & Logs — Study Guide

## Layer 12: Error Tracking & Logs

Finding Out What Broke Before Your Users Tell You

This is the study guide. Everything for Error Tracking & Logs is on this page — there's nothing to download.

## What This Study Guide Covers

This study guide covers Layer 12: Error Tracking & Logs—how you find out when your app breaks before your customers do. Every app breaks. That's not a failure—it's just reality. The difference between a professional operation and an amateur one is whether you know about it in thirty seconds or find out three days later when a customer sends an angry email.

You're not going to write error-handling code by hand. You're going to describe your monitoring needs to your AI coding tool and let it wire up error tracking services that watch your app 24/7.

Your job is to understand what error tracking does (catches crashes and problems automatically), what logs are (a running diary of everything your app does), and how alerting works (sends you a notification the moment something goes wrong). That's what this certification proves.

This study guide walks you through the concepts, tools, and checkpoints you need to pass the Error Tracking & Logs certification exam.

## Why It Matters

Right now, if your app crashes at 2 AM, you won't know until someone tells you—maybe a user, maybe a bad review, maybe a client who quietly stops paying. That's not a sustainable way to run a product. Error tracking is your early warning system. It watches your app every second and sends you a message the moment something goes wrong, along with exactly what happened and where.

AI coding tools build features. They don't build monitoring unless you ask. Your AI will happily ship an app with zero error tracking, zero logging, and zero alerting. Then when something breaks—and it will—you'll be debugging blind, guessing where the problem is instead of knowing. This study guide teaches you what to ask AI to set up so that when things break, you're the first to know, not the last.

## CERTIFICATION GOAL

You understand why error tracking matters, can describe what you need to AI, and can read error reports well enough to explain what went wrong—even if you can't fix the code yourself.

## What You Need to Know

You don't need to debug code. You need to understand what error tracking tools tell you so you can describe the problem clearly—to AI, to a developer, or in a support ticket.

**What an error is:** An error is when your app tries to do something and fails. Maybe it tried to load a user's profile from the database and the database was down. Maybe a button triggers code that has a typo. Maybe the app tries to use a feature the browser doesn't support. Errors are normal—every app has them. The question is whether you know about them.

**Error tracking services:** Tools like Sentry and LogRocket watch your app in real time. When an error happens, they capture it automatically—what went wrong, which page the user was on, what browser they were using, and a stack trace (a breadcrumb trail showing exactly where in the code the error happened). You get a notification instead of silence.

**What logs are:** Logs are your app's diary. Every time something happens—a user logs in, a payment processes, a page loads—your app can write a log entry. When something breaks, logs tell you the story of what happened right before the crash. Without logs, debugging is guesswork.

**Error boundaries (catching crashes gracefully):** An error boundary is a safety net built into your app. Instead of the whole app crashing and showing a blank white screen, an error boundary catches the crash and shows a friendly message like "Something went wrong. Please try again." The user gets a bad experience on one part of the page instead of losing the entire app.

**The vibecoder monitoring workflow:** Tell AI to add error tracking → AI integrates Sentry or a similar service → errors get captured automatically → you receive notifications when something breaks → you read the error report → you describe the problem to AI and ask it to fix it → verify the fix → ship.

## Your Toolkit

These tools do the watching for you. Your job is making sure they're connected and you know where to look when they alert you.

**Sentry (free tier available):** The most popular error tracking tool. It captures errors automatically, groups them by type, and shows you exactly what happened. Tell AI to integrate Sentry into your app—it takes one prompt.

**LogRocket or FullStory:** Session replay tools that record what a user sees and does. When a user reports a bug, you can watch their session like a video and see exactly what they experienced.

**Your platform's built-in logs:** Vercel, Railway, Fly.io, and other platforms show you server logs automatically. This is your first place to look when something goes wrong.

## Certification Exam Topics

Every exam question is scenario-based. You'll see a real-world situation and need to identify what went wrong or what to set up. Here's what gets tested:

**Error awareness:** Your app has been live for a month and you've never seen an error report.

Does that mean your app has no bugs, or does it mean you have no error tracking?

**Error report reading:** Sentry shows you an error that says "TypeError: Cannot read properties of undefined." You don't need to fix the code—but can you explain what kind of problem this describes?

**User experience during errors:** A user sees a completely blank white screen after clicking a button. What's missing that would have shown them a friendly error message instead?

**Log usefulness:** A user says "the app crashed when I tried to check out." You have no logs.

What information are you missing that logs would have given you?

**Alert setup:** You want to know within five minutes when your app crashes. What do you need to set up to make that happen?

**Stack trace basics:** An error report shows a stack trace with five lines. What is this telling you and how would you describe it to AI when asking for a fix?

**Error grouping:** Sentry shows 500 errors but they're actually just three different bugs happening repeatedly. How does error grouping help you focus?

**AI integration:** You want to add error tracking to your existing app. What would you describe to your AI coding tool to get it set up?

## Common Pitfalls

These are the mistakes vibecoders make most often with error tracking and logging. They're easy to make because your app seems fine—until it isn't. Spot them now so you don't find out the hard way.

Not setting up error tracking at all. Your app is crashing and you don't know it. Your users know.

They're just not telling you—they're leaving.

Logging sensitive data like passwords, credit card numbers, or personal information. Once it's in your logs, it's a security and privacy violation that can get you in real legal trouble.

Setting up alerts for everything and then ignoring all of them because you're drowning in noise.

Alert fatigue is real—if everything is urgent, nothing is urgent.

Not configuring source maps, so every error report shows minified gibberish instead of actual file names and line numbers. You can't debug what you can't read.

Using console.log for everything and calling it "logging." Console.log vanishes when you close the browser. Real logs persist, have severity levels, and are searchable.

Treating all errors as equal priority. A broken image on the About page is not the same as a crashed checkout flow. If you don't set severity levels, you'll waste time on the wrong problems.

## Self-Assessment Checklist

Before you take the exam, run through these questions. Every "no" is something to work on.

Do you have an error tracking service (like Sentry) connected to your app right now?

If your app crashed right now, would you get a notification within five minutes—or would you find out from a user complaint?

Can you open your error tracking dashboard and explain what the most recent error means in plain language?

Do your error reports include enough context to understand what the user was doing when the error happened?

Have you told AI to add error boundaries so your users see a friendly message instead of a blank white screen when something crashes?

Are your logs useful—meaning you can search them by user ID, action, or time range—or are they just random text?

Do you know the difference between a critical error (fix it now) and a warning (fix it this week)?

## AI Audit Prompt Template

Copy this prompt into your AI coding tool to get a quick health check on your error tracking and logging setup. It checks the same things the certification exam covers.

> Review my app's error tracking and logging setup and check the following. For each one, tell me pass or fail with a specific example:
>
>
>
> Error tracking integration: Is an error tracking service (like Sentry) connected and capturing errors automatically, or are errors happening silently?
>
>
>
> Error boundaries: Are error boundaries set up so users see a friendly message instead of a blank screen when something crashes?
>
>
>
> Logging quality: Are logs structured with consistent fields (user ID, action, timestamp, severity) or are they unstructured console.log statements?
>
>
>
> Alerting configuration: Are alerts configured so critical errors trigger immediate notifications, or is there no alerting set up?
>
>
>
> Source maps: Are source maps configured so error reports show readable file names and line numbers instead of minified code?
>
>
>
> Sensitive data protection: Are logs and error reports free of passwords, tokens, credit card numbers, and other sensitive data?
>
>
>
> Give me an overall score out of 6 and list the top 3 things to fix first.

## What’s Next

Once you've gone through this study guide and can answer "yes" to the self-assessment checklist, you're ready for the Layer 12 certification exam at your target tier.

The best way to prepare: check your own app right now. Do you have error tracking set up? Intentionally trigger an error and see if your monitoring catches it. Read the error report. Can you understand what happened? Can you describe the problem clearly enough for AI to fix it? That real-world experience is exactly what the exam tests.

## Certification Pathway

Associate Builder: Pass all 13 layers at Tier 1 Certified Builder: Pass all 13 layers at Tier 1 + Tier 2 MADE Certified: Pass all 39 tier exams + capstone project Each exam requires 80% to pass. You can retake after a 24-hour cooldown. No rush—take the time to build something real first.

———

Ready? Take the [Error Tracking & Logs Exam →](https://the-faction.mn.co/posts/the-foundation-layer-12-error-tracking-logs-exam)

---

## Discussion

**Anthony Candelario** · 2026-06-23

> *Note*: Link for download missing

**Awie Hoh** · 2026-07-01

> 12. ERROR TRACKING & LOGS
> 
> PURPOSE
> 
> Error tracking shows what broke. Logs explain what happened before, during, and after. Alerts tell a human in time to act.
> 
> PRINCIPLE
> 
> Production failures must be visible, searchable, safe, grouped, prioritized, and actionable. No error reports does not mean no bugs — it may mean no tracking, no alerts, or broken reporting.
> 
> WHAT THIS SECTION OWNS
> 
> Capturing failures, recording what happened, and alerting when it's serious. Other sections name which events matter (security events in #8, deploy failures in #5, cost signals in #6); the logging and alerting mechanism is defined here.
> 
> TOOLING
> 
> Use a real error-tracking tool (Sentry or equivalent) across frontend, backend, API, and background jobs. Console logs are not enough — real logs persist, have severity levels, and are searchable.
> 
> USER-FACING ERRORS
> 
> Users must never see a blank white screen. Use error boundaries, fallback screens, and clear messages so users know something went wrong and what to do next. Never show stack traces, secrets, database errors, or internal details to users. (This is the resilience promise from #1, kept here.)
> 
> THE FAILURE SIGNAL SET
> 
> One list of failures that matter, used three ways below: frontend crashes, backend/API errors, database errors, auth failures, permission-denied and RLS failures, payment and checkout failures, webhook failures, background-job failures, file upload/download failures, deployment failures, third-party API failures, slow requests, rate-limit events, security-sensitive events.
> 
> - TRACK: capture all of them.
> 
> - ALERT: only the ones that need immediate human action (below).
> 
> - DASHBOARD: watch their rates and trends (below).
> 
> SEVERITY
> 
> Critical = outage, data loss, payment failure, login failure, security issue, or broken core flow.
> 
> Error = failed feature or broken request.
> 
> Warning = suspicious or recoverable.
> 
> Info = important normal event.
> 
> Do not alert on everything — alert only when action is needed.
> 
> THE LOG RECORD
> 
> A useful log answers: who was affected, what action failed, when, where, which route or job ran, what status code returned, which service failed, whether the user was allowed, whether data changed, and what changed recently. To answer those, include: timestamp, environment, request ID, user ID (when safe), team/project/account ID (when relevant), route or action, status code, error type, duration, input shape (never sensitive input), external service, and job/webhook ID. Without this, "checkout crashed" is a complaint, not a diagnosis.
> 
> REQUEST ID
> 
> Every important request carries a request ID that links the frontend error, API log, database action, background job, and external call into one traceable story.
> 
> SOURCE MAPS
> 
> Configure source maps so production reports point to real files and lines, not minified gibberish.
> 
> ERROR GROUPING & PRIORITY
> 
> Group repeated errors by root cause — 500 reports may be only 3 real bugs. Prioritize by impact, affected users, affected flow, severity, and frequency.
> 
> SENSITIVE DATA & PERSONAL DATA
> 
> Never log passwords, tokens, API keys, private keys, session tokens, full payment details, or sensitive private content — redact them (echoing #8). Minimize and redact personal data (emails, IPs, names) too; logging it carries legal as well as security weight. Logs are not a dumping ground.
> 
> RETENTION & VOLUME
> 
> Logs cost money and have limits. Set a retention period that matches both incident need and budget — long enough to investigate a real failure, not so verbose that logging itself becomes a cost or noise problem (cost ceiling in #6).
> 
> ALERTS
> 
> Serious failures must reach a human fast — aim to know within ~5 minutes via error tracking, uptime monitoring, alert rules, and a real delivery channel (email, Slack, SMS, incident tool). Alert on the critical slice of the failure signal set: outage, error/500 spikes, payment and checkout failures, login failures, permission-denied spikes, webhook and job failures, database failures, high latency, security events. Avoid alert fatigue — if everything is urgent, nothing is.
> 
> DASHBOARDS
> 
> Watch production health: error rate, response time, request volume, failed requests, slow and top-failing routes, affected users, job and webhook failures, login failures, database health, external-API failures.
> 
> DEBUGGING FLOW
> 
> When something breaks, ask: what changed recently, which users are affected, which route or action failed, what status code returned, what the logs say, which layer it's in (frontend, backend, database, auth, storage, third-party, deploy), and whether it's isolated or system-wide.
> 
> AI WORKFLOW
> 
> To add tracking and logs, specify: tracking tool, frontend error handling, backend/API/job/webhook logging, request-ID behavior, source-map setup, error-boundary behavior, user-facing messages, log fields, what must never be logged, retention, severity levels, alert rules, dashboard metrics, and test cases. To fix an error, give AI: error message, stack trace, user action, expected vs actual behavior, affected page or endpoint, relevant logs, and recent code changes. (A "TypeError: cannot read properties of undefined" usually means data was missing, not yet loaded, or shaped differently than expected.)
> 
> TESTING
> 
> Before launch, verify: frontend errors report, backend/API errors log, error boundaries show friendly messages, source maps make reports readable, permission-denied/webhook/job failures are logged, alerts fire for serious failures, logs are searchable by user/action/request ID/time, and logs expose no secrets or personal data.
> 
> SHIP GATE — do not ship unless all are true
> 
> ☐ Production errors captured across frontend, backend, API, and jobs
> 
> ☐ Blank screens handled; users never see stack traces or internals
> 
> ☐ Source maps make reports readable
> 
> ☐ Logs searchable by user, action, request ID, and time
> 
> ☐ Request IDs link a failure across every layer
> 
> ☐ Errors grouped by root cause; severity clear
> 
> ☐ Serious failures alert a human fast; no alert fatigue
> 
> ☐ No secrets or personal data in logs; retention set to need and budget
> 
> ☐ A user-facing failure can be traced to its real cause


---
_Source: https://the-faction.mn.co/posts/102895502_
