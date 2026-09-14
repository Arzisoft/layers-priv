---
course: "The Vault"
module: "Module 6 — HTTPS, Headers & Transport Security"
lesson: "Module 6: HTTPS, Headers & Transport Security — Exam"
type: "course_quiz"
post_id: 104378675
space_id: 24302166
source: "https://the-faction.mn.co/posts/104378675"
updated: "2026-08-27T20:10:51Z"
---

# Module 6: HTTPS, Headers & Transport Security — Exam

> Exam for **Module 6 — HTTPS, Headers & Transport Security** (The Vault) — 25 questions. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI builds a web application that serves content over both HTTP and HTTPS depending on how the user types the URL. What is the risk?

- **A.** The application will display different content on each protocol causing user confusion about which version is current
- **B.** Users who access the HTTP version send all data including login credentials in plain text readable on the network  ✅
- **C.** Search engines will penalize the site for having duplicate content available across two separate protocol versions
- **D.** The hosting platform will flag the dual-protocol setup as a configuration error and restrict traffic flow

> **Answer:** B

### Q2. Your application has a valid SSL certificate but does not redirect HTTP requests to HTTPS. What should you direct your AI to fix?

- **A.** Remove the HTTP listener entirely so the server refuses all unencrypted connections instead of responding to them
- **B.** Add a warning banner on HTTP pages telling users to manually switch to HTTPS for a more secure connection
- **C.** Add a server-level redirect that sends all incoming HTTP requests to HTTPS before any content is delivered  ✅
- **D.** Enable HTTPS by default in the browser settings for users who have visited the site at least one time before

> **Answer:** C

### Q3. Your SSL certificate expired overnight and visitors see a full-page browser warning. What should have prevented this?

- **A.** An auto-renewal process through the certificate provider with monitoring alerts that confirm renewal succeeded  ✅
- **B.** A calendar reminder set for the certificate expiration date so a team member could renew it manually on time
- **C.** A longer certificate validity period so the renewal window was measured in years rather than in months
- **D.** A fallback self-signed certificate that the server switches to automatically when the primary one expires

> **Answer:** A

### Q4. Your AI-built application has no Content-Security-Policy header. An attacker exploits an XSS vulnerability to inject a script. What happens?

- **A.** The browser detects the injected script automatically and blocks it from executing based on built-in protections
- **B.** The web application firewall intercepts the injected script at the network layer before it reaches the browser
- **C.** The injected script fails because modern browsers no longer allow any dynamically added scripts to run on pages
- **D.** The injected script executes with full access to the page because no CSP header restricts what scripts can run  ✅

> **Answer:** D

### Q5. Your AI generates an application with inline JavaScript throughout the HTML. You add a strict CSP header. The site breaks. Why?

- **A.** The CSP header conflicts with the hosting platform configuration and overrides the allowed JavaScript execution rules
- **B.** A strict CSP blocks inline scripts from executing and the application relies entirely on inline code to function  ✅
- **C.** The CSP header is incorrectly formatted because the AI placed conflicting directives that cancel each other out
- **D.** The browser interprets the CSP header as a request to disable all JavaScript including externally loaded scripts

> **Answer:** B

### Q6. You direct your AI to add a Content-Security-Policy header. It includes the directive "script-src unsafe-inline". What is the problem?

- **A.** The unsafe-inline directive allows any inline script to execute which eliminates the core XSS protection CSP provides  ✅
- **B.** The unsafe-inline directive is deprecated in the current CSP specification and will be ignored by modern browsers
- **C.** The directive applies only to the main document frame and does not cover scripts loaded inside any nested iframes
- **D.** The unsafe-inline directive conflicts with other CSP rules and causes the browser to reject the entire CSP header

> **Answer:** A

### Q7. Your application does not send a Strict-Transport-Security header. A user types your URL without the https prefix. What happens?

- **A.** The browser refuses to load the page entirely because all modern browsers require HSTS for every website they visit
- **B.** The browser displays a security interstitial warning the user that the site may not be safe before allowing access
- **C.** The first request travels over HTTP in plain text creating a window where an attacker could intercept the data  ✅
- **D.** The user is redirected to HTTPS automatically by the browser because it caches HTTPS from the certificate

> **Answer:** C

### Q8. You add HSTS to your application today. A brand-new user visits your site for the first time tomorrow over HTTP. Are they protected?

- **A.** Yes, the HSTS header is cached by DNS servers and applied to all users regardless of whether they visited before
- **B.** Yes, browsers automatically check a global HSTS registry for all domains before making the initial connection
- **C.** No, but the browser detects the redirect from HTTP to HTTPS and retroactively encrypts the original request data
- **D.** No, HSTS only protects users after their first visit when the browser receives and stores the HSTS header  ✅

