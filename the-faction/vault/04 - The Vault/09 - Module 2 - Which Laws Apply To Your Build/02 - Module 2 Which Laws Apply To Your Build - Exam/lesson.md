---
course: "The Vault"
module: "Module 2 — Which Laws Apply To Your Build"
lesson: "Module 2: Which Laws Apply To Your Build — Exam"
type: "course_quiz"
post_id: 106173052
space_id: 24302166
source: "https://the-faction.mn.co/posts/106173052"
updated: "2026-08-27T20:10:51Z"
---

# Module 2: Which Laws Apply To Your Build — Exam

> Exam for **Module 2 — Which Laws Apply To Your Build** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A solo vibecoder in Ohio ships a SaaS tool and the first paid signup comes from Berlin. What does the geography pass say about this build?

- **A.** Nothing applies because the company is registered in the United States and keeps no physical presence anywhere in Europe
- **B.** GDPR only becomes relevant once the builder opens an EU office or hires a European data protection officer
- **C.** The builder can wait until they actively market in the EU before any European privacy rules enter the picture
- **D.** GDPR likely applies because the user is an EU resident, and privacy laws follow the data subject, not the builder  ✅

> **Answer:** D

### Q2. Your app quietly picks up signups from California residents. Which privacy trigger fires on the data pass?

- **A.** No state trigger fires because federal privacy law preempts California rules for online software products
- **B.** GDPR fires here because California formally adopted the European framework and enforces it for residents
- **C.** CCPA and its expansion CPRA fire because the build is collecting personal data from California residents  ✅
- **D.** A trigger fires only past a large revenue threshold, so small solo builders can safely ignore this pass

> **Answer:** C

### Q3. You are vibecoding a game app and analytics show a chunk of players are under 13. What does the data pass flag?

- **A.** COPPA fires because the build is collecting data from children under 13, which brings strict consent duties  ✅
- **B.** FERPA fires because anyone under 18 counts as a student and their app activity is an education record
- **C.** Nothing fires because the app is entertainment, and children's rules only reach schools and dedicated kids platforms
- **D.** Parental consent is a nice touch but stays optional until the app is marketed as a children's product

> **Answer:** A

### Q4. A client asks for a scheduling app for their dental office. Clean auth, happy client. What did the trigger tree probably catch that the builder missed?

- **A.** Nothing at all, because a calendar app only stores appointment times and those are never regulated data
- **B.** HIPAA applies only to the dentist as the covered entity involved, so the builder himself carries zero exposure
- **C.** A standard privacy policy template fully covers appointment data as long as the passwords are hashed and stored properly
- **D.** Appointment records tied to patients can be PHI, pulling HIPAA and a business associate agreement into play  ✅

> **Answer:** D

### Q5. Your checkout page touches raw card numbers before handing off to a processor. What does the industry pass say?

- **A.** The build sits in PCI DSS scope, and using a processor shrinks that scope but never deletes it entirely  ✅
- **B.** Stripe or any processor absorbs every payment duty, so the builder can skip the payments question
- **C.** Only banks and the card networks fall under PCI DSS, so an app builder is structurally outside its reach
- **D.** GLBA is the payments rule here, because any money movement counts as consumer financial services activity

> **Answer:** A

### Q6. You are building a budgeting tool that pulls in users' bank account and transaction data. Which industry trigger fires?

- **A.** PCI DSS, because anything involving money in an app automatically lands inside card security standards
- **B.** GLBA, because the build handles consumer financial data, which carries obligations beyond card rules  ✅
- **C.** No trigger, because users voluntarily connected their accounts and that consent removes regulatory duties
- **D.** Only GDPR, because privacy law is the single framework that governs personal data of every category

> **Answer:** B

### Q7. An edtech client wants a tutoring dashboard that stores grades, transcripts, and progress reports. What fires?

- **A.** FERPA, because the build touches student education records, a category with its own federal protections  ✅
- **B.** HIPAA, because tutoring notes about a student's academic progress count as protected health information
- **C.** Nothing, because the school owns the records and that ownership keeps the builder out of regulatory scope
- **D.** COPPA alone, because every regulation involving students collapses into the children's privacy rule

> **Answer:** A

### Q8. You run the tree on a new build and the data pass lights up GDPR right away. What does the module say to do next?

