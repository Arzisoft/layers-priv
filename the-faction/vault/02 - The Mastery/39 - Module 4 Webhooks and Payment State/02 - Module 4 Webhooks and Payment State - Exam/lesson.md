---
course: "The Mastery"
module: "Module 4: Webhooks and Payment State"
lesson: "Module 4: Webhooks and Payment State — Exam"
type: "course_quiz"
post_id: 106562775
space_id: 24191170
source: "https://the-faction.mn.co/posts/106562775"
updated: "2026-08-28T16:11:44Z"
---

# Module 4: Webhooks and Payment State — Exam

> Exam for **Module 4: Webhooks and Payment State** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A subscription renews at 3 AM while no customer is browsing the site. A builder asks how the application will ever find out this happened. What is the structural answer?

- **A.** Stripe sends a signed webhook event to the endpoint, which is why webhooks are the source of truth  ✅
- **B.** The customer's next login triggers a status check that discovers the renewal after the fact quietly
- **C.** Stripe emails the account owner a renewal digest, which an automation parses into the database
- **D.** The application polls the subscriptions endpoint hourly, which is the supported discovery pattern

> **Answer:** A

### Q2. A webhook endpoint accepts events without verifying signatures. A security reviewer flags it as critical. What can an attacker actually do?

- **A.** Read the payment history of any customer by replaying old event IDs against the open endpoint
- **B.** Redirect settlement funds to their own bank by injecting payout events into the handler's queue
- **C.** Extract the endpoint's signing secret by sending malformed events and reading the error output
- **D.** Send forged events, such as a fake completed checkout, and grant themselves paid access for free  ✅

> **Answer:** D

### Q3. Signature verification keeps failing on valid Stripe events. The framework parses JSON bodies automatically before the handler runs. What is the likely cause?

- **A.** The endpoint URL contains a query string, which Stripe includes in its signature computation step
- **B.** Verification is running against a parsed and re-serialized body instead of the raw request bytes  ✅
- **C.** The signing secret rotated automatically, and the handler is still holding the previous value
- **D.** The events are arriving compressed, and signatures only match the uncompressed payload form

> **Answer:** B

### Q4. A checkout.session.completed event arrives for a session with your order ID in its metadata. What is the correct business response to this event?

- **A.** Wait for the corresponding charge.settled event before releasing anything of value to the buyer
- **B.** Send a payment reminder, since session completion means checkout opened but payment is pending
- **C.** Match it to the internal order and fulfill, since the customer has finished paying for that session  ✅
- **D.** Archive the session, since completion events are informational and fulfillment keys off invoices only

> **Answer:** C

### Q5. An invoice.paid event arrives for a subscription customer. What does this event mean and what should the handler do?

- **A.** A recurring payment succeeded so extend the customer's access for the period the invoice covers  ✅
- **B.** An invoice was generated and is awaiting payment, so notify the customer that a charge is coming
- **C.** A one-time purchase completed, so this event can be ignored in a subscription-only application
- **D.** The customer manually paid a past-due balance, so a support follow-up task should be created

> **Answer:** A

### Q6. An invoice.payment_failed event arrives for an active subscriber. A junior builder's handler immediately revokes access. What is the correct handling instead?

- **A.** Cancel the subscription on the spot, since failed payments indicate the customer has churned
- **B.** Ignore the event entirely, since Stripe's retries make application-level responses redundant here
- **C.** Refund the most recent successful invoice so the account balances cleanly before suspension
- **D.** Keep access on, begin the recovery path, and let dunning and retries work before any revocation  ✅

> **Answer:** D

### Q7. A customer.subscription.updated event arrives showing a plan change. What is the handler's job when this fires?

- **A.** Email the customer to confirm they intended the change before applying anything internally
- **B.** Sync the local entitlement record so the app's access control reflects the new plan and status  ✅
- **C.** Create a new customer record, since plan changes generate a fresh subscription object each time
- **D.** Reverse the change unless it matches a pending request logged by the application beforehand

> **Answer:** B

### Q8. A customer.subscription.deleted event arrives. What does this signal, and what does the handler do?

- **A.** The subscription has ended, so conclude access according to the business's cancellation policy  ✅
- **B.** The customer object was removed, so purge all local records tied to that customer identifier
- **C.** A duplicate subscription was cleaned up, so no application response is needed for this event
- **D.** The subscription was archived for reporting, so access continues until an invoice event says stop

