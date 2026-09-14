---
course: "The Mastery"
module: "Module 2 — Payments & Billing Engine"
lesson: "Module 02: Subscription Endpoints & Webhooks — Exam"
type: "course_quiz"
post_id: 103821113
space_id: 24191170
source: "https://the-faction.mn.co/posts/103821113"
updated: "2026-08-21T14:39:55Z"
---

# Module 02: Subscription Endpoints & Webhooks — Exam

> Exam for **Module 2 — Payments & Billing Engine** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your webhook handler processes events correctly but always returns a 200 status code — even when processing fails internally. What problem does this create?

- **A.** No problem — 200 is the correct response for every webhook regardless of what happened
- **B.** Stripe thinks delivery succeeded and won't retry, so failed events are silently lost forever  ✅
- **C.** Stripe will interpret the 200 and send the next event faster than the previous delivery speed
- **D.** The 200 response causes Stripe to attempt charging the customer's payment method a second time

> **Answer:** B

### Q2. A developer on your team pushes code that includes the Stripe secret key directly in the frontend JavaScript bundle. What is the immediate risk?

- **A.** No real risk — Stripe keys are fully encrypted in transit so exposure isn't a concern
- **B.** The frontend needs the secret key to process payments and complete Stripe checkout sessions
- **C.** Anyone who views your page source can extract the key and access your full Stripe account  ✅
- **D.** Stripe will automatically rotate the key if it detects it has been publicly exposed anywhere

> **Answer:** C

### Q3. Your upgrade endpoint charges the price difference when moving Basic to Pro mid-cycle but does not update the plan in your database until next billing. What is the result?

- **A.** The customer is satisfied because the charge processed and they see the confirmation on file
- **B.** This is correct behavior — plan changes should only take effect at the start of the next billing cycle
- **C.** The customer paid for Pro but still sees Basic features — they paid for something they can't use  ✅
- **D.** The charge should also be deferred to the next billing cycle instead of being collected immediately

> **Answer:** C

### Q4. Your app has no webhook. It only checks Stripe when a user loads billing. A payment fails day 1 but the customer visits billing on day 15. What happened during those 14 days?

- **A.** Your system had no idea the payment failed — no grace period or user notification was triggered  ✅
- **B.** Stripe automatically handled the failed payment so the subscription stays in a perfectly fine state
- **C.** The customer was automatically downgraded a tier by Stripe's built-in failure handling
- **D.** The payment failure resolved itself through Stripe's automatic retry without needing intervention

> **Answer:** A

### Q5. Your subscription API has create, cancel, and get-status endpoints. A customer wants to switch from Pro monthly to Pro annual. There is no endpoint for this. What is missing?

- **A.** Nothing — the customer should cancel the monthly plan and buy the annual plan as a new signup
- **B.** An update-subscription endpoint that switches plans while preserving the billing relationship  ✅
- **C.** A support workflow where staff manually edit the subscription record in the Stripe dashboard
- **D.** A second create endpoint dedicated to annual plans so both plan types can coexist in the system

> **Answer:** B

### Q6. Your trial is 14 days. On day 14 the trial expires but your system does not prompt for payment or change the subscription status. The customer keeps using the product free. What is broken?

- **A.** This is fine — Stripe will eventually handle the trial expiration without any action from your side
- **B.** Trial expirations should be handled manually by the support team rather than through automation
- **C.** Your webhook handler isn't processing the subscription.updated event that fires when a trial ends  ✅
- **D.** The customer should be immediately locked out of their account on day 14 of their trial period

> **Answer:** C

### Q7. Your API returns a 500 Internal Server Error when a payment fails. The customer sees 'Something went wrong' with no further detail. What should the response look like instead?

- **A.** 500 errors are technically the appropriate responses for any payment-related failure in your system
- **B.** A 402 Payment Required with a clear message explaining the failure and how to update payment  ✅
- **C.** A 200 success response with an error field in the JSON body describing what went wrong
- **D.** A redirect to the Stripe-hosted payment page so they can resolve the issue on their own terms

> **Answer:** B

### Q8. Your metered billing reports 8,247 API calls but the customer claims 2,000. Your logs show the count includes internal health checks on their API key. What went wrong?

- **A.** The customer is wrong — every API call including health checks should count toward their usage limit
- **B.** Metered billing is too complicated to implement and should be replaced with a flat rate
- **C.** Health checks should use the customer's API key for accurate monitoring and consistent tracking
- **D.** Usage metering counted internal health checks alongside actual usage — billing needs filtering  ✅

