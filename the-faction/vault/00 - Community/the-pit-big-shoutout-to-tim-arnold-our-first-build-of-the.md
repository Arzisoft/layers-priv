---
space: "The Pit"
author: "Matt Murphy"
post_id: 103818876
reactions: 7
comments: 7
published: "2026-06-26T22:55:11Z"
source: "https://the-faction.mn.co/posts/103818876"
---

# Big shoutout to Tim Arnold, our first Build of the Week winner 🔥

Big shoutout to **Tim Arnold**, our first **Build of the Week winner** 🔥

Tim submitted a full multi-tenant Medicare CRM SaaS with isolated agency data, role-based access, MFA, automation flows, AI client intelligence, Stripe billing, and 441 passing tests before merge.

That’s not a toy app. That’s a real product with real architecture behind it.

Appreciate you bringing this one into the Arena, Tim. We’ve got some Faction merch headed your way in the mail. 👊😎

---

## Discussion

**Travis Wagner** · 2026-06-26

> Congrats Tim, well-deserved!

**Tim Arnold** · 2026-06-27

> THANK YOU!!!

**Mahmoud Baassiri** · 2026-06-27

> Congrats!

**Awie Hoh** · 2026-06-27

> 👏👏👏

**Robert Patch** · 2026-06-28

> This is cool, how has your experience been with Bedrock [Tim Arnold](https://the-faction.mn.co/members/40269725)? I am planning to use it for a project and became worried when I read that anthropic is requiring data sharing for mythos and fable ([https://www.reddit.com/r/aws/comments/1u1yt4k/aws_bedrock_to_require_sharing_data_with/](https://www.reddit.com/r/aws/comments/1u1yt4k/aws_bedrock_to_require_sharing_data_with/))

  ↳ **Matt Murphy** · 2026-06-28

  > I don’t have direct hands-on with bedrock, so I’m intrigued to hear [Tim Arnold](https://the-faction.mn.co/members/40269725)’s answer as well.

  ↳ **Tim Arnold** · 2026-06-29

  > Bedrock experience has been great for me i run claude-sonnet-4-6 through it for our Medicare CRM platform. Real use cases: AI-assisted lead summaries, appointment notes, commission calculations, anything that touches client health data. The whole reason we went Bedrock over direct Anthropic API is the BAA PHI can't touch a vendor that won't sign one, and Bedrock keeps everything inside the AWS boundary.
  > 
  > On the Mythos/Fable data sharing concern that's real, but it only applies to the new frontier-tier models (Fable 5, Mythos 5). Every model we actually use day-to-day Sonnet, Haiku, Opus still zero data retention, still fully inside AWS. And honestly those two models are currently suspended anyway due to a government export control order, so nobody's using them right now regardless.
  > 
  > If you're building anything in a regulated space, just stay on the existing model lineup and you're fine. The concern you read about doesn't touch what most of us are actually building on.


---
_Source: https://the-faction.mn.co/posts/103818876_
