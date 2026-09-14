---
course: "The Vault"
module: "Module 1 — The Regulatory Landscape Map"
lesson: "Module 1: The Regulatory Landscape Map — Exam"
type: "course_quiz"
post_id: 106172781
space_id: 24302166
source: "https://the-faction.mn.co/posts/106172781"
updated: "2026-08-27T20:10:51Z"
---

# Module 1: The Regulatory Landscape Map — Exam

> Exam for **Module 1 — The Regulatory Landscape Map** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder ships a booking app for a dental practice that stores patient names and appointment reasons in its fields. Which regulatory framework is most likely triggered?

- **A.** HIPAA, because patient health information is flowing through the build even though the builder is not a provider  ✅
- **B.** GDPR, because appointment records count as personal data and any app storing names falls under EU privacy rules by default
- **C.** PCI DSS, because medical practices process insurance payments and that pulls every connected tool into scope
- **D.** FERPA, because appointment reasons are confidential records protected the same way as student education files

> **Answer:** A

### Q2. A US-based SaaS with no EU office starts getting signups from Germany and France. The builder assumes EU law cannot reach him. What is the reality?

- **A.** He is right until he opens an EU entity, because GDPR jurisdiction follows where a company is legally registered
- **B.** GDPR can apply based on where users live, so EU signups pull the build into scope regardless of his location  ✅
- **C.** GDPR only applies once a build passes a threshold of EU revenue, so early signups are exempt from its demands
- **D.** EU law applies only if he markets in EU languages, so an English-only product stays outside GDPR's reach

> **Answer:** B

### Q3. A vibecoder builds a custom checkout form that collects card numbers directly on his own server instead of using a hosted provider. What happened to his compliance picture?

- **A.** Nothing changed, because PCI DSS obligations always sit with the card networks and the bank issuing the cards
- **B.** He owes PCI attention only if he stores cards after the sale, since collecting them in transit is out of scope entirely
- **C.** He pulled full PCI DSS scope onto his own stack, a burden a hosted provider would have largely carried for him  ✅
- **D.** He triggered GLBA instead, because handling card numbers makes his product a federal financial institution

> **Answer:** C

### Q4. A builder launches a quiz game aimed at elementary schoolers that collects email addresses and usernames from players. Which framework should be on his map first?

- **A.** FERPA, because any product used by school-aged children is treated as handling protected education records
- **B.** CAN-SPAM, because collecting emails from any audience makes commercial messaging rules the primary concern
- **C.** GDPR, because children's data is a special category that applies worldwide no matter where players live
- **D.** COPPA, because collecting personal information from kids under 13 triggers strict parental consent rules  ✅

> **Answer:** D

### Q5. A client asks a builder point blank: 'Is my new patient portal compliant?' What is the right move inside the builder's scope?

- **A.** Say yes if the survey came back clean, because a documented six-category sweep is enough to certify a build
- **B.** Say no by default, because builders should never express any view at all about regulation to a paying client ever
- **C.** Run an AI audit prompt and forward the output as the compliance determination the client can rely upon
- **D.** Present the regulatory map, flag the exposures found, and recommend licensed counsel for the compliance call  ✅

> **Answer:** D

### Q6. A builder adds automated appointment reminder texts to a salon booking app. Which law governs those messages?

- **A.** CAN-SPAM, which covers every automated message a product sends, whether it arrives by email or by text
- **B.** The FTC Act, because reminder texts are a form of advertising that falls under consumer protection rules
- **C.** TCPA, the communications law that governs automated text messages a product sends to its users' phones  ✅
- **D.** No law applies, because transactional reminders that users signed up for sit outside regulated messaging

> **Answer:** C

### Q7. A builder wires up an automated marketing email sequence for a course launch. Which category and law just went live on the map?

- **A.** Financial regulations via GLBA, because selling a paid course makes the email list a financial customer base
- **B.** Data privacy via CCPA, which is the primary law controlling what any marketing email is allowed to contain
- **C.** Industry rules via FERPA, because course buyers become students and their records gain federal protection
- **D.** Communications law via CAN-SPAM, which governs the commercial emails the product now sends automatically  ✅

> **Answer:** D

### Q8. A builder creates a tutoring platform for a school district that stores student names, grades, and progress notes. Which framework do the client and data pull into play?

- **A.** COPPA alone, because the platform serves children and that is the only framework covering minors' information
- **B.** HIPAA, because progress notes about a child's learning are treated as health records under federal privacy law
- **C.** GDPR, because education data is a special category that applies to all student records held anywhere globally
- **D.** FERPA, because student education records flowing through the build trigger the industry-specific rules  ✅

