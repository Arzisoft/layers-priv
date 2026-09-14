---
space: "The Pit"
author: "Matt Murphy"
post_id: 103858068
reactions: 0
comments: 6
published: "2026-06-28T12:51:28Z"
source: "https://the-faction.mn.co/posts/103858068"
---

# The Pit



---

## Video transcript

_deepgram auto-captions (Mighty) · 1m34s_

It's Sunday morning and I was just reflecting on a week ago this community was a total construction site. Space is half built, certifications being wired, many of the tests and the triggers and badges were still being tested. Today, there are real builders in here with real projects, real questions, and are passing real exams. That transition from building the thing to running the thing is something I want to talk about to all of you because it applies to all of us as builders. The hardest moment in any build is not the launch.

It's the morning after the launch. When the adrenaline fades and you realize the product is live, people are using it, and you have to operate it into perpetuity. That shift from builder to operator is usually where most projects fail. It's exactly why layers nine through thirteen exist, right? Monitoring, caching, cost, compliance and documentation.

The important stuff. Those are not build layers, those are the operational layers. You can build an application in a weekend, right? But operating it is a totally different discipline. And this community exists because building is the easy part, sustaining it is where it gets real tough.

So here's my question for the day. What is the one thing about your build right now, right now, that has you really worried about what happens after you launch it? I want to know. Let's talk about it in the comments. Being vulnerable here counts.

I have the same fears you have. I have it about this community. I have it about websites. I have it about client projects. I want to know how you guys feel about it.

What's it like?


---

## Discussion

**Anthony Candelario** · 2026-06-28

> A great question that kind of bites and most people will not want to admit. Right now, while I'm building along with my team and looking at where it is and where its going, shadow AI or rogue AI is definitely something that we are planning against accordingly. We saw that entering an API key per area or feature for your claude, openAI or OpenRouter is not a practical way to go on bigger builds. That's when we stopped building for a second, looked back and saw that not only cost but the complexity of changing a key would be horrible (Imagine changing 10 or 15 keys and then documenting everything, the nightmares). So we decided to build our own AI Gateway for routing, caching and limiting. There are AI Gateway's out there for sure like Kong but the sort of data be work with can't be risked in "public" infrastructure so we rather build our own. That's where we currently are, planning the heck out of this project in order for it to thrive.

  ↳ **Matt Murphy** · 2026-06-28

  > Wow, great share. And trust me I speak on stage quite frequently and Shadow AI is a big topic.
  > 
  > [Anthony](https://the-faction.mn.co/members/40269131), this is a very real fear and a very real architecture decision.
  > 
  > Shadow AI / rogue AI is one of those problems people ignore until the build gets big enough that every feature quietly has its own key, its own prompt logic, its own retry behavior, its own logs, and nobody really knows what is happening anymore.
  > 
  > That is how the robot bill turns into a crime scene.Sorry I crack myself up sometimes. 😂😂😂
  > 
  > Building an AI Gateway makes a lot of sense if you’re already seeing the complexity coming. One place for routing, limits, caching, logging, access control, model selection, fallback behavior, and cost visibility.
  > 
  > That’s not overengineering. That’s putting a control plane in front of something that can get very expensive and very messy very fast.
  > 
  > And you nailed the bigger point: it’s not just cost. It’s governance. It’s data boundaries. It’s observability. It’s being able to answer, “who called what, with what data, why, and what happened?”
  > 
  > That’s the 13 layers showing up right there bro.
  > 
  > The build after launch is not just “does the app work?” It’s usually “can we operate this thing without it quietly eating the company from the inside out?” 👊😎

**Wynand Coreejes** · 2026-06-28

> The one think i cannot know, cannot plan for..... security...
> 
> This one keeps me up at night,
> 
> Today secure, tomorrow ai evolve, they also use AI

  ↳ **Matt Murphy** · 2026-06-29

  > Wynand, yep, that's the one that keeps all of us up at night. Trust me.
  > 
  > Security is not a box you check once and move on from. It is a moving target, and now the people trying to break systems have AI too.
  > 
  > That does not mean we panic.
  > 
  > It means we build with evolving layers, assume things will change, and keep tightening the system as we learn more: auth, permissions, data boundaries, logging, backups, rate limits, recovery, monitoring, dependency updates, all of it.
  > 
  > “Secure today” does not mean “secure forever.” Never has, never will. It means you made intentional decisions today, and you have a process to keep hardening tomorrow.
  > 
  > That’s also why we’re going to be adding a lot more security coursework into the new tiers we’re dropping over the next month. This is not optional anymore. If we’re teaching people to build real software, we have to teach them how to protect it too.
  > 
  > You’re not wrong to be worried about it. That concern is part of becoming a real operator. 👊😎

  ↳ **Wynand Coreejes** · 2026-06-30

  > [Matt Murphy](https://the-faction.mn.co/members/39706849) LOVIT!!!! this path is perfect for insomnia, wheter you lie awake worrying about security, or you sit up building more layers to make your work more secure….
  > 
  > Makes the build so much more worth it!!! Your guidance and support makes it worth it!! Thank you
  > 
  > 👊

  ↳ **Matt Murphy** · 2026-06-30

  > I cannot wait to see you get it across the line and end into production!!!👊😎


---
_Source: https://the-faction.mn.co/posts/103858068_
