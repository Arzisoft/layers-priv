---
course: "The Vault"
module: "Module 1 — Your App's Attack Surface"
lesson: "Module 1: Your App's Attack Surface — Exam"
type: "course_quiz"
post_id: 104379952
space_id: 24302166
source: "https://the-faction.mn.co/posts/104379952"
updated: "2026-08-27T20:10:51Z"
---

# Module 1: Your App's Attack Surface — Exam

> Exam for **Module 1 — Your App's Attack Surface** (The Vault) — 25 questions. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI tool built a login form that works correctly. You inspect the page source and find your Stripe secret key hardcoded in the JavaScript bundle. What is the exposure?

- **A.** Every user who loads your page can see the key in their browser — client-side secrets are visible to anyone who views the source  ✅
- **B.** The key is safe because browsers encrypt all JavaScript source code before rendering it on the user's screen by default
- **C.** Only users with browser developer tools installed can view the page source so the exposure is limited to technical users
- **D.** The Stripe secret key is a publishable key designed to be visible in frontend code and does not grant account-level access

> **Answer:** A

### Q2. Your AI-built dashboard renders user-submitted comments on a community page. A user submits a comment containing a script tag. When other users view the page, the script executes in their browser. What vulnerability is this?

- **A.** Server-Side Request Forgery — the comment triggers the server to make requests to internal services on behalf of the attacker
- **B.** Cross-Site Scripting (XSS) — user input rendered without sanitization allows attacker scripts to execute in other users' browsers  ✅
- **C.** SQL Injection — the comment modifies a database query that exposes or corrupts data stored in the application's backend tables
- **D.** Cross-Site Request Forgery — the overall comment forces other users' browsers to perform actions on the application without their consent

> **Answer:** B

### Q3. You run a security scan on your AI-built application. The scanner reports that your site can be loaded inside an iframe on any external website. What attack does this enable?

- **A.** Man-in-the-middle interception where attackers read data transmitted between the user's browser and your application server
- **B.** Session replay attacks where the attacker records and replays the user's authenticated session from within the embedding page
- **C.** Clickjacking — an attacker overlays your app in a transparent iframe and tricks users into clicking your buttons unknowingly  ✅
- **D.** Domain spoofing where the attacker's page inherits your application's SSL certificate and appears as a trusted secure connection

> **Answer:** C

### Q4. Your application's JavaScript bundle includes references to /api/admin/users and /api/internal/export. These endpoints are not shown in the UI but are callable from the browser. What is the risk?

- **A.** The endpoints will fail because they require UI-generated tokens that cannot be replicated from the browser's developer console
- **B.** These internal routes are protected by network-level firewall rules that prevent direct browser access from external IP addresses
- **C.** Hidden endpoints are standard practice and pose no risk as long as they require authentication before returning any data response
- **D.** Attackers discover internal endpoints by reading your bundle — every hidden route without server-side auth is an exploitable entry point  ✅

> **Answer:** D

### Q5. Your AI built a contact form that accepts a name, email, and message. You notice the form submits all three fields without any validation or sanitization on either the client or server. What is the primary concern?

- **A.** Unvalidated input can carry injection payloads — script tags, SQL fragments, or malformed data that exploits downstream processing  ✅
- **B.** The form will accept very long inputs that consume excessive database storage space and increase hosting costs over time unnecessarily
- **C.** Users may enter incorrect email formats which will cause delivery failures when the platform attempts to send confirmation messages
- **D.** Missing client-side validation creates a poor user experience because users are not informed of input errors before form submission

> **Answer:** A

### Q6. You check your application's HTTP response headers and find no Content-Security-Policy, no Strict-Transport-Security, and no X-Frame-Options. The application works perfectly. Why are these headers still needed?

- **A.** Search engines rank sites with security headers higher so missing headers negatively impact your application's SEO performance score
- **B.** Modern browsers require these headers and will display warning messages to users when visiting sites that do not include them properly
- **C.** Security headers prevent entire categories of browser-based attacks — without them, XSS, clickjacking, and downgrades have maximum impact  ✅
- **D.** Hosting providers require security headers for compliance and may suspend your account if their automated scans detect missing headers

