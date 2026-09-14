---
course: "The Foundation"
module: "Layer 7: CI/CD & Version Control"
lesson: "Layer 7: CI/CD & Version Control — Study Guide"
type: "course_lesson"
post_id: 102894822
space_id: 23777123
source: "https://the-faction.mn.co/posts/102894822"
updated: "2026-08-10T17:50:13Z"
---

# Layer 7: CI/CD & Version Control — Study Guide

## Layer 7: CI/CD & Version Control

Shipping Code Without Breaking What Already Works

This is the study guide. Everything for CI/CD & Version Control is on this page — there's nothing to download.

## Layer 7 Recap

## CERTIFICATION GOAL

You can manage team workflows using branches, pull requests, and code reviews. You can set up automated tests that run on every change, and catch problems before they reach your live users.

## What You Need to Know

Yyou're not the only person working on the project. Multiple people (or you working on multiple features) need a system for working on different things at the same time without breaking each other's work.

**Branches (working on features separately):** A branch is a copy of your project where you can make changes without affecting the main version. Think of it as making a photocopy of a document to mark it up—you can experiment, make mistakes, and throw it away without touching the original. When your feature is ready, you merge the branch back into the main version.

**Pull requests (team review before merging):** A pull request (PR) is a formal request to merge your branch into the main project. It shows everyone exactly what you changed, lets teammates review and comment, and provides a record of every decision. Nothing goes into the main project without being reviewed first. This is your quality gate.

**Automated testing (CI - Continuous Integration):** Every time you push code or open a pull request, automated tests run to check if anything is broken. These tests might verify that pages load correctly, forms submit properly, and APIs return the right data. If tests fail, the merge is blocked. Think of it as a bouncer at the door—no untested code gets into the main project.

**Merge conflicts (when two people edit the same thing):** If two people change the same file at the same time, Git doesn't know which version to keep. This is a merge conflict. It sounds scary, but it's normal and fixable—Git shows you both versions side by side, and you pick which changes to keep. Your AI tool can often resolve these for you.

**Continuous Deployment (CD - automatic shipping):** CD means that when code is merged into the main branch and all tests pass, it automatically deploys to your live site. No manual deploy step, no forgetting to push the button. The pipeline handles it: commit → tests → deploy.

You focus on building; the system handles shipping.

## Your Toolkit

**GitHub Pull Requests:** The review and approval interface where teammates comment on changes, request modifications, and approve merges. This is where code quality happens.

**GitHub Actions:** GitHub's built-in automation system. You define workflows (run tests, check formatting, build the app) that trigger automatically on every push or pull request.

**Automated test frameworks (Vitest, Playwright):** Tools that run your tests automatically. Vitest handles unit tests (testing individual pieces). Playwright handles end-to-end tests (testing the whole app like a real user would).

**Branch protection rules:** GitHub settings that prevent anyone from pushing directly to the main branch. All changes must go through a pull request with passing tests and at least one review.

## Certification Exam Topics

Tier 2 tests whether you can manage team workflows and automated quality checks. You'll see scenarios about collaboration, testing, and deployment pipelines.

**Branch strategy:** Your team of three is building different features. One person is on the checkout flow, another on user profiles, and you're on the dashboard. How do you structure branches so nobody blocks anyone else?

**Pull request review:** You open a PR and the automated tests pass, but a teammate comments that the new page doesn't match the design. Should you merge? What's the right process?

**CI pipeline failure:** Your automated tests were passing yesterday, but today they fail on a PR that only changed the footer. What could cause this, and how do you debug it?

**Merge conflicts:** Two teammates edited the same component file. Git shows a merge conflict.

One version adds a new button; the other changes the button color. How do you resolve this?

**Test coverage decisions:** Your AI tool built a new feature but no tests. You're in a rush to ship.

Should you merge without tests? What's the risk?

**CD pipeline:** You merged a PR and the automated deploy failed. Your previous version is still live. What steps do you take?

**Branch protection:** A junior developer pushed directly to the main branch and broke the live site. What branch protection rules would have prevented this?

**Workflow optimization:** Your CI pipeline takes 12 minutes to run, and your team makes 15 PRs per day. The team is frustrated by the wait. How do you speed things up?

## Common Pitfalls

These are the mistakes vibecoders make most often with version control and CI/CD. No judgment—they're easy to make. But if you recognize any of them in your own workflow, fix them before sitting for the exam.

