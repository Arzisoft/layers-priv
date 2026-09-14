---
space: "The Pit"
author: "Nicholas Carmona"
post_id: 104527217
reactions: 2
comments: 17
published: "2026-07-13T21:45:51Z"
source: "https://the-faction.mn.co/posts/104527217"
---

# Hey what’s going on everyone!

Hey what’s going on everyone!

Been wondering this for awhile, what’s everyone’s debugging process look like? I feel like it’s one of the least talked about topics in the space at times and there is probably so many ways to go about it that not one way is best but maybe some of our flows or thought processes can help others!

Currently my debugging process I have looked deeply into making a full SDLC harness so I created some custom skills that has helped me speed up my decision making process on everything I do for AI engineering:

I tend to brain dump everything I can into the session, ex: support issues, my investigation, things I’ve troubleshooted and the user, console errors and I usually run a skill that looks at all logs, AWS, Langfuse, Supabase along side telling it to use gitnexuses (great repo to use to turn your code base into a knowledge base pretty much) and locate me the potential issue. I do use /workflows with Claude code as well in this process to speed up and fan out. Once it’s back I do have it run an RCA once more just for assurance after I’ve reviewed it which has helped tremendously as well

Would love to hear about everyone’s thought process!

---

## Discussion

**Matt Murphy** · 2026-07-13

