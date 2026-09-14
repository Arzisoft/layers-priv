---
course: "The Vault"
module: "Module 4 — Industry-Specific Trigger Points"
lesson: "Module 4: Industry-Specific Trigger Points — Exam"
type: "course_quiz"
post_id: 106173688
space_id: 24302166
source: "https://the-faction.mn.co/posts/106173688"
updated: "2026-08-27T20:10:51Z"
---

# Module 4: Industry-Specific Trigger Points — Exam

> Exam for **Module 4 — Industry-Specific Trigger Points** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A vibecoder ships a booking app for a dental practice. It stores patient names, appointment reasons, and a notes field. Nobody said HIPAA on the sales call. What is the compliance reality?

- **A.** Nothing triggers until the practice formally notifies the builder in writing that HIPAA governs the project
- **B.** HIPAA obligations rest only on the dental practice itself, so the builder carries no duties for the stored data
- **C.** The app is fine because appointment scheduling data does not count as medical treatment data under federal rules
- **D.** Handling that data for a covered entity likely makes the builder a business associate with HIPAA obligations  ✅

> **Answer:** D

### Q2. You build a wellness tracking app sold directly to consumers. No doctor, health plan, or clearinghouse touches the data anywhere in the chain. How should you think about health rules?

- **A.** All health data is HIPAA data, so you must sign a Business Associate Agreement with every user at signup
- **B.** You are fully unregulated, because HIPAA is the only law in the United States that covers health information
- **C.** You likely sit outside HIPAA, but FTC health data rules and state privacy laws may still apply to the build  ✅
- **D.** You must register the app with federal regulators as a consumer health device before launching it publicly

> **Answer:** C

### Q3. A covered entity wants your tool to sync patient records between their EHR and a reminder service. At what point do you become a business associate under HIPAA?

- **A.** Only if a human on your team reads record contents, since fully automated processing is exempt from scope
- **B.** Only when the contract value crosses the federal small business threshold set for health industry vendors
- **C.** Never, because subcontractors and outside tool vendors sit beyond HIPAA no matter what data they handle
- **D.** When you create, receive, maintain, or transmit PHI on behalf of the covered entity in that data chain  ✅

> **Answer:** D

### Q4. A dental client is ready to send patient data into your app next week. What does the module say about the Business Associate Agreement?

- **A.** A signed BAA must be in place before any PHI flows, since it formalizes your business associate obligations  ✅
- **B.** The BAA is optional paperwork that only matters if the practice ever gets audited by its own malpractice insurer
- **C.** A BAA can be signed within ninety days after launch as long as the data stays encrypted while you wait
- **D.** BAAs apply only to hospitals and health plans, so a small dental practice never needs one from a vendor

> **Answer:** A

### Q5. Midway through a health-adjacent build you realize you cannot tell whether a covered entity sits anywhere in your data chain. What is the right move?

- **A.** Treat it as a counsel question and stop for a professional answer instead of guessing at your HIPAA status  ✅
- **B.** Assume you are outside HIPAA, since the burden falls entirely on the client to prove a covered entity is involved
- **C.** Ship the build and monitor for complaints, because enforcement only ever follows a reported data breach
- **D.** Add encryption everywhere, which satisfies HIPAA automatically no matter who sits in the data chain

> **Answer:** A

### Q6. A federally funded school district asks for a gradebook tool that stores student names, grades, and behavior notes. Which trigger should the builder flag first?

- **A.** COPPA, because every product used inside any school building is automatically directed at young children
- **B.** FERPA, because the product handles student education records for a funded school and limits their reuse  ✅
- **C.** GLBA, because collecting school tuition payments makes the district a financial institution under the law
- **D.** No trigger, because education software is exempt from federal privacy rules whenever a district buys it

> **Answer:** B

### Q7. Your study buddy app uses bright cartoon characters and markets to elementary schoolers. Kids sign themselves up from home. What does COPPA demand here?

- **A.** Nothing at all, since COPPA applies only when you hold actual documented proof that a specific user is under thirteen
- **B.** A checkbox where the child confirms a parent said yes, which counts as valid consent under the rule
- **C.** Verifiable parental consent and strict data limits, since the service looks directed at kids under thirteen  ✅
- **D.** An age gate alone, because a birthday dropdown fully discharges duties for child-directed services

> **Answer:** C

### Q8. An edtech tool serves school classrooms and also offers a home version popular with nine year olds. How should the builder treat FERPA and COPPA?

