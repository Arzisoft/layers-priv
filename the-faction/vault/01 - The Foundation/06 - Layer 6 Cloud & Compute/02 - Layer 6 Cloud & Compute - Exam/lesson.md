---
course: "The Foundation"
module: "Layer 6: Cloud & Compute"
lesson: "Layer 6: Cloud & Compute — Exam"
type: "course_quiz"
post_id: 102901514
space_id: 23777123
source: "https://the-faction.mn.co/posts/102901514"
updated: "2026-08-20T23:47:54Z"
---

# Layer 6: Cloud & Compute — Exam

> Exam for **Layer 6: Cloud & Compute** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your app is on Vercel and a friend asks where the code actually runs. You want an accurate, plain-language answer. Which is correct?

- **A.** It runs on your own personal laptop, which must stay powered on and connected to the internet at every moment, because visitors are connecting straight to your machine
- **B.** It runs entirely inside each visitor's web browser after the page loads, with no server or backend infrastructure involved at any point in handling requests
- **C.** It runs on Vercel's own proprietary hardware, which the company designs, manufactures, and operates itself inside private facilities that it fully owns and controls
- **D.** It runs on servers in data centers owned by cloud providers like AWS. Vercel manages the cloud details, but underneath it rents compute from major providers.  ✅

> **Answer:** D

### Q2. Your hosting bill jumped from $0 to $45. No new features were added, but your app was shared in a popular community last week. What should you check first?

- **A.** Your hosting platform's usage dashboard to see which resources spiked — function invocations, bandwidth, or storage — since the community share likely drove more traffic.  ✅
- **B.** Whether your hosting provider quietly raised its pricing tiers this month for every customer on the platform, since a platform-wide increase would explain the unexpected charge
- **C.** Whether your domain name registrar charged you a separate annual renewal fee that happened to show up on the same billing cycle as your regular monthly hosting subscription
- **D.** Your local development environment logs, to check whether a bug somewhere in your code is silently generating the unexpected charges every time you run the app locally

> **Answer:** A

### Q3. Your app resizes user-uploaded photos on a serverless platform. Last month it processed 50,000 images. Is this a good use of serverless?

- **A.** No — serverless platforms cannot handle image processing workloads, because resizing images requires far more memory allocation than any function is ever permitted to use
- **B.** Yes — serverless is ideal for on-demand tasks like image resizing, but you should watch for cost increases as invocations grow since you pay per execution.  ✅
- **C.** Yes — serverless means that all of your image processing is completely free forever, no matter how many invocations your users generate against the platform each month
- **D.** No — serverless is designed only for lightweight database queries, so heavier file processing jobs like photo resizing must run on a dedicated machine

> **Answer:** B

### Q4. You are on a free plan with 100K serverless invocations per month. Your app gets featured on social media and traffic spikes. What happens at the limit?

- **A.** The hosting platform automatically deletes your entire deployment along with all of its associated data, as a protective measure designed to prevent you from being overcharged
- **B.** Nothing happens at the limit — free tier caps are only advisory guidelines, and hosting platforms do not actually enforce them against real production applications
- **C.** You start getting charged for usage beyond the free tier limits. This is one of the most common surprise bill scenarios — traffic spikes blow past the free tier.  ✅
- **D.** Your app simply continues to work normally forever, because serverless compute is always provided free of charge on every major hosting platform regardless of usage

> **Answer:** C

### Q5. Your monthly cloud bill shows high compute charges but very low storage charges. What does this pattern tell you about your app's resource usage?

- **A.** Your app is storing far too many files on the platform, and you need to delete your older data immediately in order to bring the monthly charges back down to normal
- **B.** Your app is fundamentally broken, because high compute charges are always a sign of code errors or badly misconfigured services somewhere in the stack
- **C.** Your app is doing heavy processing work (CPU and memory) but not storing much data — typical of apps that do real-time calculations or frequent API calls.  ✅
- **D.** You are being overcharged by the provider, because compute costs should always come in lower than storage costs on every cloud platform when billing works correctly

> **Answer:** C

### Q6. Your app serves 2MB product images on every page load and your cloud bill spiked. Which cost category is likely causing this, and what is a simple fix?

