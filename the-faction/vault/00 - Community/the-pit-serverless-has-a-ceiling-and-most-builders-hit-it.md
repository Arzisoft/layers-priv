---
space: "The Pit"
author: "Matt Murphy"
post_id: 104751211
reactions: 6
comments: 2
published: "2026-07-18T18:00:03Z"
source: "https://the-faction.mn.co/posts/104751211"
---

# Serverless has a ceiling and most builders hit it without knowing it existed. Th

*Serverless has a ceiling and most builders hit it without knowing it existed. This is how to identify which workloads belong on serverless, which need containers, and how to run both.*

**ORCHESTRATION PROMPT: **

*Audit my application for workloads exceeding serverless limits. List every function with execution time over 30 seconds, any WebSocket handler, and any queue worker. For the longest-running workload, create a Dockerfile and container configuration. Set up serverless functions to dispatch work to the container via a message queue, with both reporting to the same monitoring stack.*

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m36s_

Your serverless function times out after sixty seconds, but the job AI built takes three minutes. So your AI built everything on serverless because the platform made it super easy. But here are the three things you're going to direct your AI to evaluate right now to fix it. Step one: Identify what does not fit. Short lived request response stays serverless.

User hits an endpoint, function responds, done and done. But long running processes, queue workers, WebSocket connections, file processing that takes minutes on end, these cannot live on serverless. It will not work. So direct your AI to list every function that runs longer than thirty seconds or holds a persistent connection. Figure that out, that's a win.

Step two, containerize the heavy workload. Direct your AI to move your longest running process into a container. A queue process or a scheduled job runner, a WebSocket server. Serverless dispatches work to the container. The container processes it.

Both report to the same monitoring. And step three, add a lane, not a migration. You're not leaving serverless. You're adding more capacity. Serverless handles the fast work, and it's really good at it.

But containers, they handle the heavy work. So you direct your AI to route by workload type. Knowing when your platform ceiling is forcing an architecture change is an orchestration decision. And this is a classic. It's not a technical one.

You got Yes.


---

## Discussion

**Mike D** · 2026-07-19

> Long time follower on IG, diving in for first time today. Cant thank you enough. I have been working for months to self-learn these concepts, and it's often YOUR videos that gave me the "ah-hahhhh!!!" moment that filled in the gaps.
> 
> Thank you. Seriously, doing God's work, and this is a MAJOR assist to those of us trying to break free, with limited resources. You're putting gas in my engine, I BELIEVE that I CAN do it…just need the helping nudge to connect dots.
> 
> Thank you sir. May God bless you BIG time… for seeing (and building) exactly the kind of learning environment I needed to complete projects I had abandoned ages ago (due to the overwhelming feeling of not seeing the end of "bandaid-coding" to fix problems… Problems that that needed only higher level visualization explained SIMPLY… so I could understand/vibe solutions). You're the MAN!

  ↳ **Matt Murphy** · 2026-07-19

  > Mike, this means more than you probably realize. Thank you for taking the time to write it. God bless you brother!
  > 
  > The “ah-hahhh!” moments are exactly what I’ve been chasing my whole career. I don’t believe most people fail because they can’t learn technology, I think they fail first for being scared to break things and also because nobody ever zooms out and shows them how the pieces fit together. Once you can see the system, the individual tools stop feeling overwhelming.
  > 
  > I also appreciate what you said about abandoned projects. I’ve watched so many talented people quit, not because they lacked ability, but because they were stuck in an endless cycle of patching symptoms instead of understanding architecture. That’s exactly what I’m trying to change.
  > 
  > Keep that belief you mentioned. If you’ve been putting in the work for months already, you don’t need magic bro you need structure, repetition, and a community that will help connect the dots. That’s what we’re building here. It’s lead than a month in, you’re still early to the community, it’s going to be fun.
  > 
  > Really glad you decided to jump in instead of staying on the sidelines. Welcome to The Faction. Now let’s finish some of those projects together. 👊😎


---
_Source: https://the-faction.mn.co/posts/104751211_
