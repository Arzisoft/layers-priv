---
course: "The Mastery"
module: "Module 4: Usage Metering and Billing"
lesson: "Module 4: Usage Metering and Billing — Exam"
type: "course_quiz"
post_id: 106571047
space_id: 24191170
source: "https://the-faction.mn.co/posts/106571047"
updated: "2026-08-28T16:20:52Z"
---

# Module 4: Usage Metering and Billing — Exam

> Exam for **Module 4: Usage Metering and Billing** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. This module says metering errors are especially damaging. What is the underlying reason a counting mistake is so serious for an API product?

- **A.** Metering errors are billing errors, and billing errors destroy customer trust faster than almost any other kind of bug in a product ever  ✅
- **B.** Metering errors slow the API, since a miscount forces the system to recompute usage on every request until the discrepancy is resolved
- **C.** Metering errors break versioning, since usage counts are tied to the API version and a miscount routes the customer to the wrong endpoints
- **D.** Metering errors expose keys, since the counting system stores credentials alongside usage and any counting fault can leak them to others

> **Answer:** A

### Q2. This module names three dimensions to meter along. Which set matches?

- **A.** Per region, per language, per protocol, since usage varies by where and how developers call and pricing should reflect those factors
- **B.** Per version, per scope, per tier, since metering exists chiefly to enforce the access limits attached to each credential in the system
- **C.** Per key, per endpoint, per time period, since these are the dimensions that billing and product decisions actually depend upon  ✅
- **D.** Per error, per retry, per latency bucket, since usage is best understood through the reliability characteristics of each individual call

> **Answer:** C

### Q3. This module contrasts synchronous counting with async log aggregation. What is the core tradeoff between them?

- **A.** Storage cost versus query speed, since synchronous counting stores much less data overall while async aggregation stores far more but queries it faster
- **B.** Real-time accuracy versus request-path performance and reliability, since counting in the request path is accurate but adds work and a failure point  ✅
- **C.** Security versus convenience, since synchronous counting is harder to tamper with while async aggregation is easier to operate day to day
- **D.** Cost versus compliance, since synchronous counting is cheaper while async aggregation is required to satisfy financial auditing standards

> **Answer:** B

### Q4. This module calls the customer usage dashboard both a trust feature and a support-load reducer. How does it reduce support load?

- **A.** It replaces the docs, since a dashboard that shows usage answers the integration questions developers would otherwise raise as tickets
- **B.** A customer who sees they are nearing their limit does not open a ticket asking why, and one who can reconcile usage does not dispute the invoice  ✅
- **C.** It hides usage detail, since showing customers only a summary prevents the confusion that drives most usage-related support requests
- **D.** It rate-limits tickets, since customers must consult their dashboard before the support system will accept a new request from them at all

> **Answer:** B

### Q5. This module says Stripe metered subscriptions are built for usage-based pricing. What do you do rather than reimplementing billing yourself?

- **A.** Store usage in the API keys, since embedding the running total in the credential lets Stripe read it directly without a separate report call
- **B.** Export raw logs to the customer, since handing them the usage data lets them compute their own charge and removes billing from your scope
- **C.** Charge a flat monthly fee, since metered pricing is too complex to integrate and a fixed price avoids the need for any usage reporting at all
- **D.** Report usage to Stripe against a subscription item, and let Stripe compute the charge from the price model you configured for that plan  ✅

> **Answer:** D

### Q6. This module calls one requirement trust-critical. Which is it?

- **A.** The dashboard usage must reconcile to the invoice since a customer who sees different numbers in each place will trust neither of them  ✅
- **B.** Keys must be hashed, since a customer who learns their credentials were stored in plaintext will never trust the billing numbers either
- **C.** The API must be versioned, since a customer cannot trust usage counts unless every metered call is pinned to a single stable version
- **D.** Latency must be low, since a customer interprets a slow usage dashboard as evidence the underlying billing figures are also unreliable

> **Answer:** A

### Q7. A team meters every call by incrementing a counter inside the request path. What cost does this module associate with that synchronous choice?

- **A.** It undercounts, since counters in the request path miss any call that fails before reaching the increment step and leak that usage entirely
- **B.** It breaks reconciliation, since request-path counters cannot be read by the billing system and must be exported to a separate store first
- **C.** It adds work and a potential failure point to every call, trading request-path performance and resilience for real-time counting accuracy  ✅
- **D.** It exposes usage, since counting inside the request path returns the running total to the caller in a response header they can manipulate

> **Answer:** C

### Q8. This module says to meter at a specific granularity. What goes wrong if you meter too coarsely?

- **A.** You cannot price by value, since coarse metering hides which endpoints drive load and cost and leaves you unable to charge for them  ✅
- **B.** You slow the API, since coarse counting requires the system to reprocess each request multiple times to reconstruct the missing detail
- **C.** You leak revenue immediately, since any metering coarser than per-request mathematically undercounts and bills less than the customer owes
- **D.** You break Stripe, since metered subscriptions reject any usage report that is not itemized down to the individual endpoint and timestamp

