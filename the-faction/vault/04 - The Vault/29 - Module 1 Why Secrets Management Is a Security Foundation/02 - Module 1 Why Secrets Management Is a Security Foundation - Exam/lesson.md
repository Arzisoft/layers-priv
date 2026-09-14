---
course: "The Vault"
module: "Module 1: Why Secrets Management Is a Security Foundation"
lesson: "Module 1: Why Secrets Management Is a Security Foundation — Exam"
type: "course_quiz"
post_id: 107142723
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142723"
updated: "2026-09-10T19:56:42Z"
---

# Module 1: Why Secrets Management Is a Security Foundation — Exam

> Exam for **Module 1: Why Secrets Management Is a Security Foundation** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder asks whether a database connection string counts as a secret. What test does this module give?

- **A.** Whether the string is longer than twenty characters, since length is what separates identifiers from credentials in practice
- **B.** Whether someone who copies the string can act as you or your app: if presenting it grants access, it is a secret  ✅
- **C.** Whether the vendor labels it secret in the dashboard, since provider naming is the authoritative classification
- **D.** Whether the string appears in server code, since anything referenced by backend files is a secret by location

> **Answer:** B

### Q2. A teammate wants to treat a Supabase project URL and a Stripe publishable key with the same care as secret keys. What does this module say?

- **A.** They are configuration, not secrets: the string that authorizes action is the secret, and these are public by design  ✅
- **B.** They are secrets too, since anything a provider issues belongs in the same vault with the same handling rules
- **C.** They become secrets at scale, since traffic volume is what eventually converts public identifiers into sensitive credentials
- **D.** They are more sensitive than secret keys, since public strings are the ones attackers actually get to see first

> **Answer:** A

### Q3. Before storing a new key, this module says to answer one question first. Which question, and why?

- **A.** How long the key remains valid, since expiry dates are the property that determines just how much protection a key deserves
- **B.** Which teammate created it, since accountability for creation is the record that matters most in an incident
- **C.** What its blast radius is: what the key can reach if leaked, because that knowledge decides how carefully it gets handled  ✅
- **D.** What it costs the provider to reissue, since replacement price is the practical measure of how careful to be

> **Answer:** C

### Q4. A builder is about to put a Supabase service role key into client-side code. What does this module say that key reaches if leaked?

- **A.** Every row and every table, read and write: it bypasses row level security entirely, which is why it never ships client-side  ✅
- **B.** Only the tables the current user can already see, since row level security still filters every request it receives
- **C.** Only the auth schema, since Supabase isolates the service role key from application data by default separation
- **D.** Nothing at all while the project is on a free tier, since destructive operations require a billed organization

> **Answer:** A

### Q5. A weekend side project leaks an OpenAI API key. What does this module identify as the direct consequence?

- **A.** Model quality degradation, since shared keys split rate limits and slow every response the project makes
- **B.** A licensing violation, since AI provider terms prohibit key exposure and the account faces contract review
- **C.** Little consequence, since AI keys expire hourly by default and leaked ones die before abuse can begin
- **D.** Someone else's traffic on your bill: usage-billed keys are direct financial targets, small project or not  ✅

> **Answer:** D

### Q6. A key is pushed to a public repo and deleted in the very next commit. How does this module assess the situation?

- **A.** The fast deletion contains the leak, since scanners only index repositories on a daily crawl cycle at most
- **B.** The key is compromised the moment it lands: bots scan public commits within minutes and history keeps the string  ✅
- **C.** Risk depends on repo popularity, since scanners prioritize starred projects and ignore the smaller ones for weeks at a time
- **D.** The key is safe if the repo is squashed within a day, since squashing rewrites what the scanners captured

> **Answer:** B

### Q7. A builder removes a hardcoded key from the code and pushes the fix. Why does this module say the exposure continues?

- **A.** Git history preserves the key in every prior commit, so anyone with the repo, and every scanner, still has it  ✅
- **B.** Because compiled bundles cache the key for thirty days, and CDN copies of the app keep serving the older build
- **C.** Because the provider mirrors old keys server-side, and mirrored copies stay valid until support is contacted
- **D.** It does not continue: removal from the current code is exactly what revocation means in a git-based workflow

> **Answer:** A

### Q8. This module retells Uber's 2016 breach. What lesson does it draw from how that incident began?

- **A.** Sophisticated zero-day exploits drive major breaches, so patch cadence matters more than credential handling
- **B.** Cloud providers were at fault, since infrastructure vendors are responsible for credentials used against them
- **C.** The cause was dull: credentials in a repo unlocked data on 57 million people; readable secrets are the norm  ✅
- **D.** Only companies at ride-share scale attract credential attacks, so smaller teams can prioritize differently

