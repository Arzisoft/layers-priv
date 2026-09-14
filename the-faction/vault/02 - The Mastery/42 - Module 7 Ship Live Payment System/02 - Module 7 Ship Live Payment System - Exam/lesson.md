---
course: "The Mastery"
module: "Module 7: Ship: Live Payment System"
lesson: "Module 7: Ship: Live Payment System — Exam"
type: "course_quiz"
post_id: 106562785
space_id: 24191170
source: "https://the-faction.mn.co/posts/106562785"
updated: "2026-08-28T15:43:19Z"
---

# Module 7: Ship: Live Payment System — Exam

> Exam for **Module 7: Ship: Live Payment System** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. The team is ready to go live. A builder asks where the live secret key belongs and how it gets there. What is the correct answer?

- **A.** In the repository's production branch, protected by the platform's branch permission rules
- **B.** In the frontend build's environment bundle, since live checkout must initialize from the browser
- **C.** In server-side environment configuration through the host's secret store, never committed anywhere  ✅
- **D.** In a shared team document, from which each deploy copies it into the running configuration

> **Answer:** C

### Q2. After switching to live keys, every webhook delivery fails signature verification even though the handler worked perfectly in test mode. What is the classic cause?

- **A.** The handler still verifies with the test endpoint's signing secret; the live endpoint has its own  ✅
- **B.** Live events use a newer signature algorithm that test mode handlers cannot process directly
- **C.** The endpoint URL changed protocols at launch, invalidating signatures computed against it
- **D.** Live mode signs with the publishable key, and the handler still expects the secret key's hash

> **Answer:** A

### Q3. The first live checkout attempt fails: the code cannot find the price it references. Test mode worked flawlessly for weeks. What did the team forget?

- **A.** Price objects need a one-hour propagation window after account activation before use
- **B.** The live account requires a minimum balance before catalog objects become purchasable
- **C.** Live prices must be activated individually from the dashboard after business verification
- **D.** Products and prices do not copy from test to live; the live catalog must be recreated  ✅

> **Answer:** D

### Q4. A launch checklist includes items no engineer can complete: identity verification and bank account details. Why do these block the launch?

- **A.** They unlock the dashboard's reporting tier, which monitoring on launch day depends on for all of its data feeds
- **B.** Stripe cannot pay out funds until the business is verified and banking is complete, so they gate real revenue  ✅
- **C.** They are optional for the first ninety days, so they should be dropped from the checklist today
- **D.** They enable test mode parity, ensuring the live environment mirrors what was verified earlier

> **Answer:** B

### Q5. Everything is switched to live and the dashboard looks clean. What final verification does this module require before declaring the launch done?

- **A.** A real end-to-end transaction with a real card, refunded afterward, because only a live payment proves the live path  ✅
- **B.** A full replay of the test suite against live keys, since passing tests transfer directly to live environments unchanged
- **C.** A screenshot archive of every live configuration screen for the compliance folder and audit trail records
- **D.** A twenty-four hour observation window with zero traffic before any customer is allowed through the door

> **Answer:** A

### Q6. A founder asks what Stripe Radar is actually doing on every payment now that the system is live. What is accurate?

- **A.** It verifies the cardholder's identity documents against the name on each arriving payment
- **B.** It delays each payment by a review window during which staff can manually inspect the charge
- **C.** It scores every payment for fraud risk using network-wide signals and blocks the obvious cases  ✅
- **D.** It insures each transaction, reimbursing the business whenever a charge is later disputed

> **Answer:** C

### Q7. A business cranks Radar's blocking threshold to maximum, reasoning that zero fraud is the goal. What does this module say about that posture?

- **A.** It is correct; fraud losses always exceed the revenue value of any blocked legitimate customers on the platform side
- **B.** It is irrelevant; Radar thresholds only affect payments already flagged by the card networks themselves
- **C.** It is incomplete; maximum blocking must pair with allowlists for every known good customer list first
- **D.** It is miscalibrated; aggressive blocking bounces good customers, and the review queue exists for borderline cases  ✅

> **Answer:** D

### Q8. A teammate asks why everyone keeps watching the dispute rate so closely now that payments are live. What is at stake?

- **A.** Card networks monitor it, and sustained high dispute rates threaten the ability to process at all  ✅
- **B.** Each dispute permanently blocks that customer's card from ever paying the business again
- **C.** Disputes above a threshold convert automatically into refunds plus a fixed regulatory fine per case
- **D.** The rate sets the account's payout schedule, with high rates delaying settlement by weeks

