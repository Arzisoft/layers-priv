---
course: "The Vault"
module: "Module 2: Personal Data: What Counts and Why It Matters"
lesson: "Module 2: Personal Data: What Counts and Why It Matters — Exam"
type: "course_quiz"
post_id: 107139915
space_id: 24302166
source: "https://the-faction.mn.co/posts/107139915"
updated: "2026-09-10T19:51:17Z"
---

# Module 2: Personal Data: What Counts and Why It Matters — Exam

> Exam for **Module 2: Personal Data: What Counts and Why It Matters** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder claims their analytics dataset is not personal data because it contains no names, only device IDs and IP addresses. What does this module say?

- **A.** They are right if the IDs are numeric, since numbers are anonymous by nature and only text identifiers can create personal data
- **B.** They are right: without a name field, data cannot relate to a person and sits fully outside every privacy regime's working definition
- **C.** Device IDs and IP addresses relate to identifiable people, so the dataset is personal data; the definition reaches far beyond names  ✅
- **D.** The dataset's status depends on its size, since identifiability begins only when a dataset exceeds ten thousand distinct records

> **Answer:** C

### Q2. A builder trained on US terminology asks how PII relates to personal data. What does this module say?

- **A.** The two are identical terms from different regions, so builders can use whichever word their client prefers with no consequence
- **B.** PII is the narrower US concept centered on identifiers like name and SSN; personal data is broader, and building to the broad definition is safer  ✅
- **C.** PII is the broader concept and personal data the narrower one, so US-facing builds carry noticeably stricter classification duties than EU-facing ones
- **D.** PII refers only to paper records while personal data refers to digital ones, so the distinction matters mainly for archival projects

> **Answer:** B

### Q3. Which set matches the sensitive categories this module says trigger special handling?

- **A.** Favorite colors, preferred fonts, browser choice, and playlist history, since aesthetic preferences reveal the inner life most directly
- **B.** Health, biometric and genetic data, ethnicity, religion, political opinions, union membership, sexual orientation, plus criminal records and children's data  ✅
- **C.** Job title, employer, work email, and office location, since professional data is the category regulators treat with the most suspicion
- **D.** Purchase amounts, cart contents, browsing times, and loyalty points, since commercial behavior is the specially protected category

> **Answer:** B

### Q4. A builder asks the difference between an identifier and a quasi-identifier. Which pairing matches this module?

- **A.** Identifiers are stored in databases while quasi-identifiers exist only in the logs, so the difference is where each type of field lives
- **B.** Identifiers are numeric values and quasi-identifiers are text values, so field type in the schema determines the classification automatically
- **C.** Identifiers are collected with consent and quasi-identifiers without, so the consent flow determines which category a field lands in
- **D.** An identifier points at a person on its own, like an email; a quasi-identifier does not alone, like zip code or birth date, but combines toward identification  ✅

> **Answer:** D

### Q5. This module cites a classic finding about zip code, birth date, and gender. What is the point of that finding?

- **A.** Those three fields are legally exempt from privacy rules, which is why templates include them as free space on every signup form
- **B.** Those three fields are the minimum every form must collect, since identity verification depends on having at least three data points
- **C.** A large share of a population can be uniquely identified from just those three combined, which is why quasi-identifiers are personal data in waiting  ✅
- **D.** Populations cannot be identified from fewer than ten fields, which sets the safe threshold for building datasets without concern

> **Answer:** C

### Q6. A vendor offers a 'fully anonymized' dataset where names are replaced by codes, and the vendor holds the key file. How does this module classify it?

- **A.** Pseudonymized, which is useful protection but still personal data under the law's eyes, because a key exists that can reconnect codes to people  ✅
- **B.** Anonymous, since the codes contain no personal information and datasets are always judged by their visible contents rather than by any key files
- **C.** Non-personal, since replacing names with codes is the legal definition of anonymization in every regime this course surveys
- **D.** Corporate data, since once a vendor processes a dataset it stops relating to individuals and relates only to the business entity

> **Answer:** A

### Q7. A builder classifies the product's forms carefully but never looks at the logging pipeline. What does this module warn?

- **A.** Logs and analytics are where personal data hides: IPs and user IDs quietly stored forever while the product was classified carefully  ✅
- **B.** Logging is safe by default, since modern frameworks strip all personal data from logs automatically before anything ever reaches storage
- **C.** Logs matter only for public companies, since log retention obligations attach at the point of a stock exchange listing
- **D.** Logs are legally exempt, since operational records fall outside privacy regimes as long as they exist for debugging purposes

> **Answer:** A

### Q8. This module gives a rule for classification uncertainty. What is it?