> **Answer:** C

### Q9. Toyota disclosed that an access key sat in a public repo for five years. What point does this module make with that example?

- **A.** Five years without abuse proves scanners miss most keys, so leak speed claims are overstated for real-world projects
- **B.** Large enterprises handle secrets worse than small teams, since process overhead hides simple mistakes longer
- **C.** Key age determines risk, so secrets under a year old can safely wait for the next scheduled cleanup pass
- **D.** Exposure persists silently: a leaked secret stays live until someone finds it, and the timeline can run for years  ✅

> **Answer:** D

### Q10. This module cites Codecov's 2021 incident. What made one leaked credential so damaging there?

- **A.** It cascaded: one credential became an attack on thousands of downstream customers' CI secrets, multiplying the blast radius  ✅
- **B.** The credential was a root cloud account, since only top-level infrastructure keys can cause multi-company damage
- **C.** The company had no backups, since data loss rather than credential reach is what turned the incident severe
- **D.** The leak was announced publicly before rotation, since disclosure timing is what determined the damage done

> **Answer:** A

### Q11. A builder says their project is too small to worry: 'nobody targets a toy app.' What is this module's response?

- **A.** Correct: attackers research targets before acting, and unknown projects fall below the effort threshold
- **B.** Correct for the first year, since new projects enjoy a grace period before appearing in scanner indexes
- **C.** Bots do not check your star count: a leaked key on a toy project pays the same crypto miner as a funded startup's  ✅
- **D.** Partly correct: only keys tied to payment products draw real abuse, so free-tier service keys are always safe to expose

> **Answer:** C

### Q12. In the secret lifecycle this module lays out, which failures belong to the storage stage?

- **A.** Keys created with broader permissions than the build needs, since scope decisions happen when keys are born
- **B.** Hardcoding keys in source, committing .env files, pasting keys into docs and chats: secrets out of place  ✅
- **C.** Secrets appearing in logs and error messages, since output channels are where stored secrets escape to
- **D.** Nobody knowing where a key is used, since usage tracking is the record the storage stage exists to maintain

> **Answer:** B

### Q13. An app prints its config object, keys included, into error messages when requests fail. Which lifecycle stage is leaking?

- **A.** Creation, since keys that reach error output were issued with permissions broader than the application needed
- **B.** Sharing, since error messages are a distribution channel and distribution is what the sharing stage governs
- **C.** Rotation, since keys old enough to appear in logs are keys that outlived their scheduled replacement date
- **D.** Use: the app presents secrets at runtime, and runtime is where they escape into logs and error messages  ✅

> **Answer:** D

### Q14. A teammate asks for the Stripe secret key and a builder pastes it into Slack. What does this module say about that channel?

- **A.** Slack and email are searchable archives of everything pasted into them; secrets move through secret channels or not at all  ✅
- **B.** Slack is acceptable for keys still in test mode, since test-mode credentials carry no blast radius that is worth protecting
- **C.** The paste is fine if deleted within the hour, since chat retention windows are shorter than scanner cycles
- **D.** Direct messages are safe while channels are not, since visibility scope is what defines a secret channel in practice

> **Answer:** A

### Q15. A project has never rotated any key since launch two years ago. What risk does this module attach to that?

- **A.** Compliance fines accrue automatically, since every major privacy framework sets a thirty-day maximum key age
- **B.** One old leak stays live forever: any copy that escaped in two years still works today, because nothing ever expired it  ✅
- **C.** Provider throttling, since services degrade performance on keys that have not been refreshed on the schedule vendors set
- **D.** No risk on its own, since rotation only matters after a confirmed incident makes the old keys look suspect

> **Answer:** B

### Q16. A team suspects a leak but nobody will revoke the key because nobody knows what uses it. Which lifecycle failure is this?

- **A.** A creation failure, since keys issued without expiry dates are the reason revocation decisions become frightening
- **B.** The inventory problem: nobody tracked where the secret is used, so nobody dares kill it, and the leak stays live  ✅
- **C.** A sharing failure, since keys distributed through proper channels always carry usage records with them
- **D.** A storage failure, since secrets kept in a manager rather than in code are the ones that become untraceable

> **Answer:** B

### Q17. A builder plans to ship fast now and add secrets management before the public launch. What does this module say about that sequencing?

