---
course: "The Foundation"
module: "Layer 9: Rate Limiting"
lesson: "Layer 9: Rate Limiting — Exam"
type: "course_quiz"
post_id: 102901615
space_id: 23777123
source: "https://the-faction.mn.co/posts/102901615"
updated: "2026-08-20T23:49:12Z"
---

# Layer 9: Rate Limiting — Exam

> Exam for **Layer 9: Rate Limiting** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI-built search calls a paid API on every keystroke. After a quiet weekend, the bill is $400. What rate limiting approach prevents this?

- **A.** Upgrade to a premium API plan that advertises unlimited calls, so that billing limits and per-request charges simply never apply to your account no matter how often the search fires
- **B.** Remove the search feature from the product entirely, because an API that charges you per call is never going to be sustainable once real visitors arrive
- **C.** Add a CAPTCHA challenge in front of every single search box interaction, so that only verified human users are ever able to trigger requests against the paid API
- **D.** Add debouncing so the API only fires after the user pauses typing, plus a per-user rate limit on the search endpoint to cap runaway costs from both normal use and abuse  ✅

> **Answer:** D

### Q2. A user gets a 429 error during normal browsing. You check and find your main data endpoint is limited to 5 requests per minute. What is most likely wrong?

- **A.** Five requests per minute is far too strict for normal browsing — you need to study real usage patterns and set a threshold that fits how people actually use your app  ✅
- **B.** The user almost certainly has malware running in their browser that is generating extra hidden requests in the background, and those invisible calls keep tripping the limit
- **C.** The 429 status code is a server-side bug in your hosting stack that has no actual connection to the rate limit settings you configured on the data endpoint
- **D.** The user simply needs to clear their browser cache and delete their cookies, because that is what resets the rate limit counter your server keeps for their session

> **Answer:** A

### Q3. Your app uses OpenAI, Google Maps, and Stripe. What billing safeguards should you configure before launch day?

- **A.** Set spending alerts and hard caps on all three providers, with alert thresholds below your budget limits so you get advance warning before costs spike  ✅
- **B.** Wait until well after launch day so that you can observe real usage data coming in first, and only then set billing alerts based on the actual patterns you saw
- **C.** Only configure spending alerts on your most expensive API provider, and plan to manually check the dashboards of the other two services every week
- **D.** Set one single combined billing alert on the credit card statement itself, so that it covers all three of the services together with one number

> **Answer:** A

### Q4. Your paid AI service API key was committed to a public GitHub repo two days ago. What should you do first?

- **A.** Delete the offending commit from your Git history with a force push, and assume that nobody managed to clone the repository or copy the key in the two days it sat exposed
- **B.** Revoke the exposed key immediately and generate a new one, then check your usage dashboard for unauthorized charges that may have occurred over the last two days  ✅
- **C.** Add the key file to your .gitignore right away, so that the credential cannot possibly be committed to the repository again by you or anyone else on a future push
- **D.** Switch the repository's visibility from public over to private, so that nobody else browsing GitHub is able to reach the exposed credentials from now on

> **Answer:** B

### Q5. Your app's login form has no rate limiting. Why is this a risk, and what limit would you set?

- **A.** Rate limiting login forms mostly just degrades the sign-in experience for every legitimate user you have, so requiring everyone to choose stronger passwords is the better and simpler fix
- **B.** It is not a real risk anymore, because every modern browser ships with its own built-in protections that detect and stop brute-force login attempts before they ever reach your server
- **C.** The only genuine risk here is server overload from the extra traffic, and that is something your hosting provider already detects and handles automatically for you
- **D.** Attackers can use automated tools to try thousands of passwords per minute — set a limit like 5 attempts per minute per IP to block brute-force attacks while letting real users log in  ✅

> **Answer:** D

### Q6. A paying customer sends 20 messages in a minute; your limit is 10. Should you throttle or block? What approach balances cost protection and UX?

- **A.** Block every request after the 10th message immediately, and display a hard error screen telling the paying customer that they must wait and try again in 60 seconds
- **B.** Remove the rate limit for paying customers entirely, because they are trusted users who have paid you money and are considered unlikely to ever abuse the messaging system
- **C.** Permanently ban any user account that exceeds the rate limit even once, in order to protect your API budget from unexpected overruns of any size
- **D.** Throttle after the 10th message by queuing extras and delivering them at a controlled pace, so every message sends without exceeding your cost threshold  ✅

