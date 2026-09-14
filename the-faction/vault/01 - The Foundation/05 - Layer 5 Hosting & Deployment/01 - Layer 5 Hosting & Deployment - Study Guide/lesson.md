---
course: "The Foundation"
module: "Layer 5: Hosting & Deployment"
lesson: "Layer 5: Hosting & Deployment — Study Guide"
type: "course_lesson"
post_id: 102891756
space_id: 23777123
source: "https://the-faction.mn.co/posts/102891756"
updated: "2026-08-10T17:50:13Z"
---

# Layer 5: Hosting & Deployment — Study Guide

## Layer 5: Hosting & Deployment

Getting Your App Live and Keeping It Running

This is the study guide. Everything for Hosting & Deployment is on this page — there's nothing to download.

## What This Study Guide Covers

This study guide covers Layer 5: Hosting & Deployment—getting your app live on the internet so other people can actually use it. Right now your app works on your laptop. That's great for building and testing, but your customers can't see it. Hosting is renting space on a computer that's always connected to the internet. Deployment is the process of sending your app to that computer so anyone with the link can open it.

You're not going to manage servers by hand. You're going to use platforms like Vercel, Netlify, or Railway that handle the hard parts for you—you connect your project, click deploy (or it deploys automatically), and your app is live. Your job is to understand what these platforms do, pick the right one for your project, and know how to fix things when a deploy doesn't go as planned.

This study guide walks you through the concepts, tools, and checkpoints you need to pass the Hosting & Deployment certification exam.

Start at Tier 1. You can always come back for the rest.

## Why It Matters

An app that only runs on your laptop isn't a product—it's a homework assignment. The whole point of building something is getting it into the hands of people who need it. Hosting and deployment is the bridge between "I built a thing" and "people are using my thing." Until you cross that bridge, nothing else matters.

Here's the good news: modern hosting platforms have made this dramatically easier than it used to be. The bad news: there are still real decisions to make—like where your environment variables go (hint: never in your code), how to set up a custom domain, and what to do when a deploy breaks at 2am. AI tools can help you deploy, but they won't warn you about the gotchas.

This study guide teaches you what to watch for.

## CERTIFICATION GOAL

You can deploy your app to a hosting platform, connect a custom domain, confirm SSL is working, set environment variables safely, and verify your app loads correctly for anyone on the internet.

## What You Need to Know

You don't need to manage servers. You need to understand how your app gets from your laptop to a live URL—and what can go wrong along the way.

**How hosting platforms work:** Platforms like Vercel, Netlify, and Railway connect to your code (usually on GitHub) and automatically build and publish your app every time you push an update. Think of it like Dropbox for your app—you save a file, and it shows up everywhere. The platform handles the server, the internet connection, and keeping things running.

**What a domain name is and how DNS works:** A domain name is your app's address on the internet—like myapp.com instead of some random string of numbers. DNS (Domain Name System) is like the phone book that translates your domain name into the actual server address.

You buy a domain, point it to your hosting platform, and your app gets a real, professional address.

**What SSL certificates do:** SSL is what puts the padlock icon in the browser and makes your URL start with https instead of http. It encrypts the connection between your user and your app so nobody can spy on the data in between. Most hosting platforms set this up automatically— your job is to verify it's working.

**Where environment variables go:** Environment variables are secret settings your app needs —like API keys, database passwords, or payment processor credentials. They NEVER go in your code (anyone could read them). They go in your hosting platform's settings panel, where they're encrypted and only your app can access them.

**What a build process does:** When you deploy, the hosting platform runs a build step that converts your code into something browsers can understand. Sometimes the build fails—usually because of a missing dependency or a typo. You need to know how to read the build log (the error messages) to figure out what went wrong.

## Your Toolkit

Your hosting platform does the heavy lifting. Everything else supports getting your app live and keeping it running.

**Vercel or Netlify:** The two most popular hosting platforms for modern web apps. They connect to your GitHub repo, build your app automatically, and give you a live URL in minutes. Vercel is especially good if your AI tool built your app with Next.js.

