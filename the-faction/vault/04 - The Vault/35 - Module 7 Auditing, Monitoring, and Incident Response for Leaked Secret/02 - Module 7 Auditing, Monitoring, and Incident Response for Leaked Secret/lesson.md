---
course: "The Vault"
module: "Module 7: Auditing, Monitoring, and Incident Response for Leaked Secrets"
lesson: "Module 7: Auditing, Monitoring, and Incident Response for Leaked Secrets — Exam"
type: "course_quiz"
post_id: 107142743
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142743"
updated: "2026-09-10T20:03:28Z"
---

# Module 7: Auditing, Monitoring, and Incident Response for Leaked Secrets — Exam

> Exam for **Module 7: Auditing, Monitoring, and Incident Response for Leaked Secrets** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder asks whether enabling GitHub secret scanning means detection is handled. What does this module answer?

- **A.** Detection is a layered net: platform scanning, history-aware scanners, and usage signals each catch what the others miss  ✅
- **B.** Yes: platform scanning covers every key format, so additional layers would only duplicate what GitHub already does for free
- **C.** No: platform scanning is unreliable enough that dedicated scanners should replace it rather than add to it
- **D.** Detection is optional once storage is clean, since well-stored secrets have no remaining path into a leak

> **Answer:** A

### Q2. A commit containing a Stripe key is stopped before it ever lands in the repo. Which mechanism from this module did this?

- **A.** A provider webhook, since Stripe watches repository pushes for its own key formats across platforms
- **B.** Branch protection rules, since required reviews are what stand between a bad commit and the default branch
- **C.** Push protection: platform scanning that blocks commits containing detected secrets before they land  ✅
- **D.** The .gitignore file, since ignore rules intercept staged secrets during the commit process itself

> **Answer:** C

### Q3. A builder asks what truffleHog and gitleaks add on top of platform scanning. Which answer matches this module?

- **A.** Nothing for small teams: dedicated scanners exist for organizations whose repo volume exceeds platform quotas
- **B.** They scan history and find high-entropy strings platform scanning misses, running locally, in hooks or in CI  ✅
- **C.** They fix findings automatically, rewriting history to strip the secrets that platform scanning only reports
- **D.** They monitor provider dashboards for anomalous usage, which platform scanning has no visibility into at all

> **Answer:** B

### Q4. No scanner has fired, but a client's AI bill tripled overnight with unfamiliar traffic. What does this module call this?

- **A.** A billing dispute for the provider to resolve, since traffic anomalies without scanner hits are accounting issues
- **B.** A false alarm, since leaks that scanning did not catch are by definition not leaks of stored credentials
- **C.** A seasonal usage pattern, worth logging and revisiting at the end of the quarter with fuller data
- **D.** The third detection layer firing: the leak announces itself through behavior when scanning missed the string  ✅

> **Answer:** D

### Q5. A scanner finds a key in a commit from two years ago, long since removed from current files. How does this module treat that finding?

- **A.** As live until the credential is rotated: history holds every secret ever committed, and a hit in any commit counts  ✅
- **B.** As merely informational: findings older than one year are archived context rather than actionable security work items
- **C.** As a scanner tuning problem, since history hits mostly reflect entropy thresholds set too aggressively
- **D.** As resolved by the earlier removal, since deleted code is unreachable through any normal clone operation

> **Answer:** A

### Q6. A teammate asks for the incident response order when a secret leaks. Which sequence matches this module?

- **A.** Assess first, then contain once the impact is understood, then notify, remediate, and record at leisure
- **B.** Contain, assess, remediate, notify, record: the credential dies first, and investigation happens behind a shut door  ✅
- **C.** Notify first so stakeholders can weigh in, then assess, then contain with whatever response they approve
- **D.** Remediate the leak path first so that it cannot ever recur, then contain, then assess what happened before the fix landed

> **Answer:** B

### Q7. Mid-incident, a builder wants to finish investigating before touching the leaked key. What does this module say?

- **A.** Containment never waits for investigation: the door gets shut first, and the investigation happens behind it  ✅
- **B.** Investigation first is correct, since rotating the key changes the very evidence the investigation depends on
- **C.** Either order works, since containment and assessment are parallel tracks with no real dependency
- **D.** Wait for the provider's guidance, since acting before vendor confirmation can void the abuse claim

> **Answer:** A

### Q8. Two keys leaked this month. One shows zero usage; the other shows unfamiliar API calls. How does this module distinguish them?

