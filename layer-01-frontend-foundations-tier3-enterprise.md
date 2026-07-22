# Layer 1 of 13 — Frontend Foundations
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Running a frontend operation at enterprise scale. At Tier 3, you're the person responsible for
the whole frontend operation — multiple teams are building different sections, there are legal
requirements, there's more than one brand or product. The job is governance: making sure the
system holds together.

**Core goal:** You can run a frontend operation at enterprise scale — overseeing multiple
teams, meeting accessibility compliance requirements, managing multiple brands from one
codebase, and running automated quality checks across the system.

---

## Key Concepts

**Micro-frontends (independent team ownership)** — Instead of one giant app, the frontend is
split into independent pieces that different teams own and deploy separately — a mall where
each store runs independently, but they all share the same hallways and parking lot.

**Advanced rendering strategies** — At scale, decisions about what the server builds vs. what
the browser builds have real cost and speed implications. You need to know enough to evaluate
these decisions, not implement them by hand, but approve or reject how AI and your engineering
team set them up.

**Automated visual testing** — A tool takes screenshots of every component and every page,
then compares them to the last version. If anything changed that wasn't supposed to, it flags
it — the safety net when AI changes break something you didn't expect.

**Accessibility compliance (legal requirement)** — Enterprise clients and government contracts
often require WCAG 2.1 AA compliance, a formal standard for making the app usable by people
with disabilities. This isn't optional at this tier — it's auditable, and there are legal
consequences for failing.

**Multi-brand theming** — One codebase serving multiple brands, different logos, colors, and
fonts, controlled by a configuration system called design tokens. AI can build this, but only if
the token system is set up correctly first.

---

## Toolkit (adds to Tier 2)

- **Chromatic** — automated visual testing; catches when AI changes break the way things look
- **axe-core + Lighthouse** — accessibility auditing tools that check the app against the WCAG standard
- **Style Dictionary** — manages design tokens (brand rules) across multiple brands from one source
- **Playwright** — end-to-end testing across different browsers, making sure the app works in Chrome, Safari, Firefox, and Edge

---

## Certification Exam Topics

- **Micro-frontend architecture** — Can you evaluate how an app should be split across teams so each team can ship independently?
- **Rendering strategy decisions** — Can you assess whether the right parts of your app are built on the server vs. the browser for cost and speed?
- **Visual regression testing** — Do you know how to set up automated screenshot comparisons that catch unexpected visual changes?
- **Accessibility compliance** — Can you audit an app against WCAG 2.1 AA requirements and identify what needs to be fixed?
- **Multi-brand theming** — Can you evaluate whether a design token system correctly supports multiple brands from one codebase?
- **Cross-team governance** — Do you know how to establish rules and review processes when multiple teams contribute to the same frontend?
- **Performance at enterprise scale** — Can you evaluate CDN setup, edge rendering, and caching strategies for high-traffic apps?
- **Safe deployment** — Do you understand feature flags, staged rollouts, and A/B testing, and why they matter when thousands of users are affected?

---

## Common Pitfalls

- Never checking the app on an actual phone — looks fine on laptop, broken on mobile, every time
- Asking AI to "build the whole page" instead of building it from smaller pieces — big prompts produce big messes
- Not setting up a folder structure before generating — AI puts files wherever it wants, and six weeks later nobody can find anything
- Skipping accessibility because AI doesn't add it unless asked — screen readers, keyboard navigation, alt text, none of it shows up automatically
- Treating AI's first output as final instead of a first draft — always review, always iterate
- Letting every page look slightly different because brand rules (colors, fonts, spacing) were never defined in one place

---

## Tier 3 Self-Assessment Checklist

- [ ] Can you describe a screen or feature to AI clearly enough that you get something usable on the first or second try?
- [ ] Have you actually opened your app on a phone (not just a laptop simulator) and confirmed it works?
- [ ] Can a user navigate your app using only a keyboard, no mouse required?
- [ ] Did you set up a consistent folder structure and naming convention before you started generating?
- [ ] If someone else looked at your app, would every page feel like it belongs to the same product?
- [ ] Have you tested your forms with empty submissions, weird characters, and very long text?
- [ ] Do you know how to open browser DevTools and check if your app is throwing errors?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's frontend and check the following. For each one, tell me pass
or fail with a specific example:
Organization: Are my components cleanly separated into their own files with
consistent naming?
Mobile: Does every screen look correct at phone size (375px wide)?
Accessibility: Does the HTML use the right elements (buttons for actions,
links for navigation)? Are images labeled? Can I tab through the whole app?
Consistency: Are colors, fonts, button sizes, and spacing the same
everywhere?
Speed: Are images optimized? Is the app loading code it doesn't need yet?
Forms: Do forms show clear error messages and keep user input on failed
submissions?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 1 certification exam at your target tier.

The best way to prepare: build something real. Pick a project, even a small one, and go
through the full loop. Describe it to AI. Check what it builds. Fix the gaps. Ship it. Pay
attention to every place you catch a mistake. Those catches are exactly what the exam tests.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
