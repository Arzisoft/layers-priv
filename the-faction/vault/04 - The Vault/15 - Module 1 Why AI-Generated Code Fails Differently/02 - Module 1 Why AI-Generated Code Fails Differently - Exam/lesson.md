---
course: "The Vault"
module: "Module 1: Why AI-Generated Code Fails Differently"
lesson: "Module 1: Why AI-Generated Code Fails Differently — Exam"
type: "course_quiz"
post_id: 106568625
space_id: 24302166
source: "https://the-faction.mn.co/posts/106568625"
updated: "2026-08-28T16:24:58Z"
---

# Module 1: Why AI-Generated Code Fails Differently — Exam

> Exam for **Module 1: Why AI-Generated Code Fails Differently** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. An auditor finds a single endpoint that builds SQL by concatenating user input. Given how AI-generated code fails, what should the very next audit action be?

- **A.** Search the entire codebase for the same pattern because AI replicates flaws across many files at once  ✅
- **B.** Patch that one endpoint and move on, since a single injection point is an isolated coding mistake here
- **C.** Rerun the dependency scanner, since concatenated SQL usually traces to an outdated database library
- **D.** Flag it as low severity, because one unparameterized query rarely reaches production data in practice

> **Answer:** A

### Q2. A founder proudly shows an auth middleware file named security.js and asks why the audit still flags authentication. What is the auditor checking that the file's existence does not answer?

- **A.** Whether the file's author holds any security credentials, since unqualified authors produce weaker middleware
- **B.** Whether the middleware is actually enforced on the routes that matter, not merely present in the project  ✅
- **C.** Whether the file is minified, since unminified security code is easier for attackers to read and bypass
- **D.** Whether the filename matches convention, since misnamed security files confuse future AI sessions badly

> **Answer:** B

### Q3. An AI-built codebase uses a password hashing approach that was standard a decade ago and is considered weak today. What failure pattern does this illustrate?

- **A.** Hallucinated security, where the code merely looks protective while performing no real function at all
- **B.** Missing defense-in-depth, where a single protective layer carries the entire weight of the system
- **C.** Training data leakage, where the model reproduces outdated practices that were common in its training data  ✅
- **D.** Cross-session drift, where standards vary widely because the model forgets what it applied in earlier sessions

> **Answer:** C

### Q4. A codebase imports a sanitize function at the top of a file, but tracing execution shows the function is never actually called before rendering user input. What pattern is this?

- **A.** Pattern replication, where one single weak sanitizer is copied unchanged into every file across the project
- **B.** Training data leakage, where the sanitizer reflects an insecure convention absorbed during model training
- **C.** Cross-session inconsistency, where one session imported the sanitizer and another forgot to wire it in
- **D.** Hallucinated security, where the shape of a protection is present but the protection does not actually run  ✅

> **Answer:** D

### Q5. An auditor deeply reviews one well-built module and is tempted to conclude the whole codebase shares its quality. Why is that inference unsafe for AI-generated code?

- **A.** Posture varies across sessions, so a strong module says nothing about the security of its neighbors  ✅
- **B.** Deep review of one module always misses the dependency vulnerabilities that live in shared libraries
- **C.** Well-built modules attract attackers, so the strongest code is paradoxically the most likely to be breached
- **D.** Module quality is random, so no amount of sampling could ever predict the quality of any other module

> **Answer:** A

### Q6. A feature protects a sensitive action with exactly one check, and that check lives in the browser. What did the AI most likely fail to build?

- **A.** A named security middleware file, without which the browser check cannot be registered onto the given route
- **B.** Defense-in-depth, the additional server-side and database layers that should back up the single client check  ✅
- **C.** A dependency lockfile, without which the browser check silently drifts as the packages update over time
- **D.** Session persistence, without which the single check fails intermittently under heavily load-balanced production traffic

> **Answer:** B

### Q7. A founder skipped an audit because the AI-generated code reads cleanly, is well commented, and looks professional. What is the name for the trap they fell into?

- **A.** Pattern replication, where clean formatting is itself copied across files to disguise weak logic beneath
- **B.** Training data leakage, where professional-looking comments are lifted directly from insecure public tutorials
- **C.** Missing defense-in-depth, where surface polish substitutes for the protective layers that were never built
- **D.** The false confidence effect, where fluent style triggers unearned trust regardless of the real security posture  ✅

> **Answer:** D

### Q8. Across one codebase, the auditor finds three different authentication styles in three areas built in separate sessions. Why does this specifically help an attacker?

