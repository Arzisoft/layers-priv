---
course: "The Foundation"
module: "Layer 1: Frontend Foundations"
lesson: "Layer 1: Frontend Foundations — Study Guide"
type: "course_lesson"
post_id: 102891465
space_id: 23777123
source: "https://the-faction.mn.co/posts/102891465"
updated: "2026-08-22T19:30:12Z"
---

# Layer 1: Frontend Foundations — Study Guide

## Layer 1: Frontend Foundations

What Your Users See and Touch

This is the study guide. Everything for Frontend Foundations is on this page — there's nothing to download.

## What This Study Guide Covers

This study guide covers Layer 1: Frontend Foundations—what your users see and touch. The frontend is your app’s screens, buttons, menus, and forms. It’s the thing people pull up on their phone or open on their laptop. When someone says “the app,” they’re talking about this.

You’re not going to write code by hand. You’re going to describe what you want to an AI coding tool—something like Cursor, Lovable, Bolt, or Claude Code—and let it build the screens for you.

Your job is to know what to ask for, check that it works, and fix what doesn’t. That’s what this certification proves you can do.

This study guide walks you through the concepts, tools, and checkpoints you need to pass the Frontend Foundations certification exam.

Tier 2 is for someone whose app is growing and needs to stay organized. Tier 3 is for someone running a platform that multiple teams build on. Start at Tier 1. You can always come back for the rest.

## Why It Matters

If your app looks broken on someone’s phone, they won’t use it. Period. They won’t complain— they’ll just close it and never come back. The frontend is the first thing people judge, and first impressions are permanent.

**Here’s the thing about AI coding tools:** they’re excellent at building things that look great on your laptop screen. But they consistently skip things you didn’t ask for—like making sure the layout works on a phone, or making sure someone can navigate your app with a keyboard. AI builds exactly what you describe. If you don’t know what to ask for, you get gaps. This study guide teaches you what to ask for.

## CERTIFICATION GOAL

You can describe what you want your app to look like, use an AI coding tool to build it, check the result on a phone and a computer, and ship something your users can actually use.

## What You Need to Know

You don’t need to memorize code. You need to understand a handful of concepts so you can describe what you want clearly and catch problems in what AI gives you back.

**How apps are organized:** Modern apps are built from components—reusable pieces like a header, a card, a form, a button. Think of them like LEGO blocks. You need to know this so you can tell AI “build me a job card component” instead of “build me the whole page,” which gives you something harder to fix.

**How layouts work on different screens:** Your AI tool uses something called responsive design to make your app look right on phones, tablets, and desktops. If you don’t check the phone version, you’ll ship something that only works on the screen you built it on.

**How styling stays consistent:** AI uses a styling system (usually Tailwind CSS) to apply colors, spacing, and fonts. You don’t need to learn Tailwind—but if your app’s buttons are three different sizes on three different pages, that’s a styling consistency problem you need to catch.

**How to check that everyone can use your app:** Accessibility means people with disabilities can use your app—screen readers work, buttons are reachable by keyboard, text has enough contrast. AI almost never adds this on its own. You have to ask for it.

**The vibecoder workflow:** Describe what you want → AI builds it → you check the output on a real phone → you tell AI what to fix → repeat until it’s right → ship it. This is the loop. Every exam question tests whether you can run this loop effectively.

## Your Toolkit

Your AI coding tool is the center of your workflow. Everything else supports it.

**AI coding tool (pick one):** Cursor, Lovable, Bolt, Claude Code, Windsurf, or whatever AI- assisted builder you prefer. This is where you’ll describe what you want and iterate on the output.

**A framework (AI picks this for you):** Your AI will likely use Next.js or SvelteKit to build your app. You don’t need to choose—just know that it’s the engine underneath the screens AI generates.

**A browser for testing:** Chrome DevTools lets you preview your app on different screen sizes without needing every device. Right-click → Inspect → toggle the device toolbar.

## Certification Exam Topics

Every exam question is scenario-based. You’ll see a situation and need to identify what’s right, what’s wrong, or what to do next. Here’s what gets tested:

**App organization:** Can you tell whether AI built your app in a clean, organized way—or dumped everything into one messy folder?

**Phone and tablet layouts:** Can you spot when your app looks right on a laptop but falls apart on a phone screen?

**Accessibility basics:** Can you identify when AI skipped things like alt text on images, keyboard navigation, or proper heading structure?

**Styling consistency:** Can you tell when your app’s buttons, colors, and spacing are inconsistent across different screens?

**Where code runs:** Do you understand the basics of why some parts of your app run on a server and some in the browser—and why it matters for speed?

**Image loading:** Can you check that images load efficiently instead of slowing down your entire app?

**Forms that work:** Can you evaluate whether a form handles mistakes gracefully—showing clear errors, not losing what the user typed?

