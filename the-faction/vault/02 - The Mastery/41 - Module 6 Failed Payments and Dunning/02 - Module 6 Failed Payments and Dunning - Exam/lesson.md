---
course: "The Mastery"
module: "Module 6: Failed Payments and Dunning"
lesson: "Module 6: Failed Payments and Dunning — Exam"
type: "course_quiz"
post_id: 106562782
space_id: 24191170
source: "https://the-faction.mn.co/posts/106562782"
updated: "2026-08-28T16:13:28Z"
---

# Module 6: Failed Payments and Dunning — Exam

> Exam for **Module 6: Failed Payments and Dunning** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A founder sees renewal failures for the first time and assumes something is broken in the build. What is the accurate framing of why subscription payments fail?

- **A.** Failures are a normal fact of card payments: expirations, thin balances, fraud flags, and bank declines  ✅
- **B.** Failures at renewal almost always indicate an integration defect in how the charge was created
- **C.** Failures mean the customer disputed the renewal, which banks express as a declined payment
- **D.** Failures only occur when a card was entered incorrectly at signup and never validated since

> **Answer:** A

### Q2. One failure category is predictable months in advance and largely preventable. Which is it, and what prevents it?

- **A.** Fraud flags, prevented by lowering Radar's risk threshold for known returning subscribers
- **B.** Card expirations, prevented with pre-expiry outreach and automatic card updater services  ✅
- **C.** Insufficient funds, prevented by charging every customer on the first day of each month
- **D.** Bank declines, prevented by routing renewals through a backup processor automatically

> **Answer:** B

### Q3. A renewal fails with an insufficient funds decline. Why does retry timing matter more than retry count for this category?

- **A.** Banks block repeat attempts within a day, so spacing is required for retries to process at all
- **B.** Each retry costs a processing fee, so fewer well-placed attempts protect the unit economics
- **C.** Balances are often temporarily low so retrying when funds are likely present is what succeeds  ✅
- **D.** Stripe caps retry counts per invoice, so timing is the only variable left to optimize around

> **Answer:** C

### Q4. A card fails with a hard decline, and the retry configuration hammers it daily for two weeks. What is the professional concern with this?

- **A.** Repeatedly retrying hard declines damages your standing with issuers and can hurt future approval rates  ✅
- **B.** Hard declines convert at the same rate as soft ones, so the only cost is the wasted retry fees
- **C.** Daily retries reset the dunning email sequence each time, spamming the customer with notices
- **D.** Stripe suspends accounts that exceed a fixed monthly retry quota across their whole volume

> **Answer:** A

### Q5. A teammate asks the difference between voluntary and involuntary churn and why the distinction matters. What is accurate?

- **A.** Voluntary churn is cancellations you approve, involuntary is cancellations customers force through on their own
- **B.** The terms distinguish annual from monthly cancellations for revenue forecasting purposes and planning
- **C.** Voluntary churn happens in the portal, involuntary happens over support tickets and email threads
- **D.** Voluntary is a customer choosing to leave; involuntary is a payment failing under someone who meant to stay  ✅

> **Answer:** D

### Q6. A team sees churn climbing and launches a product overhaul. Later they discover most of it was failed payments. What went wrong in their diagnosis?

- **A.** They trusted dashboard churn numbers, which exclude payment failures from every churn metric they report
- **B.** They mixed involuntary churn into one number, hiding an infrastructure problem inside a product story  ✅
- **C.** They measured churn monthly instead of weekly, smoothing out the payment failure signal entirely
- **D.** They counted paused subscriptions as churned, inflating the number the overhaul responded to

> **Answer:** B

### Q7. A builder asks what Smart Retries actually do differently from a fixed schedule. What is the mechanism?

- **A.** They retry hourly until success, maximizing attempts inside the invoice's collection window period
- **B.** They escalate each failure to a human review queue that decides when to attempt again
- **C.** They use machine learning across Stripe's network to pick retry moments most likely to succeed  ✅
- **D.** They rotate retries across backup payment methods the customer saved during registration

> **Answer:** C

### Q8. A founder asks whether to direct AI to configure Smart Retries or build a custom day 1, 3, 5, 7 schedule. What is the professional default and why?

