---
type: transcript
lesson: "Shoutout to Mohamed for requesting this one. You moved off a managed platform to"
course: "The Pit"
author: "Matt Murphy"
post_id: 106527552
published: "2026-08-27T14:00:02Z"
source_url: "https://the-faction.mn.co/posts/106527552"
duration: "2m16s"
words: 354
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Shoutout to Mohamed for requesting this one. You moved off a managed platform to

> Shoutout to Mohamed for requesting this one. You moved off a managed platform to a VPS for more control. But your managed platform was handling firewall rules, SSH hardening, and patching invisibly. Your VPS handles none of it. Today I walk through SSH key-based auth, firewall lockdown, and automati

You moved to a VPS for more control, and I can't blame you, but you accidentally left the front door wide open when you did it. Your managed platform is handling security invisibly. So firewall rules, SSH hardening, automatic patching, you never thought about any of it because someone else's platform was doing it for you. Now you own that server and every vulnerability that lives on it. So here's what your AI never configured when you set up your VPS.

Number one, SSH hardening. Right now your server is accepting password authentication on a default port. Every bot on the Internet is trying root passwords against port twenty two around the clock. So your server is being attacked right now, you don't even know it. So disable password authentication entirely, switch to key based access only, and change the default SSH port.

Disable root login while you're there. These are four commands that take five minutes and stop ninety nine percent of automated attacks before they start. So direct your AI to harden your SSH configuration before you do anything else on that server. That's a win. Step two, a firewall that blocks everything you did not explicitly allow.

Your managed platform had invisible firewall rules. Your VPS has none. So every port wide open, every service fully reachable, and your database port is exposed to the public Internet. So direct your AI to configure UFW or IP tables to deny all inbound traffic by default and allow only specific ports your application needs like SSH, HTTP, or HTTPS. Nothing else gets through.

And step three, automatic security updates. Your managed platform patched itself. Your VPS does not. So every unpatched vulnerability is a door someone will eventually walk through when you don't know about it. The longer you wait, the more doors that are open.

So direct your AI to configure unattended security updates so critical patches apply automatically without you having to remember to check. More control means more responsibility. No doubt about it. Your managed platform protected you from yourself. Your VPS is not going to.

You gotta handle it.

---
_Source: https://the-faction.mn.co/posts/106527552_
