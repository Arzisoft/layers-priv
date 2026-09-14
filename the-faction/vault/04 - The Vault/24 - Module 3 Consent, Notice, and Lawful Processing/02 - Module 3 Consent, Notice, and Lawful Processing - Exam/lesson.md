---
course: "The Vault"
module: "Module 3: Consent, Notice, and Lawful Processing"
lesson: "Module 3: Consent, Notice, and Lawful Processing — Exam"
type: "course_quiz"
post_id: 107139919
space_id: 24302166
source: "https://the-faction.mn.co/posts/107139919"
updated: "2026-09-10T19:52:06Z"
---

# Module 3: Consent, Notice, and Lawful Processing — Exam

> Exam for **Module 3: Consent, Notice, and Lawful Processing** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder starting a new SaaS project plans to show a consent checkbox for every single data use, including processing needed to deliver the service. What does this module advise?

- **A.** Keep consent for everything, since a single mechanism is easier to maintain and regulators always prefer the strictest possible approach in a build
- **B.** Keep consent for everything, but hide the checkboxes for essential processing so users cannot withdraw the data uses the product depends on
- **C.** Map purposes to the six lawful bases instead; consent for everything creates fragile processing that dies on withdrawal and shows purposes were never mapped  ✅
- **D.** Drop consent entirely, since contract already covers any processing a company decides it needs once a user has created an account of any kind

> **Answer:** C

### Q2. A checkout flow needs the buyer's address to ship an order. The client asks whether to add a consent checkbox for this. Which basis does this module point to?

- **A.** Consent, since address data is personal and every field of personal data collected anywhere in a build must always carry its own dedicated checkbox
- **B.** Contract: the address is necessary to deliver what the user asked for, so no consent checkbox is needed for that specific processing at all  ✅
- **C.** Legitimate interests, since shipping is a business need and the balancing test lets the company skip asking the buyer about anything it does
- **D.** Vital interests, since undelivered orders can cause the kind of serious harm to customers that this rare basis was designed to cover

> **Answer:** B

### Q3. During review you find a signup form where the marketing checkbox is already ticked when the page loads. What does this module say about that design?

- **A.** The consent is invalid in opt-in regimes; pre-ticked boxes fail the unambiguous test and are instantly visible to anyone reviewing the build  ✅
- **B.** The consent is valid as long as the user can untick the box before submitting, since the opportunity to refuse is what the regulations require
- **C.** The consent is valid if the notice mentions the pre-ticked state, because informing users about a default converts it into an active choice
- **D.** The consent is invalid only if marketing emails are actually sent, since regulators judge outcomes and never the mechanics of the form itself

> **Answer:** A

### Q4. A regulator asks a client to prove a user consented to marketing. Which record does this module say the build should be able to produce?

- **A.** The current copy of the privacy notice, since the live version of the document is what governs every consent ever collected under any earlier one
- **B.** A screenshot of the signup form design, since the visual layout of the checkbox is the evidence regulators weigh most heavily in a dispute
- **C.** The user's most recent login timestamp, since continued use of the product is itself the strongest ongoing evidence of a valid consent
- **D.** A consent record linking the user, the purpose consented to, the timestamp, and the version of the notice they were shown at the time  ✅

> **Answer:** D

### Q5. A meditation app refuses to start any session until the user consents to marketing emails, though sessions work fine without them. What is the problem?

- **A.** The consent is not freely given: saying no breaks the product for no real reason, which invalidates the consent under this module's test  ✅
- **B.** There is no problem, since companies may set any conditions they like on access and users who dislike them are free to pick a competitor
- **C.** The problem is only cosmetic; moving the same demand to a settings page later in the flow would make the requirement fully compliant
- **D.** The consent fails only because it is collected at session start; the same gate placed at account creation would make it freely given

> **Answer:** A

### Q6. A client wants one long legal document as their privacy notice. You propose a different structure based on this module. What do you propose?