> **Answer:** D

### Q9. A builder picks a HIPAA-eligible hosting provider for a therapy practice app and tells the client everything is handled. What did he get wrong?

- **A.** Nothing, because choosing an eligible host transfers the compliance obligations onto the infrastructure vendor
- **B.** Vendor compliance does not cover the build; configuration, agreements like a BAA, and his own code still matter  ✅
- **C.** He should have used two eligible vendors, since redundancy is what regulators check in a HIPAA compliance audit today
- **D.** The host was the wrong layer, because HIPAA obligations apply only to the database and never the infrastructure

> **Answer:** B

### Q10. A builder's small business site gets a demand letter about screen reader failures. He thought accessibility rules only applied to big companies. What does the module say?

- **A.** He is right and the letter is a scam, since ADA lawsuits are only viable against companies above a size floor today
- **B.** Accessibility is best practice rather than law, so the letter carries no legal weight and can be ignored
- **C.** The ADA applies to websites and apps, WCAG is the practical standard, and suits against small sites are common  ✅
- **D.** Only government sites face accessibility law, so private builds sit outside the reach of demand letters

> **Answer:** C

### Q11. During a six-category sweep, a builder notes his app auto-renews subscriptions and makes cancellation hard to find. Which category lights up?

- **A.** Financial regulations, because recurring billing turns the product into a payments platform under federal rules
- **B.** Consumer protection, the FTC territory covering pricing, subscriptions, cancellations, and dark pattern design  ✅
- **C.** Communications law, because renewal charges arrive alongside the automated receipts the product emails out
- **D.** Data privacy, because storing an active payment relationship is a form of personal data under CCPA and GDPR

> **Answer:** B

### Q12. A builder wants to survey a new build's regulatory exposure fast, before writing any code. Which set matches the module's trigger question list?

- **A.** Who are the users, what data flows through, where do users live, does money move, and does it send messages  ✅
- **B.** What is the tech stack, who hosts it, what does it cost, how many users, and which AI model wrote the code
- **C.** Is it B2B or B2C, is it profitable, is it venture backed, is it open source, and does it have a privacy policy
- **D.** Which statutes apply, what are the penalties, which agency enforces, what case law exists, and who gets sued

> **Answer:** A

### Q13. Two builders add payments. One embeds Stripe Checkout; the other posts card numbers to his own API before forwarding them. How does PCI scope compare?

- **A.** It is identical, because both products charge cards and PCI DSS does not distinguish how numbers are captured
- **B.** The Stripe builder carries more scope, because outsourcing payment handling adds a vendor he must now audit
- **C.** Neither carries scope, because PCI DSS binds the card networks and the processors rather than app builders
- **D.** Hosted checkout keeps most burden with the provider; touching card data directly makes the burden his own  ✅

> **Answer:** D

### Q14. A vibecoder argues his weekend build is exempt from regulation because AI wrote every line and he never touched the code. What is the module's answer?

- **A.** He has a point, since liability for AI-generated code is unsettled and enforcement waits for clearer rules to arrive
- **B.** Regulations attach to what the software does, not who or what wrote it, so the exposure stays exactly the same  ✅
- **C.** He is exempt only if the AI vendor's terms accept liability, which shifts the compliance burden upstream
- **D.** The build is exempt until it earns revenue, because regulators treat unpaid projects as protected hobbies

> **Answer:** B

### Q15. A builder's new project involves storing therapy session notes. According to the escalation threshold, what is the next step?

- **A.** Bring in a licensed professional, because health data is one of the written triggers where awareness ends  ✅
- **B.** Run a deeper AI audit prompt, because a thorough enough survey substitutes for a professional review here
- **C.** Encrypt the notes and proceed, because strong technical controls satisfy the health data requirements fully
- **D.** Anonymize each client's name in the notes, which removes the data from regulated territory altogether

> **Answer:** A

### Q16. A builder skips compliance mapping because his app has 40 users and almost no revenue, reasoning nobody will notice. Which pitfall is this?

- **A.** Playing lawyer for clients, because deciding not to map is itself an unlicensed legal determination he made
- **B.** Paralysis in the wrong direction, because he is letting fear of regulators shape his product roadmap early
- **C.** Assuming small means invisible, when regulators and plaintiffs do not check revenue before taking action  ✅
- **D.** Vendor dependence, because a small stack means his providers' compliance postures cannot protect him at all

> **Answer:** C

### Q17. A builder's generic scheduling tool is adopted by a barbershop, then later by a dental office entering patient details. What changed legally?