> **Answer:** A

### Q9. This module describes overage charges as part of a pricing model. What does an overage model consist of?

- **A.** A base allowance plus per-unit charges beyond it, so the customer gets an included quota and pays incrementally once they exceed it  ✅
- **B.** A per-call price only, since overage models bill every request individually with no base allowance included in the subscription at all
- **C.** A flat fee with no usage component, since overage pricing means charging one fixed amount regardless of how much the customer actually calls
- **D.** A prepaid balance that never refills, since overage means the customer buys a fixed block of calls and access simply stops when it runs out

> **Answer:** A

### Q10. This module says the dashboard and the invoice must draw from the same source. What specifically must they share to reconcile?

- **A.** The same color scheme, since a customer trusts figures more when the dashboard and the invoice are styled to look visually consistent
- **B.** The same usage records and period boundaries, so that customer can map each invoice charge back to usage they can see in the dashboard  ✅
- **C.** The same support contact, since a customer resolves any discrepancy faster when one team owns both the dashboard and the billing system
- **D.** The same currency, since reconciliation fails whenever the dashboard displays usage in one currency and the invoice bills in another one

> **Answer:** B

### Q11. This module describes prepaid credit systems. How does prepaid change the metering job compared with pay-as-you-go?

- **A.** It shifts counting to Stripe, since prepaid balances are held on the payment platform and the API no longer tracks usage on its own side
- **B.** It removes metering entirely, since a prepaid customer has already paid and their subsequent usage no longer needs to be counted at all
- **C.** It requires synchronous counting only for reads, since prepaid balances are drawn down by read operations while writes remain free of charge
- **D.** It moves from billing after the fact to decrementing a balance in real time, warning or cutting off when the balance runs low  ✅

> **Answer:** D

### Q12. This module says usage should be recorded with enough granularity to answer two distinct questions. What are they?

- **A.** The security question and the compliance question, since metering must satisfy both the abuse detector and the financial auditor at once
- **B.** The latency question and the uptime question, since metering exists chiefly to feed the reliability monitoring the SLA depends upon
- **C.** The versioning question and the deprecation question, since usage data determines which old versions are safe to retire and when
- **D.** The billing question of what a customer owes, and the product question of which endpoints drive load and value across the whole API  ✅

> **Answer:** D

### Q13. This module says the right choice between synchronous and async metering depends on one factor. Which?

- **A.** The programming language, since synchronous counting suits compiled languages while interpreted ones require async aggregation to keep up
- **B.** Whether a decision like enforcing a hard cap must happen in real time, since real-time enforcement needs the accuracy of synchronous counting  ✅
- **C.** The number of endpoints, since APIs with many routes must count asynchronously while small APIs can afford synchronous counting easily
- **D.** The customer's plan, since free-tier usage is counted asynchronously to save cost while paid tiers are counted synchronously for accuracy

> **Answer:** B

### Q14. A customer disputes their bill because their dashboard showed 12,000 calls but the invoice charged for 12,400. What does this module identify as the root failure?

- **A.** The API was too slow, since latency caused some calls to be retried and the retries inflated the invoice beyond what the dashboard captured
- **B.** The customer exceeded their tier, since the extra 400 calls represent overage the dashboard was not configured to display to the customer
- **C.** The key was shared, since multiple users on one credential produced usage the dashboard attributed elsewhere while the invoice caught it all
- **D.** The dashboard and invoice drew from different records or period boundaries here so the two numbers disagree and the customer trusts neither  ✅

> **Answer:** D

### Q15. This module says metering too finely also has a cost. What is the downside of excessive granularity?

- **A.** It overcharges customers, since finer metering counts each sub-operation of a request separately and inflates the total the customer owes
- **B.** It wastes storage without insight, since capturing more detail than the pricing model uses consumes space while adding no usable information  ✅
- **C.** It breaks Stripe reporting, since metered subscriptions reject usage reports that exceed a fixed number of line items per billing period
- **D.** It slows every call, since fine-grained counting requires the request path to write many records synchronously before returning a response

> **Answer:** B

### Q16. This module says a usage dashboard should expose the same data that drives billing. Why come from one source rather than two?

- **A.** To reduce latency, since serving the dashboard and the billing system from one store halves the number of queries the database must run
- **B.** To simplify keys, since a single usage source lets each credential carry one running total instead of a separate count per subsystem
- **C.** So the customer's view and the billing system's view agree, since two separate sources are exactly how dashboard and invoice diverge  ✅
- **D.** To satisfy versioning, since one usage source ensures every metered call is attributed to the same API version across both systems

> **Answer:** C

### Q17. This module says a heavy endpoint may cost more to serve. How does per-endpoint metering let you act on that?

- **A.** It lets you price by value, since knowing which endpoints are expensive lets you charge more for the operations that actually cost more  ✅
- **B.** It lets you cache more, since per-endpoint counts reveal which routes are hottest and therefore which responses to store aggressively
- **C.** It lets you version faster, since per-endpoint usage shows which routes are unused and can be removed in the next breaking release
- **D.** It lets you rate-limit globally, since per-endpoint totals feed a single shared cap that throttles the whole API when any route runs hot

