---
course: "The Foundation"
module: "Layer 7: CI/CD & Version Control"
lesson: "Layer 7: CI/CD & Version Control — Exam"
type: "course_quiz"
post_id: 102901564
space_id: 23777123
source: "https://the-faction.mn.co/posts/102901564"
updated: "2026-08-20T23:48:04Z"
---

# Layer 7: CI/CD & Version Control — Exam

> Exam for **Layer 7: CI/CD & Version Control** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. You built a contact form with your AI tool and want to deploy it. What's the correct sequence?

- **A.** Commit your changes with a clear message describing what you built, push to GitHub, and your hosting platform auto-deploys the update to your live site  ✅
- **B.** Push your changes up to GitHub first, then commit them afterward once the push has finished, and then wait for the hosting platform to auto-deploy your updates
- **C.** Copy the files over to your hosting platform by hand first, and then commit everything to GitHub at some point afterward as a purely secondary backup copy
- **D.** Deploy the update straight from your AI coding tool to your hosting platform, and skip using GitHub entirely for this update since the form already works on your machine

> **Answer:** A

### Q2. You added a page, fixed a checkout bug, and changed the color scheme in one session. How should you commit?

- **A.** Make three separate commits, each with a clear message describing that specific change, so any single change can be reverted independently later  ✅
- **B.** Make one single commit with the message 'Updated site' so that your commit history stays simple, compact, and very easy to scan through later in the project
- **C.** Hold off on committing and wait until you have accumulated even more changes, so that you can bundle everything into one large weekly commit instead
- **D.** Make one commit per individual file that changed, regardless of which feature or which fix each of those separate file changes actually belongs to

> **Answer:** A

### Q3. Your AI tool generated code that broke login. You already committed and deployed. Users can't log in. What's the fastest safe fix?

- **A.** Manually rewrite the entire login page from memory, and then commit that newly written version as a fresh replacement for the broken one
- **B.** Revert the broken commit, which creates a new commit that undoes those specific changes while preserving your full project history intact  ✅
- **C.** Delete the entire repository and start over again from a backup copy that you previously saved locally on a separate external drive
- **D.** Edit the live server files directly to fix the issue as quickly as you possibly can, before any more of your users notice that login is failing

> **Answer:** B

### Q4. You made changes on both your laptop and desktop without pushing to GitHub. Now pushing from your laptop fails. What happened?

- **A.** GitHub deleted your repository automatically, because it detected what its security systems consider unauthorized access coming from two separate devices
- **B.** Git only allows one computer per repository, which means you need to create a second separate repository for the other machine to use
- **C.** Your internet connection is too slow to handle pushing code from two different geographic locations at once, so the second push simply times out and fails
- **D.** Both machines have different commits that GitHub doesn't have yet, creating a conflict that must be resolved before either can push successfully  ✅

> **Answer:** D

### Q5. Your laptop was stolen. All client project code was saved locally. You never pushed to GitHub. What's the status?

- **A.** GitHub automatically backs up every local Git repository to the cloud, which means your code is still completely safe and recoverable
- **B.** You can recover all of the code by logging into Git with your account credentials from any other computer that you have access to
- **C.** Your code is gone unless you have another backup, because GitHub only stores code you explicitly push to it — no push means no cloud copy  ✅
- **D.** Your AI coding tool keeps a copy of every project on the vendor's servers, so you can simply log back in and re-download everything that was lost

> **Answer:** C

### Q6. Your commit messages say 'fix', 'update', 'stuff', 'asdf'. A teammate needs to find when the pricing page changed last month. What's the problem?

- **A.** The commits are far too small and granular, and they should instead have been combined into larger batch commits covering entire weeks of work
- **B.** Git doesn't support searching through commit messages at all, so the content of those individual messages is essentially irrelevant to the search
- **C.** The commit messages are vague and meaningless, making it impossible to locate specific changes without manually opening and reading every single commit  ✅
- **D.** The real problem is having too many commits in the history — you should aim for fewer, larger commits so that the log stays short enough to read in one sitting

