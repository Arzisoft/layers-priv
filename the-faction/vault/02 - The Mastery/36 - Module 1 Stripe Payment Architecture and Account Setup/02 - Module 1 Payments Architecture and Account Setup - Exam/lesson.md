---
course: "The Mastery"
module: "Module 1: Stripe Payment Architecture and Account Setup"
lesson: "Module 1: Payments Architecture and Account Setup — Exam"
type: "course_quiz"
post_id: 106562769
space_id: 24191170
source: "https://the-faction.mn.co/posts/106562769"
updated: "2026-08-28T15:59:30Z"
---

# Module 1: Payments Architecture and Account Setup — Exam

> Exam for **Module 1: Stripe Payment Architecture and Account Setup** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A founder is launching a SaaS product that will take its own payments directly from customers. She asks which Stripe account type to direct AI to build against. What do you recommend?

- **A.** A Standard account, because the business is charging its own customers with no other sellers involved  ✅
- **B.** An Express account, because Stripe-hosted onboarding reduces the compliance work the founder handles
- **C.** A Custom account, because full white-label control is the safest default for any new payments build
- **D.** A Connect platform with Standard sub-accounts, because it leaves room to add marketplace sellers later

> **Answer:** A

### Q2. A builder is creating a marketplace where independent tutors get paid through the platform. He wants Stripe to handle seller onboarding screens while the platform manages payout timing. Which account type fits?

- **A.** Standard accounts for each tutor, since every seller should fully own and manage their own dashboard
- **B.** Express accounts, since Stripe hosts seller onboarding while the platform controls the payout flow  ✅
- **C.** A single Standard account, since all tutor payments can simply flow through the platform's balance
- **D.** Custom accounts, since the platform should hand-build every onboarding and verification screen itself

> **Answer:** B

### Q3. A team finished building in test mode and is preparing for launch. A junior teammate asks whether the test customers and products will be available once they switch to live keys. What is the accurate answer?

- **A.** Customers transfer to live mode automatically but products and prices must be recreated by hand first
- **B.** Everything transfers as long as the account is verified and the live bank account details are complete
- **C.** Nothing transfers, because test and live mode are fully separate environments with separate data stores  ✅
- **D.** Products transfer but customer records stay behind for privacy reasons under card network guidelines

> **Answer:** C

### Q4. During a review, you find the Stripe secret key embedded in the frontend JavaScript bundle of a client's site. What is the correct assessment of the situation?

- **A.** Acceptable short term, because the key only works from the site's own registered domain and origin
- **B.** A minor issue, because attackers would still need the publishable key to pair with it for requests
- **C.** A problem only if the site handles subscriptions, since one-time charges expose far less capability
- **D.** A critical exposure, because anyone can extract it and use it to create charges and read customer data  ✅

> **Answer:** D

### Q5. A business wants to give an external analytics vendor access to read Stripe charge data. The vendor does not need to create payments or issue refunds. What do you direct AI to configure?

- **A.** A restricted key granting read-only access to the specific resources the analytics vendor requires  ✅
- **B.** The standard secret key shared over an encrypted channel, since the vendor signed a data agreement
- **C.** The publishable key, since it is designed for third parties and cannot modify any account resources
- **D.** A second Standard account mirrored from the first, so vendor access never touches production data

> **Answer:** A

### Q6. A builder is mapping the Stripe object model before directing a build. He asks how a PaymentIntent relates to a Charge. What is the correct relationship?

- **A.** A Charge is the state machine that tracks an attempt, and the PaymentIntent records the money moving
- **B.** A PaymentIntent tracks one attempt to collect payment and a successful one produces a Charge record  ✅
- **C.** They are interchangeable names for the same object kept for backward compatibility across versions
- **D.** A PaymentIntent can only exist after a Charge succeeds, since intents summarize completed payments

> **Answer:** B

### Q7. A teammate asks why the build should create a Customer object instead of just charging cards anonymously each time. What is the strongest reason?

- **A.** Customer objects are required by card networks before any charge can be legally processed at all
- **B.** Anonymous charges cost more per transaction because Stripe prices them at a higher processing tier by default
- **C.** Customer objects speed up settlement because banks batch payments by customer record identifiers
- **D.** The Customer is the durable record that lets you attach saved payment methods, subscriptions, and history  ✅

> **Answer:** D

### Q8. A developer reports confusing authentication errors: some API calls succeed while others fail with cryptic messages. You discover the frontend uses a test publishable key while the backend uses a live secret key. What is this failure called and why does it happen?

