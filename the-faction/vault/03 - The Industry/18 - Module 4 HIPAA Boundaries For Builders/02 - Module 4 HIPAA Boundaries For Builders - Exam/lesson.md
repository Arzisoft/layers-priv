---
course: "The Industry"
module: "Module 4: HIPAA Boundaries For Builders"
lesson: "Module 4: HIPAA Boundaries For Builders — Exam"
type: "course_quiz"
post_id: 105096610
space_id: 24251863
source: "https://the-faction.mn.co/posts/105096610"
updated: "2026-08-10T18:15:43Z"
---

# Module 4: HIPAA Boundaries For Builders — Exam

> Exam for **Module 4: HIPAA Boundaries For Builders** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A dermatology practice asks you to build a photo intake tool. One file contains a patient's name, a phone number, and a note reading 'biopsy scheduled.' The office manager asks whether this file is PHI. What do you tell her?

- **A.** Yes, identifiers are combined with health context here, so the whole file is PHI and must be handled inside HIPAA safeguards.  ✅
- **B.** No, a scheduling note is administrative data, so PHI rules only apply once actual lab results or diagnoses are attached to it.
- **C.** Only the biopsy note is PHI, so the name and phone number can be stored in any convenient system without safeguards.
- **D.** It becomes PHI only if the practice retains it for more than thirty days, so short-term working files are exempt from the rules.

> **Answer:** A

### Q2. You are exporting a report from an oncology clinic's scheduler for a workflow test. One column holds appointment dates only. A colleague insists any data from a clinic is automatically PHI. What is the accurate boundary?

- **A.** All data generated inside a clinic is PHI regardless of its content, so even fully anonymous date columns require full HIPAA handling.
- **B.** Dates alone are not PHI, but paired with names or other identifiers at this clinic, the combination reveals who has a condition.  ✅
- **C.** Appointment dates are always PHI on their own because they describe care delivery, even with every identifier stripped away.
- **D.** The data is only PHI if it leaves the clinic's building, so anything used strictly for internal testing sits outside HIPAA.

> **Answer:** B

### Q3. You operate an appointment reminder tool for a four-provider family medicine group. Patient names and visit times flow through your server nightly. Where do you sit under HIPAA?

- **A.** You are a covered entity because your system touches patient records, which puts you in exactly the same category as the practice itself.
- **B.** You are a business associate because your tool receives and transmits PHI on the practice's behalf, so HIPAA reaches you directly.  ✅
- **C.** You are a neutral technology vendor with no HIPAA status, since only licensed clinical staff can carry obligations under the law.
- **D.** You are a subcontractor of the patients themselves, so your obligations come from individual consent forms rather than from HIPAA.

> **Answer:** B

### Q4. A builder friend tells you he skips HIPAA paperwork because he is 'just the tech person' and never looks at the patient data his intake tool processes. What is wrong with his reasoning?

- **A.** Building and operating a tool that handles PHI makes him a business associate with direct obligations, whether or not he views data.  ✅
- **B.** He is safe as long as the data is encrypted at rest, because encryption removes information from the definition of PHI entirely.
- **C.** He is actually right, since HIPAA obligations attach only to people who personally open and read patient records during their work.
- **D.** His exposure depends on his contract title, so relabeling himself as a consultant rather than a vendor would resolve the issue.

> **Answer:** A

### Q5. An orthopedics practice wants your referral tracker live by Monday. The BAA is drafted but unsigned, and the office manager says to launch now and sign next week. What is the correct call?

- **A.** Launch on schedule, since a BAA signed within thirty days retroactively covers all the data that moved during the gap period.
- **B.** Launch with a verbal agreement documented by email, which functions as a valid BAA until the formal signature gets collected.
- **C.** Launch but keep the data volume low, because HIPAA obligations only attach once a system handles a substantial number of records.
- **D.** Hold the launch until the BAA is signed, because the agreement must exist before any PHI flows through a system you operate.  ✅

> **Answer:** D

