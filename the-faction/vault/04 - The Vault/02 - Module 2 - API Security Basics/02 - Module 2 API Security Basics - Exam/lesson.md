---
course: "The Vault"
module: "Module 2 — API Security Basics"
lesson: "Module 2: API Security Basics — Exam"
type: "course_quiz"
post_id: 104378409
space_id: 24302166
source: "https://the-faction.mn.co/posts/104378409"
updated: "2026-08-27T20:10:51Z"
---

# Module 2: API Security Basics — Exam

> Exam for **Module 2 — API Security Basics** (The Vault) — 25 questions. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI-built API has a GET /api/invoices/456 endpoint. It returns invoice 456 without checking whether the logged-in user owns that invoice. An attacker changes the ID to 457 and sees another user's data. What vulnerability is this?

- **A.** Broken Object-Level Authorization — the API returns data without verifying that the requesting user owns the requested resource  ✅
- **B.** Insecure Direct Object Reference — the API uses predictable sequential IDs instead of randomized UUIDs for resource identification
- **C.** Missing Authentication — the API endpoint does not require any login token and serves data to completely unauthenticated visitors
- **D.** Excessive Data Exposure — the API returns the full invoice record including fields the frontend does not display to the end user

> **Answer:** A

### Q2. Your user update endpoint accepts any field sent in the request body. An attacker sends a request containing role: admin alongside their profile changes. Their account is now an admin. What API vulnerability is this?

- **A.** Privilege escalation through a broken role hierarchy where admin access is granted by the platform without proper approval workflows
- **B.** Mass assignment — the endpoint accepts and applies all submitted fields without whitelisting which properties the client can modify  ✅
- **C.** Broken authentication that allows users to modify their own session tokens to include elevated permission claims after initial login
- **D.** Insecure deserialization where the request body payload is processed without validation of the object structure or field boundaries

> **Answer:** B

### Q3. Your API returns the full user database record on every request including password hash, internal notes, billing details, and admin flags. The frontend only displays the user's name and avatar. What should change?

- **A.** Add frontend filtering to hide sensitive fields from the overall rendered display while keeping the full API response for future feature flexibility
- **B.** Encrypt the API response payload so that sensitive fields are unreadable even though they are transmitted alongside the visible data fields
- **C.** Return only the specific fields the client needs — name and avatar — and exclude password hashes, billing, and internal data from the response  ✅
- **D.** Mark sensitive fields as private in the API documentation so frontend developers know not to render them in user-facing interface components

> **Answer:** C

### Q4. Your login endpoint has no rate limiting. A penetration tester demonstrates that they can send 10,000 password attempts per minute against a single account without being blocked. What protection is needed?

- **A.** Require passwords with minimum 20 characters, special characters, and numbers so that brute force attempts take exponentially longer to succeed
- **B.** Add CAPTCHA verification on every single login attempt so automated scripts must solve a visual challenge before each password submission
- **C.** Implement account lockout after 3 failed attempts that permanently disables the account until a system administrator reactivates it manually
- **D.** Rate limiting per IP and per account with progressive delays — slowing responses after repeated failures to make brute force impractical  ✅

> **Answer:** D

### Q5. Your API error responses include the full stack trace with file paths, function names, and database table names. A security reviewer flags this. Why is this dangerous in production?

- **A.** Stack traces reveal internal architecture details — file paths, table names, and library versions that help attackers plan targeted exploits  ✅
- **B.** Stack traces consume excessive bandwidth when errors occur frequently which can degrade API response times during high-traffic error events
- **C.** Stack traces in error responses violate data privacy regulations because they may inadvertently contain fragments of user-submitted input data
- **D.** Stack traces are cached by browsers and proxy servers which means sensitive internal details persist in locations outside your direct control

> **Answer:** A

### Q6. Your AI created an API endpoint that accepts a JSON body for creating a new user. The endpoint processes the request without validating that required fields exist, data types match, or string lengths are reasonable. What is the risk?

- **A.** Missing validation only affects user experience since invalid data will cause display errors on the frontend but does not create security risks
- **B.** The database schema constraints will reject invalid data types and enforce field length limits ensuring that application-level validation is redundant work
- **C.** Unvalidated input enables injection attacks, storage abuse, and processing errors — every field needs type, length, and format validation applied  ✅
- **D.** JSON parsing libraries automatically validate data types during deserialization so the input is inherently validated by the time your code runs

