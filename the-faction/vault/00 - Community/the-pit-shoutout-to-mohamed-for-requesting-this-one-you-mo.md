---
space: "The Pit"
author: "Matt Murphy"
post_id: 106527552
reactions: 4
comments: 1
published: "2026-08-27T14:00:02Z"
source: "https://the-faction.mn.co/posts/106527552"
---

# Shoutout to Mohamed for requesting this one. You moved off a managed platform to

Shoutout to Mohamed for requesting this one. You moved off a managed platform to a VPS for more control. But your managed platform was handling firewall rules, SSH hardening, and patching invisibly. Your VPS handles none of it. Today I walk through SSH key-based auth, firewall lockdown, and automatic security updates. If you just set up a VPS, this is the first thing you do.

**PROMPT:** Direct your AI: "Perform a VPS security hardening audit with three components: (1) SSH hardening. Disable password authentication and switch to key-based access only. Change the default SSH port from 22 to a non-standard port. Disable root login entirely. Create a dedicated sudo user for all administrative access. Show me the exact sshd_config changes needed and the commands to apply them. Generate a new SSH key pair if I do not have one. (2) Firewall configuration. Configure UFW to deny all inbound traffic by default. Allow only the specific ports my application requires: SSH on my custom port, HTTP on 80, HTTPS on 443. Block all other inbound connections. Verify my database port is not exposed to the public internet. Show me the exact UFW commands and confirm the rules with ufw status verbose. (3) Automatic security updates. Configure unattended-upgrades to automatically install critical security patches. Set it to run daily. Configure email notifications for applied updates. Verify the configuration is active and test with a dry run. Show me the configuration files and the commands to enable it."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m16s_

You moved to a VPS for more control, and I can't blame you, but you accidentally left the front door wide open when you did it. Your managed platform is handling security invisibly. So firewall rules, SSH hardening, automatic patching, you never thought about any of it because someone else's platform was doing it for you. Now you own that server and every vulnerability that lives on it. So here's what your AI never configured when you set up your VPS.

Number one, SSH hardening. Right now your server is accepting password authentication on a default port. Every bot on the Internet is trying root passwords against port twenty two around the clock. So your server is being attacked right now, you don't even know it. So disable password authentication entirely, switch to key based access only, and change the default SSH port.

Disable root login while you're there. These are four commands that take five minutes and stop ninety nine percent of automated attacks before they start. So direct your AI to harden your SSH configuration before you do anything else on that server. That's a win. Step two, a firewall that blocks everything you did not explicitly allow.

Your managed platform had invisible firewall rules. Your VPS has none. So every port wide open, every service fully reachable, and your database port is exposed to the public Internet. So direct your AI to configure UFW or IP tables to deny all inbound traffic by default and allow only specific ports your application needs like SSH, HTTP, or HTTPS. Nothing else gets through.

And step three, automatic security updates. Your managed platform patched itself. Your VPS does not. So every unpatched vulnerability is a door someone will eventually walk through when you don't know about it. The longer you wait, the more doors that are open.

So direct your AI to configure unattended security updates so critical patches apply automatically without you having to remember to check. More control means more responsibility. No doubt about it. Your managed platform protected you from yourself. Your VPS is not going to.

You gotta handle it.


---

## Discussion

**Ameen Badri** · 2026-08-28

> thank you .


---
_Source: https://the-faction.mn.co/posts/106527552_