**Your AI workflow:** Can you describe a component clearly, give AI useful feedback when the output is wrong, and iterate to a working result?

## Common Pitfalls

These are the mistakes vibecoders make most often at this layer. No judgment—they’re easy to make. But if you recognize any of them in your own workflow, fix them before sitting for the exam.

Never checking your app on an actual phone. It looks fine on your laptop. It’s broken on mobile.

Every time.

Asking AI to “build the whole page” instead of building it from smaller pieces. Big prompts produce big messes.

Not setting up a folder structure before you start generating. AI will put files wherever it wants— and six weeks later, nobody can find anything.

Skipping accessibility because AI doesn’t add it unless you ask. Screen readers, keyboard navigation, alt text—none of it shows up automatically.

Treating AI’s first output as final. It’s a first draft. Always review. Always iterate.

Letting every page look slightly different because you never defined your brand rules (colors, fonts, spacing) in one place.

## Self-Assessment Checklist

Before you take the exam, run through these questions. Every “no” is something to work on.

Can you describe a screen or feature to AI clearly enough that you get something usable on the first or second try?

Have you actually opened your app on a phone (not just a laptop simulator) and confirmed it works?

Can a user navigate your app using only a keyboard—no mouse required?

Did you set up a consistent folder structure and naming convention before you started generating?

If someone else looked at your app, would every page feel like it belongs to the same product?

Have you tested your forms with empty submissions, weird characters, and very long text?

Do you know how to open browser DevTools and check if your app is throwing errors?

## AI Audit Prompt Template

Copy this prompt into your AI coding tool to get a quick health check on your frontend. It checks the same things the certification exam covers.

> Review my app’s frontend and check the following. For each one, tell me pass or fail with a specific example:
>
>
>
> Organization: Are my components cleanly separated into their own files with consistent naming?
>
>
>
> Mobile: Does every screen look correct at phone size (375px wide)?
>
>
>
> Accessibility: Does the HTML use the right elements (buttons for actions, links for navigation)? Are images labeled? Can I tab through the whole app?
>
>
>
> Consistency: Are colors, fonts, button sizes, and spacing the same everywhere?
>
>
>
> Speed: Are images optimized? Is the app loading code it doesn’t need yet?
>
>
>
> Forms: Do forms show clear error messages and keep user input on failed submissions?
>
>
>
> Give me an overall score out of 6 and list the top 3 things to fix first.

## What’s Next

Once you’ve gone through this study guide and can answer “yes” to the self-assessment checklist, you’re ready for the Layer 1 certification exam at your target tier.

The best way to prepare: build something real. Pick a project—even a small one—and go through the full loop. Describe it to AI. Check what it builds.

Fix the gaps. Ship it. Pay attention to every place you catch a mistake.

Those catches are exactly what the exam tests.

## Certification Pathway

Associate Builder: Pass all 13 layers at Tier 1 Certified Builder: Pass all 13 layers at Tier 1 + Tier 2 MADE Certified: Pass all 39 tier exams + capstone project Each exam requires 80% to pass. You can retake after a 24-hour cooldown. No rush—take the time to build something real first.

———

