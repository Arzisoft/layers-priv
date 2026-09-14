---
course: "The Foundation"
module: "Layer 2: APIs & Backend Logic"
lesson: "Layer 2: APIs & Backend Logic — Exam"
type: "course_quiz"
post_id: 102900576
space_id: 23777123
source: "https://the-faction.mn.co/posts/102900576"
updated: "2026-08-20T23:45:18Z"
---

# Layer 2: APIs & Backend Logic — Exam

> Exam for **Layer 2: APIs & Backend Logic** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your app’s Delete Account button sends a GET request to /api/users/delete. You see this in the browser’s Network tab. What is wrong with this approach?

- **A.** The endpoint URL should use underscores instead of slashes in its path — the way the route is formatted is what causes the server to mishandle the request
- **B.** DELETE actions should use a DELETE request, not a GET request — GET is for retrieving data, and using it for destructive actions is incorrect and potentially dangerous  ✅
- **C.** The request should be sent twice in a row for confirmation so the server can compare both copies before it actually processes the account deletion
- **D.** Nothing is wrong with this — GET requests can be used for any server action, including deletions, as long as the endpoint URL clearly describes what it does

> **Answer:** B

### Q2. Your AI created these endpoints: /api/getTasks, /api/createNewTask, /api/updateTaskById, /api/removeTask. A senior dev says the design is wrong. What pattern should they follow?

- **A.** The endpoints are fine as they are — longer, more descriptive action names make the API easier for other developers on the project to understand
- **B.** Combine all of the actions under one endpoint like /api/do-everything and use a request parameter to select which action should run
- **C.** Use numbered endpoints like /api/endpoint1 and /api/endpoint2 so that each separate action gets its own unique numeric identifier
- **D.** Use a resource-based URL (/api/tasks) with HTTP methods: GET to list, POST to create, PUT /api/tasks/:id to update, DELETE to remove  ✅

> **Answer:** D

### Q3. Your order endpoint works with valid data. But a user submits with a missing shipping address, the server crashes with a 500 error, and they see a blank screen. What is the problem?

- **A.** The endpoint only handles the happy path — it works with perfect data but crashes on missing or invalid input because AI didn’t build error handling  ✅
- **B.** The user’s browser is outdated and can’t properly format the shipping address data into valid JSON before sending it across to your server for processing
- **C.** 500 errors are normal and expected in production — the server returns them whenever submitted data needs manual review before it can be saved
- **D.** The shipping address field should simply be made optional since not every order placed in the system needs physical delivery to an address

> **Answer:** A

### Q4. Your AI-built registration endpoint accepts anything — no email, a name of just spaces, an age of -5. What critical backend feature is missing?

- **A.** Frontend form validation — the input fields on the registration page should stop bad data in the browser before it is ever sent across to the server
- **B.** A terms of service checkbox that users must accept before the registration form can be submitted and their new account actually gets created
- **C.** Data validation — the endpoint should check that incoming data meets requirements (valid email, non-empty name, reasonable age) before processing  ✅
- **D.** Rate limiting on the registration endpoint to prevent too many separate signup attempts from arriving from one single IP address or source

> **Answer:** C

### Q5. You get a 404 when loading one user’s profile, but a 200 with data for a different user ID. What do these status codes tell you?

- **A.** 404 means the server is broken and had an internal error of some kind; 200 means that it recovered from that failure and started working again
- **B.** 404 means the requested resource was not found (that user doesn’t exist); 200 means the request was successful and the data was returned correctly  ✅
- **C.** Both codes indicate success — 404 simply means the request succeeded but there was no matching data in the database for the server to return
- **D.** 404 means the endpoint URL is incorrect on the frontend and should be updated in your code so it points at the right path on the correct backend server

> **Answer:** B

### Q6. You ask your API for a user’s name and email. The response returns 47 fields including database IDs, password hashes, admin flags, and timestamps. What is the problem?

- **A.** JSON responses automatically include every single database field by default — this is standard API behavior and is not something you are able to change
- **B.** More data is always better — the frontend can simply filter and display only the fields it needs from the full response payload
- **C.** The response actually needs even more fields to be complete — related user activity and preference data should also be included
- **D.** The API returns far more data than requested, including sensitive info (password hashes, admin flags) that should never reach the frontend  ✅

