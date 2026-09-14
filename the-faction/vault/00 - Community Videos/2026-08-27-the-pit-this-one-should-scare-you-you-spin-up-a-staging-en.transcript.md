---
type: transcript
lesson: "This one should scare you. You spin up a staging environment or a landing page t"
course: "The Pit"
author: "Matt Murphy"
post_id: 106527657
published: "2026-08-27T19:00:01Z"
source_url: "https://the-faction.mn.co/posts/106527657"
duration: "2m26s"
words: 394
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — This one should scare you. You spin up a staging environment or a landing page t

> This one should scare you. You spin up a staging environment or a landing page test on a third-party platform. Project ends. You delete the app. But the DNS record still points to that platform. An attacker claims that same slot and now they are serving whatever they want on your subdomain. Your use

You deleted that app six months ago, but the DNS record still sitting there. An attacker is serving your content on your domain right now. So let's say you spun up a staging environment, call it a landing page test, a demo for a client, a project that ended, and then you deleted it, right? Well the DNS record still points to the platform where that app used to live. So an attacker can claim that same slot on the platform and now they are serving whatever they want on your subdomain.

Whether that's phishing pages under your brand, whether that's malware downloads from your domain, your users are seeing your URL in the address bar and they trust it. So this is how we're gonna fix it. Step one. Every dead DNS record is a live attack surface. So you launch services on third party platforms and left the DNS records behind when you shut them down.

Happens. Each one of those records though is a claim ticket that anyone can pick it up. So direct your AI to scan every DNS record on your domain, identify every record pointing to a third party platform, And then flag any record where the destination no longer exists. That's a win. Step two, a compromised subdomain is not an isolated problem.

It inherits the trust of your entire domain. So cookies set on your main domain are readable from the subdomain. Authentication flows can be redirected right through it. So an attacker sitting on staging dot your company dot com is not some random phishing site. They are inside your trust perimeter with your brand on their front door.

So direct your AI to audit your cookie scope and authentication redirects to make sure that no session data is accessible from sub domains you do not actively control. And step three, cleanup takes five minutes. The breach it prevents, not so much. So if the resource is gone, the record is gone. Not parked, not saved for later, completely deleted.

So direct your AI to remove every orphaned record and set up a monthly scan that alerts you the moment a new dangling record appears. Orphan DNS records are not technical debt. They are live weapons pointed at your users. So make sure you audit your subdomains today and delete what you do not control.

---
_Source: https://the-faction.mn.co/posts/106527657_
