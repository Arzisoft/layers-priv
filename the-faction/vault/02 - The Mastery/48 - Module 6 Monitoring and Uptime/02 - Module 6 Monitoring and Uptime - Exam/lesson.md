---
course: "The Mastery"
module: "Module 6: Monitoring and Uptime"
lesson: "Module 6: Monitoring and Uptime — Exam"
type: "course_quiz"
post_id: 106571031
space_id: 24191170
source: "https://the-faction.mn.co/posts/106571031"
updated: "2026-08-28T16:23:07Z"
---

# Module 6: Monitoring and Uptime — Exam

> Exam for **Module 6: Monitoring and Uptime** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. This module says that when developers build on your API, your uptime becomes their uptime. What follows from that for how you treat reliability?

- **A.** Reliability is a core feature of the product you sell, since an outage in your own service is an outage in every product built on top of you  ✅
- **B.** Reliability is an internal metric, since your uptime is an operational concern that developers building on you never actually observe directly
- **C.** Reliability is a pricing tier, since uptime matters only to enterprise buyers and can be ignored entirely for developers on the free plan
- **D.** Reliability is the hosting provider's responsibility, since your availability is fully determined by the cloud platform you happen to run on

> **Answer:** A

### Q2. This module says each additional nine of availability costs more than the last. Roughly how much annual downtime does 99.9% allow?

- **A.** About one minute a year, since three nines is already a near-perfect target that permits only the briefest interruption annually
- **B.** About a full day a year, since three nines is a relaxed target that tolerates roughly twenty-four hours of cumulative outage
- **C.** About nine hours a year since 99.9% leaves a tenth of a percent of the year as allowable downtime across all incidents combined  ✅
- **D.** About one week a year, since 99.9% is an entry-level commitment that permits several days of downtime spread across the year

> **Answer:** C

### Q3. This module says an SLA you miss is worse than a lower one you keep. What skill does it say choosing an SLA actually requires?

- **A.** Choosing a target you can actually honor for the price your product supports, since matching the promise to architecture and price is the skill  ✅
- **B.** Copying the SLA of the largest competitor, since matching the market leader's availability promise is the safest benchmark to adopt
- **C.** Choosing the highest number that will impress enterprise buyers, since a bold SLA wins deals even if the architecture cannot honor it
- **D.** Setting no SLA at all until the API is years old, since any availability promise before then exposes you to penalties you cannot predict

> **Answer:** A

### Q4. This module says a health check should ideally verify more than that the server responds. What else should a good health check confirm?

- **A.** That the documentation is current, since a health check is the natural place to confirm the reference matches the deployed endpoints
- **B.** That rate limits are configured, since verifying each tier's quota during the health check prevents customers from exceeding their plan
- **C.** That the latest version is deployed, since a health check should fail whenever the running code lags behind the newest released version
- **D.** That critical dependencies are reachable, since an API that responds but cannot reach its database is not actually healthy for callers  ✅

> **Answer:** D

### Q5. This module calls a status page a trust instrument. How does an honest status page reduce support load during an incident?

- **A.** Customers who can see an honest status stay calmer and file fewer tickets than customers left guessing whose end the problem is on  ✅
- **B.** The status page rate-limits tickets, since customers must acknowledge the current status before the support system accepts a new request
- **C.** The status page resolves incidents automatically, since publishing an outage triggers the failover that restores service without human action
- **D.** The status page hides outages, since showing only green status reassures customers and stops them from reporting problems they notice

> **Answer:** A

### Q6. This module says availability is not binary. What does it mean when it says an API can be up but degraded?

- **A.** The API is running an older version, since a degraded API is one that has not yet deployed the latest release to all of its instances
- **B.** The API is up but slow, or up but failing a fraction of requests, so raw up-or-down status misses the degradation customers feel  ✅
- **C.** The API is up but undocumented, since degradation refers to the reference drifting out of sync with the endpoints that are deployed
- **D.** The API is up but over budget, since a degraded service is one consuming more infrastructure than its pricing model can sustain

> **Answer:** B

### Q7. This module says to monitor latency and error rate per endpoint rather than only in aggregate. What can an aggregate number hide?

- **A.** The total request volume, since an aggregate figure averages traffic across endpoints and obscures how many calls the API served overall
- **B.** One critical endpoint quietly failing every fifth call, since an aggregate can look healthy while a single endpoint degrades badly  ✅
- **C.** The billing total, since aggregate metrics combine usage across customers and prevent the system from attributing charges to each key
- **D.** The version distribution, since aggregate monitoring cannot tell which API version each request targeted during the measured window

> **Answer:** B

### Q8. This module says your API is only as available as the things it depends on. What does dependency monitoring let you determine during a degradation?

- **A.** Which customer is causing it, since dependency monitoring attributes every slow response to the specific key that triggered the load
- **B.** How much to charge, since dependency monitoring measures the cost of each upstream call so it can be passed through to the customer
- **C.** Which version to retire, since dependency monitoring reveals that older versions are the ones consuming the failing upstream service
- **D.** Whether the fault is yours or an upstream provider's, since monitoring only your own service leaves you blind to the actual cause  ✅

