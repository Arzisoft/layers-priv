---
course: "The Foundation"
module: "Layer 4: Auth & Permissions"
lesson: "Layer 4: Auth & Permissions — Exam"
type: "course_quiz"
post_id: 102901466
space_id: 23777123
source: "https://the-faction.mn.co/posts/102901466"
updated: "2026-08-21T14:59:57Z"
---

# Layer 4: Auth & Permissions — Exam

> Exam for **Layer 4: Auth & Permissions** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A user logs out on their laptop but later finds they're still logged in on their phone with full data access. What is the problem?

- **A.** The phone's operating system is incorrectly caching the session data locally and needs to have its application cache fully cleared by the user
- **B.** The logout function is not invalidating the session token server-side, so old tokens on other devices remain active and usable  ✅
- **C.** The user simply needs to log out on every one of their devices separately — this is completely normal and expected session behavior
- **D.** The phone browser is outdated and needs a full software update before it can properly support modern secure session handling

> **Answer:** B

### Q2. You built a private note-taking app. User B can see User A's notes when logged in via an incognito window. What security measure is missing?

- **A.** Row-level security — every note must be linked to its owner so the database only returns notes belonging to the logged-in user  ✅
- **B.** User B's account permissions need to be manually set to a lower access level in the dashboard to properly restrict their data visibility
- **C.** The notes need to be encrypted with a much stronger algorithm so that other users cannot ever decode the stored note content
- **D.** The incognito window is leaking session data over from the regular browser window, creating a cross-session overlap between users

> **Answer:** A

### Q3. You inspect the database your AI tool created and see passwords stored as readable text like 'mypassword123'. What should you do?

- **A.** Leave it for now — plain text passwords are generally acceptable for small early-stage apps, and you can add hashing once you start to scale up
- **B.** Rename the password column to something much less obvious so that it would be harder for anyone to find the credentials and exploit them
- **C.** Fix this immediately — passwords must always be hashed into an unreadable format so that nobody can read them, including you  ✅
- **D.** Encrypt only the database connection itself, which will then automatically protect all of the stored passwords from ever being read

> **Answer:** C

### Q4. You navigate to /admin in a new browser without logging in and the page loads with all admin controls visible. What is wrong?

- **A.** The admin page just needs a stronger password requirement in its settings so that unauthorized users cannot easily guess any valid admin credentials
- **B.** The /admin route is completely unprotected — it must require authentication and verify admin privileges before loading any content  ✅
- **C.** You need to add a robots.txt file to block search engines and other unauthorized visitors from ever discovering the admin URL
- **D.** The page appears to load, but the actual data and admin controls won't be functional until a valid login session actually exists

> **Answer:** B

### Q5. Your AI tool's signup form accepts 'notarealemail' as an email and '1' as a password. An account is created. What should you fix?

- **A.** Add email format validation and enforce minimum password strength requirements so weak or invalid credentials are rejected  ✅
- **B.** Change the signup button color and its positioning on the page to make it more prominent and draw more attention to the form fields
- **C.** Add a CAPTCHA widget to the signup form so that automated bots cannot create new accounts with fake or invalid credentials
- **D.** Require every new user to upload a profile picture during the signup process before their new account can actually be created

> **Answer:** A

### Q6. After login, the server creates a token sent to the browser and included with every request. If missing or expired, the request is rejected. What is this token called?

- **A.** A JWT (JSON Web Token) — a digital pass containing the user's identity and expiration, sent with every authenticated request  ✅
- **B.** An SSL certificate, which establishes an encrypted connection between the browser and the web server for every data transfer between them
- **C.** An API key, which is a static credential assigned to an application for identifying it whenever it makes backend service calls
- **D.** A database index, which is a lookup structure that the server uses to quickly find and retrieve stored user information

> **Answer:** A

### Q7. Which prompt best describes access rules for a task app where users see only their own tasks and admins see all tasks?

- **A.** Build a login system for my app so that all of my users can create their own accounts and sign in with their email and password securely
- **B.** Build a task management app with a properly structured database that stores all of the tasks, due dates, and user information in organized tables
- **C.** Make sure my app is fully secure with good strong passwords and proper encryption so that every user's data stays properly protected
- **D.** Add auth: regular users view/create/edit/delete only their own tasks. Admins view/edit/delete any task. Non-logged-in users redirect to login.  ✅

> **Answer:** D

### Q8. A friend asks the difference between authentication and authorization. Which answer is correct?

- **A.** They are essentially interchangeable terms — both of them refer to the same basic process of logging into an application and verifying identity
- **B.** Authentication handles encrypting your data into a secure format, while authorization handles decrypting that data when it is needed
- **C.** Authentication verifies who you are (the login step), while authorization determines what you're allowed to do (the permissions layer)  ✅
- **D.** Authentication applies only to web-based applications, while authorization is the equivalent term used for mobile app security

