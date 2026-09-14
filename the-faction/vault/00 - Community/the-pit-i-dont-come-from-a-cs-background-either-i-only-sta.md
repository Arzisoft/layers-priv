---
space: "The Pit"
author: "Awie Hoh"
post_id: 103848238
reactions: 2
comments: 3
published: "2026-06-28T03:00:23Z"
source: "https://the-faction.mn.co/posts/103848238"
---

# I don’t come from a CS background either. I only started experimenting with AI t

I don’t come from a CS background either. I only started experimenting with AI tools earlier this year, after seeing a clip of Jensen Huang talking about how AI might change the need for traditional coding.

I’m currently building three private/internal apps with AI for workflows where spreadsheets and generic apps aren’t specific enough. Alongside them, I’m also building a structured workflow for directing AI on my own projects, with the goal of getting more reliable output than ad-hoc vibe coding.

All of the stack choices below were AI-suggested.

1. Restaurant finance & operations dashboard

For my restaurant. It automatically reconciles POS sales, bank deposits, card and QR payments, delivery-platform payouts, fees, raw-material usage, and weekly inventory — then flags mismatches that could mean timing issues, platform errors, staff mistakes, or fraud.

The tricky part is timing: my business day runs from morning to the next morning, while banks, POS, payment providers, and delivery platforms all report on different schedules.

**Stack:** Python, FastAPI + Uvicorn, Jinja2 HTML, HTMX, plain JS, SQLite, IMAP email parsing, pdfplumber + Tesseract OCR, openpyxl, Claude API for receipt extraction. Runs locally on my Mac with launchd + APScheduler; Tailscale for private phone access.

2. Private personal finance app

For my own money. It semi-automatically tracks income and expenses by treating my bank statements as the source of truth, because manual entries drift and generic apps don’t fit my real cases.

It handles accounts, categories, recurring items, and reconciliation against bank/card activity — plus a two-way personal loan ledger for informal borrowing/lending with friends: who owes whom, outstanding balances, partial repayments, repayment history, and whether repayments match actual bank activity.

Most money apps can record a transfer, but they don’t usually model that full IOU lifecycle.

**Stack:** Python, FastAPI + Uvicorn, Jinja2 HTML, plain CSS/JS, SQLite, PDF statement parsing with pdfplumber / pdfminer.six / pypdfium2, password + session + CSRF auth with secrets in the macOS Keychain, Pydantic + pytest. Runs locally on my Mac, loopback-only; Tailscale for phone access.

3. Attendance & payroll system

For a business with mobile/on-site employees. They check in from their phones with GPS and a selfie that’s checked on-device for a clear, present face, since many work outside the office.

The admin side handles device binding, lateness, overtime, leave, sick days, missing punches, field work, and payroll rules.

The hard part isn’t the check-in button — it’s encoding the company’s real payroll rules without creating loopholes or constant manual cleanup.

**Stack:** Flutter/Dart Android app for employees, Riverpod, go_router, geolocator, on-device face-presence + quality check via ONNX Runtime using the YuNet face-detection model. Admin dashboard in SvelteKit + Svelte 5 + TypeScript + Tailwind + Leaflet. Backend, database, and auth on Supabase: Postgres, Auth, row-level security, and Storage. Employee APK + admin hosted on Vercel.

4. The workflow I built for myself as a non-coder

A lot of my earlier AI-built software attempts failed because I was trying to build complex, interconnected business logic without enough structure around specs, planning, tests, and review.

Features could be built quickly, but the apps became fragile: one flow would work, another would break, and fixes in one area sometimes created new problems elsewhere.

That pushed me to develop a stricter AI-assisted build process. I call it Code-X, and I’ve made the workflow open here:

[https://github.com/1984-alt/code-x](https://github.com/1984-alt/code-x)

The goal is to make AI-assisted building more controlled and repeatable for someone like me, who can’t personally audit or debug the code line by line.

The process separates planning, building, and fixing:

**Planning:** define business rules, source-of-truth data, expected behavior, edge cases, and scope boundaries.

**Building:** work in small, controlled work-orders instead of broad feature prompts.

**Fixing:** identify the failure mode, fix the root cause, and update the process so the same class of mistake is less likely to happen again.

Roughly: **plan the truth → build one slice → test against real cases → review the evidence → fix the root cause → improve the process → next slice**

The main safeguard is that the plan gets locked first. I review it as a visual Master Blueprint, then the AI builds one small work-order at a time. A deterministic checker — not another AI — blocks dropped requirements, and each module gets a second AI review before moving forward.

Everything in Code-X came from a real failure I hit while building these apps. Each safeguard exists because something already broke once.

That said, I’m not a software engineer, so I’m sure parts could be done more cleanly with standard tools or better-known patterns. I’d really value feedback from professional engineers or experienced AI builders — especially where a cleaner, more proven approach could give the same protection or better results.

With your permission [Matt Murphy](https://the-faction.mn.co/members/39706849) , I also plan to implement the 13 things I’ve just finished learning in the T1 Foundation into this workflow too.

---

## Discussion

**Matt Murphy** · 2026-06-28

> Awie, this is a proper builder journey right here, wow.
> 
> You started with AI tools this year and now you’re building real internal systems for restaurant finance, personal finance, attendance, payroll, reconciliation, OCR, local access, Supabase, RLS, mobile check-ins, and your own AI-assisted build process.
> 
> That is not “just experimenting.” That’s real reps under pressure.
> 
> And I’m genuinely flattered that you want to fold the T1 Foundation work into Code-X. Absolutely, use what you’re learning here. That’s the point. Take the 13 layers, the questions, the checks, the structure, and make your system stronger.
> 
> I’m also curious if you’ve read *Not Murphy’s Law* yet, because a lot of what you’re describing lands right in that zone: the difference between being a business operator trying to solve real workflow problems and becoming the systems-minded builder who can turn those problems into repeatable infrastructure.
> 
> That’s the shift.
> 
> What I like most is that your apps are coming from real pain. Spreadsheets were not enough. Generic apps did not match the business rules. So you started building systems around the actual workflow. That’s the path right there bro.
> 
> Also, some of what you’re building is very relevant to conversations we’re having in our own business and with clients. Restaurant ops, reconciliation, attendance, payroll, messy real-world workflows, those are not toy problems. There is real demand for better systems in those spaces.
> 
> Code-X is interesting because you’re building your own conveyor belt: planning, building, fixing, reviewing, locked blueprint, small work orders, deterministic checks, second AI review.
> 
> That is exactly how small businesses are going to turn AI output into reliable software.
> 
> Not “let the robot freestyle until something works.”
> 
> More like: define the rules, build one slice, test against real cases, fix the root cause, improve the process, then move to the next slice.
> 
> That’s where the muscle memory builds.
> 
> Keep sharing this. I’m very interested to watch how this progresses. This is the kind of process the whole room can learn from. 👊😎

**Awie Hoh** · 2026-06-29

> They're all still (frustrating) works in progress. 😅
> Plenty of new unforeseen problems propping up.
> 
> I'm still trying to figure out how to make them work properly for just 1 user (myself), and if I can't make things work even for myself, I dont have any confidence to build for others. Still have plenty to learn from and am not trying to get overwhelmed by everything.
> 
> Thanks for all your words of encouragement!

  ↳ **Matt Murphy** · 2026-06-29

  > Just happy to have you here, keep learning, keep building, keep breaking, 💯👊😎


---
_Source: https://the-faction.mn.co/posts/103848238_