- **A.** Multiple auth styles multiply the total code, and larger codebases are statistically more likely to be breached
- **B.** Three auth styles confuse the AI in future sessions, causing it to disable authentication across all of them
- **C.** Attackers only need the weakest of the three areas and inconsistent posture guarantees a weakest corner exists  ✅
- **D.** Differing styles break the dependency scanner, which then silently skips authentication libraries entirely

> **Answer:** C

### Q9. Why do traditional human-era code review checklists systematically miss the failure classes of AI-generated code?

- **A.** They assume flaws are isolated human mistakes, not patterns replicated at scale in security-shaped disguises  ✅
- **B.** Traditional checklists require automated tooling that predates the static analyzers vibecoders rely upon today
- **C.** Traditional checklists were written before HTTPS existed, so they omit every modern transport-layer concern
- **D.** They focus only on frontend code, leaving the backend and database layers entirely outside their review scope

> **Answer:** A

### Q10. An auditor's discipline is stated as evidence over impressions. In practice, what does honoring that discipline require when grading a codebase?

- **A.** Grading strictly on code readability, since clean code is measurable evidence and messy code is a clear red flag
- **B.** Accepting the founder's description of protections, since the builder has the most direct evidence of intent
- **C.** Tracing actual execution paths and backing every grade with findings, not the professional look of the code  ✅
- **D.** Weighting the model's own confidence, since a model that reports high certainty provides evidence of correctness

> **Answer:** C

### Q11. A model generates a rate limiter, configures it in one file, but never attaches it to any route. Which two failure patterns are jointly on display?

- **A.** Pattern replication and training data leakage, since the limiter config is copied from an insecure old tutorial
- **B.** Hallucinated security and missing defense-in-depth, since a protection exists in shape but never runs anywhere  ✅
- **C.** Cross-session drift and false confidence, since a later session removed the limiter that an earlier one wired in
- **D.** Training data leakage and pattern replication, since one outdated limiter pattern spread across the whole project

> **Answer:** B

### Q12. An auditor wants to know which areas of a codebase came from which generation sessions. What technique does the method call for?

- **A.** Running the dependency scanner per directory, since session boundaries align with package manifest changes
- **B.** Measuring comment density per file, since each session leaves a distinctive and traceable commenting fingerprint
- **C.** Asking the model to recall its previous sessions, since it retains a reliable log of the standards it applied
- **D.** Session archaeology through commit history and file dating, mapping which areas emerged from which sessions  ✅

> **Answer:** D

### Q13. Why does the method treat one confirmed insecure pattern as evidence of a family rather than an isolated incident?

- **A.** Because the AI reuses the patterns it establishes, stamping the same flaw into every file that shares the shape  ✅
- **B.** Because dependency vulnerabilities cluster, and one vulnerable package always pulls in several vulnerable peers
- **C.** Because security findings are always underreported, so every single finding statistically implies several more
- **D.** Because auditors miss most instances on a first pass, so one finding is assumed to represent many overlooked ones

> **Answer:** A

### Q14. A codebase confidently implements a security control that was appropriate years ago but is now known to be inadequate. What makes this dangerous to a casual reviewer?

- **A.** The control throws no errors, so it silently passes every automated test the reviewer chooses to run against it
- **B.** It reflects yesterday's standard practice so it looks plausible and familiar even though it is known-bad today  ✅
- **C.** The control is undocumented, so the reviewer cannot determine whether it was ever intended to be secure at all
- **D.** It appears only in the git history, so a reviewer examining the current code never encounters the weakness live

> **Answer:** B

### Q15. An auditor is reviewing an app whose entire authorization logic lives in the frontend. What is the core problem the method identifies with this design?

- **A.** Frontend authorization slows page rendering, and the resulting latency pushes users toward abandoning the app
- **B.** Frontend code is harder to update, so authorization rules there become stale faster than server-side equivalents
- **C.** The browser is attacker-controlled, so a protection that lives only client-side is a suggestion, not a real control  ✅
- **D.** Frontend authorization duplicates server logic, and the redundancy wastes engineering effort without adding safety

> **Answer:** C

### Q16. During an audit, the strongest trust signal in the code, its clean structure and thorough comments, is precisely what the method warns you to discount. Why?

- **A.** AI output maximizes style signals regardless of security, so polish and safety are simply uncorrelated in vibecode  ✅
- **B.** Clean code takes longer to generate, so heavily polished files are usually rushed toward the end of a session
- **C.** Thorough comments expose the code's logic to attackers, turning documentation quality into a direct liability
- **D.** Well-structured code resists scanning tools, so the cleanest files are the ones automated analysis silently skips

> **Answer:** A

### Q17. An auditor finds a missing authorization check on one resource route and, rather than stopping, immediately checks every other resource route. Which failure pattern justifies that move?