> **Answer:** C

### Q9. Login works and the dashboard loads, but any logged-in user can query any other user's records through the API. What concept is missing?

- **A.** Password hashing, which scrambles all stored credentials into an unreadable format to protect them from any future database breaches
- **B.** Email verification, which confirms each user actually owns the address they signed up with before granting full account access
- **C.** Row-level security — each record must be linked to its owner so the database only returns data belonging to the requesting user  ✅
- **D.** HTTPS encryption, which secures data in transit between the browser and the server to prevent interception by network attackers

> **Answer:** C

### Q10. Your AI tool offers to build custom auth from scratch. An experienced builder says use Supabase Auth instead. Why is that advice better?

- **A.** Supabase Auth simply offers a nicer-looking login page design out of the box, which gives users a much more polished overall visual experience
- **B.** Supabase Auth is the only authentication system on the market that integrates properly with AI-directed development workflows
- **C.** Custom auth systems are inherently too slow for production apps because they add extra processing overhead to every single request
- **D.** Proven providers like Supabase Auth handle password hashing, session management, and brute-force protection — areas AI often gets wrong  ✅

> **Answer:** D

### Q11. What is the correct workflow for building auth with an AI coding tool?

- **A.** Describe access rules, let AI build the auth layer, test as different users, verify unauthorized access is blocked, fix gaps, then ship  ✅
- **B.** Ask your AI tool to build the login flow, visually confirm that the login page loads correctly in the browser, then ship it straight to production
- **C.** Copy pre-built auth code from an online tutorial and paste it directly into your own project without doing any further customization
- **D.** Build the entire app with all of its features first, then add authentication as the very last step right before you finally launch

> **Answer:** A

### Q12. You tested that login works — users can sign up, log in, and see their dashboard. A friend asks, 'Did you test what happens after login?' What should you test?

- **A.** Whether the logout button has proper color contrast, correct on-screen placement, and the right styling across all of the page layouts
- **B.** Whether users can successfully update their profile picture after logging in and immediately see the changes reflected in the app
- **C.** Whether the app loads quickly after login by measuring page render times and optimizing any slow-running database queries
- **D.** Whether logged-in users can access other users' data, and whether protected pages are reachable without being logged in at all  ✅

> **Answer:** D

### Q13. Your AI tool built a full login system from scratch — password storage, token generation, session handling — with no auth provider. Why is this risky?

- **A.** Custom auth systems are always noticeably slower than established auth providers because they add layers of unnecessary processing overhead
- **B.** Custom-built auth systems do not support email-based login flows, which limits the signup options that are available to your users
- **C.** AI-built custom auth often mishandles hashing, token expiration, and brute-force protection — proven providers handle these correctly  ✅
- **D.** Using an external auth provider is legally required in most countries, so building custom authentication violates those regulations

> **Answer:** C

### Q14. The database has a users table where the password column shows readable values like 'sunshine99' and 'hunter2'. What is the severity?

- **A.** Low severity — this is primarily a cosmetic issue in the database viewer and it can safely be addressed later without any real urgency
- **B.** Critical security failure — passwords must always be hashed into an unreadable format and never stored as plain readable text  ✅
- **C.** Not an issue at all — passwords are routinely stored in a readable text format in production databases and this is standard practice
- **D.** Medium severity — it should be fixed before the app gets many users, but it's broadly acceptable during early development stages

> **Answer:** B

### Q15. Users stay logged in indefinitely — even weeks later their sessions still work. Why is this a security problem?

- **A.** If a device is stolen or credentials are compromised, attackers retain permanent access because sessions never expire or force re-login  ✅
- **B.** Long-lived sessions steadily consume excessive server memory and processing resources, eventually degrading the app's performance for everyone
- **C.** It is not a problem — keeping users logged in permanently is a better user experience and it reduces login friction significantly
- **D.** Users will forget their passwords entirely if they never have to re-enter them, creating future account recovery problems for support

> **Answer:** A

### Q16. Your login form accepts unlimited password attempts from the same address and never slows down. What should you direct your AI tool to add?

- **A.** A longer minimum password length, since a longer secret is the thing that stops repeated guessing attempts from ever succeeding
- **B.** Rate limiting on login attempts, so that repeated failures from one source are slowed or blocked before guessing can succeed  ✅
- **C.** A CAPTCHA on the signup form, which is where automated traffic first enters and therefore where guessing has to be stopped
- **D.** A hidden field that only automated tools fill in, since bots always complete every input on a form and can be filtered out

> **Answer:** B

### Q17. You skipped testing row-level security because 'users won't know how to access each other's data.' Why is this reasoning dangerous?

