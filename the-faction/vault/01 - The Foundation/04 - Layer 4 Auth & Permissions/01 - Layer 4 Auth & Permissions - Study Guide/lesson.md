---
course: "The Foundation"
module: "Layer 4: Auth & Permissions"
lesson: "Layer 4: Auth & Permissions — Study Guide"
type: "course_lesson"
post_id: 102891677
space_id: 23777123
source: "https://the-faction.mn.co/posts/102891677"
updated: "2026-09-08T17:15:30Z"
---

# Layer 4: Auth & Permissions — Study Guide

## Layer 4: Auth & Permissions

Making Sure the Right People See the Right Things

This is the study guide. Everything for Auth & Permissions is on this page — there's nothing to download.

## What This Study Guide Covers

This study guide covers Layer 4: Auth & Permissions—who gets in and what they can do. Auth is short for authentication ("who are you?") and authorization ("what are you allowed to do?"). Every app that has user accounts needs both. Authentication is the lock on your front door—it verifies identity. Authorization is the set of rules about which rooms each person can enter once they're inside.

You're not going to build login systems by hand. You're going to describe what your app's access rules should be—"users can only see their own data, admins can see everything, and visitors can only see the public homepage"—and let your AI coding tool build the auth layer for you. Your job is to understand how access control works, check that the rules are enforced correctly, and make sure nobody can sneak into places they shouldn't be. That's what this certification proves you can do.

This study guide walks you through the concepts, tools, and checkpoints you need to pass the Auth & Permissions certification exam.

## Why It Matters

Getting auth wrong is the most expensive mistake you can make. If your frontend looks bad, users complain. If your backend is slow, users wait. But if your auth is broken, strangers can access other people's accounts, read private data, delete records, and take actions they were never supposed to take. Auth failures don't just cause bugs—they cause security breaches, data leaks, and lost trust that you may never recover from.

Here's the thing about AI coding tools: they can set up a login page in seconds, and it will look perfectly fine. But looking fine and being secure are two completely different things. AI often skips critical details—like checking that a logged-in user can only access their own data, or properly expiring sessions, or protecting password reset flows from abuse. Auth is the one layer where "it works in the demo" is genuinely dangerous. This study guide teaches you what to verify before you trust it with real users.

## CERTIFICATION GOAL

You can describe your app's access rules, use an AI coding tool to build login and signup, verify that users can only access their own data, and ship an app where nobody can see or do things they shouldn't.

## What You Need to Know

You don't need to understand cryptography. You need to understand a handful of concepts so you can describe your access rules clearly and catch security holes in what AI gives you back.

