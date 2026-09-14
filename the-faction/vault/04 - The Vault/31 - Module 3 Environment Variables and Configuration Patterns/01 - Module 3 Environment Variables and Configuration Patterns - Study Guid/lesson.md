---
course: "The Vault"
module: "Module 3: Environment Variables and Configuration Patterns"
lesson: "Module 3: Environment Variables and Configuration Patterns — Study Guide"
type: "course_lesson"
post_id: 107142729
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142729"
updated: "2026-09-10T19:57:52Z"
---

# Module 3: Environment Variables and Configuration Patterns — Study Guide

# Secrets and API Key Management

### T6 The Vault | Module 3 Study Guide

## Module 3: Environment Variables and Configuration Patterns

> Direct AI to configure every project so secrets live in the environment, split by stage, and never reach the browser.

## Why This Matters

Environment variables are where secrets actually live in most builder projects, which makes the env layer the place most leaks start and most fixes happen. Get the patterns right, .env hygiene, public prefix rules, per-environment separation, and every platform you deploy to becomes a place secrets are safe by default instead of exposed by accident.

## Core Concepts

**Configuration lives in the environment, not the code.** This is the twelve-factor app principle: code is the same everywhere; config differs per deploy. Your app reads DATABASE_URL and STRIPE_SECRET_KEY from its environment at runtime, so the same codebase runs locally, in preview, and in production with different values and zero code changes. Secrets are config; config lives outside the repo.

**.env files are a local convenience, not a storage system.** A .env file holds your local values so you do not export variables by hand. It is a plaintext file of your most sensitive strings, which is why the rules are absolute: .env is in .gitignore before the first secret exists; .env never gets committed, shared, or backed up into a repo. The committable sibling is .env.example: same keys, no values, so collaborators know what to set without seeing yours.

**Public prefixes are a one-way door to the browser.** NEXT_PUBLIC_ (Next.js), VITE_ (Vite), and their equivalents embed the variable into the client bundle at build time. That is correct for publishable keys and app URLs, and catastrophic for anything secret. The prefix is a declaration: this value is public forever. A secret with a public prefix is not configured; it is published.

**Not everything belongs in env vars.** Env vars fit small, per-deploy strings: keys, URLs, flags. They do not fit large blobs (certificates get mounted or fetched), truly dynamic values (feature flags at runtime scale need a service), or non-secret constants that belong in code. And local .env files stop scaling the moment a team or a second environment appears, which is where Module 4's managers come in.

**Environments are separate trust zones.** Development, preview, and production get separate values for every secret: separate Stripe test and live keys, separate database branches, separate AI keys with separate limits. A preview deploy with production keys is a production breach waiting on a pull request. Platforms support per-environment scoping; using it is not optional.

## How It Works

Standing up a clean configuration layer:

1. **Initialize hygiene first.** .gitignore contains .env and .env.* before any secret exists; .env.example is created alongside with every key the project needs, values blank.
1. **Name with intent.** SERVER-only secrets get plain names: STRIPE_SECRET_KEY, DATABASE_URL, SUPABASE_SERVICE_ROLE_KEY. Browser-safe values get the public prefix: NEXT_PUBLIC_SUPABASE_URL, NEXT_PUBLIC_SUPABASE_ANON_KEY. The name itself documents the trust decision.
1. **Load once, validate early.** The app reads env vars at startup through one config module that fails loudly if a required key is missing, rather than crashing at first use three layers deep.
1. **Mirror to the platform.** Local .env values are set in the deploy platform's env var settings (Vercel, Netlify, Railway), scoped per environment: development, preview, production.
1. **Separate by stage.** Test keys in development and preview; live keys only in production. Preview environments never see production data or production credentials.
1. **Document the map.** .env.example stays current as keys are added; a stale example file is how collaborators end up asking for secrets in Slack.

## Directing AI

