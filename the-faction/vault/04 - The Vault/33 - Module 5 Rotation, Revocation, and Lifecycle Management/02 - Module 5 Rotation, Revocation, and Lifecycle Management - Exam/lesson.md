---
course: "The Vault"
module: "Module 5: Rotation, Revocation, and Lifecycle Management"
lesson: "Module 5: Rotation, Revocation, and Lifecycle Management — Exam"
type: "course_quiz"
post_id: 107142737
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142737"
updated: "2026-09-10T20:01:29Z"
---

# Module 5: Rotation, Revocation, and Lifecycle Management — Exam

> Exam for **Module 5: Rotation, Revocation, and Lifecycle Management** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder argues an untouched key is safe because "nothing has happened to it in two years." How does this module reframe that?

- **A.** The builder is right: incident-free time is evidence of safety, and rotation would only introduce change risk
- **B.** Risk accumulates with time: every deploy, log line, and teammate laptop is another possible copy of that key  ✅
- **C.** Age matters only for payment keys, since financial credentials are the ones attackers bother to collect
- **D.** The key is safe if it was created after the provider added encryption, since modern keys resist copying

> **Answer:** B

### Q2. This module describes a secret that never changes as a particular kind of bet. Which one?

- **A.** A hedged bet, since providers monitor their old keys more closely and offset the risk the key holder carries
- **B.** A cheap bet, since the odds of any single key leaking in any single year round to zero in practice
- **C.** A one-time bet, made at creation, that the key generation process itself produced a strong value
- **D.** A bet that no copy ever escaped, renewed daily, forever: each day extends the wager without new evidence  ✅

> **Answer:** D

### Q3. A teammate asks for the scheduled rotation pattern in order. Which sequence matches this module?

- **A.** Create the new credential, deploy it everywhere the old one was used, verify, then revoke the old one  ✅
- **B.** Revoke the old credential, create the new one, deploy it everywhere, then verify the app recovered
- **C.** Announce a maintenance window, revoke both credentials, create a fresh one, then redeploy the app
- **D.** Verify current usage, revoke the old credential, wait a full day for the caches, then create the new one

> **Answer:** A

### Q4. A builder asks why two credentials briefly coexist during rotation. What does this module point to?

- **A.** A flaw in the pattern, tolerated only because most providers cannot fully delete keys quickly enough to avoid it
- **B.** A strict compliance requirement, since auditors need both keys live to confirm that the rotation actually happened
- **C.** Overlap by design: providers like Stripe with rolled keys and cloud IAM with two access keys allow for this dance  ✅
- **D.** A caching artifact, since revoked keys keep working until the provider CDNs expire their previously cached copies

> **Answer:** C

### Q5. This module calls revocation the emergency brake. What preparation does it say matters before any emergency?

- **A.** Knowing where the revoke button is in each provider dashboard before the day you need it in a panic  ✅
- **B.** Holding a spare key for every provider in a printed binder, since dashboards fail during incidents
- **C.** Having a lawyer on retainer, since revocation decisions carry liability that builders should not accept alone
- **D.** Practicing on production monthly by revoking a live key unannounced, so the team stays calibrated

> **Answer:** A

### Q6. A key is confirmed leaked. How does this module reorder the rotation steps, and why?

- **A.** Same order as scheduled rotation, since the overlap pattern is designed to be safe in every possible situation
- **B.** Deploy the new key first and leave the old one alive for a full week, since attackers watch for sudden changes
- **C.** Skip rotation entirely and just quietly monitor usage, since revoking a watched key tips the attacker off too early
- **D.** Revoke first, accept the outage risk, then create and deploy the replacement: speed beats grace when someone else may hold the key  ✅

> **Answer:** D

### Q7. This module says the frightening question is never "how do I rotate this key." What is it instead, and what answers it?

- **A.** "Who approved this key," answered by the provider's billing history and the full account audit trail
- **B.** "What breaks if I do," answered by the inventory: every consumer of every secret, known in advance  ✅
- **C.** "Which provider issued it," answered by the key prefix conventions that most vendors publish
- **D.** "When does it expire," answered by the provider dashboard's validity column for each credential

> **Answer:** B

### Q8. A builder starts a secret inventory. Which fields does this module specify?

