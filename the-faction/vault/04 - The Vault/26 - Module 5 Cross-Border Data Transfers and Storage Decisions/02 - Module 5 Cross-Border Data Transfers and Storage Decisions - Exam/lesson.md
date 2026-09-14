---
course: "The Vault"
module: "Module 5: Cross-Border Data Transfers and Storage Decisions"
lesson: "Module 5: Cross-Border Data Transfers and Storage Decisions — Exam"
type: "course_quiz"
post_id: 107139925
space_id: 24302166
source: "https://the-faction.mn.co/posts/107139925"
updated: "2026-09-10T19:53:50Z"
---

# Module 5: Cross-Border Data Transfers and Storage Decisions — Exam

> Exam for **Module 5: Cross-Border Data Transfers and Storage Decisions** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder picks a hosting region from a platform dropdown without much thought. How does this module characterize that click?

- **A.** As a performance tuning decision, since region choice affects latency and nothing else the client will ever ask the builder about
- **B.** As a reversible preference, since modern platforms migrate projects between regions automatically whenever requirements change
- **C.** As a billing decision, since regional price differences are the main consequence that follows from the selection made there
- **D.** As a legal decision that outlives the project: where data lives determines which laws attach and what residency you can promise  ✅

> **Answer:** D

### Q2. A client says their data is safe because it is 'in the cloud' rather than in any country. What does this module say?

- **A.** The cloud is not a place: it is someone's data centers in specific countries, chosen by you, often by default, with legal reach attached  ✅
- **B.** The client is right, since cloud storage is legally stateless and jurisdiction only attaches to data on physical office servers
- **C.** The client is right for major providers, since hyperscalers negotiate blanket exemptions from national data protection laws
- **D.** The question is unanswerable, since providers keep data center locations secret and no builder can find out where data sits

> **Answer:** A

### Q3. An app moves EU user records to a US server for processing. The team means well. How does this module classify the move?

- **A.** As an internal operation, since data moving between servers owned by the same company never crosses a legal boundary at all
- **B.** As a transfer that needs a recognized mechanism, not just a good intention, since GDPR-style laws restrict such flows  ✅
- **C.** As a non-event if the data is encrypted in transit, since transport security is what the transfer rules were written to ensure
- **D.** As a violation in every case, since EU personal data can never lawfully reach US infrastructure under any arrangement

> **Answer:** B

### Q4. A builder asks how data can flow to some countries with no extra paperwork. Which mechanism explains this?

- **A.** Adequacy decisions: the EU has declared some countries adequate, and transfers to those destinations flow freely without more  ✅
- **B.** Trade agreements: countries in shared tariff zones automatically exchange personal data under their commerce provisions
- **C.** Reciprocity rules: any country hosting EU embassies gains equivalent data status by longstanding diplomatic convention
- **D.** Volume thresholds: transfers under a set number of records per year are exempt from the restrictions that catch the larger flows

> **Answer:** A

### Q5. A US email provider claims it can lawfully receive EU personal data. Which credential from this module supports that claim?

- **A.** A US state privacy registration, since compliance with any American statute demonstrates equivalence with EU protections
- **B.** An ISO security certificate, since technical security certifications are what the EU examines when approving recipients
- **C.** Certification under the EU-US Data Privacy Framework, since US companies certified under the DPF can receive EU data  ✅
- **D.** A generous free tier, since consumer-friendly commercial terms are treated as evidence of trustworthy data handling

> **Answer:** C

### Q6. No adequacy covers a destination and the provider is not DPF certified. What does this module say usually fills the gap, and whose job is it?

- **A.** Nothing can fill the gap, so the builder must abandon the provider and redesign the whole architecture around an EU-only vendor set
- **B.** Standard Contractual Clauses: pre-approved terms lawyers attach; the builder's job is knowing they exist and flagging the flow  ✅
- **C.** A custom transfer treaty the builder drafts, since writing bespoke legal instruments is part of directing a compliant build
- **D.** A user checkbox at signup, since individual consent replaces every transfer mechanism whenever a provider lacks its own

> **Answer:** B

### Q7. A client with EU users wants to launch on a US default region and fix residency later if a deal demands it. What does this module say?

- **A.** The plan is sound, since region migrations are routine platform operations that vendors complete within a support ticket
- **B.** The plan is sound as long as the client accepts the risk in writing, since informed sign-off converts the gamble into strategy
- **C.** Region choice barely matters before product-market fit, since regulators focus their attention on companies at scale
- **D.** Hosting region is a day-one decision with day-1000 consequences: platforms make moving painful, so EU expectations mean EU region now  ✅

> **Answer:** D

### Q8. You are scoping a build for a client with enterprise prospects. Per this module, which question belongs in the first conversation?