- **A.** Compute costs — you need to upgrade your plan to a faster and more powerful server tier so that the large product images can be processed and sent to users much more quickly
- **B.** Data transfer costs — compress images, use smaller file sizes, or serve them through a CDN to cut the bandwidth charges from large files hitting users on every load.  ✅
- **C.** Storage costs — you should delete every image from your hosting account and replace each one with a plain text description so nothing large is ever kept on the platform
- **D.** Domain registration costs — you should switch over to a cheaper domain registrar in order to lower the recurring annual fees that are currently attached to your account

> **Answer:** B

### Q7. You need a simple API endpoint handling 500 requests per day. You are choosing between serverless functions and a dedicated server. Which is better and why?

- **A.** Serverless functions — at 500 requests per day you only pay for actual usage instead of keeping a server running 24/7, which wastes money on idle time.  ✅
- **B.** A dedicated server, because 500 requests per day far exceeds the processing capacity that serverless functions are able to reliably handle without dropping requests
- **C.** A dedicated server, because serverless functions were never designed to process or respond to API requests of any kind and cannot serve endpoints like this one
- **D.** Neither option — any API endpoint, regardless of its scale, requires a full multi-cloud architecture spread across several providers to function correctly

> **Answer:** A

### Q8. Your AI tool generated code that calls a weather API on every page load, but weather data only changes hourly. What is the cost risk and the fix?

- **A.** There is no real cost risk in this setup, because weather API calls are always free on every major platform, and therefore no fix of any kind is actually needed for this code
- **B.** The risk is that users will occasionally see slightly stale weather data, so the correct fix is to increase the API call frequency even further beyond once per page load
- **C.** The risk is unnecessary API calls and compute costs on every page load. Direct the AI to cache weather data and only fetch fresh data hourly instead of on every request.  ✅
- **D.** The risk is security, because weather APIs can expose private user data to outside parties. The appropriate fix is to remove the weather feature from the application entirely

> **Answer:** C

### Q9. A colleague says your app is serverless, so the team does not need to worry about servers at all. Is this accurate?

- **A.** Yes — serverless literally means that no servers exist anywhere at any step, from the moment a request arrives to the moment the response is delivered back
- **B.** Yes — serverless applications run entirely in each user's own browser, with zero server components involved at any point in how the product actually operates
- **C.** No — serverless is purely a marketing term with no real technical meaning behind it, and it always ends up costing more than simply running regular servers
- **D.** No — serverless means you do not manage the server yourself, but your code still runs on servers owned and operated by the cloud provider behind the scenes.  ✅

> **Answer:** D

### Q10. You are explaining cloud computing to a non-technical partner. Which analogy best describes how cloud computing works?

- **A.** It is like buying a house outright — you own everything, you keep full control over the entire property, and you never pay any recurring fees to anyone
- **B.** It is like building your own private data center — very expensive up front, but dramatically cheaper than any alternative over the long term
- **C.** It is like renting an apartment — flexible, on-demand, and you do not own the infrastructure, but your costs can change as your usage grows.  ✅
- **D.** It is like borrowing a friend's laptop — completely free and unlimited to use, but unreliable and only available to you some of the time

> **Answer:** C

### Q11. Your app is growing and you want to understand what compute means on your cloud bill. Which best describes compute in cloud billing?

- **A.** Compute refers to the cost of your domain name registration together with the recurring DNS hosting fees that you pay to keep the name active and resolving
- **B.** Compute is the processing power — the actual CPU time and memory your app uses to do work like loading pages, processing forms, or resizing images.  ✅
- **C.** Compute refers to the total amount of disk space that your files and your database records consume on the hosting platform's storage systems
- **D.** Compute is a fixed flat monthly fee that stays exactly the same regardless of how much traffic or processing work your app actually handles

> **Answer:** B

### Q12. You are launching a side project on a hosting platform's free tier. What is the most important thing to understand before going live?

- **A.** Free tiers last forever with absolutely no usage limits attached — once your app qualifies for the free plan, it stays completely free no matter how large it eventually grows
- **B.** Free tiers have hard limits on compute, storage, and data transfer. If your app exceeds those limits, you start getting charged — know the thresholds before launch.  ✅
- **C.** Free tiers only work for applications built with the specific programming languages and frameworks that the hosting platform has chosen to officially support
- **D.** Free tiers are only available during the first 24 hours after your initial deployment, after which the platform automatically switches you over to a paid plan