> **Answer:** C

### Q7. Your API uses sequential integer IDs for all resources: /api/orders/1, /api/orders/2, /api/orders/3. An attacker iterates through IDs and downloads every order in the system. Besides adding authorization checks, what should change about the IDs?

- **A.** Encrypt the integer IDs in the URL using a reversible cipher so attackers cannot determine the underlying numeric sequence from the URL alone
- **B.** Use UUIDs instead of sequential integers — unpredictable identifiers prevent enumeration even if an authorization check is accidentally missing  ✅
- **C.** Start the ID sequence at a random large number like 847291 so attackers cannot guess that the sequence begins at one and count upward from there
- **D.** Hash the integer ID with a server secret before including it in the URL so each ID appears random but can be decoded by your backend reliably

> **Answer:** B

### Q8. Your API endpoint DELETE /api/users/123 deletes any user when called. There is no authentication check, no authorization check, and no confirmation step. An attacker discovers this endpoint. What is the impact?

- **A.** The endpoint would only delete the overall user's own account since the session context automatically scopes destructive operations to the current user
- **B.** Delete operations on most databases are soft deletes that mark records as inactive so the data can be recovered by an administrator if needed
- **C.** The endpoint is only referenced in the admin frontend component so regular users would not know it exists unless they inspect the source code
- **D.** Any visitor can delete any user account — unprotected destructive endpoints allow complete data destruction without authentication or authorization  ✅

> **Answer:** D

### Q9. Your API returns a 403 Forbidden for unauthorized requests to /api/admin/users. But it returns 404 Not Found for /api/admin/settings which also exists but is restricted. A security reviewer says both should return the same status. Why?

- **A.** Different error codes for restricted endpoints reveal which admin routes exist — an attacker uses 403 versus 404 to map your hidden admin surface  ✅
- **B.** Returning 404 for restricted endpoints confuses legitimate administrators who need clear feedback about why their access request was denied
- **C.** HTTP status codes are standardized and using 404 for authorization failures violates the HTTP specification which could break client compatibility
- **D.** Error code consistency is a code quality issue not a security concern since attackers focus on exploitable vulnerabilities rather than response codes

> **Answer:** A

### Q10. Your API accepts file uploads via a multipart form endpoint. The server processes uploaded files without checking the Content-Type header, file extension, or actual file content. What types of attacks does this enable?

- **A.** Only denial-of-service through large file uploads that consume server disk space and processing resources until storage limits are exceeded
- **B.** File uploads without validation are safe as long as the uploaded files are stored in a directory that does not allow direct public web access
- **C.** The web framework automatically validates uploaded file content and rejects executable files before they reach your application's handler code
- **D.** Unrestricted uploads enable remote code execution, stored XSS via HTML files, malware distribution, and server resource exhaustion from oversized files  ✅

> **Answer:** D

### Q11. Your API endpoint GET /api/users returns a list of all users with their email addresses, phone numbers, and account creation dates. Any authenticated user can call this endpoint. What is the authorization problem?

- **A.** The endpoint is correctly available to all authenticated users since any registered member should be able to view the community member directory
- **B.** Adding pagination to limit the number of users returned per request would reduce the data exposure to a manageable and less exploitable amount
- **C.** Regular users should not access the full user list with contact details — this endpoint should be restricted to admin roles with a business justification  ✅
- **D.** Removing email and phone from the overall response while keeping names and avatars would make the endpoint safe for all authenticated users to access freely

> **Answer:** C

### Q12. Your API uses JWT tokens for authentication. The tokens are set to never expire. A user's token is stolen through a compromised public WiFi network three months ago. The attacker can still use it today. What should tokens have?

- **A.** Tokens should be encrypted with the user's password hash so that changing the password automatically invalidates all previously issued token values
- **B.** Short expiration times with refresh token rotation — access tokens expire in 15-60 minutes forcing regular renewal and limiting stolen token lifespan  ✅
- **C.** IP address binding that locks each token to the IP address where it was originally issued ensuring that using the token from a different network location fails
- **D.** Device fingerprint validation that checks the browser and operating system combination on each request to detect tokens used from unfamiliar devices

> **Answer:** B

### Q13. Your API endpoint POST /api/transfer accepts a JSON body with fromAccount, toAccount, and amount. The endpoint does not verify that the authenticated user owns the fromAccount. What can an attacker do?