- **A.** A single dense document, but placed behind more prominent links, since the visibility of the file is what regulators mean by transparency
- **B.** A layered notice: a short plain-language summary up front, details behind it, honest about collection, sharing, retention, and rights  ✅
- **C.** No notice at all for processing under contract, since lawful bases other than consent remove the duty to tell users what is happening
- **D.** A notice written in formal legal terminology, since documents drafted for lawyers give the company the strongest position in a dispute

> **Answer:** B

### Q7. A builder ships the same marketing signup for EU and US audiences and asks how the two regimes treat it. Which summary matches this module?

- **A.** Both regions run opt-out models for marketing, so a visible unsubscribe link in every email satisfies the stricter of the two regimes at once
- **B.** Both regions run opt-in models, so the only difference a builder needs to handle is the language the checkbox and the notice are written in
- **C.** EU-style regimes generally require opt-in before marketing happens; much US practice runs opt-out, with laws like CCPA mandating specific opt-outs  ✅
- **D.** The regimes differ only in how they treat cookies, so email marketing can safely run under a single opt-out model across every region served

> **Answer:** C

### Q8. You audit a site whose cookie banner announces analytics cookies that already loaded before anyone clicked. What does this module require instead?

- **A.** The banner should list the scripts by vendor name, since disclosure of specific providers is what converts early loading into compliance
- **B.** The banner should load scripts but delete the collected data if the user rejects, since retroactive cleanup satisfies the opt-in standard
- **C.** The banner is fine, since displaying it at all demonstrates good faith and regulators only check whether users can clear cookies manually
- **D.** Non-essential scripts must stay blocked until the user consents; the banner gates the scripts rather than announcing what already fired  ✅

> **Answer:** D

### Q9. A user granted marketing consent in one click at signup. Withdrawing it now takes a support ticket and a waiting period. What does this module say?

- **A.** Withdrawal must be as easy as granting: a preference center or unsubscribe path that works in a click or two and actually stops the processing  ✅
- **B.** The asymmetry is acceptable because withdrawal is rarer than granting, and a support review step protects users from revoking consent accidentally
- **C.** The asymmetry is acceptable if the notice disclosed the process, since informed users have agreed in advance to the extra friction involved
- **D.** Withdrawal difficulty only matters for sensitive data categories, so a marketing consent can carry whatever process the company prefers to run

> **Answer:** A

### Q10. A client wants fraud checks on transactions without asking users first, and the builder must place this processing somewhere. Which treatment does this module suggest?

- **A.** Run the checks under consent anyway, since asking users to approve fraud screening is the only way any regulator will accept the processing
- **B.** Skip the analysis, since security processing is exempt from lawful basis requirements the moment a company labels it fraud prevention
- **C.** Treat it as a legitimate interests candidate: document the balancing reasoning and flag the judgment call for a lawyer to confirm  ✅
- **D.** Use the public task basis, since protecting commerce from fraud is a public good that private companies perform on behalf of the state

> **Answer:** C

### Q11. A signup flow makes users accept terms of service that include marketing consent buried in clause 14. What does this module call this pattern?

- **A.** A sensible efficiency, since one agreement covering everything reduces signup friction and users consistently prefer fewer checkboxes
- **B.** Bundled consent, invalid in opt-in regimes: separate purposes need separate choices, and consent cannot hide inside terms of service  ✅
- **C.** A valid pattern as long as clause 14 is written in plain language, since readability is the only test that a consent has to pass
- **D.** A gray area that regulators have not yet addressed, so builders may keep the pattern until specific enforcement says otherwise

> **Answer:** B

### Q12. You are starting the consent work for a new build. According to the sequence in this module, what is the first step?

- **A.** Design the cookie banner, since it is the most visible consent surface and every other decision inherits its look and wording
- **B.** Write the privacy notice, since the document must exist before anyone can decide what the product will be allowed to collect
- **C.** Pick a consent management platform, since tooling choices constrain what purposes and choices the build can support later on
- **D.** Map purposes: list what data is used for what, then give each purpose a basis, with consent covering the optional extras  ✅

