---
course: "The Vault"
module: "Module 2: The Secrets Landscape: Keys, Tokens, Credentials, and Certificates"
lesson: "Module 2: The Secrets Landscape: Keys, Tokens, Credentials, and Certificates — Exam"
type: "course_quiz"
post_id: 107142727
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142727"
updated: "2026-09-10T19:57:21Z"
---

# Module 2: The Secrets Landscape: Keys, Tokens, Credentials, and Certificates — Exam

> Exam for **Module 2: The Secrets Landscape: Keys, Tokens, Credentials, and Certificates** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder calls every credential in the stack an 'API key.' Why does this module treat that habit as a problem?

- **A.** Because providers charge different rates by credential type, so mislabeling secrets distorts the project budget
- **B.** Because the term is legally reserved for REST services, so misusing it creates confusion in compliance reviews
- **C.** Types behave differently: some expire, some impersonate users, some mint other secrets, each handled its own way  ✅
- **D.** Because AI models refuse to generate code for unnamed credential types, so the vocabulary blocks the build itself

> **Answer:** C

### Q2. A Stripe sk_live key leaked six months ago and still works today. Which property of API keys does this module say explains that?

- **A.** Stripe keys are permanently valid by contract, since payment providers guarantee key stability for integrations
- **B.** API keys usually do not expire on their own, making them the most dangerous common secret: a leak works until rotation  ✅
- **C.** The key remained valid because the leak was never posted publicly, and providers only revoke keys found by scanners
- **D.** Live-mode keys outlive test-mode keys by design, since production credentials carry much longer validity windows by default

> **Answer:** B

### Q3. A build only needs to create Stripe charges and read customers. What does this module direct for the key?

- **A.** Use a restricted key limited to the operations the build actually uses, since scoped variants shrink the blast radius  ✅
- **B.** Use the full sk_live key instead, since restricted keys are still a beta feature that can break silently on version upgrades
- **C.** Use the publishable key server-side, since pk_ keys can create charges when called from a trusted backend
- **D.** Use two full keys, one per operation, since duplication is how Stripe expects builders to separate concerns

> **Answer:** A

### Q4. A builder asks the difference between an OAuth access token and the refresh token beside it. Which answer matches this module?

- **A.** They are interchangeable formats of the same grant, and providers issue both only for backward compatibility
- **B.** The access token is the long-lived secret and the refresh token expires quickly, so storage priorities follow that order
- **C.** Access tokens authenticate apps while refresh tokens authenticate machines, mirroring the key versus account split
- **D.** The access token is short-lived permission to act as a user; the refresh token mints new access tokens indefinitely  ✅

> **Answer:** D

### Q5. Two tokens leak: one access token, one refresh token. How does this module compare the two incidents?

- **A.** The access token gives a bounded window of abuse; the refresh token gives standing access until revoked  ✅
- **B.** The incidents are equivalent, since both tokens authenticate the same user against the same provider scopes
- **C.** The access token is worse, since it is the credential actually presented to APIs on every single request
- **D.** Neither matters much, since OAuth providers detect token reuse automatically and kill both within minutes

> **Answer:** A

### Q6. An AI-generated auth flow stores refresh tokens in localStorage. What does this module say about that choice?

- **A.** It is the standard pattern, since modern browser storage is sandboxed per origin and fully inaccessible to any injected scripts
- **B.** Any script injection reads them and standing account access walks out the door; refresh tokens belong server-side, encrypted  ✅
- **C.** It is acceptable when tokens are base64 encoded, since encoding prevents scripts from recognizing token formats
- **D.** It is a performance issue rather than a security one, since localStorage reads add latency to every request

> **Answer:** B

### Q7. A file named service-account.json sits in a project folder. Why does this module flag this setup as fatally easy to get wrong?

- **A.** JSON parses slowly at runtime, so file-based credentials create the startup latency that pushes teams to hardcode
- **B.** The filename collides with framework conventions, so build tools overwrite it silently during deployment
- **C.** It is a machine identity as a committable file sitting in the project: one git add -A later it is in history  ✅
- **D.** Service accounts require manual renewal monthly, so file-based storage guarantees expiry outages eventually

> **Answer:** C

### Q8. A leaked GCP service account file had the editor role on the whole project. How does this module size that incident?

