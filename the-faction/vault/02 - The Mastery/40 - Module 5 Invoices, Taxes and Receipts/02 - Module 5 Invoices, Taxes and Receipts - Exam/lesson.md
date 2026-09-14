---
course: "The Mastery"
module: "Module 5: Invoices, Taxes and Receipts"
lesson: "Module 5: Invoices, Taxes and Receipts — Exam"
type: "course_quiz"
post_id: 106562778
space_id: 24191170
source: "https://the-faction.mn.co/posts/106562778"
updated: "2026-08-28T16:12:41Z"
---

# Module 5: Invoices, Taxes and Receipts — Exam

> Exam for **Module 5: Invoices, Taxes and Receipts** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder creates an invoice and asks why it can still be freely edited, when she expected a locked legal document. What explains the behavior?

- **A.** The account is in test mode, where invoices stay editable until the live switch locks them all
- **B.** Invoices remain editable until first payment, at which point Stripe freezes the full record
- **C.** It is still a draft; invoices become locked, numbered documents only when they are finalized  ✅
- **D.** Editing stays open for thirty days by default, a window configured in the invoice settings

> **Answer:** C

### Q2. A teammate asks how subscription renewal invoices actually get paid each cycle without anyone doing anything. Which collection method is at work?

- **A.** charge_automatically, which bills the customer's stored payment method when the invoice is due  ✅
- **B.** send_invoice, which emails the customer a payment link that must be clicked before each cycle runs
- **C.** auto_settle, which draws from the customer's Stripe balance that top-ups keep replenished
- **D.** direct_debit, which is mandatory for any recurring invoice regardless of stored card details

> **Answer:** A

### Q3. A consulting firm bills corporate clients who route payments through accounts payable departments with net-30 terms. Which collection setup fits this business?

- **A.** charge_automatically with a stored corporate card, since automation always beats manual payment
- **B.** A recurring subscription with monthly cycles, since consulting revenue repeats like a SaaS plan
- **C.** send_invoice with a due date, emailing a hosted invoice page the AP department can pay from  ✅
- **D.** Payment Links sent over email, since hosted checkout pages replace formal invoicing entirely

> **Answer:** C

### Q4. A finalized invoice went out with the wrong amount. The founder wants to just edit the number and resend it. What do you direct instead?

- **A.** Unfinalize the invoice in the dashboard, correct the amount, and refinalize under the same number
- **B.** Issue a credit note against the invoice, since finalized documents are corrected, never edited  ✅
- **C.** Delete the invoice entirely and issue a fresh one, since deletion removes the numbering conflict
- **D.** Edit the amount through the API, which bypasses the dashboard's finalization lock cleanly

> **Answer:** B

### Q5. A builder handling only subscriptions asks whether this module even applies to her product. What is the structural connection?

- **A.** It does not apply; subscription payments are charges, and invoices exist only for B2B billing work
- **B.** It applies only if customers request receipts, which converts a charge into an invoice record
- **C.** It applies at year end, when Stripe consolidates subscription charges into annual invoices
- **D.** Every subscription renewal is an invoice under the hood, so invoice mechanics govern her revenue  ✅

> **Answer:** D

### Q6. A service business needs to bill a client for a project deposit before work starts, outside any subscription. What do you direct AI to create?

- **A.** A standalone invoice with a custom line item for the deposit, keeping one paper trail for all revenue  ✅
- **B.** A one-cycle subscription at the deposit amount, canceled automatically after the first payment
- **C.** A manual bank transfer request over email, since deposits fall outside payment processor scope
- **D.** A negative credit note that the final invoice will offset once the project work is completed

> **Answer:** A

### Q7. A founder asks what Stripe Tax actually uses to compute the right tax on each transaction. What are the core inputs?

- **A.** The account's home state rate, applied uniformly to every sale regardless of buyer location
- **B.** The product's tax code and the customer's location, which together determine the treatment  ✅
- **C.** A flat rate the business configures once, which Stripe applies until it is manually updated
- **D.** The card's issuing bank country, which proxies for the buyer's tax residence automatically

> **Answer:** B

### Q8. A growing business sells into many US states and several countries. The founder asks how she will know where tax obligations are approaching. What does Stripe Tax provide?