- **A.** A webhook drift issue, which happens when event versions differ between the two Stripe environments
- **B.** A key rotation fault, which happens when an old key stays cached after a new one has been issued
- **C.** Mixed mode keys, which fail because test and live are separate environments that cannot interoperate  ✅
- **D.** A scope mismatch, which happens when restricted permissions differ between the two keys in use

> **Answer:** C

### Q9. A subscription business is seeing a steady stream of chargebacks where customers claim they do not recognize the transaction. The product works fine. What account-level setting should you investigate first?

- **A.** The statement descriptor, because customers dispute charges from names they do not recognize on statements  ✅
- **B.** The default currency setting, because conversions can make familiar amounts look foreign on statements
- **C.** The payout schedule, because delayed settlement often confuses customers reviewing recent transactions each month
- **D.** The API version, because older versions format transaction records differently for the issuing banks

> **Answer:** A

### Q10. A founder describes her product: customers pay her company, and her company later pays service providers through normal vendor payouts from her bank. She asks if she needs Stripe Connect. What is the right call?

- **A.** Yes, because any business that pays third parties is legally operating as a payments platform under card rules
- **B.** Yes, because Connect is required whenever more than one bank account is involved in the flow end to end
- **C.** No, because she is collecting her own revenue, and paying vendors from her bank is not platform money movement  ✅
- **D.** No, because Connect only applies to businesses that sell physical goods across state or country lines to consumers

> **Answer:** C

### Q11. A builder asks what actually gets stored when a customer saves a card for future use. What do you tell him about how card details are handled?

- **A.** The card number is encrypted and stored in your database so future charges can skip Stripe entirely
- **B.** Stripe tokenizes the card into a PaymentMethod object, and your systems only ever hold the token reference  ✅
- **C.** The card number is split between your database and Stripe so neither party holds the complete record
- **D.** The card is stored in the customer's browser storage and transmitted again with every future purchase

> **Answer:** B

### Q12. A secret key was accidentally committed to a public repository twenty minutes ago. What sequence do you direct AI to execute first?

- **A.** Delete the repository commit and force-push, since removing the public copy ends the exposure window
- **B.** Monitor the dashboard for suspicious charges for a week before deciding whether rotation is needed
- **C.** Email Stripe support to flag the account and wait for their team to confirm before changing anything
- **D.** Roll the key immediately in the dashboard, update server environments, then audit logs for misuse  ✅

> **Answer:** D

### Q13. A builder wants a one-sentence mental model of the PaymentIntent before directing a checkout build. Which description is accurate?

- **A.** It is the state machine for collecting one payment, tracking the attempt from creation through success or failure  ✅
- **B.** It is the ledger entry Stripe writes after settlement, summarizing fees and the net amount deposited
- **C.** It is the reusable template that defines the amount every future customer will be charged at checkout during setup
- **D.** It is the fraud scoring object Radar attaches to a card before any charge is allowed to proceed alone

> **Answer:** A

### Q14. An AI agent has been directed to complete the Stripe account setup for a new business. Which parts of setup cannot be delegated to the agent and must be completed by the account owner?

- **A.** Creating products and prices, because catalog objects require a human to confirm every amount entered before the launch date
- **B.** Business verification, identity, and bank account details, because account ownership must be established by the owner  ✅
- **C.** Webhook endpoint registration, because signing secrets are only revealed to the account holder directly by email
- **D.** Test card configuration, because simulated payment behavior is locked to verified human operators remotely

> **Answer:** B

### Q15. A builder finished a checkout flow and wants to verify how the system behaves when a card is declined or requires authentication. What is the professional way to test this in test mode?

- **A.** Use a real card with a low balance, because genuine declines are the only trustworthy signal available
- **B.** Ship to production quietly and watch the first week of real traffic for declines and auth challenges
- **C.** Use Stripe's documented test card numbers that simulate declines, disputes, and authentication flows  ✅
- **D.** Ask five teammates to attempt purchases with expired personal cards and compare the resulting errors

> **Answer:** C

### Q16. A platform is weighing Custom accounts for full white-label control over seller onboarding. What tradeoff must the platform accept with that choice?

- **A.** It takes on responsibility for onboarding, compliance, and support burdens that Stripe handles in other types  ✅
- **B.** It loses access to the Stripe dashboard entirely, since Custom accounts are managed purely through the API layer
- **C.** It pays materially higher per-transaction pricing, since white-label capability is a premium feature tier
- **D.** It gives up webhook support, since Custom account events are only available through daily report files