> **Answer:** D

### Q7. API A costs $0.01/call (high quality), API B costs $0.001/call (lower quality). You get 10K calls/day. What matters most when choosing?

- **A.** Always pick the cheapest of the two options no matter what, because small per-call savings compound into very large totals across the thousands of requests your users will make
- **B.** Calculate the gap ($100 vs $10/day), then assess whether the quality difference impacts user satisfaction and retention enough to justify spending the extra $90 daily  ✅
- **C.** Always pick the highest quality option available, because the user experience it delivers matters far more than any cost difference between the two providers
- **D.** Use both of the APIs at the same time on every single search, and let the user pick whichever result they happen to like better on each individual request

> **Answer:** B

### Q8. You launched with rate limits last week. What metrics should you check to evaluate whether your rate limiting is working?

- **A.** Only review your monthly API bill once at the end of each billing cycle, scanning the statement for anomalies or line items that look larger than they reasonably should
- **B.** Check how many new users have signed up since launch week, in order to see whether the rate limits are scaring newly registered people away from the product
- **C.** Track 429 response counts, API usage trends over time, per-provider spending dashboards, and whether any endpoints show higher call volume than expected  ✅
- **D.** Ask your users directly, through a survey or a pinned support thread, whether any of them have experienced rate limiting issues anywhere in the app

> **Answer:** C

### Q9. You need to explain rate limiting to your AI builder tool. Which definition best describes what a rate limit actually does?

- **A.** A firewall rule that automatically detects suspicious IP addresses based on their request patterns and then blocks them from ever accessing any part of your server again
- **B.** A rule that restricts how many requests an endpoint can receive in a set time window, returning a 429 status code when the threshold is exceeded to signal the caller to slow down  ✅
- **C.** A database constraint that prevents duplicate or conflicting records from being created in your tables whenever two users happen to submit the same form at the same moment
- **D.** A pricing tier published by your API provider that determines exactly how much you are allowed to charge external customers for access to the API you have built on top of your own service

> **Answer:** B

### Q10. Your app has a homepage, profile page, AI search, login form, and contact page. Which endpoints are the highest priority for rate limiting?

- **A.** The AI search (costs money per request) and the login form (vulnerable to brute-force attacks) — those two carry the highest financial and security risk of all your endpoints  ✅
- **B.** Every endpoint in the application needs the exact same rate limits applied uniformly across it, because a protection scheme is only truly effective when no route is treated differently
- **C.** Only the homepage, because it receives by far the most overall traffic from visitors, search engine crawlers, and social media link previews of any page in your application
- **D.** Only the contact page, because every submission there triggers an outbound email and those messages could become genuinely expensive at a high enough sending volume

> **Answer:** A

### Q11. Your AI tool asks: billing alert or hard cap on your OpenAI usage? Budget is $200/month. What is the difference, and which should you use?

- **A.** A billing alert notifies you at a threshold so you can act; a hard cap automatically stops all calls at the limit. Set both — the alert warns you, the cap saves you if you miss it  ✅
- **B.** Hard caps are a feature made available only on expensive enterprise plans, so for a solo builder on a normal tier the billing alert is effectively your only practical safeguard option
- **C.** They are functionally identical safeguards, since both of them immediately stop every single API call the moment your account hits the configured spending limit for the month
- **D.** A billing alert is the setting that halts your application when spending gets too high, while a hard cap only sends you a notification so you can review the charges later

> **Answer:** A

### Q12. Setting up API keys for a paid service. Your AI tool asks: one key or multiple? You have dev and prod environments. What is best practice?

- **A.** Use one single shared API key across both of the environments, in order to keep your configuration simple and avoid any confusion about which key is which
- **B.** Create a unique API key for every individual user of your app, so that you can track exactly how much API usage each person generates
- **C.** Use separate API keys for dev and prod with independent limits, so a testing mishap never drains your production budget or disrupts live users  ✅
- **D.** Only use an API key in production — your development environment should call the API without any authentication so that test calls stay free

> **Answer:** C

### Q13. Your AI tool offers throttling or blocking for users who exceed the rate limit on file uploads. What is the practical difference?

