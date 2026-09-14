---
space: "The Mentoring Lounge"
author: "Wynand Coreejes"
post_id: 104373849
reactions: 2
comments: 1
published: "2026-07-09T19:48:41Z"
source: "https://the-faction.mn.co/posts/104373849"
---

# I hope this is the right place to ask advice I'm busy building this Fleet KM Das

I hope this is the right place to ask advice

I'm busy building this Fleet KM Dashboard, A daily fleet odometer dashboard that pulls distance readings for a fleet of 130 Heavy Transport Vehicles from four telematics platforms into one view. React + Vite on the front, Azure Functions on the back, Table Storage for data and Azure Communication Services for the mail-out. The whole thing lives on Azure Static Web Apps, auto-deployed from GitHub.

The good stuff is working. There's a daily ingest that fires at midnight SAST, stores each platform's reading separately, purges anything past a 60-day retention window, and emails the report to all recipients with the CSV attached. The bit I'm chuffed with is the **Platform comparison** view: one row per fleet number, every platform's odo side by side, and a difference column (highest − lowest) — so 0 means all four sites agree, and anything else is the km gap to go chase.

Reconciliation is the real headache. Four providers, four ways of reading the same truck, and they don't sample at the same time, so a non-zero difference isn't always a fault — sometimes it's just timing. Trying to work out how to flag a *real* discrepancy vs normal drift without drowning ops in false alarms. Also had a lekker time discovering the Function App runs in UTC and you must *not* set WEBSITE_TIME_ZONE or the timer goes haywire.

If anyone's done multi-source telematics reconciliation, I'd love to hear how you drew the line on "close enough."

---

## Discussion

**Matt Murphy** · 2026-07-09

> Wynand, yep this is exactly the right place to ask. I just replied to your other post about this topic but I'm excited to see it taken a step further here.
> 
> And you already identified the real problem: reconciliation, not the dashboard.
> 
> Four telematics providers means four clocks, four data models, four sampling patterns, four definitions of “current,” and four different ways to make you question your life choices. Been threre done that, not to mention asset latency, driver interference, and all the other fun nuances of mobility solutions.
> 
> I’d avoid treating every mismatch as an error. You probably need tolerance bands.
> 
> Something like this worked for my teams:
> 
> 0 km difference = clean
> small difference = normal drift
> medium difference = review
> large difference = chase it
> missing/stale reading = separate alert category
> 
> The key is to classify the gap, not just detect it.
> 
> For fleet odometer data, “close enough” usually needs to be business-defined, not purely technical. The ops team probably knows what kind of variance is normal between providers based on timing, signal delay, ignition cycles, manual updates, or platform sync behavior.
> 
> So what worked for us was to start by capturing a week or two of differences, then build your rules from the actual pattern:
> 
> same truck
> same day
> all four readings
> highest-lowest delta
> provider timestamp
> provider freshness
> historical average gap
> outlier provider
> 
> Then your dashboard can say, “this looks like normal drift” versus “this provider is stale” versus “this truck needs attention.”
> 
> That’s the path right there bro. You’re moving from “show the data” to “make the data operationally useful,” and that’s where the real value is. GAME ON!!!


---
_Source: https://the-faction.mn.co/posts/104373849_
