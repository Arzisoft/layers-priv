# Layer 1 of 13 — Frontend Foundations
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Keeping a growing app consistent and fast as more people work on it and the codebase gets
bigger. The challenge shifts from "can you ship?" to "can you keep things organized and fast
as you scale?"

**Core goal:** You can maintain a design system, monitor performance, and manage complexity
as your team and codebase grow.

---

## Key Concepts

**Design systems** — A shared set of rules (brand colors, font sizes, button styles, spacing)
documented in one place. Without one, every AI session generates slightly different-looking
components and the app starts looking like a ransom note.

**Component testing in isolation** — Storybook lets you view and test individual components
(a button, a card, a form) by themselves, outside the full app — a showroom for building
blocks before they go into the finished product.

**Performance monitoring** — Core Web Vitals measure how fast the app loads and how smooth
it feels. Google uses these to rank a site, and users feel them every visit; know whether the
numbers are good or bad.

**State management** — State is the app's memory (logged-in user, cart contents, selected
tab). AI often manages this messily; at Tier 2 you need to know when AI's approach will break
as the app grows.

**Multiple languages (i18n)** — If the app serves users in more than one language, it needs
internationalization — a system for swapping text based on the user's language. AI can build
it, but only if asked up front.

---

## Toolkit (adds to Tier 1)

- **Storybook** — build and test components in isolation before they go into the app
- **Design token tools (Figma, Style Dictionary)** — maintain brand rules in one place AI can reference
- **Lighthouse CI** — automated performance checks that run every time you ship
- **State management libraries (Zustand, TanStack Query)** — you direct which approach to use

---

## Common Pitfalls

- Never checking the app on an actual phone — looks fine on laptop, broken on mobile, every time
- Asking AI to "build the whole page" instead of smaller pieces — big prompts produce big messes
- No folder structure defined before generating — AI puts files wherever it wants
- Skipping accessibility because AI doesn't add it unless asked
- Treating AI's first output as final instead of a first draft
- Letting every page look slightly different because brand rules were never defined in one place

---

## Tier 2 Self-Assessment Checklist

- [ ] Can you describe a screen/feature to AI and get something usable in 1-2 tries?
- [ ] Have you opened the app on an actual phone (not a laptop simulator)?
- [ ] Can a user navigate the app with only a keyboard?
- [ ] Did you set a consistent folder structure/naming convention before generating?
- [ ] Would every page feel like it belongs to the same product?
- [ ] Have you tested forms with empty submissions, weird characters, very long text?
- [ ] Do you know how to check browser DevTools for thrown errors?

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
Consistency: Are colors, fonts, button sizes, and spacing the same everywhere?
Speed: Are images optimized? Is the app loading code it doesn't need yet?
Forms: Do forms show clear error messages and keep user input on failed
submissions?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