- **A.** Throttling and blocking are effectively the same mechanism under the hood, because both of them stop all incoming requests immediately the moment the limit is detected as exceeded
- **B.** Throttling permanently reduces the user's allowed request speed for the remaining life of their account, while blocking only ever pauses them temporarily
- **C.** Throttling applies only to users on mobile connections, while blocking is the underlying mechanism that works consistently across every platform you ship to
- **D.** Throttling slows requests so the user continues at a reduced pace, while blocking halts requests entirely and tells the user to wait for a cooldown period before retrying  ✅

> **Answer:** D

### Q14. A fellow vibecoder says: 'I only have 50 users, so I don't need rate limits yet.' Is that a safe assumption?

- **A.** Yes — rate limits only become relevant once you reach many thousands of users with significant daily traffic, and a 50-user app is nowhere near the point where they start to matter
- **B.** Yes — the API providers automatically shield small applications from unexpected charges on their side, without you needing to configure anything about it yourself
- **C.** No — one bot, one viral share, or one coding bug can generate thousands of requests in minutes regardless of user count. Rate limits are cheap to add and expensive to skip.  ✅
- **D.** No — but only because your hosting provider contractually requires rate limits to be configured on every app it deploys, regardless of how small the audience is

> **Answer:** C

### Q15. You integrated a paid AI API and plan to set billing alerts after launch once you see real usage. What is wrong with this plan?

- **A.** Nothing is wrong with the plan — gathering real usage data first is widely considered the smart way to set alert thresholds that are actually meaningful for your app
- **B.** Billing alerts are essentially optional for AI APIs, because all of the major providers already include their own built-in spending protections on every account by default
- **C.** You only need billing alerts if your launch plan realistically expects more than a thousand active users to show up on the very first day the product is live
- **D.** Alerts must be set before launch, not after — unexpected costs pile up fast from go-live. Your financial safety net needs to exist before users start generating traffic.  ✅

> **Answer:** D

### Q16. Your autocomplete calls a paid AI API on every keystroke. Costs are 15x over budget. The API fires on each character typed. What concept fixes this?

- **A.** Debouncing — wait until the user pauses typing before calling the API, so a 20-character search fires one call instead of twenty and your costs drop dramatically  ✅
- **B.** Pagination — return only the first page of autocomplete suggestions on each request, which immediately cuts the total number of API calls roughly in half
- **C.** Load balancing — spread the API calls evenly across multiple backend servers, which distributes the traffic and thereby reduces the total costs you end up paying
- **D.** Caching — pre-store every possible search term and its results in a database ahead of time, so that the paid API never actually needs to be called for any query at all

> **Answer:** A

### Q17. A dev-environment loop makes 5,000 API calls in ten minutes. Production users are fine, but you get a big bill. What mistake caused this?

- **A.** You should have tested the new feature without any internet connection at all, which would have completely prevented the runaway test loop from ever making real API calls
- **B.** You used the same API key for dev and production, so the runaway test loop consumed your real production budget instead of drawing from a separate dev allocation  ✅
- **C.** You should have written the development tests in a different programming language, since the one you used is what allowed the loop to run away in the first place
- **D.** This situation is simply unavoidable — development API usage always costs exactly the same amount as production usage, and no configuration choice changes that

> **Answer:** B

### Q18. Your email API returns a 429 error. Your app immediately retries in a tight loop. What is the problem with this approach?

- **A.** There is no problem with this approach — retrying as quickly and as often as possible is the best way to make sure that the queued email actually gets delivered to the recipient promptly
- **B.** The real problem is that a well-run email API should never return 429 errors in the first place — the correct response is to switch your application to a new provider
- **C.** Tight-loop retries make rate limiting worse, risk account suspension, and waste resources. Your app should use exponential backoff — waiting progressively longer between each retry attempt.  ✅
- **D.** You should stop retrying altogether after the very first failure, and simply display a permanent error message to the affected user telling them the email could not be sent

> **Answer:** C

### Q19. Your image API returns a 429 and your app shows 'Error 429: Too Many Requests' as raw text. Users think the app is broken. What should you do?

- **A.** Show a friendly message like 'This feature is busy — please try again shortly' and implement automatic retry logic behind the scenes so the request eventually succeeds  ✅
- **B.** Change the error code your backend passes along from 429 to 200, so that the user's browser and your frontend code both believe that the failed request actually succeeded
- **C.** Hide all error messages from the interface completely, so users never see anything negative — the feature should simply fail silently instead of complaining
- **D.** Remove the image generation feature from the product, because this test proves it clearly cannot handle the traffic volume your users are currently producing

