---
type: transcript
lesson: "Your AI deployed your app directly to the internet with nothing between the user"
course: "The Pit"
author: "Matt Murphy"
post_id: 105418654
published: "2026-08-02T19:59:46Z"
source_url: "https://the-faction.mn.co/posts/105418654"
duration: "2m11s"
words: 345
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your AI deployed your app directly to the internet with nothing between the user

> Your AI deployed your app directly to the internet with nothing between the user and your infrastructure. That is a store with no front door and no security camera. Today I walk through web application firewalls, adaptive rate limiting that detects attack patterns, and DDoS response plans you build 

Do you know that one kid with a laptop can take your entire product offline right now? Not a nation state hacker and not a sophisticated criminal organization, but a teenager who watched a YouTube tutorial and wrote a loop that sends ten thousand requests per second to your API. Your app goes down, every customer is dark, every page, every transaction gone. Because your AI never built a proper firewall. So here's what you direct your AI to set up before someone decides to test you.

Step one: a web application firewall that sits in front of your entire stack. Not rate limiting on individual endpoints, but a WAF that filters malicious traffic patterns before they ever reach your server. Your AI deployed your app directly to the internet with nothing between the user and your infrastructure. And unfortunately, that's the equivalent of opening a store with no front door and no security camera. You don't want that.

So direct your AI to configure a WAF through your hosting provider or a service like Cloudflare. Takes an afternoon, you'll nail it. Without it, your uptime depends entirely whether anyone has decided to hack you today. Step two, adaptive rate limiting that recognizes attack patterns. Basic rate limiting caps requests per user per minute.

Sure, not bad. But adaptive limiting detects when request volume, frequency, and origin patterns shift to attack behavior. And then it throttles it automatically. So direct your AI to implement IP based anomaly detection that escalates from throttle to temporary band based on behavior, not just volume. That's a win.

Step three, a DDoS response plan documented before the attack starts. When your app goes down under a flood of traffic, you need a predefined playbook. Who gets notified? What gets toggled? Where traffic gets redirected?

So direct your AI to build a plan right now. Not during the outage when you are panicking and your customers are leaving because the front door is wide open. You need to direct your AI to put a wall in front of it today.

---
_Source: https://the-faction.mn.co/posts/105418654_
