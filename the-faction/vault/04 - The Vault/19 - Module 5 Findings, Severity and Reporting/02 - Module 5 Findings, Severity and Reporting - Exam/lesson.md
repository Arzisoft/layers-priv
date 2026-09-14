---
course: "The Vault"
module: "Module 5: Findings, Severity and Reporting"
lesson: "Module 5: Findings, Severity and Reporting — Exam"
type: "course_quiz"
post_id: 106568632
space_id: 24302166
source: "https://the-faction.mn.co/posts/106568632"
updated: "2026-08-28T16:29:00Z"
---

# Module 5: Findings, Severity and Reporting — Exam

> Exam for **Module 5: Findings, Severity and Reporting** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. An auditor rates a missing authentication check that exposes the entire customer database. The finding sounds mundane, but what severity does the method assign and why?

- **A.** Critical, because it is exploitable right now with serious impact, and severity tracks exploitability rather than how alarming it sounds  ✅
- **B.** Medium, because a missing check only matters once an attacker learns the specific endpoint that happens to lack the check
- **C.** Low, because a single missing authentication check is a best-practice gap rather than a demonstrated exploit path in itself
- **D.** High, because exposing a database almost always requires at least some additional effort before an attacker can actually extract the records

> **Answer:** A

### Q2. The method defines severity as a product of two factors. Which two?

- **A.** Impact and exploitability, weighing what happens if it is exploited against how hard the exploit actually is to pull off  ✅
- **B.** Frequency and visibility, weighing how often the flaw occurs against how prominently it appears in the user interface
- **C.** Novelty and reputation, weighing how unusual the flaw is against how much reputational damage its disclosure would cause
- **D.** Cost and effort, weighing how expensive the fix is against how much engineering time the remediation will ultimately consume

> **Answer:** A

### Q3. An auditor writes a finding that reads: unparameterized query in the reports handler. The method calls this a failed finding. What does a successful finding do instead?

- **A.** It adds the CVE identifier and the exact line number, since precise technical coordinates are what make a finding actionable
- **B.** It explains in plain language what could happen, such as an attacker reading the entire customer database, plus the fix and its effort  ✅
- **C.** It raises the severity to critical, since attaching urgency is what turns a dry technical note into something clients act on
- **D.** It references the OWASP category, since mapping each finding to a recognized taxonomy is what makes the report credible to reviewers

> **Answer:** B

### Q4. The method warns that inflating severity to appear thorough destroys trust. What is the specific consequence it names?

- **A.** The report grows too long, since inflated ratings force the auditor to justify each one with additional supporting detail
- **B.** The scanner disagrees, since automated severity scores will contradict the inflated manual ratings and expose the discrepancy
- **C.** Critical stops meaning anything, so the founder can no longer rely on Critical to signal that they must drop everything now  ✅
- **D.** The client overpays, since inflated severity justifies a larger remediation engagement than the findings actually warrant

> **Answer:** C

### Q5. A finding must answer four questions for a non-technical reader. Which set captures the method's four-part structure?

- **A.** What is wrong, what could happen, what to do, and how hard the fix is, keeping deeper technical detail in an appendix  ✅
- **B.** Which layer, which tool found it, which severity, and which CVE, so the finding is fully traceable back to its source scan
- **C.** Who introduced it, when it shipped, which session generated it, and whether it was replicated across the rest of the codebase
- **D.** How likely, how visible, how novel, and how reputationally damaging, so the client can weigh the finding against the others

> **Answer:** A

### Q6. An auditor is deciding between High and Medium for a flaw that can only be exploited when a specific, currently-unmet condition holds. Which rating fits the method's definitions?

- **A.** High, because any flaw with a real exploit path is High regardless of whether its preconditions are currently satisfied or not
- **B.** Critical, because a flaw with any exploit path at all should be escalated to Critical until the preconditions are ruled out
- **C.** Medium, because the method reserves Medium for flaws exploitable only under specific conditions that are not presently met  ✅
- **D.** Low, because an unmet precondition reduces any finding to a best-practice gap with no current path an attacker could use

> **Answer:** C

### Q7. The method says a scary-sounding issue that cannot actually be exploited earns a particular rating. Which one, and what principle does that illustrate?

- **A.** High, illustrating that alarming findings deserve elevated ratings so the client takes the potential seriously enough to act
- **B.** Critical, illustrating that the worst-case scenario should always drive the rating regardless of current exploitability status
- **C.** Informational, illustrating that anything without a confirmed exploit is merely an observation with no severity attached to it
- **D.** Low, illustrating that severity follows real exploitability, not how frightening the finding sounds when first described  ✅

> **Answer:** D

### Q8. The method requires that the same class of finding earn the same severity across audits. What breaks if an auditor rates inconsistently?

