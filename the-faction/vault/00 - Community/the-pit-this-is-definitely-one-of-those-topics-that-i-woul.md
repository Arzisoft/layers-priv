---
space: "The Pit"
author: "Matt Murphy"
post_id: 103836209
reactions: 1
comments: 4
published: "2026-06-27T13:05:28Z"
source: "https://the-faction.mn.co/posts/103836209"
---

# This is definitely one of those topics That I would never say on Instagram becau

This is definitely one of those topics That I would never say on Instagram because it would get taken out of context.

But I stopped doing code reviews first, a long time ago.

Not because they do not matter.

But Because I was reviewing the wrong thing in the wrong sequence.

For years we looked at code first and asked is this clean. Is this efficient. Is this following best practices.

Inevitably The answer was almost always yes.

The code was fine.

It was The architecture that was not.

And Clean code inside a broken architecture is a beautifully painted house on a cracked foundation.

So Now when someone brings me a project at Faction, I do not look at the code first. I look at the thirteen layers first.

Where does the data live. How does it move. Who can access it. What happens when it fails. How quickly can I recover it.

Now The code is the last thing I check. Because it is the easiest thing to fix.

What I want to know is whether the decisions underneath were made intentionally or accidentally.

Most of the time they were accidental, especially now that AI is building the scaffolding.

And That is not a criticism.

In fact, That is the gap we are here to fill with the AI Directed Engineering path.

We want builders to be able to not only correct their code, but to solve their infrastructure issues for their product overall.

And that’s a win.

Tell me how are you testing your systems and code, eyeballing it, prompts, what’s your process, drop it in the comments.

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m53s_

This is definitely one of the topics that I wouldn't put on Instagram because it get taken out of context almost immediately. And if you knew how many DMs and comments I get, you'd understand. It's not a win. But I stopped doing code reviews first a long time ago. Not because they don't matter, but because I was reviewing the wrong thing in the wrong sequence every single time.

For years, and I mean years, we are looking at code first, if it was clean, if it was efficient, it was following best practices. And inevitably, if you look back, the answer was almost always yes. The code was fine. It was the infrastructure underneath it that was not. And clean code, well, inside a broken architecture is a beautifully painted house on top of a cracked foundation.

Also, not a win, right? So now when somebody brings me a project at Faction to review, I do not look at the code first. I look at the thirteen layers first. It's where the whole methodology began. Where does the data live?

How does it move? Who can access it? What happens when it fails? How quickly can I recover it? Now the code is the last thing I check now because it's usually the easiest thing to fix.

What I want to know is whether the decisions underneath it, the infrastructure decisions, were made intentionally or accidentally. And most of the time they were fully accidents, right? Especially now that the AI is building the scaffolding for us. And that's not a criticism. It's what we fix.

Vibe code finishing, right? But in fact, that's where the gap lived that we wanted to fill with the AI directed engineering path. Because we want builders to not only be able to correct their code, but to solve their infrastructure issues for themselves and their users related to their product overall. So I'm intrigued. Tell me how you're testing your systems.

Are you eyeballing it? Are you running prompts against it? What are your best practices? What's working for you? Drop it in the comments.

Let's talk about it.


---

## Discussion

**Alan Joyce** · 2026-06-27