- **A.** When in doubt, delete the field from the classification table, since any unresolvable ambiguity means the field should not be tracked at all
- **B.** When in doubt, tag up, not down: the cost of over-protection is small and the cost of under-protection is the whole point of the course  ✅
- **C.** When in doubt, tag down, since over-classification creates unnecessary process and most ambiguous fields turn out to be harmless
- **D.** When in doubt, average the team's votes, since classification is subjective and group consensus is the only defensible standard

> **Answer:** B

### Q9. A client's app has an open 'notes' box on every profile. How does this module say to classify it?

- **A.** Non-personal, since the field is empty at creation and classification happens at schema time rather than at usage time
- **B.** As public data, since anything a user types voluntarily is published information carrying no protection obligations
- **C.** As personal data and sensitive-capable, since free-text fields will eventually contain health details, family situations, and worse  ✅
- **D.** As metadata, since user-authored content belongs to the user and therefore falls outside the operator's classification duties entirely

> **Answer:** C

### Q10. The module's fitness app example flags the leaderboard feature. Why?

- **A.** Leaderboards are performance features that slow the app, and the flag was an engineering concern rather than a privacy one
- **B.** Leaderboards require real names by law, and the client's plan to use display names violated the identification requirement
- **C.** Leaderboards are gambling mechanics in most regimes, and ranking users by activity requires a gaming license to operate
- **D.** A leaderboard is personal data made public, which needs consent thinking rather than silent display of users' activity  ✅

> **Answer:** D

### Q11. In the same example, how was the 'how do you feel today' note handled after classification?

- **A.** It was removed entirely, since free-text emotional content can never be collected lawfully by a consumer fitness product
- **B.** It became optional with clear notice and was flagged as sensitive-capable free text, removing a landmine without killing the feature  ✅
- **C.** It became a required field, since consistent collection across all users is precisely what makes sensitive data defensible at any scale
- **D.** It was moved to the leaderboard, since public display converts sensitive entries into published content with fewer duties

> **Answer:** B

### Q12. A builder asks where the classification exercise starts. What does this module say to list?

- **A.** Only fields visible in the interface, since backend-only data cannot relate to people the way displayed data does
- **B.** Only the fields marked required, since optional fields are user choices that fall entirely outside the operator's classification duty
- **C.** Every field the build collects or stores: forms, logs, analytics, uploads, and third-party imports, since hiding places count  ✅
- **D.** Only fields added this quarter, since classification is a forward-looking exercise that never revisits existing schemas

> **Answer:** C

### Q13. Per this module, what question decides whether a set of individually innocent fields is personal data?

- **A.** Whether these fields together, or joined with plausible outside data, could single someone out, since combination creates identifiability  ✅
- **B.** Whether any field is a string type, since text fields carry identification risk that numeric and boolean fields cannot
- **C.** Whether the fields share a table, since colocation in one schema is what converts separate fields into a personal record
- **D.** Whether users typed the fields themselves, since machine-generated values cannot combine into identification by definition

> **Answer:** A

### Q14. A build touches health-adjacent data. Beyond stricter tagging, what does this module say follows automatically?

- **A.** A mandatory rewrite in a compiled language, since interpreted languages are prohibited for sensitive-category processing
- **B.** Public disclosure of the schema, since sensitive-category processing requires publishing data structures for scrutiny
- **C.** The care level rises and a legal touchpoint becomes likely, since special categories carry stricter rules and often explicit consent  ✅
- **D.** Nothing until launch, since sensitive classification is a labeling exercise with no real downstream consequences before shipping anything

> **Answer:** C

### Q15. What does this module say about who the classification table serves later in the course?

- **A.** Only the lawyer, since classification is a legal artifact with no role in the technical build after it is filed
- **B.** Only the exam, since classification is a learning exercise this course uses to teach definitions rather than a project artifact
- **C.** Only marketing, since knowing the data categories mainly helps write accurate promotional claims about the product
- **D.** Consent design, minimization, and rights handling all consume it, since the table feeds every later privacy capability  ✅

> **Answer:** D

### Q16. A builder wants the AI's help classifying a build. Which instruction matches this module's directing pattern?

- **A.** Guess which fields a regulator would care most about, since enforcement priorities matter more than systematic classification
- **B.** Confirm this build has no personal data so we can skip the privacy work, since a clean bill from the AI settles classification
- **C.** Classify every field in this form and schema as identifier, quasi-identifier, sensitive, or non-personal, as a table with a one-line reason per field  ✅
- **D.** Classify only the fields you consider risky, since the judgment of the AI about risk should filter the table before the builder sees it

> **Answer:** C

### Q17. A builder is tempted to mark a doubtful field 'probably fine' to avoid extra work. What does this module say this leads to?

