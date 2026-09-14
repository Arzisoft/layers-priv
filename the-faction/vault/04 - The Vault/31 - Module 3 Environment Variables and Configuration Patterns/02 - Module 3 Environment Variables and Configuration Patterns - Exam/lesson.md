---
course: "The Vault"
module: "Module 3: Environment Variables and Configuration Patterns"
lesson: "Module 3: Environment Variables and Configuration Patterns — Exam"
type: "course_quiz"
post_id: 107142731
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142731"
updated: "2026-09-10T19:58:12Z"
---

# Module 3: Environment Variables and Configuration Patterns — Exam

> Exam for **Module 3: Environment Variables and Configuration Patterns** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder asks why the same codebase should run locally, in preview, and in production without edits. Which principle from this module answers that?

- **A.** Continuous deployment: pipelines rebuild the code per stage, and the rebuild step is what adapts the code to each deploy target
- **B.** Framework convention: modern frameworks detect their hosting stage and rewrite their own settings to match it
- **C.** Branch parity: keeping one long-lived branch per environment is what lets a codebase serve several stages at once
- **D.** The twelve-factor approach: code is the same everywhere and config differs per deploy, read from the environment at runtime  ✅

> **Answer:** D

### Q2. A teammate describes the .env file as "where our secrets are stored, like a vault." How does this module correct that?

- **A.** The description is right: .env files encrypt their contents on save, which is what qualifies them as storage
- **B.** A .env file is a local convenience, and a plaintext one: it exists so you skip manual exports, not to be a storage system  ✅
- **C.** The description undersells it: .env files sync across machines through the framework, making them a true form of team storage
- **D.** The file is storage only when named .env.local, since the local suffix is what activates protected handling

> **Answer:** B

### Q3. A new collaborator clones the repo and asks what values they need to run the app. Which artifact does this module say should answer them?

- **A.** The .env.example file: the same keys the app needs, with no values, committed so collaborators know what to set without seeing yours  ✅
- **B.** The most recent .env file, shared over a direct message so the collaborator starts from working values immediately
- **C.** The deploy platform dashboard, since production settings are the authoritative list new collaborators should copy from
- **D.** The framework config file, since next.config.js is where a well-run project centralizes its secret values by convention

> **Answer:** A

### Q4. A builder adds NEXT_PUBLIC_ to a variable to silence a build warning. What does this module say the prefix actually does?

- **A.** It marks the variable as validated, telling the framework the value passed the startup checks and can load
- **B.** It restricts the variable to public pages, keeping it out of any route that sits behind authentication
- **C.** It embeds the value into the client bundle at build time: a declaration that this value is public forever  ✅
- **D.** It moves the variable into edge runtime scope, trading a little latency for stronger isolation guarantees

> **Answer:** C

### Q5. The browser console says an API key variable is undefined, and the quick fix on offer is a public prefix. What does this module direct instead?

- **A.** Apply the prefix but obfuscate the value first, since encoded public variables keep their secrecy in the bundle
- **B.** Move that logic server-side: the variable is undefined in the browser because a secret has no business being there  ✅
- **C.** Downgrade the framework version, since undefined env vars in the browser are a regression in recent releases
- **D.** Inline the key directly for now and remove it right after launch, since temporary exposure during testing is contained

> **Answer:** B

### Q6. A builder wants to put a TLS certificate blob and runtime feature flags into env vars. What does this module advise?

- **A.** Neither fits: env vars suit small per-deploy strings; certificates get mounted or fetched, and runtime flags need a service  ✅
- **B.** Both fit: env vars accept any string length, and flags read from the environment update instantly at runtime
- **C.** The certificate fits but flags do not, since binary-ish blobs are static while feature flags change far too often to configure
- **D.** Flags fit but the certificate does not, for size reasons alone; a split certificate across several vars works fine

> **Answer:** A

### Q7. A preview deploy for an open pull request runs with production database credentials. How does this module describe that state?

- **A.** Standard practice, since previews exist to test against real data and synthetic environments hide all the real bugs
- **B.** A minor inefficiency, since preview traffic is low enough that production impact stays within noise levels
- **C.** Safe when the repo is private, since preview URLs are unguessable and gated by the platform login already
- **D.** A production breach waiting on a pull request: environments are separate trust zones and never share credentials  ✅

> **Answer:** D

### Q8. This module says variable names should document the trust decision. What does that look like in practice?

