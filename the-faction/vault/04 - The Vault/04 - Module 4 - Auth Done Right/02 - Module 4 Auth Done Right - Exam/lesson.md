---
course: "The Vault"
module: "Module 4 — Auth Done Right"
lesson: "Module 4: Auth Done Right — Exam"
type: "course_quiz"
post_id: 104378660
space_id: 24302166
source: "https://the-faction.mn.co/posts/104378660"
updated: "2026-08-27T20:10:51Z"
---

# Module 4: Auth Done Right — Exam

> Exam for **Module 4 — Auth Done Right** (The Vault) — 25 questions. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI tool stores passwords using MD5 hashing. A security reviewer says an attacker with a modern GPU can try 10 billion MD5 hashes per second. What hashing algorithm should you direct your AI to use instead?

- **A.** bcrypt or Argon2 — intentionally slow algorithms designed for password hashing that resist GPU-accelerated brute force cracking attempts  ✅
- **B.** SHA-512 which produces a longer hash output making it computationally harder for attackers to reverse engineer the original password value
- **C.** AES-256 encryption that converts passwords to ciphertext which can only be decrypted with a server-side key stored in environment variables
- **D.** HMAC-SHA256 which adds a secret key to the hashing process preventing rainbow table attacks against the stored password hash values

> **Answer:** A

### Q2. Your application stores JWT session tokens in the browser's localStorage. Your security audit also found an XSS vulnerability on the profile page. What is the combined risk of these two findings?

- **A.** The XSS vulnerability must be fixed but localStorage tokens are safe because browsers sandbox localStorage access to your specific domain only
- **B.** The XSS script can read all localStorage data including tokens — every user who visits the profile page has their session stolen by the attacker  ✅
- **C.** JWT tokens are cryptographically signed so even if stolen from localStorage an attacker cannot use them without the server's signing secret key
- **D.** The risk is limited because XSS scripts execute only once when the page loads and cannot maintain persistent access to localStorage data values

> **Answer:** B

### Q3. Your login endpoint does not regenerate the session ID after successful authentication. A security tester explains that the same session ID existed before and after login. What attack does this enable?

- **A.** Session replay where an attacker records and replays the authentication sequence to create additional authenticated sessions under the same user
- **B.** Token prediction where the attacker analyzes the session ID format to calculate future valid session identifiers from the observable pattern
- **C.** Session fixation — an attacker sets a known session ID before the user logs in, then uses that same ID to access the authenticated session afterward  ✅
- **D.** Credential stuffing where the attacker uses the fixed session to test stolen username and password combinations from other breached platforms

> **Answer:** C

### Q4. Your login endpoint allows unlimited authentication attempts with no delays or lockouts. A penetration tester runs 50,000 password attempts against a single account in one minute. What protection should be implemented?

- **A.** Require all users to set passwords with at least 20 characters including uppercase, lowercase, numbers, and special characters to resist guessing
- **B.** Add CAPTCHA verification on every login attempt so each submission requires human interaction before the username and password are processed
- **C.** Permanently lock accounts after 3 failed attempts requiring the user to contact support for manual reactivation of their locked account access
- **D.** Progressive rate limiting per IP and per account — increase delays after repeated failures and temporarily lock after a threshold is reached  ✅

> **Answer:** D

### Q5. Your password reset flow sends a reset link with a token that never expires and can be used multiple times. An old reset email from 6 months ago still works. What should reset tokens do instead?

- **A.** Expire within 15-60 minutes and become invalid after a single use — old tokens should never grant access to password change functionality  ✅
- **B.** Expire when the user's next login session begins so the token remains valid as a backup recovery method until the user accesses their account
- **C.** Include the user's current password hash so the token automatically invalidates if the password was already changed through a different method
- **D.** Require the user to answer their security questions in addition to clicking the reset link to add a second verification layer

> **Answer:** A

### Q6. Your password reset page responds differently based on whether the submitted email exists in the system. Existing emails get 'Reset link sent.' Non-existing emails get 'No account found.' What information is leaking?

- **A.** The response difference is helpful for users who may have forgotten which email they registered with and need guidance on their account status
- **B.** Rate limiting on the reset endpoint prevents automated enumeration so the different response messages do not create a practically exploitable risk
- **C.** Account enumeration — attackers systematically test email addresses to build a confirmed list of registered users for targeted password attacks  ✅
- **D.** The email existence check happens before any security-sensitive operation so revealing this information does not compromise account credentials