> **Answer:** A

### Q9. A compliance reviewer asks why the build qualifies for SAQ-A, the lightest PCI self-assessment. What is the qualifying fact?

- **A.** The business processes under the annual transaction volume where heavier tiers begin each year
- **B.** Card data goes from the customer's browser directly to Stripe and never transits the business's servers  ✅
- **C.** The business purchased Stripe's compliance add-on, which absorbs the assessment burden for them
- **D.** All customers are businesses rather than consumers, which exempts the consumer standard entirely from scope

> **Answer:** B

### Q10. A well-meaning engineer proposes accepting card numbers into the backend just to forward them to Stripe, arguing they are never stored. What is the consequence?

- **A.** Nothing, provided the forwarding happens over an encrypted connection with no logging enabled
- **B.** A modest paperwork increase, since forwarding falls under the same SAQ-A attestation anyway
- **C.** PCI scope explodes; card data transiting your servers ends SAQ-A eligibility regardless of storage  ✅
- **D.** Stripe blocks the traffic automatically, since raw card numbers are rejected from server calls

> **Answer:** C

### Q11. During a pre-launch audit, AI-generated code is found that renders its own card number input and posts it to the application server. How does this module classify that discovery?

- **A.** A style issue, worth refactoring after launch once the revenue-critical path has stabilized
- **B.** A feature, since owning the card form gives the business full control of the checkout brand
- **C.** An optimization opportunity, since direct card handling removes a network hop from checkout
- **D.** A finding to remediate before launch, because it detonates PCI scope no matter how it is framed  ✅

> **Answer:** D

### Q12. The uptime monitor shows green across every service, yet renewals have not processed for three days. What distinction does this failure teach?

- **A.** Uptime monitoring watches servers, not the business; payment health needs its own metrics and alerts  ✅
- **B.** Uptime checks must run more frequently, since three-day gaps hide inside hourly probe intervals easily
- **C.** Renewals pause automatically whenever monitoring detects elevated latency on the platform
- **D.** Green dashboards prove the payment system is fine and the renewal gap must be seasonal

> **Answer:** A

### Q13. A founder asks what belongs on the payment health dashboard someone actually reads daily. Which set matches this module?

- **A.** Server CPU, memory, disk, and request latency across every host serving the application in production
- **B.** MRR movement, churn split by type, failed payment rate, recovery rate, dispute rate, webhook health  ✅
- **C.** Signup counts, page views, session duration, and conversion by acquisition channel each week
- **D.** Deploy frequency, lead time, incident count, and mean time to recovery for the team itself

> **Answer:** B

### Q14. Stripe retried a failing webhook endpoint for days during an outage nobody noticed, then stopped. What operational control was missing?

- **A.** A backup endpoint registered in a second region to absorb deliveries during any outage event windows
- **B.** A longer retry window purchased through support before the launch window opened for business
- **C.** An auto-scaling rule that provisions more webhook capacity as delivery volume rises sharply
- **D.** Alerting on webhook delivery failures, so a failing endpoint pages someone while retries still run  ✅

> **Answer:** D

### Q15. The webhook endpoint was down for a week, past the retry window, and events were lost. What is the recovery procedure this module prescribes?

- **A.** Wait for affected customers to report problems, then fix each account as tickets arrive through support queues
- **B.** Restore last week's database backup so local state rewinds to before the outage began that night
- **C.** Reconcile the gap window against Stripe's records, re-fetching events and object state to rebuild truth  ✅
- **D.** Issue account credits to every active customer as blanket compensation for the disruption package

> **Answer:** C

### Q16. A payment bug silently failed for nine days before anyone noticed, and the founder asks why this class of failure is treated as the most dangerous. What is the reasoning?

- **A.** Silent payment failures compound unseen: every quiet hour is lost revenue and eroded customer trust  ✅
- **B.** Silent failures corrupt the database in ways that loud failures with stack traces never do
- **C.** Regulators fine silent failures at a higher rate than incidents that were publicly disclosed early on
- **D.** Insurance policies exclude silent failures, making them uniquely uncoverable business losses

> **Answer:** A

### Q17. An exception fires in the checkout code path at 2 AM. The team asks how this module says it should be treated. What is the standard?

