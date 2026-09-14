---
course: "The Foundation"
module: "Layer 8: Security & RLS"
lesson: "Layer 8: Security & RLS — Exam"
type: "course_quiz"
post_id: 102901599
space_id: 23777123
source: "https://the-faction.mn.co/posts/102901599"
updated: "2026-08-21T15:03:32Z"
---

# Layer 8: Security & RLS — Exam

> Exam for **Layer 8: Security & RLS** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A user sees another user's profile data. You find RLS is disabled on the profiles table. What is the cause and best fix?

- **A.** The user is simply mistaken, because Supabase automatically protects all of the data in every project without any manual setup or configuration needed from you
- **B.** RLS is off by default on new Supabase tables so anyone can see every row; tell your AI tool to enable RLS and add a policy limiting each user to their own row  ✅
- **C.** The frontend is broken and is displaying cached data left over from a completely different user's session in the browser, so clearing the cache will make the problem disappear
- **D.** You must delete the profiles table and rebuild it completely from scratch, because Row-Level Security can only be turned on at the moment a table is first created in Supabase

> **Answer:** B

### Q2. Your AI tool just created a customer_orders table in Supabase. Before any user touches it, what is the first security step?

- **A.** Add a database index on the new table first, in order to improve query speed and reduce load times for all of the order lookups users will run
- **B.** Create a full database backup first, so that you have something to restore in case anything breaks during the initial period of user access to the table
- **C.** Build a frontend component that displays the orders first, so that your users have a working visual interface for the new table before anything else is added
- **D.** Enable Row-Level Security on the table and create a policy so each user can only access their own orders, preventing cross-user data leaks  ✅

> **Answer:** D

### Q3. You deployed your app and want to verify all data transfers are encrypted. What confirms HTTPS is working in Chrome?

- **A.** The page loads without showing any visible error messages in the browser window, which by itself is enough to confirm the connection is secure
- **B.** Your hosting platform sent you a welcome email that briefly mentions SSL certificate setup was completed, which proves every transfer is now encrypted
- **C.** The URL uses a non-encrypted prefix and the page still renders correctly with all images loading, which means the data transfers between browser and server are safe
- **D.** A padlock icon appears in the address bar and the URL begins with the encrypted prefix, confirming the browser has an encrypted connection to the server  ✅

> **Answer:** D

### Q4. A user types a script tag into your search bar and an alert box pops up. What does this mean and what should you do?

- **A.** Your app has a cross-site scripting vulnerability because inputs are not sanitized; tell your AI tool to add input sanitization so user text is cleaned before rendering  ✅
- **B.** The user has somehow gained full administrator access to your backend server, and you should immediately shut down the entire application until you can investigate
- **C.** The user's browser is infected with a virus that generates fake alert pop-ups on whatever site they visit, so the behavior is completely unrelated to your actual application
- **D.** This is standard, expected browser behavior for processing script tags typed into any input field, and it does not represent a real security concern that you need to spend effort on

> **Answer:** A

### Q5. You find your Supabase password hardcoded in a JavaScript file. What is the risk and the fix?

- **A.** There is no real risk, because JavaScript files live only on the server side of your project and are never exposed to the users loading your pages
- **B.** Anyone who sees the code, especially if pushed to GitHub, can read your database password; tell your AI tool to move it to an environment variable instead  ✅
- **C.** The password should be moved into a README file at the root of the repository instead, so that your teammates can find and update it far more easily during development
- **D.** Rename the JavaScript file to something obscure and unrelated to authentication, so that casual viewers browsing the project cannot easily locate the hardcoded password

> **Answer:** B

### Q6. An unfamiliar website is pulling user data from your API. What setting controls this and how should it be configured?

- **A.** Switch the application from HTTPS over to plain HTTP, which blocks unknown external sites from establishing any secure connections to your app
- **B.** The RLS policy is what handles this situation; add the unknown website's URL to a blocklist table stored inside your database so its requests get rejected
- **C.** CORS configuration controls which domains can request data from your API; restrict it to only the domains you own so unauthorized sites are blocked  ✅
- **D.** Change your DNS settings and move the app to a brand new domain name, so that the unknown website can no longer discover where your API endpoint is actually hosted