- **A.** Smart Retries, because network-informed timing outperforms naive fixed schedules for most businesses  ✅
- **B.** The custom schedule, because owning retry logic keeps the recovery system fully auditable
- **C.** Both simultaneously, because parallel retry systems maximize the total attempt coverage
- **D.** Neither at first, because retries should stay off until the dunning emails prove themselves

> **Answer:** A

### Q9. Retries are configured, but nobody decided what happens when the final retry fails. What decision is missing, and what are the options?

- **A.** The refund policy: whether the failed period is refunded, credited, or written off entirely
- **B.** The escalation contact: which team member is paged when an invoice exhausts its retries
- **C.** The blocklist policy: whether customers with exhausted retries can ever resubscribe again
- **D.** The end-of-retries action: cancel the subscription, mark it unpaid, or leave it past_due  ✅

> **Answer:** D

### Q10. A builder is directing the dunning email sequence. What is the correct structural arc across the sequence?

- **A.** A single firm notice at first failure, since repetition trains customers to ignore billing email entirely
- **B.** Soft assume-error first, escalating clarity as retries continue, ending with consequence and date  ✅
- **C.** Legal-toned notices from the start, since payment communications carry contractual weight
- **D.** Silence until the final retry fails, since most failures recover without any email at all

> **Answer:** B

### Q11. A draft dunning email opens with: your account is delinquent and service will be terminated. What is the professional critique?

- **A.** The tone treats a card problem as a character problem; write like you are helping them stay, not collecting  ✅
- **B.** The threat is premature only if retries remain; once retries exhaust, this tone becomes correct and fully earned
- **C.** The message is fine; payment emails should be maximally direct to drive immediate action from readers
- **D.** The word delinquent has legal implications that require sign-off before it can be sent out at all

> **Answer:** A

### Q12. A dunning sequence has strong open rates but weak recovery. Reviewing the emails, what is the single most important element to check first?

- **A.** Send times, since payment emails opened outside business hours rarely convert to action
- **B.** Subject line urgency, since soft subjects suppress the click behavior recovery depends on heavily
- **C.** Whether every email links directly to a one-click payment method update in the Billing Portal  ✅
- **D.** Personalization depth, since unpersonalized billing emails read as spam to most customers

> **Answer:** C

### Q13. A founder asks why she should build her own dunning emails when Stripe can send failure notices automatically. What is the honest tradeoff?

- **A.** Stripe's emails are deliverability-optimized, so custom sequences trade recovery for branding
- **B.** Stripe's notices only cover the first failure, so custom sequences exist to handle retries
- **C.** There is none; Stripe's built-in notices match custom sequences on every dimension that matters today
- **D.** Stripe covers the basics; your own sequence gives you tone, timing, and branding Stripe's cannot  ✅

> **Answer:** D

### Q14. A teammate asks what a grace period is actually for, since the customer has already failed to pay. What is the reasoning?

- **A.** It keeps a recoverable customer whole while retries and emails work, instead of punishing a bank hiccup  ✅
- **B.** It satisfies card network rules that require notice before any recurring service interruption
- **C.** It buys the business time to verify the failure was real before touching customer access
- **D.** It postpones the accounting recognition of the failure until the next reporting period closes

> **Answer:** A

### Q15. A subscription is past_due with a fourteen-day grace window configured. On day five, what access does the customer have?

- **A.** Read-only access, with full service restored the moment any retry succeeds during the window itself
- **B.** Normal access, because grace means service continues while the recovery process runs its course  ✅
- **C.** No access, because grace refers to the retry window rather than any service continuation
- **D.** Access to billing pages only, so the customer can fix payment but not use the product itself

> **Answer:** B

### Q16. A builder is asked to recite the recovery waterfall in order before directing the build. Which sequence is correct?

- **A.** Notify, cancel, retry, escalate, suspend, keeping communication ahead of every system action
- **B.** Suspend, retry, notify, escalate, cancel, protecting the business before recovery attempts start
- **C.** Retry, notify, escalate, suspend, cancel, each stage giving recovery a chance before the next  ✅
- **D.** Escalate, notify, retry, cancel, suspend, ordered by the cost each stage imposes on the customer

> **Answer:** C

### Q17. A business revokes access the moment any renewal fails. What predictable outcome does this policy produce?