- **A.** Which JavaScript framework the client prefers, since front-end choices constrain the hosting regions available downstream
- **B.** How much funding the client has raised, since compliance architecture is only worth discussing past a revenue threshold
- **C.** Where the users are and whether law, contracts, or customer expectations impose residency requirements on the data  ✅
- **D.** Whether the client has cyber insurance, since coverage status determines how carefully regions need to be selected

> **Answer:** C

### Q9. A build uses a database, an email provider, analytics, an error tracker, payments, and an AI API. What does this module say about locations?

- **A.** Each service is its own data flow with locations, and the build inherits all of them; list them with regions where known  ✅
- **B.** Only the database location matters, since third-party services act as utilities rather than as destinations for personal data
- **C.** Only paid services matter, since free-tier tools process too little data to register as flows in a residency analysis
- **D.** Locations are the responsibility of each vendor, so the builder needs no inventory beyond the primary hosting region

> **Answer:** A

### Q10. A team says 'our residency story is fine, the database is in the EU,' while their analytics and error tracker run in the US. What is the verdict?

- **A.** The story holds, since the database is the system of record and auxiliary tooling sits outside any residency assessment
- **B.** The build's residency story is its weakest component's: the analytics and error tracker flows undermine the EU claim  ✅
- **C.** The story holds if US tools receive under one percent of records, since materiality thresholds govern residency claims
- **D.** The story holds once the notice discloses the US tools, since disclosure converts a weak residency posture into a sound one

> **Answer:** B

### Q11. A builder signs a provider DPA and concludes all transfer questions are settled. What distinction does this module draw?

- **A.** DPAs are marketing documents with no legal weight, so signing one accomplishes nothing and transfer analysis starts from zero
- **B.** DPAs replace transfer mechanisms for any provider that offers them, so the conclusion is right whenever a DPA has been signed
- **C.** DPAs matter only for providers processing sensitive categories, so routine tooling needs neither a DPA nor any mechanism
- **D.** A DPA governs the processing relationship; transfers out of protective regimes still need a mechanism: related but different  ✅

> **Answer:** D

### Q12. A client wants to tell customers 'all data stays in the EU.' Before that ships, what does this module require?

- **A.** That the data-flow map actually supports the claim, backups and support access included; promise only what you can show  ✅
- **B.** That the claim appear in the terms of service, since placing a residency statement in a legal document is what makes it true
- **C.** That marketing approve the wording, since residency claims are brand positioning rather than verifiable statements of fact
- **D.** That the claim be softened to aspirational language, since no architecture can ever support a residency statement fully

> **Answer:** A

### Q13. A build sends support ticket text to an AI API for summarization. How does this module treat that integration?

- **A.** As invisible processing, since AI providers transform data rather than store it, which keeps the whole flow outside residency analysis
- **B.** As exempt tooling, since developer APIs are infrastructure and infrastructure sits outside the data-flow inventory entirely
- **C.** As a data flow to that service's region under that service's terms: classify what you send and check the provider like any vendor  ✅
- **D.** As a prohibited pattern, since personal data can never lawfully reach a machine learning service under current transfer law

> **Answer:** C

### Q14. One provider in the build offers no adequacy coverage, no DPF certification, and no SCC option for EU data. What is the move this module directs?

- **A.** Accept the flow quietly, since one weak link among many compliant providers rarely draws attention in a working system
- **B.** Terminate the client engagement, since a single unresolved transfer gap makes the entire project legally unbuildable
- **C.** Add extra encryption to that flow, since sufficiently strong technical measures substitute for any legal transfer mechanism
- **D.** Flag it as a problem to raise, not to quietly accept: the gap goes to counsel while you present the map and the options  ✅

> **Answer:** D

### Q15. An enterprise questionnaire asks where employee data is stored and under which transfer mechanisms. Which artifact answers it in minutes?

- **A.** The documented data-flow map: regions, providers, mechanisms, and DPAs signed, kept current as part of the standard kit  ✅
- **B.** The platform invoice history, since billing records show which regional data centers the project has been paying for all along
- **C.** The original project proposal, since scoping documents capture the architecture as the client first approved it
- **D.** The codebase itself, since a sufficiently careful reviewer can reconstruct every data flow from configuration files

> **Answer:** A

### Q16. You want AI to start the transfer analysis for an existing build. Which prompt matches the directing pattern in this module?

- **A.** Certify this architecture as compliant with all transfer rules and produce a signed legal statement for the client file
- **B.** Rewrite the privacy notice to say data may be processed anywhere, so the architecture never needs a transfer analysis again
- **C.** List every third-party service in this build and what personal data flows to each, as a table of service, data, and region options  ✅
- **D.** Pick the cheapest region for each service, since transfer analysis begins from the full cost profile of the candidate architecture

> **Answer:** C

### Q17. You direct AI to summarize a provider's stance on regions, DPAs, and EU transfers. What does this module add to that instruction?