- **A.** Sensible: secrets practices slow early iteration, and pre-launch hardening is when protection actually matters
- **B.** Sensible if the repo stays private until launch, since private repositories neutralize leaks during development
- **C.** The leak happens in the first commit, deploy, or generated file with a hardcoded key: it cannot be bolted later  ✅
- **D.** Sensible for solo builders, since the risks this course describes only begin once a second person joins the repo

> **Answer:** C

### Q18. Which standing instruction does this module tell you to give AI at the start of any integration build?

- **A.** Generate the fastest working example first, since security review is a separate later pass over the finished code
- **B.** Use a fresh key for each file generated, since key-per-file isolation limits what any single leak can ever reach
- **C.** Comment every single key with its creation date, since inline documentation is the foundation habit that pays off longest over time
- **D.** Read the key from an environment variable, never hardcode it, never print it, and add .env to .gitignore before anything else  ✅

> **Answer:** D

### Q19. While reviewing AI-generated integration code, what pattern does this module tell you to watch for?

- **A.** Placeholder keys hardcoded into examples, like a constant assigned an sk- string: models produce them happily  ✅
- **B.** Excessive comments around configuration, since verbose explanation is where generated code hides its mistakes
- **C.** Overuse of environment variables, since env-heavy code becomes unportable across deployment platforms
- **D.** Async patterns around key loading, since asynchronous configuration is the classic generated-code defect

> **Answer:** A

### Q20. You are about to start a client build. Which pre-build prompt matches the directing pattern in this module?

- **A.** Write the marketing page first, since public-facing copy determines which services the architecture will need
- **B.** Generate all API keys now, since collecting credentials before the design exists saves setup time later on
- **C.** Pick the newest model available, since generation quality is what ultimately determines how the secrets get handled downstream
- **D.** List every secret this architecture will need: each service, each key, what it protects, and its blast radius if leaked  ✅

> **Answer:** D

### Q21. A builder hardcodes a key 'just to test' and plans to fix it before committing. How does this module weigh that trade?

- **A.** It is standard practice, since test-phase shortcuts sit outside the window where secrets handling matters
- **B.** It is fine with a linter rule active, since automated checks reliably catch hardcoded keys before any commit
- **C.** The test commit becomes the leak: the env var takes ninety seconds and the incident takes your weekend  ✅
- **D.** It depends on repo visibility, since hardcoded keys in private repositories carry no meaningful risk at all

> **Answer:** C

### Q22. A key is found in an old commit. One teammate says delete the file; the other says rotate the key. What does this module direct?

- **A.** Delete first and monitor usage for a week, since abnormal traffic patterns are what confirm whether rotation is needed
- **B.** Rotate: a secret found in code or history is a leaked secret, and deletion does nothing about the copies already taken  ✅
- **C.** Delete and force-push a cleaned history, since rewriting the repository removes what the scanners captured
- **D.** Neither: file an issue and schedule the cleanup, since untriggered exposures can wait for the next sprint

> **Answer:** B

### Q23. A builder confuses the Supabase anon key and service role key while directing AI to build the frontend. Why does this module treat that mix-up as severe?

- **A.** One is public by design, the other bypasses your security rules: confusing them ships a master key to every browser  ✅
- **B.** The two keys use different encodings, so swapping them breaks authentication and takes the whole application offline
- **C.** Anon keys expire faster than service keys, so the swap creates outages when the shorter-lived key times out
- **D.** Supabase bills service key traffic at a higher rate, so the swap mainly shows up as an unexpected invoice

> **Answer:** A

### Q24. A builder assumes GitHub's secret scanning makes carefulness optional, since Stripe and OpenAI auto-revoke reported keys. What does this module say?

- **A.** The assumption is sound: provider auto-revocation has made manual secrets discipline largely ceremonial for builders
- **B.** Scanning only covers enterprise accounts, so free-tier builders receive none of the protection being described
- **C.** Scanning exists to punish carelessness, since providers fine account owners for every key their scanners catch
- **D.** The net is real but partial: it exists because leaks are common and does not catch everything; discipline still carries the load  ✅

> **Answer:** D

### Q25. Looking across this whole module, what is the governing principle of secrets management as a foundation?

- **A.** Secrets safety is a tooling purchase: adopt a vault product early and the handling habits become unnecessary
- **B.** Secrets safety is about reaction speed: leaks are inevitable, so detection and response deserve all of the investment
- **C.** Every secret has a blast radius: it lives outside code from minute one, and once exposed it is rotated, not deleted  ✅
- **D.** Secrets safety is a scale concern: the practices in this course begin to matter once a project has real users

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/107142723_
