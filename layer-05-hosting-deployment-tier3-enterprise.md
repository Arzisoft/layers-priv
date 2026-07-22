# Layer 5 of 13 — Hosting & Deployment
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Running a deployment operation at enterprise scale. At Tier 3, deployment is a critical business
operation — downtime means lost revenue, broken trust, and potentially legal consequences. The
job is to make deployments as safe and reliable as possible.

**Core goal:** You can run a deployment operation at enterprise scale — zero-downtime deploys,
multi-region hosting, infrastructure-as-code, automated rollback triggers, and compliance-ready
deployment audit trails.

---

## Key Concepts

**Zero-downtime deployments** — Users should never see a blank page or an error while a new
version switches in. Blue-green deployment is one strategy: two identical environments (blue
and green), the live site points to blue, you deploy to green, verify it works, then switch
traffic over — switch back instantly if something's wrong.

**Multi-region hosting** — If users are all over the world, hosting in one location means some
experience slow load times. Multi-region hosting puts copies of the app in data centers across
multiple continents, so a user in Tokyo connects to a server in Asia, not one in Virginia — edge
deployment.

**Infrastructure-as-code (IaC)** — Instead of clicking through dashboards to set up hosting,
everything is defined in configuration files: server settings, environment variables, domain
rules, scaling limits. Infrastructure becomes version-controlled, reviewable, and reproducible —
run the config file instead of remembering 47 manual steps.

**Automated rollback triggers** — Instead of waiting for a human to notice something's broken,
automated rules revert the deploy: if the error rate spikes above 5% within two minutes of a
deploy, automatically revert to the previous version. Keeps the app running even while asleep.

**Compliance and audit trails** — Enterprise deployments need records: who deployed what,
when, and what changed. Not bureaucracy, operational confidence — when something goes wrong
at 2am, the audit trail says exactly what changed and who approved it.

---

## Toolkit (adds to Tier 2)

- **Infrastructure-as-code tools (Terraform, Pulumi, SST)** — define the hosting setup in config files instead of clicking through dashboards; infrastructure becomes versioned and repeatable
- **Multi-region platforms (Fly.io, Cloudflare Workers, AWS CloudFront)** — host the app across multiple geographic locations so users everywhere get fast load times
- **Advanced monitoring (Datadog, Grafana)** — dashboards and alerts showing real-time deploy health, error rates, and performance across all regions
- **Feature flags (LaunchDarkly, Unleash)** — turn features on and off without redeploying; if a new feature causes problems, flip the switch instead of rolling back the entire deploy

---

## Certification Exam Topics

- **Zero-downtime strategy** — You need to deploy a major update to an app with 50,000 active users. Describe how you'd do this without any user seeing an error page.
- **Multi-region decisions** — Your analytics show 40% of your users are in Europe but your app is only hosted in the US. What's your deployment strategy?
- **Infrastructure-as-code** — A new developer joins and needs to set up a complete staging environment. How does IaC make this faster and safer than doing it manually?
- **Automated rollback** — You deployed at 11pm. The error rate jumped from 0.1% to 8% within 90 seconds. What should your system have done automatically?
- **Compliance requirements** — An enterprise client requires a complete record of every deployment for the last 12 months. How do you provide this?
- **Feature flag strategy** — You're launching a major new feature but aren't confident it works at scale. How do you deploy it safely to a small percentage of users first?
- **Disaster recovery** — Your primary hosting region goes offline. What should happen automatically, and what's the maximum acceptable downtime?
- **Cost management** — Your multi-region hosting bill tripled last quarter. How do you evaluate whether the spend is justified, and where do you look for savings?

---

## Common Pitfalls

- Putting API keys, database passwords, or secrets directly in code instead of environment variables
- Deploying directly to production without testing on a preview or staging environment first
- Forgetting to set up SSL and leaving the site running on http
- Buying a domain but never setting up DNS correctly, then wondering why the custom domain shows an error page (DNS propagation can take up to 48 hours)
- Never setting up deploy notifications, then finding out the site's been down for hours because a customer emailed
- Treating deployment as a one-time event instead of an ongoing, repeatable process

---

## Tier 3 Self-Assessment Checklist

- [ ] Can you deploy your app from your GitHub repo to a hosting platform and get a live, working URL?
- [ ] Are all of your API keys and secrets stored in environment variables on your hosting platform, not in your code?
- [ ] Does your live site have SSL working (padlock icon, https in the URL)?
- [ ] If you have a custom domain, does it point to your hosting platform correctly with no DNS errors?
- [ ] Do you know how to read a build log and figure out why a deploy failed?
- [ ] Could you roll back to the previous version of your app if a deploy broke something?
- [ ] Do you have some form of monitoring that would alert you if your live site went down?

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

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 5 certification exam at your target tier.

The best way to prepare: deploy something real. Take one of your projects, put it on Vercel or
Netlify, connect a custom domain, and go through the entire process. Pay attention to every
error message, every DNS delay, every environment variable you had to set. Those real-world
experiences are exactly what the exam tests.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
