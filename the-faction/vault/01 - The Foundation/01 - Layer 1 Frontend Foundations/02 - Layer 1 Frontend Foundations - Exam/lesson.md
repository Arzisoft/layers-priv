---
course: "The Foundation"
module: "Layer 1: Frontend Foundations"
lesson: "Layer 1: Frontend Foundations — Exam"
type: "course_quiz"
post_id: 102899630
space_id: 23777123
source: "https://the-faction.mn.co/posts/102899630"
updated: "2026-08-21T04:32:49Z"
---

# Layer 1: Frontend Foundations — Exam

> Exam for **Layer 1: Frontend Foundations** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. You asked AI to build a task manager. The project has all code for the header, sidebar, task list, and footer inside one file called app.js. What is the problem with this approach?

- **A.** The app isn't organized into separate, reusable components, making it harder to find, fix, and update individual pieces later  ✅
- **B.** The app won't render on mobile devices because putting all code in one file prevents the browser from loading it properly
- **C.** The file will be too large for the browser to download, causing timeout errors and blank screens whenever users try to load the application
- **D.** The AI tool made an error and you should regenerate the entire project using a completely different prompt and approach

> **Answer:** A

### Q2. You built a landing page with AI. It looks perfect on your laptop, but a phone screenshot shows the nav overlaps the hero image and two buttons are cut off. What most likely happened?

- **A.** The AI tool built the layout for your laptop screen size but didn't properly handle responsive design for smaller screens  ✅
- **B.** Your friend's phone has a virus or malware that distorts how websites render their layouts and interactive elements
- **C.** The images on the page are far too high resolution for a phone to display, causing the layout elements to shift visibly out of place
- **D.** Your app requires a specific desktop browser that isn't available on phones, so the page cannot render correctly

> **Answer:** A

### Q3. A visually impaired user says their screen reader can't identify any images in your app. The AI-generated code has no descriptive text on images. What accessibility feature is missing?

- **A.** Responsive breakpoints that adjust the image layout and sizing so pictures fit properly across many different screen widths and devices
- **B.** Tailwind CSS classes that apply proper visual styling and formatting to image elements throughout the page layout
- **C.** Alt text on images, which provides descriptive labels that screen readers announce so visually impaired users understand the content  ✅
- **D.** A dark mode toggle that switches the interface to high-contrast colors, making images easier to distinguish on screen

> **Answer:** C

### Q4. You built your app screen by screen with AI. Settings buttons are rounded blue, dashboard buttons are square green, and the profile page has a third style. What is this an example of?

- **A.** A responsive design failure where the layout cannot adapt properly to different screen sizes and viewport dimensions
- **B.** A styling consistency problem across your app, where each screen was generated separately without shared design rules in place  ✅
- **C.** An accessibility violation that prevents assistive technologies from interpreting the interface for users with disabilities
- **D.** A component rendering error where the underlying framework fails to apply the correct styling properties to elements on the page

> **Answer:** B

### Q5. Your AI built a product listing page. Product data loads server-side before reaching the browser, but the Add to Cart button runs client-side after page load. What is the best explanation?

- **A.** The AI made an error by splitting the work between server and browser, and all logic should be in one location instead
- **B.** The server-side code is only there for security purposes and has no impact on page speed or how quickly users see content
- **C.** All code should run in the browser because server-side rendering is an outdated approach that adds unnecessary complexity
- **D.** Some parts of your app run on the server for speed and SEO, while interactive elements like buttons run in the browser so users can interact  ✅

> **Answer:** D

### Q6. Your portfolio website takes 12 seconds to load on a mobile connection. Using Chrome DevTools, you discover that the page is loading a 5MB hero image. What should you ask your AI tool to do?

- **A.** Remove all images from the site to improve load time, since visual content is the primary cause of slow page performance
- **B.** Optimize the image by compressing it, using a modern format like WebP, and implementing lazy loading for images below the fold  ✅
- **C.** Move the image to the server side so it loads faster, since server-rendered images bypass the browser download queue
- **D.** Add a loading spinner so users know the page is still working while the browser finishes downloading all of the large media assets

