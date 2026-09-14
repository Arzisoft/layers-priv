---
space: "Welcome To The Faction"
author: "Matt Murphy"
post_id: 104636277
reactions: 0
comments: 2
published: "2026-07-16T20:30:02Z"
source: "https://the-faction.mn.co/posts/104636277"
---

# 92% of developers use AI daily.

92% of developers use AI daily.

Only 29% trust the output.

48% don't review before committing.

45% contains security vulnerabilities.

The bottleneck is not the AI. It is the trust.

-MM

[#aidirectedengineering](https://the-faction.mn.co/spaces/23776513/search?term=%23aidirectedengineering) [#trustgap](https://the-faction.mn.co/spaces/23776513/search?term=%23trustgap) [#aicode](https://the-faction.mn.co/spaces/23776513/search?term=%23aicode) [#orchestration](https://the-faction.mn.co/spaces/23776513/search?term=%23orchestration) [#production](https://the-faction.mn.co/spaces/23776513/search?term=%23production)

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m19s_

Ninety two percent of developers are now using AI tools daily, even if they're denying it. But only twenty nine percent of them trust the outputs. So let that gap sink in. And forty eight percent do not review AI generated code before committing it to production. Not to mention, forty five percent of that code contains OWASP security vulnerabilities on day one.

So the AI adoption question is clearly settled. Everyone is using AI to build. The trust question is not settled. Almost nobody is governing what it's producing. And trust, trust isn't a technology problem.

It's a governance and orchestration problem. The market is shifting from can the tool produce code? Because it can. To can the human that's producing it govern the output? And that is the exact shift from VibeCoder to AI directed engineer.

The tool writes the code, but the engineer verifies that it works. The engineer confirms it's secure. The engineer decides that it's ready for production. So without that critical human layer of judgment, you're just shipping at the speed of AI without the quality of a coin flip. The bottleneck, it's not the AI.

The bottleneck is the lack of trust. And Faction's AI directed engineering certification cures that bottleneck.


---

## Discussion

**Alan Joyce** · 2026-07-17

> Coffee & Code and start the day the vibe code way. Very interesting stats, I had a group that were outsourcing there work to else where, changes to little things were taking days, for the slightest refactor, is there a best practice way to get the Ai to go over the code it generates and do you ever put one against another to over view the work, is there an easy way to do that anyone can chime in with a form flow on it. I cant trust the AI, Funny story as I was beginning to migrate to a new VPS I was setting things up and all was swimmingly good until it asked me to copy and paste in the terminal via ssh on the vps, I blindly copied and ran and then looked at the site and thought oh shiiiizzzzpoooppps the images were no more :) I asked the agent I said "hey buddy, what ya gone and done with my assets" or words to that effect it then had the audacity to say "I know i've been given clear instructions never to use the -- volume command when rebuilding a docker container however is seems you did this it was inadvertently in the code I gave you to run and you executed it. what can you say to that? balls. I did chuckle and though could of been worse, what lessons is there to be had, how do I prevent this nonsense happening, I need to be clearer with prompts, and ultimately need to not be blindsided by the ai sexy speed and prowess , slow down look , read! and then execute. zero day exploits is in my head as something to be aware of yet not be afraid of any suggestions to keep platforms safe, maybe a topic for another thread?

  ↳ **Matt Murphy** · 2026-07-17

  > Alan, this is exactly why I teach orchestration instead of prompting. One AI should almost never be grading its own homework. 🤣🤣
  > 
  > My workflow is usually multiple specialized reviewers.
  > 
  > I'll have one agent build, another review security, another review architecture, another review performance, and if something is critical, I'll even have a different model challenge the findings. Consensus from cross examination is far more reliable than a single opinion, so says my attorney lol.
  > 
  > Your VPS story is also the perfect lesson: never execute first, understand second. AI is an incredible junior engineer and it can move at light speed, but it will also confidently follow a bad instruction, over and over and over and over and over lol. Anything that touches production infrastructure, customer data, or destructive commands gets a human pause. Read it. Understand it. Then execute. Every time. 👊😎


---
_Source: https://the-faction.mn.co/posts/104636277_
