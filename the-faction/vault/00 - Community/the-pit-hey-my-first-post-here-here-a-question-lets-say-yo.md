---
space: "The Pit"
author: "Manuel Lautenschlager"
post_id: 104553047
reactions: 2
comments: 3
published: "2026-07-14T10:54:26Z"
source: "https://the-faction.mn.co/posts/104553047"
---

# Hey! My first post here. Here a question, lets say you have an experienced devel

Hey!

My first post here. Here a question, lets say you have an experienced developer. What takes longer:
- create every line of the code manually?
- review every line of AI code manually, and really understand each line in the complete context, like if you have developed it?

I am getting more and more unsure about this. I made the experience, that you don't really understand the complete picture by just looking at the PR changes. Alternatives are, asking the AI questions about the changes. What are you doing here? why is it needed? Is this not covered somewhere else? costs tokens of course.

It's hard to catch up the review queue anyway. Without the help of AI it's almost impossible to process all AI produced changes. On the other hand, if the AI creates reviews (Claude/Copilot), and the changes are larger, it's an endless review process, because the AI finds issues again and again. Which makes sense, because we told the AI to find something. And every change triggers another review cycle. Even if i fix the comments with AI it's not perfect. Because AI takes the comments as instruction. My prompt here is: "investigate if the change request makes sense in the full context", which burns tokens like hell with 100s of AI review comments

I am curious how you are handling this?

On my private projects I just limit PR review cycles. One review cycle, that's it. And complete testing at the end, and a complete security and code cleaness review (and any other review you need prelaunch). But in a company environment it's hard to ignore comments, even if minor, but they are reasonable. I want it merged and not another 10 review cycles.

Another try I did, is to ask the coworkers, to tell the AI to limit found issues by explaining the context: This is the first prototype. We are not using webhooks yet. Security and RBAC is not in place yet. We need a MVP and get it merged. don't complain about typo-details, comments, things that are caught somewhere else, things that can't happen, and so on.

---

## Discussion

**Matt Murphy** · 2026-07-14

> Manuel, this is exactly why the Faction is focused on teaching systems thinking instead of code thinking.
> 
> I personally don’t review every line of AI-generated code. But I do review architecture, boundaries, interfaces, security, data flow, and tests.
> 
> If the architecture is sound, AI can rewrite functions all day long. If the architecture is wrong, understanding every line won’t save you.
> 
> The goal isn’t to know 100% of the code, it’s to know 100% of the system. Every piece of curriculum in this program is built with this principle in mind.
> 
> AI writes code. Engineers own architecture. That’s where the leverage is. It’s time to orchestrate! 👊😎

**Tim Arnold** · 2026-07-14

> Hey, welcome. Good question, everyone hits this eventually.
> 
> Honest answer: reviewing AI code and truly understandng it takes longer than writing it yourself. Nobody has time to do that on every PR so people fake it, and thats where trust breaks down.
> 
> Whats worked for me, building out a HIPAA-adjacent SaaS platform right now:
> 
> Set the scope before you prompt, not after. AI does exactly what you tell it and nothing more. If you dont say "this is a prototype, skip RBAC, skip webhooks" it defaults to paranoid mode and finds issues forever, because you told it to find issues. On my genomic ordering platform (compliance-grade, multi-tenant) that mattered a lot early on, I had to be explicit about what tier we were building at or the AI would try to enterprise-harden a feature that was still just a rough draft.
> 
> One review cycle, like your already doing. Give it a limit: "only flag what breaks this feature in prod, skip style and typos." otherwise its an unbounded loop. I run RLS and security stuff pretty tight on my current build (Supabase, real tenant data, Meta CAPI tracking in the mix) and even there I cap it at one real pass, then a dedicated security/RLS sweep at the end instead of nitpicking every commit.
> 
> Use quality gates instead of endless rounds. Tests pass, RLS on, no secrets in code, build succeeds. Gates green, you merge. Thats your definition of done, not "AI stopped complaining." Learned this the hard way on a past build where review just never ended because nobody had defined what done meant, we were just reacting to whatever the AI flagged next.
> 
> Bottom line: writing it yourself is faster per line but doesnt scale. Reviewing with real understanding is slower per line but scales, once your disciplined about scope. "AI reviewed it" and "I understand it" are not the same thing, and only one of those lets you sleep once its live and real users data is running through it.

**Manuel Lautenschlager** · 2026-07-14

> It's probably also a psychological thing. You don't want to deliver embarrassing work. If you deliver a mistake, you want it to be your mistake. You want to keep the illusion that you still have control. But this control costs scalability. I feel this too, but my strategy is different. If the AI did a mistake, tell the co-workers a and boss, the AI did it. It's not an excuse, it helps preventing, that it happens again. Nobody in our company says: The AI did the mistake. It looks like your pushing away responsability, but is actually the right way of failure-management.
> 
> For my private projects i work the way you describe. 1 cycle. clear rules during production and review. clear defined tests coverage and sofisticated test suite created with opus agent. SOLID Grade A programming pattern, Fix errors with tdd red. tdd, no fallbacks, silent errors and defensive programming without explicit permissions. Errors need to be loud. For me these are the most important rules.


---
_Source: https://the-faction.mn.co/posts/104553047_