- **A.** Higher recovery rates, since losing access is the strongest motivation to fix a payment fast of all
- **B.** Lower fraud exposure, since failed payers lose the window where unpaid usage accumulates
- **C.** No measurable change, since access policy and payment recovery are independent systems
- **D.** Recoverable customers turned into angry cancellations over what was often a temporary bank issue  ✅

> **Answer:** D

### Q18. A founder asks for the single number that tells her whether the recovery system works. What is it and how is it computed?

- **A.** Recovery rate: of payments that failed, the percentage ultimately collected by the waterfall  ✅
- **B.** Retry velocity: the average number of attempts completed per failed invoice per week of recovery
- **C.** Dunning open rate: the percentage of failure emails opened within the grace window
- **D.** Churn delta: the month-over-month change in total cancellations across all causes

> **Answer:** A

### Q19. Analysis shows nearly all recoveries happen on the second retry, before any email is opened. What does this suggest about the system?

- **A.** The retry schedule is too slow, since recoveries should concentrate on the first attempt in practice
- **B.** The emails may be decoration; test whether the sequence adds recovery beyond what retries deliver  ✅
- **C.** The grace period is too long, since recovered customers never approached its boundary
- **D.** The sequence is perfectly tuned, since silent recovery is the ideal customer experience

> **Answer:** B

### Q20. Recovery data shows a spike of payments fixed immediately after the final notice, with few before it. What is the diagnosis?

- **A.** The final notice is too aggressive, converting through fear rather than genuine intention
- **B.** The retry schedule ends too early, forcing the final notice to do the retries' actual work
- **C.** Customers game the grace window, a behavior more grace period length would only reward
- **D.** The earlier emails are too soft to drive action, leaving the deadline to do all the work  ✅

> **Answer:** D

### Q21. A business wants to reduce failures before they happen rather than recover after. Which lever targets the largest preventable category?

- **A.** Requiring two payment methods at signup so a backup exists whenever the primary fails
- **B.** Switching every customer to annual billing, cutting renewal events by a factor of twelve
- **C.** Card updater services plus pre-expiry outreach, so expiring cards are replaced before renewals fail  ✅
- **D.** Charging one dollar authorizations monthly to verify every stored card stays chargeable

> **Answer:** C

### Q22. A builder asks which event actually starts the dunning machinery when a renewal fails. What do you direct the sequence to hang off?

- **A.** The invoice.payment_failed webhook, which fires the sequence and marks the recovery clock's start  ✅
- **B.** The customer.subscription.deleted webhook, which confirms the failure ended the subscription
- **C.** A daily database scan for subscriptions whose renewal date passed without a matching payment record
- **D.** The charge.refunded webhook, which distinguishes failures from customer-initiated reversals

> **Answer:** A

### Q23. A renewal fails with a generic do-not-honor decline code. A teammate asks what the bank is actually communicating. What is accurate?

- **A.** The card was reported stolen, and any further attempts will be flagged as fraudulent activity
- **B.** The account lacks funds specifically, since do-not-honor is the standard insufficient balance code
- **C.** The issuer declined without explaining; it is the bank saying no while withholding the reason  ✅
- **D.** The customer configured a block on recurring charges, which only they can lift with the bank

> **Answer:** C

### Q24. A founder wants a sixty-day grace period to be maximally customer-friendly. What is the balancing consideration you raise?

- **A.** Long grace periods reset the retry schedule repeatedly, multiplying processing fees per failure
- **B.** Grace length trades recovery room against free riding; it should fit how long recovery realistically takes  ✅
- **C.** Stripe caps grace periods at thirty days, so the configuration cannot exceed that ceiling
- **D.** Grace periods beyond a billing cycle convert the failed period into legally uncollectable debt

> **Answer:** B

### Q25. Looking across everything in this module, what is the governing principle for failed payments and dunning?

- **A.** Treat every failure as churn immediately, because clean metrics matter more than marginal recovery
- **B.** Maximize retry aggression, because every attempt is a lottery ticket on recovering the payment
- **C.** Keep recovery invisible to customers, because any mention of payment trouble damages the brand
- **D.** Recovery is respectful infrastructure: a tuned waterfall that wins back revenue you have earned  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/106562782_
