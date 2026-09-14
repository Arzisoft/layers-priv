---
space: "The Pit"
author: "Matt Murphy"
post_id: 104411514
reactions: 0
comments: 4
published: "2026-07-10T16:15:13Z"
source: "https://the-faction.mn.co/posts/104411514"
---

# Your AI loaded scripts from 14 domains.

Your AI loaded scripts from 14 domains.

You approved 3.

Every one runs code in your users' browsers.

Direct your AI to add CSP headers, audit every external resource, and report before enforcing.

Fourteen domains is an attack surface.

Lock it down.

-MM

[#csp](https://business.facebook.com/watch/hashtag/csp?__eep__=6%2F&__cft__[0]=AZays95VOhLP-7LPPK4tVzOLF5FU201j1NKcy8iyA3G3hqJybUcXaBijQm4N603BUQZblwfIrFh5K8TCi7lTKqV3KM85wmaqLpxVc9m0SrFys6DiOB6UdUVmzN93Rt9JC2I7ZaKabCAgLhSnZCuhFCnqGlqhht0cKIfZX5jjtmglyQ&__tn__=*NK-R) [#security](https://business.facebook.com/watch/hashtag/security?__eep__=6%2F&__cft__[0]=AZays95VOhLP-7LPPK4tVzOLF5FU201j1NKcy8iyA3G3hqJybUcXaBijQm4N603BUQZblwfIrFh5K8TCi7lTKqV3KM85wmaqLpxVc9m0SrFys6DiOB6UdUVmzN93Rt9JC2I7ZaKabCAgLhSnZCuhFCnqGlqhht0cKIfZX5jjtmglyQ&__tn__=*NK-R) [#browsersecurity](https://business.facebook.com/watch/hashtag/browsersecurity?__eep__=6%2F&__cft__[0]=AZays95VOhLP-7LPPK4tVzOLF5FU201j1NKcy8iyA3G3hqJybUcXaBijQm4N603BUQZblwfIrFh5K8TCi7lTKqV3KM85wmaqLpxVc9m0SrFys6DiOB6UdUVmzN93Rt9JC2I7ZaKabCAgLhSnZCuhFCnqGlqhht0cKIfZX5jjtmglyQ&__tn__=*NK-R) [#orchestration](https://business.facebook.com/watch/hashtag/orchestration?__eep__=6%2F&__cft__[0]=AZays95VOhLP-7LPPK4tVzOLF5FU201j1NKcy8iyA3G3hqJybUcXaBijQm4N603BUQZblwfIrFh5K8TCi7lTKqV3KM85wmaqLpxVc9m0SrFys6DiOB6UdUVmzN93Rt9JC2I7ZaKabCAgLhSnZCuhFCnqGlqhht0cKIfZX5jjtmglyQ&__tn__=*NK-R) [#production](https://the-faction.mn.co/spaces/23777071/search?term=%23production)

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m34s_

Your app is loading scripts from fourteen different domains. And you only approved three of them. Your AI pulled in analytics, font libraries, third party widgets, and tracking pixels. Every one of them runs code in your users browsers. So here are the three things you're going to direct your AI to do right now to lock it down.

Step one, content security policy headers. Direct your AI to add CSP headers that whitelist exactly which domains can load scripts in your application. If a domain is not on the list, the browser blocks it. One malicious script on one compromised CDN can hijack every session on your site. CSP stops it before it executes.

And that's the win. Step two, audit what your AI installed. Direct your AI to list every external resource your application is loading. Scripts, style sheets, fonts, images, iframes. If you cannot explain why each one is there, it shouldn't be there.

Your AI added it for convenience. You need to verify it did not add risk. Step three, report before you enforce. CSP has a report only mode. Direct your AI to enable reporting first.

Collect violations for a week. See what breaks before you block it. Then you enforce. Fourteen domains is not a feature. It's an attack surface your AI built without asking you about it.

So now it's time to lock it down.


---

## Discussion

**Bashar Nammari** · 2026-07-17

> Hello [Matt Murphy](https://the-faction.mn.co/members/39706849),
> Thank you for this amazing community and videos. You are a huge help during my development process, and I always check your videos for issues I could've missed or solutions.
> Thank you, sir.

  ↳ **Matt Murphy** · 2026-07-17

  > Thank you, [Bashar](https://the-faction.mn.co/members/40611822)! we’re honored to have you here and I appreciate your feedback now get into the foundation and start building something exciting! 💪😎

**Matthew Denecke** · 2026-07-17

> add CSP headers, audit every external resource, and report before enforcing
> 
> My AI -
> You already have CSP headers on the API side (default-src 'none'; frame-ancestors 'none' on all /api/ responses). The landing page also has a CSP meta tag. ok nice! Thats a win

  ↳ **Matt Murphy** · 2026-07-17

  > That definitely is a win! 👊😎


---
_Source: https://the-faction.mn.co/posts/104411514_