> **Answer:** A

### Q17. A frontend engineer asks whether it is safe for the publishable key to appear in the browser where anyone can view source and read it. What do you tell her?

- **A.** It is unsafe, and the build should proxy every Stripe call through the backend to hide the key fully
- **B.** It is safe only when the site runs behind a login, since public pages would expose it to scrapers
- **C.** It is unsafe unless rotated weekly, since long-lived browser keys accumulate exposure over their lifetime
- **D.** It is safe by design, since the publishable key can only initiate client flows and cannot move money  ✅

> **Answer:** D

### Q18. The night before launch, a builder asks what happens to the live environment configuration given that everything was built and verified in test mode. What must the team plan for?

- **A.** Live mode inherits configuration on first API call, so the first real customer triggers the full copy
- **B.** Products, prices, webhooks, and settings must be recreated in live mode, since nothing carries over  ✅
- **C.** Only webhook endpoints carry over, so the team just needs to rebuild the product catalog by hand
- **D.** Stripe support migrates test configuration on request, so the team should file a ticket before launch

> **Answer:** B

### Q19. You are auditing where a project stores its Stripe credentials. Which storage location is the professional standard for the secret key?

- **A.** A config file in the repository, since version control provides history and access is limited to the team
- **B.** A shared password manager entry that engineers copy into their local files whenever they need it
- **C.** Server-side environment variables managed by the hosting platform's secret store, never in code  ✅
- **D.** An encrypted column in the application database, loaded into memory when the server process starts

> **Answer:** C

### Q20. A founder is deciding between direct integration and building on Connect. Her product is a simple B2B SaaS with monthly plans. What makes choosing Connect here the most expensive kind of mistake?

- **A.** It multiplies complexity across every later build layer while the business never needed platform money flows  ✅
- **B.** It permanently locks the account into marketplace pricing tiers that cannot be reversed once selected
- **C.** It disables Stripe Billing features, forcing the team to hand-build subscription logic from scratch internally
- **D.** It requires a money transmitter license in most states before the first live transaction can settle

> **Answer:** A

### Q21. A builder asks what the Charge object actually represents in the object model, as distinct from the intent that produced it. What is accurate?

- **A.** The Charge is the customer's saved payment credential, tokenized so raw card data never touches you
- **B.** The Charge is the pending authorization hold that expires unless the intent confirms within a week
- **C.** The Charge is the durable customer profile that accumulates payment history across many purchases
- **D.** The Charge is the record of an actual money movement, created when a payment attempt succeeds  ✅

> **Answer:** D

### Q22. An internal admin tool only needs to look up customers and their subscription status for the support team. When directing AI to build it, what credential principle applies?

- **A.** Use the full secret key, since internal tools behind the company VPN are inside the trust boundary
- **B.** Grant the minimum permissions needed with a restricted key, so a compromise limits what an attacker gets  ✅
- **C.** Use the publishable key, since read operations are exactly what client-side keys were designed for
- **D.** Skip Stripe credentials and scrape the dashboard, since support tooling should never hold API access

> **Answer:** B

### Q23. A new teammate asks for a plain definition of a Standard Stripe account before touching the build. Which description is correct?

- **A.** A full Stripe account the business owns and controls directly, with its own dashboard and relationship with Stripe  ✅
- **B.** A lightweight account type that can only accept payments below a monthly volume cap set at signup time by the platform
- **C.** A sub-account that always requires a parent platform account to authorize its payouts and refunds directly
- **D.** A temporary sandbox account that converts into Express or Custom once business verification completes

> **Answer:** A

### Q24. A payment failed for a customer and the engineering team is debugging blind, guessing at what Stripe saw. Where do you direct them to look first?

- **A.** The customer's bank statement, since issuer-side records are the authoritative view of any failure
- **B.** The application's own error logs, since Stripe's perspective adds little beyond the API response
- **C.** The Stripe dashboard logs and event feed, which record every API request, response, and event with details  ✅
- **D.** The browser console on the customer's device, since client-side errors precede most payment failures in practice

> **Answer:** C

### Q25. Looking across everything in this module, what is the governing principle for payments architecture and account setup?

- **A.** Optimize for launch speed first, because architecture can always be refactored once revenue proves demand
- **B.** Choose the most flexible account type available, because future business models are impossible to predict
- **C.** Delegate the full setup to AI end to end, because modern agents handle compliance better than owners do
- **D.** Get the account model, key discipline, and object model right up front, because every later layer builds on them  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/106562769_
