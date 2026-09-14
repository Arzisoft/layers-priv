---
course: "The Mastery"
module: "Module 7 — Monitoring & Observability"
lesson: "Module 07: Production Monitoring for SaaS — Exam"
type: "course_quiz"
post_id: 103821140
space_id: 24191170
source: "https://the-faction.mn.co/posts/103821140"
updated: "2026-08-21T00:55:24Z"
---

# Module 07: Production Monitoring for SaaS — Exam

> Exam for **Module 7 — Monitoring & Observability** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your SaaS is down for 3 hours on a Tuesday. You find out because a customer emails. Your monitoring dashboard shows green. What's the likely problem?

- **A.** Health checks tested server status but not app health — the server ran while the app broke inside  ✅
- **B.** The customer is wrong — the app was working and they experienced a temporary local issue
- **C.** Monitoring can't catch every single issue — some failures are inherently undetectable by any system
- **D.** The customer had a local network problem that caused the app to appear down from their perspective

> **Answer:** A

### Q2. Your error tracking shows 47 errors in the last hour, all from one customer with a corrupted data record. Generic alerting treats this the same as a platform-wide incident. What's missing?

- **A.** 47 errors over a billing cycle doesn't warrant a full investigation by the engineering team on-call
- **B.** Tenant-aware error grouping — errors tagged with tenant_id to separate customer from platform  ✅
- **C.** Increase the alert threshold to reduce noise so the team only investigates significant error spikes
- **D.** Errors from single customers should be ignored unless they exceed a minimum volume threshold

> **Answer:** B

### Q3. Your Stripe webhook handler silently fails for 48 hours. No payments process, no subscriptions update. Monitoring misses it because the endpoint returns 200 on failures. What should exist?

- **A.** Webhook failures are Stripe's responsibility to handle — not something the platform should monitor
- **B.** Standard app monitoring already covers payment issues since Stripe sends error responses
- **C.** Dedicated billing pipeline monitoring — track webhook receipt rate and alert when events stop now  ✅
- **D.** Payment monitoring is only needed for Enterprise customers due to the higher financial impact involved

> **Answer:** C

### Q4. Logs say 'Error processing request' with no user ID, tenant ID, path, or stack trace. A customer reports a bug and you can't find anything useful. What should logs include?

- **A.** A single log message per request with the HTTP status code is enough for debugging most issues
- **B.** Log only errors — successful requests don't need logging because they indicate everything worked fine
- **C.** Record every database query, cache lookup, and external API call in separate log entries per request
- **D.** Structured logs with tenant_id, user_id, request path, request ID, and stack trace for full context  ✅

> **Answer:** D

### Q5. Alerts fire at 10 errors/minute. A marketing campaign drives 5x traffic and error rates hit 12/min — all normal validation errors. The team scrambles for a non-incident. What's the problem?

- **A.** The threshold is absolute not relative — it should use error RATE as a percentage, not raw COUNT  ✅
- **B.** 12 raw errors per minute is a threshold that warrants immediate investigation by the team
- **C.** Disable alerting entirely during high-traffic campaigns to avoid unnecessary alarm and distractions
- **D.** Increase the threshold to 50 errors per minute to reduce the number of false positive alerts fired

> **Answer:** A

### Q6. Your SLA promises 99.9% uptime, tracked by an internal health check from the same data center. A European customer has a 2-hour CDN outage but monitoring shows 100%. What's wrong?

- **A.** Internal health checks from the same data center are sufficient to verify uptime for customers
- **B.** External monitoring from multiple locations is needed — internal checks miss DNS or CDN failures  ✅
- **C.** Customers will report outages faster than any automated monitoring system can detect them reliably
- **D.** A single external ping from one location every five minutes provides sufficient uptime verification

> **Answer:** B

### Q7. All errors group by HTTP status. '500 Internal Server Error' has 340 hits — lumping database timeouts, null pointers, and API failures together. What's a better approach?

- **A.** Create separate monitoring dashboards for each error type to improve visibility overall
- **B.** HTTP status code grouping is sufficient for tracking and categorizing errors across the application
- **C.** Group by stack trace and root cause so each unique bug gets its own group with accurate counts  ✅
- **D.** Group errors by the specific endpoint that triggered them to see which routes are the most unstable

> **Answer:** C

### Q8. An enterprise customer's response times climb from 200ms to 1,800ms over 3 weeks. No alerts fire — you only alert on errors, not performance. They evaluate competitors. What catches this?