> **Answer:** C

### Q7. You pushed changes to GitHub but your live app still shows the old version. Your host is connected to your repo. What should you check first?

- **A.** Delete your hosting account entirely and create a brand new one from scratch, in order to force a completely fresh connection to the repository
- **B.** Verify your hosting platform is connected to the correct repo and branch, then review the deploy logs for build errors that blocked the update  ✅
- **C.** Push the exact same code again multiple times in a row until the hosting platform finally notices the change and picks up the new version
- **D.** Manually copy your files over to the hosting platform yourself, since automatic deployments are frequently unreliable and cannot really be trusted anyway

> **Answer:** B

### Q8. Your app worked last week but is broken now. You have 20 commits since then. How do you find which commit introduced the bug?

- **A.** Delete all 20 of the commits and start completely over again from last week's version, so that you can at least get back to a working state quickly
- **B.** Ask your AI tool to automatically find and fix the bug for you, without bothering to look at the commit history or the recent changes at all
- **C.** Review the commit history, read what changed in each commit using your descriptive messages, and narrow down which specific change likely broke things  ✅
- **D.** Deploy each of the 20 commits to production one at a time, and test every single one of them live against real users until you find the one that breaks

> **Answer:** C

### Q9. A vibecoder says 'I just save my project folder to a USB drive every night.' What critical capability are they missing vs. Git?

- **A.** There is no meaningful difference between the two approaches, because both of them provide essentially the same level of protection for your code
- **B.** USB drives are actually faster than Git when it comes to saving and restoring large project files, which makes them the more efficient backup choice
- **C.** Git only works together with AI coding tools, so USB backups are actually the better and far more flexible choice for anyone who writes their code manually
- **D.** Git tracks every change as a snapshot you can revert to at any time — not just nightly backups — so you never lose more than one commit's worth of work  ✅

> **Answer:** D

### Q10. Your AI tool asks if you want to initialize Git and connect to GitHub. You plan to work solo. Is this necessary?

- **A.** No — Git and GitHub are collaboration tools that are only really needed when you are working together with a team of multiple developers
- **B.** Yes — GitHub serves as your cloud backup, and connecting your hosting platform to it enables automatic deployment every time you push changes  ✅
- **C.** No — your AI coding tool automatically saves every version of your code internally on its servers, which makes Git completely redundant
- **D.** Yes, but only if you eventually plan to make your code open source so that other developers around the world can freely use it and contribute to it

> **Answer:** B

### Q11. You click 'Commit & Push' for every tiny change, creating 50 commits in a day with messages like 'small tweak.' What should you adjust?

- **A.** Stop committing so often entirely, and only commit once per week in order to dramatically reduce the amount of clutter in your project history
- **B.** Only commit when the entire project is 100% complete and fully ready for launch, in order to keep the whole history clean and presentable
- **C.** Keep committing just as frequently as you do today, but go back and delete your older commits periodically to keep the commit history tidy and short
- **D.** Commit after each meaningful chunk of work — adding a feature, fixing a bug, or updating the design — with a clear message describing what changed  ✅

> **Answer:** D

### Q12. You accidentally committed an API key and pushed it to GitHub. You then removed the key in a new commit. Is the problem fully resolved?

- **A.** Yes — the newest commit deleted the key from the current codebase, so it is no longer accessible to anyone looking through the project
- **B.** No — the API key still exists in the previous commit in your Git history, so anyone with repo access can find it. Rotate the key immediately.  ✅
- **C.** Yes — GitHub automatically scans every push for exposed API keys and quietly removes them from all commits across your entire repository
- **D.** No — but only because GitHub is a public platform by default. If your repository is set to private, the key sitting in the old commit is perfectly safe

> **Answer:** B

### Q13. Your Vercel hosting is connected to your repo. You want to test a major redesign without affecting the live app. What's the safest approach?