> **Answer:** B

### Q7. A user fills out a long registration form, makes an email typo, and clicks Submit. The page refreshes, all fields clear, and a generic error appears. What are the two biggest problems?

- **A.** The form is clearing the user's input on a failed submission and the error message doesn't explain what specifically went wrong  ✅
- **B.** The form should use a different color scheme and the submit button should be larger to improve the visual hierarchy
- **C.** The form should be split across multiple separate pages and should not allow email addresses as a valid input type
- **D.** The page refresh is expected behavior and the error message is sufficient because most users understand generic error notifications

> **Answer:** A

### Q8. You asked AI to build a complete e-commerce homepage with listings, cart, reviews, and checkout. The result is a messy single page with broken features. What should you have done?

- **A.** Asked AI to build it in smaller pieces — first the product card, then the grid, then the cart, then checkout — reviewing each piece before combining them  ✅
- **B.** Switched to a different AI coding tool that handles large prompts better and can generate complex pages without any layout issues
- **C.** Written every line of code by hand since AI cannot handle complex pages and manual coding avoids the structural issues AI creates
- **D.** Added even more details to the single big prompt to make it more specific, including exact dimensions and detailed style requirements

> **Answer:** A

### Q9. Your AI built a job listing page. Instead of creating separate reusable pieces for the job card, search bar, and filter sidebar, it put everything into one block. What concept did it miss?

- **A.** Responsive design principles that ensure the layout adjusts fluidly across different screen sizes and device types
- **B.** Accessibility standards that require proper semantic markup, keyboard navigation, and screen reader compatibility
- **C.** Server-side rendering, which pre-builds page content on the server before sending the finished HTML down to the user's browser
- **D.** Component-based architecture — building the UI from small, reusable, separate pieces that snap together like LEGO blocks  ✅

> **Answer:** D

### Q10. You tested your app on your laptop and it looks perfect. On a phone, text overlaps, buttons are off-screen, and the layout is broken. What concept should you have verified before shipping?

- **A.** That the app uses responsive design to adapt its layout automatically for different screen sizes including phones, tablets, and desktops  ✅
- **B.** That the app uses the correct JavaScript framework, since some frameworks handle mobile layouts better than others
- **C.** That the app has a loading spinner during navigation so users know each page is actively rendering on their own device
- **D.** That the co-founder is using the latest browser version, since older browsers may not support modern layout features

> **Answer:** A

### Q11. Your app's primary blue is defined in three places. AI used a slightly different shade on two pages, making the app feel unpolished. What system would prevent this?

- **A.** An automated visual testing suite that checks each page for visual regressions and flags styling inconsistencies before every deployment
- **B.** A version control system such as Git that tracks every change to your codebase and lets you compare all the file differences
- **C.** A consistent styling system where colors, fonts, and spacing are defined in one central place and referenced everywhere across the app  ✅
- **D.** A different AI coding tool that is specifically trained to maintain consistent design patterns across generated output

> **Answer:** C

### Q12. You built a blog with AI. A keyboard-only user can't navigate past the header — Tab doesn't move focus to article links or the comment form. What accessibility concept was overlooked?

- **A.** Page load performance, which measures how quickly the browser can download, parse, and render every single piece of page content on screen
- **B.** Mobile responsiveness, which ensures the layout and interactive elements adapt properly to smaller phone and tablet screens
- **C.** Image optimization, which compresses and formats visual assets so they load quickly without degrading page performance
- **D.** Keyboard navigation — the ability for users to move through and interact with every element in the entire app using only a keyboard  ✅

> **Answer:** D

### Q13. You described a feature to AI, got the output, and deployed without checking. Users report it fails on mobile and has no error handling. What step of the vibecoder workflow did you skip?