- **A.** Only monitor performance metrics for customers on top-tier plans who pay for premium support levels
- **B.** Performance monitoring isn't necessary if the app is functioning correctly and serving responses
- **C.** Check application performance during monthly reviews instead of monitoring it continuously in real-time
- **D.** Response time tracking with anomaly detection per tenant — alert when P95 trends upward beyond variance  ✅

> **Answer:** D

### Q9. An engineer debugging Tenant A's issue searches logs and accidentally sees Tenant B's sensitive business data in the results. What log architecture prevents this?

- **A.** Tenant-scoped log access — engineers see only logs for the tenant they're debugging with controls  ✅
- **B.** Give all engineers full access to all logs — any restrictions slow down incident response too much
- **C.** Restrict log access to senior engineers only since production logs contain sensitive customer data
- **D.** Store all logs in a shared spreadsheet the team reviews together during weekly sync meetings

> **Answer:** A

### Q10. Your Slack alert channel gets 30-50 alerts daily, mostly informational. A critical production issue gets buried and isn't seen for 2 hours. What's wrong?

- **A.** Move all alerts to email digests so the Slack channel stays quiet during business hours
- **B.** Severity tiers — critical alerts page the on-call, informational ones go to a digest channel  ✅
- **C.** Delete the alert channel entirely and rely on customers to report production issues right away
- **D.** Rotate which engineer watches the alert channel so every message gets read within minutes

> **Answer:** B

### Q11. Your app appears healthy but 15% of customers can't log in because a third-party auth provider has a partial outage. Your endpoint health checks didn't catch this. What's missing?

- **A.** Monitor the auth provider's status page manually each morning to stay informed about known outages
- **B.** Third-party service outages are completely outside your responsibility and shouldn't affect your SLA
- **C.** Synthetic user journey monitoring that simulates actual workflows end-to-end, not just endpoint checks  ✅
- **D.** Add the auth provider's health endpoint to your monitoring dashboard alongside your own service checks

> **Answer:** C

### Q12. Your incident process: the on-call engineer fixes it and moves on. No post-mortem, no documentation. The same incident type recurs 3 months later. What's missing?

- **A.** Create a knowledge base article for each incident so the team can reference it for similar future issues
- **B.** Not every production incident needs a formal post-mortem — some failures are straightforward fixes
- **C.** The engineer who was on-call should have identified and fixed the root cause the first time around
- **D.** Post-incident reviews documenting what happened, root cause, fix applied, and prevention steps tracked  ✅

> **Answer:** D

### Q13. Your dashboard has 12 metric panels. There's no single indicator for system health. Engineers scan all 12 panels to assess status. What should be added?

- **A.** A top-level health score that rolls the key metrics into one at-a-glance status indicator  ✅
- **B.** More metric panels so every subsystem is visible on the dashboard at the same time
- **C.** A rotating on-call engineer assigned to watch all twelve panels throughout the day
- **D.** Color-code each panel border so unhealthy metrics stand out from the healthy panels faster

> **Answer:** A

### Q14. Your app logs every database query at DEBUG level in production. Log volume is 2GB/day. Storage costs $400/month and search takes minutes. What should change?

- **A.** Log every database query at DEBUG level including the results to have complete investigation data
- **B.** Use INFO for normal operations and DEBUG for investigation — log slow queries and errors only  ✅
- **C.** Disable all query logging in production to avoid overhead from excessive log volume
- **D.** Store all database logs in a separate system from application logs for better data organization

> **Answer:** B

### Q15. 'Connection timeout' errors spike every day at 2am for exactly 5 minutes. The team investigates each time and finds nothing wrong. What's likely happening?

- **A.** Database connection spikes at 2am mean a hardware failure is imminent — replace the server
- **B.** The database automatically runs maintenance tasks at 2am and the connection spike is expected behavior
- **C.** A scheduled job like backup or batch is consuming database connections at 2am — check the schedule  ✅
- **D.** Users in a different timezone are likely causing the spike through normal application usage patterns

> **Answer:** C

### Q16. Your status page always shows 'All Systems Operational' because it's manually updated. During outages, customers see 'operational' and assume it's their problem. What should it be?

- **A.** Manual status page updates with better team discipline during incidents is the most reliable approach
- **B.** Status pages are optional and most customers don't check them when they experience issues with the app
- **C.** Only update the status page for outages lasting longer than one hour to avoid unnecessary noise
- **D.** Automated status updates driven by monitoring data so the page reflects actual status without delay  ✅

> **Answer:** D

### Q17. A customer reports their dashboard is slow. Global monitoring shows normal response times. You can't check response times for that specific customer. What's missing?