> **Answer:** A

### Q9. The same checkout.session.completed event was delivered three times, and the customer received three welcome emails and three license keys. What discipline was missing?

- **A.** Rate limiting, which caps how many events per customer the endpoint will accept in a window
- **B.** Event batching, which groups duplicate deliveries into one payload before the handler runs
- **C.** Idempotent processing keyed on the event ID, which detects duplicates and skips reprocessing  ✅
- **D.** Sequence numbering, which rejects any event whose number is lower than the last one processed

> **Answer:** C

### Q10. A builder is surprised that duplicate webhook deliveries happen at all and asks whether something is broken. What is the accurate framing?

- **A.** Duplicates indicate the endpoint returned errors, so eliminating handler bugs eliminates duplicates
- **B.** Duplicates are a test mode artifact, and live mode guarantees exactly-once delivery per event
- **C.** Duplicates mean two endpoints share one signing secret and each is receiving the other's traffic
- **D.** Delivery is at-least-once by design, so duplicates are normal operation the handler must expect  ✅

> **Answer:** D

### Q11. A webhook handler runs fulfillment, emails, and analytics inline, taking twelve seconds before responding. Deliveries are timing out and retrying. What is the professional pattern?

- **A.** Acknowledge with a 2xx quickly and hand the real work to a queue or background job to process  ✅
- **B.** Raise the endpoint's timeout configuration in Stripe so twelve-second handlers pass cleanly
- **C.** Split the work across three endpoints so each stays under the timeout for its own slice
- **D.** Move fulfillment into the success page redirect so the webhook only records that events arrived

> **Answer:** A

### Q12. Events sometimes arrive out of order: a subscription update lands before the invoice event that preceded it in time. How does a robust handler stay correct?

- **A.** Buffer all events for five minutes and process them sorted by their created timestamps in order
- **B.** Treat events as signals and fetch the current object state from Stripe when the truth matters  ✅
- **C.** Reject out-of-order events with an error so Stripe redelivers them in the correct sequence
- **D.** Process only the newest event per object per day, discarding everything older as superseded

> **Answer:** B

### Q13. A builder needs Stripe's test events to reach a handler running on her laptop, which has no public URL. What do you direct her to use?

- **A.** A cron job that exports the day's events to a file the local handler replays each evening
- **B.** Test mode's local delivery setting, which switches all webhooks to localhost automatically
- **C.** The Stripe CLI, which forwards test mode events from Stripe to the local endpoint while it runs  ✅
- **D.** A browser extension that captures dashboard events and re-posts them to a localhost address nightly

> **Answer:** C

### Q14. A builder wants to verify the handler's behavior for a failed renewal without waiting for a real payment to fail. What is the fastest professional method?

- **A.** Deploy to production and attach a card known to be near its limit, then wait for the decline
- **B.** Hand-write a JSON payload guessing at the event structure and post it to the local endpoint
- **C.** Ask Stripe support to inject a synthetic failure event into the account's live event stream
- **D.** Trigger the invoice.payment_failed event with the Stripe CLI and watch the handler respond  ✅

> **Answer:** D

### Q15. A team runs one webhook endpoint for test mode and a separate one for production. A teammate asks whether they share the signing secret. What is correct?

- **A.** Each endpoint has its own signing secret, and verification must use the secret for that endpoint  ✅
- **B.** Secrets are shared per account, so both endpoints verify against the same account-level value
- **C.** Only live endpoints have secrets, since test mode events are unsigned to simplify development
- **D.** The secret is derived from the endpoint URL, so equal paths on both hosts produce equal secrets too

> **Answer:** A

### Q16. An endpoint went down during a deploy and returned errors for twenty minutes. A builder asks what Stripe does with the failed deliveries. What is accurate?

- **A.** Stripe drops events after the first failed attempt, so those twenty minutes are permanently lost
- **B.** Stripe retries failed deliveries with backoff over multiple days, so the events will come back around  ✅
- **C.** Stripe pauses the whole event stream until the endpoint is manually re-enabled in the dashboard
- **D.** Stripe reroutes failed events to the account email as JSON attachments for manual processing

> **Answer:** B

