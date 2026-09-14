---
course: "The Vault"
module: "Module 5 — Compliance Documentation Systems"
lesson: "Module 5: Compliance Documentation Systems — Exam"
type: "course_quiz"
post_id: 106173851
space_id: 24302166
source: "https://the-faction.mn.co/posts/106173851"
updated: "2026-08-27T20:10:51Z"
---

# Module 5: Compliance Documentation Systems — Exam

> Exam for **Module 5 — Compliance Documentation Systems** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder ships an app with a template privacy policy stating 'we never share your data.' The app actually sends events to two analytics SDKs and a session replay tool. What is the core problem?

- **A.** The policy needs a lawyer's signature before publication, since only counsel can approve statements about sharing
- **B.** The policy is too short; regulators expect long, detailed documents, so it should be padded with standard clauses
- **C.** The analytics SDKs are the problem; all third party tools must be removed before any policy can be published
- **D.** The policy makes a false statement about actual data flows, and regulators can treat that misrepresentation itself as a violation  ✅

> **Answer:** D

### Q2. Your app loads Google Analytics on page load, then shows a cookie banner asking EU visitors for consent. An audit flags this setup. Why?

- **A.** Consent must happen before non-essential trackers fire; a banner shown after analytics loads is theater with no legal effect  ✅
- **B.** The banner needs to list every cookie by name and expiration date, and yours only summarizes the broad categories of tracking
- **C.** Google Analytics is banned outright in the EU, so no banner configuration could make loading it lawful for visitors there
- **D.** Banners are only required for advertising cookies, so the audit is wrong and analytics can load without consent

> **Answer:** A

### Q3. An enterprise prospect will not sign until you provide a Data Processing Agreement. Your SaaS stores their employees' personal data. What does this request signal?

- **A.** They are stalling the deal; a DPA is optional paperwork, so you should push back and offer your privacy policy instead
- **B.** They want you to accept controller status, meaning you would take over all their compliance obligations for the data
- **C.** They need proof of a security certification like SOC 2, and a DPA is simply the document certifying you passed the audit
- **D.** You are their processor under GDPR, and a written DPA covering scope, security, subprocessors, and breach terms is required  ✅

> **Answer:** D

### Q4. You are about to direct AI to draft your privacy policy. Per this module, what should exist before a single line of the policy gets written?

- **A.** A signed engagement with a privacy lawyer who will review the finished draft and certify it before it goes live
- **B.** A data flow inventory of what you collect, where it enters and lives, which vendors receive it, and how long it stays  ✅
- **C.** A competitor's published policy from the same niche, since apps in one product category share the same data practices anyway
- **D.** A cookie banner already deployed in production, because consent tooling determines what the policy may claim

> **Answer:** B

### Q5. A user claims they never agreed to your current terms of service. Which record actually settles the dispute in your favor?

- **A.** Your deployment history showing when the terms page went live, which proves the document existed at signup time
- **B.** A timestamped log of their affirmative agreement tied to the dated version of the terms they accepted at signup  ✅
- **C.** An email announcement you sent about the terms update, which shows users were notified even if they never opened the message
- **D.** The current published terms page, since posting terms on your site binds everyone who keeps using the app

> **Answer:** B

### Q6. You direct AI to draft a privacy policy and it produces a polished document in seconds. What is the mandatory next step before you publish it?

- **A.** Verify every claim against your actual data flows and vendor list, fixing any statement the app does not really honor  ✅
- **B.** Run it through a second AI model for a full grammar and tone pass, since polish is what regulators tend to evaluate first
- **C.** Publish it immediately and schedule a review for next quarter, because having any policy live beats having none
- **D.** Add extra protective promises beyond what the app does, since stronger commitments always reduce legal exposure

> **Answer:** A

### Q7. Your signup flow has no terms checkbox; the terms are linked only in the footer. Later you need to enforce your acceptable use clause against a user. What is the weakness?

- **A.** Terms must be actually agreed to; without affirmative acceptance like a signup checkbox, enforcing them gets shaky  ✅
- **B.** Footer links are fine legally, but the terms should also appear in the welcome confirmation email to strengthen the record
- **C.** The acceptable use clause itself is unenforceable in consumer apps, so a checkbox would not change anything here
- **D.** The weakness is length; short terms read as informal, so courts discount them however users accepted the deal

> **Answer:** A

### Q8. Your policy says chat logs are deleted after 90 days. You also hold consent records and deletion request logs. How long should each kind of record live?

- **A.** Keep everything for seven years, since a uniform long retention window is the safest default for every category of record
- **B.** Delete all of it at 90 days together, because mixed retention schedules look inconsistent to anyone auditing you
- **C.** Retention is a lawyer-only decision; builders should not set any schedule until counsel approves each category
- **D.** Keep compliance evidence long enough to prove what you did, but purge personal data once its stated retention ends  ✅

