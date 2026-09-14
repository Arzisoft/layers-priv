---
type: transcript
lesson: "You said yes to every client request for 18 months and now your product does not"
course: "The Pit"
author: "Matt Murphy"
post_id: 106195379
published: "2026-08-21T14:00:18Z"
source_url: "https://the-faction.mn.co/posts/106195379"
duration: "2m04s"
words: 321
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — You said yes to every client request for 18 months and now your product does not

> You said yes to every client request for 18 months and now your product does not ship without breaking something. Today I walk through building a customization cost model before the first line of code, choosing configuration over code forks so the system maintains the customization instead of a huma

You said yes to every single client request for eighteen months straight. Now your product no longer ships without breaking something. Custom dashboards for client number four, special export for client number seven, a workflow that only client number eleven uses. So every yes felt like retention. Every yes actually ended up being tech debt.

And now your entire engineering roadmap is hostage to custom code pass because, well, you cannot ship a product update without regression testing every single one of them first. Right? So saying yes to everything is not customer service. It is a business model that breaks its own product. Here's how I think about customization as an engineering leader.

Number one, a customization cost model before the first line of code is written, not after. Before you build a custom feature, calculate the fully loaded cost, build time, test surface expansion, maintenance burden per release cycle, and the opportunity cost of what your team is not building when they're fixing that. If the annual maintenance exceeds the client's annual contract value, the feature needs to be funded differently or scoped differently. It is what it is. Step two, configuration over code.

Every custom feature that can be expressed as a configuration change instead of a code branch saves you exponentially. A feature that lives in config file is maintained by the system. A feature that lives in a code fork is maintained by a human forever. And step three, productization threshold. When three or more clients request the same customization, it stops being custom.

It becomes a platform feature. So build it once, build it right, and put it in the entire product. The line between custom work and product development is the line between losing money and making money every single time. Your best client should not be your most expensive client. So direct your AI to help you find out if they already are.

---
_Source: https://the-faction.mn.co/posts/106195379_