- **A.** Because missing row-level security noticeably degrades app query performance and slows down the database lookups for all of your active users
- **B.** Because users might accidentally share their login credentials with others, which would bypass any of the existing security controls
- **C.** Because missing row-level security is the most common AI auth gap, and attackers can exploit URLs or API calls without sophistication  ✅
- **D.** Because row-level security is a formal requirement your app must meet to pass its accessibility and compliance standards before launch

> **Answer:** C

### Q18. You're prompting your AI tool to build auth for a new app. Which is the best way to describe your access rules?

- **A.** Make my app secure — this open-ended phrasing gives the AI full flexibility to implement whatever security measures it determines are most appropriate
- **B.** Add login to my app — this tells the AI to build a sign-in page so that users can create their own accounts and authenticate properly
- **C.** Build authentication and authorization — these keywords signal the AI to implement both the identity and the permissions systems
- **D.** Users sign up with email/password. Logged-in users see only their own profiles. Admins view all profiles. Non-logged-in see landing page only.  ✅

> **Answer:** D

### Q19. You log in as User A in a normal browser window. What should you do next to test data isolation between users?

- **A.** Check that the login page uses a properly secured HTTPS connection by inspecting the certificate details shown in the browser address bar
- **B.** Log out as User A and then log back in again to confirm the login flow works correctly on a second authentication attempt
- **C.** Open an incognito window, log in as User B, and verify that each user can only see their own data with no cross-user leakage  ✅
- **D.** Ask your AI tool whether the auth system is secure and carefully review the response for any potential permission concerns

> **Answer:** C

### Q20. Your /dashboard page should only be visible to logged-in users. How do you test whether the route is properly protected?

- **A.** Log in and confirm that you can see the dashboard content — if it loads correctly for an authenticated user, the route must be secure
- **B.** Open a new browser without logging in and navigate directly to /dashboard — if it loads, the route is unprotected and exposed  ✅
- **C.** Check that the dashboard has a professional visual design and layout, since well-designed pages are generally much more secure
- **D.** Ask your AI tool to review the route configuration and confirm the dashboard is protected based on the generated code logic

> **Answer:** B

### Q21. A user requests a password reset, waits 48 hours, and the link still works. They use it to change the password, then use the same link again to change it a second time. The account owner is never notified. How many security gaps are present?

- **A.** Two issues: the link should become single-use only after being clicked, and the account owner should always receive a notification
- **B.** One issue: the link should only work once — the expiration and owner notification parts are optional security enhancements
- **C.** No issues are present at all — this is exactly how password reset flows are designed to work in standard authentication systems
- **D.** Three issues: the link must expire quickly (15-30 min), must work only once after use, and must notify the account owner  ✅

> **Answer:** D

### Q22. Your AI tool offers two options: build custom auth from scratch or integrate Supabase Auth. Which should you choose and why?

- **A.** Use Supabase Auth — proven providers handle hashing, sessions, and security correctly because auth is too critical to build from scratch  ✅
- **B.** Build custom because third-party auth providers are expensive and their subscription costs add up very quickly as your user base keeps growing
- **C.** Build custom because it gives you far more direct control over the login page interface and lets you customize every element of it
- **D.** It doesn't matter — both approaches are equally secure as long as the AI tool manages to generate the code without any errors

> **Answer:** A

### Q23. You log in, close the browser, reopen it a week later — still logged in. You click Logout, navigate back — still logged in. What two problems exist?

- **A.** The app has a browser caching issue that requires each user to manually clear all of their stored data to properly end their sessions
- **B.** These are features rather than problems — users generally prefer staying logged in and not having to re-enter their credentials
- **C.** The user's internet connection speed is keeping the session alive by maintaining a persistent link back to the auth server
- **D.** Sessions never expire (no timeout policy), and the logout function does not actually invalidate the session token server-side  ✅

> **Answer:** D

### Q24. Your AI tool built a working login page. Users can sign up, log in, and see their dashboard. You haven't tested anything else. What critical step is missing?

- **A.** Confirming that logged-in users can only access their own data — a working login doesn't prove permissions are enforced  ✅
- **B.** Updating the login page styling with your brand logo, colors, and fully custom fonts to match the rest of the application
- **C.** Running mobile-responsive layout tests on the login page across multiple phone screen sizes and tablets
- **D.** Adding a 'Remember Me' checkbox and auto-fill support so returning users don't have to log in every visit

> **Answer:** A

### Q25. A user can see another user's account details by changing the user ID number in the URL at /account/settings. What type of auth failure is this?

- **A.** A session expiration failure where the token timed out and the server fell back to showing default account data
- **B.** An authorization failure — the user is logged in, but the app never verifies whether they own the data they're requesting  ✅
- **C.** An authentication failure because the login system failed to properly establish the user's identity at sign-in
- **D.** A password hashing failure where the stored credential was compromised and allowed unauthorized access to the system

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/102901466_
