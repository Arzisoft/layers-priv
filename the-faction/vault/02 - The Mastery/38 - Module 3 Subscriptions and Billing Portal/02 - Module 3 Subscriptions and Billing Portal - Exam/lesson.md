---
course: "The Mastery"
module: "Module 3: Subscriptions and Billing Portal"
lesson: "Module 3: Subscriptions and Billing Portal — Exam"
type: "course_quiz"
post_id: 106562773
space_id: 24191170
source: "https://the-faction.mn.co/posts/106562773"
updated: "2026-08-28T16:05:18Z"
---

# Module 3: Subscriptions and Billing Portal — Exam

> Exam for **Module 3: Subscriptions and Billing Portal** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A customer's subscription just moved to past_due after a failed renewal. A junior builder wants to revoke access immediately. What does past_due actually signal, and what is the right response?

- **A.** The customer canceled and access should end today, since past_due is the final state before deletion
- **B.** Payment failed and recovery is underway, so access should continue while retries and dunning run  ✅
- **C.** The card was flagged for fraud, so the account should be suspended pending a manual review process
- **D.** The invoice was disputed, so access decisions must wait until the chargeback process fully resolves

> **Answer:** B

### Q2. A founder is launching a straightforward SaaS with one core offering and asks which price model to direct AI to configure. Nothing about the revenue model varies by usage or team size. What do you recommend?

- **A.** Metered billing, because usage data collection from day one enables pricing experiments later on
- **B.** Tiered pricing, because volume discounts should be structurally available before customers ask
- **C.** Per-seat pricing, because every SaaS eventually sells to teams and retrofitting seats is painful
- **D.** Flat rate, because it is the simplest model that fits, and complexity should be added only when earned  ✅

> **Answer:** D

### Q3. A collaboration tool charges by the number of teammates a customer adds. Which price model maps directly to this revenue design?

- **A.** Per-seat pricing, where the subscription quantity multiplies a per-unit price as a team grows  ✅
- **B.** Metered billing, where each teammate's daily activity is reported and billed in arrears monthly
- **C.** Graduated tiers, where the whole team's price shifts to a new bracket at each headcount level
- **D.** Flat rate with add-ons, where each teammate is modeled as a separate one-time purchase item

> **Answer:** A

### Q4. An API product wants to bill customers for the exact number of calls they made each month, after the month ends. Which mechanism fits, and how does it work?

- **A.** Flat rate with refunds, where overpayment is returned once actual usage is known at period close each month
- **B.** Metered billing, where you report usage to Stripe during the period and the invoice bills in arrears  ✅
- **C.** Per-seat with adjustments, where the quantity is corrected retroactively when the period closes
- **D.** Prepaid credits, since Stripe subscriptions cannot represent consumption that varies by month

> **Answer:** B

### Q5. A team is debating card-up-front trials vs no-card trials for their fourteen-day trial. What is the honest tradeoff you put in front of them?

- **A.** Card-up-front is banned in several markets, so no-card is the only globally compliant trial design
- **B.** No-card trials convert higher at trial end, since customers self-select for stronger purchase intent
- **C.** Card-up-front converts higher but demands honest reminders; no-card gets more signups and a hard wall  ✅
- **D.** The models perform identically at scale, so the choice is purely about engineering convenience

> **Answer:** C

### Q6. A customer on the 30 dollar plan upgrades to the 90 dollar plan halfway through the month. With standard proration, what happens?

- **A.** Unused time on the old price is credited and partial time on the new price is charged for the remainder  ✅
- **B.** The customer pays the full 90 immediately and the old 30 payment is refunded to the original card
- **C.** Nothing changes until renewal, when the new price takes effect for the following full billing cycle instead
- **D.** The two prices are averaged for the current month and the new price begins at the next cycle start

> **Answer:** A

### Q7. A customer downgrades from a premium plan mid-cycle. Many businesses schedule this change at period end instead of applying it instantly. What is the reasoning?

- **A.** Stripe cannot compute proration on downgrades, so period-end scheduling is the only supported path
- **B.** Immediate downgrades void the original invoice, which breaks revenue recognition for the period
- **C.** Card networks require notice before any reduction in a recurring charge takes effect for a customer
- **D.** It avoids refund math and lets the customer keep what they paid for through the period they bought  ✅

> **Answer:** D

### Q8. A founder asks you to direct AI to build a custom plan management UI: update cards, switch plans, cancel, view invoices. What is the professional counter-recommendation?