- **A.** Transfer money from any account to any other account — the endpoint processes the request based on the body content not the authenticated identity  ✅
- **B.** Only view the balance of other accounts since the transfer would fail at the banking provider level even if the API processes the request successfully
- **C.** The frontend form restricts the fromAccount field to the user's own account so attackers would need to modify the request outside the normal interface
- **D.** Transfers require two-factor confirmation via SMS code so even if the API accepts the request the transfer would not complete without phone access

> **Answer:** A

### Q14. Your API responds to an OPTIONS preflight request with Access-Control-Allow-Methods: GET, POST, PUT, DELETE, PATCH for every endpoint. Some endpoints only support GET. Why is this a problem?

- **A.** The preflight response adds an extra network round trip for every request which degrades performance for users on slow mobile connections
- **B.** Advertising unsupported methods tells attackers which HTTP verbs to try — each endpoint should only allow the specific methods it actually implements  ✅
- **C.** The OPTIONS response is informational only and does not grant actual access to the listed methods so the security impact is negligible in practice
- **D.** CORS preflight responses are handled by the browser's security engine and are not visible to attackers even through browser developer tools inspection

> **Answer:** B

### Q15. Your AI built a webhook endpoint that receives payment notifications from Stripe. The endpoint processes any POST request to /api/webhooks/stripe without verifying the webhook signature. What can an attacker do?

- **A.** Nothing significant — webhook payloads only contain event notifications and do not include any sensitive customer financial information or credentials
- **B.** Webhook URLs are not publicly discoverable so only Stripe's servers would know the endpoint path and an attacker cannot send forged requests to it
- **C.** The payment processing logic validates the payment independently through the Stripe API so a forged webhook would not actually modify any account data
- **D.** Send forged payment notifications — the attacker can trigger your system to grant access, ship products, or credit accounts for payments never made  ✅

> **Answer:** D

### Q16. Your API returns different response times for valid versus invalid usernames on the login endpoint. Valid usernames take 200ms (password hash comparison) while invalid ones return in 5ms. What information does this leak?

- **A.** Response time differences are imperceptible to human users and only detectable by automated tools that most attackers do not commonly have access to
- **B.** The timing difference is caused by the database query which runs faster when no matching record exists and this behavior cannot be changed in practice
- **C.** Timing-based account enumeration — attackers measure response times to determine which usernames exist in your system without needing any password  ✅
- **D.** Timing variations are a performance optimization concern not a security vulnerability since the endpoint still requires a correct password for access

> **Answer:** C

### Q17. Your API has an endpoint POST /api/comments that creates a comment on any resource. The endpoint checks that the user is authenticated but does not verify they have permission to comment on the specific resource. What authorization model is missing?

- **A.** Resource-level authorization — verify the user has permission to interact with the specific resource, not just that they have a valid session token  ✅
- **B.** Role-based access control that restricts the comment feature to users with a specific commenter role assigned in the platform administration panel
- **C.** Rate limiting on the comments endpoint that prevents users from posting more than a defined number of comments per hour across all resources combined
- **D.** Content moderation that reviews submitted comments for policy violations before publishing them to the resource's visible comment thread for others

> **Answer:** A

### Q18. Your API logs every request in a structured log format. You notice that POST /api/login requests include the submitted password in the log entry alongside the username and timestamp. What should change?

- **A.** Encrypt the log files at rest so that passwords stored in logs are protected even if an attacker gains access to the log storage system directly
- **B.** Reduce the log retention period from 90 days to 7 days ensuring that that logged passwords are automatically deleted before they can be discovered and exploited
- **C.** Move the log files to a restricted directory that only the operations team can access so the password exposure is limited to trusted personnel only
- **D.** Sanitize sensitive fields before logging — passwords, tokens, and credit card numbers must never appear in log entries regardless of storage security  ✅

> **Answer:** D

### Q19. Your AI built a GraphQL API that allows clients to construct arbitrary nested queries. An attacker sends a deeply nested query that causes the server to consume all available memory and crash. What protection is needed?

- **A.** Query depth limiting and complexity analysis — reject queries that exceed defined nesting depth or estimated computational cost before execution begins  ✅
- **B.** Increase the server memory allocation to handle deeply nested queries since GraphQL is designed to support flexible client-defined query structures
- **C.** Switch from GraphQL to REST APIs which do not allow client-defined query complexity and therefore eliminate this category of resource exhaustion attack
- **D.** Add request timeout limits that kill any query exceeding 30 seconds so deeply nested queries are terminated before they can crash the entire server

