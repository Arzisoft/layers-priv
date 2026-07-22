# Layer 7 of 13 — CI/CD & Version Control
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Managing team workflows once more than one person (or one person on multiple features) is
working on the project at the same time, without breaking each other's work.

**Core goal:** You can manage branches, pull requests, and code reviews; set up automated
tests that run on every change; and catch problems before they reach live users.

---

## Key Concepts

**Branches** — A copy of the project to change without touching the main version — a
photocopy to mark up, experiment on, and throw away if needed. Merge back in once the
feature is ready.

**Pull requests (PRs)** — A formal request to merge a branch into the main project. Shows
exactly what changed, lets teammates review/comment, and records every decision. The quality
gate: nothing goes in unreviewed.

**Automated testing (CI)** — Tests run automatically on every push/PR to check nothing's
broken. Failing tests block the merge — a bouncer at the door, no untested code gets in.

**Merge conflicts** — When two people change the same file, Git doesn't know which version to
keep. Normal and fixable: Git shows both versions side by side, you pick what to keep (AI tools
can often resolve these too).

**Continuous Deployment (CD)** — Merged + tests-passing code deploys automatically. No
manual deploy step. Pipeline: commit → tests → deploy.

---

## Toolkit (adds to Tier 1)

- **GitHub Pull Requests** — the review/approval interface where code quality happens
- **GitHub Actions** — automation workflows (tests, formatting, build) triggered on every push/PR
- **Automated test frameworks (Vitest, Playwright)** — unit tests (Vitest) and end-to-end tests (Playwright)
- **Branch protection rules** — no direct pushes to main; all changes need a PR with passing tests + a review

---

## Common Pitfalls

- Not committing until a feature is "done" — losing days of work if something breaks midway
- Vague commit messages ("fix", "update", "stuff") that tell future-you nothing
- Working directly on main instead of feature branches — one bad commit goes straight to production
- Skipping PR review because you're in a hurry — a rushed bug takes ten times longer to fix once users find it
- No automated tests, so you're afraid to change anything for fear of breaking it
- Resolving merge conflicts by randomly accepting one version without understanding both changes

---

## Tier 2 Self-Assessment Checklist

- [ ] Can you commit and push so work is backed up and triggers a deploy?
- [ ] Do commit messages describe what changed and why, not just "fix"?
- [ ] Could you revert to last week's version if today's changes broke something critical?
- [ ] Are you using branches when working on multiple things/with others?
- [ ] Is there at least one automated check (test/linter/build verification) before code reaches production?
- [ ] Do you know how to open a PR and what the review process looks like?
- [ ] If a deploy failed right now, would you know how to read the error log?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my project's version control and CI/CD setup and check the following.
For each one, tell me pass or fail with a specific example:
Commit hygiene: Are commits small, frequent, and descriptively messaged, or
are they large, infrequent dumps with vague labels?
Branch strategy: Is the project using feature branches and pull requests, or
is everything committed directly to the main branch?
Automated checks: Are there any automated tests, linting, or build
verifications running on pull requests or pushes?
Deployment pipeline: Is the deploy connected to the repository with automatic
deployment on merge, and is there a clear path from commit to production?
Security: Are there any secrets, API keys, or credentials committed in the
codebase or Git history?
Recovery readiness: Can the project be reverted to a previous version
quickly, and has this been tested?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