- **A.** Sensitive data ending up in a spreadsheet on someone's laptop, since downgraded classifications are how protection quietly disappears  ✅
- **B.** Nothing measurable, since classification tables are internal documents whose accuracy has no effect on real data handling
- **C.** Regulator praise for pragmatism, since the enforcement bodies actually penalize over-classification more often than under-classification
- **D.** Efficiency gains that compound, since most doubtful fields are harmless and systematic downgrading is a rational time saver

> **Answer:** A

### Q18. A product may attract users under the local age threshold. What does this module say enters the picture?

- **A.** A simple checkbox asking users to confirm adulthood, which fully discharges every obligation toward younger users
- **B.** A discount obligation, since regimes require reduced pricing for minors using data-collecting products
- **C.** Nothing until a child actually signs up, since children's data rules attach to accounts rather than to product design
- **D.** Children's data rules, and that is a lawyer conversation, since minors' data sits in the raised-care territory  ✅

> **Answer:** D

### Q19. Which working definition of personal data does this module tell builders to adopt as their default worldwide?

- **A.** Any information relating to an identified or identifiable person, directly or indirectly, which is the GDPR-style definition  ✅
- **B.** Any information stored longer than thirty days, since duration of storage is the thing that converts ordinary data into personal data
- **C.** Any information a company considers commercially valuable, since value is what attracts both attackers and regulators
- **D.** Any information a person has formally registered with a government, since official records are what privacy law protects

> **Answer:** A

### Q20. Why does this module direct the AI to read the actual database schema when classifying, rather than describing the product from memory?

- **A.** Schemas are shorter than product descriptions, so schema-based classification saves tokens without changing the result
- **B.** Schema reading is a compliance requirement, since regulators explicitly mandate that classification cite table names in its output
- **C.** Product descriptions are confidential, so schemas are the only artifact that can be legally shared with an AI system
- **D.** The schema is the classification's source of truth, and classifying from memory of the product misses fields that actually exist  ✅

> **Answer:** D

### Q21. What does this module say about analytics tools like session replay and error tracking?

- **A.** They are exempt from classification, since third-party tools carry their own compliance and inherit none from your build
- **B.** They collect personal data by default, so builders check what theirs capture and whether IP handling can be limited  ✅
- **C.** They collect only aggregate statistics, so no individual-level data ever reaches them from a standard installation
- **D.** They must be removed from every privacy-conscious build, since no analytics tool can operate on classified data lawfully

> **Answer:** B

### Q22. A dataset holds user IDs, timestamps, and precise location traces. A builder argues location is not personal since it describes places, not people. What does this module imply?

- **A.** The builder is right if traces update hourly or less, since identification requires continuous rather than sampled location
- **B.** Location traces tied to a user relate to an identifiable person and are personal data; where someone goes is data about them  ✅
- **C.** The builder is right: geographic coordinates are facts about the earth, and facts about the earth cannot relate to individuals
- **D.** The dataset is personal only if users opted into GPS, since permission status determines classification rather than content

> **Answer:** B

### Q23. How does this module describe the relationship between classification and the rest of a project's timeline?

- **A.** It is a recorded, ongoing habit: the table joins project documentation and gets re-checked as new fields join the build  ✅
- **B.** Classification precedes design entirely, since no wireframe may be drawn until every future field is classified
- **C.** Classification is optional for internal tools, since the exercise exists purely to satisfy consumer-facing disclosure rules
- **D.** Classification happens once at launch and never again, since shipping freezes the schema and the table with it

> **Answer:** A

### Q24. A client insists their aggregated dashboard 'contains no personal data.' Which check does this module suggest before agreeing?

- **A.** Whether small groups in the aggregation could combine with other data to single someone out, since aggregation with tiny cells re-identifies  ✅
- **B.** Whether the dashboard loads quickly, since performance characteristics are the one practical test of whether the data was ever truly aggregated
- **C.** Whether the client's competitors publish similar dashboards, since industry practice determines the classification of aggregates
- **D.** Whether the dashboard uses charts rather than tables, since visual presentation is what separates aggregate from individual data

> **Answer:** A

### Q25. Looking across this whole module, what is the governing principle of personal data classification?

- **A.** Classify to minimize obligations: the goal of the exercise is finding defensible reasons to place fields outside the personal data definition
- **B.** Classify by intuition at delivery time: experienced builders recognize personal data on sight, and tables merely record what instinct already knew
- **C.** Classification is a formality: since nearly everything is personal data anyway, the table exists for auditors rather than for any build decision
- **D.** Treat identifiability as the test and classify field by field, up when in doubt: personal data is anything relating to an identifiable person, alone or in combination  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/107139915_
