# Layer 7 of 13 — CI/CD & Version Control
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Running a full CI/CD pipeline as a critical enterprise business system. At Tier 3, it's not just
about catching bugs — it's about security scanning, compliance verification, release
coordination, and ensuring every change that reaches production is fully auditable.

**Core goal:** You can run a full CI/CD pipeline at enterprise scale — with quality gates,
security scanning, release management, compliance-ready audit trails, and multi-environment
deployment strategies.

---

## Key Concepts

**Quality gates (automated go/no-go decisions)** — Automated checkpoints code must pass before
moving to the next stage: tests pass, code coverage above 80%, security scan clean. Any gate
fails, deployment stops — no exceptions, no overrides without an audit trail. These gates
separate "we test sometimes" from "nothing ships without validation."

**Security scanning in the pipeline** — Every commit gets automatically scanned for known
vulnerabilities in dependencies, exposed secrets (accidentally committed API keys), and common
security flaws. Tools like Dependabot, Snyk, and CodeQL run in CI and block merges when they
find problems — not optional at enterprise scale, since one leaked API key can compromise an
entire system.

**Release management (controlled shipping)** — Instead of deploying every commit immediately,
enterprise teams use release branches, version tagging (v2.1.0), and staged rollouts: internal
testing first, then a small percentage of users, then everyone, each stage with its own approval
step — multiple chances to catch problems before they hit all users.

**Monorepo workflows (many projects, one repository)** — Large organizations often keep multiple
related projects in a single Git repository, simplifying dependency management and ensuring
related changes ship together. Requires sophisticated CI configuration so only the parts that
actually changed get tested and deployed, not everything on every commit.

**Audit trails and compliance** — Every merge, deployment, and approval is logged with who did
it, when, and what changed. Required for SOC 2, HIPAA, and other compliance frameworks — when an
auditor asks who approved a specific change, the answer needs to be instant, not a shrug.

---

## Toolkit (adds to Tier 2)

- **Security scanning (Snyk, Dependabot, CodeQL)** — automated vulnerability detection on every commit, catching known security issues in dependencies and your own code before they ship
- **Release management (GitHub Releases, semantic versioning)** — structured version numbering and release notes tracking exactly what changed in each version and who approved it
- **Advanced CI platforms (CircleCI, GitLab CI, BuildKite)** — enterprise CI systems with parallelization, caching, and fine-grained access controls for large teams
- **Policy-as-code (Open Policy Agent, GitHub Rulesets)** — automated enforcement of organizational rules: who can approve what, which tests must pass, what compliance checks are required before deployment

---

## Certification Exam Topics

- **Quality gate design** — You're setting up a CI pipeline for an app that handles financial data. What quality gates do you require before code can reach production?
- **Security incident** — Your CI pipeline flags a critical vulnerability in a widely-used dependency. The fix requires a major version upgrade that might break things. What's your process?
- **Release coordination** — Three teams need to ship features that depend on each other. How do you coordinate the release so nothing breaks?
- **Monorepo CI** — Your monorepo has 5 projects. A developer changed one project, but CI is rebuilding and testing all five. How do you optimize this?
- **Compliance audit** — An auditor asks for a complete record of all production deployments for the last quarter, including who approved each one. Can your pipeline provide this?
- **Rollback strategy** — A release passed all automated tests but users report a subtle bug that only appears under heavy load. What's your rollback plan, and how do you prevent this type of issue in the future?
- **Pipeline security** — A malicious actor could submit a PR that modifies the CI configuration to skip security scans. How do you prevent this?
- **Deployment strategy** — Your app serves 100,000 users. You're shipping a major database migration with a new feature. Describe your deployment strategy to minimize risk.

---

## Common Pitfalls

- Never committing until the feature is "done" — losing days of work if something breaks before the first commit
- Writing commit messages like "fix", "update", or "stuff" that tell you nothing six months later
- Working directly on the main branch instead of using feature branches — one bad commit goes straight to production
- Skipping pull request reviews because you're "in a hurry" — the bug shipped in a hurry takes ten times longer to fix after users find it
- Not setting up any automated tests, then being afraid to change anything
- Ignoring merge conflicts by randomly accepting one version, risking losing someone's work or creating a bug

---

## Tier 3 Self-Assessment Checklist

- [ ] Can you commit your work and push it to GitHub so it's backed up and triggers a deploy?
- [ ] Do your commit messages describe what changed and why, not just "fix" or "update"?
- [ ] Could you revert to last week's version of your app if today's changes broke something critical?
- [ ] If you're working with anyone else (or on multiple features at once), are you using branches?
- [ ] Is there at least one automated check (a test, a linter, a build verification) that runs before code reaches your live app?
- [ ] Do you know how to open a pull request and what the review process looks like?
- [ ] If your deploy failed right now, would you know how to read the error log and figure out what went wrong?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my project's version control and CI/CD setup and check the following.
For each one, tell me pass or fail with a specific example:
Commit hygiene: Are commits small, frequent, and descriptively messaged—or
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

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 7 certification exam at your target tier.

The best way to prepare: use version control on a real project. Start a feature branch, make
some changes, commit with descriptive messages, open a pull request, and merge it. Break
something on purpose, then revert. Set up one automated test — even just "does the app build
without errors?" The exam tests whether you've actually done these things, not whether you can
recite definitions.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
