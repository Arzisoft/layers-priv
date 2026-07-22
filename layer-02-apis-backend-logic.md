# Layer 2 of 13 — APIs & Backend Logic
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Making Your App Do Things, Not Just Look Good*

---

## What It Covers

The logic layer: REST APIs, how frontend talks to backend, endpoint design, error handling, data validation, and how to test with Postman.

**Core goal:** You can describe what data your app needs and how it should flow — and have AI build the endpoints correctly.

---

## Key Concepts

**REST API basics** — Four verbs: GET (fetch), POST (create), PUT/PATCH (update), DELETE (remove). Each maps to a URL endpoint. `/api/users` GET = list users. `/api/users/42` DELETE = remove user 42.

**Endpoint design** — URLs should be nouns, not verbs. `/api/orders` not `/api/getOrders`. Consistent naming prevents confusion across the whole app.

**HTTP status codes** — 200 OK, 201 Created, 400 Bad Request (your fault), 401 Unauthorized, 403 Forbidden, 404 Not Found, 500 Server Error. Always return the right one.

**Error handling** — Every endpoint can fail. Return a JSON error object with a message, not a raw stack trace. Log the real error server-side; send a safe message to the client.

**Data validation** — Validate every field that comes from a user. Email must be an email. Amount must be a positive number. Missing required fields = 400, not a server crash.

**JSON** — The standard format for API responses. Key-value pairs, arrays. Keep it consistent; define a response shape and stick to it.

---

## Toolkit

- **Postman** — Test every endpoint. Set up a collection for your app before writing frontend code.
- **Zod / Joi / Yup** — Schema validation libraries; AI knows all three
- **Your framework's built-in router** — Next.js API routes, Express, Laravel routes

---

## Common Pitfalls

- Returning 200 for errors ("success: false" with a 200 status)
- No validation — trusting whatever the frontend sends
- Exposing stack traces in production error responses
- Inconsistent naming (camelCase in one endpoint, snake_case in another)
- Forgetting to test the unhappy path (what happens when something goes wrong?)

---

## Tier 1 Self-Assessment Checklist

- [ ] Can you explain GET/POST/PUT/DELETE to a non-technical person?
- [ ] Do all your endpoints return the correct HTTP status codes?
- [ ] Is every user-provided input validated before it hits the database?
- [ ] Do error responses return a message but not a stack trace?
- [ ] Have you tested your endpoints in Postman (not just via the UI)?
- [ ] Are your URL patterns consistent across the app?
- [ ] Can you explain the difference between a 401 and a 403?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's API design and check the following. Pass or fail with a specific example:
1. Status codes: Do endpoints return correct HTTP codes (200, 201, 400, 401, 404, 500)?
2. Input validation: Is every user-supplied field validated before use?
3. Error responses: Do errors return JSON messages, not stack traces?
4. Endpoint naming: Are URLs noun-based and consistent?
5. Request/response shapes: Are response shapes consistent and documented?
6. Security: Are endpoints protected so unauthenticated users can't access private data?

Give me a score out of 6 and the top 3 things to fix first.
```