- **A.** A broad-role service account is a master key to infrastructure: compute, storage, and role escalation, not just one API  ✅
- **B.** Moderate: service accounts cannot touch storage buckets, so the leak is bounded to compute resources only
- **C.** Minor: GCP throttles service account traffic coming from unfamiliar IP addresses, which contains any real abuse quickly
- **D.** Depends on billing: free-tier projects expose nothing of value regardless of what role the account carried

> **Answer:** A

### Q9. A postgres connection string appears in a frontend bundle. What does this module call this?

- **A.** A tolerable exposure, since connection strings without the port number cannot ever be used from outside the project VPC
- **B.** A styling problem, since credentials inside bundles are minified far beyond recognition by any human reader
- **C.** A rate-limiting concern, since browsers opening database connections exhaust the connection pool first
- **D.** A full database compromise: the bundle is public, and the string carries user, password, host, and database together  ✅

> **Answer:** D

### Q10. A builder renames DATABASE_URL to NEXT_PUBLIC_DATABASE_URL to fix a build error. What did that change actually do?

- **A.** Nothing visible to users, since the prefix only controls which server process can read the variable at runtime
- **B.** It shipped the entire database to every visitor: the public prefix embeds the variable in the browser bundle  ✅
- **C.** It moved the variable to edge runtime scope, which improves latency while keeping the value server-side
- **D.** It encrypted the value for transport, since public prefixes signal the bundler to apply obfuscation first

> **Answer:** B

### Q11. A team publishes their TLS certificate publicly and panics. What distinction does this module apply?

- **A.** The certificate is public by design; the private key is the secret, and knowing which half is which is table stakes  ✅
- **B.** Both halves are secret, and a published certificate requires the same emergency response as a leaked key
- **C.** Neither half is secret in modern TLS, since certificate transparency logs already publish everything anyway, keys included
- **D.** The certificate is secret and the private key is public, which is why servers present the key during handshakes

> **Answer:** A

### Q12. This module says a leaked signing key can be worse than a leaked API key in one specific way. Which way?

- **A.** Signing keys cost more to reissue, since certificate authorities charge a fee for every replacement that they process
- **B.** Signing keys leak more often, since their file formats are larger and easier for scanners to spot in repos
- **C.** API keys stop working when rotated, but signing keys cannot be rotated at all once they reach production
- **D.** Impersonation can be invisible: someone signs as you, and unlike API key abuse, you cannot always tell it happened  ✅

> **Answer:** D

### Q13. A webhook endpoint processes Stripe events without checking the signing secret. What risk does this module name?

- **A.** Duplicate processing, since unverified endpoints receive each event twice under the Stripe retry semantics
- **B.** Latency, since skipping verification removes the checksum step that keeps the payload parsing pipeline efficient
- **C.** Forged events: the endpoint trusts anything shaped like a webhook, and signing secrets exist to be checked, not just stored  ✅
- **D.** Version drift, since signature checks are how Stripe communicates its API version changes to the endpoint

> **Answer:** C

### Q14. An attacker obtains a JWT signing secret. What can they now do, according to this module?

- **A.** Read historical tokens only, since JWT secrets decrypt past sessions but cannot create new ones on their own
- **B.** Mint sessions for any user: forged tokens validate correctly, quieter and often worse than a stolen API key  ✅
- **C.** Nothing without the refresh token store, since JWTs are only half of a credential and useless alone in practice
- **D.** Slow the auth service down, since forged tokens fail validation and consume verification compute doing so

> **Answer:** B

### Q15. Why does this module say abuse of a leaked refresh token is especially hard to spot?

- **A.** The abuse looks like legitimate user traffic: valid tokens, normal endpoints, nothing anomalous in the request shape  ✅
- **B.** Because refresh calls bypass logging infrastructure, since token endpoints are excluded from the standard log pipelines
- **C.** Because providers hide refresh activity from dashboards, treating token flows as internal implementation detail
- **D.** Because the tokens rotate themselves hourly, so investigators can never establish which token performed an action

> **Answer:** A

### Q16. A production error page prints the full config object when the database is unreachable. Which leak path from this module is this?

- **A.** The commit path, since error pages are generated at build time and captured directly into the repository history
- **B.** The sharing path, since error pages are a distribution channel equivalent to pasting secrets into chat
- **C.** The creation path, since configs that reach error output were provisioned with excessive permissions
- **D.** Error messages that print config: connection strings escape through the very output users and crawlers see  ✅

> **Answer:** D

### Q17. You inherit a codebase and want a secrets inventory. Which prompt matches the directing pattern in this module?