- **A.** As a morning-review item, since overnight traffic is too small to justify waking anyone
- **B.** As a batch item for the weekly bug triage alongside every other production exception
- **C.** As a sev-1 that pages someone now, because payment path failures burn money and trust hourly  ✅
- **D.** As a monitoring artifact to suppress unless the same exception repeats three times

> **Answer:** C

### Q18. A founder asks what a payment incident runbook should actually contain before launch. Which contents match this module?

- **A.** The full architecture diagram and the API reference for every Stripe endpoint the build uses directly
- **B.** Steps for the likely incidents: endpoint down, key rotation, dispute spike, with owners and actions  ✅
- **C.** Postmortem templates for documenting incidents thoroughly after they have been resolved
- **D.** Escalation contacts at Stripe, since payment incidents are resolved on the platform side

> **Answer:** B

### Q19. The payment success rate dipped noticeably right after Tuesday's deploy, though no errors appeared. What does the monitoring discipline in this module conclude?

- **A.** Success rates fluctuate naturally, so the dip should be rechecked at the end of the month as part of normal review
- **B.** The customers affected will retry on their own, making deploy correlation an academic question anyway
- **C.** Dips without errors indicate card network issues, which resolve without any business action needed
- **D.** The deploy is the prime suspect; investigate now, because anomalies tied to changes are how silent breaks surface  ✅

> **Answer:** D

### Q20. A builder asks for the correct ordering of the go-live sequence. Which ordering reflects this module's checklist?

- **A.** Verify the business, recreate the live catalog, register live webhooks, switch keys, then run a real transaction  ✅
- **B.** Switch keys first, then rebuild the catalog while early customers exercise the live path under real load conditions
- **C.** Register webhooks last, since event handling only matters once real volume has arrived on the account
- **D.** Run the real transaction first in test mode, then switch every component simultaneously all together

> **Answer:** A

### Q21. A security review asks what happens if the live secret key leaks a month after launch. What readiness does this module expect?

- **A.** A documented promise to investigate within thirty days, matching standard disclosure norms for software vendors
- **B.** Rotation readiness: roll the key, update environments, and audit for misuse, practiced as a known procedure  ✅
- **C.** Dependence on Stripe's automatic leak detection, which rotates compromised keys unprompted for the account
- **D.** A fallback processor to route payments through while the primary account is investigated occurs

> **Answer:** B

### Q22. Two businesses run identical Radar settings: a low-margin digital goods store and a high-touch B2B service. Why does this module call that a mistake?

- **A.** Radar requires distinct settings per industry code, and shared settings void dispute protections completely
- **B.** Identical settings double-count network signals when two accounts share configuration values
- **C.** Fraud posture is a dial set per business; risk tolerance and margin structure should shape the thresholds  ✅
- **D.** The digital store legally requires stricter screening than services under card network rules

> **Answer:** C

### Q23. After running the real live transaction test, what does this module direct you to do with that charge, and why?

- **A.** Refund it, completing the loop and verifying the refund path works while keeping the books clean  ✅
- **B.** Leave it as the first revenue on the books, marking the launch date in the financial record
- **C.** Dispute it deliberately, exercising the chargeback machinery before real customers ever can reach it
- **D.** Transfer it to a test balance, quarantining launch verification money from customer revenue

> **Answer:** A

### Q24. A founder asks what reading the Stripe event feed like a pilot reads instruments actually means in practice. What is the habit?

- **A.** Exporting the feed to a spreadsheet each quarter for the board's revenue reporting package and annual planning cycle
- **B.** Watching the feed only during deploys, when new code makes event anomalies most likely deliberately
- **C.** Assigning the feed to a support rotation that files tickets for any unrecognized event type it finds
- **D.** Regularly scanning events and deliveries so anomalies are noticed early, as boring vigilance, not crisis response  ✅

> **Answer:** D

### Q25. Looking across everything in this module and the full course, what is the governing principle for a live payment system?

- **A.** Ship fast and iterate on payments like any feature, because velocity beats caution in every domain that truly matters
- **B.** Payments are infrastructure that must never silently break: monitored, alarmed, and treated with sev-1 seriousness  ✅
- **C.** Outsource payment operations entirely, because the platform owns reliability once keys go live for good
- **D.** Freeze the payment system after launch, because any change to working revenue code is unjustifiable risk

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/106562785_
