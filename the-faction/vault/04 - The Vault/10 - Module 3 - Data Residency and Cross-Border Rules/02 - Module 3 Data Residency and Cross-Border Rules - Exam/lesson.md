---
course: "The Vault"
module: "Module 3 — Data Residency and Cross-Border Rules"
lesson: "Module 3: Data Residency and Cross-Border Rules — Exam"
type: "course_quiz"
post_id: 106173473
space_id: 24302166
source: "https://the-faction.mn.co/posts/106173473"
updated: "2026-08-27T20:10:51Z"
---

# Module 3: Data Residency and Cross-Border Rules — Exam

> Exam for **Module 3 — Data Residency and Cross-Border Rules** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. You are spinning up a Supabase project for an app whose users are all in Germany and France. The region picker defaults to us-east-1. What is the compliance-smart move?

- **A.** Keep us-east-1 since Supabase encrypts data at rest, which satisfies EU rules no matter where servers sit.
- **B.** Pick an EU region so personal data stays inside the EEA and you avoid needing a cross-border transfer mechanism.  ✅
- **C.** Keep the default region but add a privacy policy stating that data may be processed in the United States.
- **D.** Pick whichever region has the lowest latency, because performance choices and compliance choices are separate concerns.

> **Answer:** B

### Q2. A French user's data sits on a server in Virginia. Your cofounder says EU rules no longer apply because the data left Europe. What concept shows why that is wrong?

- **A.** Sovereignty: the laws tied to the user can follow the data after it leaves, even though it is resident in the US.  ✅
- **B.** Residency: once data is stored in Virginia, only United States law can govern how that data is used or shared.
- **C.** Adequacy: Virginia has been declared adequate by the EU, so the data automatically falls under American law only going forward.
- **D.** Localization: EU rules require deletion of any copy that leaves Europe, so the Virginia copy is simply unlawful.

> **Answer:** A

### Q3. You deploy a dashboard to Vercel with edge functions on default settings, and session data with user emails gets cached at edge locations worldwide. What just happened from a residency view?

- **A.** Personal data may now be processed in many jurisdictions at once, raising transfer questions in each of them.  ✅
- **B.** Nothing changed, because edge caches are temporary and residency rules only apply to permanent database storage.
- **C.** You are covered, because Vercel is a US company and its own compliance automatically extends to your application.
- **D.** Only your primary database region matters, so the edge locations never enter the compliance picture at all.

> **Answer:** A

### Q4. A SaaS vendor's terms say EU customer data flows to their US servers under pre-approved contract terms signed between sender and receiver. Which transfer mechanism is that?

- **A.** An adequacy decision, where one government declares another country's data protections good enough for free flow.
- **B.** Binding corporate rules, the regulator-approved internal policies used for transfers within one multinational.
- **C.** Standard Contractual Clauses, the pre-approved contract workhorse that most SaaS vendors rely on for transfers.  ✅
- **D.** A data localization waiver, a one-time export permit that regulators grant to individual vendors on request.

> **Answer:** C

### Q5. Your EU users' data flows to a US vendor certified under the EU-US Data Privacy Framework, with no extra contract terms in place. Which mechanism is likely doing the work?

- **A.** Standard Contractual Clauses, since every EU to US flow is automatically covered by them once a vendor certifies.
- **B.** An adequacy decision, where the EU has declared the framework's protections good enough for data to flow freely.  ✅
- **C.** Binding corporate rules, because certification under the framework makes the vendor part of your corporate group.
- **D.** No mechanism applies, because EU personal data can never lawfully be processed on servers in the United States.

> **Answer:** B

### Q6. A multinational moves employee data between its own subsidiaries in Germany, India, and Brazil under internal policies approved by a regulator. Which mechanism is that?

- **A.** Standard Contractual Clauses, since every transfer between corporate entities requires a fresh signed contract.
- **B.** An adequacy decision, because regulators only approve internal transfers between countries already deemed adequate.
- **C.** A sub-processor agreement, which is the standard vehicle for moving data between subsidiaries of one company.
- **D.** Binding corporate rules, the regulator-approved internal policies covering transfers inside one multinational.  ✅

> **Answer:** D

### Q7. Your app runs on a Frankfurt database, but your analytics, error tracker, and email provider all process user emails in the US. A customer asks where their data lives. What is the accurate picture?

- **A.** Frankfurt only, because third-party tools are separate processors and their locations count as their problem.
- **B.** Frankfurt only, since analytics and logging data are anonymous by nature and fall outside residency questions.
- **C.** The US only, because once any single service touches data there, the entire application becomes US resident.
- **D.** Frankfurt plus the US, because every third-party service touching personal data is part of the residency map.  ✅

> **Answer:** D

### Q8. You are building a portal for a Canadian provincial public-sector client. They insist data stays on Canadian servers even though PIPEDA allows transfers with accountability. What should you recognize?

