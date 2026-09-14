---
course: "The Foundation"
module: "Layer 11: Load Balancing & Scaling"
lesson: "Layer 11: Load Balancing & Scaling — Exam"
type: "course_quiz"
post_id: 102901642
space_id: 23777123
source: "https://the-faction.mn.co/posts/102901642"
updated: "2026-08-21T15:06:30Z"
---

# Layer 11: Load Balancing & Scaling — Exam

> Exam for **Layer 11: Load Balancing & Scaling** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A user reports slowness. One server sits at 95% CPU while another idles at 10%. What is missing from your setup?

- **A.** The busy server most likely picked up a virus or some malware process that is quietly consuming nearly all of its available resources
- **B.** The two servers are running on completely different hardware specifications, so one of them simply finishes its work far sooner
- **C.** The idle server was never properly activated or connected to the network and has been sitting in standby mode since the deployment
- **D.** A load balancer is missing or misconfigured. It should distribute incoming user traffic evenly across all available server copies  ✅

> **Answer:** D

### Q2. Single server runs out of memory during peak. Should you make it bigger or add more servers?

- **A.** Add more servers via horizontal scaling. There is no upper limit on copies, and if one server crashes the others keep handling traffic  ✅
- **B.** Always make the single server bigger, since one large machine is simpler to reason about and upgrading it is the most reliable fix available
- **C.** Shut the application down during the busiest peak hours and bring it back online once the traffic level drops to something manageable
- **D.** Delete older data from the database on a schedule to free up working memory and make more room for the currently active user sessions

> **Answer:** A

### Q3. Your AI set up auto-scaling. How do you verify it actually works before real users arrive?

- **A.** Run a load test simulating hundreds of concurrent users with a tool like k6 or Artillery, then confirm new server copies spin up automatically  ✅
- **B.** Review the auto-scaling configuration settings line by line and trust that they will work correctly once real production traffic arrives
- **C.** Wait for real user traffic to arrive after the launch and then monitor whether the system responds properly while people are actually using it
- **D.** Contact the hosting provider's support team directly and ask them to confirm that your scaling setup will work when traffic finally arrives

> **Answer:** A

### Q4. App auto-scaled to 20 copies overnight with zero users, running up costs. What went wrong?

- **A.** Twenty copies is the normal minimum baseline that every auto-scaling setup requires before it can safely accept production traffic
- **B.** Auto-scaling systems are deliberately designed to always run at full capacity around the clock so users never experience slow responses
- **C.** Cloud billing systems commonly overcharge accounts during overnight hours because of rate changes that apply outside business hours
- **D.** Auto-scaling had no maximum limit or used incorrect triggers, so it kept spinning up copies despite having zero actual user demand  ✅

> **Answer:** D

### Q5. User logs in, adds cart items, gets routed to a different server, and the cart is empty. What is the problem?

- **A.** Cart data was stored in that server's local memory instead of a shared store, so the second server has no record of the cart items  ✅
- **B.** The user's browser silently lost its session cookies while navigating between the different pages, so the site treated them as a new visitor
- **C.** The load balancer accidentally deleted the cart data while it was rerouting the request from one application server to another
- **D.** The user was unknowingly redirected to a completely different website by mistake and started a brand new shopping session on that site

> **Answer:** A

### Q6. One of three app copies crashed but the load balancer keeps sending traffic to it. What is missing?

- **A.** The crashed copy simply needs a bigger server with more resources allocated to it so that it can recover from the crash without help
- **B.** The load balancer requires a complete manual restart every single time any copy goes down, and nobody on the project has restarted it yet
- **C.** You need to add several more copies to the pool so that the crashed one receives a smaller share of the incoming traffic and matters less
- **D.** Health checks are missing. The load balancer should automatically test each copy and remove any unresponsive ones from the rotation  ✅

> **Answer:** D

### Q7. Launching a simple app, want load balancing without managing servers yourself. What platform type?

- **A.** Purchase a physical server for your office and install, patch, and tune all of the load balancing software on it yourself before you launch
- **B.** Use a managed platform like Vercel, Fly.io, or Railway that includes built-in load balancing and auto-scaling so you focus on your product  ✅
- **C.** Hire a full-time DevOps engineer to configure and maintain all of the routing infrastructure for you before the application goes live
- **D.** Run the production application directly on your personal laptop from your home network and add a second laptop whenever traffic grows

> **Answer:** B

### Q8. Your AI set up a single server. Traffic will grow 10x. Why is a single server a problem?

- **A.** Every server has finite CPU, memory, and bandwidth. When traffic exceeds those limits the server slows down and eventually crashes entirely  ✅
- **B.** Single servers are inherently unreliable regardless of how much traffic they handle, so the hardware will fail long before traffic grows
- **C.** A single server can only ever serve one user at a time, so every other request gets queued behind the first one until that visitor finishes
- **D.** Servers automatically shut themselves down after processing one thousand total requests, and ten times the traffic reaches that limit sooner

