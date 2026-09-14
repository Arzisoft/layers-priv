---
space: "The Pit"
author: "Matt Murphy"
post_id: 106195191
reactions: 1
comments: 0
published: "2026-08-20T19:00:02Z"
source: "https://the-faction.mn.co/posts/106195191"
---

# Your login endpoint received 14,000 requests last night and none of them were yo

Your login endpoint received 14,000 requests last night and none of them were your users. Today I walk through rate limiting rules on authentication endpoints that block at the edge before requests reach your server, bot management rules that protect high-value pages from automated scraping, and custom WAF rules that catch OWASP top 10 attacks before your application sees them. If you have Cloudflare and have not written any rules, this is where you start.

**PROMPT:** Direct your AI: "Build a Cloudflare edge security configuration with three components: (1) Rate limiting rules. Configure rate limiting on all authentication endpoints: login, registration, password reset, and API token refresh. Set thresholds per IP address: maximum 10 requests per minute on login, 5 per minute on registration, 3 per minute on password reset. Action: block for 10 minutes after threshold exceeded. Deploy as Cloudflare rate limiting rules, not application-level middleware. Verify by simulating rapid requests and confirming the block activates at the correct threshold. (2) Bot management. Identify high-value routes: pricing page, checkout flow, API documentation, and any public-facing data endpoints. Configure Cloudflare bot management to challenge or block automated traffic on these routes based on bot score. Set rules to allow verified bots (search engines) while blocking unverified automated traffic. Review bot analytics after 48 hours to tune thresholds. (3) Custom WAF rules. Deploy Cloudflare WAF rules targeting the OWASP top 10: SQL injection in query parameters and form bodies, XSS payloads in input fields, path traversal attempts in URLs, and command injection patterns. Set action to block with logging. Review the WAF event log for false positives after 72 hours and add bypass rules for legitimate application behavior that triggers false matches."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m04s_

Your login endpoint received fourteen thousand requests last night, and none of them were your users. Credential stuffing bots hitting your login, two hundred requests per minute. Scrapers on your pricing page every three seconds, and automated scanners probing every route for potential vulnerabilities. All of it sailing right through Cloudflare, hitting your origin, consuming your compute and spiking your bill. You have a security layer in front of your application and it's doing nothing because your AI never configured it correctly.

Happens to the best of us. Step one. Rate limiting rules on authentication endpoints. Your login, registration and password reset endpoints should never accept more than a defined number of requests per IP per minute. Not at your application level, at the edge, before the request ever reaches your server.

So direct your AI to configure Cloudflare rate limiting rules that block or challenge any IP exceeding thresholds on authentication routes. That is definitely a win. Step two, bot management rules on high value pages. Your pricing page, your checkout flow, your API documentation. Bots hit these pages thousands of times every day.

Cloudflare can identify automated traffic by behavior, finger print, and challenge or block it before it touches your origin. So direct your AI to configure bot management rules that protect high value routes from automated scraping and reconnaissance. And number three, custom WAF rules known attack patterns. SQL injection attempts and query strings, XSS payloads and form fields, path traversal in URLs. Cloudflare's WAF can catch these at the edge and drop the request before your application ever sees it.

So direct your AI to deploy custom WAF rules that block the oWASP top ten attack patterns at the Cloudflare edge. You're paying for a wall. Configure it as a wall.


---
_Source: https://the-faction.mn.co/posts/106195191_