> This is gold.
> 
> I don’t really have a solid grasp of best practices yet, but I watched one of your videos earlier about RLS. Up until about a month ago, while working on a side project, I asked the AI fairies what the best practices were for helping mitigate database breaches from users and bad actors. RLS (Row Level Security) kept coming up.
> 
> Thanks to your explanation I actually understand it a bit better now. With a lot of prompting I managed to get it working, although I’ll definitely need to test it properly before I trust it completely.
> 
> I originally thought JWT was the main thing I needed for security. Then I went down a rabbit hole and learned that JWT isn’t encrypted at all. It’s just a signed, short lived access token. Then I found JWE (JSON Web Encryption), but from what I’ve read it has more CPU overhead and probably isn’t necessary for standard user logins if you’re not putting sensitive information in the token.
> 
> At the moment my thinking is to layer security something like this:
> 
> Cloudflare WAF and DDoS protection.
> JWT authentication.
> Node.js role based permissions.
> PostgreSQL Row Level Security.
> Database permissions, where the API connects using a database role with only the minimum privileges it needs.
> 
> I’m pretty sure I’ve got most of that in place now, although I still need to double check the database permissions.
> 
> There’s so much to learn. Every time I think I’ve figured something out, I discover three more things I didn’t know existed. It’s actually reassuring knowing these security layers are available.
> 
> Side note, I really like magic links. I implemented them on my first Replit project, which I’m still paying for every month because it’s still hosted there. I need to migrate it off without breaking everything. It was my first proper project and I still think it has potential if I deploy it properly.
> 
> I’ve also got object storage and a VPS with Contabo in Germany waiting for me to move more of my projects across over the next few months. At the moment some of my work in progress is literally running natively on my Mac.
> 
> I’m sure some of you are probably cringing at the naïvety of what I’m doing, but that’s exactly why I’m here. I’m here to listen, learn, ask questions, and hopefully improve.
> 
> I appreciate you all.

  ↳ **Matt Murphy** · 2026-06-27

  > Alan, this is gold right back. So happy you are here, slainte-agad-sa🇮🇪!
  > 
  > And honestly, nobody should be cringing at this. This is exactly what learning the 13 layers looks like in the wild.
  > 
  > You started with “I need auth” and then uncovered JWTs, RLS, database roles, WAF, DDoS protection, permissions, token strategy, hosting choices, object storage, migration risk… that’s the path right there bro.
  > 
  > The win is not that everything is perfect yet. The win is that you’re starting to see the system underneath the app.
  > 
  > That’s the muscle, and it's all about doing the reps.
  > 
  > Also, your point about JWT is a great example. A lot of people hear “JWT” and think “security solved.” But JWT is just one piece. If the database permissions are wide open, or RLS is wrong, or every API route can touch everything, the token is not saving you.
  > 
  > Same with magic links. They can be great. But now you’re thinking about where it’s hosted, how to migrate it, what breaks, what needs to be protected, and how to move it without torching the whole thing.
  > 
  > That’s not naïve. That’s engineering judgment starting to form.
  > 
  > Keep asking these questions, stay active in here. This is exactly the kind of conversation that makes the whole room better. 👊😎

**Alan Joyce** · 2026-06-27

