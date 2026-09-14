---
course: "The Foundation"
module: "Layer 12: Error Tracking & Logs"
lesson: "Layer 12: Error Tracking & Logs — Exam"
type: "course_quiz"
post_id: 102901698
space_id: 23777123
source: "https://the-faction.mn.co/posts/102901698"
updated: "2026-08-20T23:50:09Z"
---

# Layer 12: Error Tracking & Logs — Exam

> Exam for **Layer 12: Error Tracking & Logs** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your app has been live for a month and you've never seen an error report. Does this mean your app has no bugs?

- **A.** Yes — if no error reports have surfaced after a full month of live usage, that silence strongly confirms the app is bug-free and running perfectly for every user who visits
- **B.** No — it likely means you have no error tracking set up. Errors are probably happening silently, and without monitoring you won't know until users complain or leave  ✅
- **C.** Yes — apps built with AI assistance are inherently stable, so if nothing has been flagged it means nothing is actually wrong anywhere in the codebase
- **D.** It depends entirely on how many active users the app currently has and whether any of them ever bother to report back about the issues they encounter

> **Answer:** B

### Q2. Sentry shows: 'TypeError: Cannot read properties of undefined.' You don't need to fix the code — but what kind of problem is this?

- **A.** The server ran completely out of available memory during a sudden traffic spike, which caused the app to throw this particular type of error message to the affected users
- **B.** A user entered an invalid password too many times in a row, and the authentication system responded to the repeated attempts with this specific error type
- **C.** The code tried to use a value that doesn't exist — it expected data to be there but found nothing. The app attempted to access a property on something never loaded  ✅
- **D.** The database briefly lost its connection to the app server, triggering this error because the pending queries could not be completed in time by the engine

> **Answer:** C

### Q3. A user clicks a button and sees a completely blank white screen. What's missing that would have prevented this?

- **A.** The button needed a much higher contrast color scheme so the user could clearly see that it was working and loading the next page for them
- **B.** Additional CSS styling rules were needed to make sure the page rendered properly and displayed its content to every user who clicked through
- **C.** A faster server with far more headroom would have prevented the request timeout that caused the screen to go blank while the click was still being processed
- **D.** Error boundaries — a safety net that catches crashes in your app and shows a friendly message instead of leaving the user staring at a blank screen  ✅

> **Answer:** D

### Q4. A user says 'the app crashed when I tried to check out.' You have no logs. What information are you missing?

- **A.** The user's device preferences and display settings, which could reveal a rendering conflict between your app and that particular phone or browser
- **B.** The user's internet connection speed at the exact moment of the checkout, which would explain whether the crash was really caused by a slow network timeout on their end
- **C.** What happened right before the crash — which page they were on, what they clicked, what data was processing, and the exact error. Logs record this sequence  ✅
- **D.** How many other users were online at the same time, which would tell you whether the server was under heavy load when the checkout attempt failed

> **Answer:** C

### Q5. You want to know within five minutes when your app crashes. What do you need to set up?

- **A.** An error tracking service like Sentry integrated into your app, with alerting that sends you a notification the moment a crash is detected so you respond fast  ✅
- **B.** A disciplined manual routine where you open the app every five minutes around the clock to check whether anything has broken or crashed recently
- **C.** A prominent user feedback form so that people can quickly report issues whenever they encounter a crash or any other kind of unexpected behavior
- **D.** A social media monitoring tool that continuously scans public posts on every major platform for user complaints about your app crashing, hanging, or being completely down

> **Answer:** A

### Q6. An error report shows a stack trace with five lines. What is this telling you?

- **A.** The app currently has five separate bugs sitting in production that all need to be fixed before this particular error will finally stop occurring
- **B.** Five different users were affected by this exact error at almost the same moment, and each one of them triggered a single line in the report
- **C.** A breadcrumb trail showing where in the code the error happened — from trigger through each function called. You describe this path to AI when asking for a fix  ✅
- **D.** The server that runs the app has five separate CPU cores, and the error report is showing you exactly which core encountered the problem while serving the request