Ready? Take the [Frontend Foundations Exam →](https://the-faction.mn.co/posts/the-foundation-layer-1-frontend-foundations-exam)

---

## Discussion

**Awie Hoh** · 2026-07-01

> This is my own take on Layer 1:
> 
> **01. Frontend**
> 
> **Purpose**
> 
> Build a clean, calm, consistent, accessible, responsive UI that matches the approved design. No drift.
> 
> **Principle**
> 
> Product discipline in the Apple/Jobs tradition — simplicity, clarity, restraint, consistency, polish. Remove the unnecessary. Make what remains feel obvious and refined. Respect the user's attention.
> 
> **Source of truth**
> 
> The approved design is the reference. Match it, or document why a difference is intentional.
> 
> **Consistency**
> 
> Reuse existing components, tokens, and patterns. Don't invent one-off colors, fonts, spacing, buttons, shadows, radii, icons, or layouts when a standard exists. Interactive states stay consistent.
> 
> **Quality**
> 
> Every screen must feel intentional. Alignment, spacing, hierarchy, contrast, typography, and motion must be clean — never random, crowded, or noisy.
> 
> **UX**
> 
> Every screen makes the next step obvious. Flows are simple, complete, and free of dead ends. Use clear labels and human language; hide internal system terms. Primary actions are easy to find; secondary actions don't compete. Every action gives feedback — one of: loading, success, error, disabled, empty, permission-denied. Users always know where they are, what happened, what to do next, and how to go back. Destructive actions need confirmation, undo, or a clear recovery path. Never make users redo work after an error, refresh, or wrong turn. Cut unnecessary steps, fields, and clicks.
> 
> **Resilience**
> 
> A single broken component must not crash the whole screen. Failures degrade gracefully into a recoverable state, never a blank page.
> 
> **Organization**
> 
> Separate components into clear, well-named files. Keep shared components reusable; keep page-specific ones near their page. Avoid giant files, mixed responsibilities, and duplicates.
> 
> **Mobile**
> 
> Every screen works at all supported sizes down to 375px. No unintended horizontal scroll. Text stays readable; targets stay tappable. Forms, modals, menus, tables, cards, and navigation stay usable.
> 
> **Accessibility**
> 
> Buttons for actions, links for navigation. Clear page structure. Label meaningful images and all form fields. Support keyboard navigation with logical tab order and visible focus. Never rely on color alone.
> 
> **Forms**
> 
> Show clear errors and how to fix them. Keep input after a failed submit. Handle its states (loading, success, empty, error). Prevent double submission.
> 
> **Speed**
> 
> Optimize images. Load only the code needed now. Remove unused components, libraries, and dead code. Split large pages when it helps. Avoid unnecessary re-renders.
> 
> **Security boundary**
> 
> The frontend renders the interface — it is not a security layer (Principle 4). Its checks may hide, disable, or guide, but must never be trusted as protection. Never expose secrets, keys, admin tokens, or credentials. Never treat hidden buttons, pages, or routes as secure. All protected actions and private data are enforced by Backend/API (#2), Auth & Permissions (#4), and Security & RLS (#8), reached only through approved access paths.
> 
> SHIP GATE — do not ship unless all are true
> 
> ☐ Matches the approved design; differences documented
> 
> ☐ Reuses the design system; no unjustified one-offs
> 
> ☐ Works to 375px with no unintended horizontal scroll
> 
> ☐ Accessible: keyboard, focus, labels, structure, not color-alone
> 
> ☐ Forms keep input on failure and block double-submit
> 
> ☐ Broken components fail gracefully, not blank
> 
> ☐ No secrets, keys, or credentials in the frontend
> 
> ☐ Feels simple and polished (reviewed by an AI from a different model family than the one that built it, or by a person)

**Ayam Samuel** · 2026-07-05

> Great guide to start with, I ran the audit and realised some accessibity gap on a client website I built with claude code.

  ↳ **Matt Murphy** · 2026-07-05

  > I’m very glad that you found it helpful so early in the process trust me as we continue to move through the various layers and tears and additional courses that we’re adding your confidence is going to continue to grow. We’re happy you’re here.👊😎

**Shaf Cangil** · 2026-07-17

> Sorry. But I'm going to be the fly on the ointment. This interface right here? It's not intuitive. I've been pressing everything and there's delays and pdfs with incredibly small text to read through... is this a test? We're going to learn about the front end design but I can't even navigate this on my Samsung screen.

  ↳ **Matt Murphy** · 2026-07-17

  > Shaf- You’re no fly in the ointment, thank you so much in fact. We’re currently in our beta phase and all feedback is awesome feedback and I can assure you that your feedback is going to improve the whole community! And by the way, You’re right, and I appreciate you saying it directly. The study materials were built with laptop users in mind, and that’s a gap we need to close. The exams should work on your phone, but the study guides as downloadable PDFs are not a great mobile experience. We’re working on converting the study guide content to display directly inside the lesson so it reads properly on any screen size without downloading anything. I’ll keep you posted as we roll that out. In the meantime, if you’re hitting a wall on a specific module, let me know which one and I’ll make sure you have what you need to get through it. - Matt

  ↳ **Shaf Cangil** · 2026-07-19

  > Hi Matt. Thx. You best know I'm probably on the spectrum (my daughter is autistic but I've never been tested) and I've often been told I'm abrupt and intimidating, but I don't mean to be. It was a genuine observation. I'm more front end and tend to obsess over tiny things. Lol. I'm glad you didn't get offended.

  ↳ **Matt Murphy** · 2026-07-19

  > [Shaf Cangil](https://the-faction.mn.co/members/40648972) do not ever apologize for being awesome, your obsession on my tiny things made me obsess about my tiny things and I think big things are coming lol!

**Louis Maxwell** · 2026-07-18

> Greatfull for organising and taking your valuable time to setting this up.

**Imroz ** · 2026-07-26

> Man can't put into words how great these guides are.

**Barbara Lopes Garcia Van Meter** · 2026-07-30

> I have to say, I read only the beginning and I am impressed. Matt, I started following you a few months ago when I was building my first try on an idea of an app (I ended up changing my mind about it and abandoning it). I love your videos and even though I am not a developer and English is not my first language, I feel like you are great at explaining things. I am starting a new project and now I feel like I found the place where I can ask questions and have a straightforward guide to make sure everything runs smoothly. Thanks again! 😁

  ↳ **Matt Murphy** · 2026-07-30

  > Barbara, thank you for saying that, and welcome. I’m glad the material is giving you a clearer path this time around and I'm honored to have you here.
  > 
  > Changing direction and abandoning a first build isn’t failure, it’s actually a healthy part of the builder journey. Most of us have at least one, or a dozen, projects that taught us exactly what not to do before we finally learned how to build with structure and confidence.
  > 
  > And don’t worry about not being a developer or English not being your first language. You already have the most important part: a real idea, the willingness to learn, and the courage to start again. The tools can help with the code and the language. Our job here is to help you understand the decisions underneath so the system actually works.
  > 
  > Take the Foundations one layer at a time, ask every question that comes up, and share the new project as it develops. You’re absolutely in the right place, and I’m excited to see what you build this time. 👊😎

  ↳ **Barbara Lopes Garcia Van Meter** · 2026-07-30

  > Thanks Matt!

**Tareq Dheeb** · 2026-07-31

> Hey Matt. This is my first hour here, and I'm really impressed with what I've read. I'm an old-fashioned developer 😁, and I'm trying to understand how vibe coding works and how AI can help me improve. Up until now, I've been enjoying your Instagram reels. But after joining the Faction, reading the first guide, and running the audit on a small AI project I'm building, I realized how many gaps there were in my workflow. I'm already working on fixing them.
> 
> Thank you for this opportunity. I really appreciate it!

  ↳ **Matt Murphy** · 2026-07-31

  > Tareq, welcome to The Faction!!! I love that you ran the audit in your first hour.
  > 
  > Being an “old-fashioned developer” is actually a serious advantage here, trust me. You already understand structure, logic, debugging, and why shortcuts eventually become production problems. AI doesn’t replace that experience instead it gives you leverage. The real shift is learning how to direct the build, inspect what comes back, and catch the gaps before they become expensive.
  > 
  > The fact that the first guide immediately exposed weaknesses in your workflow is a win, not a criticism of what you’ve built.
  > 
  > I have a feeling you’re going to move quickly once your engineering instincts and the AI-directed workflow fully connect. Really glad you’re here, brother. 👊😎

**David Viard** · 2026-08-04

> Matt , got 24 out 25…
> Question 14 of 25
> 
> You built your app for three weeks in Chrome on your MacBook, never checking on a phone. Half the pages are broken on iPhone — buttons stacked, text off-screen. What pitfall is this?
> 
> Two answers are valid since you mention "testing on devices" in the 'wrong' answer.
> It should be correct, mobile is a device ;-) … just saying. I assumed it was the most correct since the second implied a complete breakage and failure to test during dev. it contradicts the initial question. confusing.
> 
> My 2 cents…😅

  ↳ **Matt Murphy** · 2026-08-04

  > David, 24 out of 25, and the one you "missed" may be ours, not yours. Good catch. Our apologies.
  > 
  > Here's the problem you found. The scenario itself says the builder never checked on a phone, that's a fact I put in the stem. So an option about testing on devices isn't a wrong answer sitting there to be ruled out. It's restating something the scenario already told you happened. A distractor has to be wrong. That one isn't.
  > 
  > The fix is on the answer, not the question. I'm rewriting that option so it names a genuinely different pitfall, one the scenario sets up but that isn't the actual failure here, so there's exactly one defensible answer. The stem stays as written; it's doing its job.
  > 
  > Two cents well spent. Thank you.

**Hammad Ur Rehman** · 2026-08-14

> If I didn't followed you, I bet I can't learn these edges at 3rd semester.But we have to do less vibe code because when I sit to write code by hand I get irritated for not making the logic for a function to perform

**Krisztián Szűcs-Szabó** · 2026-08-22

> Hi Matt :) I am from Hungary. I first saw you in Facebook and you were the first where I realised It's serious and interesting and not just that millionth how to be millionaire guy in the internet.
> I am not a developer just an experineced user. We just started a small bussiness with my wife and want to optimize and automatize everything possible to support our daily processes. I started with python codes, apis and dashboards. I love vibe coding I know I can realize what I planned, its a whole new world to me.. But you add me the frame to do it properly. I am glad to be here :)

  ↳ **Matt Murphy** · 2026-08-22

  > Happy to have you here and I’m excited for your builds come to life in your small business.
  > 
  > And there’s such a huge advantage of starting a small business from scratch using AI from day one versus having to migrate legacy technology to the newest AI functionality. Focus on the foundational operational processes getting everything plugged into a single source of truth, QA loops, CRM, EMAIL, all comms, all customer nurture, and all the things the business is going to need centralize from day one.
  > 
  > You should check out my free book and the various free small business operator DIY kits I have on my website, they might prove useful.


---
_Source: https://the-faction.mn.co/posts/102891465_
