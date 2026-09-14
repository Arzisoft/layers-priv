---
course: "The Vault"
module: "Module 3: Automated Scanning Direction"
lesson: "Module 3: Automated Scanning Direction — Exam"
type: "course_quiz"
post_id: 106568628
space_id: 24302166
source: "https://the-faction.mn.co/posts/106568628"
updated: "2026-08-28T16:27:00Z"
---

# Module 3: Automated Scanning Direction — Exam

> Exam for **Module 3: Automated Scanning Direction** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A junior auditor runs every scanner, exports the raw output, and sends all four hundred findings straight to the client. What does the method say is wrong with this?

- **A.** The scanners were run in the wrong order, and running them alphabetically would have produced a cleaner combined report
- **B.** Raw scanner output is not a deliverable, and dumping unfiltered findings on a client is malpractice by sheer volume  ✅
- **C.** Four hundred findings is too few, since a thorough automated pass on any real codebase surfaces well over a thousand
- **D.** The client should receive the findings live during scanning, rather than in a single batch after the run completes fully

> **Answer:** B

### Q2. An auditor is choosing tools for the dependency-scanning portion of the audit. Which set belongs to that job?

- **A.** Semgrep, Bandit, and ESLint security rules, which read source code for dangerous patterns across multiple languages
- **B.** npm audit, Snyk, and Dependabot, which compare a project's package manifest against known vulnerability databases  ✅
- **C.** Gitleaks and TruffleHog, which scan the repository and its history for leaked API keys, tokens, and credentials
- **D.** Prowler and ScoutSuite, which walk a cloud account against benchmark checklists for IAM and storage exposure

> **Answer:** B

### Q3. A dependency scan reports a critical CVE in a package. Before treating it as urgent, what does the method say the auditor must determine?

- **A.** Whether the vulnerable code path is actually reachable from this application, since an unused package is a different conversation  ✅
- **B.** Whether the CVE was published recently, since older disclosures have usually been patched upstream by maintainers
- **C.** Whether the package is popular, since widely used packages attract more attacker attention than obscure ones do
- **D.** Whether the package has an alternative, since replaceable dependencies are always considered safer to remove than to patch in place

> **Answer:** A

### Q4. The method calls static analysis the natural detector for one specific AI failure pattern from Module 1. Which pattern, and why?

- **A.** Hallucinated security, because static analyzers confirm whether a named protection is imported anywhere in the project tree
- **B.** Cross-session drift, because static analyzers timestamp each rule match to the session that generated the offending file
- **C.** Pattern replication, because one static-analysis rule matching across forty files makes a replicated flaw visible at once  ✅
- **D.** The false confidence effect, because static analyzers grade code style and expose the polish that misleads human reviewers

> **Answer:** C

### Q5. A secret was committed months ago and deleted in a later commit. Why does the method insist secret scanners must cover the full git history, not just the working tree?

- **A.** A deleted secret remains in history, extractable and still live unless it was rotated so history hits are real findings  ✅
- **B.** Git history compresses better than the working tree, so scanning it first speeds up the overall secret-detection pass
- **C.** The working tree changes constantly, so scanning history instead gives a more stable snapshot for the audit record
- **D.** History scanning replaces working-tree scanning entirely, since any current secret also appears somewhere in the history

> **Answer:** A

### Q6. An auditor finds a secret in the git history of a public repository. Beyond noting the exposure, what does the method treat as automatically true about that secret?

- **A.** It should be treated as compromised, because public repositories get scraped by bots within minutes of any commit  ✅
- **B.** It can be ignored if the surrounding commit was later force-pushed away, since rewriting history removes the exposure fully
- **C.** It is only a finding if the secret is a production credential, since test and staging secrets carry negligible real risk
- **D.** It requires no rotation as long as access logs show no unauthorized use of the credential during the exposure window

> **Answer:** A

### Q7. The method describes header and TLS analyzers as testing something the code-level review cannot. What specifically do these outside-in tools verify?

- **A.** The intentions expressed in the source code, confirming that the developer wrote the correct header configuration originally
- **B.** The dependency tree, confirming that no transitive package downgrades the transport security the application relies upon
- **C.** The deployed reality of headers and TLS, which frequently differs from what the code intends after the host processes it  ✅
- **D.** The commit history of the configuration files, confirming that transport settings were not weakened in a recent change

> **Answer:** C

### Q8. An auditor runs a cloud config auditor and is buried in thousands of benchmark findings. What direction discipline does the method prescribe here?

- **A.** Report every benchmark item, since a cloud auditor's completeness is precisely what justifies its place in the pipeline
- **B.** Rerun the auditor with stricter rules, since the volume signals that the first pass used an overly permissive rule set
- **C.** Suppress all findings below critical severity, since benchmark tools inflate severity and only criticals ever matter
- **D.** Scope to the services actually in use, and separate what the benchmark flags from where this business is genuinely exposed  ✅

