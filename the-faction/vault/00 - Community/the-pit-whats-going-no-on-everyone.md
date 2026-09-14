---
space: "The Pit"
author: "Nicholas Carmona"
post_id: 104867513
reactions: 1
comments: 8
published: "2026-07-21T15:21:30Z"
source: "https://the-faction.mn.co/posts/104867513"
---

# What’s going no on everyone!

What’s going no on everyone!

Another question for everyone, wondering how everyone goes about their thought process here:

When you fix a bug or you create a new feature, you of course will QA the happy path, but how do you go about designing your edge cases?

It’s a bit easier personally for my self due to my years in tech support and working in very technical roles, its more of a muscle memory for myself so im very curious on how others go about it

---

## Discussion

**chris cruz** · 2026-07-21

> I've been running multiple adversarial reviews with different models. Each reviewer takes a different review role. Is this what you were asking about or do you mean for testing edge cases?

  ↳ **Nicholas Carmona** · 2026-07-21

  > Yeah I mean more so acting as a user and how they would use your application and then creating different scenarios that could potentially break the feature or continue the bug
  > 
  > I’ve used multiple adversarial agents also in that flow to see if the code is correct, but actually doing the clicking around. There are moments I do use computer use to do the QA of the platform with codex, but it takes forever at times

  ↳ **chris cruz** · 2026-07-21

  > [Nicholas Carmona](https://the-faction.mn.co/members/40267888) Good question. I'd like to know if someone has a good way to QA as well.

**Nicholas Carmona** · 2026-07-22

> Hey [Matt Murphy](https://the-faction.mn.co/members/39706849) ! could you tell us what your process is for this?

**Matt Murphy** · 2026-07-22

> I’d be happy to brother, I’ve actually been writing my reply since yesterday just been too busy to finish my thoughts.
> 
> It’s a great question every builder deals with.
> 
> I actually don’t start by thinking about edge cases, I start by assuming my users are going to break my app in ways I never intended.
> 
> Every feature gets tested from four perspectives:
> 
> 1. Happy Path, Does it work exactly as designed?
> 
> 2. Failure Path, What happens if an API times out, the payment fails, the network drops, or the database throws an error? Does the user get stuck or recover gracefully?
> 
> 3. Malicious Path, If someone actively wanted to abuse this feature, bypass permissions, inject data, or access another tenant’s information, what could they do?
> 
> 4. Human Path, This is the one most people skip. What does an exhausted, distracted, or impatient user do? Double-click the button. Refresh halfway through checkout. Submit the form three times. Close the browser. Paste garbage into every field. That’s where a surprising number of production bugs come from.
> 
> I don’t try to imagine every edge case myself anymore. I have AI generate dozens of adversarial scenarios, then I keep asking, “How would this fail?” until it runs out of ideas.
> 
> The goal isn’t perfection, it’s systematically removing the obvious ways your application can surprise you in production. 👊😎

  ↳ **Nicholas Carmona** · 2026-07-22

  > You’re the man! Appreciate the response! Apologies on if it sounded like I was rushing you 🙏🏻
  > 
  > That all makes sense, it’s nice and refreshing that I have the same thought process as you!

  ↳ **Rhet Wike** · 2026-07-22

  > Right! as a refridgeration technician i look for the thing that is gonna get me called back, the idiot that hits a breaker with a cardboard box, so we lock the breaker panel. expect the unexpected, fixate on what you dont know, and what would happen that you would neer think to happen.

  ↳ **Matt Murphy** · 2026-07-22

  > [Nicholas Carmona](https://the-faction.mn.co/members/40267888) you didn’t rush me at all brother you reminded me to press send on something sitting in my drafts. I appreciate it greatly.!


---
_Source: https://the-faction.mn.co/posts/104867513_
