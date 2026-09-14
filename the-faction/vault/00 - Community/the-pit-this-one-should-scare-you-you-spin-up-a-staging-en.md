---
space: "The Pit"
author: "Matt Murphy"
post_id: 106527657
reactions: 1
comments: 0
published: "2026-08-27T19:00:01Z"
source: "https://the-faction.mn.co/posts/106527657"
---

# This one should scare you. You spin up a staging environment or a landing page t

This one should scare you. You spin up a staging environment or a landing page test on a third-party platform. Project ends. You delete the app. But the DNS record still points to that platform. An attacker claims that same slot and now they are serving whatever they want on your subdomain. Your users see your URL in the address bar and trust it completely. Cookies from your main domain are readable. Authentication flows can be redirected. Today I walk through scanning every DNS record for orphaned entries, auditing cookie scope so session data is not accessible from subdomains you do not control, and setting up automated monthly scans so dangling records get caught the moment they appear. If you have ever deleted an app without deleting the DNS record, this is the fix.

**PROMPT:** Direct your AI: "Audit all DNS records for my domain for subdomain takeover risk with three components: (1) Orphaned record scan. Enumerate every A, AAAA, and CNAME record across all subdomains. For each record pointing to a third-party platform (Heroku, GitHub Pages, AWS S3, Azure, Netlify, Vercel, Fastly, Shopify, and similar), check whether the destination resource still exists or returns a platform default page or unclaimed resource indicator. Flag every record where the underlying resource is no longer active. (2) Trust inheritance audit. For each flagged subdomain, assess the risk: check whether parent domain cookies could be read from that subdomain, whether wildcard DNS entries exist, and whether any authentication or SSO redirect URIs reference the subdomain. Generate a prioritized report listing each vulnerable subdomain, the platform involved, and the risk level. (3) Cleanup and monitoring. Generate a deletion script using my DNS provider's API that removes all orphaned records. Create a recurring monthly scan that reruns this audit automatically and sends an alert when new dangling records are detected. Output everything in a format I can review and execute today."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m26s_

You deleted that app six months ago, but the DNS record still sitting there. An attacker is serving your content on your domain right now. So let's say you spun up a staging environment, call it a landing page test, a demo for a client, a project that ended, and then you deleted it, right? Well the DNS record still points to the platform where that app used to live. So an attacker can claim that same slot on the platform and now they are serving whatever they want on your subdomain.

Whether that's phishing pages under your brand, whether that's malware downloads from your domain, your users are seeing your URL in the address bar and they trust it. So this is how we're gonna fix it. Step one. Every dead DNS record is a live attack surface. So you launch services on third party platforms and left the DNS records behind when you shut them down.

Happens. Each one of those records though is a claim ticket that anyone can pick it up. So direct your AI to scan every DNS record on your domain, identify every record pointing to a third party platform, And then flag any record where the destination no longer exists. That's a win. Step two, a compromised subdomain is not an isolated problem.

It inherits the trust of your entire domain. So cookies set on your main domain are readable from the subdomain. Authentication flows can be redirected right through it. So an attacker sitting on staging dot your company dot com is not some random phishing site. They are inside your trust perimeter with your brand on their front door.

So direct your AI to audit your cookie scope and authentication redirects to make sure that no session data is accessible from sub domains you do not actively control. And step three, cleanup takes five minutes. The breach it prevents, not so much. So if the resource is gone, the record is gone. Not parked, not saved for later, completely deleted.

So direct your AI to remove every orphaned record and set up a monthly scan that alerts you the moment a new dangling record appears. Orphan DNS records are not technical debt. They are live weapons pointed at your users. So make sure you audit your subdomains today and delete what you do not control.


---
_Source: https://the-faction.mn.co/posts/106527657_