> **Answer:** C

### Q7. Your AI-built image upload feature accepts any file type. An attacker uploads an HTML file disguised as an image. When another user clicks the uploaded file link, the HTML executes in their browser session. What should the upload handler check?

- **A.** File size limits only — restrict uploads to under 5MB to prevent large malicious payloads from being stored on your application server
- **B.** Validate file type by checking the actual file content (magic bytes), not just the extension — reject anything that isn't a real image  ✅
- **C.** Scan uploaded files with antivirus software before storing them to detect known malware signatures embedded in the file content data
- **D.** Store all uploaded files in a private directory that is not directly accessible via URL so users cannot link to uploaded content directly

> **Answer:** B

### Q8. You open Chrome DevTools on your application and see API calls to /api/users/me returning your full user object including password hash, internal role flags, and billing details. The UI only displays your name and email. What is the problem?

- **A.** The API response is encrypted by HTTPS so the extra fields are protected during transmission and cannot be intercepted by attackers
- **B.** Only authenticated users can see their own data so returning additional fields does not create a vulnerability for other user accounts
- **C.** The frontend already filters which fields to display so the extra data in the API response is never visible to the end user directly
- **D.** Excessive data exposure — the API returns more fields than the client needs and anyone can see the full response in browser dev tools  ✅

> **Answer:** D

### Q9. Your staging environment is accessible at staging.yourapp.com with no authentication required. It contains a copy of real user data for testing purposes. A search engine indexes the staging site. What are the two problems?

- **A.** Staging should be access-restricted and never contain real user data — use synthetic test data and require authentication for access  ✅
- **B.** Add a robots.txt file to prevent search engine indexing and the staging environment will be sufficiently protected from external access
- **C.** Staging environments are internal tools that do not need the same security controls as production because they are temporary by nature
- **D.** Real user data in staging is acceptable for realistic testing as long as the staging database is deleted after each testing cycle ends

> **Answer:** A

### Q10. Your AI built a user profile page that displays the user's data by reading the user ID from the URL: /profile/123. There is no server-side check that the logged-in user is actually user 123. What can an attacker do?

- **A.** Nothing — the profile page only shows non-sensitive public information that any user is allowed to view on the platform regardless
- **B.** The URL-based ID is encrypted using a hash function that prevents attackers from guessing other users' profile identifiers easily
- **C.** The frontend routing ensures that users can only navigate to their own profile so manually editing the URL would redirect them back
- **D.** View any user's profile by changing the ID in the URL — without server-side ownership verification, every profile is publicly accessible  ✅

> **Answer:** D

### Q11. Your application logs every request including the full URL. A password reset link containing a secret token appears in your log files: /reset?token=abc123xyz. Who else might see this token?

- **A.** Log files are stored securely on the server and are only accessible to the application runtime process that generates them automatically
- **B.** Password reset tokens expire within minutes so even if the token appears in logs it would be unusable by the time anyone finds it there
- **C.** Anyone with log access — engineers, monitoring tools, log aggregation services — can extract the token and reset that user's password  ✅
- **D.** Tokens in URL parameters are automatically encrypted by the web server before being written to log files to prevent exposure in logs

> **Answer:** C

### Q12. Your application serves pages over both HTTP and HTTPS. A user types your URL without https:// and the browser connects over HTTP first before redirecting to HTTPS. What is the risk during that initial HTTP connection?

- **A.** The HTTP connection is harmless because no sensitive data is transmitted until the overall user logs in which only happens after the HTTPS redirect
- **B.** An attacker on the same network can intercept the HTTP request before the redirect — capturing cookies, injecting content, or blocking HTTPS  ✅
- **C.** Modern browsers automatically upgrade HTTP connections to HTTPS so the unencrypted request never actually reaches your server in practice
- **D.** The initial HTTP request only loads the redirect instruction so the data exposure is limited to the redirect URL itself and nothing more

> **Answer:** B

