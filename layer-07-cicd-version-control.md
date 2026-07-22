# Layer 7 of 13 — CI/CD & Version Control
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Shipping Code Safely, Every Time*

---

## What It Covers

Git commits, branches, repositories, CI/CD automation, GitHub deployments, and the rule to always commit before big AI changes.

**Core goal:** You can manage code safely with version control and automate deployment so every push to main goes live — without breaking things.

---

## Key Concepts

**Git** — A system that tracks every change to your code. Like a time machine: you can see what changed, when, and by whom. If something breaks, you can go back.

**Commits** — Snapshots of your code at a point in time. Write meaningful messages ("add user profile endpoint", not "fix stuff"). Small, frequent commits beat large infrequent ones.

**Branches** — Parallel copies of your code for isolated work. Main/master = stable production code. Feature branches = work in progress. Never develop directly on main.

**Repositories (repos)** — Where your code lives. GitHub, GitLab, Bitbucket. Private = only invited people can see. Public = anyone can. For client work: always private.

**CI (Continuous Integration)** — Every push runs automated checks: build succeeds, tests pass. Catches broken code before it ships.

**CD (Continuous Deployment)** — Every successful push to main automatically deploys to production. No manual deploy steps. Push = live.

**The golden rule: commit before AI changes** — Before asking AI to make large changes, commit the current state. If AI breaks things, you can revert cleanly. This is the single most important habit for vibecoders.

---

## Toolkit

- **GitHub** — standard for version control + CI/CD integration
- **Vercel / Netlify** — auto-deploy on push to main
- **GitHub Actions** — custom CI/CD workflows (run tests, lint, deploy)
- **Conventional commits** — standard commit message format for readability

---

## Common Pitfalls

- Working directly on the main branch
- Committing environment files (`.env`) to GitHub
- Never committing during a long session — losing all progress if something crashes
- Not reading CI output when a build fails
- Force-pushing to main (rewrites history, breaks teammates)
- Not having any tests, so CI/CD just deploys broken code faster

---

## Tier 1 Self-Assessment Checklist

- [ ] Is your code in a git repository with regular commits?
- [ ] Do you use feature branches rather than developing on main?
- [ ] Is `.env` in `.gitignore` so secrets never reach GitHub?
- [ ] Does every push to main trigger an automatic build + deploy?
- [ ] Do you commit before every major AI-assisted code change?
- [ ] Can you roll back to a previous commit in under 5 minutes?
- [ ] Do you read CI/CD output and fix failures before they accumulate?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my CI/CD and version control setup. Pass or fail with a specific example:
1. Branch strategy: Is there a clear branching strategy (main = stable, features on branches)?
2. Secrets in git: Does the repo contain any .env files, hardcoded keys, or tokens?
3. CI pipeline: Does every push to main run a build check and tests before deploying?
4. Deployment automation: Is the deploy-on-push pipeline active and working?
5. Commit quality: Are commit messages descriptive, or all "fix" / "update"?
6. Rollback: Is there a clear way to revert a bad deployment using git or the hosting platform?

Give me a score out of 6 and the top 3 things to fix first.
```