Never committing until the feature is "done." If you work for three days without committing and then break something, you've lost three days of work. Commit early, commit often—small checkpoints, not giant milestones.

Writing commit messages like 'fix', 'update', or 'stuff.' Six months from now, these tell you nothing. Take five seconds to write what actually changed: 'Fix checkout form validation on mobile' saves future-you hours of detective work.

Working directly on the main branch instead of using feature branches. One bad commit goes straight to production. Feature branches give you a safe sandbox to experiment without risking your live app.

Skipping pull request reviews because you're "in a hurry." The bug you ship in a hurry takes ten times longer to fix after users find it. The review process exists because it works.

Not setting up any automated tests, then being afraid to change anything because you might break something. Even basic tests—does the page load, does the form submit—give you the confidence to keep building.

Ignoring merge conflicts by randomly accepting one version. Merge conflicts mean two people changed the same thing. If you don't understand what both changes do, you'll lose someone's work or create a bug.

## Self-Assessment Checklist

Before you take the exam, run through these questions. Every "no" is something to work on.

Can you commit your work and push it to GitHub so it's backed up and triggers a deploy?

Do your commit messages describe what changed and why, not just 'fix' or 'update'?

Could you revert to last week's version of your app if today's changes broke something critical?

If you're working with anyone else (or working on multiple features at once), are you using branches?

Is there at least one automated check (a test, a linter, a build verification) that runs before code reaches your live app?

Do you know how to open a pull request and what the review process looks like?

If your deploy failed right now, would you know how to read the error log and figure out what went wrong?

## AI Audit Prompt Template

Copy this prompt into your AI coding tool to get a quick health check on your version control and CI/CD setup. It checks the same things the certification exam covers.

> Review my project's version control and CI/CD setup and check the following.
>
>
>
> For each one, tell me pass or fail with a specific example:
>
>
>
> Commit hygiene: Are commits small, frequent, and descriptively messaged—or are they large, infrequent dumps with vague labels?
>
>
>
> Branch strategy: Is the project using feature branches and pull requests, or is everything committed directly to the main branch?
>
>
>
> Automated checks: Are there any automated tests, linting, or build verifications running on pull requests or pushes?
>
>
>
> Deployment pipeline: Is the deploy connected to the repository with automatic deployment on merge, and is there a clear path from commit to production?
>
>
>
> Security: Are there any secrets, API keys, or credentials committed in the codebase or Git history?
>
>
>
> Recovery readiness: Can the project be reverted to a previous version quickly, and has this been tested?
>
>
>
> Give me an overall score out of 6 and list the top 3 things to fix first.

## What’s Next

Once you've gone through this study guide and can answer "yes" to the self-assessment checklist, you're ready for the Layer 7 certification exam at your target tier.

The best way to prepare: use version control on a real project. Start a feature branch, make some changes, commit with descriptive messages, open a pull request, and merge it. Break something on purpose, then revert. Set up one automated test—even just "does the app build without errors?" The exam tests whether you've actually done these things, not whether you can recite definitions.

## Certification Pathway

Associate Builder: Pass all 13 layers at Tier 1 Certified Builder: Pass all 13 layers at Tier 1 + Tier 2 MADE Certified: Pass all 39 tier exams + capstone project Each exam requires 80% to pass. You can retake after a 24-hour cooldown. No rush—take the time to build something real first.

———