- **A.** The scanner recalibrates, since automated tools learn from manual ratings and inconsistency corrupts their future scoring
- **B.** That scorecard becomes meaningless, since grades that shift by mood cannot be compared across layers, audits, or over time  ✅
- **C.** The remediation sprint stalls, since developers cannot begin fixing until every finding shares one uniform severity label
- **D.** The client disputes the invoice, since inconsistent severity is the most common reason audit engagements end in a fee dispute

> **Answer:** B

### Q9. The method says an auditor should anchor each rating by writing the answer to two questions into the finding itself. What is the purpose of writing them down?

- **A.** It lengthens the finding, since a fuller writeup signals diligence and reassures the client that the auditor examined it closely
- **B.** It satisfies the tooling, since severity fields in most reporting tools require impact and exploitability entered as text values
- **C.** It makes the rating auditable, since recording impact and exploitability lets anyone check why the finding earned its severity  ✅
- **D.** It speeds up remediation, since developers read the anchoring text instead of the finding when deciding what to fix first

> **Answer:** C

### Q10. The executive summary is described as a standalone artifact. What does writing it for someone who reads only that section require?

- **A.** Listing every Critical and High finding in full, so the section can substitute for the detailed report if the reader skips ahead
- **B.** Leading with overall posture and the single most important action, so a reader who stops there still knows what to do first  ✅
- **C.** Including the raw severity distribution table, so the executive summary carries the same quantitative weight as the full report
- **D.** Opening with the audit methodology, so the reader understands how the findings were produced before encountering any of them

> **Answer:** B

### Q11. An auditor presents a Critical finding with no remediation attached. Why does the method treat this as a reporting failure rather than a minor omission?

- **A.** It violates the report template, since every section of a compliant audit report has a mandatory remediation field to complete
- **B.** It understates the severity, since a Critical without a remediation reads to most clients as though it were actually unfixable
- **C.** It leaves the reader in fear with no path, and the method requires pairing every Critical with its fix so panic never stands alone  ✅
- **D.** It slows the sprint, since developers must request the missing remediation before they can begin addressing the Critical at all

> **Answer:** C

### Q12. The method describes the RED/YELLOW/GREEN scorecard as the report's centerpiece. Beyond summarizing, what second role does it play?

- **A.** It drives the relationship, since RED layers demand work now, YELLOW layers become a roadmap, and it gives the next audit a baseline  ✅
- **B.** It sets the invoice, since the number of RED layers directly determines the price of the remediation engagement that follows
- **C.** It certifies the app, since a scorecard with no RED layers functions as a formal guarantee the client can show to customers
- **D.** It replaces the findings list, since a founder who sees the scorecard rarely needs the underlying layer-by-layer detail anymore

> **Answer:** A

### Q13. A founder reads a Critical finding and assumes their system has already been breached. How does the method say the report's tone should be built to prevent this?

- **A.** Delay disclosure of Criticals until the fixes are already built, so the founder only ever learns about a vulnerability once it is closed
- **B.** Omit the Critical findings from the main report, moving them to a private appendix only the technical implementer will ever read
- **C.** Soften every Critical to High, since a report with no Criticals at all is far less likely to send a non-technical founder into panic
- **D.** State risks factually and frame them as fixable, pairing each Critical with its remediation so that fear never arrives without a path  ✅

> **Answer:** D

### Q14. The method insists that communicating without panic is a professional skill rather than a softness. What does it identify as the cost of inducing panic?

- **A.** Panic lengthens the engagement, since a frightened client asks for more meetings that consume the auditor's billable time
- **B.** Panic corrupts the scorecard, since a client who overreacts insists on marking every YELLOW layer RED against the evidence
- **C.** Panic raises the fee, since anxious clients demand hardened remediation far beyond what their actual risk profile requires
- **D.** Panic produces paralysis or rushed bad fixes, whereas clarity produces action, which is the entire point of delivering findings  ✅

> **Answer:** D

### Q15. The method places technical detail in an appendix rather than in the finding body. What reasoning supports that separation?

- **A.** Appendices are optional, so burying technical detail there lets the auditor omit it entirely when the client is non-technical
- **B.** The finding must be actionable for a non-technical reader, while the implementer still gets the depth they need in the appendix  ✅
- **C.** Technical detail is confidential, so isolating it in an appendix keeps it out of the copies that circulate beyond the founder
- **D.** Appendices render first, so front-loading technical detail there ensures developers see it before the executive summary loads

> **Answer:** B

### Q16. An auditor is ordering findings within a layer for the report. What ordering does the method specify?

- **A.** Alphabetical by finding title, since a predictable order lets the client locate any specific finding quickly during review
- **B.** By remediation effort, easiest first, so the client can build momentum by clearing the quick fixes before the harder ones
- **C.** By discovery time, since presenting findings in the order they surfaced preserves the auditor's reasoning trail for the reader
- **D.** By severity, highest first, so the most serious issue in each layer is the first thing the reader encounters in that section  ✅

> **Answer:** D

### Q17. The method lists a severity distribution as a required report section. What does that section let the reader see at a glance?