- **A.** Build it, but only the card update piece, since plan switching is too risky for self-service anyway
- **B.** Configure the Stripe Billing Portal instead, which delivers all of it as a maintained hosted flow  ✅
- **C.** Build it fully custom, since hosted portals cannot enforce which plan switches a business allows
- **D.** Skip self-service entirely, since support-mediated changes produce fewer billing mistakes overall

> **Answer:** B

### Q9. A business enables the Billing Portal but customers keep switching to a legacy plan that should be retired. Where is this fixed?

- **A.** In application code, by intercepting the portal redirect and blocking the legacy plan selection
- **B.** It cannot be fixed; the portal always exposes every active price the account has ever created
- **C.** In portal configuration, which controls exactly which products and prices customers may switch between  ✅
- **D.** By deleting the legacy price object, which is safe because existing subscribers migrate automatically to it

> **Answer:** C

### Q10. An app needs to check what plan a user is on every time a gated feature loads. What is the professional entitlement pattern?

- **A.** Read from a local record synced by webhooks, with plan identifiers carried in subscription metadata  ✅
- **B.** Call the Stripe API on every feature check, since live data beats any locally cached representation
- **C.** Decode the plan from the user's session cookie, set once at signup and trusted for the account's life
- **D.** Check the customer's invoice history each morning and cache the newest plan name for the day

> **Answer:** A

### Q11. A customer cancels in the portal on day 10 of a 30-day cycle. The business configured cancellation at period end. What does the customer experience?

- **A.** Access ends immediately and a prorated refund for the remaining twenty days is issued automatically
- **B.** Access ends immediately with no refund, since cancellation always terminates service on the spot
- **C.** The subscription pauses indefinitely and can be resumed at any point without creating a new one
- **D.** Access continues through day 30, then the subscription ends and no further invoices are generated  ✅

> **Answer:** D

### Q12. A builder needs to verify that renewals, trial conversions, and cancellation timing behave correctly without waiting a real month. What do you direct AI to use?

- **A.** Manually edited database dates, shifting stored timestamps backward to make renewals appear due
- **B.** Stripe test clocks, which simulate time advancing against test subscriptions to trigger real lifecycle events  ✅
- **C.** Production observation, since time-based behavior can only be trusted when watched with live data
- **D.** Shortened one-day billing intervals in test mode, then mentally scaling the results up to a month

> **Answer:** B

### Q13. A user is in the trialing status on a card-up-front trial. The product team asks how to treat them. What is correct?

- **A.** Grant full access now; trialing is an access-granting status and conversion is handled at trial end  ✅
- **B.** Grant read-only access until the first invoice pays, since no money has actually moved yet at all here
- **C.** Grant nothing until trial end, since trialing merely reserves the plan without activating service
- **D.** Grant access only after manually verifying the card, since trial cards are unvalidated by default

> **Answer:** A

### Q14. A pricing page offers 10 units at one rate and cheaper rates for units beyond that. The founder asks the difference between graduated and volume tiers before directing the build. What is it?

- **A.** Graduated applies only to annual billing, while volume tiers are the mechanism for monthly plans instead
- **B.** Volume tiers are billed in arrears while graduated tiers must always be prepaid at cycle start
- **C.** Graduated charges each bracket at its own rate; volume charges every unit at the final bracket's rate  ✅
- **D.** They are two dashboard names for identical math, kept for backward compatibility with old plans

> **Answer:** C

### Q15. During review, you find an app calling the Stripe API on every page load to check subscription status. What is the professional assessment?

- **A.** Correct as built, because entitlements must always reflect Stripe's live state with zero drift
- **B.** Acceptable if responses are cached for sixty seconds, which removes any meaningful API load
- **C.** Wrong direction entirely; status should be pushed by Stripe at signup and never checked again
- **D.** Slow and fragile; webhook-synced local state should drive access, with Stripe as the source it syncs from  ✅

> **Answer:** D

### Q16. A card-up-front trial is converting well, but refund requests spike right after each trial ends. What is the most likely gap in the build?

- **A.** No end-of-trial reminder emails, so customers are surprised by a charge they forgot was coming  ✅
- **B.** The trial length is too long, giving customers time to extract full value before the charge lands
- **C.** Proration is misconfigured, so converted customers are billed for the trial period retroactively
- **D.** The plan price is set too high for the market, and the refunds are really price objections in disguise

> **Answer:** A