### Q17. A handler processes events inline and occasionally exceeds the delivery timeout. Beyond slow responses, what compounding failure does this create?

- **A.** Stripe deprioritizes the endpoint, so future events arrive minutes late even when it is healthy
- **B.** The endpoint's signing secret is invalidated after repeated timeouts as a protective measure
- **C.** Memory pressure from queued requests corrupts event payloads before verification can run
- **D.** Timeouts count as failures, so Stripe retries events the handler actually processed, creating duplicates  ✅

> **Answer:** D

### Q18. A builder claims the webhook handler is idempotent. What is the direct test that proves or disproves the claim?

- **A.** Read the handler code and confirm a database transaction wraps the full processing routine safely
- **B.** Send one thousand distinct events rapidly and confirm the handler stays under its timeout
- **C.** Replay the same event twice and confirm the second delivery produces no repeated side effects  ✅
- **D.** Restart the worker mid-event and confirm processing resumes from the interrupted position

> **Answer:** C

### Q19. A teammate asks what returning a 2xx from the webhook endpoint actually communicates to Stripe. What is the precise meaning?

- **A.** The event was received and accepted, so Stripe considers this delivery complete and will not retry it  ✅
- **B.** The business logic finished successfully, so Stripe marks the underlying payment as reconciled
- **C.** The endpoint is healthy, which resets the account's delivery failure counter back to zero
- **D.** The event signature was valid, which Stripe records for the endpoint's compliance reporting

> **Answer:** A

### Q20. After the fast acknowledgment, the real event processing has to happen somewhere. What does the professional architecture look like?

- **A.** A second webhook endpoint that the first one forwards to, splitting receipt from processing
- **B.** A browser worker on the customer's next visit, since their session has the needed context
- **C.** A queue or background worker consuming recorded events with retries and failure visibility  ✅
- **D.** A nightly batch job that processes the day's accumulated events in one reconciliation pass

> **Answer:** C

### Q21. An endpoint was down for a full week, longer than the retry window, and some events were never delivered. What is the recovery move?

- **A.** Accept the gap, since expired events cannot be recovered once the retry schedule is exhausted
- **B.** Reconcile against Stripe's records for the gap window, re-fetching events or object state to catch up  ✅
- **C.** Ask affected customers to re-complete checkout so fresh events regenerate the missing state
- **D.** Restore the database from a backup taken before the outage so state and events realign cleanly

> **Answer:** B

### Q22. A handler was built to fulfill on an event name the builder assumed existed rather than checked. Orders are not being fulfilled. What does this failure teach about event coverage?

- **A.** Handlers should process every event type Stripe can send so no name assumption is ever needed
- **B.** Event names change between API versions, so handlers must resolve names dynamically at runtime
- **C.** Fulfillment logic belongs on redirects precisely because event names are too unstable to trust
- **D.** Read the actual event catalog and test each handled event because assumed names fail silently  ✅

> **Answer:** D

### Q23. During a dispute about whether an event ever arrived, where do you direct the team to look for the authoritative delivery record?

- **A.** The dashboard's event log, which records every event, delivery attempt, and endpoint response  ✅
- **B.** The application's own request logs, which are the only record that includes handler outcomes
- **C.** The customer's email receipts, which timestamp each payment the moment Stripe processed it
- **D.** The hosting provider's network flow logs, which capture inbound traffic at the platform edge layer

> **Answer:** A

### Q24. A reviewer asks which events a minimal money-safe handler must cover for a subscription product. Which set is the right core?

- **A.** Only checkout.session.completed, since everything downstream can be derived from checkouts
- **B.** Checkout completed, invoice paid, invoice payment failed, subscription updated, and subscription deleted  ✅
- **C.** Every event in the catalog, since selective handling always leaves revenue-relevant blind spots
- **D.** Only invoice.paid and invoice.payment_failed, since subscriptions are governed entirely by invoices

> **Answer:** B

### Q25. Looking across everything in this module, what is the governing principle for webhooks and payment state?

- **A.** Minimize webhook reliance, because event delivery adds a failure surface that polling avoids
- **B.** Trust event payloads as complete history, because they arrive signed and in guaranteed order
- **C.** Verified, idempotent, fast-acknowledging event handling is what makes payment state trustworthy  ✅
- **D.** Handle events only for revenue above a threshold, because small payments do not justify the rigor

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106562775_
