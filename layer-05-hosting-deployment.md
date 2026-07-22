# Layer 5 of 13 — Hosting & Deployment
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Getting Your App on the Internet*

---

## What It Covers

Hosting platforms, domain/DNS/SSL, environment variables, build processes, and rollback readiness.

**Core goal:** You can deploy your app to the internet with a real domain, HTTPS, and a working environment — and know how to roll back if a deploy breaks things.

---

## Key Concepts

**Hosting platforms** — Where your code runs in the cloud. For solopreneurs: Vercel, Netlify, Railway, Render. For EC2/server-based: AWS, DigitalOcean. Platform-as-a-service (PaaS) handles the server for you; you just push code.

**Domain + DNS** — Your domain (yourapp.com) is registered at a registrar (Namecheap, Google Domains). DNS records point the domain to your hosting platform's servers. A records, CNAMEs — AI can generate the right DNS config; you paste it in.

**SSL/HTTPS** — HTTPS encrypts traffic between user and server. Every modern hosting platform gives you a free SSL certificate via Let's Encrypt. Verify the padlock is showing before you launch.

**Environment variables** — Secrets (API keys, DB passwords) must NEVER be in your code. They live in a `.env` file locally, and in your hosting platform's environment config for production. AI sometimes hardcodes them — always check.

**Build process** — Source code → compiled, optimized app ready to serve. Vercel/Netlify run this automatically on every push. Know what your build command is (`npm run build`) and how to read build logs when it fails.

**Staging vs production** — Two environments. Staging = test before anyone sees it. Production = live users. Deploy to staging first, verify it works, then promote to production.

**Rollback** — If a deployment breaks things, you need to undo it in under 5 minutes. Vercel/Netlify have one-click rollback. On EC2: previous release folder + symlink swap.

---

## Toolkit

- **Vercel / Netlify / Railway** — auto-deploy from GitHub, one-click rollback
- **GitHub** — version control + deployment trigger
- **`.env` / platform env config** — secrets management
- **Build logs** — first place to look when a deploy fails

---

## Common Pitfalls

- Committing `.env` files to GitHub (instant security incident)
- Only having one environment (no staging = testing in production)
- Not knowing how to roll back after a bad deploy
- Ignoring build warnings until they become errors
- Using different environment variable names in staging vs production
- Not verifying HTTPS is active on the live domain

---

## Tier 1 Self-Assessment Checklist

- [ ] Is your app live on a custom domain with HTTPS?
- [ ] Are all secrets in environment variables, not in code?
- [ ] Is `.env` in your `.gitignore`?
- [ ] Do you have a staging environment separate from production?
- [ ] Can you roll back a bad deployment in under 5 minutes?
- [ ] Do you know how to read build logs and find errors?
- [ ] Are prod and staging environment variables configured separately?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's hosting and deployment setup. Pass or fail with a specific example:
1. Secrets: Are there any hardcoded API keys, passwords, or tokens in the source code?
2. HTTPS: Is SSL active on all domains, with no mixed-content HTTP resources?
3. Environment separation: Are staging and production clearly separated with different env configs?
4. Rollback: Is there a tested rollback procedure for bad deploys?
5. Build process: Are there unresolved build warnings that could become failures?
6. CI/CD: Does every push to main trigger a build + deploy automatically?

Give me a score out of 6 and the top 3 things to fix first.
```