- **A.** Trust the summary as delivered, since provider documentation is stable enough that verification adds delay without value
- **B.** Have it cite the pages so you can verify the current state on the provider's own site before relying on any of it  ✅
- **C.** Run the summary twice with two models and keep whichever answer describes the provider more favorably for the build
- **D.** Skip the documentation entirely, since sales representatives are the authoritative source on compliance features

> **Answer:** B

### Q18. A year after launch, a team discovers their EU client's data has sat in a US region since day one. Which mistake from this module is this?

- **A.** Defaulting the region: the platform preselected a US region, nobody looked, and the legal consequences accumulated silently  ✅
- **B.** Over-engineering: the team chose infrastructure before requirements existed, and the region reflects premature optimization
- **C.** Vendor betrayal: the platform moved the data without notice, which is the risk this module says DPAs exist to prevent
- **D.** Under-monitoring: the region was right at launch but drifted, since platforms rebalance storage across regions over time

> **Answer:** A

### Q19. Two comparable providers could fill a slot in the build. Per this module, what serves as the tiebreaker that costs nothing at selection time?

- **A.** Brand logo recognition, since familiar brands reassure enterprise reviewers regardless of the underlying compliance posture
- **B.** Community sentiment, since developer forum opinions track compliance quality more closely than official documentation
- **C.** Free-tier generosity, since a larger free allocation leaves more budget for the compliance work that matters later
- **D.** Region options, DPA quality, and transfer posture: compliance features that are free to weigh when choosing between peers  ✅

> **Answer:** D

### Q20. A client wants to serve users in a country known for strict data localization norms. What does this module direct before architecture?

- **A.** Proceed with a standard EU region, since EU hosting satisfies every localization regime that any country has enacted
- **B.** Research the regime first: some countries expect in-country storage, and that expectation is a counsel conversation  ✅
- **C.** Serve the country from the nearest adjacent region, since geographic proximity is what localization rules measure
- **D.** Decline such markets by default, since localization norms make compliant service impossible for small teams to offer

> **Answer:** B

### Q21. A builder answers a residency question from memory of a provider's options from last year. What does this module say about that habit?

- **A.** Confirm current options on provider pages at build time rather than from memory; trust and compliance pages are the verification source  ✅
- **B.** Memory is acceptable for major clouds, since AWS, Google, and Azure region offerings have been stable for over a decade
- **C.** Memory is preferable to documentation, since provider pages describe aspirations while experience reflects actual behavior
- **D.** The habit is fine if the builder double-checks after launch, since post-deploy corrections carry no cost worth mentioning

> **Answer:** A

### Q22. A client asks 'so are we fully compliant on transfers?' after you present the data-flow map. Where does this module draw the line?

- **A.** Answer yes if every provider offers a DPA, since complete DPA coverage is the definition of transfer compliance for a build
- **B.** Answer no on principle, since builders should never express any view about the compliance posture of their own work
- **C.** Present the map and mechanisms; the legal conclusion routes to counsel, since judging a transfer's legality is lawyer work  ✅
- **D.** Answer yes if the client is small, since transfer enforcement begins only at enterprise scale and spares early builds

> **Answer:** C

### Q23. An architecture stores production data in the EU, but backups replicate to a US region and support staff access production from abroad. What does this module say?

- **A.** Backups are copies rather than data, so replication abroad sits outside the residency analysis a builder owes the client
- **B.** Support access is a human resources matter, so where staff log in from has no bearing on the residency story at all
- **C.** Backups and support access are part of residency: check where backups live and who can access production data from where  ✅
- **D.** Replication is acceptable when automatic, since only deliberate manual copies count as transfers under protective regimes

> **Answer:** C

### Q24. Most current users are in the US, but you recommend the EU region for a client with EU expansion plans. Who explains this choice to the client, and how?

- **A.** The platform vendor explains it, since region trade-offs are vendor knowledge and builders should not editorialize on them
- **B.** Nobody explains it, since architecture decisions are implementation details that clients neither read nor need to see
- **C.** The AI explains it autonomously, since communication drafting is exactly the category of judgment that builders hand off entirely
- **D.** You supply the judgment and direct AI to draft the short client-facing explanation of why the EU region is the right call now  ✅

> **Answer:** D

### Q25. Looking across this whole module, what is the governing principle of transfers and storage decisions?

- **A.** Residency is a procurement topic: buy from large enough vendors and the location questions answer themselves over time
- **B.** Location is law: choose regions deliberately on day one, map every flow, verify mechanisms, and flag gaps for counsel  ✅
- **C.** Residency is reputational: the goal is a confident answer to questionnaires, whatever the underlying flows actually do
- **D.** Location is temporary: since data moves constantly anyway, the discipline is documentation after the fact rather than choice

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/107139925_
