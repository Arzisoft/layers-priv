---
course: "The Mastery"
module: "Module 6 — Usage Metering & Analytics"
lesson: "Module 06: API Throttling & Usage Metering — Exam"
type: "course_quiz"
post_id: 103821135
space_id: 24191170
source: "https://the-faction.mn.co/posts/103821135"
updated: "2026-08-21T01:09:42Z"
---

# Module 06: API Throttling & Usage Metering — Exam

> Exam for **Module 6 — Usage Metering & Analytics** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your SaaS has Free (100 calls/day), Pro (10K calls/day), and Enterprise (100K calls/day) plans. Your rate limiter applies the same 10K limit to everyone. What's broken?

- **A.** Rate limits must be tied to the user's subscription plan — free users consuming 10K defeats paid tiers  ✅
- **B.** A single rate limit for every plan simplifies operations but ignores tier differentiation
- **C.** 10,000 API calls is a reasonable default limit for all plans regardless of what the user is paying
- **D.** Free users won't actually make 10,000 calls so the limit is effectively just a safety net for abuse

> **Answer:** A

### Q2. A Pro customer hits their daily API limit at 3pm. The system returns a 429 with just 'Too Many Requests.' They call support confused. What should the error response include?

- **A.** A 429 status code with the message 'Too Many Requests' is sufficient for any client
- **B.** Their current limit, usage count, reset time, and an upgrade link — not just a generic error  ✅
- **C.** Return a 200 status with an error field inside the body instead of a proper 429 response code
- **D.** Redirect the user to the pricing page automatically whenever they exceed their plan's rate limit

> **Answer:** B

### Q3. Your usage counter is stored in memory. After a deployment (which restarts the server), a customer's usage resets to zero mid-billing-period. What's wrong?

- **A.** Deployments are rare enough that losing in-memory counters isn't a meaningful problem for billing
- **B.** Reset all counters to zero after each deployment and credit affected customers for the gap
- **C.** Usage counters must be persisted in a database or Redis — in-memory counters are lost on restart  ✅
- **D.** Store counters in a flat file on the server so they survive restarts and don't require a database

> **Answer:** C

### Q4. An enterprise with 50 employees makes 200K API calls/day. No individual exceeds their limit, but the org far exceeds its 100K org cap. What's missing?

- **A.** Per-user limits alone are sufficient for any team size and usage pattern in a SaaS app
- **B.** Only count the admin user's API calls since they're typically the heaviest consumer of the API
- **C.** Increase individual limits high enough to match the org's total expected usage across all users
- **D.** Rate limiting needs both user-level and org-level enforcement to prevent collective overuse  ✅

> **Answer:** D

### Q5. Your API returns rate limit headers (X-RateLimit-Limit, Remaining, Reset) but only on 429 responses, not successful ones. What should change?

- **A.** Include rate limit headers on every response so clients can throttle proactively before hitting limits  ✅
- **B.** Rate limit information should only be returned when the client has exceeded their usage limit
- **C.** Expose rate limit data through a separate dedicated API endpoint that clients can poll manually
- **D.** Email the account owner whenever usage reaches 80% so they can take action before being limited

> **Answer:** A

### Q6. Metered billing shows 45,000 overage calls. The customer saw 30,000 in their dashboard. Dashboard counts client-side; billing counts server-side. What caused the gap?

- **A.** Client-side counting with JavaScript gives the most accurate view since it tracks clicks
- **B.** Usage must be counted server-side from one source — dashboard and billing read the same data  ✅
- **C.** Let the billing system estimate usage based on the customer's plan type and average traffic patterns
- **D.** Count usage at the CDN layer since that captures all traffic before it reaches the application tier

> **Answer:** B

### Q7. A customer's system sends 5,000 calls in 10 seconds — 50x normal. Your limiter blocks them. They were running a legitimate one-time data migration. What feature would handle this better?

- **A.** Permanently raise the account's rate limit after the first time a legitimate burst is blocked
- **B.** Disable rate limiting for trusted enterprise accounts so migrations are never interrupted
- **C.** A temporary limit-raise process — let customers request a burst window for planned migrations  ✅
- **D.** Whitelist requests that arrive from the customer's known IP ranges regardless of volume

> **Answer:** C

### Q8. Your usage table has 45 million rows after 6 months. Monthly billing queries take 3 minutes to aggregate. What architectural change fixes this?

- **A.** Move the usage table to a larger database instance so the aggregation query completes faster
- **B.** Delete usage rows older than 90 days so the table stays small enough to aggregate quickly
- **C.** Run the monthly aggregation query more often so each individual run has less data to process
- **D.** Pre-aggregate usage into rollup tables — daily summaries make monthly billing queries fast  ✅

