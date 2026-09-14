---
space: "The Pit"
author: "Matt Murphy"
post_id: 106195379
reactions: 1
comments: 0
published: "2026-08-21T14:00:18Z"
source: "https://the-faction.mn.co/posts/106195379"
---

# You said yes to every client request for 18 months and now your product does not

You said yes to every client request for 18 months and now your product does not ship without breaking something. Today I walk through building a customization cost model before the first line of code, choosing configuration over code forks so the system maintains the customization instead of a human, and setting a productization threshold where custom requests become product features. If you are saying yes to every client request, this is the math you need to run first.

**PROMPT:** Direct your AI: "Build a client customization cost analysis with three components: (1) Customization cost model. For every custom feature currently in my codebase, calculate the fully loaded cost: original development hours, test surface expansion, maintenance burden per release cycle, regression testing overhead, and opportunity cost of delayed roadmap items. Compare the annual maintenance cost of each custom feature against the annual contract value of the client who requested it. Flag every feature where maintenance cost exceeds the client's revenue contribution. (2) Configuration migration audit. Identify every custom feature that is implemented as a code branch, conditional logic block, or separate deployment. For each, determine whether it can be refactored into a configuration-driven feature: a flag, a template, a configurable workflow, or a tenant-scoped setting. Prioritize migration by maintenance cost. Estimate engineering hours to convert each from code to configuration. (3) Productization analysis. Review all custom features across all clients. Identify any feature requested by three or more clients. For each, draft a product specification that generalizes the feature for all tenants. Estimate build cost for the productized version versus the ongoing maintenance cost of maintaining separate custom implementations. Recommend which custom features should be absorbed into the product."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m04s_

You said yes to every single client request for eighteen months straight. Now your product no longer ships without breaking something. Custom dashboards for client number four, special export for client number seven, a workflow that only client number eleven uses. So every yes felt like retention. Every yes actually ended up being tech debt.

And now your entire engineering roadmap is hostage to custom code pass because, well, you cannot ship a product update without regression testing every single one of them first. Right? So saying yes to everything is not customer service. It is a business model that breaks its own product. Here's how I think about customization as an engineering leader.

Number one, a customization cost model before the first line of code is written, not after. Before you build a custom feature, calculate the fully loaded cost, build time, test surface expansion, maintenance burden per release cycle, and the opportunity cost of what your team is not building when they're fixing that. If the annual maintenance exceeds the client's annual contract value, the feature needs to be funded differently or scoped differently. It is what it is. Step two, configuration over code.

Every custom feature that can be expressed as a configuration change instead of a code branch saves you exponentially. A feature that lives in config file is maintained by the system. A feature that lives in a code fork is maintained by a human forever. And step three, productization threshold. When three or more clients request the same customization, it stops being custom.

It becomes a platform feature. So build it once, build it right, and put it in the entire product. The line between custom work and product development is the line between losing money and making money every single time. Your best client should not be your most expensive client. So direct your AI to help you find out if they already are.


---
_Source: https://the-faction.mn.co/posts/106195379_