### Q13. Your AI built a registration form that shows 'This email is already registered' when an existing user's email is entered. A competitor systematically enters email addresses to identify your user base. What information is being leaked?

- **A.** Account enumeration — the different responses for existing versus non-existing emails lets attackers build a list of your registered users  ✅
- **B.** The response message is a standard user experience pattern that helps legitimate users who forgot they already have an existing account
- **C.** Rate limiting on the registration endpoint would prevent systematic enumeration ensuring that the response message itself is not the actual problem
- **D.** Email addresses are not sensitive information since they are publicly available through business directories and social media platforms

> **Answer:** A

### Q14. Your application uses cookies to store session tokens. The cookies are set without the HttpOnly flag. Your application also has a stored XSS vulnerability on the comments page. What is the combined impact?

- **A.** Cookies without HttpOnly can still be read but the XSS vulnerability would need to match the exact cookie domain to access them properly
- **B.** The XSS script can read session cookies via JavaScript and send them to the attacker — stealing every user's session who views the page  ✅
- **C.** HttpOnly only affects first-party cookies so third-party session cookies would still be protected even without the flag being explicitly set
- **D.** The XSS vulnerability alone is the concern and the cookie flag setting does not meaningfully change the severity of the overall attack impact

> **Answer:** B

### Q15. Your AI created a search feature that puts the search query in the URL: /search?q=userInput. The search results page displays 'Showing results for: userInput' without encoding. What vulnerability exists?

- **A.** The search query is visible in the URL which exposes user search behavior to anyone who can see the browser's address bar or history
- **B.** Search queries stored in server logs create a privacy concern primarily because user search patterns reveal personal interests and browsing behavior
- **C.** URL-based search queries can be bookmarked and shared which might expose sensitive search terms to unintended recipients via link sharing
- **D.** Reflected XSS — an attacker crafts a URL with script code as the query and sends it to a victim whose browser executes the injected script  ✅

> **Answer:** D

### Q16. Your security scan shows that your application server returns detailed error messages including stack traces, file paths, and database table names when an error occurs. Why is this a security issue in production?

- **A.** Detailed errors slow down the server response time because generating stack traces requires additional processing overhead per request
- **B.** Error messages consume excessive log storage space when errors occur frequently during peak traffic periods or automated scanning activity
- **C.** Internal details like file paths, table names, and stack traces give attackers a map of your architecture to plan targeted exploitation  ✅
- **D.** Detailed errors are helpful for debugging and should remain enabled in production so the development team can diagnose issues faster remotely

> **Answer:** C

### Q17. Your application has a form that accepts a phone number. The server stores whatever string the user submits without validation. An attacker submits a 50,000-character string. What problems can this cause?

- **A.** Database storage abuse, potential denial of service, and downstream processing failures wherever the application reads that phone number field  ✅
- **B.** The database column length constraint will automatically truncate the input to the defined field size preventing any storage or processing issues
- **C.** A 50,000-character phone number is harmless because the field is only used for display purposes and never processed by any backend logic
- **D.** Input length alone is not a security concern since the content of the string matters more than its size for exploitation potential overall

> **Answer:** A

### Q18. Your AI built an admin panel at /admin with a login form. The panel is functional and contains user management tools. You deployed it to production without changing the default credentials admin/admin. What is the risk?

- **A.** Default credentials are acceptable for initial deployment as long as the administrator changes them during the first login session manually
- **B.** The admin panel URL is not linked from the main application so attackers would need to guess the path before they could attempt any login
- **C.** Adding IP-based access restrictions to the admin panel provides sufficient protection even if the default credentials remain unchanged
- **D.** Automated scanners check common admin paths with default credentials — your admin panel will be discovered and compromised within hours  ✅

> **Answer:** D

### Q19. Your application accepts file uploads and stores them in a publicly accessible directory served by the web server. An attacker uploads a PHP file. When they navigate to the uploaded file URL, the server executes it. What should be different?