### Q6. You discover your intake tool for a pediatrics group has been live for two weeks with no BAA in place. The practice signs one today. What is the status of the data that already flowed?

- **A.** It is covered automatically, because a signed BAA applies to the entire engagement dating back to the original project start.
- **B.** It is covered as long as no breach occurred during the gap, since HIPAA only penalizes disclosures that caused actual harm.
- **C.** The new BAA does not cover it, since agreements are not retroactive, so the exposure must be documented and escalated now.  ✅
- **D.** It becomes covered after a sixty-day cure period, which HIPAA grants vendors who sign agreements in good faith after launch.

> **Answer:** C

### Q7. Your patient recall tool for an OB/GYN practice stores data on a cloud host you chose. You hold a signed BAA with the practice, but the host has signed nothing with you. What is missing?

- **A.** Nothing is missing, because your BAA with the practice automatically extends its coverage to infrastructure vendors you select.
- **B.** A BAA between you and the host, because the subcontractor chain extends downward to every service touching PHI on your behalf.  ✅
- **C.** A BAA between the host and the practice directly, since agreements must always connect back to the covered entity itself.
- **D.** A security certification from the host, which substitutes for a BAA when the vendor is a major cloud infrastructure provider.

> **Answer:** B

### Q8. You prototyped an urgent care intake form on a form builder's free plan. It works well, and the client wants to go live this week. What must you check before real patient data flows?

- **A.** Whether the service offers a BAA at all, since free tiers rarely include one, which usually means moving to a covered paid plan.  ✅
- **B.** Whether the free plan's uptime guarantees are strong enough for clinical use, since availability is the core HIPAA requirement.
- **C.** Whether the form builder is popular with other medical practices, since widespread healthcare adoption establishes compliance.
- **D.** Whether the practice's own HIPAA policies mention the tool by name, since client-side documentation is what covers a vendor.

> **Answer:** A

### Q9. A multi-provider dermatology group asks you to add text reminders that include appointment type. You are comparing messaging services. Which choice keeps the build inside the fence?

- **A.** Any major consumer texting platform, since SMS carriers are common conduits and are therefore exempt from HIPAA obligations.
- **B.** The cheapest service available, with reminder text worded vaguely enough that patients can guess the appointment details.
- **C.** A messaging service that signs a BAA with you, on a plan tier the BAA covers, before any reminder containing PHI is sent.  ✅
- **D.** Whichever service the practice already uses for staff chat, since internal adoption means it has been vetted.

> **Answer:** C

### Q10. A family medicine client wants AI-generated visit summaries produced from real patient notes. Before patient data touches any AI service, what must be true?

- **A.** The AI service is widely used in healthcare and the practice signs an internal memo accepting responsibility for any exposure.
- **B.** The prompts avoid mentioning HIPAA explicitly, since regulatory exposure attaches to stated intent rather than the data itself.
- **C.** The output is reviewed by a clinician afterward, since human review of results is what brings AI processing into compliance.
- **D.** The AI service is under a BAA and configured so patient data is not used for training, with both conditions met before launch.  ✅

> **Answer:** D

### Q11. A practice manager at a pediatrics office pastes a patient's name and symptom history into a free consumer AI chat tool to draft a reply. She asks you if that was fine. What do you tell her?

- **A.** It was fine because the chat happened in a private session, and data typed into a login-protected account is not a disclosure.
- **B.** It was fine since drafting correspondence is a routine office task, which HIPAA exempts from all of its disclosure rules entirely.
- **C.** That was a disclosure to a non-covered service, and future drafts need de-identified text or an AI tool operating under a BAA.  ✅
- **D.** It is only a problem if the AI company confirms it trained on the message, so she should wait before treating it as an issue.

> **Answer:** C

### Q12. You are directing AI to design an intake form for a physical therapy clinic. The client's draft asks every visitor for full medical history, employer details, and a social security number. What principle should reshape the form?

