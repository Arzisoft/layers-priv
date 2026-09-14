---
space: "The Pit"
author: "Matt Murphy"
post_id: 103506415
reactions: 1
comments: 21
published: "2026-06-19T23:56:43Z"
source: "https://the-faction.mn.co/posts/103506415"
---

# Alright — what are you building right now? Not your big vision. Not your five-ye

Alright — what are you building right now? Not your big vision. Not your five-year plan. What did you actually work on today or this week? Drop it below. One sentence is fine. I'll go first: I rebuilt an entire client intake pipeline this morning using Claude Code. Took 40 minutes. Would've been a two-week dev cycle six months ago.

---

## Discussion

**Wynand Coreejes** · 2026-07-09

> Fleet KM Dashboard.
> 
> A daily fleet odometer dashboard that pulls distance readings for a fleet of 130 Heavy Transport Vehicles from four telematics platforms into one view. React + Vite on the front, Azure Functions on the back, Table Storage for data and Azure Communication Services for the mail-out. The whole thing lives on Azure Static Web Apps, auto-deployed from GitHub. all done with Claude Code

  ↳ **Efrain Gonzalez** · 2026-07-09

  > Nice!

  ↳ **Matt Murphy** · 2026-07-09

  > Wynand, this one hits a soft spot for me. 👊
  > 
  > I’ve spent a lot of the last decade around mobility, logistics tracking, telematics, autonomous trucking, and fleet infrastructure work including time on Deloitte’s Mobility 2035 board working and building in the mobility space.
  > 
  > So anytime I see somebody pulling messy fleet data out of multiple telematics systems and turning it into one clean operating view, I’m immediately interested.
  > 
  > 130 heavy transport vehicles, four telematics platforms, Azure Functions, Table Storage, Azure Communication Services, Static Web Apps, GitHub deploys, Claude Code helping stitch it together, that’s a very real operator build.
  > 
  > The big win here is not “dashboard.” It’s normalization.
  > 
  > Different systems, different data shapes, different update rhythms, different odometer readings, one view the business can actually use.
  > 
  > That’s where the value is.
  > 
  > This is exactly the kind of thing AI can help accelerate, but the judgment still comes from understanding the business workflow underneath it. That’s the path right there bro. 👊😎
  > 
  > [https://www.avvamobility.com/](https://www.avvamobility.com/)
  > 
  > [https://deloitte.wsj.com/cmo/the-future-of-mobility-consumers-consider-car-subscription-services-f13367a2](https://deloitte.wsj.com/cmo/the-future-of-mobility-consumers-consider-car-subscription-services-f13367a2)

  ↳ **Wynand Coreejes** · 2026-07-10

  > [Matt Murphy](https://the-faction.mn.co/members/39706849) WOW!!! this is impressive!!! You have really gone the distance on AVVA, and thanks for the reply Matt👊💯

  ↳ **Matt Murphy** · 2026-07-10

  > [Wynand Coreejes](https://the-faction.mn.co/members/40268131) like I said, I have a thing for mobility projects, in fact, Deloitte is shipping me off to a keynote in Detroit next month to meet with manufacturers about telematics best practices in captive finance.

**Efrain Gonzalez** · 2026-07-09

> I built a ID Card creating software. Took me 2 days, now tightening it up so there are no loose ends. It connects to my patient (read only) DB via ODBC to pull Basic info for the cards, creates barcode, puts basic info , photo, prints card. I am also using it to connect to UKG via API to pull employee info also for ID Cards. It has a manual "fallback" for cases where there is no db connection and a manual card needs to be done. Saves all created cards. Checks for duplicates, role based access (tested), ... still working on it checking for bugs but it ended up as a pretty solid piece. Having fun with it!

  ↳ **Matt Murphy** · 2026-07-09

  > Efrain, this is a proper internal-tools build. Well Done!!!
  > 
  > And honestly, those are some of my favorite builds because they solve the annoying operational mess that nobody wants to deal with manually. I love bizOps solutions.
  > 
  > ID cards sound simple until you start dealing with patient data, employee records, barcodes, photos, printing, fallback logic, duplicate checks, role access, read-only database connections, API pulls, manual exceptions, and “why did this one card not generate?” moments.
  > 
  > That’s where a two-day build can quietly turn into a real business system lol.
  > 
  > I like that you’re already thinking about loose ends, fallback paths, duplicate checks, and role-based access. That’s the difference between “it makes a card” and “the business can trust this workflow.”
  > 
  > Good build. Very practical. Very real. That’s exactly the kind of thing AI-Directed Engineering is great for when you keep tightening the process as you go. 👊😎

  ↳ **Efrain Gonzalez** · 2026-07-09

  > [Matt Murphy](https://the-faction.mn.co/members/39706849) thanks to you! It prints the cards!!

  ↳ **Matt Murphy** · 2026-07-09

  > [Efrain Gonzalez](https://the-faction.mn.co/members/40272248)I love that!!!

  ↳ **Efrain Gonzalez** · 2026-07-10

  > [Matt Murphy](https://the-faction.mn.co/members/39706849) ive just added a photo edit Api. I noticed many id photos were very incredibly wrongly taken... now they can edit the picture, zoom, rotate, crop, place correctly on a placeholder with a face/shoulder guide in the center so they make it a decent id photo. Foto edit doesnt let ussr of HR see ids from patients, clinical record personnel cant see/edit employee id/photo. Tomorrow we will be running a real world test with HR... wish me luck!
  > All responsive, tested on desktop, ipad, iphone, android... just the way you taught us!!

  ↳ **Matt Murphy** · 2026-07-10

  > [Efrain Gonzalez](https://the-faction.mn.co/members/40272248) I can’t help but laugh, most people would universally vote that the worst picture they have is their work ID and drivers license, so it’s a legitimate monetization opportunity. Well done, keep building!

**Rob Smith** · 2026-07-14

> I just finished smoke testing all my platform pricing backend - credits, subscriptions, stripe, dunning.

  ↳ **Matt Murphy** · 2026-07-14

  > Sweet, how'd it go?

  ↳ **Rob Smith** · 2026-07-14

  > [Matt Murphy](https://the-faction.mn.co/members/39706849) very interesting process to go through without a front end wired up yet. The AI wired up temp frontend windows, caught many bugs inc. gst tax calculation accuracy relevant here in AU.

**Tim Arnold** · 2026-07-14

> Over the last two days, we finished building a new security logging system for the portal that automatically records important events — like when someone tries to access something they're not allowed to, or when a login check fails so we have a clear compliance trail if anything ever needs to be reviewed. We also built an admin screen where Matt or Chase could look through these security records and export them to a spreadsheet, and we tested everything thoroughly (over 800 tests passing) to make sure nothing broke; the only things left are a final walkthrough and getting it moved from our testing environment onto the live site.

  ↳ **Matt Murphy** · 2026-07-14

  > I like where you're going with this big dog, that sounds really good and I have a couple use cases that could likely use functionality like that so I'm paying close attention 👊😎

**Efrain Gonzalez** · 2026-07-17

> Approx three months back i started a ERP Suite project for the company. I am now in the testing phase running real transactions in parallel to the existing method. Yes, the project is very ambitious, pretty big, very risky. That is why i am tweaking EVERYTHING, tightening "screws", quad checking all those security points we've learned here. The app includes everything from purchase requests to utilization, receiving, GS1 compliant barcodes (and scanning) for shipping and receiving, warehouse management, asset management, KPI Dashboards, Audit, Financials, Reports, imports and exports... mobile friendly, responsive, RBAC, many more. It is a huge project. Thanks to [Matt Murphy](https://the-faction.mn.co/members/39706849) for all his guidance and teachings i have been able to go from a dream, to a very powerful tool the company now has all eyes put on. Next is continue testing, move to full productuon, support, uodatws,... later ads a ANSI-X12 Module for electronic Purchase and Receiving.... who knows what this will grow into!! Thanks Matt!!

  ↳ **Matt Murphy** · 2026-07-17

  > Efrain, this is incredible to watch. I'm really blown away and excited by your progress on this project! Three months ago this was an idea, now you're running real transactions in parallel with your existing ERP. That's a massive milestone. THAT'S A WIN!
  > 
  > What I love most is your mindset. You're not rushing to production because it "works." You're hardening it, validating every security layer, tightening RBAC, and building confidence before flipping the switch. That's exactly how enterprise software gets built.
  > 
  > An ERP touches the heart of a business in ways many can't comprehend, so taking the time to get purchasing, inventory, financials, auditing, reporting, and permissions right will pay dividends for years. Keep stacking those wins one layer at a time.
  > 
  > Really proud of what you've built, brother, and you should be too. Can't wait to see the day you retire the old system for good. 👊😎🚀

**Efrain Gonzalez** · 2026-07-26

> As i mentioned some days back, im working a ERP software that is being tested as i write. [Matt Murphy](https://the-faction.mn.co/members/39706849) posted a note about hippaa compliance which made me think ... am i in compliance with whatever governing rules on purchase/inventory/financials data? Internet search is more confusing than helping. Does anyone care to point me into the right direction so i can make sure i comply with governing rules? Many of the security aspects we talk about here are already in place but you can never be too sure and/or "cocky" about it. Corporate financials is not a kids game.

  ↳ **Matt Murphy** · 2026-07-26

  > Brother, this is exactly the right question to be asking *before* you go into production.
  > 
  > One thing to keep in mind is that "compliance" isn't usually one thing, it's a collection of requirements based on the type of data you're handling, where your customers are located, and the industries you serve, so you're doing the right thing right now.
  > 
  > For an ERP, I'd start by mapping your application into domains:
  > 
  > • Financial records and accounting requirements
  > • Privacy regulations for any personal information (employees, vendors, customers)
  > • Security controls around authentication, RBAC, encryption, logging, and audit trails
  > • Industry-specific regulations if you serve regulated sectors like healthcare, defense, or government.
  > 
  > The good news is that the security work you've already been doing including least privilege, audit logs, encryption, testing, RBAC, is foundational across almost every framework. Compliance is often about proving you consistently do those things.
  > 
  > My advice would be to identify the first customer profile you're targeting and work backward from *their* regulatory requirements rather than trying to become compliant with every framework at once. That's a much more manageable path. Direct your AI to research your exact industry and use case for your specific compliance needs document.
  > 
  > Keep us posted on what you uncover, I think a lot of people here can learn from your journey. 👊😎

  ↳ **Efrain Gonzalez** · 2026-07-26

  > Working on it. Thanks [Matt Murphy](https://the-faction.mn.co/members/39706849) !


---
_Source: https://the-faction.mn.co/posts/103506415_