> **Answer:** D

### Q13. A build shows a compliant marketing checkbox, but nothing is stored when users tick it. What does this module say about this situation?

- **A.** Consent you cannot prove is the practical equivalent of no consent: when asked who agreed to what and when, the build has no answer  ✅
- **B.** The checkbox itself is sufficient evidence, since the form's existence in version control shows exactly what every user must have seen
- **C.** Storage is optional because regulators contact users directly to confirm consent rather than asking companies for their records
- **D.** The gap matters only for sensitive data, since ordinary marketing consent is presumed valid until a specific user disputes it

> **Answer:** A

### Q14. Two versions of a consent ask: 'Send me product updates by email' versus a paragraph of legal language. Which does this module prefer, and why?

- **A.** The paragraph, since detail is what makes consent informed and short phrasing always hides material facts from the person agreeing
- **B.** The plain ask, with the full notice linked beneath: consent must be informed, and plain language is what actually informs a reader  ✅
- **C.** Either works equally, since validity depends on the storage of the consent record rather than anything about the wording of the ask
- **D.** Neither, since written asks are steadily being replaced by inferred consent based on user behavior across sessions and devices

> **Answer:** B

### Q15. A US client asks what CCPA specifically requires their e-commerce site to offer users. Which answer matches this module?

- **A.** Opt-in consent before any cookie loads, since CCPA imported the EU model wholesale and applies it to every category of site visitor
- **B.** Nothing, since CCPA governs data brokers exclusively and ordinary retail businesses fall entirely outside the scope of the statute
- **C.** Mandated opt-outs, including the right to opt out of the sale or sharing of personal information, under an opt-out style model  ✅
- **D.** A paid tier without data collection, since CCPA requires every business to sell a privacy-preserving version of each product

> **Answer:** C

### Q16. A build will serve EU and US users from one codebase, and the client wants to avoid maintaining two consent behaviors. What option does this module offer?

- **A.** Adopt the stricter opt-in standard everywhere, which is simpler and safer than maintaining per-region consent behavior in one codebase  ✅
- **B.** Apply US opt-out behavior everywhere, since the larger market's rules take precedence whenever a single codebase must choose one standard
- **C.** Average the two regimes by requiring opt-in only for cookies and opt-out for email, splitting the difference across the two channels
- **D.** Block EU visitors entirely, since serving two regimes from one codebase is not something consent tooling can realistically support

> **Answer:** A

### Q17. A client must keep invoice records for seven years under tax law and asks which lawful basis covers that retention. Which fits?

- **A.** Consent, refreshed annually, since long retention periods require users to repeatedly reaffirm that their records may be kept on file
- **B.** Vital interests, since financial records can become critical in emergencies and the basis exists for exactly these situations
- **C.** Legitimate interests, since the balancing test is the default home for any processing a business finds inconvenient to stop
- **D.** Legal obligation: the law itself requires the processing, so the retention rests on that basis rather than on user choice  ✅

> **Answer:** D

### Q18. A user unsubscribes; the app database flag flips, but the external campaign tool keeps mailing them. What does this module call this failure?

- **A.** A tooling limitation outside the builder's control, since third-party platforms own their own send logic and suppression lists
- **B.** Withdrawal that does nothing: revocation must reach every system doing the processing, not just a flag in the application database  ✅
- **C.** A timing issue only, since regulators allow unlimited transition periods for external tools to catch up with consent changes
- **D.** An acceptable pattern if the notice disclosed that third-party tools process the data, since that disclosure cures the ongoing sends

> **Answer:** B

### Q19. You want AI to help assign lawful bases for a build. Which prompt matches the directing pattern in this module?