- **A.** Every secret, where it is stored, which systems consume it, when it was last rotated, and who owns it  ✅
- **B.** Every secret and its value, kept together so the inventory doubles as the backup of last resort
- **C.** Only production secrets and their costs, since development credentials sit outside lifecycle management
- **D.** The provider list alone, since per-key detail goes stale too fast for any inventory to stay honest

> **Answer:** A

### Q9. Nobody on a team has rotated a three-year-old key because nobody can predict the fallout. What does this module call this state?

- **A.** Rational prudence: keys with unknown consumers should never be touched until a leak forces the issue
- **B.** A provider failure, since vendors should publish which systems consume each key they have issued
- **C.** The inventory gap making keys immortal: nobody dares touch what nobody can predict, so old keys never die  ✅
- **D.** A staffing gap, since rotation of aged keys is specialist work that generalist builders should not attempt

> **Answer:** C

### Q10. A builder asks which rotations can come off the calendar entirely. What does this module answer?

- **A.** None: automation is a convenience layer, and every credential still needs its own quarterly manual pass anyway
- **B.** All of them: once any manager is adopted, every single stored secret rotates itself automatically by default
- **C.** Payment keys only, since financial providers are the only vendors that actually ship rotation automation today
- **D.** The ones providers manage: AWS rotating RDS credentials on schedule, short-lived tokens and workload identity rotating by design  ✅

> **Answer:** D

### Q11. The rotation runbook in this module starts before any new key is created. With what?

- **A.** Consulting the inventory: what consumes this secret, in which environments, and which settings hold it  ✅
- **B.** Notifying the provider, since undeclared rotations can trigger fraud detection on the account
- **C.** A full backup of the database, since credential changes are when data loss historically happens
- **D.** Freezing all deploys for the day, since parallel changes make rotation failures much harder to attribute

> **Answer:** A

### Q12. While creating a replacement credential, what opportunity does this module say rotation naturally presents?

- **A.** Renaming the key to match current conventions, since naming drift is the main cost of old credentials
- **B.** Tightening permissions: the new credential gets the same or narrower scope, never broader by habit  ✅
- **C.** Switching providers, since rotation moments are when vendor migrations cost the least attention
- **D.** Consolidating several keys into one, since fewer credentials always means a smaller attack surface

> **Answer:** B

### Q13. Right after revoking the old key, something unexpected breaks. What does this module say that break represents?

- **A.** Proof the rotation was premature, and reason to restore the old credential permanently while investigating
- **B.** A provider-side propagation bug, worth a support ticket before any further rotations are attempted
- **C.** A consumer the inventory missed: fix the consumer, and add it to the inventory so the next cycle knows it  ✅
- **D.** Normal turbulence that resolves on its own, since most consumers retry until a valid key succeeds

> **Answer:** C

### Q14. Why does this module insist on recording each rotation in the inventory afterward?

- **A.** The inventory gets better every cycle; skipping the record means the next rotation starts from archaeology again  ✅
- **B.** Because providers require rotation logs for full support eligibility, and unrecorded rotations void that assistance
- **C.** Because unrecorded rotations invalidate the audit log, forcing the manager to rebuild its history
- **D.** Because the record is legally required once a team passes five people, under standard contract terms

> **Answer:** A

### Q15. A builder revokes the old key before deploying the new one, during routine scheduled rotation. What does this module call this?

- **A.** The security-first order: accepting downtime on every single rotation is the honest price of taking secrets seriously
- **B.** A provider limitation, since platforms without dual-key support force exactly this sequence on builders
- **C.** A reasonable variation, since the order of the middle steps matters less than completing all of them
- **D.** A self-inflicted outage: scheduled rotation never needs downtime, because the overlap pattern exists for exactly this  ✅

> **Answer:** D

### Q16. After a "rotation," the old key still works because nobody revoked it. What does this module call this, and when does rotation actually end?

- **A.** A grace period: providers keep old keys alive intentionally, and rotation ends when the grace expires
- **B.** Rotation theater: both keys now live indefinitely, and rotation ends only when the old credential is dead  ✅
- **C.** Dual-key steady state: a valid end condition for providers that support multiple concurrent keys
- **D.** A verification gap: rotation ends when monitoring confirms the new key served its first production request

> **Answer:** B

### Q17. A collaborator with repo and dashboard access leaves the team on good terms. What does this module direct?

