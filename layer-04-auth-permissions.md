# Layer 4 of 13 — Auth & Permissions
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Knowing Who's Logged In and What They're Allowed to Do*

---

## What It Covers

Authentication (who you are), authorization (what you can do), JWT tokens, row-level security, session expiry, and proven auth providers.

**Core goal:** You can verify that only the right people see the right data — by directing AI to implement proper auth, not just hiding buttons.

---

## Key Concepts

**Authentication vs Authorization**
- Authentication = *who are you?* (login, identity)
- Authorization = *what are you allowed to do?* (permissions, roles)
- You need both. Authentication without authorization = everyone logged in can do everything.

**JWT tokens** — JSON Web Tokens. After login, the server gives the user a signed token. Every subsequent request sends that token. The server verifies the signature — no database lookup needed per request. Tokens expire (usually 1h–24h).

**Session management** — How long does a login last? Short sessions = more secure but more friction. Long sessions = convenient but risky. Refresh tokens extend sessions without re-login. Never store JWT in localStorage — use httpOnly cookies.

**Row-Level Security (RLS)** — Database-level rules: "User A can only read rows where `user_id = A`." Prevents one user from seeing another's data even if someone bypasses your app logic.

**Auth providers (use proven ones)** — Don't build auth from scratch. Use Supabase Auth, Clerk, or Auth0. They handle password hashing, OAuth, MFA, session management. AI can wire them up; you verify the config.

**Always enforce on the server** — Hiding a button is not access control. Anyone can call your API directly. Every protected endpoint must verify the user's token and check their permissions server-side.

---

## Toolkit

- **Supabase Auth / Clerk / Auth0** — managed auth, don't reinvent
- **NextAuth.js** — for Next.js apps
- **JWT.io** — decode and inspect JWT tokens during debugging
- **Postman** — test endpoints without auth to confirm they're actually blocked

---

## Common Pitfalls

- Relying on the frontend to hide protected content (UI-only auth)
- Storing JWT in localStorage (vulnerable to XSS)
- No token expiry — sessions last forever
- Building custom auth when a provider would be faster and safer
- Forgetting to test what users *cannot* do — only testing the happy path
- Not implementing RLS, so database queries return all rows

---

## Tier 1 Self-Assessment Checklist

- [ ] Can you explain the difference between authentication and authorization?
- [ ] Is your auth handled by a proven provider (not hand-rolled)?
- [ ] Are JWT tokens stored in httpOnly cookies, not localStorage?
- [ ] Do tokens expire? Is there a refresh mechanism?
- [ ] Is RLS enabled on every table that contains user-specific data?
- [ ] Have you tested that User A cannot access User B's data?
- [ ] Do all protected API endpoints verify the token server-side?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's authentication and authorization setup. Pass or fail with a specific example:
1. Auth provider: Is authentication handled by a proven provider or custom code?
2. Token storage: Are tokens stored in httpOnly cookies (not localStorage)?
3. Token expiry: Do tokens expire and is there a refresh flow?
4. Server-side enforcement: Does every protected endpoint verify identity AND permissions?
5. RLS: Is row-level security enabled on all tables with user-specific data?
6. Role separation: Are different user roles (admin, viewer, client) enforced consistently?

Give me a score out of 6 and the top 3 things to fix first.
```
