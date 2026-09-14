---
space: "The Mentoring Lounge"
author: "Navy Dad"
post_id: 106727744
reactions: 1
comments: 5
published: "2026-09-01T06:23:14Z"
source: "https://the-faction.mn.co/posts/106727744"
---

# New Here. I am finishing up a solo project and have done everything I could thin

New Here. I am finishing up a solo project and have done everything I could think and have researched to do to keep my AI from any database access other than specifically what it is intended to do. What are you doing for guardrails to ensure the AI sticks to its sole purpose.

---

## Discussion

**Matt Murphy** · 2026-09-01

> Navy Dad, welcome in, we're happy to have you and this is exactly the right question to be asking before you call the project done.
> 
> The biggest thing I’d tell you is: don’t make the prompt responsible for keeping the AI in its lane. Make the architecture responsible.
> 
> I generally want the model to have zero direct database access. It should only be able to act through narrowly defined tools or backend functions that you control. If the AI needs customer data, give it a function like get_customer_summary(customer_id) rather than credentials that let it query the entire database.
> 
> Then stack the guardrails:
> 
> **Least privilege:** separate service accounts/roles with only the permissions each tool needs.
> 
> **RLS/RBAC:** tenant and user boundaries enforced by the database/server, not by the model.
> 
> **Allowlisted actions:** the agent can only call functions you explicitly expose.
> 
> **Schema validation:** every tool input is validated before anything executes.
> 
> **Read vs. write separation:** default to read-only. Anything destructive or financially meaningful should require a stronger gate.
> 
> **Human approval for irreversible actions:** delete, refund, send, publish, change permissions, etc.
> 
> **Audit everything:** who requested it, what tool ran, parameters, result, and whether it actually completed.
> 
> **Rate limits / quotas:** one confused agent shouldn’t be able to hammer your database 10,000 times.
> 
> **Kill switch:** you need a way to immediately disable agent actions without taking the entire application down.
> 
> And one of my favorite rules: never trust the agent’s claim that something happened. Verify it independently. “I updated the customer record” and “the database confirms the expected row changed” are two different things.
> 
> The goal isn’t to make the AI perfectly obedient. You won’t. The goal is to build a system where even a confused or compromised agent has a very small blast radius.
> 
> If you’ve already been thinking this way on a solo build, you’re ahead of a lot of people. That’s exactly the kind of architecture discussion the Mentoring Lounge is for. 👊😎

  ↳ **Navy Dad** · 2026-09-02

  > Great. Appreciate the feedback. You're a great teacher. Coming from the Navy side of the house I like your no nonsense, right to the point way of communicating. Thank you for sharing your knowledge and experience with all of the community. It means a lot so Thank You!

  ↳ **Matt Murphy** · 2026-09-02

  > [Navy Dad](https://the-faction.mn.co/members/40845879) much appreciated, I was raised in a military house with a spectrum disorder, so my ability to shoot straight my be my best asset to my clients lol. Thank you for your support and if you need anything don't hesitate to speak up.

  ↳ **Navy Dad** · 2026-09-03

  > [Navy Dad](https://the-faction.mn.co/members/40845879)I don't believe in putting all your eggs in one basket. So I have 3 different AI's should 1 go down or app will still function where AI is required. Since they are 3 different is there anything from your response on guard rails that I may have to adjust per AI or will the guardrails etc work universally?

  ↳ **Matt Murphy** · 2026-09-03

  > [Navy Dad](https://the-faction.mn.co/members/40845879) you are doing it right. Never just one, or too many, but just enough to provide oversight and cross auditing power across your builds.


---
_Source: https://the-faction.mn.co/posts/106727744_