> **Answer:** C

### Q7. Users log in with email and password and can view settings but not change another user's. What two security concepts work together here?

- **A.** Input sanitization and secrets management working together handle the access control by cleaning what users type and keeping your keys hidden from them
- **B.** HTTPS and CORS are working together in this design, because transport encryption combined with domain restrictions is what handles all of the access control rules
- **C.** Authentication verifies who a user is at login, and authorization determines what they can do, restricting each person to only their own settings and data  ✅
- **D.** RLS and environment variables are working together, because row-level database policies plus secret storage are the pair that prevents every kind of unwanted access

> **Answer:** C

### Q8. Your AI tool skipped security headers. A friend says Content-Security-Policy and X-Frame-Options are missing. Why add them?

- **A.** Security headers tell browsers how to handle your content, blocking clickjacking, preventing code injection, and enforcing encrypted connections as extra protection  ✅
- **B.** Security headers primarily exist to improve app performance, since they instruct the server to compress data transfers between itself and each visitor's browser
- **C.** Security headers are only actually required for applications that process credit card payments or handle other kinds of regulated financial data, so a simple app can skip them
- **D.** Security headers are deprecated legacy features from an earlier era of the web, and they are no longer read or supported by any of the modern browsers your users are running today

> **Answer:** A

### Q9. A friend asks what RLS stands for and what it does. Which answer best explains Row-Level Security in plain language?

- **A.** RLS encrypts each individual row of data in the table so that it cannot be read by anyone who lacks a special decryption key
- **B.** RLS limits how many rows a single database query is allowed to return at once, in order to prevent slow queries from degrading performance
- **C.** RLS automatically deletes old rows of data after a set retention period passes, in order to maintain user privacy and meet compliance requirements
- **D.** RLS is a set of database rules ensuring each user sees only their own rows, like invisible walls between users sharing the same table  ✅

> **Answer:** D

### Q10. A colleague asks why HTTPS matters when your app sends data between the browser and server. Which analogy best fits?

- **A.** HTTPS is like a speed boost applied to your data transfers, making the whole application load significantly faster for every user who visits
- **B.** HTTPS is like sending a letter in a locked box instead of on a postcard; it scrambles data in transit so nobody between sender and receiver can read it  ✅
- **C.** HTTPS is like a spam filter sitting in front of your app, blocking unwanted or malicious requests before they ever get the chance to reach your server at all
- **D.** HTTPS is like a post office that guarantees your letter will be delivered to the right address, but does nothing to protect the actual contents of the mail inside

> **Answer:** B

### Q11. Your AI tool hardcoded a database password in a source file. Where should this value be stored instead?

- **A.** In an environment variable, which is a secure location outside the codebase that only the server can read, keeping secrets out of source control  ✅
- **B.** In a code comment placed at the very top of the file, so the password is easy for you to find but is never actually executed by the running app
- **C.** In the app's own user interface, on a settings screen where administrators can view and update the password whenever they need to without touching the code
- **D.** In the database itself, stored as a regular row in a settings table right alongside your other configuration values, where the application can query it directly

> **Answer:** A

### Q12. You hear the term input sanitization during a security discussion. What does it mean for your app?

- **A.** It means cleaning user input before your app processes it, so special characters or malicious code cannot trick your app into unintended behavior  ✅
- **B.** It means requiring every user to solve a CAPTCHA challenge before they are allowed to submit any of the forms in your app, to keep the bots out
- **C.** It means permanently deleting all of the user accounts that have ever entered suspicious or unusual data values into any of the forms across your application
- **D.** It means logging every keystroke that users type anywhere in your app, so that an administrator can go back and review all of the collected input at a later date

> **Answer:** A

### Q13. You see CORS on a security checklist. What does it stand for and what does it control?