> **Answer:** D

### Q9. The method says false-positive filtering is a judgment call made with evidence, not a checkbox. What does honoring that look like in practice?

- **A.** Deferring all filtering to the client, since only the business can judge which scanner findings genuinely apply to them
- **B.** Suppressing any finding the scanner marks low confidence, since low-confidence findings are false positives by definition
- **C.** Removing duplicates automatically by tool, since the scanner that reports a finding last is always the least reliable one
- **D.** Recording a documented reason each time a finding is suppressed, so every filtering decision remains auditable afterward  ✅

> **Answer:** D

### Q10. Why does the method insist on assembling scanners into a repeatable pipeline rather than running them ad hoc each engagement?

- **A.** A fixed pipeline runs faster, since caching scanner results across clients avoids recomputing the same checks repeatedly
- **B.** A pipeline removes the need for manual review, since a mature automated pass eventually covers every audit layer completely
- **C.** Same scanners, same order, same parsing every audit makes results comparable across time and across different clients  ✅
- **D.** Repeatability satisfies the client contract, since engagements legally require identical tooling on every single codebase

> **Answer:** C

### Q11. An auditor reads a dependency report showing a high-severity CVE in a package that the application code never actually invokes. How should this be triaged?

- **A.** As fix-now, since any high-severity CVE in the manifest is an immediate emergency regardless of whether it is reachable
- **B.** As identical to a login-flow CVE, since severity ratings already account for reachability inside the published CVE score
- **C.** As a false positive to delete silently, since unreachable vulnerabilities never belong anywhere in the findings record
- **D.** As not-reachable, distinct from findings in live code paths, and communicated with that reachability context to the client  ✅

> **Answer:** D

### Q12. The method positions automated scanning as giving the audit its speed and its floor. What does the floor metaphor mean here?

- **A.** Scanning sets a hard ceiling on findings, since anything automation misses is by definition outside the audit's real scope
- **B.** Scanning is the cheapest layer, so it establishes the lowest price point at which a rapid audit can be profitably offered
- **C.** Scanning runs at the foundation layer only, checking infrastructure while manual review handles everything above it entirely
- **D.** Scanning establishes the reliable baseline of mechanical checks that no audit should ever fall below, done fast and cheaply  ✅

> **Answer:** D

### Q13. An auditor is selecting a static-analysis tool for a Python codebase specifically. Which tool does the method name for that language?

- **A.** Gitleaks, the scanner the method names for finding committed secrets across a repository's entire history
- **B.** Bandit, the static analyzer the method names for scanning Python source for dangerous patterns and weak calls  ✅
- **C.** Mozilla Observatory, the analyzer the method names for testing deployed security headers from outside the app
- **D.** Dependabot, the service the method names for surfacing known vulnerabilities in a project's declared dependencies

> **Answer:** B

### Q14. Two different scanners report what is clearly the same underlying root cause. What does the method direct the auditor to do during consolidation?

- **A.** Deduplicate them into a single finding, since the same root cause reported twice is one issue, not two separate ones  ✅
- **B.** Keep whichever finding has the higher severity rating and silently discard the other tool's version of the same issue
- **C.** Escalate the finding one level, since agreement between two distinct scanners is strong grounds to raise its priority
- **D.** Report both findings separately, since two tools independently flagging an issue doubles the evidence of its severity

> **Answer:** A

### Q15. An auditor configured header checks in application middleware and assumes the deployed site is protected. Why does the method require testing the live URL anyway?

- **A.** The hosting platform can strip or override headers the code sets, so the deployed reality may differ from the code's intent  ✅
- **B.** Live testing is faster than reading middleware, so it is simply the more efficient way to confirm the same information
- **C.** Middleware headers apply only to authenticated routes, so the live test is needed to cover the public pages separately
- **D.** Live testing satisfies the CVE database requirement, which only accepts header findings verified against a running server

> **Answer:** A

### Q16. The method warns against dumping raw cloud-auditor output into a report. What is the underlying reason benchmark tools specifically need heavy filtering?

- **A.** Benchmark tools scan slower than other classes, so their output arrives too late in the pipeline to filter properly
- **B.** Benchmark tools flag against a generic checklist, so many items describe what the benchmark says, not real exposure here  ✅
- **C.** Benchmark tools only run against production, so their findings are too risky to include without client sign-off first
- **D.** Benchmark tools cannot assign severity, so every finding arrives unranked and must be manually scored before reporting

> **Answer:** B

### Q17. An auditor parses every scanner's output into a common structure before filtering. What structure does the method specify for each finding?