- **A.** Store uploads outside the web-accessible directory, validate file types by content, and serve files through a handler that sets safe headers  ✅
- **B.** Rename uploaded files with random identifiers ensuring that attackers cannot predict the URL path needed to access and trigger their uploaded payload
- **C.** Add a file extension whitelist that blocks PHP files specifically while allowing all other file types to be uploaded without restrictions
- **D.** Configure the web server to require authentication before serving any file from the upload directory to prevent anonymous file execution

> **Answer:** A

### Q20. You inspect your application's cookies and find a session token stored with no Secure flag and no SameSite attribute. What attacks do these missing attributes enable?

- **A.** Missing Secure flag allows the cookie to persist beyond the browser session which extends the window for session theft after the user leaves
- **B.** Missing SameSite attribute prevents the browser from sending the cookie on subsequent visits which forces users to re-authenticate every time
- **C.** Without Secure, the cookie transmits over HTTP where it can be intercepted — without SameSite, the cookie sends on cross-site requests enabling CSRF  ✅
- **D.** Both flags are optional convenience features that improve user experience but do not materially impact the security posture of the session cookie

> **Answer:** C

### Q21. Your AI built a password change feature. The form only requires the new password — it does not ask for the current password. If an attacker has a stolen session cookie, what can they do?

- **A.** Nothing additional — if the attacker has the session cookie they already have full account access so the password form is not a factor
- **B.** Change the password without knowing the current one — locking the real user out permanently while the attacker maintains persistent access  ✅
- **C.** The session cookie alone does not grant access to account settings because sensitive operations require a separate elevated authentication step
- **D.** Password changes through the form are logged and the real user would receive an email notification allowing them to reverse the change quickly

> **Answer:** B

### Q22. Your application uses CORS headers set to Access-Control-Allow-Origin: * which allows any website to make API requests to your backend. Why is this dangerous for authenticated endpoints?

- **A.** The wildcard CORS header is the standard default for public APIs and only needs restriction if your API handles financial transaction data
- **B.** CORS headers only affect browser requests and do not impact server-to-server API calls so the wildcard has limited practical security impact
- **C.** Modern browsers ignore CORS headers for same-origin requests so the wildcard only affects cross-origin requests from third-party websites
- **D.** Any malicious website can make authenticated requests to your API using the visitor's cookies — reading their data or performing actions on their behalf  ✅

> **Answer:** D

### Q23. You deploy your application and forget to remove a /api/debug endpoint that returns your application's full configuration including database credentials and API keys. How quickly will this be discovered?

- **A.** Automated bots continuously scan for common debug endpoints — exposed configuration with credentials will likely be found within minutes to hours  ✅
- **B.** Debug endpoints are only accessible from localhost by default ensuring that external attackers cannot reach them even if the route exists in production code
- **C.** The endpoint requires the application to be in debug mode which is automatically disabled when deployed to a production hosting environment
- **D.** Configuration data returned by debug endpoints is encrypted by the framework runtime so credentials are not readable in the API response output

> **Answer:** A

### Q24. Your AI-built application has no rate limiting on any endpoint. An attacker writes a script that sends 10,000 login attempts per minute trying common passwords against every user account. What protection is missing?

- **A.** Account lockout after three failed attempts that permanently disables the account until a system administrator manually reactivates it
- **B.** CAPTCHA challenges on every single login attempt that require human verification before the username and password are submitted for processing
- **C.** Rate limiting that restricts login attempts per IP and per account — with progressive delays or temporary lockout after repeated failures  ✅
- **D.** Two-factor authentication that requires a second verification step which makes password-only brute force attacks completely ineffective always

> **Answer:** C

### Q25. You review your AI-built application and find that user input from a search form is used directly in a database query through string concatenation rather than parameterized queries. What attack does this enable?

- **A.** Cross-Site Scripting where the overall search input is reflected back to the user's browser and executed as JavaScript in their current session context
- **B.** SQL Injection — the attacker can modify the database query structure to read, modify, or delete data by crafting malicious search input strings  ✅
- **C.** Command Injection where the search input is passed to the operating system shell and executed as a system-level command on the web server
- **D.** Path Traversal where the search input navigates the server file system to read configuration files and source code outside the web directory

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/104379952_
