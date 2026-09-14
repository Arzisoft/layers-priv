---
course: "The Vault"
module: "Module 1: Why Secrets Management Is a Security Foundation"
lesson: "Module 1: Why Secrets Management Is a Security Foundation — Study Guide"
type: "course_lesson"
post_id: 107142722
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142722"
updated: "2026-09-10T19:56:25Z"
---

# Module 1: Why Secrets Management Is a Security Foundation — Study Guide

# Secrets and API Key Management

### T6 The Vault | Module 1 Study Guide

## Module 1: Why Secrets Management Is a Security Foundation

> Direct AI to handle every credential like it can burn the whole project down, because it can.

## Why This Matters

Every build you ship carries keys: Supabase service keys, Stripe secret keys, OpenAI API keys, database passwords. Any one of them, leaked, hands a stranger your data, your customers' money, or your client's AI bill. The Vibecoder Security Audit Method (#10) taught you how to audit; this course covers the finding those audits surface most often: secrets handled carelessly. Fix this and you remove the most common way builder projects get burned.

## Core Concepts

**A secret is anything that grants access on presentation.** API keys, database connection strings, OAuth client secrets, service account files, signing keys, webhook secrets, admin passwords, encryption keys. The test is simple: if someone who copies this string can act as you or your app, it is a secret. Project IDs, publishable keys, and public URLs are configuration; the string that authorizes action is the secret.

**Blast radius is what a leaked secret reaches.** A leaked Stripe secret key reaches money: refunds, payouts, customer data. A leaked Supabase service role key bypasses row level security entirely: every row, every table, read and write. A leaked OpenAI key reaches your wallet: someone else's traffic on your bill. A leaked database password reaches everything the database holds. Before you store any secret, know what it can do; that knowledge decides how carefully it gets handled.

**Leaks are harvested by machines, not discovered by luck.** Bots scan every public GitHub commit within minutes of push. A key committed to a public repo is compromised the moment it lands, even if you delete it in the next commit; git history keeps it and the scanners already have it. This is a documented, industrial process, not a theoretical risk.

**The pattern behind real breaches is boring.** Uber's 2016 breach began with credentials found in a GitHub repo that unlocked AWS data on 57 million people. Toyota disclosed in 2022 that an access key sat in a public repo for five years. Codecov's 2021 incident turned one leaked credential into an attack on thousands of downstream customers' CI secrets. The same story repeats at every scale, including solo builders whose OpenAI keys get drained on weekend side projects. The cause is never exotic: a secret sat where someone could read it.

**Secrets management is a foundation, not a feature.** You cannot bolt it on later, because the leak happens in the first commit, the first deploy, the first AI-generated file with a hardcoded key. The habits in this course run from project minute one.

## How It Works

The lifecycle every secret follows, and where leaks happen:

1. **Creation.** A key is generated in a dashboard (Stripe, Supabase, OpenAI) or by infrastructure. Risk: keys created with broader permissions than needed.
1. **Storage.** The secret lands somewhere: an env var, a secrets manager, or, wrongly, source code. Risk: hardcoding, committing .env files, pasting keys into docs or chats.
1. **Use.** The app presents the secret at runtime. Risk: client-side exposure, secrets in logs, secrets in error messages.
1. **Sharing.** Teammates or deploy platforms need the secret. Risk: Slack messages, email, screenshots, shared docs.
1. **Rotation.** The secret gets replaced on schedule or on suspicion. Risk: never rotating, so one old leak stays live forever.
1. **Revocation.** The secret is killed. Risk: nobody knows where it is used, so nobody dares revoke it.

Modules 2 through 7 work through this lifecycle. The foundation habit is refusing step 2 failures: no secret ever lives in source code, ever.

## Directing AI

- "Generate this integration with the API key read from an environment variable. Never hardcode the key, never print it, and add .env to .gitignore before anything else."
- "Review this codebase for hardcoded secrets: API keys, connection strings, tokens, passwords, in code, config, and git history. List each finding with file and line."
- "Before we start this build, list every secret this architecture will need: each service, each key, what it protects, and its blast radius if leaked."
- "Explain the blast radius of this Supabase service role key versus the anon key, and confirm which belongs in client code and which never does."
- "Write the project README section that tells collaborators how secrets are handled here: where they live, how to get them, and what never gets committed."

When AI generates example code with placeholder keys, watch it: models happily produce `const apiKey = "sk-..."` patterns. Your standing instruction is that secrets load from the environment, always.

## Common Mistakes

- **Hardcoding a key "just to test."** The test commit becomes the leak. The env var takes ninety seconds; the incident takes your weekend.
- **Committing the .env file.** The file designed to hold secrets, pushed to the repo. .gitignore comes first, before the first secret exists.
- **Treating deletion as revocation.** Removing the key from code does nothing; it lives in git history and in every scanner's database. Leaked means rotate, not delete.
- **Using the service role key where the anon key belongs.** One is public by design; the other bypasses your security rules entirely. Confusing them ships a master key to every browser.
- **Assuming small projects are safe.** Bots do not check your star count. A leaked key on a toy project pays the same crypto miner as one from a funded startup.
- **Sharing keys in chat.** Slack and email are searchable archives of everything ever pasted into them. Secrets move through secret channels or not at all.

## Real-World Application

A builder ships a client MVP over a weekend: Next.js on Vercel, Supabase, Stripe, OpenAI. Because the foundation habits are on, the first commit contains .gitignore with .env excluded; every key loads from environment variables; the Supabase anon key is the only key in client code; Stripe and OpenAI keys live server-side only. Monday, the client asks a contractor to review the repo. The contractor clones it and finds zero secrets: nothing to leak, nothing to rotate, nothing to explain. The alternate version of this story, with one hardcoded OpenAI key, ends with a four-figure usage bill and a Stripe key rotation during the client demo.

## Decision Framework

- **Is this string a secret?** If presenting it grants access or spends money: yes. Handle accordingly.
- **What is its blast radius?** Money, all data, one service, one user? The bigger the radius, the tighter the handling.
- **Where does it live?** Environment variable or secrets manager. Never code, never the repo, never chat.
- **Who can see it?** Only the people and systems that need it. Everyone else gets access through the app, not the key.
- **Found a secret in code or history?** Treat it as leaked. Rotate now, then fix the storage pattern that put it there.

## Tool and Platform Notes

- Supabase issues an anon (publishable) key and a service role key; the service role key bypasses row level security and is server-side only. This pair is the cleanest teaching example of public versus secret.
- Stripe splits publishable (pk_) and secret (sk_) keys and supports restricted keys with narrowed permissions; use restricted keys when a build only needs a slice of the API.
- OpenAI and similar AI providers bill by usage, which makes their keys direct financial targets; usage limits and alerts on the account are part of secrets handling.
- GitHub scans public repos for known key formats and notifies providers; some, like Stripe and OpenAI, auto-revoke keys they are alerted to. That safety net is real but partial: it exists because leaks are that common, and it does not catch everything.

## Key Takeaways

- A secret is any string that grants access when presented; know each one's blast radius before you store it.
- Public repo leaks are harvested by bots within minutes, and git history preserves every mistake.
- Real breaches, from Uber to Toyota to solo builders, start with a secret sitting where someone could read it.
- Secrets management starts at project minute one: .gitignore before the first key, environment variables from the first line.
- A secret found in code or history is a leaked secret: rotate it, do not just delete it.

## What's Next

You know why secrets handling is the foundation. Module 2 maps the terrain: the kinds of secrets builders actually hold, what each one protects, and how each one gets compromised.

## Exam Prep Notes

Focus on: the definition and test for what counts as a secret, blast radius reasoning across Stripe, Supabase, and OpenAI keys, how fast public leaks are harvested and why git history matters, the lifecycle stages and where leaks happen, and the foundation habits that start at minute one. Scenarios will present leaks and handling choices and ask what the principled response is.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107142722_