> **Answer:** A

### Q18. This module says a prepaid balance a customer cannot trust is worse than no balance at all. What must you handle carefully to make the balance trustworthy?

- **A.** The color of the balance display, since customers judge the reliability of a prepaid figure largely by how prominently it is styled
- **B.** The currency conversion, since prepaid balances denominated in one currency must be shown in the customer's local currency to be believed
- **C.** The edge cases: what happens at zero, whether overage is allowed, and how top-ups apply, since unpredictable behavior destroys trust in the balance  ✅
- **D.** The API version, since a prepaid balance is only trustworthy when every draw-down is pinned to the same version the customer purchased under

> **Answer:** C

### Q19. This module says most API products at scale lean async for the hot path and reconcile. What does reconcile mean here?

- **A.** Refunding overcharges, since reconciliation is the monthly process of returning money to customers whose async counts came in too high
- **B.** Merging versions, since reconciliation aligns usage counts across API versions so a customer on multiple versions sees one combined total
- **C.** Rotating keys, since reconciliation is the step that matches each logged call back to a current credential after old keys are retired
- **D.** Tallying all the logged calls in a separate pipeline to finalize usage, accepting some delay before the numbers are settled and billable  ✅

> **Answer:** D

### Q20. A team computes billing charges themselves in application code instead of using Stripe metered subscriptions. What does this module suggest they have taken on?

- **A.** Better security, since keeping billing math in-house avoids sending any usage data to a third party where it could potentially be exposed
- **B.** Improved accuracy, since computing charges in your own code is inherently more precise than delegating the calculation to an external platform
- **C.** Reimplementing billing math that Stripe already handles when reporting usage to metered subscriptions would let the platform do it accurately  ✅
- **D.** Lower latency, since in-code billing avoids the network call to Stripe and therefore returns invoices to customers faster each cycle

> **Answer:** C

### Q21. This module says invoice line items should be legible. What does legibility mean for a line item?

- **A.** The line item is encrypted, since a legible invoice protects the customer's usage detail from anyone who intercepts the billing document
- **B.** The line item is versioned, since a legible invoice notes which API version generated each charge so the customer can audit by release
- **C.** The line item is short, since a legible invoice reduces every charge to a single number so the customer is not overwhelmed by detail
- **D.** The customer can read the invoice and map each charge back to usage they can see, so the bill is not a mystery total they must accept  ✅

> **Answer:** D

### Q22. Credits also support promotions, free-tier allowances, and enterprise commitments. What does this module say a credit system fundamentally tracks?

- **A.** A balance drawn down by usage, decremented in real time, which the customer can see in the dashboard and which must behave correctly at zero  ✅
- **B.** A version number, since credits are issued per API version and each release grants the customer a fresh allowance to spend on that version
- **C.** A key scope, since credits define what a credential is permitted to do and are consumed whenever the key exceeds its granted permissions
- **D.** An SLA percentage, since credits represent the availability owed to a customer and are drawn down whenever the API fails to meet its uptime

> **Answer:** A

### Q23. A team wants to enforce a hard prepaid cap that stops calls the instant a balance hits zero, but they rely on async log aggregation. What conflict does this module surface?

- **A.** Async aggregation overcharges, since delayed counting always tallies more calls than actually occurred and would bill past the cap unfairly
- **B.** Async aggregation leaks keys, since holding calls in a log before counting exposes the credentials attached to each pending request
- **C.** Async aggregation settles usage with a delay, so a hard real-time cap needs synchronous counting the async hot path cannot provide alone  ✅
- **D.** Async aggregation breaks versioning, since logged calls lose their version attribution and the cap cannot tell which version to stop first

> **Answer:** C

### Q24. A customer emails support asking why they were billed for more than they expected, and the team realizes the dashboard never showed near-real-time usage. What does this module say the dashboard should have done?

- **A.** Displayed the pricing page, since the dispute would not have arisen had the customer reviewed the per-call rates before integrating the API
- **B.** Shown near-real-time usage broken down as the bill would be, so the customer could have seen the trend and never needed to open a ticket  ✅
- **C.** Pinned the API version, since usage disputes are resolved by proving every metered call ran against the version the customer signed up under
- **D.** Hidden the detail, since showing less usage information is what prevents customers from questioning the totals on their monthly invoice

> **Answer:** B

### Q25. Looking across everything in this module, what is the governing principle for usage metering and billing?

- **A.** Meter accurately at the right granularity and make the dashboard reconcile to the invoice, because metering errors are trust-destroying billing errors  ✅
- **B.** Count everything synchronously, because real-time accuracy in the request path is the only way to guarantee a customer is never mischarged
- **C.** Delegate all counting to Stripe, because a payment platform should own both the metering and the billing so the API never tracks usage itself
- **D.** Meter as finely as technically possible, because the most detailed usage records always produce the most accurate bills for every customer

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106571047_