> **Answer:** C

### Q7. Your application implements logout by deleting the JWT token from the browser's localStorage. The server does not invalidate the token. An attacker who copied the token before logout can still use it. What should logout do?

- **A.** Logout should clear browser storage including cookies, localStorage, sessionStorage, and cached data to remove traces of the session
- **B.** Invalidate the session server-side — add the token to a deny list or use short-lived tokens with refresh rotation so old tokens stop working  ✅
- **C.** Redirect the user to the login page after clearing the token which ends their visual session even if the underlying token technically remains valid
- **D.** Set the token expiration to the current timestamp on the client side so the browser treats it as expired on any subsequent authentication attempt

> **Answer:** B

### Q8. Your AI implemented multi-factor authentication by sending a 4-digit code via SMS. The code is valid for 30 minutes and has no attempt limit. An attacker can try all 10,000 possible codes within that window. What should change?

- **A.** Increase the code length from 4 digits to 8 digits which expands the possible combinations from 10,000 to 100 million making brute force slower
- **B.** Switch from SMS codes to email-based verification codes which are delivered through more secure channels and are harder for attackers to intercept
- **C.** Require the user to enter their password again alongside the MFA code creating a dual verification step that an attacker must bypass simultaneously
- **D.** Limit code entry attempts to 5 tries, reduce the validity window to 5 minutes, and use 6-digit codes to make brute force verification impractical  ✅

> **Answer:** D

### Q9. Your application sends login credentials over HTTPS. But the login form page itself loads over HTTP before redirecting to HTTPS for submission. A security reviewer says this is still vulnerable. Why?

- **A.** An attacker can intercept the HTTP page load and modify the form to submit credentials to their own server before the HTTPS redirect ever occurs  ✅
- **B.** The HTTP page load exposes the login form HTML structure which reveals input field names that attackers use to craft automated login scripts
- **C.** Browser security indicators show a mixed-content warning when the form page loads over HTTP which reduces user trust but does not create a real attack
- **D.** The HTTP page load is cached by the browser and served on subsequent visits even after the site is fully configured to use HTTPS for all connections

> **Answer:** A

### Q10. Your application allows users to stay logged in indefinitely. A user's laptop is stolen. The thief opens the browser and has full access to the account with no re-authentication required. What session policy would reduce this risk?

- **A.** Require biometric authentication on every page load so stolen devices cannot access the application without the original user's fingerprint or face
- **B.** Encrypt all application data in the browser storage so that even with an active session the thief cannot read any information displayed on screen
- **C.** Monitor for unusual login locations and automatically terminate sessions when access originates from a geographic location the user has not visited before
- **D.** Session expiration after a defined inactivity period — require re-authentication after idle time so stolen devices with stale sessions are locked out  ✅

> **Answer:** D

### Q11. Your application uses OAuth to let users sign in with Google. The OAuth callback URL accepts any redirect parameter without validation. An attacker crafts a callback URL that sends the authorization code to their server. What vulnerability is this?

- **A.** Token leakage through referrer headers where the authorization code appears in the HTTP Referrer header when the user navigates to external pages
- **B.** Cross-site request forgery where the attacker forces the user's browser to initiate an OAuth flow that links the attacker's Google account instead
- **C.** Open redirect in the OAuth callback — unvalidated redirect parameters let attackers intercept authorization codes by redirecting to their own server  ✅
- **D.** Client-side token exposure where the authorization code appears in the browser's address bar and can be copied by anyone viewing the user's screen

> **Answer:** C

### Q12. Your application checks user roles on the frontend to decide which pages to show. An administrator demotes a user to a basic role. The user's cached frontend still shows admin pages and their API calls still succeed. What is broken?

- **A.** The frontend cache should be invalidated whenever user roles change by sending a push notification that forces the browser to reload all page assets
- **B.** Role enforcement must happen on the backend API — frontend checks are display logic only and cached roles let demoted users retain access indefinitely  ✅
- **C.** The user's JWT token should be re-issued with updated role claims whenever their permissions change so the frontend automatically reflects the new access
- **D.** A session timeout of 15 minutes would limit the window where cached roles remain active since the user must re-authenticate with their updated permissions

> **Answer:** B

### Q13. Your AI built a 'Remember Me' feature that stores the user's email and password in a browser cookie so they don't need to type it on return visits. What is wrong with this implementation?