- **A.** Per-tenant performance monitoring — response time and error tracking scoped to each customer  ✅
- **B.** Ask the customer to run a speed test from their location and share the full results
- **C.** Global performance metrics are sufficient for monitoring across the entire customer base at scale
- **D.** Monitor the customer's internet connection quality to rule out client-side networking issues first

> **Answer:** A

### Q18. Your error tracking captures full request bodies including passwords and credit card numbers. This data sits in your third-party error tracking service. What's the risk?

- **A.** Tracking services are internal tools so sending raw user data including PII is acceptable practice
- **B.** Only anonymize data for users in the European Union since other regions have fewer privacy regulations
- **C.** Sensitive fields must be scrubbed before sending to tracking — PII in third-party tools violates rules  ✅
- **D.** Collect all possible user data in tracking services and filter sensitive fields only in the dashboard views

> **Answer:** C

### Q19. Critical alerts go via email only. During a Saturday night outage, the on-call engineer doesn't check email for 4 hours. What escalation is missing?

- **A.** Engineers should check their email more frequently when they're on-call to catch critical alerts fast
- **B.** Multi-channel escalation — critical alerts should page via phone or push, with auto-escalation  ✅
- **C.** Set all alerts to low priority during off-hours to avoid disturbing the on-call engineer overnight
- **D.** Route all alerts through a shared Slack channel and trust on-call to check it regularly

> **Answer:** B

### Q20. Your app uses three microservices. A request fails but each service shows a different error. You spend 2 hours manually correlating logs across services. What should be implemented?

- **A.** Each service team should investigate their own logs independently when cross-service issues are reported
- **B.** Centralize all microservice logs into a single file and search through it when debugging system issues
- **C.** Add timestamps to every log entry and manually correlate events across the services by time
- **D.** Distributed tracing with correlation IDs — a unique request ID through all services to connect logs  ✅

> **Answer:** D

### Q21. You use Sentry for errors, Datadog for logs, UptimeRobot for uptime, and a separate performance tool. All four alert on the same incident, creating 4 threads. What consolidates this?

- **A.** A unified incident management system that correlates alerts from all sources into a single incident  ✅
- **B.** Disable alerts on all but the most important monitoring tool to reduce noise across the board
- **C.** Use only one monitoring tool and remove the rest to eliminate duplicate alerts from multiple systems
- **D.** Multiple alerts from different tools ensure that nothing important is missed during a production incident

> **Answer:** A

### Q22. Your team reviews dashboards only during incidents. Gradual trends — rising errors, growing latency, filling disk — go unnoticed until they cause outages. What practice catches these?

- **A.** Review monitoring dashboards quarterly to check whether the alerts are still relevant overall
- **B.** Regular operational reviews plus automated trend alerts when metrics move consistently the wrong way  ✅
- **C.** Only update monitoring configurations after a major incident reveals a gap in the current alerting setup
- **D.** Hire a dedicated monitoring engineer whose sole job is to keep the alert configurations current always

> **Answer:** B

### Q23. Your error tracking captures frontend JavaScript errors. Hundreds show 'Script error.' with no stack trace, file, or line number. They're useless for debugging. What's causing this?

- **A.** Client-side errors are the user's problem — the platform only needs to monitor server-side operations
- **B.** Client-side monitoring is only needed for mobile apps — web apps don't have front-end errors
- **C.** Cross-origin script errors are anonymized by browsers — add CORS headers and crossorigin for detail  ✅
- **D.** Browser compatibility issues are solved by telling customers to use the latest version of Chrome only

> **Answer:** C

### Q24. Your SLA guarantees 99.9% uptime (8.7 hrs/year). You've had 6 hours of downtime in Q1. Monitoring tracks total downtime but doesn't project breach risk. What reporting should exist?

- **A.** SLA monitoring is only needed for Enterprise plans since smaller plans lack strict uptime needs
- **B.** SLAs are legal commitments and should be tracked by the legal team rather than the engineering team
- **C.** Check SLA compliance manually at the end of each month when generating customer billing statements
- **D.** Automated SLA tracking that alerts before thresholds are breached — not discovered at invoice time  ✅

> **Answer:** D

### Q25. Your on-call covers weekdays only. A Saturday outage goes undetected until Monday — 40 hours of downtime for a 24/7 product. What needs to change?

- **A.** Round-the-clock on-call coverage with weekend rotation — a 24/7 product needs 24/7 response  ✅
- **B.** Ask customers to email a dedicated emergency address on weekends so someone sees the outage
- **C.** Schedule weekend deploys only — outages on Saturdays usually come from Friday releases anyway
- **D.** Accept weekend gaps as a cost of a small team and credit customers for the downtime hours

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/103821140_