> **Answer:** B

### Q13. You want to understand your cloud spending before the monthly bill arrives. Which tool should you check first and how often?

- **A.** Your bank account — wait for the charge to appear on a statement, and then dispute it through your bank if the amount seems wrong to you
- **B.** Your email inbox — check it once a quarter for invoices, and only review the individual line-item charges if a total on one of them looks unusually high
- **C.** Your code editor's built-in cost calculator — check it every time you push code so you can estimate the resource impact of each change
- **D.** Your hosting platform's billing dashboard — check it weekly so you catch spending trends early, rather than waiting for the monthly bill to arrive.  ✅

> **Answer:** D

### Q14. You ran your app for three months without checking your cloud bill. You just got a $280 charge for last month. What pitfall does this illustrate?

- **A.** Not using enough serverless functions across your architecture, which leads directly to over-provisioned resources and wasted spending on the platform every month
- **B.** Using too many different programming languages inside one app, which creates unnecessary processing overhead and steadily increases your cloud resource usage
- **C.** Deploying your application to too many cloud regions at the same time, which multiplies your compute costs once for every additional region you have enabled
- **D.** Never checking your cloud bill regularly — by the time you see it, a runaway function or misconfigured service may have been burning money for weeks unchecked.  ✅

> **Answer:** D

### Q15. A builder says their app is serverless so they do not need to worry about costs. Why is this thinking dangerous?

- **A.** Because serverless means you pay per execution — if your function fires on every page load and traffic grows, those pennies per call add up to real money fast.  ✅
- **B.** Because serverless is always more expensive than running dedicated servers, in every single usage scenario, so the bill is guaranteed to keep climbing
- **C.** Because serverless apps cannot scale beyond their initial platform limits, and will simply crash long before they ever manage to generate a real bill
- **D.** Because serverless platforms charge one fixed monthly subscription fee that stays exactly the same regardless of how much or how little you actually use the service

> **Answer:** A

### Q16. Your AI tool set up a cloud database and got everything working, but your bill is higher than expected. What pitfall likely occurred?

- **A.** You let AI pick cloud services without understanding the pricing model. AI optimizes for working code, not cost-effective code — always ask what it costs at scale.  ✅
- **B.** The database is storing too many separate tables, which increases your cloud costs exponentially with each additional table that your application creates
- **C.** The AI intentionally selected the single most expensive database service available on the market, in a deliberate attempt to sabotage your project and drain your budget
- **D.** AI tools are technically unable to connect to cloud databases at all, so every one of those database charges on your bill must actually be a billing error

> **Answer:** A

### Q17. Your app only gets traffic 9-5 on weekdays, but your cloud bill is the same every day including nights and weekends. What is happening?

- **A.** Cloud providers always charge one flat rate no matter when your traffic occurs, so the timing of usage never has any effect on what shows up on your monthly billing
- **B.** You are running compute resources 24/7 when your app only has traffic 8 hours a day — paying for 16 hours of idle servers. Auto-scaling or serverless would fix this.  ✅
- **C.** The charges during nights and weekends are for mandatory cloud maintenance windows, which every provider runs on a fixed schedule that customers cannot change
- **D.** Your app is being accessed by automated bots during the off-hours, which is perfectly normal, expected behavior and simply a routine part of operating anything on the internet

> **Answer:** B

### Q18. Your data transfer charges are higher than compute charges. You only optimized processing time. What pitfall did you fall into?

- **A.** Using too many serverless functions instead of containers, which generates excessive per-invocation overhead and networking charges across your whole architecture
- **B.** Using a CDN, which always increases data transfer costs when compared with serving every piece of content directly from the origin server yourself
- **C.** Ignoring data transfer costs — moving data between services and out to users often costs more than compute, especially with large images and uncompressed assets.  ✅
- **D.** Deploying your app into the wrong cloud region, which adds latency-based fees along with cross-region data transfer surcharges to your monthly bill

> **Answer:** C

### Q19. You deployed your app last month and got a surprise $150 cloud bill. You never set up spending notifications. What should you have done on day one?

