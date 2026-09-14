---
type: transcript
lesson: "An attacker sent a phishing email from your domain. SPF, DKIM, DMARC all passed."
course: "The Pit"
author: "Matt Murphy"
post_id: 107201803
published: "2026-09-13T19:00:02Z"
source_url: "https://the-faction.mn.co/posts/107201803"
duration: "2m15s"
words: 345
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — An attacker sent a phishing email from your domain. SPF, DKIM, DMARC all passed.

> An attacker sent a phishing email from your domain. SPF, DKIM, DMARC all passed. Your AI integrated Resend and drops user input into templates without sanitization. An attacker types HTML into a name field. A phishing link delivered from your verified domain. Indistinguishable from your real emails.

An attacker just sent a phishing email from your domain. SPF passed, DKIM passed, DMARC passed. It was your own email system, but your AI let them in through a name field. So your AI integrated resend for transactional emails and drops user input into the template. No sanitization.

So an attacker types HTML into a form field and resend delivers it from your verified domain. Well, the attacker did not compromise your email. Your template just invited them right in. So let's get this locked down. Step one, a name field should contain a name, not a login button that links to an attacker's phishing page.

The phishing email that results is indistinguishable from your legitimate ones because your infrastructure sent it to them. It's your domain. It's your sender reputation. It's your SPF record all confirming that it was real. So one form field that accepts markup turns your entire email system into a phishing platform for attackers.

So direct your AI to sanitize every user input before it enters any template at all. Strip the HTML, escape special characters. That's a win. Step two, your template engine allows raw HTML insertion. User content should never use that path.

Data gets displayed, markup gets executed. So a password reset email that renders user input as HTML is an email an attacker can turn into anything they want. So you need to direct your AI to render user content as plain text, never as raw HTML. That's a win. And step three, send an email with angle brackets, link tags, and script tags in every input field.

If any of them render as a clickable link instead of a plain text, your template is fully injectable. This test will take you thirty seconds. And the alternative is finding out when a customer clicks a phishing link that contains a domain that you sent them. So DirectoryAI to test every single template. Your domain reputation is your business reputation, and one injectable template burns both to the ground.

That's not a win. Get it fixed.

---
_Source: https://the-faction.mn.co/posts/107201803_