### Q17. A teammate asks what the canceled status means for a subscription, as distinct from a cancellation that is merely scheduled. What is accurate?

- **A.** Canceled means the customer requested cancellation, which may still be withdrawn before period end
- **B.** Canceled means a subscription has actually ended; a scheduled cancellation still shows as active  ✅
- **C.** Canceled means payment failed past all retries, which is distinct from customer-initiated endings
- **D.** Canceled means the price was archived, ending every subscription attached to it simultaneously

> **Answer:** B

### Q18. A seasonal business wants customers to stop paying during their off months without losing their account history or forcing a fresh signup later. What fits this need?

- **A.** Cancel each fall and direct customers to re-subscribe each spring under a new subscription object
- **B.** A 100 percent discount coupon applied during off months, keeping invoices flowing at zero dollars
- **C.** Pausing the subscription, which halts billing while preserving the subscription for later resumption  ✅
- **D.** Downgrading to a hidden free price each fall, then upgrading again when the season starts back up later

> **Answer:** C

### Q19. A team product needs billing to scale as seats are added or removed mid-cycle. Where does seat count actually live in a per-seat subscription?

- **A.** In subscription metadata, as a number the application increments and decrements as seats change over time
- **B.** In a separate add-on product purchased once per seat through an additional checkout session
- **C.** In the customer object's account settings, which the invoice generator reads at each renewal
- **D.** In the subscription item's quantity, which multiplies the per-unit price and can prorate on change  ✅

> **Answer:** D

### Q20. A subscription entered past_due this morning. The business has a defined grace period. What does the access policy look like while recovery runs?

- **A.** Access continues through the grace window while retries and dunning work, then suspends if recovery fails  ✅
- **B.** Access is cut at the first failure and restored only after the customer contacts support directly
- **C.** Access drops to a read-only tier immediately and full service resumes only at the next renewal
- **D.** Access continues indefinitely, since revoking service over payment issues creates churn risk

> **Answer:** A

### Q21. A builder is wiring the Billing Portal into an app. What does the integration actually consist of on the application side?

- **A.** Embedding the portal as an iframe with a public URL that is identical for every customer account type
- **B.** One endpoint that creates a portal session for the customer, then a link that sends them to that URL  ✅
- **C.** A nightly job that emails each customer a fresh portal link, since sessions expire within hours
- **D.** A full OAuth handshake between the app and Stripe, granting portal scope per customer account

> **Answer:** B

### Q22. A founder wants metered billing because it feels sophisticated, but the product's cost and value do not vary with usage. What is the strategic counsel?

- **A.** Adopt metered anyway, since usage data becomes a moat and pricing can be simplified later cheaply
- **B.** Split the difference with tiered pricing, which signals sophistication without usage reporting overhead
- **C.** Adopt metered but bill everyone the same amount, keeping the machinery warm for future pricing
- **D.** Choose the simplest model that fits the business, because every added model multiplies future changes  ✅

> **Answer:** D

### Q23. Support keeps fielding tickets like: why was I charged 13.47 this month? The amounts are correct. What is the actual root cause to fix?

- **A.** A currency conversion bug, since odd cents almost always trace to exchange rate rounding drift
- **B.** Stripe fee pass-through, which itemizes processing costs on customer invoices unless disabled
- **C.** Proration ran on plan changes without a deliberate policy or customer-facing explanation of the math  ✅
- **D.** Duplicate partial invoices, which occur when webhooks process subscription updates out of order somewhere

> **Answer:** C

### Q24. A builder asks why Module 4's invoice events matter so much for subscriptions specifically. What is the structural reason?

- **A.** Every subscription renewal is an invoice under the hood, so invoice events are how renewals reach your app  ✅
- **B.** Invoices are the only Stripe object that carries metadata, so entitlements can only sync through them
- **C.** Subscription objects are deleted after each cycle, leaving invoices as the only durable record
- **D.** Invoice events arrive faster than subscription events, so they are preferred purely for latency

> **Answer:** A

### Q25. Looking across everything in this module, what is the governing principle for subscription systems?

- **A.** Maximize pricing flexibility up front, because changing a price model after launch is nearly impossible
- **B.** Keep customers away from self-service billing, because plan changes are too consequential to automate
- **C.** Respect the lifecycle: subscriptions are long-running state machines the app must track and respond to  ✅
- **D.** Check Stripe directly for every decision, because local state can never be trusted to match reality

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106562773_
