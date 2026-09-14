---
space: "The Pit"
author: "Matt Murphy"
post_id: 104586701
reactions: 3
comments: 8
published: "2026-07-15T18:00:10Z"
source: "https://the-faction.mn.co/posts/104586701"
---

# The follow-up to the 2 AM support script. Your agent handles the known issues. B

*The follow-up to the 2 AM support script. Your agent handles the known issues. But the billing dispute where the customer is right and the system says otherwise, that requires you.*

**ORCHESTRATION PROMPT: **

*Build a support ticket classification system with three categories including automated resolution (known issues the agent handles), assisted triage (unknown issues escalated with context), and human-required (billing disputes, feature requests disguised as bugs, escalated emotional situations). Route tickets automatically. For human-required tickets, include full customer interaction history.*

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m36s_

Just last week, I told you your AI assistant is your first support engineer. And this week, I wanna tell you where the agent stops and you start as the human in the loop. Your AI handles seventy percent of the support automatically from the playbooks you built. The known issues, the documented fixes, password resets, permission syncs, configuration errors. So again, when those playbooks exist, the agent follows them perfectly.

The customer never files a ticket in most cases. That is the way the seventy percent is supposed to work. But the thirty percent that determines whether customers stay or leave is because the human in the loop. So step one, the billing dispute where the customer is right but the system said otherwise. So a customer is charged twice.

Your AI system shows one charge. They have a screenshot of two charges. When your AI assistant reviews it, it sees one charge. It closes the ticket as resolved. The customer is furious because your bot just told them everything's fine.

This is one of those spots that requires a human in the loop that can check the payment dashboard, find the duplicate authorization, issue the customer a refund, and write or tell the customer that they acknowledge the mistake. It's normal human stuff. Right? Step two, the feature request disguised as a bug report. A customer says a filter is broken.

Right? It works exactly the way it was designed, but they expected it to do something else completely. Your AI doesn't see an error in that, so it closes the ticket. The customer feels totally dismissed. Cancels.

This requires a human who reads the intent behind the request and decides whether the product should change to serve other customers with the same request. Step three, the angry email that is not about the bug. A customer sends a furious message about a minor formatting issue, but we all know it's not about formatting. It's about the three other issues they had last month that were never resolved. The formatting issue is just the last straw.

So your AI responds to the formatting issue. Uh-oh. The customer cancels. This requires a human who reads the history and picks up the phone and calls that customer. The thirty percent is not about technical complexity.

It's judgment, empathy mixed with nuanced context that your AI does not have. So you need to build the seventy percent so the time you save for the thirty percent is there because thirty percent is where the trust is earned or lost with every customer. So get it cleared up.


---

## Discussion

**Modest Kissima** · 2026-07-15

> Hey matt if you can enable copy paste it will be wonderful

  ↳ **Matt Murphy** · 2026-07-15

  > It is enabled. Some LLM pasting engines won’t accept it so perhaps try pasting it into an email or your Notes app to see if it pops up. Let me know if it doesn’t.

  ↳ **Modest Kissima** · 2026-07-16

  > What i mean is when i try to copy your prompt there is no such option until i screenshot and ask ai to transcribe

  ↳ **Matt Murphy** · 2026-07-16

  > [Modest Kissima](https://the-faction.mn.co/members/40597981) Hey Modest, I dug into this. The Mighty Networks mobile app doesn’t support text selection on post content. This is a platform limitation on their end, not something I can toggle from our admin settings. Two workarounds: (1) Open the post in your phone’s browser instead of the app. Go to the-faction.mn.co, find the post, and you can select and copy normally. (2) On Android, an app called Universal Copy can force text selection in apps that block it. I’ll flag this to Mighty Networks as a new feature request.

  ↳ **Modest Kissima** · 2026-07-16

  > [Matt Murphy](https://the-faction.mn.co/members/39706849) thanks very much now i am good to go

**Alan Joyce** · 2026-07-15

> oh i've been that customer!! got damn that makes me angry, quick story im still in battle for over a decade for exactly that situation so its good that these things can be addressed and nipped in the bud for customer as it can get messy very messy. Great to oversight to think of these during build I now considering what you is needed to have ai agents doing the bidding on a server, would I spin up say something like open lama and parse it in to Hermes or other openweb to get it to do these things and have it runing on a nice rtx 5090 or the like and que the requests so it dont blow up, jsut thinking it would save so many tokens or at least allow some fun learning.

  ↳ **Matt Murphy** · 2026-07-16

  > Yo big dog! You're thinking about it the right way. But I wouldn't tie the whole system to one LLM like Llama, though. I'd build an orchestration layer that can route requests to whatever model is best for the task based on specific use case and pull, OpenAI, Anthropic, Gemini, local models, etc. That gives you better performance, lower cost, and no vendor lock-in. The LLM should be the hot swappable replaceable worker, not the architecture.

**Alan Joyce** · 2026-07-16

> So from an engineering point of view, you’re really designing the system so it isn’t hard locked into Model A, B or C. Instead, you’re building an abstraction layer that lets you swap models in and out as the landscape changes, whether that’s because something is cheaper, faster, or simply better. That clicked with me today.
> 
> When I’m building, I usually go with whatever is recommended unless it completely hurts my brain or just doesn’t fit the project. The downside is that changing one core component later has often felt like rebuilding half the platform, so hearing you talk about keeping that flexibility from day one genuinely made me stop and think.
> 
> The only reason I mentioned running models locally on GPUs is because I think it’d be fun to experiment. Zero inference cost beyond electricity, and I’d learn a lot about what’s actually happening under the bonnet instead of treating it like a black box.
> 
> That got me thinking about orchestration.
> 
> Am I on the right track thinking about breaking requests into multiple routes? Something like n8n sitting in the middle deciding where each request goes?
> 
> For example:
> 
> “User wants contact details.” Route that to a simple lookup.
> 
> “User wants general support.” Route it to an LLM with a heavily scripted knowledge base and guardrails.
> 
> “User wants a refund.” Route them into a continuous loop until they finally give up… 😄
> 
> Joking aside, I’m starting to realise the routing itself is prompt driven. You’re not just choosing a model, you’re deciding what kind of task you’re dealing with first, then sending it to the most appropriate worker.
> 
> A friend of mine already uses n8n to orchestrate multiple vendors for a fairly niche workflow, so I’m wondering whether I should stop overthinking it, spin up n8n in Docker, plug into its API, and start experimenting.
> 
> Actually… I think I answered my own question while typing this.
> 
> This is literally how my engineering brain works. I start rambling, paste my thoughts into text, and somewhere around paragraph six my brain quietly goes, “Oh… I get it now.”
> 
> Error… error… solution found. 🤣
> 
> Thanks for the insight. It genuinely shifted how I’m thinking about architecting this.


---
_Source: https://the-faction.mn.co/posts/104586701_