- **A.** Maximum capture, gather every field now so the practice never has to ask its patients for additional information later on.
- **B.** Minimum necessary, collect only the fields this workflow actually requires and cut everything the job does not truly need.  ✅
- **C.** Data symmetry, mirror whatever fields the practice's EHR is able to store so the two systems always match record for record.
- **D.** Progressive disclosure, collect everything up front but reveal sensitive fields to staff across multiple visits.

> **Answer:** B

### Q13. Your after-hours message router for an urgent care clinic moves patient callback details from the answering service to on-call staff. What does the transmission path require?

- **A.** Encryption in transit through BAA-covered services, so PHI never moves over unprotected channels or non-covered tools.  ✅
- **B.** Speed above everything else, since urgent care messages are exempt from transmission safeguards when patient safety is invoked.
- **C.** Plain email to the on-call phone, since messages that will be deleted after reading fall outside HIPAA's transmission rules.
- **D.** A password on the final document only, since HIPAA regulates stored data and leaves data in motion to carrier policies.

> **Answer:** A

### Q14. You are deciding where completed intake forms for a three-provider family practice should live. Which architecture most shrinks your exposure as the builder?

- **A.** Forms save to your own database first so you can run quality checks, then sync to the practice's system nightly.
- **B.** Forms are emailed to you personally for manual review, since direct human oversight is the strongest safeguard available.
- **C.** Forms land directly in the practice's PMS, so your system routes data without keeping its own store of patient records.  ✅
- **D.** Forms are duplicated across your server and the PMS, since holding redundant copies protects the practice from data loss.

> **Answer:** C

### Q15. Your reporting dashboard for an orthopedics group needs to show which patients have unfinished paperwork. How should the dashboard handle patient records?

- **A.** Cache full patient records locally so the dashboard stays fast, refreshing the copies from the source system every hour.
- **B.** Export a weekly spreadsheet of patient details to your drive, since periodic snapshots are simpler to audit than live links.
- **C.** Hold record references or IDs that point into the practice's system, rather than storing copies of patient details itself.  ✅
- **D.** Store patient names but not their conditions, since a list of names on its own can never constitute PHI in any circumstance.

> **Answer:** C

### Q16. A dermatology client wants trend reports on visit volume by condition type for planning. Patient identity is irrelevant to the reports. How do you direct AI to build the data pipeline?

- **A.** Include identifiers but restrict the audience, since limiting readership makes identified data equivalent to de-identified.
- **B.** De-identify at the source, so the reporting layer works with stripped data and identifiers never enter the pipeline at all.  ✅
- **C.** Keep identifiers in a hidden column, since data that is not displayed on screen does not count as being held by the system.
- **D.** Replace names with initials only, since initials are not listed as identifiers and fully satisfy the de-identification standard.

> **Answer:** B

### Q17. A multi-provider OB/GYN group asks what your patient documents portal does when someone opens a record. What capability should your design include, and why?

- **A.** Automatic deletion of records after each viewing, since removing data immediately is the strongest form of access control.
- **B.** A shared team login for simplicity, since fewer credentials mean a smaller attack surface for the practice to manage daily.
- **C.** Open access for all practice staff, since HIPAA treats everyone inside a covered entity as equally entitled to records.
- **D.** Audit logging of who accessed what and when, so the practice can review access history and investigate anything irregular.  ✅

> **Answer:** D

### Q18. An office manager at an urgent care client calls you: a staff laptop with access to your scheduling tool was left in a taxi last night. What is your move?

- **A.** Reset the laptop's password remotely and consider it closed, since credential changes cure any potential data exposure.
- **B.** Stop, document what is known, and get the practice's counsel or compliance contact involved, since this may be a breach.  ✅
- **C.** Wait two weeks to see whether the laptop is returned, since breach obligations only begin once the loss becomes permanent.
- **D.** Quietly rebuild the affected accounts and say nothing, since raising alarms would create liability that silence avoids.

> **Answer:** B

### Q19. A pediatrics client is behind schedule and asks you to skip encryption setup and launch the patient portal now, promising to accept the risk in writing. How do you respond?