- **A.** Server-only secrets get plain names like STRIPE_SECRET_KEY; browser-safe values carry the public prefix: the name says which  ✅
- **B.** Every variable carries a SECRET_ prefix so the scanners can find them all quickly, whatever their exposure level happens to be
- **C.** Variables are numbered by sensitivity tier, with documentation mapping each number to its exact handling requirements
- **D.** Names stay short and generic like KEY1 and URL2, since descriptive names advertise targets to anyone reading the bundle

> **Answer:** A

### Q9. An app crashes at first use of a missing key, three layers deep in a request handler. What pattern does this module say was skipped?

- **A.** Retry logic: transient env var reads fail under load, and requests should re-read the environment until success
- **B.** Error suppression: production apps should default missing keys to empty strings so requests degrade gracefully
- **C.** A single config module that reads env vars at startup and fails loudly, with a clear message, if a required key is missing  ✅
- **D.** Framework upgrade discipline: modern versions inline env values at build time, which removes these runtime failures entirely

> **Answer:** C

### Q10. Local .env values work, but the deployed app cannot find its keys. What step from the workflow in this module is missing?

- **A.** Committing the .env file to the deploy branch, since platforms read their configuration from the repository contents directly
- **B.** Mirroring the values into the platform env settings, scoped per environment: the deploy does not read your local file  ✅
- **C.** Renaming variables to lowercase, since hosting platforms normalize environment variable names on ingestion
- **D.** Restarting the local dev server, since platform deploys inherit their environment from the last local process

> **Answer:** B

### Q11. Six months in, collaborators keep asking for secrets in Slack during onboarding. Which hygiene failure does this module point to?

- **A.** A stale .env.example: keys were added and the example was not updated, so onboarding became secret-sharing over chat  ✅
- **B.** Missing platform access: collaborators should read values from the production dashboard on their first day
- **C.** Absent documentation culture: the wiki should hold the current secret values for exactly this situation
- **D.** Overactive gitignore: the .env file cannot reach the repo, which is exactly what forces values through side channels

> **Answer:** A

### Q12. A review finds an OpenAI key pasted directly into next.config.js. Why does this module treat framework config files as the wrong place?

- **A.** Framework configs are parsed twice per build, so values in them double their exposure window in process memory
- **B.** Framework configs cannot read strings, only booleans and numbers, so pasted keys break type checking
- **C.** Framework configs are ignored during production builds, so pasted keys silently vanish from the deploy
- **D.** Config files are code and get committed like code: they may reference env vars, but they never contain values  ✅

> **Answer:** D

### Q13. process.env is read directly in forty files across a codebase. What does this module say about that pattern?

- **A.** It is idiomatic: reading the environment at the point of use keeps modules independent and avoids tight coupling
- **B.** Nobody can list what the app needs: the single config module exists to keep the whole secret surface listable  ✅
- **C.** It is a performance win, since distributed reads let the runtime cache environment access per module
- **D.** It only matters for TypeScript projects, where untyped env reads defeat the compiler; JavaScript is fine

> **Answer:** B

### Q14. A .env file was committed three weeks ago; the .gitignore rule came later. What does this module say the fix is?

- **A.** Rotation: history holds every secret the file contained, so each one is leaked and gets replaced, not just ignored  ✅
- **B.** Adding the gitignore rule and a fresh commit, since ignore rules apply retroactively to files already tracked
- **C.** Making the repo private, since visibility controls neutralize whatever the commit history happens to contain
- **D.** Deleting the file in a new commit, since removal from the current working tree removes it from what fresh clones receive

> **Answer:** A

### Q15. You are starting a fresh project. Which setup prompt matches the directing pattern in this module?

- **A.** Generate the data model first and add configuration hygiene once the schema stabilizes, to avoid churn in the example file
- **B.** Create a .env file with placeholder secrets and commit it, so the repo carries a working template from the first day
- **C.** A .gitignore for .env files first, a .env.example with every key, no values, and a config module validating at startup  ✅
- **D.** Configure the deploy platform first and pull its values into local .env files, so production is the source of truth

> **Answer:** C

### Q16. You direct AI to audit the env vars in a project. Per this module, what is the audit checking about public prefixes?

- **A.** That prefixed variables are alphabetized in the example file, since ordering is what keeps audits repeatable
- **B.** That every value uses the prefix, since consistency across variables simplifies the deployment pipeline
- **C.** That prefixes match the framework version, since prefix conventions change between major releases
- **D.** That each prefixed variable is truly safe to be public, and that no secret would reach the browser bundle  ✅

> **Answer:** D

### Q17. You are wiring Stripe across environments. Which instruction matches the separation this module requires?

