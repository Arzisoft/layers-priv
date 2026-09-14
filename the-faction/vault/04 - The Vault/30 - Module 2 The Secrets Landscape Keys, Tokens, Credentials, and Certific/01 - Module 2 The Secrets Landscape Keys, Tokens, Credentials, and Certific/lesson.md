---
course: "The Vault"
module: "Module 2: The Secrets Landscape: Keys, Tokens, Credentials, and Certificates"
lesson: "Module 2: The Secrets Landscape: Keys, Tokens, Credentials, and Certificates — Study Guide"
type: "course_lesson"
post_id: 107142726
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142726"
updated: "2026-09-10T19:57:03Z"
---

# Module 2: The Secrets Landscape: Keys, Tokens, Credentials, and Certificates — Study Guide

# Secrets and API Key Management

### T6 The Vault | Module 2 Study Guide

## Module 2: The Secrets Landscape: Keys, Tokens, Credentials, and Certificates

> Direct AI to name every credential type in your stack and handle each by what it actually protects.

## Why This Matters

"API key" is what builders call everything, but the secrets in a real stack behave differently: some expire on their own, some live forever, some identify an app, some impersonate a user, some can mint other secrets. You cannot handle them correctly until you can tell them apart. This module gives you the working taxonomy, what each type protects, and the specific ways each one gets compromised.

## Core Concepts

**API keys: long-lived strings that identify and authorize an app.** Stripe's sk_live keys, OpenAI keys, SendGrid keys. They usually do not expire on their own, which makes them the most dangerous common secret: a leaked API key works until someone notices and rotates it. Some providers offer scoped or restricted variants (Stripe restricted keys); prefer them whenever the build needs less than everything.

**OAuth tokens: short-lived permission to act as a user.** An access token proves a user granted your app specific scopes; it expires in minutes or hours. The refresh token that accompanies it is the real secret: it mints new access tokens indefinitely. Leaked access token: a bounded window of abuse. Leaked refresh token: standing access to the account until revoked. Treat refresh tokens with API-key seriousness.

**Service accounts: machine identities with their own credentials.** GCP service account JSON files, AWS IAM access key pairs. These are not tied to a human; they are how servers authenticate to cloud services. Their danger is scope: a service account file with broad roles is a master key to infrastructure, and the JSON file format makes it fatally easy to commit by accident.

**Database credentials and connection strings.** Username, password, host, port, often bundled into one connection string (the Supabase or Neon postgres URL). The bundle is the secret; a connection string in a frontend bundle or a log line is a full database compromise.

**Certificates and private keys: cryptographic identity.** TLS certificates, signing keys, SSH keys. The certificate is public; the private key is the secret. A leaked signing key means anyone can impersonate your service or sign malicious code as you, and unlike an API key, you cannot always tell it happened.

**Signing secrets: proof that a message is genuine.** Stripe webhook signing secrets, JWT signing secrets, HMAC keys. They do not grant API access; they let someone forge things your systems trust: fake webhook events, forged session tokens. A leaked JWT secret means attackers can mint valid sessions for any user, which is quieter and often worse than a stolen API key.

## How It Works

How each type gets compromised, in practice:

1. **API keys** leak through code, commits, logs, and client-side bundles. Detection is often the provider's scanner or an anomalous bill.
1. **OAuth refresh tokens** leak from insecure storage (localStorage, unencrypted databases) and from over-logged auth flows. Abuse looks like legitimate user traffic, which makes it hard to spot.
1. **Service account files** leak by being committed whole; a JSON file named service-account.json in a repo is a classic audit finding. Abuse means infrastructure-level actions: spinning up compute, reading buckets, escalating roles.
1. **Connection strings** leak through frontend env var mistakes (a database URL exposed to the browser build) and through error messages that print config.
1. **Private keys** leak from repos (id_rsa committed), from backup archives, and from careless copying between machines.
1. **Signing secrets** leak the same ways, but abuse is forged traffic: webhook endpoints that trust unverified events, sessions that validate because the attacker signs them correctly.

The cross-cutting rule: identify the type, know its expiry behavior, know what abuse looks like, and store it accordingly.

## Directing AI