> **Answer:** D

### Q7. Your business rule: free shipping over $50. AI implements it. You test with a $55 order but shipping is still charged. AI calculated the total after shipping was added. What happened?

- **A.** The AI coding tool is fundamentally broken and simply can’t reliably handle mathematical calculations like price comparisons or running totals inside checkout code
- **B.** Free shipping is impossible to implement in application code because shipping costs are calculated by external carrier services outside your control
- **C.** AI implemented the rule wrong — it checks the total after shipping, not the subtotal before. Always verify AI’s logic order and test with specific values  ✅
- **D.** The database is storing incorrect prices because the product catalog was never updated after the free shipping promotion was first created

> **Answer:** C

### Q8. You told AI: ‘Create an endpoint that lets users update their profile.’ Testing shows it lets users update ANY profile, not just their own. What was missing from your description?

- **A.** The specific database table name and its full column structure so AI could build the profile update query correctly
- **B.** That users can only update their own profile — and you should test with another user’s ID to confirm the restriction works  ✅
- **C.** The exact SQL query the endpoint should run so that AI doesn’t have to generate any of its own database update logic
- **D.** That the endpoint should use HTTPS encryption to fully protect all of the profile data while it travels across the open network

> **Answer:** B

### Q9. A non-technical co-founder asks you to explain what happens when a user taps ‘Place Order’ in your app. How would you describe the request-response cycle in plain language?

- **A.** The button runs a JavaScript function in the page that writes the order data directly into the database from the user’s own browser
- **B.** The order details are sent over via email to a fulfillment team member who manually enters each one into the ordering system for processing
- **C.** The browser stores the completed order in local memory first and then syncs it up to the server afterward whenever a network connection becomes available
- **D.** The app sends a request saying ‘save this order,’ the server validates, checks inventory, calculates the total, saves it, and responds ‘order confirmed’  ✅

> **Answer:** D

### Q10. AI created /api/handleUserStuff — one endpoint handling create, list, update, and delete based on an ‘action’ parameter. What API design principle does this violate?

- **A.** The endpoint name is far too short and doesn’t describe the resource that it manages clearly enough for other developers
- **B.** The endpoint should require an API key on every single request to prevent unauthorized access to any of the stored user data
- **C.** Each endpoint should do one thing — use /api/users with GET, POST, PUT, DELETE instead of one catch-all that handles everything  ✅
- **D.** The endpoint simply needs a few more parameters so it can properly distinguish between all the different types of user operations it supports

> **Answer:** C

### Q11. Your API endpoint uses the four REST methods. A junior teammate asks: ‘Why can’t we just use POST for everything?’ What is the best explanation of why different HTTP methods matter?

- **A.** Using different methods is just a leftover convention from the early days of the web with no real practical benefit in modern applications
- **B.** Each method communicates intent: GET = retrieve (cacheable), POST = create, PUT = update, DELETE = remove. Correct methods make the API predictable  ✅
- **C.** POST is actually fine for everything — the HTTP methods are interchangeable and the server can determine the action from the request body
- **D.** Different methods are only really needed for security reasons — GET requests are less secure than POST requests because the submitted data appears in the URL

> **Answer:** B

### Q12. Your backend always returns 500 ‘Internal Server Error’ — whether the user sends bad data, requests something missing, or the database is down. Why is this a problem?

- **A.** Error handling is purely a frontend responsibility — the backend should just process the data and let the frontend decide how failures get handled
- **B.** It’s not a problem — every error should return 500 because the specific error type is an internal detail that the client never needs to see or handle
- **C.** The error message text should be longer and much more descriptive, but the 500 status code itself is the correct one to use for every kind of failure
- **D.** Different errors need different responses: bad data = 400 with field errors, missing resource = 404, only real crashes = 500. Generic errors make debugging impossible.  ✅

> **Answer:** D

### Q13. AI generated backend code for a new feature. Your mentor says test with Postman, not through the frontend. Why is an API tool better for verifying backend behavior?