> **Answer:** A

### Q9. AI asks: horizontal or vertical scaling? You expect traffic spikes and want resilience. Which do you choose?

- **A.** Vertical scaling with a bigger single server, since one powerful machine can absorb all of the incoming traffic spikes
- **B.** Both horizontal and vertical scaling must always be deployed at the same time together, because neither approach ever works properly alone
- **C.** Neither type of scaling is needed, since any modern server can already handle whatever amount of traffic your launch brings in
- **D.** Horizontal scaling. Multiple copies means no upper limit on capacity, and if one copy crashes the others keep serving users  ✅

> **Answer:** D

### Q10. You want your app to handle traffic spikes automatically. What do you tell your AI to configure?

- **A.** Purchase the largest single server available from your provider so that it can absorb every potential traffic spike that might ever arrive
- **B.** Schedule additional servers to run only during standard business hours on weekdays, which keeps the monthly hosting costs down
- **C.** Set up auto-scaling with a minimum number of copies, a maximum for cost control, and a trigger metric like CPU usage or request count  ✅
- **D.** Limit the number of users who are allowed to access the application at any given time so the servers can never become overloaded

> **Answer:** C

### Q11. What does a load balancer actually do when a new user visits your app?

- **A.** The user connects directly to one random server without any routing logic being applied anywhere along the path of the request
- **B.** The load balancer rebuilds the entire page from scratch using its own hardware before delivering the finished copy of that page to the user
- **C.** The load balancer stores a full copy of all of the user's personal data before routing the request onward to an application server
- **D.** It receives the request and routes it to the least busy copy. The user never sees this happen and just experiences a fast, responsive app  ✅

> **Answer:** D

### Q12. What is the vibecoder scaling workflow?

- **A.** Let the AI configure everything perfectly on the first attempt and never bother to verify the results, since modern tooling rarely makes mistakes
- **B.** Describe your expected traffic patterns to AI, let it configure scaling, test with load tools, verify results, iterate, and ship confidently  ✅
- **C.** Manually configure every single scaling setting yourself without any AI assistance at all, because scaling is too important to delegate
- **D.** Deploy the application straight to production immediately and just wait for real problems to surface before thinking about scaling at all

> **Answer:** B

### Q13. App live 3 months, never load-tested, about to launch a big campaign. What pitfall is this?

- **A.** The application does not yet have enough features to attract the campaign audience, so the launch will underperform no matter what happens
- **B.** Never load-testing before a launch means it works for you alone but was never verified under real concurrent traffic conditions  ✅
- **C.** The marketing campaign itself is insufficient and needs more channels and a much bigger budget allocated before it can succeed
- **D.** The application has too many pages in its sitemap, which makes it inherently slower for every visitor who arrives from the campaign

> **Answer:** B

### Q14. Two servers, users randomly logged out. Session data lives in each server's local memory. What pitfall?

- **A.** Sessions stored on individual servers instead of a shared store like Redis. When users get routed to a different server, their session is lost  ✅
- **B.** The authentication system is simply outdated and randomly drops user sessions even under completely normal day-to-day production use
- **C.** Two servers is just not enough capacity for the current load, and adding a few more copies of the app would resolve the logout issues entirely
- **D.** The wrong type of load balancer was selected during setup, and that specific model is known to cause random authentication failures

> **Answer:** A

### Q15. App works locally with one DB connection. Five production copies cause 'too many connections' errors. What happened?

- **A.** The database engine on your laptop simply performs better than the cloud production database that the deployment is using
- **B.** Database connection limits were ignored. Multiple app copies each open many connections, which overwhelms the database's maximum pool  ✅
- **C.** The database software itself is buggy and cannot handle a normal production workload, so the vendor needs to ship a fix before you scale
- **D.** The database schema has accumulated too many tables, which starts causing connection errors once traffic climbs to higher levels

> **Answer:** B

### Q16. Auto-scaling with no maximum set. A bot triggers 200 copies overnight and a $5K bill arrives. What pitfall?

- **A.** Auto-scaling for an app of this size always costs about this much every month, no matter how the configuration settings are arranged
- **B.** The cloud provider overcharged your account because of a billing error on their platform, and support will refund the difference
- **C.** Auto-scaling without a maximum cap means a bot or bug can spin up unlimited copies, generating massive and unexpected cloud costs  ✅
- **D.** A competitor deliberately deployed a bot specifically to attack your infrastructure and inflate your monthly hosting costs

> **Answer:** C

### Q17. Three copies running, one crashes, but traffic still routes to it for 15 minutes. What is missing?