- **A.** Disconnect Vercel from GitHub entirely, make all of your redesign changes, test them thoroughly on your machine, and then reconnect the two later
- **B.** Work on a separate branch so the main branch connected to your live app stays completely untouched until the redesign is tested and ready to merge  ✅
- **C.** Make the changes directly on the main branch, but ask Vercel support to temporarily pause all deployments until the redesign work is done
- **D.** Create a completely new GitHub repository just for the redesign work, and figure out how to merge the two separate repositories together at the end

> **Answer:** B

### Q14. A vibecoder built a feature for three days without committing. On day three, their AI tool breaks the project. What pitfall did they hit?

- **A.** They should have picked a different AI coding tool, one that ships with more reliable auto-save and project recovery features built in
- **B.** Three days between commits is a perfectly normal and acceptable amount of time to go dark for complex, multi-part feature work like this
- **C.** They fell into the trap of never committing until the feature is 'done' — now three days of work is lost with zero checkpoints to roll back to  ✅
- **D.** The real problem is that they relied on an AI tool at all, instead of carefully writing every line of the code by hand themselves like a professional would

> **Answer:** C

### Q15. Commit messages say 'fix', 'update', 'stuff', 'done.' Six months later, a client asks when payment integration was added. What's the consequence?

- **A.** There is no consequence — you can simply search the codebase directly for payment-related files and find the answer that way
- **B.** GitHub automatically generates better commit messages as a repository ages, so these vague ones will eventually be overwritten
- **C.** You'll need to open and review every single commit to find the payment integration, turning a quick lookup into hours of detective work  ✅
- **D.** The commit messages are perfectly fine as long as the actual code works correctly — messages are just decorative labels on top of the history

> **Answer:** C

### Q16. A solo vibecoder pushes all changes directly to main. Their host auto-deploys from main. A bad AI commit breaks the live site. What pitfall caused this?

- **A.** They should have chosen a different hosting platform, specifically one that does not support automatic deployment from a GitHub repository
- **B.** They were working directly on main instead of using feature branches — so one bad commit went straight to production and broke the live site  ✅
- **C.** They should have turned off auto-deploy completely, and only deployed manually after personally testing every single change themselves
- **D.** Auto-deployment itself is inherently risky, and it should never be used by solo builders under any circumstances on a real production application

> **Answer:** B

### Q17. A teammate says 'skip the PR review, I need this live in 10 minutes.' They merge without review and ship a bug. What pitfall is this?

- **A.** The pitfall of using pull requests at all — they add unnecessary process overhead and noticeably slow down the delivery pace of the entire team
- **B.** The pitfall of having teammates at all — solo development is always the safer, faster, and more reliable way to run a software project
- **C.** The pitfall of skipping PR reviews because you're 'in a hurry' — the bug shipped fast takes ten times longer to fix once real users discover it  ✅
- **D.** The pitfall of deploying during business hours — production changes should only ever be pushed late at night when almost no users are on the app

> **Answer:** C

### Q18. A vibecoder has zero automated tests. They're terrified to add features because they might break existing functionality. What pitfall is this?

- **A.** They're correctly being cautious — you should never modify working code, because the risk of breaking an existing feature through regression is far too high
- **B.** They need to completely rewrite their entire app from scratch, this time using a modern framework that has proper support for automated testing
- **C.** This fear indicates that their app architecture is fundamentally flawed, and that the codebase needs a full structural overhaul before anything else happens
- **D.** They fell into the trap of having no automated tests, making them afraid to touch anything — even basic tests would give them confidence to keep building  ✅

> **Answer:** D

### Q19. Two people edited the same file. Git shows a merge conflict. One vibecoder panics and clicks 'Accept Current' without reading both versions. What's the risk?

- **A.** The risk is losing someone's work or creating a bug, because they didn't understand what both versions do before choosing which changes to keep  ✅
- **B.** There is no real risk at all — Git always picks the objectively better version automatically whenever you click to accept the current changes
- **C.** Merge conflicts always mean that one person's code is simply wrong, and that the incorrect version should be deleted from the repository entirely
- **D.** The risk is purely cosmetic — merge conflicts never affect actual app functionality, and they are unable to break any of the user-facing features in the app