- **A.** Postman is faster than using a browser and consumes far fewer system resources, which makes it a better choice for running the same tests repeatedly
- **B.** Frontend testing is always unreliable because different browsers handle network requests differently depending on each individual user’s configured settings
- **C.** An API tool lets you send specific requests and see exact responses — test edge cases (missing fields, bad data, unauthorized access) that are hard to trigger via the frontend  ✅
- **D.** Postman automatically detects and highlights any bugs in your API responses after each run so that you can find and fix every one of them much faster

> **Answer:** C

### Q14. You tested your order endpoint with three valid orders — all passed. In production, it crashes on empty carts, expired sessions, and special-character coupon codes. What pitfall is this?

- **A.** You tested on the wrong server — the development environment doesn’t match the production configuration, so results there never predict real behavior
- **B.** Three test orders weren’t nearly enough — you needed at least 100 of them to get a statistically meaningful sample of the possible inputs
- **C.** You should have tested everything on real mobile devices, since the majority of checkout failures come from mobile-specific browser limitations and rendering quirks
- **D.** You only tested the happy path — valid data that works. You didn’t test empty fields, expired sessions, special characters, or other real-world edge cases  ✅

> **Answer:** D

### Q15. Your endpoint returns 200 — so you called it working. But you never checked the response body. A researcher finds it exposes password hashes and personal data. What pitfall is this?

- **A.** Not checking what your API actually returns — you verified the status code but never inspected the response data, which exposes sensitive info  ✅
- **B.** The endpoint should really return a 201 status code instead of 200 because it is serving user-created content to the client rather than static data
- **C.** The data should simply be encrypted in transit using HTTPS so that none of the sensitive fields can be intercepted by any third parties
- **D.** Password hashes are safe to expose in responses because they’re encrypted versions of the password that can’t be reversed by attackers

> **Answer:** A

### Q16. AI created DELETE /api/users/:id. It works — you can delete a user. But there’s no auth check — anyone with a user’s ID can delete accounts without logging in. What pitfall is this?

- **A.** Skipping authentication on a sensitive endpoint — AI built the delete function but didn’t verify the requester is logged in and authorized  ✅
- **B.** The endpoint URL is far too predictable — sequential user IDs sitting in the URL path make it very easy for attackers to guess valid targets to attack
- **C.** DELETE endpoints don’t need their own authentication check because the HTTP method itself already restricts who is able to use them
- **D.** The user ID should be a much longer random string instead of a simple number to prevent attackers from ever guessing valid IDs

> **Answer:** A

### Q17. AI created /api/do-everything — registration, login, orders, payments, and reporting all in one endpoint, determined by a ‘type’ parameter. What’s wrong?

- **A.** The endpoint name should simply be more professional and follow standard naming conventions that describe the underlying resource much more clearly
- **B.** One endpoint is actually more efficient for runtime performance because the server only ever needs to register, load, and handle one single route
- **C.** One giant endpoint instead of separate, focused ones is a maintenance nightmare — each action needs its own endpoint to test, secure, and update independently  ✅
- **D.** The ‘type’ parameter should really live in the URL path instead of the request body so that every incoming action is clearly visible inside the server’s request logs

> **Answer:** C

### Q18. Your dashboard request takes 30 seconds. The backend runs a complex report, and when it fails, the user sees only an endless spinner — no error, no timeout. What is missing?

- **A.** A faster backend server with much more processing power that can handle the complex report generation quickly enough that users never even notice a delay
- **B.** A prettier loading spinner with a detailed percentage progress bar so the user always knows the system is still actively working on their long-running request
- **C.** Timeouts and error handling for slow or failed requests — every request needs a reasonable timeout and a clear ‘something went wrong’ message when the server is slow or unavailable  ✅
- **D.** The user should just refresh the page manually — long-running reports are expected and the browser will automatically retry the failed request for them

> **Answer:** C

### Q19. AI’s booking system works in your demo. In production, users report double bookings (no time conflict check) and cancellations don’t refund credits. What pitfall is this?

- **A.** The demo environment is simply different from production — database settings and server configurations often cause features to work in one but not the other
- **B.** Treating AI’s first output as production-ready — it works for demos but breaks in real use because edge cases (conflicts, refunds) weren’t tested  ✅
- **C.** Backend code can’t handle bookings natively — you need a specialized third-party scheduling service to manage the time slots and conflicts
- **D.** You need a different database engine in production because demo databases never enforce constraints like keeping time slots unique

