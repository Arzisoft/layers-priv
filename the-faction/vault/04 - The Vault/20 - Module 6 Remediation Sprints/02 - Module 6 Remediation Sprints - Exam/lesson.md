---
course: "The Vault"
module: "Module 6: Remediation Sprints"
lesson: "Module 6: Remediation Sprints — Exam"
type: "course_quiz"
post_id: 106568633
space_id: 24302166
source: "https://the-faction.mn.co/posts/106568633"
updated: "2026-08-28T15:44:50Z"
---

# Module 6: Remediation Sprints — Exam

> Exam for **Module 6: Remediation Sprints** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. An auditor is told a report full of findings changes nothing on its own. According to the method, when is the audit's value actually realized?

- **A.** When the findings are fixed, verified, and confirmed gone, since remediation is where the audit's value is finally realized  ✅
- **B.** When the report is delivered, since a thorough writeup of every finding is itself the deliverable the client paid for
- **C.** When the scanner run completes, since the automated pass is the mechanical core that the entire audit engagement is built upon
- **D.** When severity is assigned, since classifying each finding is the moment the client understands the true risk they carry

> **Answer:** A

### Q2. The method warns that the naive version of remediation, ask AI to fix each finding and move on, quietly fails in three ways. Which is one of those failures?

- **A.** It over-documents, producing so much fix history that the client cannot locate the changes that actually mattered to them
- **B.** It escalates severity, since asking AI to fix a finding causes the model to re-rate it higher than the auditor originally did
- **C.** It fixes without the finding as context, producing a plausible change that may never close the actual hole it targeted  ✅
- **D.** It slows the scanner, since interleaving fixes with scans forces the pipeline to re-parse the entire codebase each time

> **Answer:** C

### Q3. An auditor orders the remediation queue. Beyond putting Critical and High first, what second ordering factor does the method require?

- **A.** Dependency order, since some fixes are prerequisites for others and some findings share a root cause one change resolves  ✅
- **B.** Discovery order, since fixing findings in the sequence they surfaced preserves the auditor's original reasoning for the team
- **C.** Alphabetical order by affected file, since a predictable file order lets the developer batch edits within each module cleanly
- **D.** Effort order, since clearing the quickest fixes first builds visible momentum before the team reaches the harder findings

> **Answer:** A

### Q4. The method says the finding is the specification for the fix. What does directing AI to remediate with the full finding as context actually supply?

- **A.** The severity rating alone, since knowing a finding is Critical is what tells the model how much effort to invest in the fix
- **B.** The scanner's raw output, since the model needs the exact tool message to reproduce and then resolve the flagged condition
- **C.** The client's approval, since a fix should not proceed until the finding has been signed off by the business that owns it
- **D.** The weakness, location, exploit path, and intended secure behavior, so the fix targets the real vulnerability, not a guess at it  ✅

> **Answer:** D

### Q5. Because of pattern replication, every fix prompt in the method asks one recurring question. What is it?

- **A.** Does this pattern appear elsewhere, and should this fix apply across the whole family rather than the single found instance  ✅
- **B.** Does this fix introduce a new dependency, and should that dependency be scanned before the remediation is allowed to proceed
- **C.** Does this finding warrant escalation, and should its severity be raised now that a fix is being actively developed for it
- **D.** Does this change need client sign-off, and should the fix wait until the business has formally accepted the associated risk

> **Answer:** A

### Q6. The method calls a fix a hypothesis until something confirms it. What confirms a fix for a finding that came from a scanner?

- **A.** A code review by a second engineer, since peer confirmation is the standard that separates a believed fix from a verified one
- **B.** Re-running the scan or test that produced the finding and confirming it now passes, which closes the believe-versus-know gap  ✅
- **C.** The client's acceptance, since a fix is only truly confirmed once the business agrees the associated risk has been retired
- **D.** A passing unit test suite, since green tests across the codebase demonstrate that the specific vulnerability has been resolved

> **Answer:** B

### Q7. For a finding discovered through manual exploitation rather than a scanner, how does the method say verification should work?

- **A.** Re-running the full automated pipeline, since manual findings are best confirmed by whichever scanner covers that same layer
- **B.** Re-attempting the original exploit and confirming it now fails, since manual findings are verified the same way they were found  ✅
- **C.** Marking it resolved once the code changes, since manual findings lack a repeatable test and must be closed on the fix alone
- **D.** Waiting for the next scheduled audit, since manual findings can only ever be re-verified during a fresh end-to-end engagement later

> **Answer:** B

### Q8. The method stresses regression prevention specifically for vibebuilt code. What makes regression an acute risk in AI-generated codebases?

- **A.** AI writes verbose code, so each regenerated file is larger and statistically more likely to reintroduce some earlier flaw by volume
- **B.** AI randomizes structure, so regenerated code never matches the fixed version and the regression guard cannot locate the change
- **C.** AI prefers newer libraries, so every regeneration upgrades dependencies and reopens vulnerabilities the previous versions had patched
- **D.** AI has no memory of the fix, so the next generation session will happily reintroduce the original pattern unless something stops it  ✅