**A domain registrar (Namecheap, Google Domains, Cloudflare):** Where you buy your custom domain name. You'll update the DNS settings there to point to your hosting platform.

**GitHub:** Where your code lives. Your hosting platform watches your GitHub repo and redeploys every time you push an update. If you're not using GitHub yet, Layer 7 covers this in detail.

## Certification Exam Topics

Every exam question is scenario-based. You'll see a real situation and need to identify what's right, what's wrong, or what to do next.

**Deployment basics:** Your app works on your laptop but shows a blank white page after deploying. What are the first three things you check?

**Environment variables:** Your app works locally but crashes on the live site with 'API key not found.' Where did you forget to put the key, and where should it go?

**Domain setup:** You bought a custom domain but visitors still see 'DNS not found.' Can you identify what DNS records need to be configured?

**SSL verification:** A user reports that your site shows a 'Not Secure' warning. What does this mean and how do you fix it?

**Build failures:** Your deploy failed and the build log says 'Module not found.' Can you explain what this means in plain language and what to do?

**Platform selection:** You have a simple marketing site and a complex web app with a database.

Should they be on the same hosting platform? Why or why not?

**Live site testing:** Your app deployed successfully but a page that works locally returns a 404 error on the live site. What could cause this?

**Environment safety:** A teammate committed an API key directly into the code on GitHub.

What's the risk, and what should you do immediately?

## Common Pitfalls

These are the mistakes vibecoders make most often with hosting and deployment. No judgment —they're easy to make. But if you recognize any of them in your own workflow, fix them before sitting for the exam.

Putting API keys, database passwords, or secrets directly in your code. Anyone who can see your code can steal your credentials. Environment variables exist for exactly this reason—use them.

Deploying directly to production without testing on a preview or staging environment first. Your users are not your beta testers. Break things in staging, not in front of customers.

Forgetting to set up SSL and leaving your site running on http. Browsers show a scary 'Not Secure' warning, users don't trust it, and their data is exposed in transit.

Buying a domain but never setting up DNS correctly, then wondering why the custom domain shows an error page. DNS changes take time to spread across the internet (up to 48 hours).

Plan ahead.

Never setting up deploy notifications, then finding out your site has been down for hours because a customer emailed you. Automated monitoring is not optional.

Treating deployment as a one-time event instead of an ongoing process. Your app will change constantly. Build a deployment workflow you can repeat reliably, not one you barely survived once.

## Self-Assessment Checklist

Before you take the exam, run through these questions. Every "no" is something to work on.

Can you deploy your app from your GitHub repo to a hosting platform and get a live, working URL?

Are all of your API keys and secrets stored in environment variables on your hosting platform— not in your code?

Does your live site have SSL working (padlock icon, https in the URL)?

If you have a custom domain, does it point to your hosting platform correctly with no DNS errors?

Do you know how to read a build log and figure out why a deploy failed?

Could you roll back to the previous version of your app if a deploy broke something?

Do you have some form of monitoring that would alert you if your live site went down?

## AI Audit Prompt Template

Copy this prompt into your AI coding tool to get a quick health check on your hosting and deployment setup. It checks the same things the certification exam covers.

> Review my app's hosting and deployment setup and check the following. For each one, tell me pass or fail with a specific example:
>
>
>
> Environment variables: Are all secrets stored in the hosting platform's environment variable settings, with nothing hardcoded in the source code?
>
>
>
> SSL and HTTPS: Does the live site load with https and show a valid SSL certificate with no mixed-content warnings?
>
>
>
> Build process: Does the build complete without errors, and are there any unnecessary steps slowing it down?
>
>
>
> Domain configuration: Is the custom domain properly configured with correct DNS records and no redirect loops?
>
>
>
> Deployment pipeline: Is the deploy connected to the GitHub repo with automatic deploys on push, and is there a preview deployment setup for pull requests?
>
>
>
> Rollback readiness: Can the site be reverted to the previous deploy with one click or one command, and has this been tested?
>
>
>
> Give me an overall score out of 6 and list the top 3 things to fix first.

## What’s Next