> **Answer:** D

### Q9. Completing a DPA annex, you list subprocessors. Your stack: Vercel hosting, an AI API for chat, Stripe, and a managed Postgres vendor. Which belong on the list?

- **A.** Only Stripe, because payment processors are the only vendor category regulators treat as processing personal data
- **B.** Every vendor that touches your customers' personal data, including your hosting and AI API providers, goes on it  ✅
- **C.** None of them; subprocessor refers to human contractors you hire, not the software services running in your stack
- **D.** Only vendors headquartered inside the EU, since GDPR obligations cannot attach to companies based outside Europe

> **Answer:** B

### Q10. A business customer's auditor asks you to demonstrate compliance. Per this module, what does being compliant partly mean in practice?

- **A.** Holding a certification badge on your website, since third party seals are what auditors are trained to check first
- **B.** Having a lawyer on retainer who can respond to the auditor, because producing records is inherently professional work
- **C.** Being able to produce evidence on request: data inventory, consent logs, DPAs, dated policy versions, request logs  ✅
- **D.** Showing the auditor your current privacy policy, since the live published document is the whole compliance record

> **Answer:** C

### Q11. The module's audit prompt flags crash reporting, session replay, and your AI API as receiving user data your policy never mentions. Why is this the most common mismatch in vibecoded apps?

- **A.** Because those vendors hide their data collection, so builders cannot reasonably discover what each SDK transmits
- **B.** Because policies legally cover only data users type into forms, so automatic collection sits outside the document
- **C.** Because AI coding tools add SDKs that are exempt from disclosure, and builders wrongly document them anyway
- **D.** Because builders document what they consciously collect and forget the SDKs quietly sending data to third parties  ✅

> **Answer:** D

### Q12. A SaaS founder loses momentum on an enterprise deal when the buyer asks for a DPA before signing. What lesson does the module draw from this pattern?

- **A.** Enterprise buyers use DPA requests mainly to renegotiate price, so founders should treat them as a bargaining tactic
- **B.** Founders should avoid enterprise customers until they can afford in-house counsel to field these requests
- **C.** Documentation is a sales asset, not just defense; builders who can produce accurate paperwork close deals faster  ✅
- **D.** DPAs are only needed after the contract is signed, so the buyer's request was premature and safe to defer

> **Answer:** C

### Q13. You have quietly edited your privacy policy five times this year with no changelog. A user now disputes what they consented to. What position are you in?

- **A.** Fine, since the server's file modification timestamps can reconstruct which version any given user actually saw
- **B.** Fine, because the newest published version automatically governs everyone who continues using the product
- **C.** Weak only if users complained at the time; silent edits are acceptable when no objections were ever raised
- **D.** Weak; without dated versions and update notices you cannot prove what any user agreed to at any point in time  ✅

> **Answer:** D

### Q14. Your app sets a session cookie for login, a fraud prevention cookie at checkout, and a marketing pixel on every page. For EU visitors, which needs consent before it fires?

- **A.** All three cookies equally, since EU rules require prior opt-in consent for anything a site stores on a device
- **B.** None of them, because consent rules cover only third party ad networks and your marketing pixel is first party
- **C.** The marketing pixel; it is non-essential tracking, while login and fraud prevention serve the service itself  ✅
- **D.** The fraud cookie only, since payment data is the most sensitive category and sensitivity determines consent

> **Answer:** C

### Q15. To look trustworthy, a builder adds 'we encrypt all data end to end' to their policy, though the app only uses TLS in transit. What has the builder done?

- **A.** Improved their posture, since aspirational commitments push teams to implement the described protections later
- **B.** Nothing risky, because overstating security is safer than understating it if a regulator ever comes reviewing
- **C.** Created a marketing claim living outside the privacy policy's legal scope, so it carries no compliance weight
- **D.** Made a misrepresentation; a policy overstating protections can be a violation on its own even with good intent  ✅

> **Answer:** D

### Q16. You are writing an AI prompt to audit your compliance docs. Per the module's template, which instruction makes the audit actually useful?

- **A.** Build the data inventory from the app itself, then compare it line by line against the policy and flag mismatches  ✅
- **B.** Ask the AI to confirm the documents look professional and complete, since presentation drives regulator impressions
- **C.** Provide only the policy text without the codebase, so the AI can evaluate the document on its own legal merits
- **D.** Instruct the AI to certify you as compliant at the end, so you hold a written record that a review took place

> **Answer:** A

### Q17. Your audit surfaces two findings: a retention period typo, and your policy covering health data flowing to an AI vendor for a big enterprise client. How do you triage?