- **A.** Here is the data-and-purpose table. Propose a basis per purpose, flag every judgment call for a lawyer, and mark which need consent UI  ✅
- **B.** Read this codebase and certify it as GDPR compliant, providing a signed legal opinion I can forward to the client's own regulator
- **C.** Generate a privacy notice with maximum legal protection, using the broadest language available so every future purpose is covered
- **D.** List every privacy law on earth with a short summary of each, so the team can read the full landscape before any build decision is made

> **Answer:** A

### Q20. A signup screen offers one checkbox covering product emails, marketing, and analytics together. What does this module direct instead?

- **A.** Keep one checkbox but expand its label to name all three purposes, since a fully descriptive label makes a combined consent specific
- **B.** Move analytics out of the checkbox into silent collection, since measurement is operationally necessary and needs no user choice
- **C.** One consent per purpose: separate, specific, unticked choices, since consent must be granular to stay valid in opt-in regimes  ✅
- **D.** Replace the checkbox with a modal on first login, since the timing of the ask matters more than how many purposes it bundles

> **Answer:** C

### Q21. A banner shows a giant Accept button, a Reject link hidden in settings, and analytics scripts that fired on page load. What is the verdict in this module?

- **A.** Acceptable, since offering any reject path at all satisfies opt-in rules regardless of prominence, placement, or script timing
- **B.** A design preference question for the client's brand team, since button sizing and color sit outside the scope of privacy rules
- **C.** Fixable through the consent record: if the store logs the eventual click, the early script firing becomes retroactively covered by it
- **D.** Consent theater: a compliance liability pretending to be a consent flow, since reject must be easy and scripts must wait for a yes  ✅

> **Answer:** D

### Q22. A builder asks when the vital interests and public task bases apply to typical client work. What does this module say?

- **A.** Both are common fallbacks for startups, covering most analytics and personalization when consent rates come in lower than hoped
- **B.** Rarely: vital interests is for life-and-death situations and public task is mostly government, so neither fits typical client builds  ✅
- **C.** Vital interests covers anything health-adjacent including wellness apps, while public task covers any company serving the general public
- **D.** They are interchangeable with legitimate interests, so builders can cite whichever of the three reads best in the documentation

> **Answer:** B

### Q23. A client is proud of a lawyer-written privacy notice, but users cannot say what data is collected after reading it. What test does this module apply?

- **A.** Whether a reader can answer 'what do they collect and why' in about a minute; a notice failing this fails its purpose, whoever wrote it  ✅
- **B.** Whether the lawyer who drafted it carries malpractice insurance, since professional accountability is what gives a notice its force
- **C.** Whether the notice has been translated into every language the product supports, since full coverage is the true measure of communication
- **D.** Whether it lists every conceivable future purpose, since breadth of legal coverage is what regulators actually score notices on

> **Answer:** A

### Q24. A small project needs cookie consent, and the client asks whether to buy a consent management platform. How does this module frame the choice?

- **A.** Always buy a CMP, since custom banners cannot legally block scripts and only certified platforms are recognized by the regulators
- **B.** Never buy a CMP, since third-party consent tooling introduces its own trackers and defeats the purpose of the exercise entirely
- **C.** Defer the choice until after launch, since consent tooling is easiest to retrofit once real traffic shows which regions matter
- **D.** Choose based on complexity: CMPs exist for cookie consent at scale, but a well-directed banner plus consent records is often enough  ✅

> **Answer:** D

### Q25. Looking across this whole module, what is the governing principle of consent, notice, and lawful processing?

- **A.** Consent is the universal answer: collect it for every purpose and store nothing else, since a full consent trail replaces the other bases
- **B.** Notices are the core deliverable: a sufficiently thorough document lawfully covers whatever processing the product later performs
- **C.** Every purpose rests on a recognized lawful basis, consent is unbundled and provable, and notices communicate: build mechanics you can show  ✅
- **D.** Lawful processing is a legal document problem: builders implement what the lawyers hand down and mechanics play no independent part

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/107139919_
