---
course: "The Mastery"
module: "Module 3: Social and SSO Logins"
lesson: "Module 3: Social and SSO Logins — Exam"
type: "course_quiz"
post_id: 105098591
space_id: 24191170
source: "https://the-faction.mn.co/posts/105098591"
updated: "2026-08-10T20:44:09Z"
---

# Module 3: Social and SSO Logins — Exam

> Exam for **Module 3: Social and SSO Logins** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What actually happens when a user clicks "Sign in with Google" on your AI-built app?

- **A.** Google shares the user's password with your app so future logins can happen locally
- **B.** Your app copies the user's Google profile database into its own tables permanently
- **C.** The browser links the two accounts at the cookie level without any server involvement at all
- **D.** Your app delegates the identity check to Google and receives verified claims about them  ✅

> **Answer:** D

### Q2. What does your app receive after a successful social login, and what does it never receive?

- **A.** A one-year access pass to the user's full account; it never receives the profile photo
- **B.** Verified identity details like a stable ID and email; it never receives the password  ✅
- **C.** The user's contact list and calendar; it never receives their subscription status
- **D.** A copy of the provider's session cookie; it never receives the user's real legal name

> **Answer:** B

### Q3. Why offer social login at all?

- **A.** Less signup friction and no password of yours to protect, at the cost of provider reliance  ✅
- **B.** Providers pay per referred login, making social buttons a small but real revenue line
- **C.** Social logins bypass email verification laws that apply to password-based accounts
- **D.** Apps with provider buttons rank higher in search results under current algorithms

> **Answer:** A

### Q4. A user signed up with a password, then clicks "Sign in with Google" using the same email. What must the design decide?

- **A.** Nothing; matching emails resolve themselves since providers handle these collisions internally
- **B.** Which login wins permanently, since an account can only ever hold a single method
- **C.** How to link the two safely into one account, without email overlap alone hijacking access  ✅
- **D.** Whether to charge twice, since two login methods technically create two billable seats

> **Answer:** C

### Q5. Why does the OAuth redirect URI need to be strictly whitelisted?

- **A.** Unregistered URIs slow the flow, since providers re-verify them on every single login
- **B.** Otherwise the login result could be sent to an attacker's address instead of your app  ✅
- **C.** Providers bill per unique redirect target, so a tight list keeps authentication costs flat
- **D.** Browsers cache redirect targets aggressively, and loose lists poison that cache quickly

> **Answer:** B

### Q6. Your app receives provider tokens after login. What is the rule for scope and storage?

- **A.** Request every available scope up front, since asking again later doubles the consent friction
- **B.** Store tokens in the frontend so the user's own browser carries the liability for them
- **C.** Share tokens across your services freely, since they are already public by OAuth design
- **D.** Request the minimum scopes needed and guard stored tokens like credentials, since they are  ✅

> **Answer:** D

### Q7. A user deletes their Google account, which was their only login method. What should your design have anticipated?

- **A.** A recovery path that doesn't depend on the provider, so the account isn't lost with it  ✅
- **B.** Automatic account deletion on your side, mirroring the provider's action within a single day
- **C.** Nothing; provider accounts are permanent by contract, so this situation cannot arise
- **D.** Charging the user for manual recovery, since provider loss is outside your control

> **Answer:** A

### Q8. What is enterprise SSO, and why does it come up in sales conversations?

- **A.** A shared password vault for teams, which large buyers expect vendors to also maintain
- **B.** A discount program from identity providers that enterprise buyers can pass to vendors
- **C.** Centralized company login for employees; buyers require it to manage access and offboarding  ✅
- **D.** A visual login theme matching corporate branding, a common procurement checkbox item

> **Answer:** C

### Q9. Your AI requests full profile, contacts, and calendar scopes for a simple login. Why direct it to cut back?

- **A.** Excess scopes scare users at the consent screen and hand you data you must now protect  ✅
- **B.** Providers charge per scope requested, so unused permissions inflate authentication cost
- **C.** Wide scopes slow the login redirect measurably, hurting conversion on mobile networks
- **D.** Scopes beyond two trigger a manual review that pauses your app for several weeks

> **Answer:** A

### Q10. Your AI hardcoded the OAuth client secret into the frontend bundle. What is the direction?

- **A.** Obfuscate the bundle so the secret is present but no longer readable by casual viewers
- **B.** Rotate the secret weekly, accepting exposure but shrinking each leaked value's lifespan
- **C.** Rename the variable so automated scanners stop matching it in the shipped bundle
- **D.** Move it server-side immediately and rotate it, since anything shipped to browsers is public  ✅

> **Answer:** D

### Q11. The social provider has an outage during your business hours. What does resilient design look like?

- **A.** A status page apology, since provider outages are legally the provider's problem alone
- **B.** An alternative way in, like email login, so one company's outage doesn't lock your users out  ✅
- **C.** Automatic account creation bypassing login, keeping signups flowing during the window
- **D.** Queueing login attempts for replay after recovery, so no click is ultimately wasted

> **Answer:** B

### Q12. The provider sends an email_verified flag with the identity claims. Why does it matter?

- **A.** It routes the login through faster infrastructure reserved for verified addresses
- **B.** It is decorative metadata, logged for completeness but never used in real decisions
- **C.** Trusting an unverified email for account linking lets an attacker claim someone's account  ✅
- **D.** It controls which marketing lists the address may join under provider agreements

