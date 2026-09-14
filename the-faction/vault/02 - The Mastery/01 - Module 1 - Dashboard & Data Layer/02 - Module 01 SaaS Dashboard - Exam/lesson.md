---
course: "The Mastery"
module: "Module 1 — Dashboard & Data Layer"
lesson: "Module 01: SaaS Dashboard — Exam"
type: "course_quiz"
post_id: 103821095
space_id: 24191170
source: "https://the-faction.mn.co/posts/103821095"
updated: "2026-08-21T14:31:16Z"
---

# Module 01: SaaS Dashboard — Exam

> Exam for **Module 1 — Dashboard & Data Layer** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI tool built a SaaS dashboard as one massive component with sidebar, top bar, charts, billing, and team list in a single file. What is the problem?

- **A.** One file means updating the sidebar risks breaking the chart, billing section, and team list  ✅
- **B.** Single-file dashboards load faster since there's only one network request to the server
- **C.** The AI tool doesn't support building multi-file component projects for SaaS dashboards
- **D.** The combined file will be too large for the browser to parse and render on most devices

> **Answer:** A

### Q2. Your SaaS has Free, Pro, and Enterprise plans. Team Management is Pro+ only but the tab is visible to all users and shows upgrade to access on click. What is wrong?

- **A.** Showing locked features is helpful — it motivates free users to upgrade their plan
- **B.** Conditionally render the tab based on the user's plan — locked features frustrate users  ✅
- **C.** All features should be available to every user regardless of their current subscription tier
- **D.** The tab should automatically redirect free-tier users to the pricing page when they click on it

> **Answer:** B

### Q3. Your pricing page shows three plan columns with no visual indicator highlighting which plan you recommend. All three look identical except for price. What is missing?

- **A.** A detailed comparison table positioned directly below the plan cards to clarify differences
- **B.** A free trial button on every plan card with automatic activation for new sign-ups
- **C.** Testimonials from existing customers displayed prominently alongside each pricing plan card
- **D.** A highlighted 'Most Popular' badge on the mid-tier plan to anchor the buying decision  ✅

> **Answer:** D

### Q4. Your dashboard shows a usage chart, activity feed, billing summary, and team list. On load a spinner shows for 6 seconds while all sections load at once. What should change?

- **A.** Add a visual progress bar instead of a generic spinner so users see how far along the load is
- **B.** Load each section independently so users see content as it becomes ready instead of waiting  ✅
- **C.** Cache all dashboard data permanently so it never needs to load from the server again
- **D.** Remove the slowest-loading section from the dashboard entirely to improve the overall load time

> **Answer:** B

### Q5. Your AI built a pricing page with hardcoded plan prices. After raising Pro from $49 to $59, the checkout page still shows $49. What caused this?

- **A.** Stripe automatically overrides the price shown on the frontend during the checkout flow process
- **B.** The customer's browser cached the old price and hadn't been cleared or refreshed yet
- **C.** Hardcoded prices in multiple spots drift out of sync — plan data needs one single source  ✅
- **D.** The checkout page and pricing page are separate apps that can't easily share data between them

> **Answer:** C

### Q6. You're testing your SaaS dashboard on mobile. The sidebar navigation takes up the full screen width and there's no way to collapse it. The main content area is invisible. What's the fix?

- **A.** SaaS dashboards aren't designed for mobile devices and shouldn't attempt to support that layout
- **B.** Build a separate mobile application dedicated to the dashboard experience instead
- **C.** Remove the sidebar entirely and replace it with a bottom tab bar optimized for mobile navigation
- **D.** Make the sidebar collapsible via a hamburger menu, keeping main content visible by default  ✅

> **Answer:** D

### Q7. A paying customer downgrades from Pro to Free. Your dashboard still shows the Team Management tab but throws an error when they click it. What should happen instead?

- **A.** Remove the Team Management tab from navigation when the user's plan changes down to Free tier  ✅
- **B.** The error message is fine — it tells them they need to upgrade to access that feature
- **C.** Their team data should be deleted immediately once the user completes the downgrade to Free tier
- **D.** The downgrade should be blocked entirely until they remove all their team members manually first

> **Answer:** A

### Q8. Your settings page has Profile, Billing, Team, and Security built as four separate pages with no shared layout and inconsistent header and button styles. What is the problem?

