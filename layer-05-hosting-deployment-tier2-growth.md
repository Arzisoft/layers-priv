# Layer 5 of 13 — Hosting & Deployment
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Managing an ongoing deployment workflow with multiple environments and team members
contributing changes, not just deploying once.

**Core goal:** You can manage multiple deployment environments, configure preview deployments
for team review, handle environment variables across staging/production, and keep the deploy
pipeline reliable as the app and team grow.

---

## Key Concepts

**Preview deployments** — Every pushed change gets a temporary live version at a unique URL
the team can click around and approve before it goes to the real site — a dress rehearsal
before opening night.

**Staging vs. production** — Production is what real users see; staging is an identical copy for
testing changes first. Never test on production. Each environment has its own env vars
(different API keys, different DB connections).

**Build optimization** — As the app grows, builds get slower. Understand caching (reuse parts
of previous builds), parallel build steps, and keeping build time reasonable — a 20-minute build
is 20 minutes of waiting every deploy.

**Deploy notifications and monitoring** — Know when deploys succeed, fail, or cause problems:
Slack/email alerts for deploy events, plus a basic check that the live site actually responds
after a deploy.

**Rollbacks** — Instantly revert the live site to the previous working version when a deploy
breaks something preview didn't catch. Know how to do this on your hosting platform before you
need it — when the site is down, every minute counts.

---

## Toolkit (adds to Tier 1)

- **Preview deployment URLs** — built into Vercel/Netlify, every pull request gets its own live preview
- **Environment variable management** — hosting platform dashboard, per-environment variables
- **Deploy hooks and notifications** — Slack/email alerts on deploy success/failure
- **Uptime monitoring (UptimeRobot, Better Stack)** — pings the live site, alerts before customers notice

---

## Common Pitfalls

- API keys/secrets hardcoded in the code instead of environment variables
- Deploying straight to production without testing on preview/staging first — users are not beta testers
- Forgetting SSL, site running on plain http
- Buying a domain but never setting up DNS correctly (DNS propagation can take up to 48 hours — plan ahead)
- No deploy notifications — finding out the site's been down for hours because a customer emailed
- Treating deployment as a one-time event instead of a repeatable workflow

---

## Tier 2 Self-Assessment Checklist

- [ ] Can you deploy from GitHub to a hosting platform and get a live, working URL?
- [ ] Are all API keys/secrets in environment variables, not in the code?
- [ ] Does the live site have SSL working (padlock, https)?
- [ ] Does a custom domain point correctly with no DNS errors?
- [ ] Do you know how to read a build log and diagnose a failed deploy?
- [ ] Could you roll back to the previous version if a deploy broke something?
- [ ] Do you have monitoring that would alert you if the live site went down?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's hosting and deployment setup and check the following. For
each one, tell me pass or fail with a specific example:
Environment variables: Are all secrets stored in the hosting platform's
environment variable settings, with nothing hardcoded in the source code?
SSL and HTTPS: Does the live site load with https and show a valid SSL
certificate with no mixed-content warnings?
Build process: Does the build complete without errors, and are there any
unnecessary steps slowing it down?
Domain configuration: Is the custom domain properly configured with correct
DNS records and no redirect loops?
Deployment pipeline: Is the deploy connected to the GitHub repo with
automatic deploys on push, and is there a preview deployment setup for pull
requests?
Rollback readiness: Can the site be reverted to the previous deploy with one
click or one command, and has this been tested?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