- **A.** The client and the data pulled the trigger; the same tool now touches HIPAA because of who uses it and what flows in  ✅
- **B.** Nothing changed, because industry rules attach to what the builder intended the software to do at design time originally
- **C.** The dental office assumed all the exposure, because regulations bind only the customer who inputs the data
- **D.** The tool now needs FDA clearance, because software used inside any medical setting becomes a regulated device

> **Answer:** A

### Q18. A builder launches a budgeting tool that connects to users' bank accounts and stores transaction histories. Which industry framework belongs on the map?

- **A.** HIPAA, because financial stress data reveals sensitive personal wellbeing information about the app's users
- **B.** COPPA, because family budgeting tools are commonly used by households that include children under age 13
- **C.** GLBA, because handling consumer financial data pulls the build toward the financial privacy regulations  ✅
- **D.** FERPA, because financial literacy tools are educational products holding protected learner record data

> **Answer:** C

### Q19. A builder's first EU deletion request arrives and his app has no way to delete a user's data. What does the module say this moment reveals?

- **A.** He discovered GDPR after launch, and retrofitting deletion capability costs far more than designing it in  ✅
- **B.** A gap in customer service, since deletion requests are support tickets rather than regulatory obligations to handle
- **C.** An engineering edge case, because deletion rights only bind platforms above a defined EU user threshold
- **D.** A vendor problem, because deletion requests should be forwarded to the hosting provider storing the data

> **Answer:** A

### Q20. A builder runs the AI regulatory survey prompt on a new build and gets a clean, confident category table back. How should he treat that output?

- **A.** As a final answer, because a well-structured prompt produces a complete and reliable regulatory ruling every time
- **B.** As legally binding documentation he can attach to client contracts as proof the exposure was assessed
- **C.** As noise, because AI systems cannot meaningfully enumerate regulatory categories for a software build
- **D.** As a first draft of the map, where the AI supplies breadth and the builder still supplies the judgment  ✅

> **Answer:** D

### Q21. A builder debates whether to design consent flows now or bolt them on later if a regulator ever asks. What does the module teach about this choice?

- **A.** Retrofitting costs roughly ten times what designing for compliance costs, so map first and ship second  ✅
- **B.** Bolting on later is safer, because requirements change and early compliance work is usually wasted effort
- **C.** Either order works, because consent flows are a UI concern with no bearing on regulatory exposure at all
- **D.** Waiting is standard practice, because enforcement always begins with a warning that leaves time to build

> **Answer:** A

### Q22. A builder's simple newsletter signup page collects names and email addresses, nothing else. Does any regulatory category apply to something this small?

- **A.** No, because data privacy law only activates once a build stores sensitive categories like health or payments
- **B.** No, because names and emails are public-facing information that privacy frameworks explicitly carve out
- **C.** Yes, nearly every signup form touches data privacy, which governs collection, retention, and user rights  ✅
- **D.** Yes, but only communications law, since the sole risk of a newsletter is the sending of the emails later

> **Answer:** C

### Q23. After learning the six categories, a builder freezes and stops shipping, convinced every project needs a legal department first. What is the module's correction?

- **A.** Regulatory risk is managed, not eliminated; most builds need a handful of concrete actions, so keep shipping  ✅
- **B.** His instinct is right, because pausing all launches until counsel reviews each build is the safest posture overall
- **C.** He should ship only unregulated builds, and the sweep exists to find the categories a builder must avoid
- **D.** He should incorporate first, because a company structure absorbs the regulatory exposure a builder carries

> **Answer:** A

### Q24. A builder completes a six-category sweep for a client project. Which statement stays inside the builder's scope?

- **A.** 'This build is fully compliant,' since a completed sweep is the evidence a compliance declaration rests on
- **B.** 'This build touches health data and EU users; here are the flags to resolve with counsel before launch'  ✅
- **C.** 'You cannot be fined,' because a documented map is a recognized legal defense against regulatory penalties
- **D.** 'No regulations apply,' since the sweep found no certain exposure and maybes do not need to be flagged

> **Answer:** B

### Q25. Which statement best captures the governing principle of Module 1, The Regulatory Landscape Map?

- **A.** Regulation is a lawyer's domain, so the builder's job is to ship fast and route every question to counsel instead
- **B.** Map which regulations touch a build before shipping; awareness is builder scope, legal advice is counsel scope  ✅
- **C.** Compliance is achieved by choosing certified vendors, because their obligations flow through to the build
- **D.** Memorizing the major statutes lets a builder certify compliance and remove the need for outside review

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/106172781_