- **A.** The AI tool should have automatically ensured consistency across all the generated settings pages
- **B.** Each settings section should have its own unique design so users can tell the pages apart easily
- **C.** Settings pages don't need consistent styling because users rarely visit them at all
- **D.** Settings pages should share a layout shell with consistent styling — separate pages drift  ✅

> **Answer:** D

### Q9. You ask AI to build a billing page. It shows the current plan and a Change Plan button but no invoice history, payment method display, or cancel option. What is missing?

- **A.** Payment methods are handled entirely by Stripe so there's no reason to build that into the product
- **B.** Invoice history should be kept as a separate standalone page rather than part of billing settings
- **C.** A billing page needs invoice history, payment methods, plan changes, and cancellation  ✅
- **D.** The current plan display is enough — users can contact support for any billing needs

> **Answer:** C

### Q10. Your AI added a notification bell to the dashboard. It loads the last 50 notifications on every page load even when the dropdown is closed. What should change?

- **A.** Notifications should be delivered via email only rather than being shown inside the dashboard UI
- **B.** 50 notifications is too few — the system should load all of them for completeness
- **C.** Notifications should load only when the user clicks the bell — not on every single page load  ✅
- **D.** The dropdown should always stay open and visible so users never miss an important notification

> **Answer:** C

### Q11. Your pricing page has a monthly/annual toggle. Selecting Annual updates prices but the Save 20% badge is hardcoded and the real discount is 16%. What is the risk?

- **A.** The savings badge should be calculated from actual prices — a mismatch erodes user trust  ✅
- **B.** Rounding up the discount percentage is standard marketing practice and shouldn't cause any issues
- **C.** Users don't typically check the math on pricing pages so conversion won't be affected
- **D.** The annual plan should simply be priced higher to make the displayed savings percentage accurate

> **Answer:** A

### Q12. Your dashboard chart renders monthly revenue correctly on desktop but is illegible on mobile with overlapping labels and the legend covering the bars. What should you evaluate?

- **A.** Remove the chart from the mobile layout entirely since detailed data belongs on desktop
- **B.** Rotate the chart ninety degrees on smaller screens so long labels gain more horizontal room
- **C.** Ask users to zoom the page manually since mobile browsers already handle scaling content
- **D.** Direct AI to make the chart responsive — fewer labels, repositioned legend, mobile sizing  ✅

> **Answer:** D

### Q13. Your dashboard sidebar has 12 navigation items. Users report feeling overwhelmed. What should you consider?

- **A.** Add a search bar to the sidebar instead of reorganizing any of the existing navigation structure
- **B.** Remove sidebar items until there are only five left to keep the navigation clean and manageable
- **C.** Group related items into collapsible sections and prioritize the most-used items at the top  ✅
- **D.** Every navigation item is equally important so the sidebar shouldn't be reorganized

> **Answer:** C

### Q14. A Free plan user opens DevTools and changes a CSS class from hidden to visible on the Team Management section. They can now use premium features. What does this reveal?

- **A.** CSS-based hiding isn't real access control — plan gating must be enforced by the backend, not UI  ✅
- **B.** Users shouldn't be able to open DevTools — that capability should be disabled in the app
- **C.** This approach is fine because users can see the interface elements but can't actually save any data
- **D.** The hidden CSS class should use a more obscure name so users can't easily locate it in the markup

> **Answer:** A

### Q15. Your settings page saves on every keystroke. As a user types a new company name, 15 API calls fire in 3 seconds. What is the fix?

- **A.** Batch the requests on the server side so rapid incoming calls get merged after arrival
- **B.** Switch the settings page to a manual save button so users decide when the data persists
- **C.** Debounce the auto-save so it fires once after the user pauses typing, not per keystroke  ✅
- **D.** Queue every keystroke's call in the browser and replay the sequence when the user leaves

> **Answer:** C

### Q16. Your pricing comparison table has 30 rows. On desktop it looks clean but on mobile users must scroll horizontally to see all plan columns. What is the better approach?

- **A.** Collapse the table into stacked per-plan cards on mobile, surfacing key differences first  ✅
- **B.** Keep the table but shrink the font size until all plan columns fit on the mobile screen
- **C.** Show a desktop-only notice asking mobile users to revisit pricing from a larger device
- **D.** Convert the table into a downloadable image that mobile users can pinch and zoom as needed

> **Answer:** A

### Q17. Your AI tool generated a SaaS dashboard with a light theme. Your brand uses a dark foundation (#0E0E0E). Instead of asking AI to rebuild, what's the efficient approach?

