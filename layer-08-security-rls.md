# Layer 8 of 13 — Security & RLS
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Making Sure Nobody Sees Data They Shouldn't*

---

## What It Covers

Row-Level Security (RLS), HTTPS, input sanitization, secrets management, and CORS.

**Core goal:** You can verify that your app keeps each user's data private, uses encrypted connections, blocks common web attacks, and stores secrets safely — all by directing AI with the right prompts.

---

## Key Concepts

**Row-Level Security (RLS)** — Database-level rules ensuring User A can't see User B's rows. In Supabase: RLS is built-in but *off by default*. Every new table with user data needs RLS turned on and a policy written. If you don't ask AI for this explicitly, it won't do it.

**HTTPS** — Data traveling between user browser and server is encrypted. Hosting platforms (Vercel, Netlify, Railway) give it free. Verify the padlock is showing. No HTTP fallbacks.

**Input sanitization** — Users type things into your app. Bad actors type `<script>alert('xss')</script>` into text fields. Input sanitization cleans up what users type before it hits your database or gets rendered. Without it: SQL injection, XSS attacks, data corruption.

**Secrets management** — API keys, DB passwords = secrets. Never in your code. Always in environment variables. AI tools hardcode secrets regularly — always check every file AI generates.

**CORS** — Cross-Origin Resource Sharing. Controls which domains can request data from your API. Without CORS restrictions, any website can try to pull from your backend. Lock it to only your own domains.

**Authentication ≠ Authorization** — Authentication proves who you are. Authorization defines what you can do. You need both. Server-side enforcement only — hiding UI elements is not access control.

---

## Toolkit

- **Supabase RLS** — built-in, enable on every table with user data
- **`.env` / platform env config** — secrets outside your code
- **Browser DevTools (Network tab)** — verify all requests use HTTPS
- **Security headers** — Content-Security-Policy, X-Frame-Options, Strict-Transport-Security

---

## Common Pitfalls

- RLS off by default in Supabase — forgetting to enable it on new tables
- API keys hardcoded in source files (AI does this all the time)
- Frontend-only permission checks (hiding buttons ≠ blocking access)
- Skipping input sanitization ("nobody would do that")
- Never testing by trying to access another user's data

---

## Tier 1 Self-Assessment Checklist

- [ ] Can you log in as User A and confirm you cannot see User B's data?
- [ ] Is RLS enabled on every table with user-specific data?
- [ ] Are all secrets in environment variables (never in code)?
- [ ] Does the app use HTTPS everywhere, with no HTTP fallbacks?
- [ ] Have you tested input fields with special characters and script tags?
- [ ] Are CORS settings restricted to only your domains?
- [ ] Does every protected API endpoint verify identity AND permissions server-side?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's security setup. Pass or fail with a specific example:
1. RLS: Is Row-Level Security enabled on every table with user data? Do policies correctly restrict rows?
2. Secrets: Are there any API keys, passwords, or tokens hardcoded in source files?
3. HTTPS: Are all connections encrypted? Any HTTP URLs or mixed-content warnings?
4. Input sanitization: Are user inputs validated and sanitized before database queries or rendering?
5. CORS: Is the app's CORS policy restricted to only authorized domains?
6. Auth enforcement: Does every API endpoint verify identity and permissions before returning data?
7. Security headers: Are Content-Security-Policy, X-Frame-Options, and Strict-Transport-Security present?

Give me a score out of 7 and list the top 3 security issues to fix first.
```
