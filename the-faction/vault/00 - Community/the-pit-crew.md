---
space: "The Pit"
author: "Tim Arnold"
post_id: 103606420
reactions: 8
comments: 5
published: "2026-06-22T22:41:56Z"
source: "https://the-faction.mn.co/posts/103606420"
---

# Crew,

Crew,

I'm Tim Arnold. Marine veteran. No CS degree. No bootcamp. No tech background.

Before I started building, I was doing what most veterans do after service — figuring out what's next. I stumbled into GoHighLevel and started building automations for local businesses. That turned into Web Synq Design, a GHL-based infrastructure agency. I wasn't a developer. I was just someone who refused to stop until things worked.

Then I built my first real app — a fitness tracking platform. Physique Tracker Pro. Full stack. Vercel, DigitalOcean, Supabase, Cloudinary for image storage. I was proud of it. And then someone found a hole.

I had an unsigned upload preset on Cloudinary — meaning anyone who found the endpoint could upload files directly to my storage bucket without any authentication. No signature. No validation. No gate. Someone found it and used it to upload explicit material. Thousands of files. Nearly 20,000 unauthorized uploads sitting in my storage before we caught it.

We caught it because the storage usage spiked in a way that didn't match user activity. I pulled the logs, saw requests coming in from IPs with no corresponding user sessions, traced it back to the unsigned preset, and locked it down immediately. HMAC-SHA256 signing on every upload. Server-side only. CORS locked to explicit origins. IDOR vulnerabilities patched across every endpoint. That breach cost me nothing but time — but it could have cost everything.

I don't take shortcuts on security anymore. Every project I build starts with the security layer before any application logic gets written.

Here's what I'm building now:

**GHW Agent Portal** — A custom Medicare CRM SaaS for Gruening Health and Wealth. React 19, FastAPI, MongoDB Atlas, deployed on Vercel and Render. Multi-tenant. Magic link + TOTP MFA. 441 passing tests. Built for licensed insurance agents managing Medicare clients at scale.

**HelixOS** — A HIPAA-compliant multi-tenant genomic ordering platform. Next.js 14, Supabase, Stripe Connect, GHL API v2. Tenant-isolated. Per-tenant encryption. Built to replace a clinical platform I built for someone else and never got paid for — so I built it as my own product instead.

**CoachG Meta Tracking** — Server-side Meta CAPI attribution system for a Medicare agency coaching brand. Phases A and B live. Built so ad spend actually gets credited correctly instead of disappearing into the pixel black hole.

**FirstSource Revenue System** — GHL-based revenue execution infrastructure with equity participation. Not a CRM. A full operating system for business revenue.

I build real infrastructure for real businesses. I came from nothing in this industry and I learned everything the hard way — including what happens when you leave a door open.

Security isn't a feature I add at the end. It's the first thing I write.

---

## Discussion

**Matt Murphy** · 2026-06-22

> WOW! Tim, this is exactly the kind of story people need to hear. 👊😎
> 
> Not because of the breach, because of what you did after it.
> 
> A lot of builders learn security as a checklist. You learned it as scar tissue. That changes how you build forever.
> 
> The Cloudinary preset lesson is a perfect example of why I keep preaching the 13 layers. Most people think the app is “working” because the UI works and data moves. But production is different. Production asks:
> 
> Who can touch storage?
> Who can call this endpoint?
> What happens if this URL leaks?
> What happens if someone bypasses the front end?
> What are the logs telling us?
> 
> That’s the real shift from “I built an app” to “I operate infrastructure.”
> 
> And Marine veteran, no CS degree, no bootcamp, no traditional tech path, and that matters. Because this industry is changing fast, and a lot of serious builders are going to come from nontraditional backgrounds. The difference is not the degree. The difference is discipline, curiosity, pain tolerance, and whether you actually learn from the hits.
> 
> Security-first is not paranoia. It is professional maturity.
> 
> Glad you’re here, man. This is a very real operator stack and a very real builder story.
> 
> Honored to have you here brother! 💯👊😎 - Matt

**Travis Wagner** · 2026-06-23

> I'm on a similar but more winding path after the Marine Corps. Non-CS background and learning everything from the ground up while I'm building my company.
> 
> When did you serve, and what was your MOS? I was a 2847 (telephone & computer tech) from 2002-2007.

  ↳ **Tim Arnold** · 2026-06-23

  > 0311, 2007-2013. Miss sleeping in the dirt some days! 😂

  ↳ **Travis Wagner** · 2026-06-23

  > [Tim Arnold](https://the-faction.mn.co/members/40269725) ah you were the real deal. I was happy with my cushy POG life :P lol

  ↳ **Tim Arnold** · 2026-06-23

  > [Travis Wagner](https://the-faction.mn.co/members/40271102) LOL-Semper Fi Brotha


---
_Source: https://the-faction.mn.co/posts/103606420_