- **A.** Test keys in development and preview, live keys only in production, all read from platform env settings, never hardcoded  ✅
- **B.** Live keys everywhere, since test mode diverges from production behavior and hides real integration bugs until launch day
- **C.** Test keys everywhere including production, promoted to live keys only after the first real customer complains
- **D.** One shared restricted key across all environments, since scoping permissions substitutes for separating stages

> **Answer:** A

### Q18. Production crashes with an undefined API key that works locally. Which diagnostic prompt matches this module?

- **A.** Delete and recreate all env vars on the platform, since bulk recreation clears whatever state caused the mismatch
- **B.** Add a fallback default value in code so production stops crashing, then investigate when time permits
- **C.** Trace how the variable flows from platform settings to the code, and find where the name or the scope mismatches  ✅
- **D.** Roll back to the last working deploy and freeze configuration changes until the next scheduled release window

> **Answer:** C

### Q19. A builder deploys to Vercel and asks what env var capabilities to use. Which summary matches this module?

- **A.** Vercel injects all variables into the browser automatically, so naming conventions are cosmetic on that platform
- **B.** Scope variables to development, preview, and production; mark sensitive values write-only; pull remote values locally via the CLI  ✅
- **C.** Vercel only supports a single shared environment tier, so all stage separation has to happen entirely in application code instead
- **D.** Store variables in a vercel.json file in the repo, since file-based configuration is the platform's supported path

> **Answer:** B

### Q20. In env var terms, how does this module divide the Supabase credentials?

- **A.** The anon key and URL are browser-safe and may be prefixed; the service role key and database URL are server-only, never prefixed  ✅
- **B.** All Supabase values are browser-safe, since row level security makes every credential effectively public by design
- **C.** All Supabase values are server-only, since no database-adjacent string can ever be safely exposed to a client
- **D.** The service role key may be prefixed in staging builds, since non-production exposure carries no real risk at all

> **Answer:** A

### Q21. A builder asks how Netlify and Railway handle the separation this module requires. Which answer fits?

- **A.** Neither platform separates environments, which is why this module recommends a single production-only workflow there
- **B.** Both platforms share one variable pool across all their deploys, relying on naming conventions for separation
- **C.** Netlify separates only paid tiers, and Railway requires a plugin, so separation is effectively enterprise-only
- **D.** Netlify scopes vars per deploy context and Railway per environment with references; the same discipline applies  ✅

> **Answer:** D

### Q22. A public-prefixed value was changed in platform settings, but the live site still shows the old one. A prefixed secret was also leaked. What does this module say about both?

- **A.** Both fix themselves on the next request, since prefixed variables are read fresh from the environment at runtime
- **B.** The first needs a support ticket and the second needs a takedown request, since both are platform-side issues in the end
- **C.** Prefixed values embed at build: changing one needs a rebuild, un-prefixing a leaked secret needs rotation, not renaming  ✅
- **D.** Both indicate cache misconfiguration, since env vars bypass the build and flow through the CDN cache layer instead

> **Answer:** C

### Q23. A team has grown to four builders with three environments, and local .env files are the only secret store. What does this module say?

- **A.** The setup scales indefinitely, since .env files replicate naturally as each new collaborator clones the whole repository
- **B.** Local files stop scaling when teams and environments multiply: this is the point where a secrets manager takes over  ✅
- **C.** The fix is a shared cloud drive holding the canonical .env, so every builder syncs the same file on pull
- **D.** The fix is committing an encrypted .env variant, since encryption removes the reason the file was ignored

> **Answer:** B

### Q24. One set of live keys is used across development, preview, and production "to keep things simple." What does this module call the consequence?

- **A.** Simplification of the audit trail, since one key means one usage stream and cleaner monitoring overall
- **B.** A modest convenience win that most teams keep, since stage separation matters mainly for the larger companies
- **C.** A cost optimization, since providers bill per key and consolidated usage reaches volume discounts sooner
- **D.** Every experiment becomes a production risk: a dev mistake spends live money and touches live customer data  ✅

> **Answer:** D

### Q25. Looking across this whole module, what is the governing principle of environment configuration?

- **A.** Convenience first: configuration should minimize keystrokes, since friction is what drives builders to hardcode
- **B.** Centralize in the framework: the config file is the home of configuration, secrets included, under version control
- **C.** Secrets live in the environment, split by stage, validated at startup, and never cross into the browser bundle  ✅
- **D.** Trust the platform: hosting providers manage configuration correctly by default, so local discipline is redundant

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/107142731_