> I am excited to hear from the community as well, Nicholas!
> 
> Love this topic.
> 
> My process always starts one layer higher than debugging.
> 
> Before I chase code, I ask: **which of the 13 layers is actually failing?** Data? Auth? API? Infrastructure? State? Permissions? Most bugs aren't code bugs, they're architecture bugs.
> 
> Once I isolate the layer, then I use Bertha (Claude), logs, traces, git history, and whatever else helps narrow the root cause. Then I finish with an RCA so the same class of bug doesn't come back.
> 
> Debugging gets a lot faster when you're diagnosing the systems instead of files. 👊😎

  ↳ **Nicholas Carmona** · 2026-07-13

  > Going to test this out actually thank you Matt!
  > 
  > In those edge cases that it’s not in the 13 layers, how do you go about tackling it by chance?

  ↳ **Brian Bowman** · 2026-07-13

  > Do you have a skill for referencing all 13 layers? I’d love to firm up my reference to the layers in working with Claude.

  ↳ **Matt Murphy** · 2026-07-13

  > [Nicholas Carmona](https://the-faction.mn.co/members/40267888) Great question bro.
  > 
  > If I genuinely can't place it in one of the 13 layers, honestly I assume I don't fully understand the problem yet, not that it's outside the framework. I keep tracing the symptom upstream until I find the layer where reality and expectation diverged.
  > 
  > Nine times out of ten, it eventually lands somewhere. The framework isn't there to give answers, it's there to keep me from chasing ghosts.

  ↳ **Nicholas Carmona** · 2026-07-13

  > Love it, thank you as always!

  ↳ **Matt Murphy** · 2026-07-13

  > [Brian Bowman](https://the-faction.mn.co/members/40287351) now that is a great question, honestly I think I have been using my 13-layer best practices with my AI Assistant for nearly two years all day everyday, so it's been trained so much so we never really reference any of it directly anymore it just follows my best practices with everyhting I work on or do, however there has been no shortage of followers out there trying to turn my 13-layers and all my videos into a dfownloadable skill file LOL, not sure if anyone has had any success, but if I was really trying to hack it together for you I may perhaps download all of the study guides for all 39 courses into my assistant and have it organize my thoughts around each of those artifacts.

  ↳ **Nicholas Carmona** · 2026-07-13

  > lol I didn’t wanna recommend it but [Matt Murphy](https://the-faction.mn.co/members/39706849) yeah that’s the first thing I did as well and then just put my specifics to my work inside it
  > 
  > Matt pocock has a repo called skills, inside he actually has a specific Skill on writing good skills, ironic but I noticed a difference in using that skill specifically vs me just having Claude/codex create it just from my conversation

  ↳ **Nicholas Carmona** · 2026-07-13

  > [Brian Bowman](https://the-faction.mn.co/members/40287351)

  ↳ **Matt Murphy** · 2026-07-13

  > [Nicholas Carmona](https://the-faction.mn.co/members/40267888) to be fair it’s the first thing I would’ve done also.
  > 
  > The moment I figured out that the study guides had actions, and prompts, and outcomes, that would lead me directly to building the product, or answering the questions in the exams, then feeding those to my assistant to participate in the build and working through my exams will be the natural work flow to be successful in this program.
  > 
  > I’m hoping that there’s more people using that technique than not, because we’re in an AI directed space. I don’t expect people to get paper and pencil out and start trying to figure this stuff out. No, I expect you to feed your AI, train your AI, work with your AI, and orchestrate your AI, so however you choose to use it use it. That’s a win. 🏆 👊😎

  ↳ **Nicholas Carmona** · 2026-07-13

  > That’s exactly what I did haha, plugged it into my Hermes agent so it sends me daily challenges to help me expand my thought processes on my complex problems within the 13 layers!

**Brian Bowman** · 2026-07-13

> I’m curious about workflow in general. I’m a bit ADHD, so I tend to run an open bug, roadmap, and current build queue report and work from that. It usually means I am trying to prioritize the quickest wins and looking for the most progress I can achieve in one session. I’m doing all of my building at night and on weekends so I feel like I’m going slower than some of you.

  ↳ **Matt Murphy** · 2026-07-13

  > Bro, I chase my ADHD and Asperger's around like a wild man, trust me I get it, so don't compare your pace to anyone else's.
  > 
  > Shipping nights and weekends while juggling a full-time job is the proper builder journey for 80% of the builders out there right now. Your open bug list and build queue are actually a good habit, it keeps the work visible instead of living in your head. I have Bertha, my AI Chief of Staff, track every single detail in every aspect of my life for this exact reason.
  > 
  > Keep stacking small wins. Consistency beats speed every time.👊😎

**Nicholas Carmona** · 2026-07-13

> Alright another question, where would asynchronous processing and workflow orchestration sit in the 13 layers? Asking because in the space we are in I feel as if this is something that almost deserves its own layer but maybe I’m looking at it on a more granular level? [Matt Murphy](https://the-faction.mn.co/members/39706849) would love to hear your thoughts!

  ↳ **Matt Murphy** · 2026-07-14

  > Great question and you caught me right before I was walking out the door.
  > 
  > So I wouldn't make it its own layer. I'd treat orchestration as a cross-cutting concern that spans several layers.
  > 
  > The workflow itself usually lives in the **Business Logic** layer, while the orchestration engine (n8n, Temporal, [Trigger.dev](http://Trigger.dev), LangGraph, etc.) sits in the **Infrastructure/Platform** layer. The agents it coordinates live in the **AI layer**, and the events flow through the **API/Data layers**.
  > 
  > That's exactly why I teach the 13 layers, one workflow almost always touches multiple layers at once. Hope that helps bro. 👊😎

  ↳ **Nicholas Carmona** · 2026-07-14

  > Hell yeah, appreciate you! Have a great night Matt!

**Tim Arnold** · 2026-07-14

> Yo, this is a great thread topic, glad someone finally brought it up.
> 
> Your setup honestly sounds more advanced than most, the gitnexus knowledge base plus fanning out with workflows is a smart way to compress investigation time. Here's roughly how mine goes, on the Gruening SaaS build and the genomic platform:
> 
> I front load context too, but I lean hard on structured logs over raw console output. If a user reports "checkout broke," I search by user ID and get the whole timeline instead of guessing. Severity levels matter a ton here, a payment failure and a broken image are not the same emergency, and if you don't split those out early you end up chasing noise instead of the actual fire.
> 
> Before I even touch code I ask: does this look like a data problem (RLS blocking a query, tenant isolation issue) or a logic problem (bad state, race condition)? That split alone saves a lot of wasted investigation, because multi tenant bugs are almost always permissions or scoping, not the feature logic itself.
> 
> Then I do what you're doing, brain dump everything, console errors, what the user did, what I already ruled out, and let AI chase the stack trace. Where I differ a little is I try to get source maps and structured fields (user, action, timestamp) in place before the bug even happens, so when it does, the RCA has real ingredients instead of minified gibberish to decode.
> 
> And yeah, I always run a second pass RCA after reviewing the first one myself. Same reasoning as the review cycle conversation, AI's first answer is a hypothesis, not a verdict, and a second look with your own eyes in the loop is what turns "probably this" into "confirmed this."
> 
> Curious what you're using gitnexus for specifically, sounds like it's doing double duty as both a debugging tool and a documentation layer.

  ↳ **Nicholas Carmona** · 2026-07-14

  > This is fantastic! Helps seeing that I’m on the same page with others!
  > 
  > Yeah that extra level of granular info you are mentioning makes total sense!
  > 
  > So I’ve leaned heavily to gitnexus because of my experience and my current situation:
  > 
  > Not a traditional developer and got hired to do Generative AI engineering along side normal software development for an AI company, so since I didn’t build the code and this was actually my first time working in a team environment on a code base I never built, it helps tremendously to see what’s touching what and maybe even what should not be getting touched lol
  > 
  > Best decision I did when I first got access to the repo


---
_Source: https://the-faction.mn.co/posts/104527217_