- **A.** Delete every credential you find and regenerate them all, since a clean slate beats an inventory of unknowns
- **B.** Count the secrets and report a total, since volume is the metric that determines the audit approach to take
- **C.** List every secret by type: what it protects, whether it expires, and what abuse would look like for each one  ✅
- **D.** Encrypt every string that looks random, since entropy-based detection is how inventories reach completeness

> **Answer:** C

### Q18. You direct AI to set up a Stripe integration with a restricted key. What accountability does this module add to the prompt?

- **A.** Ask the model to benchmark the restricted key against the full key, since performance parity is what justifies restriction
- **B.** Tell me exactly which permissions you enabled and why, so the scope decision is visible and reviewable, not silent  ✅
- **C.** Ask the model to store the permission list in the database, since runtime records outlast configuration files
- **D.** Request a second restricted key as a backup, since scoped keys fail more often and need a standby kept ready

> **Answer:** B

### Q19. You are directing AI to implement OAuth token storage. Which instruction matches this module?

- **A.** Refresh tokens server-side and encrypted, access tokens short-lived and in memory, and nothing in localStorage  ✅
- **B.** Both tokens in localStorage with an expiry wrapper, since client-side storage keeps the auth flow stateless
- **C.** Both tokens in cookies without flags, since cookie transport is encrypted by TLS and needs no further care
- **D.** Access tokens in the database and refresh tokens in memory, since the rarely used token belongs in fast storage

> **Answer:** A

### Q20. You ask AI to audit webhook security across a project. What does this module say the audit must show you?

- **A.** The retry configuration per endpoint, since redelivery windows are where webhook security actually lives
- **B.** The average payload size per endpoint, since oversized events are the signature of forged webhook traffic
- **C.** The uptime of each endpoint, since availability is what webhook providers measure when scoring their integrations
- **D.** Each handler and its verification line: every endpoint checks the signing secret before trusting the payload  ✅

> **Answer:** D

### Q21. An audit finds a full-permission Stripe key, unencrypted Google refresh tokens, a committed service account file, and unverified webhooks. How does this module order the fixes?

- **A.** Alphabetically by service name, since consistent ordering prevents fixes from being skipped under pressure
- **B.** Webhooks first in every case, since forgery risks always outrank credential exposure in severity models like this one
- **C.** By blast radius: rotate and restrict the payment key, revoke and reissue the service account, encrypt tokens, verify webhooks  ✅
- **D.** By age of the finding, since the oldest exposure has leaked the longest and should therefore always go first

> **Answer:** C

### Q22. A builder runs five projects on one OpenAI API key. What does this module recommend instead, and why?

- **A.** One key per model family, since separating by capability tier is how providers expect usage to be divided
- **B.** One key per project, so a leak is isolated to one project and revocable without breaking the other four  ✅
- **C.** Keep the single key but raise its rate limit, since higher headroom absorbs any abusive traffic a leak invites
- **D.** Rotate the shared key weekly across all projects, since frequency compensates for the shared blast radius

> **Answer:** B

### Q23. A builder is choosing between a GitHub classic personal access token and a fine-grained token for a deploy script. What does this module direct?

- **A.** The fine-grained token with expiry: scoped to the one repo and the permissions needed, instead of everything forever  ✅
- **B.** The classic token, since fine-grained tokens cannot push commits and deploy scripts always need push rights
- **C.** Either token works identically, since GitHub normalizes both types into the same permission set internally
- **D.** Neither: deploy scripts should authenticate with the account password itself, since tokens add an extra layer that can leak

> **Answer:** A

### Q24. A scanner finds an id_rsa file committed to a repo two years ago. What does this module say about private keys and repos?

- **A.** Two-year-old keys have aged out, since SSH keys stop authenticating after eighteen months without renewal
- **B.** The finding is low priority if the repo is private, since visibility settings neutralize committed key material
- **C.** The key format is harmless without the matching config file, so the exposure depends on what sat beside it
- **D.** Private keys are generated where used and never committed; a committed key is a leaked key, whatever its age  ✅

> **Answer:** D

### Q25. Looking across this whole module, what is the governing principle of the secrets landscape?

- **A.** Volume is the enemy: the goal is reducing the number of secrets to a handful, whatever their types happen to be
- **B.** Provider trust is the foundation: choose reputable services and their default credential handling is sufficient
- **C.** Handle by type, not habit: know what each secret protects, how long it lives, what abuse looks like, and scope it narrowly  ✅
- **D.** Encryption solves the landscape: any secret stored encrypted is handled correctly regardless of its category

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/107142727_