- **A.** Decline and escalate, since a client's willingness to accept risk does not remove your own obligations as a business associate.  ✅
- **B.** Agree once the risk acceptance is signed, since documented client instructions transfer HIPAA liability over to the practice.
- **C.** Agree for thirty days at most, since temporary launches under deadline pressure fall within HIPAA's good faith provisions.
- **D.** Agree but limit the portal to adult caregivers, since the safeguard rules apply only to records viewed by minors directly.

> **Answer:** A

### Q20. A dermatology practice asks you to pull patient emails from the intake system so they can promote a new cosmetic service line. What is the right response?

- **A.** Fulfill it, since patients provided the emails to the practice and internal reuse is always permitted under HIPAA's rules.
- **B.** Fulfill it but strip the last names first, since partial identifiers make a marketing list automatically compliant.
- **C.** Fulfill it only for patients seen within the last year, since recency of care creates an implied consent to marketing.
- **D.** Pause and route the request to counsel or a compliance professional, since marketing uses of patient data are not your call.  ✅

> **Answer:** D

### Q21. You receive a subpoena demanding records from a system you run for a family medicine group. The attached letter pressures you to respond within days. What do you do?

- **A.** Stop and involve counsel before releasing anything, since legal demands for patient records are an escalation trigger, not a task.  ✅
- **B.** Comply immediately with a full export, since a subpoena overrides HIPAA and any delay would expose you to contempt charges.
- **C.** Send the records directly to the requesting attorney with names redacted, which satisfies both the subpoena and HIPAA at once.
- **D.** Ignore it entirely, since subpoenas can only be served on the practice itself and vendor systems fall outside legal process.

> **Answer:** A

### Q22. You built a website chatbot for a chiropractic office to answer general questions, but visitors have started typing in symptoms and appointment requests. You are unsure whether you are now a business associate. What is the professional move?

- **A.** Treat the ambiguity itself as an escalation trigger, get a qualified opinion, and minimize PHI handling in the meantime.  ✅
- **B.** Assume you are not one until the practice tells you otherwise, since all status determinations belong to the covered entity.
- **C.** Assume you are safe because the chatbot was not designed for PHI, since intent at build time controls your legal status.
- **D.** Delete the chat logs weekly and continue as before, since short retention windows keep a vendor below HIPAA's threshold.

> **Answer:** A

### Q23. During a kickoff call, a practice administrator asks you to explain who counts as a covered entity under HIPAA versus a business associate like you. Which answer is accurate?

- **A.** Covered entities are any companies with access to health data, including every software vendor in the practice's full stack.
- **B.** Covered entities are only hospitals and large health systems, so independent practices fall outside HIPAA's direct reach.
- **C.** Covered entities are government health agencies alone, with private providers bound only through their own state privacy laws.
- **D.** Covered entities are providers, health plans, and clearinghouses; business associates are vendors handling PHI for them.  ✅

> **Answer:** D

### Q24. A client's office manager at an orthopedics group asks you a detailed question about breach notification timelines. You have a rough memory of the answer. What is the right way to respond?

- **A.** Answer from memory confidently, since projecting certainty is what maintains a builder's credibility with practice staff.
- **B.** Give a conservative guess and double every timeline you recall, since overestimating deadlines is always the safe direction.
- **C.** Point her to hhs.gov guidance and her compliance resources, since rules questions get cited sources, not your recollection.  ✅
- **D.** Tell her that breach timelines are negotiable with regulators, so exact numbers matter less than showing good faith effort.

> **Answer:** C

### Q25. You are onboarding a new builder onto your healthcare projects and want to leave them with the single governing principle for HIPAA boundaries. Which statement captures it?

- **A.** Master the full regulation yourself, since a builder who can answer every compliance question never needs outside counsel.
- **B.** Collect data generously and secure it heavily, since strong encryption makes the quantity of PHI you hold irrelevant.
- **C.** Move fast and resolve gray areas with your own best judgment, since practices hire builders for speed rather than caution.
- **D.** Know where the fence line sits and stop at it; when in doubt, minimize the PHI you hold and escalate rather than improvise.  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/105096610_