- **A.** Choosing the right framework for your project, which determines how well the app handles mobile layouts and error states
- **B.** Reviewing the AI's output, testing it on a real phone, identifying problems, and iterating with the AI to fix them before shipping  ✅
- **C.** Writing unit tests manually for each function and component to catch every bug before the code reaches production users
- **D.** Reading through the AI's generated source code line by line to verify every function and variable is implemented correctly before deploying

> **Answer:** B

### Q14. You built your app for three weeks in Chrome on your MacBook, never checking on a phone. Half the pages are broken on iPhone — buttons stacked, text off-screen. What pitfall is this?

- **A.** Not setting up a folder structure before generating code, which causes files to scatter across random directories as the project grows
- **B.** Treating AI's first output as final and shipping it without reviewing the code, questioning its choices, or iterating
- **C.** Never checking your app on an actual phone during development, so mobile layout problems pile up and become expensive to fix  ✅
- **D.** Skipping accessibility features like keyboard navigation, screen reader labels, and proper focus management throughout the app

> **Answer:** C

### Q15. You asked AI to build a full dashboard with user management, analytics, notifications, settings, and activity feed. The result is a messy page with broken interactions. What pitfall is this?

- **A.** Asking AI to build the whole page at once instead of breaking it into smaller components and reviewing each one before combining  ✅
- **B.** Never checking the dashboard on a phone or tablet, so responsive layout problems go completely unnoticed until real users find them
- **C.** Skipping accessibility features like keyboard navigation, screen reader support, and proper focus on interactive elements
- **D.** Not defining brand rules for consistent colors, fonts, and spacing before generating any code, leading to visual inconsistency across pages

> **Answer:** A

### Q16. Six weeks in, you need to update the pricing card. Components are scattered across random folders with names like PricingCard.jsx, pricing_widget.js, and card2.tsx. What pitfall caused this?

- **A.** Not checking the app on a real phone during development, which means mobile layout and interaction issues quietly accumulate unnoticed
- **B.** Not setting up a folder structure and naming convention before you started generating, so AI scattered files wherever it wanted  ✅
- **C.** Letting every page look different by not defining shared brand rules for colors, fonts, button styles, and spacing
- **D.** Treating AI's first output as final without reviewing the generated code, testing edge cases, or iterating on quality

> **Answer:** B

### Q17. Your app looks great with a mouse. But a keyboard-only user can't interact with buttons or forms, and their screen reader announces every image as just 'image.' What did you skip?

- **A.** Performance optimization, which focuses on reducing load times, compressing assets, and minimizing server requests
- **B.** Mobile responsiveness testing, which verifies that layouts, buttons, and text adapt properly across phone and tablet screens
- **C.** Setting up a consistent folder structure and naming convention so components stay organized predictably throughout the entire project
- **D.** Accessibility — screen reader support, keyboard navigation, and alt text — features AI does not add unless you specifically ask  ✅

> **Answer:** D

### Q18. AI generated a signup form that works, so you ship it. A week later: empty fields crash the server, special characters break the display, no email validation. What pitfall is this?

- **A.** Not checking the form on a real phone, which means touch interactions and mobile layout issues go completely unnoticed by the whole team
- **B.** Treating AI's first output as final without reviewing for edge cases like empty fields, special characters, and iterating to fix issues  ✅
- **C.** Not defining brand rules for consistent visual styling, which causes each form and page to look different from the rest
- **D.** Not setting up a folder structure and naming convention before generating, which leads to disorganized and hard-to-find files

> **Answer:** B

### Q19. Your checklist says test on a real phone. Chrome DevTools looked fine, but on an actual phone touch targets are too small and scrolling feels janky. What does this teach you?

- **A.** The laptop simulator is a useful first check, but testing on an actual phone catches real-world issues like touch target sizing and scroll behavior that simulators can't replicate  ✅
- **B.** Chrome DevTools is fundamentally broken and shouldn't be used for any kind of mobile testing because its device simulation is unreliable compared to real hardware
- **C.** Your phone's browser is simply outdated and needs updating to the latest available version to resolve both the touch target and the scrolling problems
- **D.** You need to rebuild the entire app for mobile as a totally separate project because responsive design cannot handle both desktop and phone in one codebase

