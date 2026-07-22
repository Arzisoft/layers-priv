# Layer 2 of 13 — APIs & Backend Logic
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Keeping a growing backend organized and reliable as traffic and workflows get more complex.
The challenge shifts from "does it work?" to "does it stay reliable and organized as the app
grows?"

**Core goal:** You can manage API versions, implement webhooks, handle errors gracefully at
scale, and coordinate multiple backend services as the app grows.

---

## Key Concepts

**API versioning** — Updating an API can break existing users/other apps that talk to yours.
Versioning keeps the old version running (`/api/v1/orders`) while rolling out the new one
(`/api/v2/orders`). Without this, every update is a gamble.

**Webhooks** — Your app proactively notifying another system when something happens ("a new
order just came in", "this payment just failed") instead of that system polling for updates.
A doorbell instead of repeatedly checking the peephole.

**Middleware** — Code that runs between receiving a request and processing it — a security
desk that checks your badge, logs your visit, and decides if you're allowed in. Common
middleware checks authentication, validates data, logs requests.

**Rate limiting** — A cap on how many requests someone can make in a given time (e.g. 100/min
per user). Without it, one misbehaving user or bot can flood the server and crash it for
everyone.

**Background jobs** — Slow tasks (emails, image processing, report generation) handled after
the initial response so the user isn't staring at a spinner — the waiter takes the order
instantly, the kitchen works on it in the background.

---

## Toolkit (adds to Tier 1)

- **API documentation (Swagger/OpenAPI)** — auto-generates a readable manual for the API
- **Queue/job processors (BullMQ, Inngest)** — manage background jobs so the API stays fast
- **Logging and monitoring (Sentry, LogTail)** — tracks every error/request, what's breaking and for whom
- **Webhook testing (webhook.site, ngrok)** — temporary public URL to test webhooks locally

---

## Common Pitfalls

- Only testing the happy path — AI almost never builds error handling unless specifically asked
- Not checking what the API actually returns — it may leak passwords, internal IDs, or data the user shouldn't see
- Skipping authentication on endpoints that need it (e.g. account deletion)
- Building one giant endpoint instead of separate, focused ones
- Not handling a slow/down server — infinite spinner or silent failure instead of a timeout + clear message
- Treating AI's first backend output as production-ready — it works for the demo, breaks under real conditions

---

## Tier 2 Self-Assessment Checklist

- [ ] Can you describe a backend feature to AI and get a working endpoint in 1-2 tries?
- [ ] Have you tested endpoints with an API testing tool, not just through the app's frontend?
- [ ] Can you read a JSON response and verify it has the right data in the right structure?
- [ ] Do endpoints return helpful error messages, not just a blank 500?
- [ ] Have you checked that endpoints validate incoming data before processing it?
- [ ] Can you trace a request from button click to server response in the network tab?
- [ ] Do you know GET/POST/PUT/DELETE well enough to catch AI using the wrong one?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's backend API and check the following. For each one, tell me
pass or fail with a specific example:
Endpoint organization: Are my API endpoints logically organized with
consistent naming and proper HTTP methods (GET, POST, PUT, DELETE)?
Error handling: Does every endpoint handle errors gracefully, returning
helpful error messages with correct status codes instead of crashing silently?
Input validation: Does every endpoint check incoming data before processing
it, rejecting missing fields, wrong data types, and invalid values?
Authentication: Are protected endpoints properly checking that the user is
logged in and authorized before allowing the action?
Response quality: Are responses returning only the data the frontend needs,
not leaking sensitive fields like passwords, internal IDs, or private user data?
Performance: Are there any endpoints that will be slow under load, missing
pagination, loading too much data at once, or making unnecessary database calls?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
