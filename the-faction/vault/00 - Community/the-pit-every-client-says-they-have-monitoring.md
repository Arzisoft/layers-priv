---
space: "The Pit"
author: "Matt Murphy"
post_id: 104058103
reactions: 1
comments: 0
published: "2026-07-02T14:16:10Z"
source: "https://the-faction.mn.co/posts/104058103"
---

# Every client says they have monitoring.

Every client says they have monitoring.

Three questions later the room goes quiet.

External health checks. Correlated traces. SLOs that define good before something breaks.

Monitoring is not a dashboard. It is a system that calls you.

-MM

[#observability](https://the-faction.mn.co/spaces/23777071/search?term=%23observability) [#monitoring](https://the-faction.mn.co/spaces/23777071/search?term=%23monitoring) [#opentelemetry](https://the-faction.mn.co/spaces/23777071/search?term=%23opentelemetry) [#slo](https://the-faction.mn.co/spaces/23777071/search?term=%23slo) [#production](https://the-faction.mn.co/spaces/23777071/search?term=%23production)

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m35s_

Every single client tells me they have monitoring up and running. Then I ask these three questions in a room full of people, and it usually gets quiet. Question number one. If your app goes down right now while we're in this meeting, how would you find out about it? If the answer is from a customer email or someone running by the window waving their arms, I'm sorry, but you have alert theater not monitoring.

Real monitoring has external health checks from multiple regions. Not your server asking itself if it feels okay because your server will report healthy while your users in Singapore cannot reach it. And I know somebody's gonna make a Singapore joke. Outside end monitoring is the only monitoring that counts. Question two.

When something fails, can you trace the full request in under sixty seconds? This is where most teams collapse. They have the logs, they have the metrics, and they have the dashboards, right? But none of them are connected. The three pillars of observability are logs, metrics, and traces.

And they only work when they are correlated. That means a log tells you what happened, a metric tells you how often, and a trace tells you where. So without all three connected by a request ID, a unique request ID, you're investigating with one eye closed. OpenTelemetry standardizes this and it's not a product, it's a protocol. It gives you vendor agnostic instrumentation that connects your logs, your metrics, and your traces across all your services.

That's a win. Question number three, do you have SLOs? Service level objectives define what good before something breaks looks like. Ninety nine percent uptime sounds impressive until you calculate it. That's actually three days and fifteen hours of downtime per year.

Ninety nine point nine is eight hours and forty five minutes. And what about ninety nine point nine nine? That's still fifty two minutes. SLOs turn vague expectations into measurable commitments. When your error budget is burning, you slow down the releases.

When it's healthy, you ship as fast as you can. The companies that survive at scale are not the ones with the best code. They aren't. They are the ones that know their systems are breaking before their customers do. And that is the win.

Monitoring is not a dashboard you built. It's a system that calls you. So go build that system.


---
_Source: https://the-faction.mn.co/posts/104058103_