> **Answer:** B

### Q20. You want AI to build an endpoint for a contact form. Which description would most likely produce a working endpoint on the first or second try?

- **A.** ‘POST /api/contact: name (required), email (required, valid format), message (required, min 10 chars). Validate all. Return 400 with field errors on failure, 201 on success.’  ✅
- **B.** ‘Build a contact form endpoint that saves incoming messages somewhere sensible and sends a confirmation to the user whenever they submit the form’
- **C.** ‘Make the backend work properly for the contact page — it should handle all of the form submissions and store them somewhere that seems reasonable’
- **D.** ‘I need a REST API for contacts that handles absolutely everything the frontend ever sends over to it and stores all of it properly somewhere safe’

> **Answer:** A

### Q21. You verified your endpoint by clicking through the frontend — it works. Your mentor says also test with Postman. Why is frontend-only testing insufficient?

- **A.** Postman has a much better user interface than a browser window and organizes your test results so they are much easier to review afterward
- **B.** Frontend testing only shows what the app displays — you can’t inspect raw responses, test edge cases (missing fields, wrong types), or verify auth handling  ✅
- **C.** Browsers can’t actually make API requests directly by themselves — they always need a frontend application to format and send the requests properly
- **D.** Postman tests are formally required for deployment — most modern hosting platforms won’t accept your code for release without documented API tests attached to it

> **Answer:** B

### Q22. Your API returns id, name, email, role, password_hash, and internal_notes for a user profile. The frontend only needs name and email. What problems do you see?

- **A.** The response includes sensitive data (password_hash, internal_notes) and internal details the frontend doesn’t need — only return required fields  ✅
- **B.** The response is completely fine — extra data doesn’t hurt performance and the frontend can simply ignore any fields it doesn’t need
- **C.** The JSON format is wrong — the user profile data should be nested underneath a ‘user’ key instead of sitting flat at the top level of the response
- **D.** The response should really be in XML instead of JSON because XML provides a far better structure for complex nested data like these detailed user profiles

> **Answer:** A

### Q23. You send invalid data (missing email) and get status 500 with a generic ‘Internal Server Error’ — no details on what went wrong. What should the response be?

- **A.** Status 400 with a specific error like {"fields": {"email": "Email is required"}} — telling the frontend exactly what’s missing so it can show a useful message  ✅
- **B.** Status 500 is the correct choice — the error message just needs to be much longer and include the full server stack trace for easier debugging
- **C.** Status 200 with the error details in the response body — the status code should always be 200 and the errors belong in the data payload
- **D.** No response at all — the server should just silently reject the bad input and let the frontend handle the resulting timeout gracefully

> **Answer:** A

### Q24. Your registration endpoint accepts any data without validation. You can create a user with email: ‘12345’, age: ‘hello’, and name: ‘’. What should the endpoint do instead?

- **A.** Accept the data and let the frontend handle all validation — server-side checks just slow down the registration flow for legitimate users
- **B.** Only validate the email format and simply ignore the other fields — email is the only field that truly needs to follow a specific required structure
- **C.** Store the submitted data exactly as-is and flag it for manual review — an administrator can clean up any of the bad entries later during scheduled database audits
- **D.** Validate before processing: check email format, age is a positive number in a reasonable range, name is not empty — reject invalid data with specific errors  ✅

> **Answer:** D

### Q25. Save Profile stops working. The Network tab shows a PUT to /api/users/profile returning 401 Unauthorized. What does this tell you, and what is the likely issue?

- **A.** The request was rejected — 401 means the session may have expired or the auth token is missing/invalid. Use the Network tab to tell AI exactly what to fix.  ✅
- **B.** The server is completely down and nothing is working — 401 errors indicate the backend service has crashed and needs an immediate restart
- **C.** PUT requests are simply not allowed on this server — some hosting platforms deliberately block both PUT and DELETE methods for security reasons
- **D.** The profile endpoint was entirely deleted from the codebase — someone must have removed it accidentally during a recent deployment or a routine code cleanup pass

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/102900576_
