# Layer 8 of 13 — Security & RLS
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Governing security at enterprise scale. At Tier 3, security is a system-wide concern:
compliance requirements, coordinating security across multiple teams, and having a plan for
when (not if) something goes wrong.

**Core goal:** You can govern security at enterprise scale — implementing compliance
frameworks, managing security across multiple teams and services, running penetration tests,
and maintaining an incident response plan for when things go wrong.

---

## Key Concepts

**Compliance frameworks (SOC 2, GDPR, HIPAA)** — Formal standards for how data must be
handled. SOC 2 proves security practices are solid; GDPR (European privacy law) gives users the
right to see, export, and delete their data; HIPAA protects health information. At enterprise
scale, customers and partners ask for proof of compliance before signing contracts — you don't
implement these alone, but you need to know what they require and verify your app meets them.

**Penetration testing (hiring someone to try to break in)** — A security professional
deliberately tries to hack your app, with permission, to find vulnerabilities before real
attackers do. At Tier 3, this should happen regularly; you need to understand pen test reports,
prioritize what to fix, and direct your AI tools to implement the fixes.

**Secrets rotation and vault management** — At enterprise scale, secrets don't just live in
environment variables — a vault (HashiCorp Vault, AWS Secrets Manager) automatically changes
passwords on a schedule, so a leaked secret stops working soon anyway.

**Zero-trust architecture** — The old approach was "trust everything inside our network." Zero
trust means verify every request, every time, no matter where it comes from — every service
checks identity and permissions independently, like every room in a building having its own
lock and ID check even after you got through the front door.

**Security incident response** — When (not if) a security incident happens at scale, you need a
documented plan: who gets notified, how you contain the damage, how you investigate, and how
you prevent it from happening again. Not optional at enterprise scale — auditors and customers
will ask to see it.

---

## Toolkit (adds to Tier 2)

- **HashiCorp Vault or AWS Secrets Manager** — enterprise-grade secrets storage with automatic rotation, so a leaked secret has a short shelf life
- **Snyk or Dependabot** — automated tools that scan code dependencies for known security vulnerabilities and alert when updates are needed
- **Security audit platforms (Vanta, Drata)** — continuously monitor the app against compliance frameworks like SOC 2 and generate the reports auditors need
- **WAF (Web Application Firewall)** — a security layer in front of the app that blocks known attack patterns before they reach the code

---

## Certification Exam Topics

- **Compliance requirements** — A potential enterprise client asks if your app is SOC 2 compliant. What does this mean, and what evidence do you need to provide?
- **Penetration testing** — A pen test report shows that an attacker could access admin functions by modifying a URL parameter. What category of vulnerability is this, and how do you prioritize the fix?
- **Secrets management** — Your team discovers that a database credential was accidentally committed to your code repository three months ago. What's your immediate response plan?
- **Zero-trust architecture** — Two internal services communicate with each other, trusting each other automatically because they're on the same network. What's wrong with this approach, and what should change?
- **GDPR compliance** — A European user requests that all their data be deleted from your system. What needs to happen across your database, backups, and third-party services?
- **Multi-team security governance** — Three different teams are building features that handle user data. How do you ensure consistent security standards across all three teams?
- **Incident response** — You discover that user data may have been accessed by an unauthorized party. Walk through the first four steps of your incident response plan.
- **Dependency vulnerabilities** — A security scanner flags a critical vulnerability in a library your AI tool used to build a core feature. What's your process for evaluating and addressing this?

---

## Common Pitfalls

- Forgetting to enable RLS on new database tables — Supabase creates tables with RLS off by default; every table with user data needs RLS turned on and a policy written, or every user can see every row
- Putting API keys, database passwords, or other secrets directly in code instead of environment variables
- Only checking permissions on the frontend — hiding a button doesn't block the action, since anyone can call the API directly; security must be enforced server-side
- Skipping input sanitization because "nobody would do that" — automated bots scan every app on the internet for common vulnerabilities without needing a reason
- Using HTTP instead of HTTPS, or not checking whether HTTPS is actually active on the deployed app
- Never testing security by trying to break it yourself — log in as one user and try to access another user's data, try weird characters in every input field

---

## Tier 3 Self-Assessment Checklist

- [ ] Can you log in as User A and confirm you cannot see User B's data anywhere in the app?
- [ ] Have you verified that RLS is enabled on every database table that contains user data?
- [ ] Are all secrets (API keys, database passwords) stored in environment variables, not in your code?
- [ ] Does your app use HTTPS for every connection, with no HTTP fallbacks?
- [ ] Have you tested your input fields by typing special characters, script tags, and SQL-like commands to see what happens?
- [ ] Can you explain the difference between authentication (who you are) and authorization (what you're allowed to do)?
- [ ] Have you checked your app's CORS settings to make sure only your domains can access your API?

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

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 8 certification exam at your target tier.

The best way to prepare: take a real app you've built and try to break its security. Log in as
one user and try to see another's data. Put weird characters in every text field. Check that
your secrets aren't in your code. Every vulnerability you find and fix is proof of work, and
exactly what the exam tests.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
