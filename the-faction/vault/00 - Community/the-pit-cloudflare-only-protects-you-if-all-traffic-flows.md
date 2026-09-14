---
space: "The Pit"
author: "Matt Murphy"
post_id: 105993297
reactions: 1
comments: 0
published: "2026-08-16T14:00:00Z"
source: "https://the-faction.mn.co/posts/105993297"
---

# Cloudflare only protects you if all traffic flows through it. If your origin ser

Cloudflare only protects you if all traffic flows through it. If your origin server IP is discoverable, attackers skip everything. Today I walk through finding leaked origin IPs, locking your firewall to Cloudflare ranges, and fixing Flexible SSL to Full Strict. A locked front door with an open garage is not security.

**PROMPT:** Direct your AI: "Cloudflare configuration audit: origin IP exposure scan across DNS/email/subdomains, origin firewall lockdown to Cloudflare IP ranges only, and SSL configuration verification for Full Strict with origin certificate."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m17s_

You put Cloudflare in front of your app, but an attacker found your server's real IP and went right around it. All your WAF rules, all your DDoS protection, your bot filtering, your rate limiting, all of it bypassed completely. Because your origin server's IP address is discoverable and your attacker just hit it directly. Cloudflare only protects you if all traffic is flowing through it. The moment someone finds your real IP, they skip everything that you set up.

Here's what your AI missed when it configured your Cloudflare. Step one, your origin IP is leaking. DNS history tools store every IP your domain has ever pointed to. If you added Cloudflare after your site was already live, your pre Cloudflare IP is a public record. Your email headers are exposing it, misconfigured subdomains will point straight to it.

So direct your AI to check every sub domain, every MX record, every outbound email header, and every DNS history service for your origin IP. If it's discoverable anywhere, your Cloudflare setup is a locked front door with a wide open garage door. That's not a win. Step two, your origin server still accepts connections from the entire Internet. It should only accept connections from Cloudflare's IP range.

So direct your AI to configure your firewall to whitelist Cloudflare's published IP ranges and block everything else. If a request does not come through Cloudflare, it does not reach your server. Period. And number three, your SSL is probably set to flexible. That means traffic between your user and Cloudflare is encrypted but traffic between Cloudflare and your server is not encrypted.

So an attacker on the network between Cloudflare and your origin sees everything in plain text. So direct your AI to set SSL to full strict mode and install a Cloudflare origin certificate on your server. Encrypted end to end, no gaps. Cloudflare is not a switch that you flip. It is an architecture that you must configure.

So direct your AI to configure it correctly before somebody walks right around it.


---
_Source: https://the-faction.mn.co/posts/105993297_