Authentication vs. authorization (two different questions): Authentication asks "who are you?"— that's the login process. Authorization asks "what are you allowed to do?"—that's the permissions system. AI often builds authentication (the login screen works) but skips authorization (anyone who's logged in can access everything). You need both, and you need to check for both.

**How login actually works behind the scenes:** When a user logs in, the server checks their credentials and creates a session or a token—a digital pass that says "this person proved who they are." That pass is sent to the browser and included with every future request. If the pass is missing or expired, the server rejects the request. Think of it like a wristband at an event—you show your ID once at the door, get a wristband, and flash it everywhere else.

**What a JWT token is:** JWT (pronounced "jot") stands for JSON Web Token. It's the most common type of digital pass AI tools create. It's a string of text that contains the user's identity information and an expiration time. Your app sends it with every request to prove the user is logged in. You don't need to decode it—you need to know that it exists, that it expires, and that it should never be shared.

**Row-level security (users can only see their own data):** Just because someone is logged in doesn't mean they should see everything. Row-level security means each database row has an owner, and users can only access rows they own. For example, User A can see User A's orders but not User B's. AI almost never sets this up unless you specifically ask for it—and skipping it is a serious security hole.

**The vibecoder workflow for auth:** Describe your access rules clearly (who can sign up, who can log in, what each user type can see and do) → AI builds the auth layer → you test by logging in as different users and trying to access each other's data → you verify that unauthorized access is blocked → you fix any gaps → ship it. The key difference from other layers: you must test what users CANNOT do, not just what they can.

## Your Toolkit

Your AI coding tool builds the auth system. These tools help you verify it's actually secure.

**AI coding tool (pick one):** Cursor, Lovable, Bolt, Claude Code, Windsurf, or whatever AI- assisted builder you prefer. This is where you'll describe your access rules and let AI build the auth layer.

**An auth provider (Supabase Auth, Clerk, Auth0):** Pre-built authentication services that handle the hard parts—password hashing, session management, email verification—so AI doesn't have to build them from scratch. Using a proven auth provider is always safer than letting AI build a custom one.

**Browser incognito/private windows:** The simplest way to test auth: open your app in two browser windows (one normal, one incognito), log in as two different users, and make sure each user can only see their own data. If User A can see User B's data, your auth is broken.

## Certification Exam Topics

Every exam question is scenario-based. You'll see a situation and need to identify what's right, what's wrong, or what to do next. Here's what gets tested:

**Authentication basics:** Can you identify whether a login system properly verifies identity— checking credentials, creating sessions, and handling incorrect passwords?

**Authorization rules:** Can you spot when a logged-in user has access to data or actions they shouldn't—like seeing another user's account details?

**Password security:** Can you tell whether passwords are being stored securely (hashed, never in plain text) and whether the reset flow is protected from abuse?

**Session management:** Can you identify when sessions don't expire properly—leaving users logged in forever—or when session tokens are stored insecurely?

**Row-level security:** Can you evaluate whether your database enforces that users can only read, update, and delete their own records?

**Protected routes:** Can you identify when pages or API endpoints that should require login are accessible to anyone—even without being logged in?

**Signup validation:** Can you check that your signup flow properly validates email addresses, enforces password requirements, and prevents duplicate accounts?

**Your AI workflow:** Can you describe access rules to AI clearly, test the result by logging in as different users, catch security holes, and iterate to a secure result?

## Common Pitfalls

These are the mistakes vibecoders make most often at this layer. No judgment—they're easy to make. But if you recognize any of them in your own workflow, fix them before sitting for the exam.

Only testing that login works—never testing what happens after login. Your login screen looks great. But did you check that User A can't access User B's data? Did you try accessing protected pages without being logged in? Auth isn't just about the door—it's about every room behind it.

Letting AI build a custom auth system instead of using a proven auth provider. AI can build a login form, but that doesn't mean it handles password hashing, token expiration, session invalidation, and brute-force protection correctly. Supabase Auth, Clerk, and Auth0 exist because auth is too important to improvise.

Storing passwords in plain text or in the database without hashing. If AI creates a users table with a column called "password" that stores readable text, that's a critical security failure.

Passwords must always be hashed—scrambled into an unreadable format that can't be reversed.

Forgetting to add row-level security. Users can log in, but once they're in, they can see everyone's data. This is the most common auth gap AI creates. Always tell AI to enforce that users can only access their own records, and then verify it by testing with multiple accounts.

Sessions that never expire. AI creates a login token that lasts forever. If someone's device is stolen or their credentials are compromised, there's no way to force them out. Sessions should expire and require re-authentication after a reasonable time.

Not protecting the password reset flow. Anyone can request a password reset, the link never expires, and it can be used multiple times. A password reset link should expire quickly (15-30 minutes), work only once, and send a notification to the account owner.

## Self-Assessment Checklist

Before you take the exam, run through these questions. Every "no" is something to work on.

Can you describe your app's access rules to AI clearly—who can sign up, who can log in, and what each user type can see and do?

Have you tested your app by logging in as two different users and confirming each can only see their own data?

Have you tried accessing protected pages and API endpoints without being logged in—and confirmed they're blocked?

Are you using a proven auth provider (Supabase Auth, Clerk, Auth0) instead of letting AI build a custom one from scratch?

Do your sessions expire after a reasonable time, and does logging out actually end the session?

Have you tested the password reset flow—checking that links expire, work only once, and notify the account owner?

Can you explain the difference between authentication (who you are) and authorization (what you're allowed to do)—and identify gaps in either one?

## AI Audit Prompt Template

Copy this prompt into your AI coding tool to get a quick health check on your auth system. It checks the same things the certification exam covers.

> Review my app's authentication and permissions system and check the following. For each one, tell me pass or fail with a specific example:
>
>
>
> Authentication flow: Is the login/signup system using a proven auth provider with proper password hashing, session management, and email verification?
>
>
>
> Authorization enforcement: Does every protected page and API endpoint check that the user is logged in AND authorized to perform the requested action?
>
>
>
> Row-level security: Can users only access their own data—or can a logged-in user see, edit, or delete records belonging to other users?
>
>
>
> Session management: Do sessions expire after a reasonable time, get invalidated on logout, and refresh securely?
>
>
>
> Password reset security: Do reset links expire quickly, work only once, and notify the account owner when their password is changed?
>
>
>
> Protected routes: Are all pages and endpoints that should require authentication actually gated—with no unprotected backdoors?
>
>
>
> Give me an overall score out of 6 and list the top 3 things to fix first.

## What’s Next

Once you've gone through this study guide and can answer "yes" to the self-assessment checklist, you're ready for the Layer 4 certification exam at your target tier.

The best way to prepare: build something real. Pick a project that needs user accounts—even a simple one like a personal dashboard or a shared task list— and go through the full loop. Describe your access rules to AI. Test by logging in as different users. Try to break into places you shouldn't be. Fix every gap. Ship it. Every security hole you catch during building is exactly what the exam tests.

## Certification Pathway

Associate Builder: Pass all 13 layers at Tier 1 Certified Builder: Pass all 13 layers at Tier 1 + Tier 2 MADE Certified: Pass all 39 tier exams + capstone project Each exam requires 80% to pass. You can retake after a 24-hour cooldown. No rush—take the time to build something real first.

———

Ready? Take the [Auth & Permissions Exam →](https://the-faction.mn.co/posts/the-foundation-layer-4-auth-permissions-exam)

---

## Discussion

**Awie Hoh** · 2026-07-01

> This is my own take on Layer 4:
> 
> 4. AUTH & PERMISSIONS
> 
> PURPOSE
> 
> Auth proves who the user is. Permissions decide what they can do. Scope decides which data they can touch.
> 
> PRINCIPLE
> 
> No private page, endpoint, file, record, or action runs until identity, permission, and scope are verified server-side. Auth is the keymaker: it issues the verified identity that the two locks (#2, #8) check — it is not itself a lock.
> 
> DEFINITIONS
> 
> Authentication = who the user is.
> 
> Authorization = what the user is allowed to do.
> 
> Scope = which user, team, project, account, record, or file a permission applies to.
> 
> AUTH PROVIDER
> 
> Use a proven provider (Supabase Auth, Clerk, Auth0) unless there is a reviewed reason not to. Do not let AI invent custom auth unless hashing, sessions, token expiry, reset flows, rate limits, and recovery are all fully reviewed.
> 
> LOGIN
> 
> Verify credentials securely, create a valid session, handle wrong passwords safely. A failed login must not reveal whether the email exists. Repeated failures must be limited (mechanism in Rate Limiting #9).
> 
> SIGNUP
> 
> Validate email, password strength, and required fields. Prevent duplicate accounts. Require email verification when the app depends on a real email.
> 
> PASSWORD SECURITY
> 
> Never store passwords in plain text — use a slow, salted, industry-standard hash (bcrypt/argon2), never a fast or plain hash. Reset links expire quickly, work once, and notify the owner. Reset, email change, and recovery are protected from abuse.
> 
> SESSIONS & REVOCATION
> 
> Verify sessions and tokens server-side. Sessions expire after a reasonable time. Logout ends the session. Expired, missing, invalid, or unclear sessions fail closed. Tokens are stored securely and never exposed through unsafe frontend code. A password change or reset invalidates other active sessions. Removing a user or changing their role takes effect immediately, not at next login.
> 
> SSO / SOCIAL LOGIN
> 
> A third-party login (Google, etc.) proves identity only — the same permission and scope checks still apply. The provider grants identity, never authorization. Every external identity maps to one verified internal identity.
> 
> STRONGER AUTH (per-project)
> 
> Multi-factor auth is per-project, but strongly recommended for admin and other privileged roles.
> 
> PROTECTED ROUTES
> 
> Protected pages and endpoints block logged-out users. A logged-in user does not automatically get all data — User A must never reach User B's private data. Direct URL visits, refreshes, API calls, and network requests all enforce the same rules.
> 
> ROLES & PERMISSIONS
> 
> Define each role clearly (Owner, Admin, Member, Viewer, Guest). For each, define what it can read, create, update, delete, invite, export, manage, and approve. Use least privilege. Deny by default — allow only what is explicitly permitted (Principle 5).
> 
> OWNERSHIP & SCOPE
> 
> Every private record or file has clear ownership or scope (user, team, project, workspace, organization, account). Access must match the correct owner. The scope model is defined here; per-request enforcement and rejection of user-submitted IDs/roles/owner fields happen in Backend/API (#2).
> 
> DATA-LAYER ENFORCEMENT
> 
> Permissions must also be enforced at the data layer, not just the app — backend is the first lock, database/storage rules are the second, both required (Principle 3). The actual RLS and storage policies, and their default-deny tests, are authored in Security & RLS (#8).
> 
> ADMIN ACCESS
> 
> Admin power is explicit, limited, protected, and logged (logging via #12). Admin tools still check identity, permission, and scope. Service-role keys, admin tokens, and privileged credentials stay server-side. User-facing actions never borrow admin power without an access check first.
> 
> ACCESS TEST MATRIX — verify with multiple real accounts
> 
> 1. Logged-out users are blocked from protected pages and endpoints
> 
> 2. Wrong passwords fail safely; email existence not revealed
> 
> 3. Sessions expire; logout ends access
> 
> 4. Password reset links expire and work once
> 
> 5. Password change/reset invalidates other sessions
> 
> 6. Duplicate signup is blocked
> 
> 7. User A cannot access User B's data
> 
> 8. Wrong roles cannot perform restricted actions
> 
> 9. Removed or role-changed users lose access immediately
> 
> 10. RLS blocks direct data access (#8)
> 
> 11. Private files cannot be accessed directly
> 
> AI WORKFLOW
> 
> Describe the access rules to AI: who can sign up and log in, what roles exist, what each role can and cannot do, which data each user can access, which pages and endpoints require login, which records need ownership checks, which files are private, which RLS/storage rules are required, and which allowed/denied cases to test. Then run the access test matrix by logging in as different users.
> 
> SHIP GATE — do not ship unless all are true
> 
> ☐ Login verified; signup validated; passwords slow-salted-hashed
> 
> ☐ Sessions expire; logout works; credential changes revoke other sessions
> 
> ☐ Protected routes block logged-out and cross-user access
> 
> ☐ Roles clear; permissions explicit; least privilege; deny by default
> 
> ☐ Scope enforced; no user-submitted IDs/roles trusted (#2)
> 
> ☐ Data-layer rules exist and default to deny (#8)
> 
> ☐ Admin power limited, server-side, and logged
> 
> ☐ Access test matrix passed with multiple real users

**Erik Howard** · 2026-08-04

> I think the last question is worded poorly.
> 
> **A reset link was used to change a password, then the same link changed it again. The account owner was never notified. How many issues are present?**
> 
> The way this question is written, it does not imply that any significant amount of time was waited before clicking the link again, but rather, it reads as if the user immediately tried the link again. Whether the link expired quickly enough or not is never made clear. The link working twice and the user not being notified are the only clear issues with this scenario without the question including how much time was waited between clicks.

  ↳ **Matt Murphy** · 2026-08-04

  > Erik, great catch, you're right, and the question needs fixing. Thank you.
  > 
  > The intended answer is three: the link should expire on a short clock, it should work exactly once, and the owner should get an email the moment the password changes. But as written, the stem only demonstrates two of those, and the two you named are the right two.
  > 
  > You can't observe an expiry failure in a scenario with no clock in it. If both clicks happened sixty seconds apart, a properly configured 15-minute token behaved exactly as designed so the reuse is a single-use failure, not an expiry failure. Those are independent controls. A token with a perfect 15-minute lifetime can still be redeemed ten times inside that window, and a strict single-use token that stays valid for 30 days is still a standing credential sitting in somebody's inbox. Neither one gets you the other for free.
  > 
  > So the question is asking you to count a defect it never showed you. That's on the question, not on you.
  > 
  > I'm rewriting the stem right now to put the clock back in:
  > 
  > *"A user requests a password reset, waits 48 hours, and the link still works. They use it to change the password, then use the same link again to change it a second time. The account owner is never notified. How many security gaps are present?"*
  > 
  > Three explicit failures, three-gap answer, nothing left to infer.
  > 
  > Also worth saying out loud for anyone else reading this: the reasoning you just did is the actual skill this layer is testing, great work. Reasoning from what the evidence shows, and refusing to count a problem you can't see, is exactly what you need when your AI hands you an auth flow and tells you it's secure. You caught the exam doing the thing the exam is warning you about. Much appreciated.

**Juan Carlos Bandin** · 2026-09-08

> this guides have helped alot ! thanks Matt , im going to copy the result i got from my programmer AI agent 😆 **Just completed the full Layer 4: Auth & Permissions audit for Edimy (our condominium management SaaS for Mexico).**
> 
> Final Score: 6/6 PASS ✅
> 
> We systematically reviewed all critical security pillars:
> 
> **1. Authentication Flow **✅ — Firebase Auth + Google Sign-In properly implemented. Tokens are managed securely by the native SDK with automatic persistence and refresh.
> 
> **2. Authorization Enforcement **✅ — Role-Based Component Trees on frontend (residents literally cannot load admin code) + backend authorization guard that validates every sensitive operation. Impossible to escalate privileges.
> 
> **3. Row-Level Security **✅ — Firestore Rules enforce ownership at the document level. Residents only see their own charges/payments. Admins only access their assigned buildings. No cross-user data leakage possible.
> 
> **4. Session Management **✅ — Tokens expire after 1 hour with automatic refresh every 55 minutes. Logout completely purges session state. No lingering access.
> 
> **5. Password Reset Security **✅ — Firebase Cloud Email Handler sends one-time-use links that expire in 60 minutes. Cannot be reused or exploited.
> 
> **6. Protected Routes **✅ — Zero-Trust architecture. No public dangerous routes. Everything requires authentication + proper role. Tried to find backdoors, found none.
> 
> Why This Matters
> 
> The architecture implements **defense-in-depth** across three layers:
> 
> **Frontend:** Conditional component loading (unauthorized users can't even see the code)
> 
> **Backend:** Authorization validation on every Cloud Function
> 
> **Database:** Granular security rules enforcing data ownership
> 
> Result: it's mathematically impossible for a resident to access another resident's data, or for an admin of Building A to see Building B.
> 
> **No shortcuts. No hardcoded credentials. No unprotected endpoints.** Production-ready for iOS/Android release.
> 
> The study guide was invaluable — especially the emphasis on testing what users *cannot* do, not just what they can. That mindset caught several edge cases early. Highly recommend this framework for anyone shipping SaaS with user accounts.

  ↳ **Matt Murphy** · 2026-09-08

  > Juan, this is exactly what I hoped people would do with the coursework, not just read the Layer 4 material, but turn around and use it to interrogate a real production system. 👊😎
  > 
  > A 6/6 pass across auth, authorization, row-level security, session handling, password reset, and protected routes is a strong result, especially because you’re testing the negative space too: what a user should never be able to do. That’s where a lot of serious vulnerabilities hide.
  > 
  > The one thing I’d challenge you on is the language around “impossible” and “mathematically impossible.” In security, I try not to let myself get that comfortable. 😂 A clean audit means the controls you tested held under the conditions you tested, which is great, but now I’d have a second model or reviewer come in cold and actively try to disprove the result. Different assumptions, different attack paths, same system.
  > 
  > That’s how you turn “my agent says we’re secure” into actual confidence.
  > 
  > But this is a proper win. You took the framework, applied it to Edimy, found the architecture was doing what you intended, and now you have evidence instead of hope. That is the muscle we’re trying to build here.
  > 
  > Keep posting these layer-by-layer results. This is exactly the kind of thing other builders need to see. 🔥


---
_Source: https://the-faction.mn.co/posts/102891677_