> **Answer:** A

### Q20. The self-assessment asks: 'Can you commit and push to GitHub so it's backed up and triggers a deploy?' You only save locally. What do you need?

- **A.** A GitHub repository connected to your project, plus a hosting platform linked to that repo for automatic deployment whenever you push new changes  ✅
- **B.** A paid GitHub Enterprise account, plus a dedicated deployment server that you administer yourself to handle the automatic build process for the project
- **C.** An FTP connection that you use to manually upload the project files to your hosting platform after each local save on your machine
- **D.** A separate cloud backup service running alongside GitHub, since GitHub does not natively support any form of automatic deployment by itself

> **Answer:** A

### Q21. The self-assessment asks: 'Do your commit messages describe what changed and why?' Your last 10 all say 'update.' What's the standard?

- **A.** Messages should be at least 500 characters long, and should include full technical documentation covering every single change that was made
- **B.** Messages should include the exact date, the time, and your full legal name in addition to the description text explaining the change
- **C.** Messages don't matter for certification purposes at all — only the actual quality and the real-world functionality of your shipped code is ever evaluated
- **D.** Messages should describe what changed and why, like 'Fix checkout form validation on mobile' — concise but specific enough to understand later  ✅

> **Answer:** D

### Q22. The self-assessment asks: 'Could you revert to last week's version if today's changes broke something?' You've never tried reverting. What should you do?

- **A.** Practice reverting on a real project — break something on purpose, then revert to confirm you can actually recover and understand the full process  ✅
- **B.** Memorize the exact Git revert command syntax, so that you can type it out perfectly from memory if you are ever asked to during the exam
- **C.** Skip this particular checklist item entirely, since reverting commits is very rarely needed in anyone's actual day-to-day development work
- **D.** Read a detailed tutorial about how reverting works in Git, but don't actually try running it against any of the files inside your real projects just yet

> **Answer:** A

### Q23. The self-assessment asks: 'Is there at least one automated check before code reaches your live app?' You have zero. What's the minimum?

- **A.** At least one automated check — a test, linter, or build verification — that runs before code reaches production, catching obvious errors before users see them  ✅
- **B.** A comprehensive automated test suite with 100% code coverage, plus full integration tests running across every single component in the application
- **C.** Manual testing performed by at least two separate team members before every single deploy is allowed to go live to your production application
- **D.** Automated checks are only a requirement for the Tier 2 and Tier 3 certification levels, so they are not something a Tier 1 Foundation builder needs to think about

> **Answer:** A

### Q24. The self-assessment asks: 'Could you read a deploy error log and figure out what went wrong?' You've never looked at one. Where do you find it?

- **A.** Deploy logs are hidden system files, accessible only to the platform's own engineers who hold special administrator credentials
- **B.** Deploy errors are only ever sent out via email notifications, and they cannot be viewed in real time on any dashboard in the product
- **C.** You need to SSH directly into the production server and manually dig through all of the raw system logs yourself in order to find deploy errors
- **D.** In your hosting platform's dashboard (Vercel, Netlify) — they show build and deploy logs with clear error messages whenever something fails  ✅

> **Answer:** D

### Q25. The self-assessment asks: 'Do you know how to open a pull request?' You've been pushing directly to main. What does a PR actually do?

- **A.** A PR is a formal request to merge your branch into the main project — it shows what changed, lets others review and comment, and creates a record of every decision  ✅
- **B.** A pull request downloads code from GitHub onto your local machine, so that you can keep working on the project offline from home without an internet connection
- **C.** A pull request is GitHub's way of formally requesting payment from you for hosting your repository and for continuing to store your code on its servers
- **D.** A pull request automatically resolves all of the merge conflicts between two branches, without ever requiring any human input, code review, or approval along the way

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/102901564_