- **A.** The shape of the risk, since counting how many Critical, High, Medium, and Low findings exist makes the overall profile visible  ✅
- **B.** The auditor's workload, since the count of findings per severity documents how much effort the engagement actually required
- **C.** The remediation timeline, since the number of findings at each severity directly sets the number of sprint weeks to schedule
- **D.** The tool coverage, since the distribution reveals which scanners contributed findings and which layers they each examined most

> **Answer:** A

### Q18. An auditor defines Informational for a finding. What does that level actually denote in the method's rubric?

- **A.** A flaw exploitable only by an insider, since threats requiring internal access are downgraded to the lowest reporting tier
- **B.** An observation worth noting that is not itself a weakness, distinct from Low, which marks an actual best-practice gap  ✅
- **C.** A best-practice gap with a clear fix, since Informational is the method's label for low-effort hardening recommendations
- **D.** A finding still under investigation, since Informational marks items the auditor has not yet confirmed as genuine weaknesses

> **Answer:** B

### Q19. The method says the report should lead with the scorecard and severity distribution. What failure does leading with them prevent?

- **A.** It prevents posture from being invisible at a glance, since a findings list with no scorecard hides the overall shape of the risk  ✅
- **B.** It prevents the report from being skimmed, since a visual scorecard discourages readers from skipping the detailed findings below
- **C.** It prevents severity disputes, since a client who sees the distribution first is less likely to challenge individual ratings later
- **D.** It prevents scope creep, since presenting the scorecard up front locks the engagement boundary before the client reads further

> **Answer:** A

### Q20. An auditor writes what could happen for a finding in terms of money, data, downtime, or reputation. Why does the method frame consequences this way?

- **A.** These are the categories the scanner outputs, so aligning the finding to them keeps the report consistent with the raw tool data
- **B.** These are the fastest to write, so using four fixed categories lets the auditor produce consequence text without much deliberation
- **C.** These are required by cyber-insurance underwriters, so framing consequences this way lets the client file a claim more easily later
- **D.** These are the terms the founder actually weighs decisions in, so business consequences land where abstract technical risk does not  ✅

> **Answer:** D

### Q21. The method warns against rating severity by how scary a finding sounds. What discipline does it prescribe to keep ratings honest?

- **A.** Deferring to the scanner's severity score, since automated ratings are immune to the emotional pull of an alarming description
- **B.** Anchoring each rating to impact and exploitability in writing, so a boring exposure outranks a dramatic but unexploitable one  ✅
- **C.** Averaging several auditors' instinctive ratings, since the mean of independent gut reactions cancels out individual bias reliably
- **D.** Rating every finding one level below instinct, since a uniform downward adjustment corrects for the natural tendency to inflate

> **Answer:** B

### Q22. The method describes the four-part finding as translating a vulnerability for a non-technical stakeholder. What is lost if the auditor skips the translation?

- **A.** The finding stays engineer-language the founder cannot act on, so the vulnerability is understood by no one and stays live  ✅
- **B.** The report gets shorter, since untranslated findings omit the plain-language layer and therefore consume less space overall
- **C.** The severity becomes unclear, since technical phrasing hides the impact rating that the four-part structure would have exposed
- **D.** The appendix grows, since detail that belonged in the plain-language finding spills into the technical section instead

> **Answer:** A

### Q23. A report's executive summary buries the single most important action three pages in. Why does the method treat placement as a real failure?

- **A.** The summary exceeds its length budget, since the most important action appearing late signals the section was not edited down
- **B.** The scorecard contradicts it, since an action buried in prose cannot be reconciled with the RED layers shown on the scorecard
- **C.** The remediation sprint misorders, since developers read the executive summary top to bottom and fix in the sequence they find
- **D.** The reader who stops after the summary never reaches it, so the one thing they most needed to do goes unseen and undone  ✅

> **Answer:** D

### Q24. The report ends with a remediation priorities section. According to the method, what is that ordered list, and what does it become downstream?

- **A.** A catalog of every tool the auditor ran, which the client's engineers consult to reproduce the scanning pipeline themselves later
- **B.** A restatement of the severity distribution counts, which gives the founder a second numeric view of the same finding totals
- **C.** An ordered fix list that becomes the sprint plan, sequencing the work the remediation module then executes finding by finding  ✅
- **D.** A summary of the layers graded GREEN, which reassures the client by highlighting everything the audit confirmed was already sound

> **Answer:** C

### Q25. Looking across everything in this module, what is the governing principle for findings and reporting?

- **A.** Report every finding at maximum severity, because overstating risk guarantees the client takes the audit seriously enough to act
- **B.** Write for the engineer who implements, because precise technical findings are what ultimately close the vulnerabilities that matter
- **C.** Rate by real exploitability and write for the decision-maker, because an audit's value is the informed action its findings enable  ✅
- **D.** Minimize the finding count, because a short report with few findings reassures the client and protects the ongoing relationship

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106568632_