> **Answer:** D

### Q9. An auditor encodes a fix so it stays fixed across future sessions. Which mechanism matches the method's approach to regression guards?

- **A.** A comment in the file explaining the vulnerability, since documenting the fix inline is what teaches the next session to preserve it
- **B.** A test or lint rule that fails if the vulnerability returns, since an automated guard catches the pattern the moment it reappears  ✅
- **C.** A note in the audit report, since recording the fix in the deliverable ensures the client's team knows never to undo the change
- **D.** A locked file permission, since making the fixed file read-only prevents any later session from regenerating and reopening it

> **Answer:** B

### Q10. The method's sprint cadence is a fixed four-step loop per finding. Which sequence is it?

- **A.** Scan, fix, escalate, invoice, moving each finding from detection through to billing in one continuous pass without any interruption
- **B.** Fix, verify, re-scan, document, running each finding through the same deliberately boring loop where the discipline is the point  ✅
- **C.** Triage, delegate, review, approve, routing each finding through the team hierarchy before any code change is actually made
- **D.** Reproduce, patch, deploy, monitor, pushing each fix straight to production and watching telemetry to confirm it took effect

> **Answer:** B

### Q11. The method warns against fixing a Medium while a Critical stays open. What principle does that violation break?

- **A.** Prioritize by severity first, since spending effort on a Medium while a Critical remains exploitable misallocates the sprint's work  ✅
- **B.** Fix in dependency order, since the Medium may depend on the Critical and fixing it first guarantees the work will be redone
- **C.** Group by root cause, since a Medium and a Critical that share a cause must always be fixed together in a single change
- **D.** Verify before moving on, since leaving the Critical unverified is what actually makes fixing the Medium premature and wasteful

> **Answer:** A

### Q12. An auditor groups several findings that share a single root cause. Why does the method treat this grouping as central to efficient remediation?

- **A.** Grouped findings share a severity, so rating them once instead of individually saves classification time during the sprint
- **B.** Grouped findings read better in the report, so clustering them by cause makes the remediation section shorter for the client
- **C.** Grouped findings deploy together, so bundling them into one release reduces the number of production pushes the team must run
- **D.** One change can resolve the whole group, so addressing the shared cause fixes a family of findings rather than one at a time  ✅

> **Answer:** D

### Q13. The method defines production-ready as one of three finish lines. What does production-ready specifically mean?

- **A.** Every finding from the audit resolved and verified, including Mediums and Lows, so the entire scorecard has turned green
- **B.** The app works and has no Critical or High findings, so it is safe to operate even though lower-severity items may remain open  ✅
- **C.** Defense-in-depth added beyond the findings, with proactive controls against attacks that were never actually attempted during the audit
- **D.** The codebase passes every automated scan, regardless of whether the manual pass uncovered business logic flaws still left unfixed

> **Answer:** B

### Q14. The method distinguishes audit-clean from production-ready. What does audit-clean require that production-ready does not?

- **A.** Proactive hardening against unattempted attacks, since audit-clean is the method's term for going beyond the findings that were found
- **B.** Only that the app runs without Critical or High findings, since audit-clean and production-ready describe the same operational bar
- **C.** Every finding from the audit resolved and verified, including Mediums and Lows, so the scorecard is fully green across all layers  ✅
- **D.** A second independent audit, since audit-clean status can only be certified once a different auditor confirms the first one's results

> **Answer:** C

### Q15. The method defines hardened as the third finish line. What sets hardened apart from audit-clean?

- **A.** Hardened adds defense-in-depth beyond the findings, with proactive controls against attacks that were never attempted in the audit  ✅
- **B.** Hardened means the app merely runs safely, since it is the method's operational baseline that every deployed application must meet
- **C.** Hardened means an external certificate was issued, since the distinction is about third-party attestation rather than the code itself
- **D.** Hardened means only the Criticals are fixed, since it is a faster interim state a business reaches before becoming audit-clean later

> **Answer:** A

### Q16. A solo founder's simple app is being remediated. Why does the method warn against building all the way to hardened for this client?

- **A.** Hardened costs more than the audit, so exceeding the engagement's fee on remediation is a billing problem for the auditor to avoid
- **B.** Hardened voids production-ready, so layering extra controls on a simple app paradoxically reopens the Criticals that were closed
- **C.** Hardened requires cloud access, so a solo founder's minimal infrastructure cannot support the proactive controls it would demand
- **D.** Over-building for a solo founder wastes effort the client does not need, since the target should be matched to the business's real risk  ✅

> **Answer:** D

### Q17. A business handling sensitive data is remediated only to production-ready. Why does the method flag stopping there as a mistake for this client?