- "Set up this project's configuration: .gitignore covering .env files first, a .env.example with every key we need and no values, and a config module that validates required env vars at startup and fails with a clear message."
- "Review every env var in this project: list which have public prefixes, confirm each prefixed one is safe to be public, and flag any secret that would reach the browser bundle."
- "Wire this Stripe integration for environment separation: test keys in development and preview, live keys only in production, read from the platform env settings, never hardcoded."
- "This build deploys to Vercel. List the env vars to set, which environments each applies to, and which are sensitive; then give me the exact settings to configure."
- "The app crashes in production with an undefined API key. Trace how this variable flows from platform settings to the code and find where the name or scope mismatches."

## Common Mistakes

- **Committing .env anyway.** The .gitignore came after the first commit, or someone force-added the file. History now holds every secret; rotation time.
- **The public prefix reflex.** A build error says a variable is undefined in the browser, and the "fix" is adding NEXT_PUBLIC_. Now the secret ships to every visitor. The correct fix moves that logic server-side.
- **One set of keys everywhere.** Production Stripe keys in the dev .env, production database in preview deploys. Every experiment becomes a production risk.
- **Config spread across the codebase.** process.env read in forty files, so nobody can list what the app needs; the startup validator and single config module exist to prevent exactly this.
- **Secrets in framework config files.** Keys pasted into next.config.js or vite.config.ts get committed like any code. Config files reference env vars; they do not contain values.
- **A stale .env.example.** New keys were added, the example was not updated, and onboarding becomes secret-sharing over chat.

## Real-World Application

A builder joins a project mid-stream: the app crashes locally, and the repo has no .env.example. They direct AI to scan the codebase for every process.env read, generate the complete .env.example, and add a startup validator. Ten minutes later the crash points to the missing key by name. Next, the env audit: two variables carry NEXT_PUBLIC_ prefixes, one is the Supabase anon key (correct), one is an OpenAI key (published to every visitor since launch). The OpenAI key gets rotated, the call moves to a server route, and the prefix is dropped. Finally, preview deploys get pointed at Stripe test keys instead of the live ones they had been using. Three structural risks, closed in an afternoon, all from patterns this module makes routine.

## Decision Framework

- **Is the value secret?** Plain name, server-side only, never a public prefix.
- **Is it needed in the browser?** Then it must be public by nature (anon key, URL); prefix it and confirm it is truly safe.
- **Does the same value differ by stage?** Separate values per environment, scoped in the platform.
- **Is it a large blob or runtime-dynamic?** Not an env var; mount it, fetch it, or use a service.
- **Is the team growing or environments multiplying?** Local .env files are at their limit; move to a secrets manager (Module 4).
- **Variable undefined in the browser?** The answer is almost never a public prefix; it is moving the code server-side.

## Tool and Platform Notes

- Vercel: env vars scope to development, preview, and production; sensitive values can be marked so they are write-only after creation. Pulling remote values locally is supported through the CLI.
- Netlify: env vars scope per deploy context (production, deploy previews, branch deploys); same separation discipline applies.
- Railway: variables live per environment and can reference each other; database URLs are injected for attached services.
- Supabase: the anon key is browser-safe by design (paired with row level security); the service role key and the direct database URL are server-only and never take a public prefix.
- Next.js and Vite embed prefixed variables at build time: changing a public value requires a rebuild, and un-prefixing a leaked secret requires rotation, not just renaming.

## Key Takeaways

- Config lives in the environment; the same code runs everywhere with per-deploy values.
- .env is gitignored before the first secret exists; .env.example carries the keys, never the values.
- A public prefix publishes the value forever; secrets never take one, and build errors never justify one.
- Every environment gets its own keys: test in dev and preview, live only in production.
- One config module, validated at startup, keeps the whole secret surface listable.

## What's Next

Env vars and .env files carry a solo project cleanly. Module 4 covers what happens when they stop scaling: secrets managers, from platform-native to Doppler, Infisical, and Vault, and how to choose for your size.

## Exam Prep Notes

Focus on: the twelve-factor separation of config from code, .env versus .env.example rules, exactly what public prefixes do and when they are correct, per-environment key separation, the single config module with startup validation, and the platform-specific scoping on Vercel, Netlify, and Railway. Scenarios will present misconfigurations and ask what went wrong or what the fix is.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107142729_
