---
type: transcript
lesson: "Your AI loaded scripts from 14 domains."
course: "The Pit"
author: "Matt Murphy"
post_id: 104411514
published: "2026-07-10T16:15:13Z"
source_url: "https://the-faction.mn.co/posts/104411514"
duration: "1m34s"
words: 232
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your AI loaded scripts from 14 domains.

> Your AI loaded scripts from 14 domains.

Your app is loading scripts from fourteen different domains. And you only approved three of them. Your AI pulled in analytics, font libraries, third party widgets, and tracking pixels. Every one of them runs code in your users browsers. So here are the three things you're going to direct your AI to do right now to lock it down.

Step one, content security policy headers. Direct your AI to add CSP headers that whitelist exactly which domains can load scripts in your application. If a domain is not on the list, the browser blocks it. One malicious script on one compromised CDN can hijack every session on your site. CSP stops it before it executes.

And that's the win. Step two, audit what your AI installed. Direct your AI to list every external resource your application is loading. Scripts, style sheets, fonts, images, iframes. If you cannot explain why each one is there, it shouldn't be there.

Your AI added it for convenience. You need to verify it did not add risk. Step three, report before you enforce. CSP has a report only mode. Direct your AI to enable reporting first.

Collect violations for a week. See what breaks before you block it. Then you enforce. Fourteen domains is not a feature. It's an attack surface your AI built without asking you about it.

So now it's time to lock it down.

---
_Source: https://the-faction.mn.co/posts/104411514_