> **Answer:** C

### Q13. A user logs in with Google today and Apple next month, same person. What does the data model need?

- **A.** One account holding multiple linked identities, so any of their providers reaches their data  ✅
- **B.** Separate accounts per provider, merged manually by support when the user complains
- **C.** A rule forcing users to pick one provider forever at signup, simplifying the schema
- **D.** Duplicate rows synced nightly, trading storage for the simplicity of separate per-provider tables

> **Answer:** A

### Q14. How should OAuth flows be tested during development?

- **A.** Against your founders' real personal accounts, since authentic data exercises every path
- **B.** Not at all locally, since OAuth only functions on production domains with real traffic
- **C.** By mocking the entire provider away permanently, shipping the first real flow to production
- **D.** With the provider's test apps and sandbox credentials, so no real accounts get touched  ✅

> **Answer:** D

### Q15. What does SSO actually buy the enterprise buyer, in one sentence?

- **A.** A faster login screen for employees, worth roughly two seconds per person per day
- **B.** Central control: one directory grants access, and one action at departure revokes it all  ✅
- **C.** A compliance certificate that transfers all breach liability from the buyer to the vendor
- **D.** Bulk pricing on seats, since identity providers subsidize apps that adopt their standard

> **Answer:** B

### Q16. Why is making social login the only way into your app a strategic risk?

- **A.** Your access to your own users depends on another company's uptime, policies, and pricing  ✅
- **B.** Social-only apps cannot legally operate in most regions without a password login alternative
- **C.** Provider buttons expire annually and must be repurchased through developer programs
- **D.** Search engines derank apps whose login pages contain third-party branding elements

> **Answer:** A

### Q17. A user logs out of your app. Are they logged out of Google too? What is the design point?

- **A.** Yes, always; OAuth chains sessions so one logout cascades through every connected app instantly
- **B.** Yes, but only on mobile, where the operating system owns the shared session state
- **C.** No; your session and the provider's are separate, and your logout must fully kill yours  ✅
- **D.** It depends on the user's plan tier, since providers link sessions for paid seats only

> **Answer:** C

### Q18. The provider offers rich profile data at login. How much should your app store?

- **A.** All of it, since data you decline at login cannot be requested again later on request
- **B.** Everything but the photo, which is the only field with meaningful privacy weight
- **C.** A rotating sample, keeping storage flat while retaining statistical usefulness overall
- **D.** The minimum your features actually need, since every stored field is a liability held  ✅

> **Answer:** D

### Q19. What is the state parameter in an OAuth flow protecting against?

- **A.** Duplicate charges, by ensuring a payment attached to a login only processes one time
- **B.** Forged or replayed callbacks, by tying the provider's response to the request you began  ✅
- **C.** Slow networks, by carrying enough context to resume a login after a connection drop
- **D.** Case mismatches in emails, by normalizing identity data before it reaches your database tables

> **Answer:** B

### Q20. How do you choose which social providers to offer?

- **A.** Match who your users already are: their platforms, their devices, and their work context  ✅
- **B.** Offer all available providers, since each button is free and choice always converts better
- **C.** Choose the provider with the newest brand design, since login screens signal modernity
- **D.** Rotate providers quarterly, measuring which combination produces the best signup rate

> **Answer:** A

### Q21. An enterprise customer's SSO sends group claims like "engineering" and "finance". What is the opportunity?

- **A.** Charging per group, since claims arrive itemized and map cleanly onto invoice lines
- **B.** Publishing the org chart inside your app, a feature enterprise buyers frequently request
- **C.** Mapping their groups to your app's roles, so access assigns itself from their directory  ✅
- **D.** Storing the claims as marketing segments for targeted feature announcement campaigns

> **Answer:** C

### Q22. An employee leaves the enterprise customer. With SSO wired correctly, what happens in your app?

- **A.** Their account survives until your quarterly cleanup job removes directory strays
- **B.** Their access dies when the company disables them centrally, with no work on your side  ✅
- **C.** They keep read-only access for ninety days, which is the standard courtesy window in B2B
- **D.** Your support team receives a removal ticket, since deprovisioning is manual by design

> **Answer:** B

### Q23. What differs about social login on mobile apps versus the web?

- **A.** Mobile logins skip OAuth entirely, using the app store account as the sole identity source
- **B.** Nothing; the flows are byte-identical, and platform differences are marketing fiction
- **C.** Mobile requires no client secret anywhere, removing the main web security concern
- **D.** Mobile flows should use the system browser or native SDKs, not webviews providers block  ✅

> **Answer:** D

### Q24. Where does SSO usually sit in a SaaS pricing model, and why?

- **A.** In the free tier, since identity features cost vendors nothing and drive viral signups
- **B.** As a metered add-on billed per login event, so that cost always matches actual usage patterns
- **C.** In the enterprise tier, since buyers who require it have budget and it carries setup cost  ✅
- **D.** Outside pricing entirely, since charging for security features is considered bad practice

> **Answer:** C

### Q25. Which principle should govern every social and SSO decision you direct?

- **A.** Borrowed identity, owned responsibility: providers prove who they are, the account stays yours  ✅
- **B.** Providers are infallible: whatever claims arrive from a big platform can be trusted blind
- **C.** More buttons, more growth: every provider added is pure conversion with no trade-offs
- **D.** SSO is cosmetic: enterprise login is a checkbox, not a system that needs real design

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105098591_