Ready? Take the [CI/CD & Version Control Exam →](https://the-faction.mn.co/posts/the-foundation-layer-7-cicd-version-control-exam)

---

## Discussion

**Awie Hoh** · 2026-06-24

> The study guide for Layer 7 isnt up yet?

  ↳ **Matt Murphy** · 2026-06-24

  > Thank you for pointing that out it has been fixed.

**Awie Hoh** · 2026-06-25

> Thanks! Will read it now!

**abdulrahman khuthaila khuthaila** · 2026-06-28

> study guide is not working

  ↳ **Matt Murphy** · 2026-06-28

  > Hey Abdulrahman, again our apologies for any inconvenience. Support just checked and all the study guides from Layer 7 through 13 are live and loading on our end, so this looks like it’s on your side. Try this: if you’re on desktop, clear your browser cache and reload the page. If you’re on mobile, close the Mighty Networks app completely, reopen it, and try again. Let me know if that clears it up.💯👊😎

**abdulrahman khuthaila khuthaila** · 2026-06-28

> from layer 7 till 13 or failed to load

  ↳ **Matt Murphy** · 2026-06-28

  > We are reviewing this as we speak I apologize for the delay in your process. 💯😎

**Awie Hoh** · 2026-07-01

> 7. CI/CD & VERSION CONTROL
> 
> PURPOSE
> 
> Version control protects your code history. CI/CD tests, builds, and deploys changes safely.
> 
> PRINCIPLE
> 
> No production change should be untracked, untested, unclear, or hard to undo.
> 
> WHAT THIS SECTION OWNS
> 
> Version-control discipline (Git as the undo button) and the CI pipeline mechanism (which checks run, and that they gate main). Environments, release, and deploy rollback are defined in Hosting & Deployment (#5) — this section references them.
> 
> VERSION CONTROL
> 
> Use Git from the start. Without version control, AI can overwrite working code with no clean way back. Every meaningful change becomes a commit — a save point. A push sends those save points to the remote (e.g. GitHub). If code only exists on your laptop, it is not backed up; push so the project is backed up, shareable, reviewable, and deployable.
> 
> COMMIT PRACTICE
> 
> Commit early and often — never a whole day across many files with no commits. Each commit is small, focused, reversible, with a clear message of what changed and why.
> 
> Good: "Fixed login redirect bug"
> 
> Bad: "Updated stuff"
> 
> AI SAFETY (the core habit — Principle 2)
> 
> Commit before asking AI to make large changes. Review the diff after AI changes code. Reject unrelated edits. Do not treat AI output as safe just because it runs.
> 
> BRANCHES & PROTECTED MAIN
> 
> Use branches for features, experiments, fixes, and risky changes. Keep main stable — never push unfinished or untested work to it. Merge only after the change is reviewed, tested, and safe. Protect main: required checks must pass before anything merges, so broken code cannot reach production by a quick push.
> 
> PROTECT THE HISTORY
> 
> Git history is your safety net — do not destroy it. Never force-push main or rewrite history that has already been pushed.
> 
> IGNORE FILE (secret prevention)
> 
> A .gitignore must exclude .env files, secret files, node_modules, and build output, so secrets and junk can never be committed in the first place. This is the preventive half; the cure is below.
> 
> SECRETS
> 
> Never commit API keys, tokens, service-role keys, private keys, passwords, or credentials. If a secret is committed, treat it as leaked and follow the rotation steps in #5 (revoke, replace, remove from code, move to env vars, check access logs).
> 
> CI PIPELINE
> 
> CI/CD makes builds, checks, and deployments repeatable. Required checks run before production and a failure blocks the deploy: build, tests, linting, type checks, secret scanning, dependency-vulnerability scanning (#8), and migration checks when needed. The push-to-build-to-live flow itself is defined in #5; reproducible builds (committed lockfile) are too.
> 
> MIGRATIONS IN VERSION CONTROL
> 
> Database migrations, RLS and storage policies, indexes, constraints, and permission changes are versioned in Git and reviewed like code. (Controlled and reversible per #3; sequenced with deploys per #5.)
> 
> UNDOING MISTAKES
> 
> If broken code reaches main or production, do not panic-edit. At the deploy level, roll back to the last good deployment (#5). At the git level, revert the bad commit, or branch and test a hotfix before merging. Disable the broken feature if needed. If security, data, login, payments, or core flows are broken, roll back the deploy first, then fix in Git. If a deploy fails or won't update, read the logs before re-pushing — never push the same broken code twice without understanding why (common errors listed in #5).
> 
> SHIP GATE — do not ship unless all are true
> 
> ☐ Code committed in small, clear, reversible commits
> 
> ☐ Pushed to a remote; not laptop-only
> 
> ☐ Diff reviewed after AI changes; unrelated edits rejected
> 
> ☐ main protected; checks must pass before merge
> 
> ☐ History intact; no force-push or rewrite of pushed history
> 
> ☐ .gitignore excludes secrets and build junk; no secrets committed
> 
> ☐ Required CI checks run and block on failure
> 
> ☐ Migrations and policies versioned and reviewed (#3, #5)
> 
> ☐ A clear, tested way to undo: revert, hotfix, or deploy rollback (#5)


---
_Source: https://the-faction.mn.co/posts/102894822_
