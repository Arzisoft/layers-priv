---
space: "The Pit"
author: "Matt Murphy"
post_id: 104423426
reactions: 0
comments: 0
published: "2026-07-10T22:48:57Z"
source: "https://the-faction.mn.co/posts/104423426"
---

# The database you started with is not the one you need.

The database you started with is not the one you need.

Staying too long costs hours.

Moving too early costs weeks.

Three questions tell you when.

When the math says go, go decisively.

A slow migration is the most expensive migration.

-MM

[#database](https://the-faction.mn.co/spaces/23777071/search?term=%23database) [#migration](https://the-faction.mn.co/spaces/23777071/search?term=%23migration) [#scaling](https://the-faction.mn.co/spaces/23777071/search?term=%23scaling) [#orchestration](https://the-faction.mn.co/spaces/23777071/search?term=%23orchestration) [#production](https://the-faction.mn.co/spaces/23777071/search?term=%23production)

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m48s_

At some point along the journey, every builder realizes the database they started with is not the database they need. And this conversation is one of the most expensive decisions in the life of a product for my clients, so it's an important discussion to have. The first thing we talk about is the cost of staying too long. Your starter platform was perfect for the first thousand users, but the connection limits are maxed out, the pricing tier has jumped, and the features you need are on a plan that you can't afford. So what do you do?

You start building workarounds. You direct your AI to add a pooler, you optimize your queries, you cache aggressively. But every workaround is technical debt with a monthly payment. The cost of staying too long is not the database bill. It is the hours your AI is spending finding a platform instead of building your product.

And at some point, the workarounds cost more than that migration. But most builders pass that point and keep paying because migrations feel scary. They aren't. The second thing I talk to my clients about is the cost of moving too early. Migration is not a weekend project.

Schema changes, data transfers, connection strings across every service, orm reconfigurations and testing every query against a new engine. Even with your AI handling implementation, the coordination and verification take real time, even if everything goes right. So if you migrate before you have a genuine scale problem, you likely just spent two weeks solving a problem you didn't have yet. The right time to move is not when you are frustrated. It's when the data shows you spend more on the workarounds than the migration would cost.

So the next thing I talk to them about is the decision framework. I ask founders these three questions every time. Number one, can your current platform handle ten times your current load with just optimizations? If yes, stay and optimize without question. Number two, is the feature you need architecturally impossible on your current platform?

If yes, it's time to migrate. No optimization can fix a missing capability. Number three is the cost of workarounds exceeding the cost of migration. This one's easy. Run the numbers.

Hours on workarounds times your rate versus estimated migration costs. The answer is usually stay longer than you think, but most platforms scale further than their free tier ever suggests. But when the math says go, you must go decisively. Direct your AI to plan the migration with you milestones, rollback points and verification checklists. Because a slow migration is actually the most expensive kind of migration and that's not what your clients want.


---
_Source: https://the-faction.mn.co/posts/104423426_