- **A.** Layer, finding, evidence, and severity, a common shape that lets results from different tools be compared and filtered  ✅
- **B.** Tool name, timestamp, and raw output, preserving the scanner's exact formatting so nothing is lost during consolidation
- **C.** Severity and remediation only, since the layer and evidence belong in a separate technical appendix for implementers
- **D.** CVE number and package name, since every automated finding ultimately reduces to a dependency vulnerability identifier

> **Answer:** A

### Q18. The method describes the $200 rapid audit as economically possible largely because of automated scanning. What is the mechanism behind that economics?

- **A.** Scanners eliminate the manual pass, so a rapid audit can be delivered entirely by automation with no auditor time at all
- **B.** Scanners are free, so the entire $200 is margin once the pipeline has been configured a single time for all clients
- **C.** Scanners do in minutes what manual review does in days, automating the mechanical layer that would otherwise dominate cost  ✅
- **D.** Scanners run overnight, so the audit consumes no business-hours labor and can therefore be priced near zero profitably

> **Answer:** C

### Q19. An auditor is choosing tools to check the deployed transport security of an application. Which class of tool does the method assign to that check?

- **A.** Dependency scanners like Snyk, which read the manifest to find packages with known transport-layer vulnerabilities inside
- **B.** SSL/TLS checkers and header analyzers, which test the live endpoint's certificate health, protocol versions, and headers  ✅
- **C.** Static analyzers like Semgrep, which read the source to confirm the code configures TLS correctly before deployment
- **D.** Secret scanners like TruffleHog, which ensure no private TLS keys were accidentally committed into the repository history

> **Answer:** B

### Q20. During consolidation an auditor suppresses a finding as a false positive. What does the method require accompany that suppression?

- **A.** Client approval in writing, because suppressing any scanner finding transfers liability that only the client can accept
- **B.** A second scanner confirming absence, because no single tool's silence is sufficient grounds to suppress a finding alone
- **C.** A recorded reason for the suppression, because filtering is a judgment call that must remain auditable after the fact  ✅
- **D.** Removal from the pipeline, because a rule that produced a false positive should not run against future codebases again

> **Answer:** C

### Q21. An auditor triages a dependency report into three buckets. Which set of buckets matches the method's approach to dependency findings?

- **A.** Frontend, backend, and database, sorting each vulnerable package by which architectural layer it happens to serve within
- **B.** Free, paid, and deprecated, sorting each vulnerable package by its licensing status before any severity is considered
- **C.** Critical, high, and medium, applying the CVE severity score directly with no adjustment for the app's actual usage
- **D.** Fix-now, fix-scheduled, and not-reachable, sorting by severity and whether the vulnerable path runs in this application  ✅

> **Answer:** D

### Q22. The method groups Semgrep matches by pattern and lists every file per pattern rather than reporting matches file by file. What does this grouping surface?

- **A.** The deployment topology, since grouping by pattern reveals which server each vulnerable file is ultimately deployed onto
- **B.** The replicated families of a flaw, since one pattern spanning many files is exactly the AI replication problem made visible  ✅
- **C.** The dependency graph, since patterns that co-occur across files indicate which packages introduced the vulnerable code
- **D.** The session boundaries, since each pattern group corresponds precisely to one generation session that produced those files

> **Answer:** B

### Q23. An auditor scoping a cloud audit limits the run to the services the application actually uses. What problem does scoping prevent?

- **A.** It prevents the scanner from timing out, since an unscoped cloud audit exceeds the provider's API rate limits every time
- **B.** It prevents access errors, since unscoped audits require permissions the auditor is rarely granted during an engagement
- **C.** It prevents duplicate findings, since scoping is the only reliable mechanism the pipeline has for deduplicating cloud output
- **D.** It prevents drowning in inapplicable benchmark items, since an unscoped run flags services the business does not even run  ✅

> **Answer:** D

### Q24. An auditor is directing AI to parse a scanner's raw output. Why does the method treat parsing as a required step rather than an optional convenience?

- **A.** Parsing compresses the output, since raw scanner logs are too large to store in the audit record without reduction first
- **B.** Parsing translates the findings, since scanners report in languages the client's own engineering team cannot read directly
- **C.** Parsing turns raw output into a common finding structure, without which deduplication and filtering cannot run at all  ✅
- **D.** Parsing ranks the findings, since raw output arrives unordered and the client expects severity sorting above all else

> **Answer:** C

### Q25. Looking across everything in this module, what is the governing principle for directing automated scans?

- **A.** Automate the mechanical floor, then direct the tools: right tool, right scope, parsed output, and evidence-filtered signal  ✅
- **B.** Trust scanner severity ratings as final, because automated tools weigh exploitability more objectively than any human can
- **C.** Run more tools than any competitor, because scanner coverage breadth is the single strongest signal of audit thoroughness
- **D.** Deliver raw output quickly, because clients value the speed of unfiltered scanner results over the delay of careful curation

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106568628_