- **A.** Follow whichever one the school names in the contract, since one federal rule governs any single app
- **B.** Set both aside until a regulator reaches out, because edtech enforcement actions are essentially unheard of
- **C.** Treat both as live until proven otherwise, since one build can trip student records and under-13 triggers  ✅
- **D.** Apply COPPA only, because FERPA duties always fall entirely on the school and never shape the product

> **Answer:** C

### Q9. A regional lender hires you to build a borrower portal processing applications with income and account details. You are not a bank. What is your GLBA exposure?

- **A.** You can land in GLBA scope as a service provider handling nonpublic personal information for the lender  ✅
- **B.** None, because GLBA regulates chartered banks only and never reaches vendors who build their software
- **C.** None, because borrower application data does not become financial information until a loan closes
- **D.** GLBA applies only if you retain the data past thirty days, so a short retention window keeps you outside its scope

> **Answer:** A

### Q10. You are adding a wallet feature where user funds sit in your company account for a day before paying out to sellers. What should stop you cold?

- **A.** Nothing, because holding funds for under a week is a recognized safe harbor across the state regimes
- **B.** A short terms of service update, since clear disclosure alone is what state regulators want to see on money flows
- **C.** PCI DSS paperwork, which is the framework governing any product that ever touches user payment data
- **D.** Money transmitter laws, since holding other people's funds can require state licensing and needs counsel  ✅

> **Answer:** D

### Q11. A vibecoder argues their marketplace only touches buyer money briefly before forwarding it to sellers, so licensing is not their problem. What does the module say?

- **A.** Brief custody is fine as long as the funds sit in a clearly labeled escrow subaccount held at your own company bank
- **B.** Even momentary holding of user funds can trigger transmitter laws, so route money through licensed processors  ✅
- **C.** Custody under twenty-four hours is exempt federally, so only slow payout schedules create licensing risk
- **D.** The exposure is civil fines only, so a small marketplace can rationally price the risk into its fees

> **Answer:** B

### Q12. Your fintech app wants a feature suggesting which tokenized assets users should buy based on their stated goals. What is the right posture?

- **A.** Treat securities and investment advice territory as a hard stop and bring in counsel before you build it  ✅
- **B.** Ship it with a prominent disclaimer that the app is not financial advice, which reliably neutralizes SEC exposure
- **C.** Proceed freely, because tokenized assets are digital goods sitting outside every securities framework
- **D.** Cap suggestions at five assets or fewer, which keeps recommendation features under regulatory notice

> **Answer:** A

### Q13. A law firm wants your tool to summarize client case files by sending them to a third-party AI API. What risk should the builder flag before writing code?

- **A.** Latency and cost, since legal documents run long and the API bills by token with no confidentiality angle
- **B.** Piping privileged client documents to an outside system without safeguards can put privilege itself at risk  ✅
- **C.** Copyright exposure, since court filings are government works that commercial models may not process
- **D.** None at all, because privilege restricts only what lawyers say in court, never how their vendors move the case files

> **Answer:** B

### Q14. You are pitching practice management software to a small law firm. Why should confidentiality shape your design from day one?

- **A.** Bar rules make lawyers vet vendors on technology and confidentiality, so weak design loses deals and risks clients  ✅
- **B.** Law firms are legally barred from cloud software, so confidentiality features earn an on-premise exemption
- **C.** Legal data is always HIPAA data, so the firm will demand a Business Associate Agreement before any pilot
- **D.** Privilege transfers to the vendor, making you the client's attorney of record the moment their data flows

> **Answer:** A

### Q15. You land a subcontract supporting a defense prime contractor's supply chain tooling. Which framework should be on your radar first?

- **A.** FERPA, because defense training programs count as federally funded education under the governing statute
- **B.** FedRAMP, which governs every product sold to any private company that also happens to hold a government contract
- **C.** CMMC, the certification framework that reaches defense supply chain work even at the subcontractor level  ✅
- **D.** COPPA, since military family programs mean defense products are presumed to be directed at children

> **Answer:** C

### Q16. A federal agency wants to adopt your cloud-hosted SaaS product. What certification reality should the builder be aware of before saying yes?

- **A.** Nothing special, because agencies procure cloud software under the same terms as any private customer
- **B.** CMMC, the framework that authorizes every civilian cloud service purchased by any federal agency
- **C.** A simple self-attestation letter, which is all that a federal buyer can legally ask any cloud vendor to provide
- **D.** FedRAMP, the authorization framework for cloud used by federal agencies, which takes months and real money  ✅

> **Answer:** D