- **A.** You need to buy crash-proof servers that are guaranteed by the manufacturer to never go down under any operating conditions
- **B.** Adding more copies to the pool would reduce the impact that any single crashed copy has on the overall flow of traffic
- **C.** Health checks are missing. Without them the load balancer has no way to detect a crashed copy and keeps routing traffic to it  ✅
- **D.** Physical monitoring staff in the server room should have caught the crash right away and rerouted the traffic manually

> **Answer:** C

### Q18. Scaled to 10 app copies but the single database is now the bottleneck. What was missed?

- **A.** You also need exactly ten frontend copies deployed so that they match the number of backend app server copies one to one
- **B.** Databases never actually need any scaling work, because every modern database engine handles unlimited connections automatically
- **C.** Ten app copies is simply far too many, and reducing the count back down to a handful would eliminate the bottleneck issue entirely
- **D.** The app servers were scaled but the database was forgotten. A single DB becomes the bottleneck no matter how many app copies exist  ✅

> **Answer:** D

### Q19. Why does an app that works fine for ten users crash when a thousand show up?

- **A.** Applications ship with a fixed maximum of ten concurrent users by default, and nothing beyond that number is allowed in until you change a setting
- **B.** The internet itself can only handle about ten simultaneous connections to any single server before the routing between them breaks down
- **C.** A server has limited CPU, memory, and bandwidth. Ten users stay within limits but a thousand exceeds capacity, causing slowdowns and crashes  ✅
- **D.** Web browsers impose strict visitor limits that prevent more than ten users from connecting to the same small site at the same moment

> **Answer:** C

### Q20. Horizontal vs vertical scaling: what is the difference and which should you direct your AI to implement?

- **A.** Vertical means a bigger single server but has limits and one failure point. Horizontal adds copies with no cap and built-in redundancy  ✅
- **B.** Vertical scaling means adding more databases to the stack, while horizontal scaling means adding more app server copies behind the balancer
- **C.** They are exactly the same technique under two different names, and both of them produce identical scaling results in production
- **D.** Horizontal scaling is always significantly more expensive than vertical scaling, so budget-conscious teams should never choose it

> **Answer:** A

### Q21. You need to verify your app handles traffic before launch. What should you do?

- **A.** Launch the application on schedule and simply hope that everything works out fine once the real user traffic starts arriving
- **B.** Ask a few friends to visit the site simultaneously from their homes and see if it still feels responsive enough while they browse around
- **C.** Run a load test with k6 or Artillery simulating concurrent users, then check response times, error rates, and auto-scaling behavior  ✅
- **D.** Review the server specifications on paper and assume that they will comfortably handle the expected traffic volume on launch day

> **Answer:** C

### Q22. Describe what a load balancer does in plain terms.

- **A.** It is a dedicated backup server that sits idle and only activates to begin serving pages after your main production server has crashed completely
- **B.** A traffic cop that distributes incoming requests across multiple app copies so no single copy gets overwhelmed and users stay on a fast app  ✅
- **C.** A file compression tool that shrinks the size of every asset before sending it down to the user so that each page arrives a little faster
- **D.** A firewall that inspects and blocks malicious traffic and prevents any unauthorized access from ever reaching your application servers

> **Answer:** B

### Q23. You set auto-scaling to add a server at 80% CPU, but users still see slow responses during the first minutes of a traffic spike. Why?

- **A.** New copies need time to boot and warm up, so the trigger should fire at a lower threshold to have capacity ready before saturation  ✅
- **B.** The trigger metric is wrong, because CPU never reflects real load and scaling should be driven only by the count of connected users
- **C.** Auto-scaling responds only to scheduled traffic patterns and cannot react to any spike that was not configured well in advance
- **D.** The maximum copy limit was reached instantly, which is the only reason a correctly scaled service would ever still respond slowly

> **Answer:** A

### Q24. A user says your app is slow. What metrics should you check first?

- **A.** Total page count and the color scheme, since using too many distinct colors can measurably slow down how quickly the pages render
- **B.** Response time to measure speed, error rate to catch failures, and server CPU usage to see if the machine is maxed out under load  ✅
- **C.** The total number of images and fonts being loaded, since heavy assets like those are almost always the sole cause of any slowness report
- **D.** The user's email address and geographic location, which together determine the quality of the internet connection they are using

> **Answer:** B

### Q25. Your app crashed when a popular blog linked to it. What happened and what should you have directed your AI to set up?

- **A.** The domain registration unexpectedly expired overnight and caused the entire application to go offline
- **B.** The blog post itself contained a virus that infected your hosting server environment and compromised security
- **C.** A single server got overwhelmed by the traffic surge, which load balancing and auto-scaling would have prevented  ✅
- **D.** The database corrupted itself and then deleted all of the stored records automatically and permanently

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/102901642_