> **Answer:** D

### Q9. Your rate limiter uses a fixed 1-hour window. A customer makes 999 calls at 11:59 and 999 at 12:01 — 1,998 in 2 minutes, never hitting the 1,000 limit. What prevents this?

- **A.** A sliding window algorithm tracking usage over any rolling 60-minute period prevents burst gaming  ✅
- **B.** A fixed window counter that resets at the top of each hour is the simplest and most accurate method
- **C.** Let users send unlimited requests as long as they stay below the daily total across a 24-hour span
- **D.** Count only successful responses — failed requests shouldn't be counted against the limit

> **Answer:** A

### Q10. A free user hits their 100 calls/day limit. Your system returns a plain 429 error with no context. What should the response include for free users specifically?

- **A.** A 429 response is sufficient — free-tier users should expect limitations on their API access level
- **B.** A message explaining their free plan limit, current usage, reset time, and a prominent upgrade CTA  ✅
- **C.** Block free users silently after they hit the limit to encourage upgrading to a paid subscription
- **D.** Redirect free users to the pricing page on every 429 response until they upgrade their plan tier

> **Answer:** B

### Q11. A bug double-counts POST requests. A customer is billed $450 instead of $225. They dispute. What should have prevented this?

- **A.** Usage data should be reviewed only when a customer disputes their bill — proactive checks are waste
- **B.** Spot-checking a few accounts manually each month is sufficient to verify that metering is accurate
- **C.** Counter validation tests for each request type, plus reconciliation checks comparing logs to totals  ✅
- **D.** Compare the current month's total against the previous month's to detect any significant variance

> **Answer:** C

### Q12. Your rate limiter only applies to authenticated endpoints. Anonymous users can hit public endpoints unlimited times. What's the exposure?

- **A.** Block all traffic from IP addresses that have previously exceeded the rate limit for any endpoint
- **B.** Public endpoints don't need rate limiting since only authenticated users make real requests
- **C.** CAPTCHA challenges on every public endpoint request will prevent automated abuse effectively here
- **D.** Public endpoints need IP-based rate limiting — without it, anyone can overwhelm your APIs easily  ✅

> **Answer:** D

### Q13. Your app runs on 3 servers, each with its own in-memory rate counter. A user making 300 calls gets spread across all 3 — each sees 100, none exceeds 200. What's the fix?

- **A.** Run a single API server to completely avoid the distributed rate limiting synchronization problem
- **B.** Use a centralized counter store like Redis that all servers share for accurate distributed limits  ✅
- **C.** Set each server's individual limit to 67 so the combined total equals the intended 200 limit
- **D.** The load balancer should be responsible for tracking and enforcing rate limits across all servers

> **Answer:** B

### Q14. Your 429 responses don't include a Retry-After header. A customer's automated system retries immediately, gets another 429, retries again — creating a loop. What's missing?

- **A.** Retry behavior after rate limiting is entirely the client's responsibility to implement correctly
- **B.** Block the client's IP address permanently after 10 consecutive failed retry attempts are detected
- **C.** Return a 503 Service Unavailable status code instead of the standard 429 Too Many Requests response
- **D.** A Retry-After header telling the client exactly when to retry — letting automated systems back off  ✅

> **Answer:** D

### Q15. Your metering charges per active user monthly. The counter increments per login — a user logging in 15 times counts as 15 users. The customer is overbilled. What's correct?

- **A.** Count unique users per billing period using a distinct set of user IDs — not login events  ✅
- **B.** Count only each user's first login per day to avoid inflating the active user metric
- **C.** Login count is a reasonable and straightforward proxy for tracking monthly active user metrics
- **D.** Define active users by their API call volume instead of login frequency for more accuracy

> **Answer:** A

### Q16. Twelve free accounts coordinate requests from different IPs, collectively consuming 10x a single account's allowance. Each is under its own limit. What abuse pattern is this?

- **A.** Each account is under its own limit so no coordinated abuse is actually occurring here
- **B.** Coordinated multi-account abuse — detect patterns like shared domains or correlated timing  ✅
- **C.** Block all accounts that were created on the same day since they're likely part of the same attack
- **D.** Raise the individual rate limits so legitimate users aren't affected by the increased traffic

> **Answer:** B

### Q17. Rate limiting only counts requests returning 200. A buggy integration sends 50K malformed requests/hour returning 400. They don't count but eat server resources. What should change?

