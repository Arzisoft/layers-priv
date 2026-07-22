# Layer 8 of 13 — Security & RLS
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Managing security once an app has multiple user types (admins, team members, customers)
each with different access levels — not just isolating individual users, but managing groups,
roles, and permissions.

**Core goal:** You can manage role-based access control, implement defense-in-depth, audit
AI-generated code for security, and monitor for suspicious activity.

---

## Key Concepts

**Role-based access control (RBAC)** — Roles (admin, manager, member, viewer) each carry
different permissions. AI can build it, but you must define the roles clearly and verify the
boundaries hold: log in as a regular user and try to do admin things — if it works, security is
broken.

**Defense in depth** — Don't rely on one security measure. If an RLS policy has a bug, the API
should also check permissions; if the API check fails, the frontend should still hide
unauthorized actions — a locked front door, a security desk, and locked office doors, so one
failure doesn't expose everything.

**SQL injection prevention** — An attacker typing database commands into an input field that
your app accidentally executes. AI tools should use parameterized queries, but verify it
yourself, especially on search fields and login forms.

**Security logging and monitoring** — Know when something suspicious happens (50 failed
logins in a row, an account accessing data it shouldn't). Log failed logins, permission denials,
unusual access patterns — catch problems before they're breaches.

**API security** — Every endpoint is a door: is this person logged in, are they allowed this
specific action, is the data they sent valid? AI often builds endpoints that work but skip these
checks.

---

## Toolkit (adds to Tier 1)

- **Supabase Auth with custom claims** — RLS policies can check role, not just ownership
- **OWASP ZAP or Burp Suite** — automated vulnerability scanning, an automated attacker that reports what it found
- **Sentry or LogRocket** — error and unusual-behavior monitoring in the live app
- **Helmet.js** — automatically adds protective security headers to responses

---

## Common Pitfalls

- Forgetting to enable RLS on new tables — Supabase creates tables with RLS off by default; every user-data table needs it on with a policy written
- Secrets hardcoded in code instead of environment variables
- Only checking permissions on the frontend — hiding a button doesn't block the API call; enforcement must be server-side
- Skipping input sanitization because "nobody would do that" — bots scan every app on the internet, no reason needed
- HTTP instead of HTTPS, or never verifying HTTPS is actually active on the deployed app
- Never testing your own security by trying to break it — log in as one user, try to access another's data

---

## Tier 2 Self-Assessment Checklist

- [ ] Can you log in as User A and confirm you can't see User B's data anywhere?
- [ ] Have you verified RLS is enabled on every table with user data?
- [ ] Are all secrets in environment variables, not code?
- [ ] Does the app use HTTPS for every connection, no HTTP fallbacks?
- [ ] Have you tested input fields with special characters, script tags, SQL-like commands?
- [ ] Can you explain authentication vs. authorization?
- [ ] Have you checked CORS settings so only your domains can hit the API?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's security setup and check the following. For each one, tell me
pass or fail with a specific example:
RLS policies: Is Row-Level Security enabled on every table with user data? Do
the policies correctly restrict each user to their own rows?
Secrets management: Are there any API keys, database passwords, or tokens
hardcoded in the source code instead of environment variables?
HTTPS: Are all connections encrypted? Are there any HTTP URLs or mixed-
content warnings?
Input sanitization: Are user inputs validated and sanitized before being used
in database queries or rendered on pages?
CORS configuration: Is the app's CORS policy restricted to only the domains
it should accept requests from?
Authentication and authorization: Does every API endpoint verify the user's
identity and check their permissions before returning data?
Security headers: Are headers like Content-Security-Policy, X-Frame-Options,
and Strict-Transport-Security present?
Give me an overall score out of 7 and list the top 3 security issues to fix
first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
