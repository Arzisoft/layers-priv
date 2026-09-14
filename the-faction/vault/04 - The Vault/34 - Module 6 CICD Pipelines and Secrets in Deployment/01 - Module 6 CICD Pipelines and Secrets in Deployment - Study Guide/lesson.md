---
course: "The Vault"
module: "Module 6: CI/CD Pipelines and Secrets in Deployment"
lesson: "Module 6: CI/CD Pipelines and Secrets in Deployment — Study Guide"
type: "course_lesson"
post_id: 107142739
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142739"
updated: "2026-09-10T20:01:59Z"
---

# Module 6: CI/CD Pipelines and Secrets in Deployment — Study Guide

# Secrets and API Key Management

### T6 The Vault | Module 6 Study Guide

## Module 6: CI/CD Pipelines and Secrets in Deployment

> Direct AI to build pipelines where secrets flow in at the right moment and never flow out through logs, artifacts, or images.

## Why This Matters

Your pipeline touches every secret you have: it builds with them, deploys with them, and, misconfigured, prints them into logs and bakes them into artifacts that outlive the build. CI/CD is where secrets handling either becomes systematic or leaks at industrial scale, because pipelines run unattended, on every push, forever. This module makes the deployment machinery as disciplined as the code it ships.

## Core Concepts

**Pipeline secrets are injected, never stored in the workflow.** GitHub Actions secrets, GitLab CI variables, and platform deploy settings exist so workflow files reference names, not values: `${{ secrets.STRIPE_SECRET_KEY }}` in the YAML, the value in the encrypted store. The workflow file is code, committed and public to the team; the secret store is configuration, scoped and access-controlled. Anything pasted into the YAML itself is a committed secret, full stop.

**Build-time and runtime are different exposure windows.** A build-time secret (a private registry token, a prefixed public variable) is consumed while the artifact is assembled; a runtime secret (database URL, Stripe key) is needed when the app serves traffic. The rule: give each secret to the stage that needs it and no other. A runtime secret passed at build time risks being baked into the artifact; a build that embeds a server key into a client bundle has published it, exactly as Module 3 warned with public prefixes.

**Logs are the pipeline's most reliable leak.** CI logs are written, stored, and shared by default. Providers mask registered secrets (GitHub Actions replaces known values with ***), but masking only covers what the store knows: derived values, encoded copies, and secrets echoed by debug commands walk straight through. The discipline: never echo env vars for debugging, never run commands that print full config, and treat any secret that ever appeared in a log as leaked.

**Artifacts and images remember. **Docker images are the sharpest case: a secret copied in during a build step lives in that layer forever, even if a later step deletes it. COPY .env into an image is a permanent publication. The tools exist: multi-stage builds where secrets stay in a discarded stage, BuildKit secret mounts (--mount=type=secret) that inject without layering, and runtime injection where the container gets its env at start. The same logic covers build artifacts: bundles, sourcemaps, and cached dependencies can all carry embedded values if the build was careless.

**Pipelines authenticate somewhere; make it short-lived.** The pipeline itself holds credentials: a deploy token, a cloud role, a registry login. The modern pattern is OIDC federation: GitHub Actions proves its identity to AWS or GCP and receives short-lived credentials per run, no stored cloud keys at all. Where OIDC is available, stored cloud keys in CI are legacy risk.

## How It Works

Building a clean pipeline:

1. **Store secrets in the CI secret store.** Repository or organization secrets in GitHub Actions; environment-scoped where supported (production secrets only available to the production environment's jobs, ideally behind required reviewers).
1. **Reference by name in workflows.** Values appear only as `${{ secrets.NAME }}`; pull requests from forks get no secret access by default, and that default stays on.
1. **Split by stage.** Build jobs receive build-time values; deploy jobs receive deploy credentials; runtime secrets go to the platform's env settings (Vercel, Railway), not into the artifact.
1. **Keep secrets out of output.** No echo of env vars, no verbose flags that dump config, no printing request headers with authorization values. Masking is a net, not a strategy.
1. **Build containers with secret mounts.** BuildKit secret mounts for anything needed during docker build; runtime env injection for everything the running container needs; never COPY .env, and .dockerignore excludes it as a backstop.
1. **Federate pipeline identity.** OIDC to cloud providers where supported; scoped, expiring deploy tokens where not; the pipeline's own credentials rotate like any other secret (Module 5).

## Directing AI

- "Write this GitHub Actions workflow with all secrets referenced from the secrets store, environment-scoped for production, and no step that echoes environment variables or prints config."
- "Review this workflow file and flag: hardcoded values, secrets passed to build steps that only runtime needs, steps whose output could contain secret values, and fork PR exposure."
- "Convert this Dockerfile to a multi-stage build with BuildKit secret mounts for the npm token; confirm no layer in the final image contains the secret, and add .env to .dockerignore."
- "Set up OIDC between this GitHub repo and AWS so deploys assume a role scoped to this one service, and remove the stored AWS keys from the repo secrets afterward."
- "Audit our CI logs for the last month for anything that looks like a key, token, or connection string; list findings so we can rotate them."

## Common Mistakes

- **Secrets in the workflow file.** The YAML is code; a value pasted there is committed. The store exists precisely so this never happens.
- **Debug-echoing the environment.** One `env` or `printenv` step to diagnose a failure, and every secret the job holds is in a stored log.
- **Trusting masking completely.** Masking catches registered values verbatim; base64 variants, substrings, and derived tokens pass through unmasked.
- **COPY .env into Docker images.** The layer remembers forever; deleting the file in a later step changes nothing. Multi-stage and secret mounts exist for this.
- **One credential for the whole pipeline.** A single god token that builds, deploys, and administers everything: one compromised run compromises all of it. Scope per job, per environment.
- **Fork PRs with secret access.** Enabling secrets for fork pull requests hands your credentials to anyone who opens a PR. The default is safe; changing it is the mistake.

## Real-World Application

A builder inherits a client pipeline: deploys work, but the workflow file contains a hardcoded Supabase service key, a debug step that prints the environment, and a Dockerfile that copies .env into the image. They direct AI through the cleanup: the key moves to repository secrets and gets rotated (it was in git history and in every log of every run); the debug step is deleted and the last month of logs audited for exposed values; the Dockerfile becomes a two-stage build with a secret mount for the registry token; deploys switch from a stored AWS key to OIDC role assumption. Four changes, one afternoon. The pipeline now runs on every push without a single long-lived secret stored in it, and the client's next security questionnaire has a clean answer for "how do credentials reach production."

## Decision Framework

- **Does the workflow need a value?** Reference it from the secret store by name; never paste it.
- **Build-time or runtime?** Give the secret to the stage that needs it; runtime secrets live in platform env settings, not artifacts.
- **Does docker build need a secret?** BuildKit secret mount, multi-stage build; never COPY, never a plain ARG.
- **Deploying to a cloud with OIDC support?** Federate; delete stored cloud keys from CI.
- **Did a secret appear in any log?** It is leaked; rotate it now (Module 5's emergency order).
- **Fork PRs in play?** Secrets stay off for them; required reviewers gate production environments.

## Tool and Platform Notes

- GitHub Actions: repository, environment, and organization secrets; environment protection rules with required reviewers; OIDC federation to AWS, GCP, and Azure; automatic masking of registered secrets in logs.
- Vercel and Netlify: env vars set in the platform are the runtime path for Jamstack deploys; sensitive marking prevents read-back; deploy hooks and tokens are secrets too.
- Railway: per-environment variables injected at deploy; service tokens scoped per project.
- Docker: BuildKit --mount=type=secret for build-time injection; multi-stage builds to discard secret-touching stages; .dockerignore as the .gitignore of images.
- Doppler and Infisical (Module 4) both integrate with GitHub Actions, replacing scattered repo secrets with synced, centrally rotated values.

## Key Takeaways

- Workflow files hold secret names; the CI secret store holds values; anything pasted in YAML is committed.
- Match secrets to stages: build-time and runtime are different windows, and artifacts remember what builds embed.
- Logs leak by default: never echo the environment, treat masking as a net, and treat logged secrets as burned.
- Docker layers are permanent: secret mounts and multi-stage builds, never COPY .env.
- Prefer OIDC federation over stored cloud keys; scope and rotate every credential the pipeline itself holds.

## What's Next

Your secrets are stored, typed, scoped, rotated, and deployed cleanly. Module 7 closes the loop: detecting leaks, responding when one happens anyway, and the hygiene checklist that keeps the whole system honest.

## Exam Prep Notes

Focus on: store-versus-workflow separation, build-time versus runtime exposure, why logs leak and what masking does and does not catch, Docker layer permanence and the mount/multi-stage fixes, OIDC federation versus stored keys, fork PR defaults, and per-job credential scoping. Scenarios will present pipeline configurations and ask what leaks, what to fix first, or which pattern applies.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107142739_