> **Answer:** A

### Q20. Your API serves both public content and private user data. All endpoints use the same authentication middleware. An attacker finds that the public /api/blog/posts endpoint also accepts and processes authentication tokens. Why is this a concern?

- **A.** Public endpoints that process tokens provide a better user experience by personalizing public content based on the authenticated user's preferences
- **B.** Processing valid tokens on public endpoints is harmless because the endpoint only returns public data regardless of whether a token is present or not
- **C.** Stolen tokens can be validated against public endpoints to confirm they work — and token processing on public routes expands the attack surface unnecessarily  ✅
- **D.** Authentication middleware on public endpoints adds processing overhead that slows response times for content that does not require any access control

> **Answer:** C

### Q21. Your API endpoint PATCH /api/users/123 accepts partial updates. The endpoint uses the same handler for regular users and admins. A regular user sends a PATCH with isVerified: true and their account becomes verified. What control is missing?

- **A.** Separate API endpoints for user self-service updates versus administrative user management to physically isolate the two authorization contexts
- **B.** Field-level authorization — certain fields like isVerified and role should only be modifiable by admin users, not by the resource owner themselves  ✅
- **C.** Request schema validation that rejects any request containing fields not explicitly listed in the API documentation for that specific endpoint version
- **D.** A review queue where user-submitted profile changes are held for administrator approval before being applied to the user's account record permanently

> **Answer:** B

### Q22. Your API uses API keys for service-to-service authentication. All services share a single API key. If one service is compromised, the attacker has access to every other service in the system. What should be different?

- **A.** Rotate the shared API key on a weekly schedule so that a compromised key is only valid for a maximum of seven days before it expires automatically
- **B.** Add IP allowlisting so the shared API key only works from specific server IP addresses reducing the risk of exploitation from unauthorized locations
- **C.** Encrypt the API key in transit using mTLS between services so that even if the key is intercepted it cannot be used from a different network location
- **D.** Issue unique API keys per service with minimum required permissions — compromising one service only exposes the specific access that service was granted  ✅

> **Answer:** D

### Q23. Your API responds to GET /api/health with a 200 status and includes your database version, OS version, framework version, and memory usage in the response body. This endpoint has no authentication. What is the exposure?

- **A.** Version information helps attackers identify known vulnerabilities in your specific software versions — health endpoints should return status only, not internals  ✅
- **B.** Health endpoints are used by load balancers and monitoring tools that need detailed system information to make routing and alerting decisions accurately
- **C.** The information returned is already visible in HTTP response headers so including it in the health endpoint body does not create additional exposure risk
- **D.** Monitoring tools require unauthenticated health endpoints to function properly so adding authentication would break infrastructure health check workflows

> **Answer:** A

### Q24. Your API processes a webhook from a payment provider and immediately provisions the purchased subscription without verifying the payment status by calling the provider's API. A attacker sends a fake success webhook. What verification step is missing?

- **A.** Webhook signature verification confirms the request came from the payment provider and is sufficient to trust the payment status in the webhook payload
- **B.** The payment provider's webhook infrastructure guarantees delivery accuracy so additional verification is redundant and adds unnecessary API call overhead
- **C.** Server-side payment verification — after receiving the webhook, call the payment provider's API directly to confirm the payment status before provisioning  ✅
- **D.** Add a delay between receiving the webhook and provisioning the subscription so the payment has time to clear through the banking system completely first

> **Answer:** C

### Q25. Your API returns paginated results but allows the client to set the page size parameter. An attacker sends pageSize=1000000 and the server attempts to load a million records into memory. What should the API enforce?

- **A.** Remove the client-configurable page size entirely and use a server-defined fixed page size of 20 results for all list endpoints without any override option
- **B.** A maximum page size limit enforced server-side — accept the client's preference up to a defined ceiling and ignore values that exceed the allowed maximum  ✅
- **C.** Streaming pagination that sends results progressively as they are loaded from the database so the server never holds all records in memory simultaneously
- **D.** Database query timeouts that kill any query exceeding 5 seconds so oversized page requests are terminated before they can consume excessive server memory

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/104378409_