### Q17. A builder plans to bolt accessibility onto their government portal after launch to hit the deadline. What does the module say about that plan?

- **A.** It is standard practice, since agencies expect the accessibility work to land in a post-launch remediation phase
- **B.** Retrofitting WCAG costs multiples of building it in, and government clients reject noncompliant deliverables  ✅
- **C.** It is safe, because Section 508 covers only internal federal tools and never public-facing portals
- **D.** Accessibility is purely voluntary for private builders, so a schedule slip is the only real business risk

> **Answer:** B

### Q18. Before quoting a price on any new client project, what does the module's toolkit tell you to do?

- **A.** Send the client a liability waiver stating that all regulatory compliance is entirely their responsibility
- **B.** Quote high across the board so any surprise regulation is already priced into every project you accept
- **C.** Run the industry trigger checklist and intake questions on users, data, industry, regulator, and counsel  ✅
- **D.** File a preliminary disclosure with each relevant regulator describing the build before writing any code

> **Answer:** C

### Q19. You run the AI Trigger Audit prompt against your build's actual data model and user flows. What is the audit's proper role?

- **A.** It certifies compliance, so a clean audit output means you can market the build as fully compliant
- **B.** It replaces counsel entirely, because a well-prompted model resolves regulatory questions as reliably as a lawyer
- **C.** It is mainly a sales artifact, giving clients a reassuring document whatever the flags actually say
- **D.** It flags likely triggers and drafts questions for a professional, never telling you that you are compliant  ✅

> **Answer:** D

### Q20. Why does the module tell builders to keep a Counsel Escalation Log on every project?

- **A.** It doubles your billable documentation hours, which compliance-minded clients expect to see invoiced
- **B.** Regulators demand a formal log from every software vendor operating in a regulated industry vertical
- **C.** It lets you skip actual counsel, since a well-kept log is treated as fully equivalent to legal advice if audited later
- **D.** It records where you decided counsel was or was not needed and why, protecting you if that call is questioned  ✅

> **Answer:** D

### Q21. A dentist client never mentions HIPAA and a school client never mentions FERPA during sales calls. What should the builder conclude?

- **A.** Silence means safety, because clients in regulated industries must disclose their regulations to vendors
- **B.** The contract should simply state that any regulation the client fails to mention is waived for the project
- **C.** Clients rarely name their regulations, so mapping the trigger points is the builder's job at every intake  ✅
- **D.** Regulations attach only when named in the statement of work, so careful drafting removes the exposure

> **Answer:** C

### Q22. A builder treats every scrap of health-related data in every app as HIPAA-covered, no matter who the customer is. What downside does the module identify?

- **A.** None, because over-compliance is always the cheapest and safest posture for a small independent builder
- **B.** Wasted effort on out-of-scope builds while missing the FTC and state health privacy rules that do apply  ✅
- **C.** It voids errors and omissions insurance, which excludes any builder who over-classifies their data types
- **D.** It creates HIPAA scope by itself, since claiming coverage in your policies creates the legal obligation

> **Answer:** B

### Q23. A builder wires every free-text field in their apps, including patient notes and student records, straight into a third-party AI model. What does the module warn?

- **A.** This is fine if the AI vendor is large and reputable, since their terms of service absorb the exposure
- **B.** Sending regulated data to a third-party model without proper agreements can itself be the violation  ✅
- **C.** Only the AI vendor carries exposure, because liability sits with whoever hosts the model weights
- **D.** The warning covers open source models only, since commercial APIs are certified for regulated data

> **Answer:** B

### Q24. After this module a builder can name CMMC, GLBA, and FERPA triggers on sight. What does the module say that knowledge amounts to?

- **A.** A map showing where to bring in professionals, which is boundary awareness and never a substitute for them  ✅
- **B.** Effective legal clearance, since trigger recognition is the substantive skill that regulators actually test
- **C.** Enough to self-certify small builds, reserving counsel for enterprise contracts above six figures
- **D.** A credential to sell paid compliance consulting to other builders working in regulated industries

> **Answer:** A

### Q25. Which statement best captures the governing principle of Module 4, Industry-Specific Trigger Points?

- **A.** Know which rules are watching each build: map the industry triggers, grasp their meaning, and stop for counsel  ✅
- **B.** Memorize the full text of every major regulation so you can make final compliance calls without outside professionals
- **C.** Avoid regulated industries entirely, since healthcare, finance, and government never pay off for builders
- **D.** Compliance belongs to the client, so a builder's only duty is a clause shifting all regulatory risk away

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106173688_