> **Answer:** D

### Q9. Your AI-built application can be loaded inside an iframe on any external website. What attack does this enable?

- **A.** Clickjacking, where an attacker overlays your app in a transparent iframe and tricks users into clicking your controls  ✅
- **B.** Cross-site scripting, where the iframe injects malicious JavaScript directly into your application source code
- **C.** Session fixation, where the iframe forces the user browser to adopt a session token controlled by the attacker
- **D.** DNS rebinding, where the iframe redirects your domain resolution to a server controlled by the attacker instead

> **Answer:** A

### Q10. Your application does not set the X-Content-Type-Options header. A text file uploaded by a user is served without a content type. What could happen?

- **A.** The browser refuses to download the file entirely and shows an error message about the missing content type header
- **B.** The browser may MIME-sniff the file and interpret it as executable JavaScript which then runs in the user session  ✅
- **C.** The text file is delivered but rendered as plain HTML with all formatting stripped and no interactive behavior added
- **D.** The server automatically assigns a default content type of application/json and delivers the file in that format

> **Answer:** B

### Q11. Your HTTPS page loads an image from an HTTP source. Users report the image is missing or a browser warning appears. What is this called?

- **A.** A cross-origin resource violation where the browser blocks all resources not hosted on the same domain as the page
- **B.** A certificate mismatch error where the image server TLS certificate does not match your application domain name
- **C.** Mixed content, where an HTTPS page loads resources over HTTP and the browser blocks or warns about the mismatch  ✅
- **D.** A content-type conflict where the image format does not match the MIME type declared in the response

> **Answer:** C

### Q12. Your application does not send a Referrer-Policy header. A user clicks a link from your site to an external page. What information might leak?

- **A.** The user authentication token from the active session which the external page could use to impersonate the visitor
- **B.** The full response body of your page content which the external site receives as part of the navigation request data
- **C.** The user IP address and device fingerprint data that the browser attaches to every outbound navigation request it sends
- **D.** The full URL of your page including any sensitive path segments or query parameters visible in the referrer header  ✅

> **Answer:** D

### Q13. You scan your AI-built application with SecurityHeaders.com and receive an F grade. What does this most likely indicate?

- **A.** The application is missing most or all recommended security headers leaving browsers with no protection guidance  ✅
- **B.** The application has a critical vulnerability in its backend code that the scanner detected through response analysis
- **C.** The TLS certificate is expired or improperly configured and the scanner cannot establish a secure connection at all
- **D.** The application is running on an outdated web server version that the scanner flagged as having known exploits

> **Answer:** A

### Q14. Your AI configures X-Frame-Options as SAMEORIGIN. Your marketing team wants to embed the app in a partner iframe. What do you do?

- **A.** Remove the X-Frame-Options header entirely so that any external site can embed the application without restrictions
- **B.** Change the value to ALLOWALL which permits framing from any origin while still keeping the header present
- **C.** Switch to CSP frame-ancestors with the specific partner domain listed so only that approved origin can embed it  ✅
- **D.** Ask the partner site to add your domain to their own X-Frame-Options header to create a mutual trust agreement

> **Answer:** C

### Q15. An XSS vulnerability exists in your application. With a properly configured CSP, what is the realistic impact of this vulnerability?

- **A.** The vulnerability is completely neutralized and the attacker cannot execute any malicious action whatsoever
- **B.** The impact is significantly reduced because CSP blocks injected scripts even though the vulnerability still exists in code  ✅
- **C.** The impact is unchanged because CSP only protects against clickjacking attacks and not script injection threats
- **D.** The vulnerability becomes worse because CSP error messages reveal internal application paths to the attacker

> **Answer:** B

### Q16. An attacker on a public WiFi network intercepts the first HTTP request from a user to your application before the HTTPS redirect. What attack is this?

- **A.** A protocol downgrade attack that exploits the unencrypted initial request before the redirect to HTTPS occurs  ✅
- **B.** A certificate spoofing attack where the attacker presents a fraudulent TLS certificate to the user during redirect
- **C.** A session hijacking attack where the attacker steals the encrypted session token from the TLS handshake exchange
- **D.** A DNS poisoning attack where the attacker redirects the domain resolution to a malicious server before connection

> **Answer:** A

### Q17. Your AI sets CSP frame-ancestors to "none" and also sets X-Frame-Options to DENY. Do you need both headers for clickjacking protection?