- **A.** Only successful responses should count — charging users for failed requests is unfair
- **B.** Failed requests should count at half the rate of successful ones to balance fairness and protection
- **C.** All requests should count toward rate limits regardless of status — failed calls use resources  ✅
- **D.** Track failed and successful requests in separate counters and only bill for the successful responses

> **Answer:** C

### Q18. You rate-limit at the API gateway, but your app also uses WebSockets. The limiter doesn't cover WebSocket messages. A user sends 100K messages per minute. What's the gap?

- **A.** Rate limiting must cover all channels — HTTP and WebSocket — not just REST API endpoints  ✅
- **B.** Let the WebSocket server handle its own limits independently from the main API gateway
- **C.** WebSocket messages are lightweight enough that rate limiting them isn't worth the implementation
- **D.** WebSocket connections don't need rate limiting because they use a persistent connection model

> **Answer:** A

### Q19. Your usage dashboard refreshes hourly. A customer sees 1,500 calls remaining, kicks off a 2,000-call batch, and gets rate-limited. What's the frustration?

- **A.** Hourly refresh is a reasonable trade-off since real-time usage data is expensive to compute
- **B.** Show real-time usage data — stale quota numbers mislead customers into exceeding limits  ✅
- **C.** Add a dashboard disclaimer warning that displayed usage may be up to an hour old
- **D.** Refresh the dashboard every thirty minutes instead of hourly to cut the staleness in half

> **Answer:** B

### Q20. Rate limiting exists in production but not staging. A developer tests an integration with unlimited calls. In production, it immediately exceeds limits. What should staging include?

- **A.** Staging should stay unlimited so developers can load test without interference
- **B.** A note in the API docs warning developers that production enforces limits staging does not
- **C.** The same rate limits as production — staging should mirror what integrations will face  ✅
- **D.** A lower rate limit than production so developers hit limits earlier and learn them faster

> **Answer:** C

### Q21. Your API docs say Pro gets 10K calls/day but your rate limiter is set to 5K. A Pro customer hits the limit at 5K and cites the docs. What's the root cause?

- **A.** The customer misread the documentation — the 5K limit was correct for their billing plan tier
- **B.** Support should have granted a temporary limit increase as soon as the customer complained
- **C.** The docs team should sign off on every limit change before engineering deploys the new value
- **D.** The limit lives in two places with no single source of truth — docs and config drifted apart  ✅

> **Answer:** D

### Q22. Your usage dashboard shows daily totals but not which endpoints consume the most calls. A customer wants to optimize but can't tell where to focus. What's missing?

- **A.** Per-endpoint usage breakdown showing which API routes consume the most calls for optimization  ✅
- **B.** Daily usage totals are sufficient for most customers to understand their API consumption patterns
- **C.** Endpoint-level data is too granular for most customers and adds unnecessary dashboard complexity
- **D.** Total call count is the only metric that matters for billing and should be the primary focus

> **Answer:** A

### Q23. Your 'Usage Alert' emails customers at 80% of their limit — but only checks once daily. A customer hits 80% at 9am and exceeds 100% by noon without ever being notified. What should change?

- **A.** Daily threshold checks are frequent enough for most customers' usage monitoring requirements
- **B.** Check usage thresholds every hour instead of running a single daily batch job for detection
- **C.** Check thresholds in real-time or near-real-time — trigger alerts when crossed, not on a daily batch  ✅
- **D.** Only alert customers at 100% usage — the 80% warning threshold creates unnecessary notification noise

> **Answer:** C

### Q24. A customer's runaway script makes 2 million excess calls overnight. Their bill jumps from $99 to $20,099. They're furious. What safeguard should exist?

- **A.** Customers rarely check usage data so investing in a detailed dashboard isn't worth the effort now
- **B.** Provide a downloadable CSV export of raw usage logs that technical customers can analyze on their own
- **C.** Email the customer a usage summary at the end of each month when they receive their invoice
- **D.** A real-time usage dashboard showing consumption, remaining quota, and projected overage costs  ✅

> **Answer:** D

### Q25. Your rate limiter blocks with 429 but doesn't log who gets throttled or how often. A Pro customer says they hit limits daily. You can't verify. What should be tracked?

- **A.** Log every throttle event — account, endpoint, and timestamp — so reports can be verified  ✅
- **B.** Customer reports of throttling are reliable enough that logs aren't worth the overhead
- **C.** Only log throttle events for Enterprise accounts since they generate the most support tickets
- **D.** Sample one throttled request per hour to keep logging costs low while spotting the trends

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/103821135_
