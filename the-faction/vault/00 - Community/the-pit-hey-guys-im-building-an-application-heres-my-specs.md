---
space: "The Pit"
author: "Rhet Wike"
post_id: 104889209
reactions: 1
comments: 2
published: "2026-07-22T05:29:21Z"
source: "https://the-faction.mn.co/posts/104889209"
---

# hey guys im building an application, heres my specs, tell me what im missing so

hey guys im building an application, heres my specs, tell me what im missing so far?

 Here’s the no-BS builder inventory.

 The platform is a production-shaped Rust backend with 213 database migrations, paired with an HTML/JavaScript browser UI. The UI has not been rewritten in Rust. ?platform=1 is the opt-in Rust-backed path; the default demo and Focus lane still use Python.

 ## What currently works through the UI

 Surface What it does Current authority Safety/trust boundary

 ━━━━━━━━━━━━━━━━━━━━ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ ━━━━━━━━━━━━━━━━━━━━━━━━━━━ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

 Sign-in Request/redeem magic links and establish a browser session UI → Rust Secure HttpOnly __Host- cookie, CSRF, exact Origin/Host checks, one-use token, token removed from URL, no auth secrets in localStorage

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 First contact Helper privately advises, Jim drafts, reviewer approves introduction UI → Rust, migration 0211 Closed contracts, idempotent worker job, atomic delivery, exactly zero memory actions

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Chat Send turns and receive Jim’s exact response over SSE UI → Rust Response matched to exact turn UUID; retries reuse the turn key; safety blocks render as system notices, never counterfeit Jim speech

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Profile Read/save display name UI → Rust Account-scoped; closed fields; failed refresh leaves the last confirmed state read-only

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Account email Displays signed-in email Read-only UI cannot claim an unsupported email-changing authority

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Memories List, paginate, search, inspect provenance, correct, and remove UI → Rust Account isolation, identity-preserving successor on correction, tombstones cannot reactivate, stale data becomes read-only; no arbitrary Add-memory UI

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 People Create, list, open, fully replace, archive contact cards UI → Rust, migration 0212 Account-and-companion scoping, UUID identities, idempotent creation, closed merge shape, dependency guards, no localStorage persistence

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Export Request/list full-account exports and handle completion/download grants UI → Rust One active job per account, sensitive-column exclusions, bounded artifact retention, short-lived signed same-origin download grant

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Reach Read/save timezone and actively enforced quiet hours UI → Rust, migration 0213 Closed partial PATCH, exact HH:MM pair, overnight allowed, equal endpoints rejected, atomic write, exact retries emit nothing

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Events Powers live chat and invalidation through durable SSE UI → Rust Per-account sequence, signed account-bound cursors, Last-Event-ID, anti-buffering/no-store headers, stream closes on token/account revocation

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Focus setup Helper-reviewed goal intake with Jim’s final judgment Python server lane Evaluation quarantine, private Helper input, harmful-goal screening, zero-canon-write close receipt

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Saved focuses Switchboard, Focus/Witness/Neutral/Never, cadence, windows, pauses Browser-local Clearly labeled prototype state; never presented as Rust/server authority

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Open conversations Resumable temporary Focus rooms Browser/Python Separate from canonical memory; message previews hidden

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Offline/PWA Installable shell and honest offline page Browser Service worker caches only the offline page—not app/API code—and never fabricates an offline Jim reply

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Voice call Mute/caption/hang-up interaction preview Preview only No microphone, audio stream, provider call, or billing effect

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Phone and inbox Number, passphrase, trusted-caller, guest and email concepts Preview only No number, mailbox, purchase, or provider authority is created

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Tools UI Weather/battery preferences and Gmail preview Local/preview No device permission or external tool grant is silently created

 ──────────────────── ───────────────────────────────────────────────────────────────────────── ─────────────────────────── ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

 Local wipe Removes prototype messages, focuses, preferences and profile state Browser-local Explicitly says it is not server account deletion

 ## Rust backend feature families

 - Accounts and identity: accounts, profiles, subscription/tier authority, companions, magic-link identity, browser sessions, API tokens, device binding, reauthentication, account deletion grace and cancellation.

 - Conversation runtime: idempotent sessions and turns, device-isolated sessions, evaluation sessions, assistant jobs, cancellation, exact SSE completion, first contact, durable chat.message and terminal events.

 - Model execution: model routes, deployments, provider adapters, execution modes, cancellation, retry/dead-letter recovery, prompt-cache identities and invocation receipts. The repo contains no model weights.

 - Sealed Jim persona: byte-exact Jim prompt profile, immutable companion binding, persona seal validation, prompt budgets and startup/per-turn drift refusal.

 - Prompt assembly: component hashes, profile/version/seal receipts, token-budget snapshots, retention sweeps, no raw rendered prompt stored.

 - Memory system: Heart/Spine memory surfaces, tags, embeddings, graph links, versions, provenance, privacy controls, semantic search, candidate review, consolidation, correction, suppression, tombstones and recall-repair proposals.

 - People system: person entities, merging, archiving, contact cards, relationship/context notes, contact methods and recall preference storage.

 - Switchboard and consent: typed topic switches, Focus/Witness/Neutral/Never semantics, append-only consent events, policy-v3 authority and tier downgrade boundaries.

 - Temporal system: scheduled tags, decision traces, folding, canonical resolution, salience evaluation, quiet holds, budgets, deduplication and account policy serialization.

 - Proactive delivery machinery: touch claims, salience receipts, durable outbox, provider-effect reconciliation, retries and receipts. Production external delivery remains disabled; only a loopback local-test adapter exists.

 - Safety: safety policies, turn-safety assessments, harmful-goal screening, Helper activity receipts, active safety walks, escalation resources and explicit resolution.

 - Tools: tool registry, grants, revocation, queued invocations, account-generation fencing, cancellation and explicit one-shot confirmation decisions.

 - Imports: source registry, bounded locators, import jobs, leases, retry/dead-letter handling, active-account and wipe-generation gates.

 - Full-account exports: queued execution, temporal-state projection, artifact creation, expiry sweeping, secret/raw-webhook exclusions and deletion-grace download access.

 - Devices: registration, push-token vault references, token/device binding, disabling and structural revocation. API responses never expose stored push-token material.

 - Phone ingress: guarded numbers, trusted callers, relay authorization, Twilio idempotency, caller budgets, immutable provider envelopes and number parking/grace lifecycle.

 - Email ingress: trusted sender/provider proofs, recipient routing, HMAC webhook verification, immutable envelopes, provider idempotency and disabled-account gates.

 - Audit and events: account audit log, append-only consent, durable account events, commit sequences, filtered listing and resumable SSE.

 - Live-pattern detection: production-shaped detectors operate only on immutable live consolidation sources and exclude evaluation traffic.

 - Parity/evaluation: golden scenarios, run-keyed shadow execution, Python/Rust comparison receipts, artifact lifecycle, Oracle/Candidate/Pairing bundles and migration-upgrade matrices.

 - Operations: health/readiness, environment validation, API/worker/migrator credential separation, worker health, retention sweeps, install/activate checks and rollback mechanics.

 - Release system: isolated source snapshot builds, contained toolchains, exact manifests/checksums, tamper tests, source-custody checks and unsigned signing requests.

 ## The main trust controls

 - API, worker and migrator are separate database principals. Current audited surfaces are API 59 reads / 66 callables, worker 83 / 85, with 293 closed SECURITY DEFINER routines.

 - API and worker do not receive arbitrary table access. Migration 0213 specifically replaced raw quiet-hours table mutation with one fixed-path API-only function.

 - Security-definer functions use fixed search paths, exact signatures, explicit grants and no PUBLIC execution.

 - Bearer secrets, magic links and reauthentication proofs are hash-only at rest. Newly minted API-token secrets are returned once.

 - Browser cookies and bearer credentials cannot be mixed. Cookie reads require same-origin authority; mutations additionally require CSRF.

 - Database constraints enforce account/person/session/device coherence, active-account gates, metadata bounds, immutable provider envelopes and append-only evidence.

 - Evaluation/test sessions are a separate species and cannot create production memory, person, temporal, budget-touch or account-event state.

 - First contact creates no memory. Reach changes create no tag, touch, outbox, consent or provider authority.

 - Idempotency keys, leases, account generations, retry caps and dead-letter state protect against duplicate work and stale workers.

 - Deleted memory cannot be reactivated. Sensitive tombstone/version receipts are redacted.

 - The UI never fabricates Jim when a backend fails. It preserves confirmed state, disables writes, and labels platform errors and safety notices separately.

 - Production signing keys, trust roots and guardian state are deliberately absent from the repo and this host. Packaging can measure a candidate; it cannot authorize deployment.

 ## What we added during this run

 - Migration 0211: sealed Helper/Jim/reviewer first-contact workflow.

 - Migration 0212: Rust People contact-card create/read/replace/archive authority.

 - Migration 0213: Rust Reach timezone/quiet-hours authority without raw policy-table access.

 - Browser magic-link auth, exact SSE chat, profile, memory, export, People and Reach wiring under ?platform=1.

 - Streaming /v1 proxy behavior and honest cache/auth failure handling.

 - Release checksum ordering fix using byte-stable locale sorting.

 - Restricted-role, scope, conflict, migration, UI and live-browser adversaries.

 Current evidence is green:

 - 84 Python tests

 - 12/12 browser transport tests

 - 61/61 UI tests

 - Restricted API/worker role audit

 - Full restricted API and auth smokes

 - Fresh 0001→0213 and historical 0172→0213 migration matrix

 - Live HTTPS browser journey through auth, first contact, chat, profile, memory, export request, People and Reach

 ## Still honestly unfinished

 - Default UI traffic remains Python; Rust mode is opt-in.

 - Focus and everyday Helper/warm-memory behavior remain on the Python track.

 - Proactive production delivery, real phone calls, SMS and email providers are not authorized.

 - Tools, billing and server account deletion are not UI-connected.

 - The 0213 Rust checkpoint is tested but not yet committed, clean-packaged, threshold-signed, installed or activated.

 - Production guardian, trust roots and private signing keys are absent.

 - No production canary, provider-capacity, family-consent or stranger-cohort claim has been made.