- **A.** Stop there, because the strictest regulation was found first and it covers whatever the others require
- **B.** Skip straight to legal review, because one confirmed trigger means the map is finished and ready for a professional
- **C.** Run all three passes anyway, because data, industry, and geography can each fire on the same build at once  ✅
- **D.** Run geography only if the product actively sells abroad, since domestic builds stay under a single law

> **Answer:** C

### Q9. A kids' tutoring app takes card payments from parents in California. How do the triggered regulations interact?

- **A.** The strictest regulation absorbs the rest, so satisfying COPPA automatically settles the other exposure
- **B.** PCI DSS wins out because payment risk outranks privacy risk whenever both appear in the same build
- **C.** They stack, so COPPA, CCPA/CPRA, and PCI DSS each add separate obligations that go on the map individually  ✅
- **D.** GDPR acts as the global umbrella here, and meeting it satisfies American state and sector rules too

> **Answer:** C

### Q10. You finish the three passes and hand the client your compliance map. What is the map allowed to conclude?

- **A.** That the build is fully compliant, since a completed map is exactly what regulators ask companies to produce
- **B.** That the client now holds legal advice in writing and can skip hiring a professional for the launch
- **C.** That any regulation not listed on the map is legally settled and can be ignored for future features
- **D.** That these regulations likely apply, why each one fires, and which items need professional review first  ✅

> **Answer:** D

### Q11. A vibecoder tells you Stripe handles payments, so PCI is not their problem. Per the module, what is the reality?

- **A.** They are right, because using a hosted payment processor deletes PCI obligations for everyone upstream
- **B.** They are right as long as the checkout page shows the processor's logo and links out to its legal terms
- **C.** PCI only matters when card numbers sit in your own database, so pass-through builds are fully exempt
- **D.** A processor shrinks PCI scope but does not delete it, so pages touching the payment flow keep obligations  ✅

> **Answer:** D

### Q12. Your app launches with open worldwide signups on day one. What does the geography pass conclude?

- **A.** Only the laws of the builder's home state apply until a regulator sends a formal notice of jurisdiction
- **B.** Launching worldwide by default triggers worldwide regulations by default, since laws follow the users  ✅
- **C.** Geography is settled by where the hosting servers sit, so a US data center keeps things domestic
- **D.** International rules attach only after revenue in a given country crosses a locally defined tax threshold

> **Answer:** B

### Q13. A builder skipped the trigger tree, shipped fast, and says their AI wrote the whole thing anyway. How do regulators see that?

- **A.** Regulators do not grade on effort or intentions, and saying my AI built it is not a recognized defense  ✅
- **B.** Good faith reliance on modern AI tooling is treated as a safe harbor in most current privacy frameworks
- **C.** Solo builders under a certain revenue floor are exempt, so enforcement only reaches funded companies
- **D.** Liability transfers over to the AI vendor whose model actually generated the offending product code

> **Answer:** A

### Q14. A campus app stores students' course grades and also notes from the student health clinic. How do the triggers split?

- **A.** FERPA fires on the education records and HIPAA can fire on the health data, so both go on the map  ✅
- **B.** One law covers everything on campus, because the campus setting merges all records into one bucket
- **C.** HIPAA covers the grades too, since anything touching a student's wellbeing counts as health information
- **D.** FERPA covers the clinic notes as well, because any record a school touches becomes an education record

> **Answer:** A

### Q15. Your AI runs the audit prompt and hands back a tidy list of regulations. What does the module say happens next?

- **A.** Ship it, because a structured AI audit is exactly the verification step the decision tree calls for
- **B.** Check the output against the Regulation-to-Trigger Table, because AI can miss a trigger or invent one  ✅
- **C.** Forward the list straight to the client as confirmed legal findings that are ready for their records
- **D.** Only double check the list if HIPAA shows up, since lower stakes regulations are safe to take on faith

> **Answer:** B

### Q16. The map marks HIPAA as likely for a client build. What does the Escalation Flag rule require before launch?

- **A.** Nothing extra at all, because marking a regulation as likely on the map already satisfies the escalation duty
- **B.** A professional review line item, because any high stakes regulation marked likely gets one before launch  ✅
- **C.** A self certification memo from the builder stating the app follows HIPAA best practices as understood
- **D.** Escalation only if the client is enterprise scale, since small clinics get much lighter expectations

> **Answer:** B

### Q17. Your LLC is registered as a software company, but your client is a dental office. Whose rules shape the build?