- **A.** Both are wording fixes; audits by definition produce editing tasks, and AI can redraft each finding immediately
- **B.** Fix the typo yourself; the health data and enterprise finding is a signal to bring in a professional to scope it  ✅
- **C.** Escalate both to a lawyer, since once an audit finds anything a builder should stop touching the documents
- **D.** Ignore the health data finding until a customer actually asks, since triage means handling only what currently blocks you

> **Answer:** B

### Q18. Three months after launch you add a referral feature, a new email vendor, and start logging phone numbers. Your policy is untouched. What does the module say happened?

- **A.** Your documents have drifted from reality; new features, vendors, and data fields invalidate them until re-audited  ✅
- **B.** Nothing significant yet; policies only need updating on a fixed annual cycle regardless of what shipped in the meantime
- **C.** The email vendor is covered by its own policy, so only the phone number logging would require any update
- **D.** Your terms of service absorb the changes automatically, since terms govern features and policies govern data

> **Answer:** A

### Q19. You are building the module's Data Flow Inventory for your app. Which set of fields makes it the source of truth your other documents are written from?

- **A.** Feature names, sprint dates, and the developer responsible for each, so audits can assign accountability for each flow
- **B.** Each data category, where it enters, where it is stored, which vendors receive it, and how long it lives there  ✅
- **C.** Only the fields users type into forms, since automatic collection belongs in each vendor's own documentation
- **D.** Revenue per feature, so you can prioritize compliance spending on the data flows that earn the most money

> **Answer:** B

### Q20. A user emails asking you to delete their account data. You delete it. Per the module's record-keeping guidance, what else should exist afterward?

- **A.** Nothing; keeping any record of a deletion request defeats the purpose and recreates the data you just removed
- **B.** A log entry of the request and your action, kept as evidence you honored the right without hoarding their data  ✅
- **C.** A full backup of the deleted records, retained indefinitely in case the user ever comes back to dispute what was removed
- **D.** A notarized letter to the user confirming deletion, since informal email confirmations carry no real weight

> **Answer:** B

### Q21. A cofounder says 'we're fine, we have a privacy policy' and points to the published page. Per this module, what is the right response?

- **A.** Agree; the FTC and EU regulators primarily check that a policy exists, so publication is the main hurdle passed
- **B.** Ask whether a lawyer wrote it, since professional authorship separates valid policies from invalid ones
- **C.** Point out that having a policy is not the bar; the policy matching your actual data practices is what protects you  ✅
- **D.** Suggest making it longer, since detailed policies signal diligence and short ones invite regulator attention

> **Answer:** C

### Q22. You are directing AI to draft terms of service for your app. Which sections does the module say builders lean on hardest?

- **A.** Intellectual property assignment, jury trial waivers, and export controls, the clauses enterprises check first
- **B.** Pricing tables, refund windows, and service level guarantees, since money terms are what users actually read
- **C.** Acceptable use, disclaimers, and termination, plus making sure users affirmatively agree to a dated version  ✅
- **D.** Privacy disclosures and cookie notices, since modern practice merges compliance text into a single terms page

> **Answer:** C

### Q23. Your policy says 'we do not sell or share personal data.' Marketing wants to add a data enrichment vendor that ingests your user emails. What is the trigger to recognize?

- **A.** The new vendor makes your published statement false, so the policy must change before the data starts flowing  ✅
- **B.** Enrichment vendors are exempt from sharing disclosures because they return data to you rather than keeping it
- **C.** The statement stays fine as long as no money changes hands, since sharing legally requires payment in return
- **D.** Marketing tools fall under legitimate interest, which overrides whatever the published policy happens to say

> **Answer:** A

### Q24. You are drafting your first DPA for a B2B customer. Which contents does the module say the agreement must specify?

- **A.** What you process, your security obligations, your subprocessors, and what happens on breach or termination  ✅
- **B.** Your pricing, payment schedule, and renewal terms, since the DPA replaces the master service agreement itself
- **C.** A guarantee of zero data breaches, since customers sign DPAs specifically to transfer all liability onto you
- **D.** The customer's own privacy policy text, since a DPA works by importing the controller's documents wholesale

> **Answer:** A

### Q25. Which statement best captures the governing principle of Module 5, Compliance Documentation Systems?

- **A.** Compliance documents are legal formalities; once a professional publishes them they protect you regardless
- **B.** More documentation is always better; volume and detail are what demonstrate good faith to any regulator
- **C.** Every document is a claim about how your product behaves; the product is ground truth, so keep them matched  ✅
- **D.** Documentation should be regenerated fresh by AI for every release, since regeneration replaces any need to audit it

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106173851_
