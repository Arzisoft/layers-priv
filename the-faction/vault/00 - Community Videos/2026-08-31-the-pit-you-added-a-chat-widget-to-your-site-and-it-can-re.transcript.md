---
type: transcript
lesson: "You added a chat widget to your site and it can read every password your users t"
course: "The Pit"
author: "Matt Murphy"
post_id: 106707443
published: "2026-08-31T19:00:01Z"
source_url: "https://the-faction.mn.co/posts/106707443"
duration: "2m17s"
words: 332
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — You added a chat widget to your site and it can read every password your users t

> You added a chat widget to your site and it can read every password your users type on every page. That script tag runs with the same privileges as your own code. Full access to every form field, keystroke, cookie, and session token on every page including your login and checkout. Today I walk throu

Your AI added a chat widget to your site during your build. Not uncommon. But now it can read every password your users are typing on every single page. So your AI dropped in a script tag, one line, instant customer support widget in the corner of every page. But that script runs with the same privileges as your own code.

It can read every form field, every keystroke, every cookie, every session token. Guess what? On every page, including your login page, your checkout page, your admin panel. So you didn't install a chat widget. Your AI gave a third party full access to your entire application.

Let's get it fixed. Step one, audit every third party script on your site and what it can access. Most teams cannot even list how many external scripts are loaded in their system. Analytics, chat, reviews, retargeting, AB testing. Every one of them has full DOM access by default.

So direct your AI to inventory every third party script, identify what data each can access, and then document which pages each script loads on. That's a win. Step two, remove third party scripts from every sensitive page. Your login page, your checkout page, your account settings page, your admin panel. No analytics tag needs to watch your users type their passwords.

No chat widget needs to load on your payment form. So direct your AI to implement page level script loading. That excludes third party scripts from any page that handles credentials, payment data or administrative functions. And step three, implement a content security policy that restricts what external scripts can do. A CSP tells the browser which domains are allowed to execute scripts on your page.

Any script not on that list gets blocked. So direct your AI to build a content security policy that whitelists only approved script sources and blocks inline script injection from any unauthorized origin. You control your code. Control who else gets to run theirs next to it.

---
_Source: https://the-faction.mn.co/posts/106707443_