- **A.** Storing credentials in cookies exposes them to theft — use a secure remember-me token that references the session server-side without containing secrets  ✅
- **B.** The cookie should be encrypted using the application's secret key so that even if stolen the credentials cannot be extracted without decryption capability
- **C.** Cookies are secure storage because they are scoped to the specific domain and cannot be accessed by JavaScript from other websites or browser extensions
- **D.** The remember-me feature should store only the email in the cookie and require the password to be entered manually on each return visit for safety

> **Answer:** A

### Q14. Your application issues JWT tokens signed with the HS256 algorithm. The signing secret is the word 'secret'. A security reviewer says any attacker can forge valid tokens. Why?

- **A.** The HS256 algorithm itself is weak and should be replaced with RS256 which uses asymmetric key pairs that are inherently more resistant to brute force
- **B.** The signing secret 'secret' is trivially guessable — attackers will try common words first and can then forge tokens with any user identity or role claims  ✅
- **C.** JWT tokens signed with HS256 transmit the signing secret in the token header which allows anyone who decodes the token to extract and reuse the key
- **D.** The token payload containing user claims is unencrypted in all JWT implementations regardless of signing algorithm so the secret provides no protection

> **Answer:** B

### Q15. Your application redirects users to a URL specified in a query parameter after login: /login?redirect=https://evil.com. After successful authentication, the user is sent to the attacker's site. What should the redirect handler validate?

- **A.** The redirect URL should be encoded and signed with a server-side secret so the handler can verify the URL was generated by your application originally
- **B.** The redirect should only work for URLs that use HTTPS protocol to ensure the user's session token is not exposed through unencrypted HTTP connections
- **C.** The redirect parameter should be limited to relative paths only by rejecting any URL that contains a protocol scheme like http or https in the value
- **D.** Only allow redirects to your own domain — validate that the redirect URL belongs to an approved allowlist of internal application paths and trusted domains  ✅

> **Answer:** D

### Q16. Your application stores user sessions in a database table. When a user changes their password, their existing sessions on other devices are not invalidated. An attacker who stole a session token before the password change still has access. What should password changes trigger?

- **A.** A notification email to the user listing all active sessions so they can manually review and terminate any sessions they do not recognize as legitimate
- **B.** An automatic password expiration policy that forces all users to change their password every 90 days reducing the overall lifespan of any stolen credentials
- **C.** Immediate invalidation of all existing sessions except the current one — a password change should end every other active session across all devices  ✅
- **D.** A 24-hour grace period where old sessions continue working so users on other devices have time to log in again with the new password without disruption

> **Answer:** C

### Q17. Your sign-up endpoint creates accounts without email verification. An attacker creates accounts using other people's email addresses. Those people later cannot register because their email is already taken. What verification step is missing?

- **A.** Email verification before account activation — send a confirmation link and only activate the account after the email owner clicks to prove ownership  ✅
- **B.** CAPTCHA verification on the sign-up form to prevent automated account creation which would reduce the volume of fraudulently registered email addresses
- **C.** A duplicate email check that warns the user if the email is already registered and provides a password reset link instead of blocking new registration
- **D.** Rate limiting on the sign-up endpoint to prevent mass account creation from a single IP address which would slow but not eliminate the email squatting

> **Answer:** A

### Q18. Your API accepts authentication tokens in the URL query string: /api/data?token=abc123. This token appears in server logs, browser history, and referrer headers when users click external links. Where should tokens be transmitted instead?

- **A.** In a custom HTTP request header like X-Auth-Token which is not logged by default and does not appear in browser history or referrer header values
- **B.** In the request body as a JSON field which keeps the token out of the URL but requires all API requests to use POST method instead of GET for data retrieval
- **C.** In a URL fragment after the hash symbol which is not sent to the server in the HTTP request and therefore does not appear in server-side access log files
- **D.** In an Authorization header or httpOnly cookie — both keep tokens out of URLs, logs, browser history, and referrer headers where they would be exposed  ✅

> **Answer:** D

### Q19. Your application has a CSRF vulnerability. An attacker creates a page that automatically submits a form to your /api/transfer endpoint when a logged-in user visits the attacker's page. What protection prevents this attack?

- **A.** CSRF tokens — include a unique server-generated token in each form that the server validates on submission to confirm the request originated from your site  ✅
- **B.** CORS headers that restrict which domains can make requests to your API which prevents the attacker's domain from submitting forms to your endpoints directly
- **C.** Content-Security-Policy headers that block your pages from being loaded inside iframes on the attacker's website preventing the form from being embedded
- **D.** Rate limiting on the transfer endpoint that restricts the number of requests per user per hour which would slow but not prevent the fraudulent submission