- **A.** Some provinces and public-sector contracts expect Canadian hosting, so the client's requirement is a real pattern.  ✅
- **B.** The client is mistaken, because PIPEDA federally overrides any provincial or contractual hosting expectations.
- **C.** Canadian residency is impossible to deliver, because the major cloud providers offer no regions inside Canada.
- **D.** The requirement only applies to health data, so general citizen records can be hosted anywhere with encryption in place.

> **Answer:** A

### Q9. A telehealth startup in Australia asks you to store patient records in a cheap us-west-2 setup because it is faster to ship. What should raise your hand before you build?

- **A.** Nothing, because Australia has adopted full adequacy with the United States, so health data flows without limits.
- **B.** Only the backup strategy, since Australian rules focus on backup redundancy rather than where records are hosted.
- **C.** Australia restricts offshore disclosure with strict rules for health records, so this needs professional review.  ✅
- **D.** The latency for Australian users, which is the primary reason regulators discourage hosting records offshore.

> **Answer:** C

### Q10. You are picking a region for an app serving users in India. A teammate says India bans all cross-border data transfers outright. What does the DPDP Act actually do?

- **A.** It requires all personal data of Indian users to be stored on servers physically located inside India at all times.
- **B.** It mirrors the GDPR adequacy system, so transfers are only lawful to countries the EU has already approved first.
- **C.** It permits transfers only inside one corporate group under regulator-approved binding internal policies today.
- **D.** It permits transfers generally but blocks them to specific blocklisted countries, so most regions remain usable.  ✅

> **Answer:** D

### Q11. Your app is growing in Brazil and you need to reason about moving Brazilian user data to US servers. Which mental model does the module say fits the LGPD?

- **A.** Treat it like India's DPDP, where transfers flow freely unless Brazil has blocklisted the destination country.
- **B.** Treat it like the GDPR, since the LGPD mirrors that transfer model with mechanisms like adequacy and clauses.  ✅
- **C.** Treat it as fully open, because Brazil has no cross-border transfer rules for private-sector applications yet.
- **D.** Treat it as fully closed, because the LGPD requires all Brazilian personal data to stay on servers in Brazil.

> **Answer:** B

### Q12. A client wants to launch the same product in the UAE and Saudi Arabia. How should you approach data residency planning for the Middle East?

- **A.** Apply one regional standard, since the Gulf countries harmonized their data laws under a single shared framework.
- **B.** Assume GDPR compliance covers it, because Middle East regimes copy EU rules and accept the same EU mechanisms.
- **C.** Host in the EU for both markets, which automatically satisfies every localization rule across the entire region.
- **D.** Check each country and sector individually, because regimes vary sharply and UAE rules may not fit Saudi Arabia.  ✅

> **Answer:** D

### Q13. You are drafting the data location inventory for your compliance map. Which set of items belongs in it?

- **A.** The primary database region only, since backups and logs are just copies whose location changes no obligations at all.
- **B.** Primary database, backups, file storage, logs, and each third party touching data, with region and country listed.  ✅
- **C.** Only services with signed enterprise contracts, because free-tier tools fall outside residency obligations.
- **D.** Only production systems, since staging environments and log pipelines never contain any real personal data.

> **Answer:** B

### Q14. A builder never touched the AWS region picker, shipped on us-east-1, and then landed an EU customer. What does the module say about that default?

- **A.** Defaults are safe harbors, since cloud providers preconfigure regions to satisfy the strictest global regimes.
- **B.** Defaults are neutral until a regulator objects, so obligations only begin once a complaint has been filed.
- **C.** Defaults only matter on paid tiers, because free-tier infrastructure is exempt from residency obligations.
- **D.** Defaults are decisions, so accepting us-east-1 was a choice that now creates cross-border transfer questions.  ✅

> **Answer:** D

### Q15. Your database lives in an EU region, but your US-based support team routinely opens customer records from laptops in Texas. Does the EU hosting settle the residency picture?

- **A.** Yes, because residency rules only govern where data is stored at rest, not where humans view or process it day to day.
- **B.** No, because processing and support access count too, so US access to EU data still raises transfer questions.  ✅
- **C.** Yes, so long as support sessions are encrypted in transit, which keeps the data legally resident in the EU.
- **D.** No, because any US access instantly makes the whole database US resident and voids your EU region choice.

> **Answer:** B

### Q16. You want to know where a vendor really sends your users' data after it leaves your code. Which resource does the module point you to?

- **A.** The vendor's published sub-processor list, which shows who they share data with and where it gets processed.  ✅
- **B.** The vendor's marketing site, since compliance badges shown there are legally binding statements of location for users.
- **C.** The vendor's status page, because uptime regions reliably reveal every country where data gets processed.
- **D.** The vendor's pricing tiers, since enterprise plans are the only ones involving cross-border data processing.