> **Answer:** C

### Q7. Sentry shows 500 errors but they're actually just three different bugs happening repeatedly. How does error grouping help?

- **A.** It doesn't really help at all — you are still left with 500 individual error occurrences that each need their own separate investigation and attention
- **B.** It only displays the very first error that occurred and quietly hides all of the newer ones so that your dashboard looks much cleaner than it really is
- **C.** It permanently deletes every duplicate error record from the system in order to free up storage space in your error tracking tool before the next billing cycle begins
- **D.** It combines the 500 occurrences into 3 groups by type, so you fix 3 bugs instead of wading through 500 individual reports. You see which bugs affect the most users  ✅

> **Answer:** D

### Q8. You want to add error tracking to your existing app. What would you describe to your AI tool?

- **A.** Tell AI to wrap every single line of code in its own dedicated try-catch block so that no error of any kind can possibly go unhandled anywhere in the application
- **B.** Tell AI to integrate Sentry into the app so errors are captured automatically with context, and configure notifications so you're alerted when crashes happen  ✅
- **C.** Tell AI to build a dedicated contact form where users can manually describe and report any bugs that they happen to encounter while browsing
- **D.** Tell AI to add more console.log statements throughout the codebase so that you can watch the output scroll past in the browser while you test

> **Answer:** B

### Q9. Your AI tool asks whether you need error tracking or logging. What's the difference?

- **A.** They are exactly the same thing — error tracking and logging are simply two different names that vendors use to describe the identical underlying process of recording problems
- **B.** Error tracking is designed to be used by professional developers only, while logging is a user-facing transparency feature that shows people what the app is doing
- **C.** Error tracking captures crashes automatically with context. Logs are a running diary of everything the app does. Both are needed — errors show what broke, logs tell the story  ✅
- **D.** Logging completely replaces error tracking, so once you have proper logging set up there is no reason to ever configure a separate error tracking product as well

> **Answer:** C

### Q10. Your app crashed and a user saw a blank white screen. What is an error boundary and how would it have helped?

- **A.** A safety net that catches crashes and shows a friendly message like 'Something went wrong' instead of a blank screen. The user loses one section, not the entire app  ✅
- **B.** A firewall layer that prevents hackers from exploiting application crashes to gain unauthorized access to your backend systems while they are restarting after a sudden failure
- **C.** A CSS border style that visually highlights every error message shown on the screen so that the warning text stands out clearly to users as they browse
- **D.** A configuration setting that limits how many errors are allowed to occur inside your app before the platform automatically shuts the whole thing down entirely

> **Answer:** A

### Q11. You receive a Sentry notification about an error. What information should the error report contain?

- **A.** Only the error message text itself — additional details like the page location and the browser are unnecessary clutter that slows down your triage
- **B.** A complete video recording of the user's entire session, covering absolutely everything from the moment they logged in all the way to the moment the error finally occurred
- **C.** The user's personal information, including their full name, their email address, and the account credentials that they used when they first signed in
- **D.** What went wrong (error type), which page, what browser, a stack trace showing where in code it happened, and relevant context like the user's action before the crash  ✅

> **Answer:** D

### Q12. Your app writes log entries when users log in, make payments, and load pages. Why is this useful when debugging?

- **A.** It's not useful at all — logs are just background noise that clutters up your system and makes it harder to spot the real issues
- **B.** Logs actively slow down the performance of the application so much that they should simply be avoided entirely in any serious production environment
- **C.** Logs are really only useful for billing and invoicing purposes and have no practical relevance at all when you are debugging errors
- **D.** Logs tell the story of what happened before a crash. When something breaks, you trace the sequence of events to understand what led to the failure  ✅

> **Answer:** D

### Q13. Your monitoring workflow for errors should follow what pattern?