> **Answer:** D

### Q9. This module says silence during an incident turns an outage into something. What?

- **A.** A security breach, since going quiet during an outage signals to attackers that the team is distracted and the system is vulnerable
- **B.** A churn event, since customers left without communication during an incident lose trust and leave, whatever the eventual resolution  ✅
- **C.** A billing dispute, since customers charged during an unexplained outage refuse to pay for the window when the API was unavailable
- **D.** A version conflict, since incidents that go uncommunicated are usually caused by an unannounced version change breaking integrations

> **Answer:** B

### Q10. This module says a published, honest postmortem does something valuable after an incident. What does it turn a failure into?

- **A.** A marketing opportunity, since a well-written postmortem doubles as promotional content that attracts developers to the platform
- **B.** Evidence of operational seriousness, since that honest postmortem is exactly what enterprise customers look for before they commit  ✅
- **C.** A legal shield, since a published postmortem primarily serves to limit the provider's liability for the damage the outage caused
- **D.** A pricing justification, since documenting an outage in detail supports charging customers more for the higher reliability tier next

> **Answer:** B

### Q11. This module says uptime for an API product is a feature with a dollar value. What does it say enterprise customers do with that feature?

- **A.** They scrutinize it first, since reliability is often the feature enterprise buyers examine before anything else when evaluating an API  ✅
- **B.** They ignore it, since enterprise buyers assume any serious API is reliable and focus their evaluation entirely on its feature set
- **C.** They negotiate it away, since enterprise buyers prefer a lower price to a strong SLA and trade uptime guarantees for a discount
- **D.** They replicate it, since enterprise buyers build their own redundant copy of the API rather than depending on the provider's uptime

> **Answer:** A

### Q12. This module says you should measure your API's real availability rather than assume it. Why is measuring necessary?

- **A.** Because measurement lowers cost, since instrumenting availability reveals idle capacity you can shut down to save on infrastructure spend
- **B.** Because measurement replaces monitoring, since once availability is measured the separate latency and error-rate tracking is unnecessary
- **C.** Because measurement is required by REST, since the specification mandates that every public API publish its measured availability figures
- **D.** Because a commitment must be real and demonstrable, since developers make integration decisions based on reliability you can actually prove  ✅

> **Answer:** D

### Q13. This module says each step up in SLA demands more of the system. What does moving from 99.9% to 99.99% require?

- **A.** More documentation, since a higher SLA obligates that provider to document every endpoint's individual availability separately and in detail
- **B.** More redundancy, faster failover, and more operational maturity, at a rapidly rising cost, since each additional nine grows harder to reach  ✅
- **C.** More endpoints, since a stricter availability target is met by spreading load across a larger number of routes that each fail independently
- **D.** More versions, since a higher SLA is achieved by maintaining multiple parallel API versions so a failure in one does not affect the others

> **Answer:** B

### Q14. This module describes incident communication as part of the deliverable, not overhead. What should incident communication tell API consumers?

- **A.** The name of the engineer responsible, since consumers want accountability and expect to know who caused the incident they are experiencing
- **B.** The full technical root cause immediately, since consumers require the complete diagnostic detail before they can respond to an incident
- **C.** What is affected, what you are doing, and when to expect an update, delivered in near real time through the status page and direct channels  ✅
- **D.** A discount offer, since the primary purpose of incident communication is to retain customers by compensating them for the disruption

> **Answer:** C

### Q15. This module says telling customers an outage is due to an upstream provider is very different from an unexplained failure. Why does that distinction matter?

- **A.** It shapes honest incident communication, since knowing the true fault lets you tell customers accurately what is happening and why  ✅
- **B.** It changes the billing, since outages caused by an upstream provider are charged to that provider rather than absorbed by your own margin
- **C.** It determines the version, since an upstream failure requires cutting customers over to a different API version that avoids that dependency
- **D.** It sets the rate limit, since an upstream outage is handled by throttling customers until the dependency recovers its normal capacity

> **Answer:** A

### Q16. This module says a functionally perfect API that goes down unpredictably is worse than a simpler one that never does. What reasoning supports that?

- **A.** Simpler APIs are cheaper, so the one that never goes down wins purely on the lower infrastructure cost of its reduced feature set
- **B.** Simpler APIs rank higher in search, so the reliable one wins on discoverability regardless of how its uptime compares in practice
- **C.** Perfect APIs attract more attackers, so the feature-rich one is likelier to be breached and its downtime is therefore self-inflicted
- **D.** Developers can design around limited features but cannot design around an unreliable foundation, so reliability outranks feature breadth  ✅

> **Answer:** D

### Q17. This module says you match the SLA promise to the architecture and the price, not to what sounds impressive. What is the danger of promising to impress?