> **Answer:** A

### Q20. Your app uses two paid APIs but you only set a billing alert on the expensive one. Your checklist asks if this is sufficient. Is it?

- **A.** No — every paid API needs its own alert because any of them can spike unexpectedly. A cheap API can still run up a huge bill if a bug or bot triggers high call volume.  ✅
- **B.** No — but only because compliance regulations in most jurisdictions technically require billing alerts to be configured on every paid service that a production application uses
- **C.** Yes — you really only need alerts on the most expensive API, since that is where nearly all of the genuine financial risk in your stack is concentrated
- **D.** Yes — a cheap API is very unlikely to ever generate a meaningful billing problem for your account, so an alert there would just be extra notification noise

> **Answer:** A

### Q21. Your AI recommendation engine ($0.02/call) has no rate limit, but your free static pages all do. What should you change?

- **A.** Nothing — the static pages get the most raw traffic of anything in the app, so those are exactly the endpoints that rate limits are supposed to be protecting
- **B.** Move rate limits from static pages to the recommendation engine — expensive endpoints calling paid APIs are always the highest priority for rate limiting in your stack  ✅
- **C.** Add rate limits to absolutely everything including the recommendation engine, but set every one of the thresholds so high that no real user could ever actually hit them
- **D.** Keep the static page limits exactly as they are, and add a billing alert for the recommendation engine instead of giving that endpoint any rate limit of its own

> **Answer:** B

### Q22. You have three paid APIs but have never logged into any of their usage dashboards. Why is this a problem?

- **A.** It is not really a problem — API usage dashboards are tools that only become genuinely useful for enterprise-scale applications with dedicated operations teams watching them all day long
- **B.** Dashboards only become necessary once you have deliberately disabled all of the billing alerts on a provider, because until then the alerts are already doing the same job
- **C.** Without dashboards you have zero visibility into call volume, costs, or unexpected spikes — you are flying blind on API spending and cannot spot problems before they become expensive  ✅
- **D.** You only need to check the API usage dashboards about once a year, as one part of the annual financial review you run when planning out the budget for the following year

> **Answer:** C

### Q23. You test your app by exceeding the AI endpoint's rate limit. The app shows a white screen with 'HTTP 429.' Does it pass the graceful-handling checklist item?

- **A.** Yes — it correctly identifies the situation and displays the 429 status code right on screen, so the user knows exactly what happened with their request
- **B.** Yes — showing the raw HTTP status code directly is the standard, documented best practice for handling rate limit errors in any user-facing application
- **C.** No — but only because the error screen should be styled in a different color scheme, rather than being displayed as plain unformatted black text on a stark white background
- **D.** No — a graceful response shows a friendly message and ideally retries automatically. A raw HTTP error code means nothing to most users and looks like the app is broken.  ✅

> **Answer:** D

### Q24. Your AI tool asks how long the debounce delay should be on your search bar that calls a paid API. What is a reasonable setting?

- **A.** Set it to 0 milliseconds, so that the search results always appear on screen instantly with no perceptible delay of any kind for the person typing
- **B.** Set it to a full 30 seconds, so that your users are only able to trigger one single search request per half minute at the very most
- **C.** Use 300-500ms — long enough to wait for the user to finish typing but short enough that search still feels responsive and snappy to the user  ✅
- **D.** Debounce delays should always be set to exactly 1 second, regardless of which feature or use case the timer happens to be attached to

> **Answer:** C

### Q25. You use three APIs but only know the pricing for one. You assume the others are cheap. Why is this risky?

- **A.** It is not actually risky — if either of the other two APIs charged a significant amount per call, the providers would have clearly warned you about the pricing terms when you first signed up
- **B.** Without knowing per-request costs you cannot set meaningful rate limits, calculate cost per user, or forecast monthly spend — you could be losing money on every request and not realize it  ✅
- **C.** It is only risky once your user count grows past about a thousand people — below that size, the combined costs of the extra services are always going to stay negligible
- **D.** Per-request costs are largely irrelevant in this situation, because all of the major API providers have moved over to charging a single flat monthly fee for access

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/102901615_