- **A.** Nothing, since good-terms departures carry no risk and rotation would signal distrust to the person leaving
- **B.** A six-month observation window, rotating only if the ex-collaborator joins a competitor in that time
- **C.** Offboarding is a rotation trigger, every time: the keys they could have seen outlive the trust otherwise  ✅
- **D.** Revoking their chat and email accounts only, since communication access is where real exposure lives

> **Answer:** C

### Q18. You want AI to build the secret inventory. Which prompt matches the directing pattern in this module?

- **A.** Every credential, where it is stored, every consumer, last rotation date, owner: output as a table for the private docs  ✅
- **B.** List the providers this project uses, since a vendor list is the inventory at the level busy builders actually maintain
- **C.** Find and print every secret value in the codebase, so the inventory doubles as the full recovery document too
- **D.** Estimate which keys are probably fine, so the inventory focuses its attention on the risky minority of keys

> **Answer:** A

### Q19. A key must be rotated now due to suspected exposure. Which AI-directed request matches this module?

- **A.** Draft an email to the provider requesting that they investigate before any action is taken on the client account
- **B.** Walk me through emergency revocation for this provider: what breaks the moment I revoke, and in what order do I restore service  ✅
- **C.** Generate a stronger replacement value first, since key strength is what failed if exposure is suspected here
- **D.** Search the logs for evidence of abuse first, since rotation before confirmation wastes a calm afternoon needlessly

> **Answer:** B

### Q20. You are offboarding a collaborator and direct AI to plan the rotations. What ordering does this module specify?

- **A.** Alphabetical by provider, since a mechanical order prevents skipped entries during a long rotation session
- **B.** Oldest key first, since age is the best available proxy for how widely a credential has been copied
- **C.** Cheapest first, since early wins build the momentum needed to finish the full offboarding list
- **D.** Highest blast radius first: every secret they could have seen, ranked by what each one reaches  ✅

> **Answer:** D

### Q21. A client's previous developer left on bad terms. In the module's scenario, how does the builder handle Stripe specifically?

- **A.** Stripe keys are skipped, since payment providers monitor abuse closely enough to make rotation redundant
- **B.** Stripe is rotated at midnight with the store offline, since payment keys cannot overlap safely
- **C.** Stripe rotates with overlap so checkout never blinks: the new key deploys before the old one dies  ✅
- **D.** Stripe support is called to freeze the account for a week while the other credentials rotate first

> **Answer:** C

### Q22. This module calls one Stripe dashboard detail "inventory gold." Which detail, and why?

- **A.** When each key was last used: live usage data that tells you which credentials still have consumers  ✅
- **B.** The key creation timestamps, since age is the field every rotation schedule is ultimately computed from
- **C.** The webhook delivery log, since event traffic is the truest map of which systems consume keys
- **D.** The team member list, since access records are what the inventory's owner column is built from

> **Answer:** A

### Q23. A builder sets expiry dates on their GitHub fine-grained tokens. What does this module say they gain?

- **A.** Nothing but reissue friction, since expiring tokens fail their pipelines at whatever moment they lapse
- **B.** Lower rate limits, since GitHub grants expiring tokens less capacity than the long-lived classic ones
- **C.** Regulatory alignment only, since expiry dates exist mainly to satisfy compliance frameworks rather than real practice
- **D.** A rotation reminder built into the credential itself: an expiring token forces the renewal an old key never asks for  ✅

> **Answer:** D

### Q24. How does a sync-tier manager (Doppler, Infisical) change the deploy step of rotation, per this module?

- **A.** It removes the need for verification, since synced values are guaranteed to be correct across all environments
- **B.** Deploy becomes one update: the manager pushes the new value everywhere, its activity log is the rotation record  ✅
- **C.** It adds an extra step, since the manager itself must be rotated first before any provider credential can change
- **D.** It makes rotation optional, since managed secrets are encrypted and encryption removes the aging problem entirely

> **Answer:** B

### Q25. Looking across this whole module, what is the governing principle of secret lifecycle management?

- **A.** Rotation is an enterprise ritual: small teams get more safety per hour from better storage than from rotation schedules
- **B.** Revocation should be rare: a well-stored secret never needs its lifecycle managed, only its access carefully controlled
- **C.** Exposure accumulates, cap it: rotate on schedule, overlapped, revoke first in crisis, keep the inventory enabling both  ✅
- **D.** Providers own the lifecycle: builders simply consume credentials and the vendors decide when those credentials change

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/107142737_