Once you've gone through this study guide and can answer "yes" to the self-assessment checklist, you're ready for the Layer 5 certification exam at your target tier.

The best way to prepare: deploy something real. Take one of your projects, put it on Vercel or Netlify, connect a custom domain, and go through the entire process. Pay attention to every error message, every DNS delay, every environment variable you had to set. Those real-world experiences are exactly what the exam tests.

## Certification Pathway

Associate Builder: Pass all 13 layers at Tier 1 Certified Builder: Pass all 13 layers at Tier 1 + Tier 2 MADE Certified: Pass all 39 tier exams + capstone project Each exam requires 80% to pass. You can retake after a 24-hour cooldown. No rush—take the time to build something real first.

———

Ready? Take the [Hosting & Deployment Exam →](https://the-faction.mn.co/posts/the-foundation-layer-5-hosting-deployment-exam)

---

## Discussion

**Awie Hoh** · 2026-07-01

> This is my own take on Layer 5:
> 
> 5. HOSTING & DEPLOYMENT
> 
> PURPOSE
> 
> Hosting runs the app. Deployment controls what code, settings, domains, secrets, and releases reach users.
> 
> PRINCIPLE
> 
> Production must be deliberate, tested, secure, monitored, and reversible.
> 
> ENVIRONMENTS
> 
> Separate local, preview, staging, and production. Never use production data, secrets, or services in unsafe non-production environments. Each environment has its own database, storage, auth settings, domain, webhook URLs, and environment variables.
> 
> RELEASE & ROLLBACK
> 
> Deploy from version control, never random local changes. Test preview or staging before production. Every production deploy is tied to a commit, build, or release. Failed checks block the deploy. Every release has a rollback path, and a deploy that fails its post-deploy health check rolls back automatically where the platform supports it. (The automated pipeline that runs all this is CI/CD #7.)
> 
> MIGRATIONS & DEPLOY ORDER
> 
> Sequence schema migrations and code deploys so neither breaks the other: migrations stay backward-compatible, run in a safe order, and never strand a rollback. (Migrations themselves are controlled in Database & Storage #3.)
> 
> REPRODUCIBLE BUILDS
> 
> Commit the dependency lockfile so the build that passed staging is identical in production. No silent dependency drift between environments.
> 
> ENVIRONMENT VARIABLES
> 
> Local .env files do not automatically exist on the live site. If production says "API key not found," add the key to the hosting platform's environment variables for the correct environment. Secrets live in private server-side variables. Only intentionally public frontend variables may reach the browser. Keep public and private clearly separated.
> 
> SECRETS
> 
> Never hardcode API keys, database passwords, private keys, service-role keys, admin tokens, or credentials in code. If a secret is committed to GitHub, treat it as leaked: immediately revoke it, replace it, remove it from code, update environment variables, and review access logs.
> 
> DOMAIN & DNS
> 
> A custom domain points to the host through correct DNS records: A record for root domains, CNAME for subdomains, TXT for verification when required. DNS changes can take time to propagate.
> 
> SSL / HTTPS
> 
> Production must use HTTPS. "Not Secure" means HTTPS is missing, broken, expired, misconfigured, or the page loads unsafe HTTP assets. Fix DNS, enable or renew SSL, force HTTPS, and remove mixed-content HTTP assets.
> 
> PLATFORM FIT
> 
> Choose hosting by app need. A marketing site can use static hosting; a full web app may need backend compute, database, storage, auth, background jobs, scheduled tasks, and logs. Use one platform if it supports the app cleanly; split platforms when it improves security, reliability, cost, or maintainability.
> 
> CONFIGURATION
> 
> Variables must match the target environment. Wrong config must fail safely — never connect to the wrong database, storage, auth provider, payment system, or webhook. Domains, redirects, callback URLs, auth URLs, webhook URLs, and allowed origins must all match the correct environment.
> 
> EXPOSURE
> 
> Never expose debug tools, test routes, admin panels, logs, internal dashboards, public source maps, stack traces, or development errors. Source maps may be uploaded privately to error tracking (#12). Preview and staging must never expose private production data.
> 
> MONITORING
> 
> Deployment is not one-time. Uptime monitoring, deploy notifications, error alerts, and basic health checks must exist. A broken live site must be discovered by monitoring, not by users. (Error tracking detail in #12; uptime targets and recovery in #13.)
> 
> COMMON DEPLOY FAILURES (debugging aid, not law)
> 
> - Blank page after deploy: check build logs, env vars, browser console, network requests, routing, and missing assets.
> 
> - 404 in production but works locally: route not deployed, wrong file path or route name, host not configured for client-side routing, wrong build output directory, domain points to the wrong project, or missing env vars/data.
> 
> - "Module not found" at build: package installed? file exists? import path correct? filename casing matches? file committed?
> 
> - "API key not found": the variable is missing on the host for that environment.
> 
> - "Not Secure" or mixed content: HTTPS missing/expired/misconfigured, or the page loads HTTP assets — fix DNS, enable/renew SSL, force HTTPS, remove mixed content.
> 
> POST-DEPLOY VERIFICATION
> 
> After deploy, confirm: the site loads, HTTPS works, the domain works, login works, protected routes are blocked, key pages do not 404, API calls work, env vars are present, forms submit correctly, private data is not exposed, and critical user flows work.
> 
> AI WORKFLOW
> 
> When asking AI to set up hosting or deployment, specify: hosting platform, environment names, build command, start command, output directory, required env vars, public vs private variables, domain settings, DNS requirements, SSL requirement, auth callback URLs, webhook URLs, monitoring requirement, rollback plan, and post-deploy checks.
> 
> SHIP GATE — do not ship unless all are true
> 
> ☐ Environments separated; no prod data/secrets in non-prod
> 
> ☐ Deploys come from version control; failed checks block release (#7)
> 
> ☐ Migrations sequenced with deploys; rollback stays safe (#3)
> 
> ☐ Builds reproducible; lockfile committed
> 
> ☐ Secrets protected; none in code; leaked secrets rotated
> 
> ☐ DNS works; HTTPS enforced; no mixed content
> 
> ☐ Config matches environment; wrong config fails safe
> 
> ☐ Debug tools, admin panels, and public source maps hidden
> 
> ☐ Monitoring and rollback exist; failed health checks trigger auto-rollback where supported, otherwise a documented manual rollback
> 
> ☐ Post-deploy verification passed on the live site

**Bene Richi** · 2026-07-30

> Hey Hey [Matt Murphy](https://the-faction.mn.co/members/39706849)
> 
> ![blush emoji](https://cdn.jsdelivr.net/npm/emoji-datasource-apple/img/apple/64/1f60a.png)
> 
> Question 25.
> 
> The question does not tell us how much time passed between the two password changes. Both uses could have occurred within the intended 15–30 minute validity period. Therefore, the scenario only clearly proves two issues: the reset link was reusable, and the account owner was not notified. The expiration time cannot be counted as a third issue without additional information.
> 
> Or is it just me?
> 
> ![dizzy_face emoji](https://cdn.jsdelivr.net/npm/emoji-datasource-apple/img/apple/64/1f635.png)

  ↳ **Matt Murphy** · 2026-07-30

  > It is just you….but for a good reason!
  > 
  > First off, it's a great question and I appreciate the critical thinking. You're actually applying forensic analysis to a security architecture question, which tells me you're thinking at a higher level than the question requires.
  > 
  > You're right that the scenario alone doesn't prove the expiration failed. But the question is asking how many security controls SHOULD be present in a properly designed password reset flow, not how many you can prove broke from this one incident.
  > 
  > OWASP and NIST treat these as three independent, required controls: time-based expiration, single-use invalidation, and account owner notification. They're defense-in-depth layers. Each one should exist independently of the others. The correct answer is three because all three controls must be present in production, regardless of whether this specific scenario proves each one failed.
  > 
  > Your reasoning would be correct if the question asked 'how many issues can you confirm from this scenario.' It didn't. It asked how many issues are present in the system. Keep pushing back on questions though. That's exactly the kind of thinking that makes a strong security engineer. 👊😎


---
_Source: https://the-faction.mn.co/posts/102891756_
