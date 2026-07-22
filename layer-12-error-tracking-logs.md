# Layer 12 of 13 — Error Tracking & Logs
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Knowing When Something Breaks (Before Your Users Tell You)*

---

## What It Covers

Error tracking services, structured logging, error boundaries, alerting, and the difference between `console.log` and real logging.

**Core goal:** You understand why error tracking matters, can have AI set it up, and can read an error report well enough to explain what went wrong — even if you can't fix the code yourself.

---

## Key Concepts

**Why monitoring matters** — If your app crashes at 2am, you won't know until a user emails you. Error tracking is your early warning system: it watches 24/7 and tells you immediately when something breaks, with exactly what happened and where.

**Error tracking services** — Sentry, LogRocket. When an error happens, they capture: what went wrong, which page, which browser, the stack trace (breadcrumb trail through the code). You get a notification instead of silence. AI can integrate Sentry in one prompt.

**What logs are** — Your app's diary. Every significant event gets written: user logged in, payment processed, query executed. When something breaks, logs tell you the story of what happened right before. Without logs, debugging is guesswork.

**Error boundaries** — A safety net in your app. Instead of a crash showing a blank white screen, an error boundary catches the crash and shows "Something went wrong. Please try again." One component fails; the rest of the app keeps running.

**Structured logging** — Logs with consistent fields: timestamp, user ID, action, severity level (INFO / WARN / ERROR). Structured logs are searchable. Raw `console.log` statements are not. Use severity levels — not everything is an emergency.

**The vibecoder monitoring workflow** — Tell AI to add error tracking → AI integrates Sentry → errors auto-captured → you get a notification → you read the error report → you describe the problem to AI → AI fixes it → verify → ship.

---

## Toolkit

- **Sentry (free tier available)** — error tracking, grouping, stack traces, alerts
- **LogRocket / FullStory** — session replay: watch what the user did when the error happened
- **Platform built-in logs** — Vercel, Railway, Fly.io show server logs automatically; first place to look
- **Severity levels** — ERROR (fix now), WARN (fix this week), INFO (informational)

---

## Common Pitfalls

- No error tracking at all — app crashes silently, users just leave
- Logging sensitive data (passwords, credit card numbers) — legal violation
- Alert fatigue: alerting on everything = ignoring everything
- No source maps — every error shows minified gibberish instead of readable file + line
- Using `console.log` everywhere and calling it logging
- Treating all errors equally — a broken About page image is not the same as a crashed checkout

---

## Tier 1 Self-Assessment Checklist

- [ ] Is an error tracking service (Sentry) connected to your app right now?
- [ ] Would you get notified within 5 minutes if your app crashed?
- [ ] Can you open the error dashboard and explain the most recent error?
- [ ] Do error reports include enough context (user action, page, browser)?
- [ ] Are error boundaries set up so crashes show a friendly message?
- [ ] Are logs structured (searchable by user ID, action, time range)?
- [ ] Do you know the difference between a critical error and a warning?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's error tracking and logging setup. Pass or fail with a specific example:
1. Error tracking: Is Sentry (or similar) connected and capturing errors automatically?
2. Error boundaries: Do users see a friendly message instead of a blank screen on crash?
3. Logging quality: Are logs structured with consistent fields (user ID, action, timestamp, severity)?
4. Alerting: Are critical errors configured to trigger immediate notifications?
5. Source maps: Are source maps configured so errors show readable file names and line numbers?
6. Sensitive data: Are logs and error reports free of passwords, tokens, and personal data?

Give me a score out of 6 and the top 3 things to fix first.
```