- **A.** Yes, both are required because CSP only protects modern browsers while X-Frame-Options protects legacy ones too
- **B.** No, X-Frame-Options alone is sufficient because it is the original anti-clickjacking header and has wider support
- **C.** Yes, both are required because each header protects against different types of clickjacking targeting different elements
- **D.** Setting both provides defense in depth since CSP frame-ancestors is the modern standard and X-Frame-Options is legacy  ✅

> **Answer:** D

### Q18. A user connects to your application from a coffee shop WiFi. Your app uses HTTPS with HSTS enabled. What is the user protected from?

- **A.** All malware on the local network because HTTPS and HSTS create a complete security tunnel around the device
- **B.** Eavesdropping on their traffic between the browser and your server because HTTPS encrypts all data in transit  ✅
- **C.** All tracking by the WiFi network operator because HSTS prevents the router from logging any connection metadata
- **D.** Other users on the network accessing their device because HSTS adds mutual authentication between all endpoints

> **Answer:** B

### Q19. Your AI generates inline script tags throughout your HTML. You want a strict CSP that blocks XSS. What is the correct approach?

- **A.** Add unsafe-inline to the CSP to allow your existing inline scripts while still blocking externally injected ones
- **B.** Remove the CSP header entirely until all inline scripts have been refactored since a partial CSP creates conflicts
- **C.** Direct your AI to move all inline scripts into external files and then set a strict CSP that allows only those sources  ✅
- **D.** Set the CSP to report-only mode permanently so violations are logged but inline scripts continue executing freely

> **Answer:** C

### Q20. Your hosting platform provisions a free TLS certificate through Let's Encrypt. Do you still need to verify the configuration?

- **A.** No, Let's Encrypt certificates are validated by the certificate authority and no additional checks are required
- **B.** Only if you use a custom domain because default platform domains come with pre-verified certificate settings
- **C.** No, hosting platforms that integrate Let's Encrypt handle all certificate configuration and renewal automatically
- **D.** Yes, verify the certificate chain is complete, auto-renewal works, and HTTPS redirect is enforced in your config  ✅

> **Answer:** D

### Q21. You run the SSL Labs server test on your application and receive a grade of A. What does this grade confirm?

- **A.** Your TLS configuration and certificate chain are properly set up with no significant protocol vulnerabilities  ✅
- **B.** Your application has all recommended security headers configured and passes both transport and header analysis
- **C.** Your server is fully protected against all known attack types including XSS, clickjacking, and SQL injection
- **D.** Your application code has been reviewed for vulnerabilities and no security issues were found in the scan results

> **Answer:** A

### Q22. Your AI builds an application but adds zero security headers. The site loads fine and all features work. Why should you still add headers?

- **A.** Because search engines rank sites lower when security headers are missing from the server response configuration
- **B.** Because security headers instruct the browser to block attacks like XSS and clickjacking that work without them  ✅
- **C.** Because hosting platforms will eventually refuse to serve applications that do not include the required header set
- **D.** Because browser vendors are planning to block all sites without security headers in upcoming version releases

> **Answer:** B

### Q23. You need to configure multiple security headers for your AI-built application at once. What is the most efficient approach?

- **A.** Add each header individually in separate deployment cycles so you can test the impact of each one independently
- **B.** Use a third-party security proxy service that automatically injects all recommended headers into every response
- **C.** Copy the exact header configuration from a well-known site since their security team has already validated it
- **D.** Direct your AI to add all headers in the response middleware and verify each one with a header scanning tool  ✅

> **Answer:** D

### Q24. A browser marks your application as "Not Secure" in the address bar even though it loads correctly. What is the most likely cause?

- **A.** Your application is missing security headers and the browser uses the label to warn users about the header gap
- **B.** Your domain registration has expired and the browser is alerting users that the site ownership is not verified
- **C.** The page is being served over HTTP without TLS encryption and modern browsers flag all unencrypted sites this way  ✅
- **D.** The application contains known JavaScript vulnerabilities that the browser detected during its security preflight

> **Answer:** C

### Q25. You complete a transport security audit: HTTPS enforced, all headers configured, SSL Labs grade A. How often should you re-audit?

- **A.** Regularly and after any infrastructure change because new deployments can reset or override header configuration  ✅
- **B.** Only when the TLS certificate is close to expiring because that is the only transport setting that changes over time
- **C.** Once per year during a scheduled annual review since transport security settings rarely need modification after setup
- **D.** No re-audit is needed because transport security is a one-time infrastructure configuration that does not degrade

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/104378675_