- **A.** Production-ready requires a second audit, which a sensitive-data business cannot skip without violating its compliance obligations
- **B.** Production-ready is not a real finish line, so any client stopping there has simply failed to complete the remediation sprint at all
- **C.** Production-ready leaves lower-severity findings open, and under-building for a sensitive-data business ignores the risk its data warrants  ✅
- **D.** Production-ready reopens Criticals over time, so a sensitive-data business must re-run the entire audit weekly to stay at that level

> **Answer:** C

### Q18. When an auditor fixes one instance of a replicated pattern, the method says re-scanning serves a second purpose beyond confirming that fix. What is it?

- **A.** It updates the severity, since re-scanning right after a fix recalculates how serious the remaining instances of the pattern now are
- **B.** It resets the pipeline, since a fresh scan clears the cached results that would otherwise skew the next engagement's baseline
- **C.** It refreshes the report, since re-scanning regenerates the findings document so the client always sees the current fix status
- **D.** It confirms no sibling was missed and nothing regressed, since the broader scan checks the whole family and the surrounding code  ✅

> **Answer:** D

### Q19. The method says marking a finding resolved without re-running the check that proves it is a specific failure. What does that failure produce?

- **A.** A duplicated finding, since an unverified resolution leaves the original entry in the report where it is later counted twice
- **B.** The belief that you are safe without the evidence, since a plausible-looking change may not have actually closed the vulnerability  ✅
- **C.** A severity mismatch, since a finding closed without verification retains its original rating that no longer reflects the current code
- **D.** A broken pipeline, since the scanner expects every finding to be re-run and an unverified closure corrupts its internal state

> **Answer:** B

### Q20. The method says naming the target finish line explicitly prevents two opposite errors. What are those two errors?

- **A.** Over-scanning and under-scanning, the two coverage errors that a stated target resolves by fixing how many tools are run
- **B.** Fixing too fast and fixing too slow, the two pacing errors that an explicit finish line corrects by setting a firm schedule
- **C.** Over-building for a solo founder and under-building for a sensitive-data business, the two ways an unstated target goes wrong  ✅
- **D.** Over-charging and under-charging, the two pricing errors that naming the finish line prevents by tying fee to remediation depth

> **Answer:** C

### Q21. An auditor documents each remediated finding at the end of the loop. What does the method say this documentation is for?

- **A.** It satisfies the invoice, since billing the client for remediation requires an itemized record of every change that was made
- **B.** It replaces the regression guard, since thorough documentation of a fix removes the need for an automated test to protect it
- **C.** It trains the model, since feeding documented fixes back into the AI is truly what prevents it from regenerating the same flaws again
- **D.** It completes the audit trail and gives the next audit a baseline, recording what was found, what changed, and how it was verified  ✅

> **Answer:** D

### Q22. The method calls the sprint cadence deliberately boring and says the discipline is the point. What happens when a team skips a step to move faster?

- **A.** The report drifts, since an incomplete loop leaves the findings document out of sync with the true state of the codebase
- **B.** The severity inflates, since a skipped verification step causes the remaining findings to be re-rated higher than they should be
- **C.** Silent failures re-enter, since skipping fix, verify, re-scan, or document is exactly where unclosed holes slip back in unnoticed  ✅
- **D.** The invoice grows, since skipped steps must be redone later at a higher cost that the client ultimately absorbs in the fee

> **Answer:** C

### Q23. An auditor directs a fix without supplying the finding, and the model produces a change that addresses symptoms rather than the cause. What does the method say distinguishes the two approaches?

- **A.** A fix directed without context tends to address symptoms, while a fix directed with the finding as context addresses the cause  ✅
- **B.** A fix without context runs faster, while a fix with the finding as context is slower but produces more thoroughly commented code
- **C.** A fix without context needs no verification, while a context-rich fix must always be re-scanned before it can be marked resolved
- **D.** A fix without context is cheaper, while a fix with the finding as context costs more because it consumes additional model tokens

> **Answer:** A

### Q24. During a sprint, a fix for one finding introduces a new flaw elsewhere in the code. Which step of the method's cadence is designed to catch this, and how?

- **A.** The fix step, since supplying the finding as context prevents the model from ever introducing a new flaw while resolving the old one
- **B.** The document step, since writing up the change is where the auditor notices the new flaw while describing what the fix touched
- **C.** The re-scan step, since running the broader scan after each fix is what surfaces a newly introduced issue the targeted verify would miss  ✅
- **D.** The verify step, since re-attempting the original exploit also exercises the surrounding code and reveals anything the fix broke nearby

> **Answer:** C

### Q25. Looking across everything in this module, what is the governing principle for remediation sprints?

- **A.** Fix with context, verify by re-testing, guard against regression, and name the finish line, because a believed fix is not a real one  ✅
- **B.** Delegate every fix to AI without oversight, because the model resolves findings faster than a human auditor can review its changes
- **C.** Fix the easy findings first, because clearing volume quickly demonstrates progress and keeps the client confident in the engagement
- **D.** Ship fixes straight to production, because closing vulnerabilities the very moment they are found minimizes the exposure window overall

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106568633_