> **Answer:** D

### Q9. Your downgrade revokes Pro features immediately even though the customer paid through month end. But cancellations grant access until period end. What is the inconsistency?

- **A.** Downgrades and cancellations should behave the same — access continues until the period ends  ✅
- **B.** Downgrade access should be reduced immediately — the customer chose a lower plan, so apply it now
- **C.** The system should prorate a refund at the downgrade and cut access to premium features
- **D.** Premium features should stay available forever — the customer already paid so the access was earned

> **Answer:** A

### Q10. Your endpoint creates a Stripe subscription but stores nothing in your own database. During a 30-minute Stripe outage your app cannot check any customer's plan. What is the fix?

- **A.** Stripe outages are rare enough that building resilience for them isn't worth the engineering effort
- **B.** Store subscription status locally and sync via webhooks — so your app works if Stripe is down  ✅
- **C.** Cache Stripe API responses with a 24-hour TTL to handle temporary availability issues
- **D.** Build a backup payment processor integration that automatically activates when Stripe is unavailable

> **Answer:** B

### Q11. A customer tries a free trial without entering payment. On day 14 it expires. Your system requests payment which fails. The customer gets a failed payment email. What is wrong?

- **A.** The error email is an appropriate notification — it clearly tells them to add a valid payment method
- **B.** The trial should extend itself until the customer adds a valid payment method on file
- **C.** Stripe should require a valid payment method at signup for all trial subscriptions automatically now
- **D.** Trial-to-paid conversion should prompt for payment before charging — not attempt a failing charge  ✅

> **Answer:** D

### Q12. Your billing page has a Cancel Subscription button that immediately calls Stripe to cancel — no confirmation, no explanation, no retention offer. What is missing?

- **A.** Immediate cancellation is the most user-friendly approach since it respects the user's decision
- **B.** A confirmation step explaining what happens — access until period end, data retention — plus offers  ✅
- **C.** The cancel button should be hidden or hard to find in order to reduce the overall customer churn rate
- **D.** Cancellation should require contacting support directly so the retention team can attempt to save them

> **Answer:** B

### Q13. Your app charges $49/month for Pro. A customer upgrades from Basic $19 to Pro on day 15 of a 30-day cycle. Your endpoint charges the full $49 immediately. What should the charge be?

- **A.** $49 is correct — they're upgrading to the full Pro plan so they owe the complete monthly amount
- **B.** $30 — just the difference between Pro and Basic pricing for the full monthly billing cycle amount
- **C.** The upgrade should be completely free until the next billing cycle starts at the regular interval
- **D.** A prorated charge for the remaining 15 days plus the full $49 Pro charge starting the next cycle  ✅

> **Answer:** D

### Q14. Your webhook gets invoice.payment_failed and immediately sets the subscription to canceled. Three hours later Stripe's auto-retry succeeds but your app still shows canceled. What went wrong?

- **A.** The customer should create a brand new subscription since the original payment failed and was canceled
- **B.** The webhook handler should ignore payment_failed events and let Stripe manage retry logic
- **C.** Stripe shouldn't retry failed payments without getting explicit customer approval for each attempt made
- **D.** First failure sets 'past_due' with a grace period — not 'canceled' — and retry restores 'active'  ✅

> **Answer:** D

### Q15. Your API has create, read, and cancel subscription endpoints but no way to retrieve invoice history. Enterprise customers need invoices for accounting. What should you add?

- **A.** An endpoint that retrieves invoice history from Stripe and returns it in a format your UI displays  ✅
- **B.** Direct customers to the Stripe-hosted portal whenever they want to view their invoices
- **C.** Send monthly invoice summary emails to customers and don't worry about building in-app invoice access
- **D.** Invoice history is a nice-to-have feature, not a hard requirement for launching the billing system now

> **Answer:** A

### Q16. Your create-subscription endpoint accepts a coupon code but does not validate it before applying. An invalid coupon causes the entire subscription to fail. What should happen?

- **A.** The error is correct behavior — invalid coupons should always prevent new subscription creation entirely
- **B.** Coupons should be applied after the subscription is created, not validated during signup
- **C.** Accept any coupon code the user enters and let Stripe sort out validity during subscription creation now
- **D.** Validate the coupon with Stripe before creating the subscription and return a clear error if expired  ✅

> **Answer:** D

### Q17. Your webhook is a single handler processing all Stripe event types in one function with a long if/else chain now at 400 lines. What is the better architecture?