- **A.** By blast radius alone: the key with wider permissions is the worse incident regardless of what the usage logs actually show
- **B.** By provider: payment keys always outrank AI keys in severity whatever their respective usage logs happen to say
- **C.** Exposure versus breach: unused means a clean rotation and record; used means downstream duties and possible escalation  ✅
- **D.** By discovery source: scanner findings are exposures while billing-alert findings are breaches by definition

> **Answer:** C

### Q9. During assessment, where does this module say the "was it used" answer comes from?

- **A.** From the attacker, since credential abuse is typically followed by a ransom contact that scopes the damage
- **B.** From the app's own database, since abused credentials always leave rows the application layer can query
- **C.** From intuition calibrated by experience, since usage evidence is rarely available in provider tooling
- **D.** From provider views: Stripe key usage, OpenAI usage logs, and cloud audit trails for the exposure window  ✅

> **Answer:** D

### Q10. A builder asks what the hygiene checklist covers and how often it runs. Which answer matches this module?

- **A.** Password strength and MFA settings, run annually alongside the client's cyber insurance renewal questionnaire
- **B.** Storage, prefixes, per-env keys, inventory, rotation, CI patterns, scanning, incident doc: ten minutes monthly  ✅
- **C.** Whatever the last incident touched, run whenever the next incident finally makes the gaps impossible to ignore
- **D.** Framework versions and dependency audits, run weekly since the supply chain is where most secrets actually leak

> **Answer:** B

### Q11. A team marks a scanner finding "known issue" and moves on without rotating. What does this module call that state?

- **A.** A leak with a bookmark: the finding without a rotation leaves the credential exactly as exposed as before  ✅
- **B.** Reasonable triage: acknowledged findings are managed findings, and rotation can wait for the next quiet sprint
- **C.** A scanner limitation, since tools cannot know which findings matter and teams must filter aggressively
- **D.** Standard practice for historical hits, since old commits sit behind enough friction to deter abuse

> **Answer:** A

### Q12. On discovering a leak, a builder force-pushes cleaned history and deletes the CI logs, then starts assessing. What went wrong, per this module?

- **A.** Nothing: removing exposed material is containment, and the assessment can proceed from memory afterward
- **B.** The force-push was right but the log deletion wrong, since history and logs carry very different evidence value
- **C.** The credential is still live and the exposure window is now unknowable: contain first, preserve while assessing  ✅
- **D.** The order was right but too slow: cleanup should happen within minutes to beat scanner indexing

> **Answer:** C

### Q13. In a panic, a builder considers revoking every credential in the project simultaneously, with no replacements staged. What does this module say?

- **A.** Do it: total revocation is the only certain containment, and outages are fully acceptable during incidents
- **B.** Do it for the payment keys only, since financial credentials justify the outages that other keys do not
- **C.** Never revoke during business hours, since the outage cost exceeds the exposure cost until nightfall comes
- **D.** Emergency order is per-credential, contain-then-restore: killing everything turns one leak into an outage  ✅

> **Answer:** D

### Q14. A client's key leaked and was contained quickly; the builder considers not mentioning it. What does this module say about that option?

- **A.** The trust cost when it surfaces later dwarfs the cost of the honest message now: silent incidents are the mistake  ✅
- **B.** Discretion is professional: clients pay for outcomes, and contained incidents are outcomes with no residue at all
- **C.** Disclosure depends on contract terms alone, and absent a clause, silence is the safe commercial default
- **D.** Mention it only if the client asks directly, since unprompted disclosure invites unnecessary escalation

> **Answer:** A

### Q15. The same leak path opened twice in one year at a team with no incident documentation. Which control from this module was missing?

- **A.** A stronger scanner, since second occurrences mean the detection layer needs a lower entropy threshold
- **B.** The incident record: the two-paragraph write-up whose absence is why nobody remembered the first leak  ✅
- **C.** A dedicated security hire, since repeat incidents indicate the function has outgrown builder ownership
- **D.** Longer log retention, since the evidence of the first incident expired before the second one arrived

> **Answer:** B

### Q16. A hygiene checklist ran monthly for a quarter, then quietly stopped. What does this module prescribe?

- **A.** Retire it entirely: checklists that stop being run have proven themselves unnecessary for that team's current maturity
- **B.** Double its length on resumption, since the missed months mean more ground needs covering on every pass
- **C.** Replace it with annual audits, since standing habits fail and scheduled ceremonies at least actually happen
- **D.** Wire it to a calendar or a delivery step: the checklist works only as a standing habit, and drift returns quietly  ✅

