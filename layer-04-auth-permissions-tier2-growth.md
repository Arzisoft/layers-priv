# Layer 4 of 13 — Auth & Permissions
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Managing access for multiple user types as an app grows. The challenge shifts from "can people
log in?" to "can you control exactly what each person can access based on their role and
organization?"

**Core goal:** You can manage a role-based permission system, implement team/organization
access, handle secure session management, and integrate third-party login providers.

---

## Key Concepts

**Roles and permissions** — A role (admin, editor, viewer) is a label that bundles a set of
permissions, so you assign a role instead of setting access per individual user — like job
titles at a company determining what keys you get.

**OAuth and social login** — "Log in with Google/Apple/GitHub" lets a provider confirm identity
instead of your app managing another password. More secure and more convenient.

**Multi-factor authentication (MFA)** — Requiring something beyond a password (an app code,
a text). Even a stolen password isn't enough to get in. Know when to require it (admin accounts,
sensitive actions) and how to verify AI implemented it correctly.

**Team-based access** — Users see/manage things belonging to their own team/organization,
not other teams'. AI commonly gets this wrong by giving any logged-in user access to all data
instead of scoping to their org.

**Secure session handling** — Tokens should expire, refresh securely, and be invalidated on
logout or password change. AI often creates sessions that never expire or persist after logout.

---

## Toolkit (adds to Tier 1)

- **Role management (Clerk, Supabase RLS policies)** — define roles/permissions once, enforce everywhere
- **OAuth providers (Google, Apple, GitHub integrations)** — pre-built, don't hand-roll login
- **Session monitoring (Clerk dashboard, Supabase auth logs)** — active sessions, login attempts, suspicious activity
- **Permission testing frameworks** — test suites verifying each role only accesses what it should

---

## Common Pitfalls

- Only testing that login works, never testing what happens after — can User A see User B's data?
- Letting AI build custom auth instead of a proven provider — hashing, expiry, brute-force protection are easy to get wrong by hand
- Passwords stored in plain text instead of hashed
- Missing row-level security — the most common auth gap AI creates: logged-in users can see everyone's data
- Sessions that never expire — no way to force out a stolen device/compromised credential
- Unprotected password reset flow — link never expires, reusable, no notification to the account owner

---

## Tier 2 Self-Assessment Checklist

- [ ] Can you describe access rules to AI clearly — who signs up, who logs in, what each type can see/do?
- [ ] Have you logged in as two different users and confirmed each only sees their own data?
- [ ] Have you tried protected pages/endpoints while logged out and confirmed they're blocked?
- [ ] Are you using a proven auth provider instead of a custom-built one?
- [ ] Do sessions expire, and does logout actually end the session?
- [ ] Have you tested the password reset flow (expiry, single-use, owner notification)?
- [ ] Can you explain authentication vs authorization and spot gaps in either?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's authentication and permissions system and check the
following. For each one, tell me pass or fail with a specific example:
Authentication flow: Is the login/signup system using a proven auth provider
with proper password hashing, session management, and email verification?
Authorization enforcement: Does every protected page and API endpoint check
that the user is logged in AND authorized to perform the requested action?
Row-level security: Can users only access their own data, or can a logged-in
user see, edit, or delete records belonging to other users?
Session management: Do sessions expire after a reasonable time, get
invalidated on logout, and refresh securely?
Password reset security: Do reset links expire quickly, work only once, and
notify the account owner when their password is changed?
Protected routes: Are all pages and endpoints that should require
authentication actually gated, with no unprotected backdoors?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
