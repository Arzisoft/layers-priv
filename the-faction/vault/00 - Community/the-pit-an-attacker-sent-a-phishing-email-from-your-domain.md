---
space: "The Pit"
author: "Matt Murphy"
post_id: 107201803
reactions: 3
comments: 4
published: "2026-09-13T19:00:02Z"
source: "https://the-faction.mn.co/posts/107201803"
---

# An attacker sent a phishing email from your domain. SPF, DKIM, DMARC all passed.

An attacker sent a phishing email from your domain. SPF, DKIM, DMARC all passed. Your AI integrated Resend and drops user input into templates without sanitization. An attacker types HTML into a name field. A phishing link delivered from your verified domain. Indistinguishable from your real emails. Direct your AI to sanitize every input before it enters any template. Strip HTML. Escape special characters. Render user content as text, never raw HTML. Data gets displayed. Markup gets executed. Test every template. Send emails with angle brackets and link tags in every field. If they render as clickable links, your template is injectable. Your domain reputation is your business reputation. One injectable template burns both.

**PROMPT:** You are an email security auditor specializing in template injection. Review the following Resend email implementation. Check: (1) Are user-supplied values sanitized before insertion into templates? (2) Is HTML stripping or escaping applied to all dynamic content? (3) Are templates using raw HTML insertion or unescaped variables? Flag as CRITICAL. (4) Do components render user content as text nodes or raw HTML? (5) Is there input validation on fields that appear in emails? (6) Can users control any part of subject, from address, or reply-to? Flag as CRITICAL. (7) Are templates tested with injection payloads? For each finding, provide the exact sanitization implementation.

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m15s_

An attacker just sent a phishing email from your domain. SPF passed, DKIM passed, DMARC passed. It was your own email system, but your AI let them in through a name field. So your AI integrated resend for transactional emails and drops user input into the template. No sanitization.

So an attacker types HTML into a form field and resend delivers it from your verified domain. Well, the attacker did not compromise your email. Your template just invited them right in. So let's get this locked down. Step one, a name field should contain a name, not a login button that links to an attacker's phishing page.

The phishing email that results is indistinguishable from your legitimate ones because your infrastructure sent it to them. It's your domain. It's your sender reputation. It's your SPF record all confirming that it was real. So one form field that accepts markup turns your entire email system into a phishing platform for attackers.

So direct your AI to sanitize every user input before it enters any template at all. Strip the HTML, escape special characters. That's a win. Step two, your template engine allows raw HTML insertion. User content should never use that path.

Data gets displayed, markup gets executed. So a password reset email that renders user input as HTML is an email an attacker can turn into anything they want. So you need to direct your AI to render user content as plain text, never as raw HTML. That's a win. And step three, send an email with angle brackets, link tags, and script tags in every input field.

If any of them render as a clickable link instead of a plain text, your template is fully injectable. This test will take you thirty seconds. And the alternative is finding out when a customer clicks a phishing link that contains a domain that you sent them. So DirectoryAI to test every single template. Your domain reputation is your business reputation, and one injectable template burns both to the ground.

That's not a win. Get it fixed.


---

## Discussion

**Rob Smith** · 2026-09-13

> Matt this prompt just uncovered a few critical flaws in my project. Thanks a million. Both Astra and Fable missed it until this prompt.

  ↳ **Matt Murphy** · 2026-09-14

  > 🔥🔥🔥love it when that happens🔥🔥🔥 the fable and astra bandwagoners wouldn’t believe you lol 🤣

**Jonathon Carr** · 2026-09-14

> welp.. that was wild to see in real time! 😆

  ↳ **Matt Murphy** · 2026-09-14

  > 🤣🤣🤣


---
_Source: https://the-faction.mn.co/posts/107201803_