- **A.** Deployed your app to multiple cloud providers at the same time, so that the total cost would be split evenly across the different platforms' bills
- **B.** Set up a VPN to hide your application from the cloud platform's billing systems entirely, so that your usage is never tracked and never gets charged to your account
- **C.** Disabled all application logging on day one, to reduce the total amount of data that gets processed and stored on the platform as your traffic grows
- **D.** Set up billing alerts with a budget so you get notified when spending approaches your limit — every cloud platform supports this and it takes minutes to configure.  ✅

> **Answer:** D

### Q20. An investor asks where your app's code actually runs when a user visits your site. Which answer demonstrates genuine cloud literacy?

- **A.** It runs on my personal laptop, which I keep plugged in and connected to the internet around the clock so that the product stays up whenever anyone wants to visit
- **B.** It runs on servers in data centers owned by our cloud provider. When a user visits, their request hits those servers, which execute our code and return the response.  ✅
- **C.** It runs entirely inside each user's phone or computer once the page has finished loading — there is no server or backend infrastructure involved anywhere in the product
- **D.** I am not completely sure — my AI coding tool handles all of that infrastructure for the company, and I have honestly never looked into how any of it actually works

> **Answer:** B

### Q21. Your co-founder asks what you pay for cloud services and which cost the most. You are not sure. What does this indicate about your readiness?

- **A.** This is a gap in your operational knowledge. You should know your monthly cloud spending and which services are the biggest cost drivers at all times.  ✅
- **B.** This is totally fine — most successful founders do not bother tracking their cloud costs at all until the company reaches genuine enterprise scale
- **C.** This is expected — cloud costs are intentionally unpredictable and unknowable by design, so practically no founder ever tries to track them closely
- **D.** This only matters once your cloud spending exceeds $10,000 per month — below that spending threshold, the numbers are simply not worth anyone's time to track

> **Answer:** A

### Q22. You just launched your app. What is the very first billing-related step you should complete before getting significant traffic?

- **A.** Negotiate a discounted enterprise contract with your cloud provider based on projected volume, before any real traffic has even started hitting your app
- **B.** Hire a full-time DevOps engineer whose primary responsibility is to manually monitor your cloud costs every single day and report anything unusual
- **C.** Pre-pay for a full 12 months of compute resources up front, in order to lock in the current pricing before the provider's rates have a chance to increase
- **D.** Set up billing alerts so you get notified if cloud spending spikes unexpectedly — every platform supports this and it should be configured on day one.  ✅

> **Answer:** D

### Q23. Someone asks you to explain serverless functions versus a traditional server. Why does this distinction matter for your cloud bill?

- **A.** Traditional servers are always the cheaper choice for a growing product, because they never charge you per execution the way serverless platforms are designed to do
- **B.** It does not matter at all for billing purposes — serverless functions and traditional servers will end up costing you exactly the same total amount in every realistic usage scenario
- **C.** Serverless charges per execution and sits idle for free, while traditional servers run 24/7 and charge regardless of traffic. Choosing wrong means paying for idle resources.  ✅
- **D.** Serverless functions are always cheaper regardless of workload, because the major cloud providers heavily subsidize them as a strategy to attract brand new customers

> **Answer:** C

### Q24. Your app is on a free tier with 100K invocations and 100GB bandwidth per month. You are at 85,000 invocations. What should you do?

- **A.** You are close to exceeding free tier limits. Investigate what is driving high invocations and optimize before you cross the threshold and start getting charged.  ✅
- **B.** Immediately delete your entire app and start the whole project over again from scratch on a completely different hosting platform with a much more generous free tier
- **C.** Nothing — you are still technically under the monthly limit, so there is absolutely no reason for you to take any kind of action on the account yet
- **D.** Switch the account to an enterprise plan immediately, to avoid any potential overage charges that might otherwise appear on your next monthly bill

> **Answer:** A

### Q25. A blog post about your product just went viral and you expect 10x traffic tomorrow. You have not prepared. What are the two main concerns?

- **A.** Your cloud costs could spike dramatically from the surge, and your app's performance could degrade or crash if it is not configured to handle the load.  ✅
- **B.** Your database schema might begin changing automatically under the heavy traffic, and your front-end CSS styling might break for a portion of your visitors
- **C.** Your source code might become publicly visible while the app is under load, and your AI coding tool might stop working entirely at the worst moment
- **D.** Your domain name might expire under the sudden load, and your logo might start rendering blurry on mobile devices for many of the new visitors

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/102901514_
