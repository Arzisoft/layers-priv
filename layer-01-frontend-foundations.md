# Layer 1 of 13 — Frontend Foundations
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Making Your App Look Right on Every Screen*

---

## What It Covers

The visual layer users interact with. Components (LEGO blocks of UI), responsive design, Tailwind CSS consistency, accessibility, and the vibecoder loop.

**Core goal:** You can build a consistent, accessible, mobile-friendly interface by directing AI — without writing CSS from scratch.

---

## Key Concepts

**Components** — Reusable UI building blocks (button, card, form, nav). Build once, reuse everywhere. AI generates them; you verify they match your design system.

**Responsive design** — Layout adapts to screen size. Mobile-first: design for small screens, layer up. Verify on real devices, not just your laptop.

**Design system / Tailwind** — A shared visual language (colors, spacing, type). Tailwind's utility classes keep things consistent. One `primary-500` everywhere beats 40 scattered hex codes.

**Accessibility** — Alt text on images, keyboard navigation, color contrast (4.5:1 min). Screen readers must work. Non-negotiable for any real product.

**The vibecoder loop** — Describe component → AI builds it → preview in browser → give feedback → iterate. Your job is taste + direction, not handwriting CSS.

---

## Toolkit

- **Tailwind CSS** — utility-first, consistent spacing/color
- **shadcn/ui or Radix UI** — accessible component library
- **Chrome DevTools (device toolbar)** — mobile preview
- **Lighthouse (Accessibility tab)** — audit score + fixes

---

## Common Pitfalls

- Copying AI code without checking it works on mobile
- Hardcoding hex colors instead of using design tokens
- Skipping alt text ("it's just decorative")
- Building the whole page before testing one component
- Ignoring keyboard navigation — tab order, focus states

---

## Tier 1 Self-Assessment Checklist

- [ ] Can you describe a component to AI and get a usable result?
- [ ] Does your layout work on mobile, tablet, and desktop?
- [ ] Are you using a consistent color/spacing system (not random values)?
- [ ] Do all images have alt text?
- [ ] Can every interactive element be reached by keyboard?
- [ ] Have you run Lighthouse and resolved accessibility errors?
- [ ] Can you explain the difference between a component and a page?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's frontend and check the following. Pass or fail with a specific example:
1. Components: Are reusable components used consistently, or is there duplicated markup?
2. Responsive design: Does every page render correctly on mobile and desktop?
3. Design system: Is color, spacing, and typography consistent across the app?
4. Accessibility: Do all images have alt text? Can the UI be navigated by keyboard?
5. Performance: Are there large unoptimized images or unnecessary re-renders?
6. Tailwind usage: Are utility classes used consistently, or are there inline style overrides?

Give me a score out of 6 and the top 3 things to fix first.
```
