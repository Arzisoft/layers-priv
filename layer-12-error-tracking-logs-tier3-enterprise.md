# Layer 12 of 13 — Error Tracking & Logs
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Architecting observability across a whole platform. At Tier 3, the platform has multiple
services, multiple teams, and reliability requirements with real business consequences —
debugging isn't just about finding errors, it's about tracing problems across an entire system
and responding to incidents with a coordinated process.

**Core goal:** You can architect centralized observability across multiple services, implement
distributed tracing, define error budgets and SLOs, and build automated incident response
workflows for enterprise platforms.

---

## Key Concepts

**Distributed tracing** — When a user clicks "Place Order," that request might pass through five
different services: authentication, inventory, payment, shipping, notification. If the order fails,
which service broke? Distributed tracing follows a request across every service it touches, like a
tracking number for your code. Tools like Jaeger and OpenTelemetry do this.

**Centralized observability** — Instead of each service having its own separate logs and error
reports, centralized observability collects everything into one place. One dashboard shows
errors from the frontend, backend, database, and every microservice — essential when multiple
teams each run their own services.

**SLOs and error budgets** — An SLO (Service Level Objective) is a target you set, like "99.9% of
requests succeed." The error budget is how much failure that allows (0.1% of requests can fail).
Within budget, you can ship fast; burning through the error budget means slowing down and
focusing on reliability. This replaces gut feelings with data.

**Automated incident response** — When a critical error happens, an automated workflow kicks
in: the right team gets paged, a status page updates automatically, a communication channel
opens, and a runbook (step-by-step instructions) appears — turning panicked firefighting into a
coordinated process.

**Compliance and audit logging** — Enterprise clients and regulated industries require logs that
prove what happened, when, and who did it. These logs can't be deleted or modified — they're
proof of work, showing auditors and clients exactly how the system behaved during any incident.

---

## Toolkit (adds to Tier 2)

- **Datadog or New Relic** — enterprise observability platforms that combine logs, metrics, traces, and dashboards into one system, giving a single view across the entire platform
- **OpenTelemetry** — an open standard for distributed tracing that works across different services and languages; ask AI to instrument services with OpenTelemetry to trace requests end-to-end
- **PagerDuty with automated workflows** — enterprise-grade incident management that pages the right team, opens a war room, updates the status page, and triggers runbooks, all automatically
- **Grafana Loki** — a log aggregation system that collects logs from every service into one searchable place, with dashboards showing log patterns and anomalies across the entire platform

---

## Certification Exam Topics

- **Distributed tracing** — A user's checkout fails. The request passed through four services. How does distributed tracing help you identify which service caused the failure?
- **Centralized vs. scattered** — Your platform has eight services, each with its own Sentry project and separate logs. What problems does this create and how does centralized observability solve them?
- **SLO definition** — Your platform has a 99.9% uptime SLO. You had 10 minutes of downtime this month. Are you within your error budget? Show your reasoning.
- **Incident response automation** — A critical payment service goes down at midnight. Walk through what an automated incident response workflow should do in the first five minutes.
- **Compliance logging** — A client asks for proof that no unauthorized access occurred during a security incident last Tuesday. What kind of logging makes this possible?
- **Error budget policy** — Your error budget is nearly exhausted with two weeks left in the quarter. What should change about how your team ships new features?
- **Cross-service debugging** — Service A calls Service B, which calls Service C. The user sees a timeout error. Without distributed tracing, how would you investigate? With it, what changes?
- **Observability cost management** — Your centralized logging platform costs $15,000/month and growing. How do you optimize costs without losing the ability to debug critical issues?

---

## Common Pitfalls

- Not setting up error tracking at all — the app is crashing and you don't know it, but users do; they just leave instead of telling you
- Logging sensitive data like passwords, credit card numbers, or personal information — once it's in the logs, it's a security and privacy violation that can create real legal trouble
- Setting up alerts for everything and then ignoring all of them because you're drowning in noise — alert fatigue is real, if everything is urgent, nothing is urgent
- Not configuring source maps, so every error report shows minified gibberish instead of actual file names and line numbers
- Using console.log for everything and calling it "logging" — console.log vanishes when you close the browser, real logs persist, have severity levels, and are searchable
- Treating all errors as equal priority — a broken image on the About page is not the same as a crashed checkout flow

---

## Tier 3 Self-Assessment Checklist

- [ ] Do you have an error tracking service (like Sentry) connected to your app right now?
- [ ] If your app crashed right now, would you get a notification within five minutes, or would you find out from a user complaint?
- [ ] Can you open your error tracking dashboard and explain what the most recent error means in plain language?
- [ ] Do your error reports include enough context to understand what the user was doing when the error happened?
- [ ] Have you told AI to add error boundaries so your users see a friendly message instead of a blank white screen when something crashes?
- [ ] Are your logs useful, meaning you can search them by user ID, action, or time range, or are they just random text?
- [ ] Do you know the difference between a critical error (fix it now) and a warning (fix it this week)?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's error tracking and logging setup and check the following.
For each one, tell me pass or fail with a specific example:
Error tracking integration: Is an error tracking service (like Sentry)
connected and capturing errors automatically, or are errors happening
silently?
Error boundaries: Are error boundaries set up so users see a friendly
message instead of a blank screen when something crashes?
Logging quality: Are logs structured with consistent fields (user ID,
action, timestamp, severity) or are they unstructured console.log statements?
Alerting configuration: Are alerts configured so critical errors trigger
immediate notifications, or is there no alerting set up?
Source maps: Are source maps configured so error reports show readable file
names and line numbers instead of minified code?
Sensitive data protection: Are logs and error reports free of passwords,
tokens, credit card numbers, and other sensitive data?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 12 certification exam at your target tier.

The best way to prepare: check your own app right now. Do you have error tracking set up?
Intentionally trigger an error and see if your monitoring catches it. Read the error report. Can you
understand what happened? Can you describe the problem clearly enough for AI to fix it? That
real-world experience is exactly what the exam tests.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