- **A.** Wait patiently for users to email you about bugs, then attempt to reproduce each one of them manually on your own machine before fixing anything
- **B.** Direct AI to add error tracking, errors are captured automatically, you receive alerts, read the report, describe the problem to AI for a fix, verify, and ship  ✅
- **C.** Check the app manually once every week by clicking through all of the key pages yourself to see whether anything on them looks obviously broken or out of place
- **D.** Only invest time fixing the errors that are specifically reported by paying customers who take the trouble to open a formal support request

> **Answer:** B

### Q14. Your app has been crashing for users but you had no idea because you never set up monitoring. What pitfall is this?

- **A.** Building far too many features far too quickly, which introduced a deep level of instability that a simpler and more focused product would easily have avoided
- **B.** Not setting up error tracking at all — your app is crashing and you don't know it. Users see the problems but they leave instead of telling you about them  ✅
- **C.** Choosing the wrong hosting platform, which caused the crashes through server-level compatibility issues between the platform and your code
- **D.** Having too few active users on the platform to generate enough error volume for the underlying problems to ever become truly noticeable to you

> **Answer:** B

### Q15. Your AI tool generated logging that includes user passwords and credit card numbers in plain text. What pitfall is this?

- **A.** Logging sensitive data like passwords and credit card numbers — a security and privacy violation that can expose you to serious legal consequences  ✅
- **B.** Logging far too much data on every request, which gradually slows down your application's performance and fills up the available storage space rapidly
- **C.** Using the wrong logging format, which makes the log files much harder for people to read and parse during a stressful debugging session
- **D.** Keeping log data around that is far too old and outdated to be relevant for any of the current debugging or analysis work you are doing

> **Answer:** A

### Q16. You set up Sentry alerts for every error. You now get 200 notifications per day and ignore all of them. What pitfall is this?

- **A.** Sentry is badly misconfigured and is sending you far too many duplicate email notifications about the exact same recurring error events over and over
- **B.** Your app simply has far too many bugs in production right now, and the very high alert volume is an accurate reflection of genuine underlying instability in the codebase
- **C.** Alert fatigue — setting up alerts for everything means you ignore them all. When every notification is urgent, nothing feels urgent and real problems get missed  ✅
- **D.** You need a better email client that can automatically sort, group, and prioritize all of the incoming alert notifications much more effectively

> **Answer:** C

### Q17. Sentry reports show errors in files like 'chunk-abc123.js' at line 1. You can't understand them. What's wrong?

- **A.** Source maps aren't configured. Your deployed code is minified, so error reports show garbled filenames. Source maps translate these back to readable code references  ✅
- **B.** The errors are far too complex and technical for anyone other than a senior developer with many years of experience to accurately read and understand
- **C.** Sentry does not actually support the programming language that your app is written in, which is why every single one of the file references appears garbled in the reports
- **D.** The error messages are being displayed in a foreign language because of the regional localization settings that are configured on the app server

> **Answer:** A

### Q18. Your app uses console.log for all its 'logging.' When you close the browser, all log information vanishes. What's wrong?

- **A.** console.log vanishes when the browser closes. Real logs persist, have severity levels, and are searchable. You need proper logging that saves to a permanent location  ✅
- **B.** console.log is the industry-standard approach that professional teams everywhere rely on for logging in production, and there is truly nothing wrong with using it this way
- **C.** console.log runs far too fast for the browser to keep up with, which causes the log entries to be written out of order and become completely unreliable
- **D.** You should simply switch every logging call from console.log over to console.error instead, which automatically persists all of the output for you

> **Answer:** A

### Q19. A broken image on your About page and a crashed checkout both show as errors with the same priority. What pitfall is this?