- **A.** Nothing; obligation tracking is left entirely to that business's accountant to monitor manually
- **B.** Automatic registration in every jurisdiction the moment the first sale lands there each year
- **C.** Threshold monitoring that shows where sales are approaching registration obligations by region  ✅
- **D.** A quarterly letter from Stripe's compliance team summarizing new obligations by jurisdiction

> **Answer:** C

### Q9. During an audit you find every product in a catalog uses one generic tax code, though the business sells software, services, and physical goods. Why is this a finding?

- **A.** Different offerings carry different tax treatment, so one generic code produces wrong tax on real sales  ✅
- **B.** Generic codes are deprecated, and Stripe will begin rejecting transactions that still carry them
- **C.** Tax codes drive dashboard revenue grouping, so reporting is the only thing actually affected here
- **D.** Mixed catalogs require a separate Stripe account per product category under card network rules

> **Answer:** A

### Q10. A European B2B customer asks why your invoice must show their VAT number for cross-border reverse charge treatment to apply. What is the underlying mechanism?

- **A.** The VAT number activates a discount tier that offsets the tax amount on qualifying invoices
- **B.** Displaying the number is a courtesy convention with no actual bearing on the tax treatment
- **C.** The number lets Stripe deduct tax at source and remit it to the customer's home tax authority
- **D.** Reverse charge shifts tax responsibility to the buyer, which requires their tax ID collected and shown  ✅

> **Answer:** D

### Q11. A teammate asks the practical difference between tax-inclusive and tax-exclusive pricing before configuring the catalog. What is it?

- **A.** Inclusive applies to consumers and exclusive to businesses, assigned automatically per customer
- **B.** Exclusive adds tax on top of the displayed price at checkout; inclusive contains it within the price  ✅
- **C.** Inclusive prices settle faster because the tax portion skips the standard clearing process
- **D.** They differ only in invoice formatting, since the charged total is identical either way

> **Answer:** B

### Q12. A US company launching a consumer product in Germany plans to keep showing exclusive prices with tax added at checkout. What outcome should you warn about?

- **A.** German banks decline exclusive-priced transactions, since local rules require inclusive amounts
- **B.** Nothing changes, because European checkout flows convert display pricing automatically anyway
- **C.** European consumers expect inclusive prices, so the checkout surprise reads as bait-and-switch  ✅
- **D.** The business pays the VAT itself on top of the price, cutting margin on every German sale

> **Answer:** C

### Q13. A customer asks for a receipt, and separately the accounting team asks about invoices. A builder asks whether these are the same document. What is accurate?

- **A.** No; an invoice requests and records a billing, while a receipt confirms a payment happened  ✅
- **B.** Yes; receipt is simply the consumer-facing name for the invoice PDF that Stripe generates
- **C.** No; receipts exist only for one-time charges, and subscription customers get neither document
- **D.** Yes, once paid; an unpaid invoice becomes a receipt the moment its payment fully settles

> **Answer:** A

### Q14. A teammate asks what a credit note actually does in the books, beyond being paperwork attached to a refund. What is its function?

- **A.** It transfers the refunded amount into a customer credit balance that future invoices draw down
- **B.** It voids the original invoice entirely, removing it from revenue reports as if never issued
- **C.** It flags the customer record for review so future invoices require an extra approval step
- **D.** It documents the reduction against the original invoice so revenue records stay reconcilable  ✅

> **Answer:** D

### Q15. A finance review finds refunds issued through the dashboard with no corresponding credit notes. What problem has this created?

- **A.** The refunds failed silently, since dashboard refunds require credit notes to actually process
- **B.** Invoice totals no longer match money movements, so the books cannot be reconciled cleanly  ✅
- **C.** Customers were refunded twice, once by the dashboard and once by the missing credit notes
- **D.** Stripe's fees on those refunds went unrecorded, understating costs in the monthly summary

> **Answer:** B

### Q16. A client receiving a send_invoice email clicks through to pay. What experience is on the other side of that link?

- **A.** A hosted invoice page showing the document with online payment options the client can use directly  ✅
- **B.** A PDF download of the invoice with the business's bank wire details listed for manual transfer offline
- **C.** A login wall for a Stripe account the client must create before any payment can be attempted
- **D.** A checkout session for a product named after the invoice, created fresh for each payment click

> **Answer:** A

