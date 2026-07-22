# Layer 4 of 13 — Auth & Permissions
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Running an enterprise-grade auth operation. At Tier 3, you're the person responsible for
security across the entire platform — multiple organizations use the system, compliance
requirements are non-negotiable, a security breach affects thousands of users. The job is
architecture and governance: making sure the system is locked down at every level.

**Core goal:** You can run an enterprise-grade auth operation — overseeing SSO integration,
multi-tenant security isolation, compliance-grade audit logging, and zero-trust architecture
across a platform serving multiple organizations.

---

## Key Concepts

**Single Sign-On / SSO (one login for everything)** — Lets enterprise customers use their
company's existing login system (Okta, Azure AD, Google Workspace) instead of creating separate
credentials — employees log in once with their company account and get access to all their
tools. Integrating with SSO providers and verifying the integration is secure is a requirement
for most enterprise sales.

**Multi-tenant architecture (keeping organizations separate)** — Multiple organizations share
the platform, but each one's data is completely isolated from the others. If Company A can
accidentally see Company B's data, that's a catastrophic security failure. Tenant isolation must
be enforced at the database level, the API level, and the UI level, and verified across every
feature.

**Zero-trust security model** — No request is automatically trusted; every request must prove
it's authorized, every time. Instead of "you're on the company network, so you're trusted," it's
"prove who you are and what you're allowed to do with every single request." Every API call,
every data access, every action gets verified.

**Compliance-grade audit logging** — Enterprise clients need a complete, tamper-proof record
of who did what, when, and from where. Audit logs must be immutable (can't be edited or
deleted), timestamped, and stored securely — regulations like SOC 2, HIPAA, and GDPR require
this.

**API key and service account management** — At enterprise scale, other software systems and
automated processes also need access, not just humans. API keys and service accounts need the
same careful permission management as human users: rotatable, with expiration dates, and
following the principle of least privilege (only the permissions needed, nothing more).

---

## Toolkit (adds to Tier 2)

- **SSO providers (Okta, Azure AD, WorkOS)** — enterprise identity providers that handle single sign-on integration, letting the app plug into customers' existing login systems
- **Compliance and audit platforms (Vanta, Drata)** — automated compliance monitoring that tracks security posture against frameworks like SOC 2 and helps pass audits
- **Secret management (AWS Secrets Manager, HashiCorp Vault)** — secure storage for API keys, database credentials, and service account tokens, so sensitive credentials aren't hardcoded in the app
- **Penetration testing services** — third-party security firms that attempt to break into the auth system, finding vulnerabilities before real attackers do

---

## Certification Exam Topics

- **SSO integration** — Can you evaluate whether an SSO implementation correctly handles user provisioning, deprovisioning, and session management across the identity provider and your app?
- **Multi-tenant isolation** — Can you verify that tenant data is completely isolated at every layer, database, API, and UI, with no possibility of cross-tenant data leaks?
- **Zero-trust evaluation** — Can you assess whether every API endpoint and data access point properly verifies authorization on every request, with no assumed trust?
- **Audit logging completeness** — Can you verify that security-critical events are being logged in a tamper-proof, compliant format, and that no important events are missing?
- **API key governance** — Can you evaluate whether API keys and service accounts follow least-privilege principles, have expiration dates, and can be rotated without downtime?
- **Incident response** — Can you evaluate a security incident response plan, including how a compromised account is detected, isolated, and remediated?
- **Compliance readiness** — Can you assess whether your auth system meets the requirements for SOC 2, GDPR, or HIPAA, depending on your industry and customer base?
- **Security architecture review** — Can you evaluate the overall auth architecture, identifying single points of failure, unnecessary trust assumptions, and areas that need hardening?

---

## Common Pitfalls

- Only testing that login works, never testing what happens after — can User A see User B's data? Are protected pages blocked when logged out?
- Letting AI build a custom auth system instead of using a proven auth provider — password hashing, token expiration, session invalidation, brute-force protection are easy to get wrong by hand
- Storing passwords in plain text instead of hashed
- Forgetting row-level security — the most common auth gap AI creates: logged-in users can see everyone's data
- Sessions that never expire — no way to force out a stolen device or compromised credential
- Not protecting the password reset flow — link never expires, reusable, no notification to the account owner

---

## Tier 3 Self-Assessment Checklist

- [ ] Can you describe your app's access rules to AI clearly, who can sign up, who can log in, and what each user type can see and do?
- [ ] Have you tested your app by logging in as two different users and confirming each can only see their own data?
- [ ] Have you tried accessing protected pages and API endpoints without being logged in, and confirmed they're blocked?
- [ ] Are you using a proven auth provider (Supabase Auth, Clerk, Auth0) instead of letting AI build a custom one from scratch?
- [ ] Do your sessions expire after a reasonable time, and does logging out actually end the session?
- [ ] Have you tested the password reset flow, checking that links expire, work only once, and notify the account owner?
- [ ] Can you explain the difference between authentication (who you are) and authorization (what you're allowed to do), and identify gaps in either one?

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

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 4 certification exam at your target tier.

The best way to prepare: build something real. Pick a project that needs user accounts, even a
simple one like a personal dashboard or a shared task list, and go through the full loop.
Describe your access rules to AI. Test by logging in as different users. Try to break into
places you shouldn't be. Fix every gap. Ship it. Every security hole caught during building is
exactly what the exam tests.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
