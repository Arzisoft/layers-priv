---
space: "The Pit"
author: "Matt Murphy"
post_id: 106707443
reactions: 0
comments: 0
published: "2026-08-31T19:00:01Z"
source: "https://the-faction.mn.co/posts/106707443"
---

# You added a chat widget to your site and it can read every password your users t

You added a chat widget to your site and it can read every password your users type on every page. That script tag runs with the same privileges as your own code. Full access to every form field, keystroke, cookie, and session token on every page including your login and checkout. Today I walk through auditing every third-party script for what it can actually access, removing external scripts from any page that handles credentials or payment data, and implementing a Content Security Policy that restricts what external scripts can execute. If you have dropped in any analytics, chat, or review widget, this one matters.

**PROMPT:** Direct your AI: "Build a third-party script security audit and restriction system with three components: (1) Script inventory and access audit. Scan every page of my application and list every third-party script that loads: analytics, chat widgets, review platforms, retargeting pixels, A/B testing tools, font loaders, and any other external JavaScript. For each script, document: the source domain, which pages it loads on, what DOM elements it can access, whether it reads form inputs, whether it accesses cookies or local storage, and what data it sends to external servers. Flag any script that loads on pages handling credentials, payment data, or administrative functions. (2) Sensitive page isolation. Identify every page that handles user credentials, payment information, personal data, or administrative access. Implement page-level script loading that prevents any third-party script from executing on these pages. Verify by loading each sensitive page and confirming zero third-party scripts execute in the browser console. (3) Content Security Policy implementation. Build a Content Security Policy header that whitelists only approved external script sources by exact domain. Block all inline scripts except those with a nonce or hash. Set report-uri to log any CSP violations. Deploy in report-only mode first, monitor for 48 hours, then enforce. Verify by attempting to inject an unauthorized script tag and confirming the browser blocks execution."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m17s_

Your AI added a chat widget to your site during your build. Not uncommon. But now it can read every password your users are typing on every single page. So your AI dropped in a script tag, one line, instant customer support widget in the corner of every page. But that script runs with the same privileges as your own code.

It can read every form field, every keystroke, every cookie, every session token. Guess what? On every page, including your login page, your checkout page, your admin panel. So you didn't install a chat widget. Your AI gave a third party full access to your entire application.

Let's get it fixed. Step one, audit every third party script on your site and what it can access. Most teams cannot even list how many external scripts are loaded in their system. Analytics, chat, reviews, retargeting, AB testing. Every one of them has full DOM access by default.

So direct your AI to inventory every third party script, identify what data each can access, and then document which pages each script loads on. That's a win. Step two, remove third party scripts from every sensitive page. Your login page, your checkout page, your account settings page, your admin panel. No analytics tag needs to watch your users type their passwords.

No chat widget needs to load on your payment form. So direct your AI to implement page level script loading. That excludes third party scripts from any page that handles credentials, payment data or administrative functions. And step three, implement a content security policy that restricts what external scripts can do. A CSP tells the browser which domains are allowed to execute scripts on your page.

Any script not on that list gets blocked. So direct your AI to build a content security policy that whitelists only approved script sources and blocks inline script injection from any unauthorized origin. You control your code. Control who else gets to run theirs next to it.


---
_Source: https://the-faction.mn.co/posts/106707443_