- **A.** Rebuild the entire dashboard from scratch with all the dark styling specified in the first prompt
- **B.** Prompt your AI agent to swap the theme tokens — background, surface, text — to the dark palette  ✅
- **C.** Ship the light theme now and schedule a full dark redesign for a later product release
- **D.** Apply a display filter that inverts all page colors so the light theme renders as dark

> **Answer:** B

### Q18. Your onboarding asks users to connect Stripe at step 2. Some users lack a Stripe account and cannot skip or proceed. What design principle is violated?

- **A.** Never hard-block onboarding on an outside dependency — let users skip and connect later  ✅
- **B.** Every onboarding flow should collect payment details early so billing is never an afterthought
- **C.** Onboarding should be one single screen — multi-step flows lose users before completion
- **D.** The Stripe step is fine but belongs first, before users invest time in earlier steps

> **Answer:** A

### Q19. Your dashboard loads usage data from an API taking 3 seconds. The section shows nothing during load — no spinner or skeleton screen. Users think it is broken. What is missing?

- **A.** A retry button that appears whenever a dashboard section takes longer than one second
- **B.** A permanently cached copy of the previous data so the section never once appears empty
- **C.** A skeleton or loading indicator so users see the section is fetching rather than broken  ✅
- **D.** A smaller API payload — three whole seconds means the response is too heavy for the dashboard

> **Answer:** C

### Q20. Your AI generated separate React projects for marketing, dashboard, and settings. Each has its own button component. Updating brand colors requires three changes. What went wrong?

- **A.** Nothing — separate projects are safer since a broken element in one can't hurt the rest
- **B.** The three projects should all be merged into one single page so each element exists only once
- **C.** Brand colors should be left out of shared elements so updates never require any changes
- **D.** Shared elements belong in one design system — direct AI to reuse components across projects  ✅

> **Answer:** D

### Q21. A new user signs up for your SaaS app. They land on the dashboard and see an empty screen — no data, no charts, no guidance. They close the tab and never return. What should have been there?

- **A.** Sample data pre-loaded into their account so they can explore the full dashboard immediately
- **B.** Empty states with guidance prompts — finish setup, add their first item, or connect integrations  ✅
- **C.** A pop-up video tutorial that auto-plays on first login to walk users through every feature
- **D.** A redirect to the documentation page where they can read guides about getting started on their own

> **Answer:** B

### Q22. Your dashboard data table works fine with 50 test records. With 12,000 production records the page freezes for 10 seconds on load. What is the root cause?

- **A.** The browser can't handle more than 1,000 rows — switch to a spreadsheet format for large data
- **B.** All 12,000 rows render at once — add pagination or virtualization to display only visible rows  ✅
- **C.** The CSS styling applied to the table is too complex and heavy for large data sets to render well
- **D.** The database query is too slow and there's nothing the frontend can realistically do to fix that

> **Answer:** B

### Q23. Your onboarding flow has 6 steps. Analytics show that 40% of users drop off at step 3, which asks for their company size, industry, and revenue range. What should you do?

- **A.** Make all form fields required so users can't skip any steps during the onboarding setup process
- **B.** Remove the onboarding flow entirely and let users figure out the product on their own with docs
- **C.** Add a progress bar so users can clearly see how far along they are in the full onboarding flow
- **D.** Check if step 3 data is truly essential — if not, make it optional or defer it past first value  ✅

> **Answer:** D

### Q24. Your marketing site uses blue and white. Your dashboard uses dark gray with green accents that AI generated independently. What is the problem?

- **A.** Marketing sites and dashboards should look completely different so users know they've transitioned
- **B.** Marketing site and dashboard should share brand tokens — colors, fonts, spacing — to feel cohesive  ✅
- **C.** The customer is wrong about the disconnect — dark dashboards are the accepted industry standard
- **D.** AI tools can't maintain brand consistency across separate projects without manual intervention

> **Answer:** B

### Q25. Your Create Team step lets users invite by email. Entering an invalid email and clicking Send Invite refreshes the page with no error and no invite sent. What is broken?

- **A.** The invite form needs inline validation — show an error next to the email field without refreshing  ✅
- **B.** Email validation should only happen on the server side and never be duplicated on the frontend
- **C.** The page refresh behavior is correct — the user should just re-enter the email address manually
- **D.** The invite system should accept any input text and let the email delivery service handle validation

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/103821095_
