---
space: "The Pit"
author: "Matt Murphy"
post_id: 106084251
reactions: 1
comments: 0
published: "2026-08-18T14:00:07Z"
source: "https://the-faction.mn.co/posts/106084251"
---

# 47 files in one commit. No PR. No review. Straight to production. Payments broke

47 files in one commit. No PR. No review. Straight to production. Payments broke on a Friday night. You are staring at 47 file changes trying to find which one killed your revenue. Today I walk through branch protection on main, automated CI checks that block broken merges, and scoped commits that let you trace and reverse any change in seconds. If your AI is pushing directly to main, this one is urgent.

**PROMPT:** Direct your AI: "Perform a GitOps security and workflow audit with three components: (1) Branch protection configuration. Lock the main branch to reject all direct pushes. Require pull requests for every change with at least one approval. Enable status checks that must pass before merge is allowed. Show me the exact GitHub settings and any CLI commands needed. (2) CI pipeline setup. Configure GitHub Actions to run on every pull request: build verification, linter, test suite, and a security scan for secrets and dependency vulnerabilities. If any check fails, block the merge. Show me the workflow YAML file and explain each step. (3) Commit hygiene audit. Review my last 20 commits for scope and traceability. Flag any commit that changes more than 10 files as a traceability risk. Recommend a commit strategy: one logical change per PR, descriptive commit messages, and a branching convention (feature branches off develop, merged to main only through PR). Set up a pre-commit hook that warns when a commit exceeds 10 files."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m16s_

Your AI pushed forty seven files to production in one commit, and one of them broke your payment flow, but you cannot figure out which one it was. So all forty seven files changed. No pull request. No review. No test.

Just straight to main. So payments stop processing at six PM on Friday, and you are staring at forty seven file changes trying to figure out which one killed your revenue, all while your customers are filing chargebacks. That's not a win. And this is why DevOps doesn't ship on Fridays. So this is what happens when your AI treats GitHub like a filing cabinet instead of an engineering system.

Here's what your AI should have configured in GitHub from day one. Step one, branch protection on main. Nobody pushes directly to production. Nobody. Not you, not your AI, not anyone.

Every change goes through a planned pull request. The PR is where you review what changed, why it changed, and whether it breaks anything in your system. So direct your AI to lock your main branch so direct pushes are totally rejected. And all changes require a PR with at least one approval. That's a win.

Step two, automated checks that run before any merge. Your CI pipeline should run your test suite, your linter, your build verification and your security scan on every pull request before it's allowed to merge. If any check fails, the merge is blocked. The one file that broke your payment flow would have been caught before production if you had this in place. So your AI knows how to configure GitHub actions for all of this.

And that's a win. Use it right. Step three, small scoped commits that you can trace and reverse. Forty seven files in one commit? Totally untraceable.

One change per PR means when something breaks you know exactly which change caused it. And you roll back that one change in seconds instead of spending a Friday night reading forty seven different files. Your code deserves a gate between your keyboard and your customers, trust me. So direct your AI to build that gate. And that's a win.


---
_Source: https://the-faction.mn.co/posts/106084251_