> Many moons ago I learned WordPress and, like a lot of people starting out, I relied heavily on plugins.
> 
> Back then I was involved with InvolvedFM, an online radio station. We had a VPS in Amsterdam acting as a relay server so we could broadcast audio and video from pubs and clubs around Ireland, giving DJs, singers, songwriters and local talent somewhere to perform. Bear in mind this was over 3G mobile broadband. We were streaming 640×480 video with 128kb MP3 audio and, for the time, it was more than enough to have fun.
> 
> I had someone looking after the Linux VPS while I focused on the front end, writing articles, building the website and trying to grow the community.
> 
> Then, about an hour before my very first live DJ stream, disaster struck.
> 
> Some script kiddie from a Tunisian hacking group brute forced their way into the WordPress installation through a vulnerable plugin. From what I remember there were also concerns around the domain registrar, but whatever the route, the site was compromised. I genuinely thought the project was finished before it had even begun.
> 
> That experience led me onto security forums where I met a French white hat hacker. He helped me recover everything, taught me a huge amount, and even hosted my WordPress installation on his own server for free while I got back on my feet.
> 
> That’s community.
> 
> Ever since then I’ve had a healthy respect for security. Firewalls, networking, Linux, hardware, application security. Not because I’m an expert, but because I’ve learned the hard way that hoping someone else has it covered isn’t a strategy.
> 
> Fast forward to today and I’m building a community platform for filmmakers.
> 
> A friend in the UK is learning app development alongside me. He said something like, “Don’t worry about security. The big platforms take care of that.”
> 
> I couldn’t disagree more.
> 
> You don’t need to become a penetration tester, but if you’re building something that people trust with their data, you owe it to them to understand the basics. Authentication. Rate limiting. Logging. Firewalls. Bot detection. Session management. At least enough to understand what your own application is doing.
> 
> So I started building those pieces in.
> 
> I added dashboards showing IP activity. Pulled in threat intelligence feeds containing known bad actors. Added rate limiting. Temporary bans that escalate into permanent bans. Login protection. Borrowed ideas from QNAP where repeated failures trigger timed lockouts before a permanent block.
> 
> Within a few days I could see it working. Temporary bans became permanent bans and the attack traffic dropped noticeably.
> 
> Then I decided to have a bit of fun.
> 
> The platform isn’t WordPress. It’s React, HTML and a Node backend. Yet one of the most common things bots probe for is /wp-admin.
> 
> So I built a fake /wp-admin.
> 
> Instead of a login page, they’re greeted with the Jurassic Park “Ah ah ah… you didn’t say the magic word!” screen. It serves absolutely no purpose other than making me smile every time a bot wanders in expecting WordPress.
> 
> Somewhere in the stack there’s also a proper honeypot collecting information. Ironically, I build, test, move onto the next challenge, and now I can’t even remember exactly where I left it or how to get back to it. That’s probably a project for future me.
> 
> What surprised me most wasn’t blocking the obvious attackers.
> §It was figuring out the bots that are supposed to be there.
> 
> SEO crawlers.
> AI crawlers.
> Monitoring services.
> Search engines.
> And then the bots pretending to be all of those.
> 
> One day a crawler arrived over HTTP instead of HTTPS. I was showing it to a friend who isn’t technical and he immediately said, “That’s probably not Google.”
> 
> I’d completely overlooked something so simple.
> 
> Sometimes the best observations come from people who aren’t buried in the technology.
> 
> Now I’m spending more time verifying crawler identities instead of trusting whatever user agent string they present, because pretending to be Googlebot takes about five seconds.
> 
> I’d love to hear how everyone else approaches this. How are you validating legitimate AI and SEO crawlers versus the ones simply wearing a disguise? Oh on another note I tried to take a screen grab of the Jurassic park dude waving his finger for when someone tries WP access but I think I banned myself :) yes the learning is real, I mean I have local access but how many of you locked yourself or banned yourself on a firewall or is to only me? ssh access can happen on that as well. Ive had many awesome adventures. Peace and thank you guys.

  ↳ **Matt Murphy** · 2026-06-27

  > Alan, this is exactly why I say the code is usually the last thing I want to review.
  > 
  > This whole story is the 13 layers showing up in the reality of day-to-day tech: hosting, plugins, auth, bot traffic, rate limits, threat feeds, session management, logging, moderation, dashboards, recovery, and the lovely little surprise that half the internet still thinks every site has /wp-admin.
  > 
  > And you’re dead right that you don’t have to become a penetration tester to care about security. But if people are trusting you with accounts, content, customer data, or community access, you do owe them intentional decisions.
  > 
  > That’s the difference. Not perfect security. Intentional security. I also love the “Jurassic Park magic word” fake /wp-admin screen. That is proper builder humor and honestly a pretty great reminder that bots are often dumb, loud, and predictable… until they aren’t, right.
  > 
  > The bigger win here is that you’re not just blocking obvious attackers now. You’re starting to ask: who is touching my system, why are they here, what are they pretending to be, and what should happen next?That’s not plugin thinking anymore. That’s operator thinking. Proper scar-tissue engineering right there bro, keep it up.


---
_Source: https://the-faction.mn.co/posts/103836209_