> **Answer:** A

### Q17. Your residency audit finds personal data leaving the EU to a vendor with no adequacy decision, no SCCs, and no binding corporate rules in their terms. What is the right builder move?

- **A.** Flag it for professional review before shipping, since a transfer with no mechanism is an escalation trigger.  ✅
- **B.** Ship anyway and self-certify the transfer, since builders can adopt clauses unilaterally by updating their terms.
- **C.** Delete the EU users from the database, which is the standard remediation the module recommends for this case.
- **D.** Add a consent checkbox at signup, which fully replaces the need for any formal transfer mechanism in the EU.

> **Answer:** A

### Q18. A vendor's terms mention SCCs, and your teammate declares the integration fully compliant for your EU launch. What is the correct read?

- **A.** The teammate is right, because SCCs in a vendor's terms automatically cover every customer's specific use case.
- **B.** The teammate is right if the vendor is US based, since SCCs were designed to blanket all EU to US data flows.
- **C.** A mechanism exists, but whether your specific use is covered is a separate question for a professional to confirm.  ✅
- **D.** SCCs are obsolete, so the mention signals the vendor has not updated its terms and should be dropped from your stack.

> **Answer:** C

### Q19. You enable CDN caching for API responses containing profile data, and the platform caches them at 30 edge locations. What is the residency consequence?

- **A.** None, because CDN caches are ephemeral, and residency rules only count storage lasting more than thirty days.
- **B.** One extra jurisdiction at most, since CDNs legally count as an extension of your origin server's home region.
- **C.** You must disable caching entirely, because static assets and personal data are treated identically at the edge.
- **D.** Potentially 30 jurisdictions, because caching personal data at each edge location can put it under new laws.  ✅

> **Answer:** D

### Q20. You run the AI residency audit prompt against your stack and it produces a tidy data flow map. What does the module say to do before relying on it?

- **A.** Verify the map against provider documentation, because the output is only as good as its underlying accuracy.  ✅
- **B.** Ship it directly to customers, since AI-generated maps are accepted by regulators as authoritative records.
- **C.** Discard it and start over manually, because AI output has no place anywhere in a serious compliance mapping workflow.
- **D.** Have the AI certify legal sufficiency itself, since the prompt tells it to reach binding legal conclusions.

> **Answer:** A

### Q21. You build client apps on an edge-first platform that distributes data globally by default. What is the risk to your clients specifically?

- **A.** None, since compliance obligations attach to the platform vendor rather than the client whose app you built.
- **B.** Slower page loads in a few regions, the main downside the module identifies for global edge distribution.
- **C.** They inherit your hosting decisions without knowing it, gaining obligations in countries they never heard of.  ✅
- **D.** Higher hosting bills only, because compliance exposure never varies with where an application's data lives.

> **Answer:** C

### Q22. An EU prospect's legal team asks where their data is processed, and the deal stalls while you scramble. Which module artifact is built to answer that question cleanly?

- **A.** The uptime dashboard, which shows every region where your infrastructure has ever served production traffic.
- **B.** The data location inventory, listing every place data is stored or processed with its region and country.  ✅
- **C.** The privacy policy alone, since a well-written policy substitutes for knowing where data actually resides.
- **D.** The penetration test report, which certifies data location as part of its standard security assessment scope.

> **Answer:** B

### Q23. A builder ships worldwide on an edge platform because deployment was one click, despite having users only in the US and Canada. What pitfall is that?

- **A.** Under-provisioning, since the module warns single-region deployments cannot survive customer due diligence.
- **B.** Vendor lock-in, which the module flags as the primary compliance risk of edge-first deployment platforms.
- **C.** Deploying globally because the platform makes it easy, creating obligations in markets with zero users.  ✅
- **D.** Cache poisoning, the security failure the module says follows from distributing an application worldwide.

> **Answer:** C

### Q24. You pass the Module 3 exam and finish a residency map for your app. A client asks if that certifies their build as compliant. What does certification actually prove?

- **A.** That the build is fully compliant in every region listed on the map, with no further professional input needed.
- **B.** That you are qualified to give legal advice on transfers, since the exam covers the same ground as counsel.
- **C.** That you can build the residency portion of a compliance map, while compliance judgment stays with professionals.  ✅
- **D.** That your infrastructure choices are permanently locked, because certification freezes the audited architecture.

> **Answer:** C

### Q25. Which statement best captures the governing principle of Module 3?

- **A.** Data lives somewhere physical and hosting choices are legal choices, so map where it lives and flows before you ship.  ✅
- **B.** Cross-border transfer law is settled and uniform worldwide, so one compliant architecture works in every market.
- **C.** Compliance is a lawyer's job alone, so builders should avoid learning residency concepts and defer everything.
- **D.** Data location only matters for regulated industries, so general consumer apps can ignore residency entirely.

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106173473_