- **A.** Cached Object Retrieval Service, which controls how your application stores and then retrieves the data that users request the most frequently
- **B.** Central Origin Routing System, which controls the list of backend servers that your database is permitted to open direct network connections to at runtime
- **C.** Cross-Origin Resource Sharing controls which external websites are allowed to make data requests to your app API, preventing unauthorized access  ✅
- **D.** Client-Only Rendering Standard, which controls whether your application renders its pages on the server side or entirely in the visitor's browser on each visit

> **Answer:** C

### Q14. You created three new Supabase tables last week and forgot to check RLS. What is most likely true now?

- **A.** RLS is switched on by default for every new Supabase table, which means all three of the tables you created are already fully protected right out of the box
- **B.** RLS is off by default on new Supabase tables, so every user can potentially see every row in all three tables until you enable it and add policies  ✅
- **C.** Supabase forces you to enable RLS as part of the table creation flow, so it is technically impossible to end up with a new table where you forgot to do it
- **D.** RLS only really matters for tables holding more than a thousand rows, so three small tables like yours are not at any meaningful risk while the app stays small

> **Answer:** B

### Q15. Your AI tool put your Stripe API key directly in payment.js. You plan to push to GitHub. What is the danger?

- **A.** There is no danger, because all GitHub repositories are private by default and cannot be viewed publicly by anyone outside your account
- **B.** Anyone with repo access, or anyone on the internet if it is public, can see and misuse your Stripe key to make charges or access your account  ✅
- **C.** GitHub automatically scans every incoming push for API keys and quietly removes them from your code before they ever become publicly visible to anyone
- **D.** The Stripe API key will automatically expire and become invalid the moment the code is pushed to GitHub, so there is nothing an attacker could do with it

> **Answer:** B

### Q16. A hidden Admin Panel button's API endpoint is called directly by a curious user who deletes another account. What went wrong?

- **A.** The curious user must have somehow guessed the administrator password, which gave them the elevated access needed to delete the other account
- **B.** The frontend framework has a rendering bug that accidentally exposed the hidden admin button to regular users, and updating the framework will fix this
- **C.** The user has installed a special browser extension that automatically unlocks hidden buttons on any website it encounters, which is not something you can defend against
- **D.** Security was only enforced on the frontend by hiding the button; the API itself must check permissions server-side and reject unauthorized requests  ✅

> **Answer:** D

### Q17. You skipped input sanitization thinking your app is too small to attack. A week later your database is compromised. What happened?

- **A.** A competitor manually researched, targeted, and attacked your specific application shortly after discovering it was online and taking real user signups
- **B.** Your hosting provider experienced a serious data center failure during that week, and the outage briefly exposed your database to unauthorized outside access
- **C.** Automated bots that scan every app on the internet for common vulnerabilities found your unprotected inputs and exploited them without any human involvement  ✅
- **D.** Your domain name expired without you noticing, and a malicious party claimed it and began redirecting all of your traffic to a lookalike server under their own control

> **Answer:** C

### Q18. Your app uses HTTP, not HTTPS. A user connects from coffee shop Wi-Fi. What risk does this create?

- **A.** Without HTTPS, anyone on the same network can read user data in transit, including login credentials, personal info, and everything sent to or from the app  ✅
- **B.** The coffee shop's router automatically encrypts all of the network traffic passing through it, so serving your app over plain HTTP is perfectly fine
- **C.** HTTP is actually the more secure choice on public Wi-Fi, because it uses a simpler and more direct connection path with fewer moving parts for attackers to target
- **D.** The app will load a little more slowly for users on public Wi-Fi networks, but all of their data remains fully safe and encrypted no matter which protocol you serve

> **Answer:** A

### Q19. You never tested whether one user can see another's data. A beta tester reports seeing others' private messages. What pitfall is this?