---

## Discussion

**Matt Murphy** · 2026-07-22

> First off, Rhet, this is one of the most comprehensive build inventories I've seen someone post here. You should be proud of yourself. The thing I appreciate most is that you're very honest about what's production-ready, what's preview-only, and what still lives on the Python path. That level of discipline is rare.
> 
> Looking through it, I don't think your biggest gaps are in the code anymore, I think they're in production operations.
> 
> A few areas I'd challenge you to inventory next:
> 
> **Observability:** logs, metrics, traces, alerting, SLOs, incident response.
> 
> **Disaster Recovery:** backups, restore testing, RPO/RTO, failover strategy.
> 
> **Release Management:** feature flags, canary deployments, rollback procedures, kill switches.
> 
> **Performance:** load testing, stress testing, capacity planning, scaling limits.
> 
> **Infrastructure:** hosting architecture, CDN, autoscaling, WAF, DDoS protection.
> 
> **Compliance & Privacy:** retention policies, audit readiness, regulatory requirements.
> 
> **Business Operations:** billing, support workflows, customer success, pricing, legal, and operational playbooks.
> 
> The software itself looks increasingly production-shaped. The next stage is making sure the *business* around the software is just as mature as the code.👊😎

**Rhet Wike** · 2026-07-23

> On it my friend, your a G


---
_Source: https://the-faction.mn.co/posts/104889209_