- **A.** Yours, because regulatory obligations attach to the business code of the entity writing the software
- **B.** Neither side's, because a contractor relationship insulates both parties from each other's exposure
- **C.** The client's, because a regulated industry's rules reach into your build until proven otherwise  ✅
- **D.** Whichever is lighter, because vendors may choose the friendlier of the two applicable frameworks

> **Answer:** C

### Q18. A builder heard CPRA replaced CCPA and wants to know what to put on the map for California users. What is accurate?

- **A.** CPRA is the EU's update to GDPR, so it belongs on the geography pass rather than on the data pass
- **B.** CCPA was fully repealed, so only builds from before 2020 still carry California privacy obligations
- **C.** CPRA applies only to registered data brokers, so an ordinary app maps to CCPA and nothing more
- **D.** CPRA is the expansion of CCPA, and California residents' data puts the combined regime on the map  ✅

> **Answer:** D

### Q19. Your general audience app never markets to kids, but signup data shows some users are 12. What is the COPPA reality?

- **A.** COPPA covers all minors under 18, so nearly every consumer app carries children's privacy duties anyway
- **B.** COPPA applies only to products deliberately designed and advertised for children, so intent decides it
- **C.** COPPA protects children under 13, so collecting data from those 12 year old users fires the trigger  ✅
- **D.** Parental consent is implied by the act of account creation, so no additional duties attach to the app

> **Answer:** C

### Q20. You are running the data pass and classifying the fields your build collects. What determines which privacy law fires?

- **A.** Who the data belongs to, since EU residents, Californians, children, students, and patients map to laws  ✅
- **B.** How much data is collected, since privacy statutes only activate above defined volume thresholds
- **C.** Whether the data is encrypted, since properly secured fields fall outside privacy law entirely
- **D.** Where the database physically lives, since data stored on US servers answers only to United States law

> **Answer:** A

### Q21. A client says the product is already GDPR compliant, so the compliance work is done. What does the module say?

- **A.** They are right, because GDPR is the strictest regime and satisfying it satisfies everything beneath it
- **B.** Regulations stack rather than replace each other, so GDPR work says nothing about HIPAA, COPPA, or PCI  ✅
- **C.** They are right only if the GDPR work was verified by counsel, since legal signoff transfers across regimes
- **D.** GDPR compliance covers US federal rules, though state level rules like CCPA still need a separate look

> **Answer:** B

### Q22. You are starting a compliance map for a new build. Per the Data Inventory Prompt, what is the first concrete step?

- **A.** Read the full text of every relevant statute so the map can quote exact sections instead of plain language triggers
- **B.** Book a lawyer before doing any mapping, since builders should never attempt trigger analysis on their own
- **C.** Direct your AI to enumerate every field the product collects or infers, then classify each against triggers  ✅
- **D.** Copy the compliance page of the closest competitor, since similar products share identical legal duties

> **Answer:** C

### Q23. A law firm hires you to build a document portal for active case files. What does the industry pass flag?

- **A.** Nothing, because legal documents become public record the moment they are part of a court proceeding
- **B.** PCI DSS, because law firms bill their clients and billing brings every vendor into card security scope
- **C.** FERPA, because case files about a person function like education records held by a formal institution
- **D.** Legal records carry privilege and retention rules, so the client's industry reaches into the build  ✅

> **Answer:** D

### Q24. A fintech friend says GLBA and PCI DSS are basically the same payments rule. How does the module separate them?

- **A.** PCI DSS attaches to card payment data while GLBA covers consumer financial data, as separate triggers  ✅
- **B.** GLBA formally replaced PCI DSS in the United States, so only one of the two ever belongs on a modern build map
- **C.** PCI DSS is the federal government statute and GLBA is the private card network standard mirroring it
- **D.** They are identical in scope and differ only in which agency a company reports its yearly audits to

> **Answer:** A

### Q25. What is the governing principle of Module 2, Which Laws Apply To Your Build?

- **A.** A builder who documents good faith effort earns safe harbor from most modern privacy enforcement actions
- **B.** Triggers from data, industry, and user geography decide what applies, and the map flags it for pro review  ✅
- **C.** The safest path is building for the strictest law, since satisfying it covers every lighter regime too
- **D.** Regulation mapping is a lawyer's job, so builders should ship first and route open questions to counsel

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/106173052_