> **Answer:** A

### Q20. You need to build a pricing page for your SaaS app. Which approach would most likely get you a usable result from your AI coding tool on the first or second try?

- **A.** Tell AI to make you a pricing page without specifying any details about the tiers, the features, the prices, or the visual style guidelines it should follow
- **B.** Ask AI to use its best judgment on the pricing layout, trusting the tool to pick the right structure, colors, and content without any concrete guidance
- **C.** Build a pricing page with 3 tiers (Basic, Pro, Enterprise) showing price, 5 features with checkmarks, and a CTA button. Use brand blue (#2563EB) and match my dashboard style  ✅
- **D.** Tell AI to copy a competitor's pricing page layout wholesale, which skips the essential work of defining your own brand identity, structure, and content

> **Answer:** C

### Q21. You test keyboard navigation by pressing Tab. Main nav works, but at product cards focus skips to the footer — Add to Cart buttons are unreachable. What should you do?

- **A.** This is fine because most users use a mouse anyway, and keyboard-only navigation is an edge case that does not need fixing
- **B.** Tell your AI tool that the Add to Cart buttons inside product cards need to be keyboard-accessible and focusable via Tab navigation  ✅
- **C.** Remove the product cards from the page entirely and replace them with a simpler text list that avoids the focus problem
- **D.** Add a prominent notice telling users to use a mouse instead of the keyboard, since the product cards were not designed for Tab navigation

> **Answer:** B

### Q22. Before coding, you told AI: use components/ for UI, pages/ for layouts, utils/ for helpers, PascalCase filenames. A new collaborator finds everything easily. What checklist item is this?

- **A.** Testing on a real phone to verify that responsive layouts, touch targets, and scrolling all work correctly on mobile devices
- **B.** Defining brand colors, fonts, and spacing rules in a single shared config file so every generated component looks visually consistent
- **C.** Adding accessibility features like keyboard navigation, screen reader labels, and alt text so all users can interact with it
- **D.** Setting up a consistent folder structure and naming convention before you started generating, so every file lands in its place  ✅

> **Answer:** D

### Q23. You test forms: submit empty, enter bad email, paste 10,000 chars into the name field, use emoji in the phone number. Several inputs crash the app. What checklist item were you testing?

- **A.** Whether your app works on mobile devices, since phone screens often reveal layout and interaction problems desktops hide
- **B.** Whether your app keeps consistent styling across every one of its pages, with unified colors, fonts, button shapes, and spacing throughout
- **C.** Whether your forms handle empty submissions, weird characters, and very long text gracefully instead of crashing or failing silently  ✅
- **D.** Whether your app meets accessibility standards including keyboard navigation, screen reader support, and labeled fields

> **Answer:** C

### Q24. Your checkout stops working — Place Order does nothing. You open Chrome DevTools Console and see a red error: Cannot read property of undefined. What checklist skill is this?

- **A.** Knowing how to describe components to AI so it generates the right structure, styling, and functionality on the first attempt
- **B.** Testing on a real phone to verify that touch targets, scrolling, and responsive layouts all function on mobile devices
- **C.** Knowing how to open browser DevTools and check if your app is throwing errors, so you can tell AI exactly what needs fixing  ✅
- **D.** Setting up a folder structure and naming convention before generating code so components are organized and easy to find

> **Answer:** C

### Q25. An investor says your app doesn’t feel like one product — homepage uses one font and colors, dashboard uses another, settings looks completely different. What pitfall caused this?

- **A.** Building with too many AI prompts across separate sessions, which causes the tool to lose context about your project design
- **B.** Using the wrong JavaScript framework for your project, which limits how consistently styles and components render across pages
- **C.** Not testing on mobile devices during development, so responsive layout and touch interaction issues went completely unnoticed
- **D.** Letting every page look slightly different because you never defined your brand rules (colors, fonts, spacing) in one place  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/102899630_
