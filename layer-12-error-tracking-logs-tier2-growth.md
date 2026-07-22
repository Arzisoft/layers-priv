# Layer 12 of 13 — Error Tracking & Logs
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Managing errors efficiently once the app has real users and a team — the challenge shifts from
knowing errors exist to prioritizing which ones matter, understanding patterns, and debugging
faster.

**Core goal:** You can implement structured logging, configure intelligent alerting, group and
prioritize errors by impact, and use session replay to debug user-reported issues quickly.

---

## Key Concepts

**Structured logging** — Basic logs are plain text, hard to search and filter. Structured logs
add consistent fields to every entry: user ID, action, page, timestamp, severity level, turning
logs from a messy notebook into a searchable database. Search a user's ID and see every step
they took.

**Error severity levels** — Not all errors are equal. "Critical" means the payment system is
down, fix it now. "Warning" means something is degraded but still working. "Info" is a routine
record. Setting severity correctly means getting paged for crashes, not for a mistyped email.

**Alerting rules** — Without rules, you get notified about everything (alert fatigue, you start
ignoring them) or nothing (you miss real problems). Good alerting sends a message for critical
issues, batches warnings into a daily summary, and ignores routine noise.

**Session replay** — When a user reports "it's broken," that's not enough information. Tools
like LogRocket record the user's screen so you can watch exactly what they saw, what they
clicked, and where things went wrong — a security camera for the app.

**Source maps** — Deployed code is minified to load faster, so error reports show garbled file
names and line numbers. Source maps translate these back to the original code so error reports
actually make sense.

---

## Toolkit (adds to Tier 1)

- **Sentry with alerting rules** — alert on critical errors immediately, batch warnings daily, ignore known low-priority issues already triaged
- **LogRocket or FullStory (session replay)** — watch exactly what users experienced when they hit a bug, no more guessing from vague bug reports
- **Structured logging library (Winston, Pino)** — write structured, searchable logs instead of plain text console messages
- **PagerDuty or Opsgenie** — escalation tools that wake up the right person for critical errors that truly can't wait

---

## Certification Exam Topics

- **Alert fatigue** — Your team is getting 200 notifications per day and has started ignoring them. Most are low-severity warnings. How do you fix your alerting rules?
- **Structured log search** — A user with ID 4829 reports a checkout failure at 3:15 PM. How do structured logs help you investigate compared to plain text logs?
- **Error prioritization** — Sentry shows three errors: one affecting 500 users on the payment page, one affecting 3 users on the settings page, and one in a feature nobody uses. How do you prioritize?
- **Session replay usage** — A user says "the page looked weird and I couldn't click the button." Without session replay, what would you do? With it, what changes?
- **Source map configuration** — Your Sentry error reports show errors in files named "chunk-abc123.js" at line 1. What's wrong and what needs to be configured?
- **Severity level design** — Your team wants to be paged for payment failures but not for failed image loads. How do you set up severity levels and alerting?
- **Error budget** — Your app had 50 errors yesterday affecting 200 users out of 10,000. Is that acceptable? How do you decide what error rate is too high?
- **Log retention** — Your logs are using 50GB of storage per month and your costs are climbing. What strategies balance keeping useful logs with controlling costs?

---

## Common Pitfalls

- Not setting up error tracking at all — the app is crashing and you don't know it; users know, they're just not telling you, they're leaving
- Logging sensitive data like passwords, credit card numbers, or personal information — a security and privacy violation with real legal exposure
- Setting up alerts for everything and then ignoring all of them — alert fatigue is real, if everything is urgent, nothing is urgent
- Not configuring source maps, so every error report shows minified gibberish instead of actual file names and line numbers
- Using console.log for everything and calling it "logging" — console.log vanishes when the browser closes; real logs persist, have severity levels, and are searchable
- Treating all errors as equal priority — a broken image on the About page is not the same as a crashed checkout flow

---

## Tier 2 Self-Assessment Checklist

- [ ] Do you have an error tracking service (like Sentry) connected to your app right now?
- [ ] If your app crashed right now, would you get a notification within five minutes, or would you find out from a user complaint?
- [ ] Can you open your error tracking dashboard and explain what the most recent error means in plain language?
- [ ] Do your error reports include enough context to understand what the user was doing when the error happened?
- [ ] Have you told AI to add error boundaries so users see a friendly message instead of a blank white screen when something crashes?
- [ ] Are your logs useful, meaning you can search them by user ID, action, or time range, or are they just random text?
- [ ] Do you know the difference between a critical error (fix it now) and a warning (fix it this week)?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's error tracking and logging setup and check the following. For
each one, tell me pass or fail with a specific example:
Error tracking integration: Is an error tracking service (like Sentry)
connected and capturing errors automatically, or are errors happening
silently?
Error boundaries: Are error boundaries set up so users see a friendly message
instead of a blank screen when something crashes?
Logging quality: Are logs structured with consistent fields (user ID, action,
timestamp, severity) or are they unstructured console.log statements?
Alerting configuration: Are alerts configured so critical errors trigger
immediate notifications, or is there no alerting set up?
Source maps: Are source maps configured so error reports show readable file
names and line numbers instead of minified code?
Sensitive data protection: Are logs and error reports free of passwords,
tokens, credit card numbers, and other sensitive data?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