- **A.** An impressive SLA raises latency, since the redundancy required to sound competitive slows every request the API serves to customers
- **B.** An impressive SLA confuses developers, since a very high availability number is harder for a non-technical buyer to interpret correctly
- **C.** An SLA you cannot honor is worse than a lower one you keep, since missing the promise costs more trust than a modest promise ever would  ✅
- **D.** An impressive SLA voids the terms of service, since promising availability beyond the platform's capacity breaches the provider's own contract

> **Answer:** C

### Q18. This module says a status page shows current status, ongoing incidents, and history. Why does showing history matter?

- **A.** History replaces the SLA, since a published record of past incidents makes a formal availability commitment unnecessary for the customer
- **B.** History lowers latency, since caching the incident timeline lets the status page load faster during the traffic spike an outage brings
- **C.** History satisfies versioning, since the incident log records which API version was live during each outage for the migration guides
- **D.** History gives customers a track record they can weigh since a visible incident history lets a prospect judge the API's real reliability  ✅

> **Answer:** D

### Q19. This module says latency and error rate are the metrics that catch degradation before it becomes an outage. What is error rate specifically?

- **A.** The number of deprecated endpoints still in use, tracked so the team knows when it is safe to remove an old version from production
- **B.** The fraction of requests returning 5xx, monitored per endpoint with alerting so a failing endpoint is caught before customers complain  ✅
- **C.** The count of customers over their rate limit, measured so the team can decide when to raise the caps on the busiest pricing tier
- **D.** The percentage of requests that hit the cache, watched so the team can tune how aggressively responses are stored for reuse later

> **Answer:** B

### Q20. This module says reliability is something you design and measure, not something you hope for. What does treating it that way require you to build?

- **A.** A larger feature set, since the way to design for reliability is to add redundant endpoints that duplicate each other's functionality
- **B.** A cheaper architecture, since designing for reliability means cutting infrastructure to the minimum the SLA can be met on affordably
- **C.** Instrumentation to know the real availability, a target you can meet, and the operational practices that keep you there over time  ✅
- **D.** A higher price, since the only way to design in reliability is to charge enough that customers fund the redundancy it demands

> **Answer:** C

### Q21. This module says a postmortem documents three things after an incident is resolved. Which set matches?

- **A.** The cost, the refund, and the discount, since a postmortem exists primarily to calculate what compensation affected customers are owed
- **B.** The version, the endpoint, and the region, since a postmortem's job is to record exactly which parts of the deployment were involved
- **C.** The attacker, the vulnerability, and the patch, since a postmortem treats every outage as a security incident to be traced to its source
- **D.** What happened, why, and what will prevent a recurrence, since that is what turns a failure into evidence of operational maturity  ✅

> **Answer:** D

### Q22. This module says the API stops being code and becomes infrastructure other businesses depend on. What responsibility does that shift carry?

- **A.** The responsibility to raise prices, since becoming infrastructure justifies charging more regardless of the reliability you actually deliver
- **B.** The responsibility to add features, since infrastructure status obligates you to expand the API faster than a mere feature would require
- **C.** The responsibility to keep the promise, since other businesses depending on you means your reliability is now their reliability too  ✅
- **D.** The responsibility to version constantly, since dependable infrastructure is defined by how frequently it ships new releases to consumers

> **Answer:** C

### Q23. A team wants to advertise 99.999% availability but runs a single-region deployment with manual failover. What does this module say about that gap?

- **A.** Five nines demands redundancy and fast automated failover, so a single region with manual failover cannot honor that promise being made  ✅
- **B.** It improves adoption, since a bold availability claim wins developers and the single-region architecture can be quietly upgraded afterward
- **C.** It is fine, since the advertised number is a marketing target and customers rarely measure whether the five-nines promise is actually met
- **D.** It only matters for writes, since read-only endpoints on a single region can still reach five nines even without any failover in place

> **Answer:** A

### Q24. During an incident, a team stays silent until they have a complete root-cause analysis, then posts once at the end. What does this module say they got wrong?

- **A.** They should have posted the engineer's name, since customers experiencing an outage primarily want to know who was responsible for it
- **B.** They should have offered a refund first, since compensation is the opening move that retains customers through any significant incident
- **C.** They should communicate in near real time with what is affected and when to expect an update, since silence turns an outage into churn  ✅
- **D.** They should have pinned the API version, since incident updates are only useful when they specify which release the outage affected

> **Answer:** C

### Q25. Looking across everything in this module, what is the governing principle for monitoring and uptime?

- **A.** Treat reliability as a product commitment: set an honest SLA, monitor per endpoint and dependencies, and communicate through every incident  ✅
- **B.** Monitor only aggregate availability, because a single up-or-down number is the clearest signal of health for a non-technical customer to read
- **C.** Treat uptime as a hosting concern, because availability is determined by the cloud provider and is largely outside the API team's control
- **D.** Promise the highest SLA possible, because a bold availability number wins enterprise deals and the architecture can be improved later to match

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106571031_
