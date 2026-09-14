---
space: "The Pit"
author: "Matt Murphy"
post_id: 105993219
reactions: 4
comments: 2
published: "2026-08-15T14:00:04Z"
source: "https://the-faction.mn.co/posts/105993219"
---

# Your RBAC is static. Your threats are dynamic. An attacker with stolen credentia

Your RBAC is static. Your threats are dynamic. An attacker with stolen credentials looks exactly like your real user because your roles never evaluate context. Today I walk through attribute-based access control, zero-trust enforcement on every internal request, and continuous session risk scoring. Tier 3 security.

**PROMPT:** Direct your AI: "Build a Tier 3 access control system: attribute-based policy engine evaluating time/location/device/IP on every request, zero-trust enforcement on all internal requests, and continuous session risk scoring with anomaly detection."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m06s_

A hacker logged into your app at three AM from another country. Your app said, welcome back. Stolen credentials, foreign IP, middle of the night. So your app cannot tell the difference between your real user and the person who has stolen their password. It's the same role, same permissions, same access to everything.

Because your AI built static roles that never evaluate context in the moment. So here's what tier three RBAC actually looks like for your app. Step one, attribute based access control. Permissions that evaluate context, not just the role. What time of day it is, what location, where the device fingerprint is, what's the IP reputation, what's the data sensitivity level.

So DirectoryAI to build a policy engine that evaluates these attributes on every single request. A user accessing financial records at three AM from an unrecognized device gets stepped up authentication or denied entirely. Same role, different context, different decision. That's definitely a win. Step two, zero trust enforcement on every internal request.

Not just the login gate, every API call, every database query, so every service to service request that reverifies identity and authorization. Your AI trusts everything inside the network perimeter. Perimeter. Zero trust assumes there is no perimeter. Every request who proves it is or gets rejected.

And step three, continuous session risk scoring. Not a one time check at login, a running evaluation that monitors behavior throughout their session. If a user's behavior pattern shifts mid session, the system challenges or terminates automatically. So direct your AI to build session anomaly detection that watches for impossible travel, unusual data access volume, or privilege escalation attempts in real time. Static roles tell you who someone else is.

Contacts tells you whether to trust them right now or not. So direct your eye to build for both.


---

## Discussion

**Clare Martinez** · 2026-08-18

> 👍 This is so interesting. I am new and alot of what you're saying convinces me that VibeCoding without this knowledge is risky business.

  ↳ **Matt Murphy** · 2026-08-18

  > That is indeed factual🤣 and welcome to the Faction we’re happy to have you here. 👊😎


---
_Source: https://the-faction.mn.co/posts/105993219_
