---
space: "The Mentoring Lounge"
author: "Rob Smith"
post_id: 104581720
reactions: 2
comments: 3
published: "2026-07-14T23:36:17Z"
source: "https://the-faction.mn.co/posts/104581720"
---

# Ways of working. Forgive we if this has been covered elsewhere.

Ways of working. Forgive we if this has been covered elsewhere.
My way of working as changed overtime from simple developing directly in Codex/Claude code but realising I was missing an orchestrator. I moved to using Claude chat for scoping and maintaining build documentation Inc. Handovers, Claude.md touchups, etc and looping briefs into Claude Code, then feeding Code reports back to Chat with a CodeRabbit report. Then a new brief to fix issues, etc. it was a solid loop that kept the code clean (I think) and stopped scope creep. However, I was getting swamped in documentation at the expense of moving the code forward (I had my newly build Mac Mini hosting my Langgraph agent system analysis this workflow and SaaS projects) Now my workflow is: work out of Claude co-work connected directly to the local repo, so no longer needed to be constantly updating Claude project file memory. The orchestration happens in co-work and Code still takes the brief so the repo is where the only Claude.md file lives in all the briefs, handovers, backend spec, velocity docs etc. This has sped up the build dramatically. Fable 5 has also caught a few things in some of the more complex briefs. I have also just added a read only code and doc checker (GPT5.6 Sol chat/codex) to read the GitHub repo to cross check Claude and CodeRabbits work.
I would love to get any feedback on my workflow and hear from others on their ways of working. Thanks.

---

## Discussion

**Matt Murphy** · 2026-07-15

> Rob, this is a solid evolution. You’re in the right place bro.
> 
> I think a lot of people over-document early because AI makes documentation cheap. I know I was guilty of it. The bottleneck isn’t writing docs, because the AI will document a mountain of data, it’s shipping.
> 
> My rule is simple: the repo is the source of truth. Everything else should help move the code forward, not become another project to maintain.
> 
> I also try to keep one orchestrator responsible for the build, that’s my CoWork Bertha on Claude with all input queries, prompts, and outputs automatically logged to a Notion data lake. Low token usage, no memory leakage, and hot swappable compute.
> 
> Once you have multiple AIs reviewing multiple AIs, you can end up managing reviewers instead of building software. I’m running reviewer loops across agents on Claude code, codex, and cursor.
> 
> So it sounds like you’re converging on a workflow that keeps velocity high without losing architectural discipline. That’s where the sweet spot is. Well done. 👊😎

**Rob Smith** · 2026-07-16

> Thanks Matt

**Daniel Siman Tov** · 2026-07-16

> Hey man! you just added a third reviewer (Sol) on top of Claude + CodeRabbit. I did the same thing a few months back and it bit me hard.
> 
> Within a week I wasn't building anymore. I was refereeing. Three reviewers, three opinions, and half of them kept re-flagging stuff I'd already decided was fine. The point above about managing reviewers instead of shipping is the real trap, and a third reviewer is usually where it kicks in.
> 
> What pulled me out wasn't more reviewers, and it wasn't fewer. It was giving them a hard stop condition. Three things did most of the work:
> 
> Tests break ties. If a reviewer flags something a test can settle, I write the test and run it instead of going another round. Running the code beats arguing about it.
> 
> A killed finding stays killed. I keep a dumb little "already looked, it's fine" list and hand it to the reviewers before every pass. That one killed most of the token bleed. It was almost all re-litigation.
> 
> Not everything gets the full panel. A copy change doesn't need three AIs. Auth, money, migrations, the DB, those get the whole loop. The rest gets one cheap pass and moves on.
> 
> The thing that finally clicked for me: "done" can't be a reviewer's gut feeling. It has to be evidence I can actually point to. Tests green, the review actually ran (not just "looks good to me"), and I personally signed off on the scary stuff. Once done was concrete, the loops stopped being infinite.
> 
> Curious though. With Sol reading the repo read-only, how are you stopping it and CodeRabbit from flagging the same thing and bouncing you into a round you didn't need? That overlap is exactly where it got loud for me.
> 
> (Got so tired of rebuilding this per project that I open-sourced the ledger + the tiers as a small gate. Not pitching you, just say the word and I'll drop the link.)


---
_Source: https://the-faction.mn.co/posts/104581720_