### Q17. A founder assumes that enabling Stripe Tax means Stripe now handles her tax registrations and filings everywhere she sells. What is the accurate division of responsibility?

- **A.** Stripe assumes full liability for registration, filing, and remittance once the feature is enabled
- **B.** Stripe registers automatically but the business files returns, splitting the compliance burden
- **C.** Stripe calculates and monitors; registering and remitting remain obligations the business owns  ✅
- **D.** Tax authorities bill Stripe directly for merchant obligations, removing the business entirely

> **Answer:** C

### Q18. A builder asks why finalization assigns an invoice number and why that matters beyond tidiness. What is the significance?

- **A.** The number is a routing key for Stripe's internal settlement and has no external meaning
- **B.** Numbers exist so customers can reference invoices in support tickets more conveniently
- **C.** Numbering is optional branding; sequential numbers simply look more professional to clients
- **D.** The number makes it a sequential legal document that accountants and auditors can rely on  ✅

> **Answer:** D

### Q19. A junior teammate asks for the one rule about changing invoices after finalization. What is the discipline this module teaches?

- **A.** No post-finalization edits, ever; corrections happen through credit notes so the trail stays intact  ✅
- **B.** Edits are fine within the same tax period, since reporting only snapshots at period close
- **C.** Edits are allowed for amounts under a materiality threshold the business sets in advance
- **D.** Edits are fine if the customer approves in writing before the corrected version is reissued

> **Answer:** A

### Q20. A business using inclusive pricing notices net revenue per sale varies by customer country. The price displayed never changed. What explains this?

- **A.** Currency conversion fees differ by country and are deducted before revenue is recorded
- **B.** With inclusive pricing, the tax inside the fixed price varies by buyer, so the net remainder varies too  ✅
- **C.** Stripe's processing rates differ per country, shifting the net independently of any tax math
- **D.** Some countries round displayed prices to local conventions, changing the collected amount

> **Answer:** B

### Q21. An AP department routinely pays send_invoice bills late. The founder asks what Stripe Invoicing offers before anyone writes custom code. What is built in?

- **A.** Automatic collections referral after sixty days, escalating unpaid invoices to a partner agency
- **B.** Late fees compounding daily, applied automatically to any invoice past its stated due date
- **C.** Due dates with automatic reminder emails, and visibility into which invoices remain unpaid  ✅
- **D.** Automatic cancellation of overdue invoices, forcing a fresh billing cycle and clean restart

> **Answer:** C

### Q22. A builder asks what actually changes at the moment an invoice is finalized. What is the precise transition?

- **A.** The invoice converts to a receipt and is emailed to every contact on the customer record
- **B.** Payment is attempted immediately, regardless of which collection method was configured
- **C.** The customer gains dashboard access to view the invoice alongside their payment history going forward
- **D.** The draft locks against edits, receives its number, and becomes collectible as a real document  ✅

> **Answer:** D

### Q23. A consulting invoice needs three lines: discovery work, build hours, and a discount. The builder asks whether invoices support this without a product catalog. What is accurate?

- **A.** Invoices accept custom line items directly, so bespoke billing does not require catalog objects  ✅
- **B.** Every line must reference a cataloged price, so three products must be created beforehand
- **C.** Invoices carry a single total only; line detail belongs in an attached PDF the business writes itself
- **D.** Line items are subscription-only; standalone invoices bill one description and one amount

> **Answer:** A

### Q24. A teammate asks why the US market default is exclusive pricing when much of the world expects inclusive. What is the practical reason?

- **A.** US processors add tax at settlement, so displayed prices cannot legally include it upfront anywhere
- **B.** US sales tax varies by state and locality, so a single inclusive price cannot fit every buyer  ✅
- **C.** Card networks mandate exclusive display in North America under their merchant agreements
- **D.** Inclusive pricing is taxed at a penalty rate federally, making it uneconomical to offer

> **Answer:** B

### Q25. Looking across everything in this module, what is the governing principle for invoices, taxes, and receipts?

- **A.** Keep paperwork manual and human-reviewed, because automation is where billing errors creep in
- **B.** Minimize documentation to what customers demand, because unused paperwork is pure overhead
- **C.** Route all tax questions to Stripe support, because the platform owns compliance end to end
- **D.** Make the paper trail automatic and untouchable so the documents always match the money moved  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/106562778_
