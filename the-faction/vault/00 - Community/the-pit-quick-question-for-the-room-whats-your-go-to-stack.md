---
space: "The Pit"
author: "Matt Murphy"
post_id: 103506384
reactions: 2
comments: 59
published: "2026-06-19T23:53:54Z"
source: "https://the-faction.mn.co/posts/103506384"
---

# Quick question for the room — what's your go-to stack right now? I'm not asking

Quick question for the room — what's your go-to stack right now? I'm not asking what's "best." I'm asking what you're actually using day to day to get stuff out the door. Cursor? Bolt? Lovable? Claude Code? Some Frankenstein combo? No wrong answers. Just curious where everyone's head is at.

---

## Discussion

**Tim Arnold** · 2026-06-22

> Based on everything i've built together:
> 
> **Frontend**
> 
> Next.js 14 (App Router)
> 
> React 18
> 
> Tailwind CSS + shadcn/ui
> 
> **Backend**
> 
> Node.js + Express
> 
> Next.js API routes
> 
> Cloudflare Workers (edge logic)
> 
> **Database**
> 
> Supabase (PostgreSQL + RLS + Auth) — primary
> 
> Neon Postgres — secondary/lightweight
> 
> **Auth**
> 
> Supabase Auth
> 
> JWT
> 
> GHL OAuth v2
> 
> **Deployment**
> 
> Vercel (frontend/API)
> 
> DigitalOcean (heavier backend)
> 
> Cloudflare (DNS, CDN, Transform Rules)
> 
> **Payments**
> 
> Stripe Connect (multi-tenant)
> 
> **Automation**
> 
> [Make.com](http://Make.com)
> 
> GHL Workflows + API v2
> 
> **AI**
> 
> Anthropic API (Claude) — primary
> 
> OpenAI via middleware
> 
> **Validation**
> 
> Zod — every input, always
> 
> **Ads/Tracking**
> 
> Meta CAPI + Meta Pixel

  ↳ **Matt Murphy** · 2026-06-22

  > 🔥Solid stack, Tim. This is a very real-world “get it out the door and keep control” setup. 👊😎
  > 
  > I like the Supabase primary + Neon lightweight split, and Zod everywhere is one of those boring decisions that saves you from exciting problems later.
  > 
  > Also love seeing Cloudflare Workers in there for edge logic. That’s usually where the stack starts growing up from “I built an app” into “I’m operating a system.”
  > 
  > The Meta CAPI / audience sync piece is especially interesting. That’s the kind of workflow where AI + automation + clean data plumbing can create actual business leverage, not just demo magic.💯

  ↳ **Kyle Becker** · 2026-06-23

  > I see you mention meta pixels have you been seeing some of the CIPA lawsuits targeting small businesses. I currently don’t have pixels on any of my pages but just curious on your thoughts.

  ↳ **Tim Arnold** · 2026-06-23

  > [Kyle Becker](https://the-faction.mn.co/members/40271287) From what I've seen, the issue usually isn't the pixel itself it's how tracking is implemented, what data is collected, and whether proper disclosures/consent are in place. Attribution is still important businesses just need to be more privacy conscious about how they do it. Not legal advice, of course lol.

**Kyle Becker** · 2026-06-23

> From my current builds it has all been very similar. Im packaging a leads management system for fitness and health coaches. (A space I’ve been in for years)
> 
> Frontend
> Next.js App Router
> React
> TypeScript
> Custom CSS / operational UI components
> Lucide icons
> Sanity-rendered content on public website
> 
> Backend
> Next.js API routes
> Node.js scripts for migrations, MCP, and operational tooling
> Hosted MCP server for agent access
> Local MCP server for desktop/agent workflows
> 
> Database
> Postgres
> pg Node driver
> SQL migrations
> CRM tables for leads, submissions, timeline events, contact attempts, tasks, email logs, calendar connections, appointments, and MCP identities
> 
> Auth
> Google OAuth
> Signed session cookies
> Admin email allowlists
> Owner-gated Google Calendar reconnect
> Per-user MCP bearer-token identities
> 
> Calendar
> Google Calendar API
> Shared owner calendar connection
> Availability based on `Available...` calendar blocks
> Booking writes to Google Calendar and CRM records
> 
> CMS / Content
> Sanity Studio
> Sanity Content Lake
> Next.js website rendering published Sanity content
> 
> Deployment
> Railway for website, CRM, Postgres, and hosted MCP services
> GitHub as source control
> Custom domains/DNS as needed
> 
> Automation / Agent Layer
> MCP server for CRM operations
> Claude/Cowork/Codex-compatible agent workflows
> Preview/confirm pattern for risky bulk writes
> Per-user MCP token generation and rotation
> 
> Validation / Safety
> Server-side validation
> Raw payload preservation
> Duplicate lead checks
> Consent tracking
> Signed lead access tokens
> Rate limiting and origin controls on hosted MCP
> Secret separation through Railway env vars
> 
> Lead Flow
> Website forms
> Performance diagnostic
> Lead magnets / gated guides
> Multi-step coaching applications
> CRM lead creation
> Submission history
> Timeline events
> Follow-up tasks
> 
> Mail / Communication
> Google Apps Script mail sender or mail handoff flow
> Email log table
> `tel:`, `sms:`, and `mailto:` frontend actions with CRM-side activity logging

  ↳ **Matt Murphy** · 2026-06-23

  > Kyle, ummm…lol..this is much stronger than “lead management system” makes it sound. 👊🤣
  > 
  > You’re really building an operating layer for fitness and health coaches: website capture, CRM, calendar booking, follow-up tasks, lead magnets, applications, activity history, and agent access through MCP.
  > 
  > That’s the right direction because coaches don’t need another generic CRM. They need their money path tightened up:
  > 
  > Lead captured,> qualified,> booked,> followed up with,> converted,> reactivated later.
  > 
  > The parts I like most are the Google Calendar workflow, CRM-side activity logging, consent tracking, duplicate checks, and preview/confirm for risky agent actions. That tells me you’re thinking beyond “AI can do stuff” and into “AI needs rails.”
  > 
  > I’d keep the product simple on the surface and strong underneath. Coaches should feel like it is easy. Operators should see that it is structured.
  > 
  > This is a very real vertical SaaS lane.💯😎

  ↳ **Kyle Becker** · 2026-06-23

  > [Matt Murphy](https://the-faction.mn.co/members/39706849) thank you. I’ve delivered 2 thus far working on my 3rd. Most of these coaches have been using something like Go High Level which honestly I think is great but they were using 3 features out of the whole system and the UI is very complicated. I removed the bloat and offered them what they need.

  ↳ **Matt Murphy** · 2026-06-23

  > [Kyle Becker](https://the-faction.mn.co/members/40271287) simplicity sometimes is the best approach right.

**Travis Wagner** · 2026-06-23

> I build in VS Code with Claude Code running inside a VS Code terminal. Lately I've been using:
> Next JS, Neon, NextAuth, GitHub, Vercel, Sentry

  ↳ **Matt Murphy** · 2026-06-23

  > Solid building tools, you're well on your way. 👊😎

**Bukie Faforiji** · 2026-06-25

> Started in Google AI Studio for early prototyping then moved to Claude Code for the full build. Recently switched to Codex, so using both now. Dabble in Lovable too, on level 3/Gold. Build stack: Next JS, Vercel, Supabase, GitHub, Railway, Sentry, PostHog. It's becoming an expensive passion!

  ↳ **Matt Murphy** · 2026-06-25

  > Bukie, that’s a very real stack.
  > 
  > I like the progression too: Google AI Studio for fast thinking and early prototyping, then Claude Code / Codex once the build starts getting more serious.
  > 
  > That’s usually how it goes. One tool helps you explore, another helps you execute, and then suddenly you’ve got Vercel, Supabase, Railway, Sentry, PostHog, GitHub, and a monthly bill that looks like it went to private school. 😂😂
  > 
  > But that’s also the sign you’re moving from “playing with tools” into actually operating builds. Game on!!!🚀🚀🚀

**Pasha Zahid** · 2026-06-25

> Claude
> n8n
> Cursor
> Obsidian
> GitHub
> Render

  ↳ **Matt Murphy** · 2026-06-25

  > Pasha, clean and dangerous combo right there bro!!!
  > 
  > Claude, n8n, Cursor, Obsidian, GitHub, Render, that’s a solid operator stack.
  > 
  > What I like about that setup is you’ve got thinking, building, automation, documentation, version control, and deployment all represented. That’s when the toolchain starts becoming a workflow instead of a pile of apps.
  > 
  > Simple stack. Plenty of leverage. Fully ready to rock 🤘 😎

**Alan Joyce** · 2026-06-26

> Hi everyone, Al here from Ireland. I started with Replit having zero knowledge of anything mainstream only open ai and note book and pen and making sense of what I wanted was nice starting off point. In fairness I took that and used manus ai to make sense of my own thoughts as an exercise then realised it could mock up html and some scripts and started to get excited:) from then on I moved in to Replit and their offerings only to realise I burned through api database tokens or data in about ½ hour as to be fair I didn’t fully understand what was happening in the back ground. With that said i figured I have my own domestic machines on 24/7 and running Linux which brought me on to node.js and all its delightful things. And Postgres and well I had already been using Cloudflare for sites and bits and running Unifi systems at home for obfuscation and port mapping, I got in to Docker as a tool, sorry for the long story I then in my infinite wisdom moved on to antigravity and started to get the feel for what these platforms and agents llm models could do. To me every one had its own idea of what was right and to me none were infallible and none would hit the ball out of the park and they all seemed to sing from the same hym sheet. I’ve been having fun and i remember hooking up my fist little sass through to the internet from at home and thinking yes I love this.! The other day I was doing some cleanup in an old running Mac mini circa 2012 16gb ram 256GB ssd, it runs azurcast in docker, I ssh’d added the key to stop having to type passwords setup some fan controls and checked the drive for smart failure. As that all worked and I realised I could control the fan via ssh I span up a little front end to Marry to the back end now I can see the two radio stations that run via api, and the I/O of each drive internal ssd and external spinny drive :) I can play the music of each station directly through the front end, i can see bandwidth uses and start and stop remotely but more importantly control the fan and see live speed. Two things I love is making dashboards and getting things controlled. Thankful and grateful to be here with all you guys/gals and look forward to learning and being part of the community. Thanks for reading.

  ↳ **Matt Murphy** · 2026-06-26

  > Alan, this is a proper builder journey for sure.
  > 
  > Started with Replit, burned through tokens, got curious, hit the limits, moved local, found Docker, Node, Postgres, Cloudflare, Linux boxes, old hardware, radio streams, fan controls, dashboards… that’s the path right there bro.
  > 
  > Honestly, I love this kind of stack because it’s not theoretical. It came from you trying to control real machines and solve real problems in your own environment. That's where that muscle memory builds with reps.
  > 
  > Also, “none were infallible” is an important lesson. Every tool has opinions. Every model has gaps.
  > 
  > The builder’s job is learning enough of the 13-layers underneath to know when the tool is helping and when it’s confidently driving into a ditch, lol, we've all been there.
  > 
  > Glad you’re here. And I fully support any build that starts with “old hardware in the attic” and somehow turns into dashboards and remote control. That’s proper mad scientist energy. 👊😎

**Rob Smith** · 2026-06-26

> I’m building a SaaS with VS Code/Claude Code/Codex
> Supabase
> Cloudflare
> Vercel
> Railway
> Stripe
> Resend
> Open exchanges
> Supabase OAuth
> Wasabi
> Coderabbit
> Sentry
> Thanks Matt for telling me about CodeRabbit. It has been amazing.

  ↳ **Matt Murphy** · 2026-06-26

  > Rob, this is becoming a very common vibe coder stack, and I mean that in a good way. Well done.
  > 
  > VS Code with Claude Code / Codex, Supabase, Cloudflare, Vercel, Railway, Stripe, Resend, Sentry, CodeRabbit, that combo probably looks like 60% of the serious builders trying to get real SaaS products out the door right now.
  > 
  > And honestly, it makes sense.
  > 
  > You’ve got AI-assisted building, hosted database/auth, deployment, edge/networking, payments, email, error tracking, and code review all represented. That’s not a bad stack at all.
  > 
  > The trick now is learning enough of the 13 layers underneath it so you know where the tool is helping, where it’s hiding complexity, and where it might be quietly setting you up to drive into a ditch.
  > 
  > But yes, solid setup. Very recognizable modern builder stack. Happy to have you here! 👊😎

  ↳ **Rob Smith** · 2026-06-26

  > Thanks Matt, good to be here. If this build goes well I will need the knowledge to run it or there’s no point.

  ↳ **Matt Murphy** · 2026-06-26

  > [Rob Smith](https://the-faction.mn.co/members/40329969) that's what we're her for bro, to help you get that bad boy into production and generating revenue. That's a win! 💪

  ↳ **Tim Arnold** · 2026-06-27

  > Whats CodeRabbit?

  ↳ **Rob Smith** · 2026-06-27

  > Hi Tim, I run CodeRabbit as a VS-Code plugin to check every code change in my local repo before pushing to GitHub. It picks up on sloppy code from Claude amongst other issue. It also questions Claude briefs before getting Claude code to implement. Matt will have a more advanced view.

  ↳ **Matt Murphy** · 2026-06-27

  > Rob’s explanation is pretty much how I think about CodeRabbit too. 🙌
  > 
  > It is basically an AI code review layer. Not a replacement for understanding your own code, but a second set of eyes that can catch sloppy diffs, missing edge cases, weird Claude/Codex decisions, and “why did the robot do that?” moments before they hit GitHub.🤣
  > 
  > That layer matters more now because AI can help you generate code faster than you can mentally review it. But we all know it’s spaghetti under the hood.
  > 
  > CodeRabbit is one option. GitHub Copilot code review is another. Snyk is one I like a lot because it’s strong when you care more about security scanning. SonarQube / SonarCloud are great for code quality and static analysis. I know of but haven’t broadly used Qodo, Greptile, Graphite, and Bito, they are also worth looking at depending on your workflow.
  > 
  > My general advice:
  > 
  > Use AI to write faster.
  > Use review tools to slow the mistakes down.
  > Use tests to prove the thing works.
  > Use your own brain before anything goes to production.💥
  > 
  > No tool is infallible. The point is adding enough guardrails that when Claude confidently drives into a ditch, something yells before you ship it. 😂😂

  ↳ **Tim Arnold** · 2026-06-27

  > [Rob Smith](https://the-faction.mn.co/members/40329969) oh damn I'll have to check this out! I got a local ai called Verdent and it sounds similar.

**Awie Hoh** · 2026-06-27

> I'm using (and still learning) Claude Code together with Codex. Currently still trying to make software which helps me automate my small business. At the same time i'm trying to develop a system for a non-coder to ship more reliable software using both of those tools. It's still a work in progress and would very much appreciate help and input from the professionals.

  ↳ **Matt Murphy** · 2026-06-27

  > Awie, this is exactly the right kind of work in progress. 💯
  > 
  > Using Claude Code and Codex to solve your own small business problems is where the real learning starts. But the bigger idea you’re circling is even more important: every small business is going to need its own production conveyor belt for automation and software.
  > 
  > Meaning anyone in the business can spot a problem, start an automation, or build a tool, but it doesn’t go straight into production. It goes onto the conveyor belt.
  > 
  > Spec it. Build it. Review it. Test it. Harden it. Check the data, security, workflow, edge cases, and deployment. That’s what the 13 layers are really doing.
  > 
  > That’s the process we run inside The Faction Group: we take an idea from rough build to production-ready system.
  > 
  > Because the crazy part is this: every small business is becoming a software company now. Every single one. If you haven’t read my book yet, you should check it out. This is literally what it’s all about.
  > 
  > The winners will not be the ones who let two confident robots freestyle in production.
  > 
  > The winners will be the ones who create a repeatable process for turning business problems into reliable systems.
  > 
  > You’re thinking in the right direction, bro. Keep building it. 💯👊😎

**James Alan** · 2026-07-20

> I have zero coding and or IT experience. Started with Chat GPT and VS Code, went to Claude and VS Code with Claude Code, Obsidian w/Gdrive and now Mempalace.

  ↳ **Matt Murphy** · 2026-07-20

  > Jimmy, I love seeing how your stack has evolved. You didn't just learn new tools, turns out you learned when each tool has a job. That's a much bigger milestone than people realize.
  > 
  > Going from ChatGPT to Claude Code, then layering in VS Code, Obsidian, Google Drive, and Mem0 is exactly how builders mature. You're building a system around yourself instead of relying on one AI to do everything. Keep stacking those skills, brother. 👊😎

**Chris B** · 2026-07-20

> Combination of
> 
> - windsurf/devin (pro subs - free access to models like kimi 2.7 and glm 5.2 for doing majority of the low level coding)
> 
> - Claude code (max x20) - picks up the heavy duty work and refinement
> 
> - codex (pro x5) - code review alternative and to Claude code. Basically if I build it in CC/Codex I’ll use the other for verification
> 
> - was using AWS credits but moved to superbase, then neon/qstash/vercel. Now self host Postgres/redis etc vercel still hosts
> 
> - self host glitchtip, infisical, unleash,
> 
> - probably forgotten a few things
> 
> I’m a business owner, run a penetration testing consultancy and ex-developer now building apps for my business

  ↳ **Matt Murphy** · 2026-07-20

  > Chris, this is a seriously well-balanced stack. I especially like that you're using Claude Code and Codex to challenge each other's work instead of letting one model validate itself. That's one of my favoriate go-to crosschecking tricks and one of the fastest ways to reduce blind spots bro.💯
  > 
  > The migration from AWS credits to a self-hosted Postgres/Redis stack also tells me you're making decisions based on operational needs instead of hype. That's engineering, not tool collecting.
  > 
  > And the fact that you're a penetration tester explains a lot. 😂 Your default mindset is "assume it can fail and prove me wrong," which is exactly the perspective more builders need as AI-generated code becomes the norm. We might have some pen test conversations on the horizon as our requests for that service at Faction Group is climbing rapidly everyday.
  > 
  > Looking forward to seeing more of your architecture decisions in here. I know you've got a lot of experience that can help the rest of the community, jump in any time. 👊😎

  ↳ **Rhet Wike** · 2026-07-22

  > [Matt Murphy](https://the-faction.mn.co/members/39706849) Yes! like i said ive drifted to sol allmost entirely, no model has found an issue with sols work yet, but that is not the case vice versa, on big projects i roll thru all the big ones with a copy paste block, Take whats good, leave whats bad behind, and move to the next LLM, we find multiple new lanes this way everytime. I have saved a lot of time doing it this way, as well as having a model check another models work mid write, (read only) usually catches good stuff, paste reply to the main worker and tell them to take whats good and leave whats not.

  ↳ **Matt Murphy** · 2026-07-22

  > [Rhet Wike](https://the-faction.mn.co/members/40719050)That's a solid thought process.

**Chris B** · 2026-07-20

> Thanks for the feedback, always good to know i'm on the right track. Always up for a new task and challenge and AI dev/coding with the same ethical pentesting approach is something i'm focusing on.
> 
> Working my way through your content, found your instagram reels great and the content you provide is really interesting.

**Hector Padron** · 2026-07-21

> Here you go. It was a 5 Ai model stack but, I had to fire Grok for constantly losing access to the repo and falsely reporting that it had verified Codex's work.
> 
> GPT=Compliance, Claude = Architectural Authority & Gate 2 verifier, Gemini = Research & Gate 3 verifier (API), Codex=Implementation Engineering/DevOps.
> 
> I included Gov given the number of moving parts (>100k LOC SPA).
> 
> IDE=VS Code

  ↳ **Matt Murphy** · 2026-07-22

  > Hector, I actually like seeing stacks evolve like this. You didn't just throw five models together because it sounded cool, you assigned each one a job and then adjusted when reality proved something wasn't pulling its weight. That's exactly what production engineering looks like. The fact that you removed Grok because it wasn't reliably doing what you needed is a bigger lesson than adding another model. Real builders optimize for outcomes, not logos. I'd love to hear how that stack changes six months from now after another few hundred thousand lines of code.

  ↳ **Hector Padron** · 2026-08-01

  > The evolution continues and a great lesson learned. Found a hole in my QA process - great at validating the code against specs but failed to validate to Production. Just added Claude Code as execution/production evidence instrument to test and provide proof of function. The cost - set may go live date back by 2 months (full audit and refactoring work). Ugh! But better now than at end stage (pre-live activities) of the project.

  ↳ **Matt Murphy** · 2026-08-01

  > [Hector Padron](https://the-faction.mn.co/members/40523060) Sounds like some really powerful learning has been happening as well as the evolution of your product, great share! And we can all empathize with pushing the timeline back a little bit to get it right, but never push the timeline back to get it perfect. Get it in the hands of the users, they’ll help you get it perfect by breaking it in ways you have yet to imagine 💪😎

**Timothy Smith** · 2026-07-22

> I am using Claude Code in VS Code. What are the perks to the other stacks and is there a lot of costs to them?

  ↳ **Matt Murphy** · 2026-07-22

  > Timothy, Claude Code inside VS Code is probably the most common answer I'm seeing right now. The interesting part isn't whether there are "better" stacks, it's knowing *why* you'd switch. Every additional model or tool adds complexity, context switching, and cost. If Claude Code is getting your product shipped, I'd stay there until you can clearly identify a bottleneck that another model actually solves. Don't optimize the toolbox before you've optimized the build.

**Benedikt Thomas** · 2026-07-22

> As a non tech i use Claude Code harness to orchestrate with Opus 4.8 , i have gpt 5.6 in claude harness which makes the implementation and fable i have as an advisor. I work from one session in orca and orchestrate through their cli. I use to Next.js and Convex as my tech stack. My current Problem is i worked so messy with no clear goal thats why face the problem of finishing projects

  ↳ **Matt Murphy** · 2026-07-22

  > Benedikt, this is a really thoughtful setup. You're treating models like specialists instead of expecting one AI to be great at everything, and I definietly think that's where the industry is headed bro. The orchestration layer becomes more important than any individual model. I'm especially interested in hearing how Orca is working in your workflow over the long term, because there aren't many people running a stack quite like yours. Keep sharing what works with us, and just as importantly, what doesn't.

**Rhet Wike** · 2026-07-22

> I have narrowed to 5.6 sol almost exclusively, Fable cant hold to any of my work, flags immediately on frontier model development, or cybersecurity. Grok proved to be the best for video gen.

  ↳ **Matt Murphy** · 2026-07-22

  > I appreciate that you're willing to cut tools when they stop creating value. Too many people become emotionally attached to a model instead of evaluating whether it's actually helping them ship. If 5.6 is carrying the workload for you today, lean into it. The stack should serve the builder, not the other way around. It'll be interesting to see how many people end up with these "leaner" workflows over the next few months as the models continue to leapfrog each other.

**Andrew Park** · 2026-07-23

> I am also using VS Code with Claude and Codex simultaneously, with a Hermes agent on vps as my personal assistant/executive assistant and I have a Herdr software factory and paperclip companies that I am making into the workers for my companies, its a pretty complex setup but the main driver is claude with vscode at the seat still really mapping out the foundational stuff. I just joined today your free community and I think you have a lot of great insight and information that I don't really get anywhere else. I am not a programmer or developer but I think I use AI at a very advanced level because I have real world applications to implement them on, but your information really hits at the stuff I would probably miss because I am not from this background and I appreciate it.

  ↳ **Matt Murphy** · 2026-07-23

  > Andrew, welcome aboard, and thanks for sharing your stack. It looks like my business operating stack.
  > 
  > From experience I actually think you’re in a position a lot of business owners are heading toward, using AI at a very high level without having spent years as a software engineer first.
  > 
  > The important part is that you’re solving real business problems, not just collecting tools. Claude, Codex, Hermes, VS Code… those are all just parts of the factory.
  > 
  > The value comes from how you orchestrate them to produce consistent outcomes, which you likely know is not the easiest of tasks for an active operator.
  > 
  > As you work through the Foundations, you’ll probably find yourself putting names and frameworks around instincts you’ve already developed.
  > 
  > Keep sharing what you’re building as it evolves. We have a lot of builders here who are taking a similar path, and those conversations are where the community really shines.
  > 
  > Glad you found us, brother. Looking forward to seeing those software factories come to life. 👊😎

**Tareq Dheeb** · 2026-07-30

> I'm using VS Code with compaination of OpenCode, Agancy agents and superpower skills.

**Emekalam Chibuzor** · 2026-07-31

> Claude Code💯

**Cody Hughes** · 2026-08-08

> Claude Code
> Supabase
> Vercel
> GitHub

**Nevon Jameel** · 2026-08-10

> VS Code, Claude Code (CLI) Fable 5 orchestration and Opus 5 for the subagent-driven tasks, VPS server, Sentry, ExpressJS, TypeScript, Github. 🤗

  ↳ **Matt Murphy** · 2026-08-10

  > That's a good looking stack right there, even some frontier model action, well done. Happy to have you in the room, welcome! 👊😎

**Collin Leijenaar** · 2026-08-22

> Frankenstein combo, and unapologetically so.
> 
> Started in Lovable, apps still live there, Lovable still does the UI and the hosting. But 90% of my day is Claude Code and Codex on the same repo. Opus 5 builds, Fable 5 writes the build briefs, Codex Sol and Grok do the reviewing. Nothing gets built by the same model that checks it.
> 
> The glue is GitHub Projects. Every bug or feature is an issue on a board, and a few Claude Code runs fire every morning to tell me what moved overnight and what's waiting on a decision from me. I approve the plan, the loop executes it, I'm the only one who merges.
> 
> Supabase underneath.

  ↳ **Matt Murphy** · 2026-08-23

  > Collin, this is proper Frankenstein architecture 😂 and I mean that as a compliment.
  > 
  > What I like most is not the number of tools, it’s the separation of responsibilities.
  > 
  > One model builds, another writes the brief, others review, and nothing checks its own homework. That’s a much more mature pattern than “pick one AI and trust it.”
  > 
  > GitHub Projects as the control plane is also smart. Every feature or bug becomes visible work, the overnight runs surface movement and blockers, and you remain the human approval gate before anything merges. That is exactly the balance I like: automate aggressively, but keep ownership and accountability human.
  > 
  > And Supabase underneath gives the whole thing a pretty clean spine.
  > 
  > Keep sharing how this evolves. 👊😎

**Mark Kirby** · 2026-08-23

> Clock code.
> Supabase with Postgres.
> Vercel
> Github
> Sentry |

  ↳ **Matt Murphy** · 2026-08-23

  > Mark, that’s a clean stack. Clock Code, Supabase/Postgres, Vercel, GitHub, Sentry, nothing fancy just for the sake of being fancy.
  > 
  > What I like is that every piece has a very obvious job: build, data, deploy, version, observe.
  > 
  > That’s usually a sign the stack has matured around the work instead of becoming the work. 😂
  > 
  > Curious how you’re using Clock Code day to day, mostly implementation, or are you also using it for planning, debugging, and review? 👊😎

  ↳ **Mark Kirby** · 2026-08-23

  > [Matt Murphy](https://the-faction.mn.co/members/39706849) Firstly, my bad. My English accent confused Wispr, and you got clock code rather than Claude code, 😂
  > 
  > All four, and the split has shifted a lot.
  > 
  > I have relied on interacting with the Claude Code and Claude Design to lead me on this virgin path. I have used Replit in the past to do some small app-type stuff, but this is a fairly significant build that I have ended up developing. I'm your classic founder/business person who thrives on taking on new challenges and going into the unknown, and I've got to say, your forum and your Facebook posts are exceptionally helpful. I thank you for that!! 🫡
  > 
  > Implementation is the smallest part now. Most of the value sits in planning and review, because that's where the expensive mistakes live.
  > 
  > What changed it for us wasn't the tooling, it was writing the record down. Every ruling goes into an append-only decisions file with a number, and it's never rewritten. Superseded reasoning stays where it is, dated. A separate board is the only thing allowed to say what happens next. A session opens by reading those rather than by asking me.
  > 
  > Sounds like overhead. What it buys is parallelism. I run several sessions at once on the same repo and they don't collide, because the record arbitrates instead of me. Two of them filed work under the same reference number this week, spotted it, and one renumbered itself without my involvement.
  > 
  > Review is where it earns most. This week I asked why some photos I'd added weren't appearing on a printed sheet from our app. It came back with three defects in one four-line function: the exporter never reads two fields that exist in the data model, so an uncaptioned photo prints as a blank row and a link's URL gets dropped whenever there's also a caption. I'd have found the first one. Not the other two.
  > 
  > Debugging, yes, but I've learned to make it prove things rather than explain them. Every claim has to carry the command that produced it.
  > 
  > And your MCP post landed. We run one with 39 tools and have never measured its token cost against a direct call. That's on the list now!!
  > 
  > Over the next week, I'm moving from prototype stage on to getting an external expert to review and design the schema. I'm just soaking up all the great best practices you are providing to help ensure I'm delivering the best set of documents possible so he can provide the plan that I can hopefully execute with minimal future headaches.

  ↳ **Matt Murphy** · 2026-08-23

  > [Mark Kirby](https://the-faction.mn.co/members/41185591) that makes a lot more sense…lol. 🤣🤣👊😎

**James Jackson** · 2026-08-24

> My stack's a bit of a Frankenstein setup, built out of necessity. I'm a surgical tech and lifelong tradesman with zero coding background, and typing/screen work is hard for me, so everything runs through voice. Claude Code is the actual build engine, in VS Code. Gemini Notebook (NotebookLM) does the heavy research synthesis before it feeds back in. Cowork handles autonomous browsing and screen tasks. No Cursor, no Bolt, no Lovable, I'm not touching code by hand at all, I'm directing Claude conversationally to build, debug, and troubleshoot everything, including the home automation system I'm building right now. Found this community because I realized what I've been doing for six months has a name: vibecoding. Here to close the gap to production-grade."

  ↳ **Matt Murphy** · 2026-08-24

  > James, welcome to The Faction, brother. This is actually one of the best examples of AI-directed engineering I’ve seen because your stack didn’t come from chasing tools, it came from solving around a real constraint.
  > 
  > Voice as the primary interface, Claude Code as the build engine, NotebookLM doing research synthesis, Cowork handling the screen work…
  > 
  > Nice.
  > 
  > And I love the line that you’re not touching code by hand. That’s exactly why understanding the architecture matters even more. If AI is doing the implementation, your job becomes knowing what should exist, how the pieces connect, what can fail, how you test it, and whether what came back is actually production-worthy.
  > 
  > The home automation build should be a great project to carry through the layers because it’ll force you into permissions, networking, integrations, state, failure recovery, security, and a bunch of real-world edge cases where “works on my machine” doesn’t mean much. 😂
  > 
  > Really glad you found us, James. Keep sharing this build,I think your voice-first workflow is going to be useful for a lot of people in here. 👊😎

**J Ramos** · 2026-08-26

> Frankenstein steup: My current stack is mostly TypeScript, JavaScript, Supabase, Postgres for the backend and database, Supabase Edge Functions for server-side jobs, GitHub for version control, and Cloudflare Pages, Workers for lightweight web projects. For mobile I’m working with Expo, React Native. I use VS Code with Claude Code and Codex in the development workflow, plus Docker, WSL for local development. On the data side I’m integrating APIs such as Helius and Moralis for blockchain/market data.


---
_Source: https://the-faction.mn.co/posts/103506384_