- **A.** Beta testers are always granted elevated permissions by default on every major platform and hosting provider, which is why this tester could see the messages
- **B.** You deployed the application onto the wrong hosting platform for this kind of product, and that platform choice is what caused the data isolation to break down
- **C.** You chose the wrong database provider for the project, and the provider you picked does not support any real form of data isolation between the accounts stored inside it
- **D.** You never tested security by trying to break it yourself; logging in as one user and trying to access another's data is a basic test you should run before launch  ✅

> **Answer:** D

### Q20. You log in as User A and can see User B's order history. What should you do next?

- **A.** Ignore the finding, because it only affects the test accounts you created during development and will not impact any of the real users in production
- **B.** Add a frontend filter that hides User B's data from User A's view, so that the other customer's orders simply no longer appear anywhere on the rendered screen
- **C.** Tell your AI tool to enable RLS on the orders table and create a policy restricting each user to only their own rows, then retest to confirm the fix works  ✅
- **D.** Delete User B's account from the application entirely, so that the exposed order history no longer appears for anyone and the report can be closed out as resolved

> **Answer:** C

### Q21. Four of six user-data tables have RLS, but user_notes and user_files do not. What should you do?

- **A.** Enable RLS on user_notes and user_files and create appropriate policies, because every table holding user data must have RLS to prevent exposure  ✅
- **B.** Four protected tables out of six is close enough to a passing grade; focus your remaining effort on the other items in the security checklist
- **C.** Disable RLS across all six of the tables so the configuration stays consistent, and rely solely on your frontend security checks to protect the user data
- **D.** Merge all six of the tables into one single combined table, so that you only need to write and manage one RLS policy to cover everything the app ever stores

> **Answer:** A

### Q22. You find your email service API key hardcoded in config.js. How do you fix this?

- **A.** Rename config.js to something far less obvious, so that attackers scanning the repository are unlikely to guess which file holds the credentials
- **B.** Encrypt the entire config.js file with a password on your machine before uploading it to GitHub, and share that password with anyone who needs to run the app
- **C.** Add a code comment at the top of the file instructing all current and future developers to never share the key with anyone external to the team or the project
- **D.** Move the API key to an environment variable and update config.js to reference that variable instead of containing the raw key directly in source code  ✅

> **Answer:** D

### Q23. Most requests use HTTPS but one image loads over HTTP. What is this called and why is it a problem?

- **A.** This is called partial rendering, and it only affects the visual quality of the images on the page rather than the security of the application
- **B.** This is mixed content; the HTTP request is unencrypted and can be intercepted, and browsers may show security warnings or block the resource entirely  ✅
- **C.** This is completely normal behavior, because image files do not contain any sensitive user data and therefore never need to be delivered over an encrypted channel
- **D.** This is a routine browser caching issue, and it will resolve itself automatically the next time you or the user clears the local browser cache and reloads the page

> **Answer:** B

### Q24. You type OR 1=1 -- into a login email field and the app logs you in as admin. What does this reveal?

- **A.** The admin account has an extremely weak password, and the text you typed into the email field just happened to coincidentally match that exact password
- **B.** The app correctly interpreted the text you typed as a valid and legitimate administrator login credential, which is why it signed you into the admin account
- **C.** Your app is vulnerable to SQL injection because the input was executed as a database command instead of being sanitized, allowing unauthorized admin access  ✅
- **D.** The login form is functioning exactly as designed, because this kind of shortcut is intended for developer testing and QA and gets removed automatically in production

> **Answer:** C

### Q25. CORS is set to wildcard (*), letting any website hit your API. What should you change?

- **A.** Replace the wildcard with a list of only the specific domains you control, like your app's frontend URL, so unauthorized sites cannot access your API  ✅
- **B.** Remove the CORS configuration from the API entirely, so that no external websites are able to establish any kind of connection to it at all
- **C.** Add a second wildcard entry alongside the first one in the configuration, which gives the API an additional stacked layer of access security on requests
- **D.** Leave the wildcard exactly where it is, because it is the simplest and easiest CORS configuration to maintain and it never needs updating when your domains change

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/102901599_