- **A.** Both errors really are equally important to the business, and each one of them deserves exactly the same level of attention and urgency from your team
- **B.** Treating all errors as equal priority. A broken About page image is minor; a crashed checkout costs revenue. Without severity levels you waste time on wrong problems  ✅
- **C.** Sentry cannot actually differentiate between the different types of errors it collects, so it is expected behavior that every issue appears at exactly the same priority level
- **D.** Both errors share exactly the same underlying root cause, which is why the monitoring system displays the two of them with completely identical priority

> **Answer:** B

### Q20. Do you have an error tracking service connected to your app right now?

- **A.** This is the first checklist item — you should have Sentry or similar connected and capturing errors. If not, that is the very first thing to set up for your app  ✅
- **B.** Error tracking is only needed after your app launches publicly, so during the development and beta phases there is really nothing worth setting up yet
- **C.** Error tracking is unnecessary for small apps — it only becomes relevant once you have reached a genuinely large user base with heavy traffic arriving every single day
- **D.** The browser's built-in console is entirely sufficient for all of your error tracking needs, so no extra tooling of any kind ever needs to be added

> **Answer:** A

### Q21. If your app crashed right now, how would you find out?

- **A.** You should get a notification within minutes via your error tracking service's alerting. If you'd find out from a user complaint instead, your alerting needs work  ✅
- **B.** A user would eventually email or message you directly to let you know that something had gone wrong with the application while they were trying to use it
- **C.** You would see user complaints about the crash slowly begin to appear on social media platforms like Twitter or Reddit within a few hours of the initial failure
- **D.** Your hosting provider's status dashboard would show a server error indicator somewhere that you could check periodically throughout the working day

> **Answer:** A

### Q22. Can you open your error tracking dashboard and explain the most recent error in plain language?

- **A.** Only professional developers with deep technical training can accurately read and interpret the detailed reports that an error tracking service produces
- **B.** AI should read and interpret every single error report for you from start to finish, since humans cannot realistically be expected to understand the technical data inside
- **C.** Error reports are far too technical for vibecoders to ever work with directly and should only ever be handled by a team of dedicated engineering specialists
- **D.** You should be able to open Sentry, find the most recent error, and explain it: error type, page, users affected. Understanding error reports is a core vibecoder skill  ✅

> **Answer:** D

### Q23. Your error reports show an error occurred but don't include what page or action the user was on. What's missing?

- **A.** Error reports never include contextual information like the user's page or action — that data simply is not available to any tracking tool
- **B.** Error context — your tracking should capture page, user action, browser, and relevant data so you understand what the user was doing when the error happened  ✅
- **C.** You need to contact each affected user individually and politely ask them exactly what they were doing at the precise moment the error occurred on their screen
- **D.** Only dedicated session replay tools can provide that level of information — error tracking services are simply not able to capture any of it themselves

> **Answer:** B

### Q24. A user sees a blank white screen when your app crashes. What should they see instead?

- **A.** A technical error code like '500 Internal Server Error' displayed on screen, so that the user knows exactly what went wrong inside the application stack
- **B.** An automatic redirect straight back to the app's homepage so that the user can start their entire session over again from the very beginning of the checkout flow
- **C.** Nothing — blank white screens are expected and completely normal behavior whenever a modern app runs into an error that it cannot gracefully handle
- **D.** A friendly message like 'Something went wrong. Please try again' — provided by an error boundary that catches the crash gracefully instead of showing nothing  ✅

> **Answer:** D

### Q25. Your logs are random unstructured text with no consistent format. Can you search them by user ID or time range?

- **A.** Logs do not really need to be searchable — their entire purpose is simply to exist as a passive historical record of everything the application has done so far
- **B.** Only database logs require any real structure — ordinary application logs can safely remain as unformatted plain text output sitting on the production server
- **C.** No, and that's a problem. Logs should be structured with consistent fields (user ID, action, time) so you can search and filter when debugging. Random text logs are useless  ✅
- **D.** AI tooling can search and interpret completely unstructured logs just as quickly and effectively as it handles well-structured ones, so the storage format makes no real difference

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/102901698_
