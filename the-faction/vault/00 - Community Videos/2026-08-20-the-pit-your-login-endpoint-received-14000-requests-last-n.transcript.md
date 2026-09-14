---
type: transcript
lesson: "Your login endpoint received 14,000 requests last night and none of them were yo"
course: "The Pit"
author: "Matt Murphy"
post_id: 106195191
published: "2026-08-20T19:00:02Z"
source_url: "https://the-faction.mn.co/posts/106195191"
duration: "2m04s"
words: 296
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your login endpoint received 14,000 requests last night and none of them were yo

> Your login endpoint received 14,000 requests last night and none of them were your users. Today I walk through rate limiting rules on authentication endpoints that block at the edge before requests reach your server, bot management rules that protect high-value pages from automated scraping, and cus

Your login endpoint received fourteen thousand requests last night, and none of them were your users. Credential stuffing bots hitting your login, two hundred requests per minute. Scrapers on your pricing page every three seconds, and automated scanners probing every route for potential vulnerabilities. All of it sailing right through Cloudflare, hitting your origin, consuming your compute and spiking your bill. You have a security layer in front of your application and it's doing nothing because your AI never configured it correctly.

Happens to the best of us. Step one. Rate limiting rules on authentication endpoints. Your login, registration and password reset endpoints should never accept more than a defined number of requests per IP per minute. Not at your application level, at the edge, before the request ever reaches your server.

So direct your AI to configure Cloudflare rate limiting rules that block or challenge any IP exceeding thresholds on authentication routes. That is definitely a win. Step two, bot management rules on high value pages. Your pricing page, your checkout flow, your API documentation. Bots hit these pages thousands of times every day.

Cloudflare can identify automated traffic by behavior, finger print, and challenge or block it before it touches your origin. So direct your AI to configure bot management rules that protect high value routes from automated scraping and reconnaissance. And number three, custom WAF rules known attack patterns. SQL injection attempts and query strings, XSS payloads and form fields, path traversal in URLs. Cloudflare's WAF can catch these at the edge and drop the request before your application ever sees it.

So direct your AI to deploy custom WAF rules that block the oWASP top ten attack patterns at the Cloudflare edge. You're paying for a wall. Configure it as a wall.

---
_Source: https://the-faction.mn.co/posts/106195191_