- "List every secret in this project by type: API key, OAuth token, refresh token, service account, connection string, private key, or signing secret. For each: what it protects, whether it expires, and what abuse would look like."
- "This build needs Stripe. Configure it with a restricted key limited to the operations we actually use, and tell me exactly which permissions you enabled and why."
- "Implement the OAuth flow storing refresh tokens server-side encrypted, never in localStorage, with access tokens kept in memory and short-lived."
- "Verify every webhook handler in this project checks the signing secret before trusting the payload. Show me each handler and its verification line."
- "Review this repo for service account JSON files, private keys, and connection strings in any committed file, including old commits."

## Common Mistakes

- **Treating all secrets as interchangeable "API keys."** A refresh token, a service account file, and a webhook secret need different storage, different rotation, and different alarm responses.
- **Storing refresh tokens in localStorage.** Any script injection reads them; standing account access walks out the door.
- **Committing service account JSON.** The file format invites it: it is a file, it sits in the project, and one git add -A later it is in history.
- **Exposing connection strings to the frontend.** Prefixing a database URL with NEXT_PUBLIC_ or VITE_ ships the entire database to every visitor. Module 3 covers the prefix rules in depth.
- **Skipping webhook signature verification.** The endpoint works fine in testing, and accepts forged events in production. The signing secret exists to be checked, not just stored.
- **Confusing the public and private halves.** Publishing a certificate is fine; publishing the private key is the breach. Knowing which half is which is table stakes.

## Real-World Application

A builder audits a client's inherited codebase using this taxonomy. Findings: a Stripe secret key with full permissions where a restricted key would do; refresh tokens for a Google integration sitting unencrypted in a users table; a GCP service account JSON committed eight months ago with editor role; webhook handlers that never verify signatures. The builder directs AI through the fixes in order of blast radius: rotate and restrict the Stripe key, revoke and reissue the service account with minimal roles, encrypt the token store, add signature verification to every handler. Each fix maps to a type-specific failure. Without the taxonomy, this audit reads as "keys everywhere, seems fine": with it, every finding has a name, a severity, and a fix.

## Decision Framework

- **Does it identify an app to a provider?** API key. Restrict its scope if the provider allows; rotate on schedule.
- **Does it act as a user?** OAuth. Access tokens short-lived in memory; refresh tokens server-side, encrypted.
- **Does it authenticate a machine to infrastructure?** Service account. Minimal roles, never in the repo, rotate like an API key.
- **Does it open a database?** Connection string. Server-side only, never in client bundles, never in logs.
- **Does it prove identity cryptographically?** Private key. Generated where used, never copied casually, never committed.
- **Does it prove a message is genuine?** Signing secret. Store server-side and verify on every message, every time.

## Tool and Platform Notes

- Stripe: publishable pk_ keys are public; sk_ keys are full-access; restricted keys narrow permissions per integration. Webhook signing secrets are per-endpoint.
- Supabase: anon key is public and governed by row level security; service role key bypasses RLS; the direct postgres connection string is a separate, equally critical secret.
- OpenAI and AI providers: usage-billed API keys, often with per-project scoping available; use one key per project so leaks are isolated and revocable.
- GCP service accounts issue JSON key files; AWS IAM issues access key pairs; both platforms prefer short-lived credentials and workload identity where configurable, which downstream modules build on.
- GitHub: personal access tokens and deploy keys are secrets too; fine-grained tokens with expiry beat classic tokens with everything.

## Key Takeaways

- Secrets differ by what they protect, how long they live, and what abuse looks like; handle by type, not by habit.
- Refresh tokens and service account files deserve API-key-level care or more; they grant standing or infrastructure-level access.
- Connection strings and private keys never touch client code or repos, in any commit, ever.
- Signing secrets exist to be verified against, not just stored; unverified webhooks trust forgeries.
- Prefer scoped variants everywhere: restricted keys, minimal roles, fine-grained tokens, per-project keys.

## What's Next

You can name every secret in a stack. Module 3 covers where they live in a working project: environment variables, .env files, and the configuration patterns of the platforms builders actually deploy on.

## Exam Prep Notes

Focus on: the secret types and what each protects, expiry behavior differences, access versus refresh tokens, why service account files and connection strings are high-severity, signing secrets and forgery, and the scoped-variant preference across Stripe, Supabase, and cloud providers. Scenarios will present a credential and ask what type it is, what its leak means, or how it should be handled.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107142726_