- **A.** The false confidence effect, since one clean-looking route implies the others were reviewed with equal care already
- **B.** Training data leakage, since a missing check means the model learned authorization from an insecure training source
- **C.** Missing defense-in-depth, since a single missing check means every route lacks its second protective layer too
- **D.** Pattern replication, since the model likely stamped the same missing-check shape across the sibling routes as well  ✅

> **Answer:** D

### Q18. A model builds only the happy path of a requested feature, with protection at a single point. What broader security philosophy is absent from this output?

- **A.** Least privilege, the principle that every component should receive only the minimum permissions it strictly requires
- **B.** Defense-in-depth, the assumption that protection should be layered so one bypass does not open the whole system  ✅
- **C.** Zero trust, the model in which no internal network request is ever treated as inherently trustworthy by default
- **D.** Fail-closed design, the rule that a system encountering an error should deny access rather than grant it by default

> **Answer:** B

### Q19. Why does the method insist that an auditor verify each area of a codebase independently rather than sampling one area and generalizing?

- **A.** Because sampling violates audit compliance standards that require every single file to be individually documented
- **B.** Because generalizing from a sample is slower than a full review once tooling is configured to scan everything at once
- **C.** Because the AI has no memory of prior standards, so security posture genuinely differs area to area within one codebase  ✅
- **D.** Because areas built later always contain more vulnerabilities, so only the newest code actually needs verification

> **Answer:** C

### Q20. A secret was committed to a repository, then deleted in a later commit. Why does the auditor still treat it as a live finding?

- **A.** Because deleted secrets remain in git history, extractable and still valid unless the credential was actually rotated  ✅
- **B.** Because deletion commits are unreliable and frequently fail to remove the file from the working tree as intended
- **C.** Because the secret scanner cannot distinguish deleted secrets from active ones, so all hits are treated identically
- **D.** Because deleting a secret signals carelessness, which is itself the real finding regardless of the credential's status

> **Answer:** A

### Q21. An auditor describes their core question at every step as: what would I try if I were attacking this? Why is that mindset essential against AI-generated code specifically?

- **A.** Because AI writes faster than humans, so only an attacker's speed of thought can keep pace with reviewing its output
- **B.** Because attackers exclusively target AI-generated apps, making the adversarial lens irrelevant for human-written code
- **C.** Because the mindset is the only way to satisfy the compliance requirement for documented penetration testing coverage
- **D.** Because AI builds the requested feature and never asks what an adversary would do, leaving that thinking to the auditor  ✅

> **Answer:** D

### Q22. A codebase looks secure on inspection, passes a casual review, and yet the audit rates several layers RED. What core insight of this module explains that gap?

- **A.** RED grades are assigned conservatively by default, so any codebase under initial review starts red until proven safe
- **B.** Security-shaped code satisfies readers who skim structure, while the audit verifies enforcement and finds it missing  ✅
- **C.** Inspection catches only frontend issues, so any codebase with backend logic will always show red on the deeper layers
- **D.** Casual review counts findings, while the audit counts severity, and severity always outranks the number of findings

> **Answer:** B

### Q23. A team argues their AI-generated app is safe because they used a modern, well-regarded model. How does the module frame the relationship between model quality and security?

- **A.** Better model style produces stronger unearned trust, so a more capable model can actually deepen the confidence trap  ✅
- **B.** Model quality directly determines security, so a top-tier model reliably yields a codebase that needs no real audit
- **C.** Model quality is irrelevant to output, since all models draw from identical training data with identical vulnerabilities
- **D.** Newer models eliminate pattern replication, so codebases from current models no longer require family-wide searches

> **Answer:** A

### Q24. An auditor treats a security-named library that is installed but never invoked as equivalent to no protection at all. Which principle is being applied?

- **A.** Least privilege, since an unused library still holds permissions that expand the application's overall attack surface
- **B.** Fail-closed defaults, since an uninvoked library leaves the system in an undefined state that should deny by default
- **C.** Verify enforcement over existence, since a protection that does not run on the real path provides no actual security  ✅
- **D.** Dependency minimalism, since every installed package that goes unused is primarily a supply-chain liability to remove

> **Answer:** C

### Q25. Looking across everything in this module, what is the governing principle for auditing AI-generated code?

- **A.** Trust the model's fluency as a first-order signal, because a capable model's clean output rarely hides real flaws
- **B.** Audit the newest code first, because AI-generated vulnerabilities concentrate entirely in the most recently built areas
- **C.** Apply the traditional review checklist rigorously, because established human-era practices already cover these failures
- **D.** Verify enforcement over appearance and treat findings as families, because vibecode fails in patterns disguised by polish  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/106568625_