- **A.** Long functions are perfectly fine as long as they work correctly and handle all the necessary events
- **B.** Create a separate webhook URL for each event type so Stripe sends them to different endpoint routes
- **C.** Route each event type to a dedicated handler — payment events to one, subscription events to another  ✅
- **D.** Use Stripe's built-in event processing system so you don't need a custom handler for each event type

> **Answer:** C

### Q18. A customer's credit card expires. Stripe sends customer.source.expiring but your system ignores it. The next charge fails and the customer is surprised. What should your system have done?

- **A.** Card expiration is entirely the customer's responsibility — your platform shouldn't need to get involved
- **B.** Automatically switch to their backup payment method without notifying the customer at all
- **C.** Notify the customer that their card is expiring soon and prompt them to update payment details  ✅
- **D.** Extend their current billing cycle until they notice the issue and update the expired card themselves

> **Answer:** C

### Q19. Your subscription API handles individual accounts. A company wants 25 seats. Your API has no concept of seat-based billing — only one subscription per customer. What is missing?

- **A.** Your subscription model needs to support organization-level billing with variable seat counts  ✅
- **B.** Seat-based billing isn't common enough to justify building dedicated support for it in your system
- **C.** The company should create 25 separate subscriptions — one for each user on their team
- **D.** Add a 'quantity' field to the existing individual subscription endpoint to handle multiple user seats

> **Answer:** A

### Q20. Your Stripe webhook receives payment_intent.succeeded and credits the account. Five minutes later the same event arrives again via retry. What happens if you do not handle this?

- **A.** The customer gets credited twice, resulting in a double charge or double service allocation  ✅
- **B.** Nothing — Stripe never sends the same event twice so duplicates aren't a real concern here
- **C.** Stripe automatically prevents duplicate processing on your behalf without any extra handling
- **D.** The second event will fail because the payment was already processed and marked as complete

> **Answer:** A

### Q21. A customer cancels their subscription. Your cancellation endpoint removes their access immediately even though they paid for the full month and still have 18 days remaining. What's wrong?

- **A.** Immediate cancellation is standard SaaS practice and users expect their access to stop right away
- **B.** Access should continue until the billing period ends — the customer already paid for those 18 days  ✅
- **C.** The customer should receive a prorated refund for the remaining days on their current billing cycle
- **D.** Cancellation should require a mandatory 30-day notice period before it takes effect on the account

> **Answer:** B

### Q22. Your webhook receives subscription.deleted and deletes the customer's entire database record — projects, files, history — all gone. The customer calls furious. What should have happened?

- **A.** Deletion is correct — they cancelled their plan, so all of their associated data should be removed
- **B.** Store a full backup of customer data before deletion so it can be restored if they change their mind
- **C.** Ask the customer to confirm deletion via email before proceeding with any data removal operations
- **D.** Mark the subscription as canceled and retain data for a grace period — don't delete on cancellation  ✅

> **Answer:** D

### Q23. Your webhook endpoint accepts any POST request and processes it as a Stripe event without verification. What security vulnerability does this create?

- **A.** Anyone who discovers the URL can send fake events like fake payment confirmations to your system  ✅
- **B.** No vulnerability — only Stripe knows the webhook URL so no outside party could ever reach it
- **C.** The URL is protected by HTTPS encryption so it's already fully secure against unauthorized access
- **D.** Stripe only sends events from whitelisted IP addresses so no additional verification is needed

> **Answer:** A

### Q24. You hardcode Stripe plan IDs in your endpoint: price_1ABC123 for Basic, price_1DEF456 for Pro. You create an Enterprise plan in Stripe. What must you do to make it available?

- **A.** Stripe automatically adds new plans to your application without any changes needed on your end
- **B.** Hardcoded plan IDs are the recommended approach for long-term reliability and type-safe references
- **C.** You have to modify the code and redeploy — plan IDs should come from a config or database instead  ✅
- **D.** Build a new endpoint specifically for the Enterprise plan separate from the existing subscription flow

> **Answer:** C

### Q25. Your webhook handler validates the event, updates the database, and sends an email — all synchronously. The email takes 8 seconds. Stripe times out and retries. What should change?

- **A.** Return 200 immediately after validation, then process the event asynchronously in a background job  ✅
- **B.** Ask Stripe to increase the timeout limit for webhook delivery to your specific application endpoint
- **C.** Remove the email notification from the webhook processing flow entirely to speed up response time
- **D.** The 8-second response time is within acceptable limits for webhook processing in most situations

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/103821113_