> **Answer:** D

### Q17. You direct AI to set up gitleaks for a repo. Which instruction set matches this module?

- **A.** CI on every push, a pre-commit hook, and a one-time full-history scan with findings output as a rotation to-do list  ✅
- **B.** A weekly scheduled scan of just the default branch, since push-time scanning slows the whole development loop badly
- **C.** A scan of open pull requests only, since merged history has already passed whatever review existed then
- **D.** Local scans on demand, left to each builder's own discretion, since mandatory hooks breed quiet workarounds

> **Answer:** A

### Q18. An OpenAI key sat in a public repo for six hours. You direct AI through the incident. Which request matches this module?

- **A.** Draft a legal threat to whoever cloned the repo during the window, since deterrence is the fastest containment
- **B.** Estimate the odds the key was found, since probability determines whether the incident process starts at all
- **C.** Walk me through containment for this provider, what the usage log tells us, and what the client message should say honestly  ✅
- **D.** Generate a stronger replacement key first, since key strength is the variable that failed in this incident

> **Answer:** C

### Q19. You hand AI a provider dashboard export after a leak. What question from this module is it answering?

- **A.** Whether the provider's uptime held during the window, since outages mask the traffic assessment depends on
- **B.** Whether this specific key shows any usage outside our known traffic patterns during the exposure window  ✅
- **C.** Whether the account should upgrade tiers, since higher plans include the forensics the incident now needs
- **D.** Whether other customers of the provider were also affected, since shared infrastructure spreads exposure

> **Answer:** B

### Q20. In the module's billing-alert scenario, what made containment take twenty minutes instead of hours?

- **A.** The provider's fraud team intervened automatically, freezing the key before the builder was even awake
- **B.** The attacker stopped voluntarily once the traffic was noticed, as abusers typically do under observation
- **C.** The app had no real users yet, so revocation carried no stakes and needed no coordination at all
- **D.** The key was revoked from the dashboard and a staged replacement deployed: preparation done before it was needed  ✅

> **Answer:** D

### Q21. In that same scenario, the assessment concluded no customer data was touchable. What supported that conclusion?

- **A.** The attacker's own traffic pattern, since crypto-mining abuse never coincides with any real data access attempts
- **B.** The client's assurance that their customers had noticed nothing unusual during the exposure window
- **C.** The scope of the key: it reached only the AI API, so the spend was the damage and the data was never reachable  ✅
- **D.** The six-hour window, since meaningful data access requires longer than any same-day response allows

> **Answer:** C

### Q22. A builder asks what truffleHog's verification feature adds to scan results. What does this module say?

- **A.** It checks whether found credentials are live, which turns a list of findings into a list of priorities  ✅
- **B.** It confirms the scanner itself is fully up to date, which keeps false negatives from aging quietly in place
- **C.** It signs the scan report, which is what makes findings admissible in client security reviews
- **D.** It verifies repo permissions, which determines who could have seen each finding historically

> **Answer:** A

### Q23. How does this module say billing alerts should be tuned on AI and cloud accounts, and why?

- **A.** At ten times normal usage, since alerts that fire on ordinary variance train teams to ignore them
- **B.** Alerts are redundant where scanning is enabled, since string detection catches leaks before spend does
- **C.** At the free-tier boundary, since crossing from free to paid is the signal that matters financially
- **D.** Close to normal usage: spend alerts set tight catch abuse faster than most scanning ever will  ✅

> **Answer:** D

### Q24. A client security review asks for evidence of secrets discipline. Which artifacts from this module answer it?

- **A.** The team's professional certifications, since personnel credentials are what security reviews are truly designed to check
- **B.** The hygiene checklist and the incident records kept beside it: together they are the audit trail the review asks for  ✅
- **C.** A signed statement that no incident has ever occurred, since a clean history is the strongest evidence
- **D.** The provider invoices, since stable spend is the objective proof that no credential was ever abused at all

> **Answer:** B

### Q25. Looking across this whole module, what is the governing principle of auditing, monitoring, and incident response?

- **A.** Prevention makes response unnecessary: a team that stores secrets well can treat incident planning as optional
- **B.** Detection is the specialist's job: builders ship, and monitoring belongs to whoever the client hires for security
- **C.** Survivable when the system is ready: layered detection, containment first, honest closure, and standing hygiene  ✅
- **D.** Tools decide outcomes: the team with the newest scanner has already done what this module asks of a serious builder

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/107142743_