> **Answer:** A

### Q20. Your application uses cookie-based sessions. The session cookie has SameSite set to None with no Secure flag. What two vulnerabilities does this combination create?

- **A.** The cookie expires immediately after the browser is closed because SameSite=None without Secure triggers the browser's default session-only cookie behavior
- **B.** The cookie is blocked entirely by modern browsers because SameSite=None requires the Secure flag and browsers reject cookies with this invalid configuration
- **C.** The cookie sends on cross-site requests enabling CSRF, and transmits over HTTP enabling interception — both attacks are possible simultaneously from this config  ✅
- **D.** The cookie is accessible to JavaScript on third-party sites because SameSite=None removes the same-origin restriction on the browser's cookie access policy

> **Answer:** C

### Q21. Your application allows users to link their account to social login providers (Google, GitHub). When a user unlinks a provider, the OAuth tokens for that provider are not revoked. What risk remains after unlinking?

- **A.** The user's social login profile photo and display name remain cached in your application database and continue displaying until manually cleared by an admin
- **B.** The unreleased OAuth tokens still grant your application access to the user's Google or GitHub data even though the user believes the connection is severed  ✅
- **C.** The social login provider continues sending webhook notifications to your application about the user's activity on their platform consuming server resources
- **D.** Other users who linked the same social provider experience authentication errors because the token pool has an orphaned entry that conflicts with active tokens

> **Answer:** B

### Q22. Your application's password strength meter runs entirely on the client side. It accepts 'password123' as strong because it meets the character count requirement. The server has no password strength validation. What is the problem?

- **A.** The client-side meter should use a more sophisticated algorithm that checks against common password dictionaries in addition to character count and complexity
- **B.** Password strength should be evaluated by a third-party API service that maintains an updated database of compromised passwords from known data breach records
- **C.** The strength meter creates a false sense of security but does not need server-side enforcement since users are responsible for choosing their own secure passwords
- **D.** Server-side password validation is required — client-side checks are bypassed by direct API calls, so the server must reject weak passwords independently  ✅

> **Answer:** D

### Q23. Your application generates session IDs using a sequential counter: session_1, session_2, session_3. An attacker who receives session_5847 knows that session_5846 and session_5848 are likely valid sessions. What should session IDs use?

- **A.** Cryptographically random values with sufficient entropy — at least 128 bits of randomness so session IDs cannot be predicted or enumerated by attackers  ✅
- **B.** UUID version 4 identifiers which appear random but contain embedded timestamp and machine information that could theoretically reveal generation patterns
- **C.** Hashed sequential values using SHA-256 so the counter is hidden behind a one-way hash that prevents attackers from determining the underlying sequence number
- **D.** Encrypted sequential values using AES where the counter is encrypted with a server key making the output unpredictable without access to the decryption key

> **Answer:** A

### Q24. Your application has a feature where admins can impersonate regular users for support purposes. The impersonation does not log which admin is acting as which user. A customer reports unauthorized changes to their account. You cannot determine who made them. What audit control is missing?

- **A.** Impersonation should require a second admin to approve each session creating a dual-control mechanism that prevents any single admin from acting alone
- **B.** Impersonation sessions should be limited to read-only access so administrators can view the user's experience without the ability to modify any account data
- **C.** Every action during impersonation must log both the admin's identity and the impersonated user so all changes are traceable to the responsible administrator  ✅
- **D.** Impersonation should be removed entirely since allowing administrators to act as other users creates inherent accountability gaps regardless of logging controls

> **Answer:** C

### Q25. Your application sends a password reset email containing the new password in plain text rather than a reset link. The email reads: 'Your new password is TempPass123. Please log in and change it.' What are the security problems?

- **A.** The temporary password is visible in the email but this is acceptable as a convenience feature since the user is instructed to change it immediately after login
- **B.** Plain text passwords in email are stored in email servers, readable by anyone with mailbox access, and may not be changed — use time-limited reset links instead  ✅
- **C.** The generated password TempPass123 is predictable and could be guessed by an attacker but a randomly generated complex password would make this approach secure
- **D.** Email delivery is not guaranteed so the user may never receive the temporary password and would be locked out of their account with no alternative recovery method

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/104378660_
