---
course: "The Foundation"
module: "Layer 5: Hosting & Deployment"
lesson: "Layer 5: Hosting & Deployment — Exam"
type: "course_quiz"
post_id: 102901501
space_id: 23777123
source: "https://the-faction.mn.co/posts/102901501"
updated: "2026-08-20T23:47:19Z"
---

# Layer 5: Hosting & Deployment — Exam

> Exam for **Layer 5: Hosting & Deployment** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI-built app deploys to Vercel but shows a blank white page, even though it runs fine locally. What three things should you check first?

- **A.** Delete the entire Vercel project completely, re-upload every single file by hand, and then open an urgent support ticket with Vercel right away
- **B.** Restart your computer, clear out all of your browser data, and register a completely new domain name to fully replace the current one
- **C.** Check the build log for errors, verify environment variables are configured on Vercel, and confirm the correct branch was deployed to production  ✅
- **D.** Test your internet connection speed, update your browser to the very latest version, and then do a full clean reinstall of Node.js on your machine

> **Answer:** C

### Q2. Your app runs locally but crashes on Netlify with 'API key not found.' You set the key in a local .env file. What went wrong?

- **A.** The .env file should have been committed and then pushed up to your GitHub repository so that Netlify could automatically read it during each of its builds
- **B.** Local .env files don't transfer to hosting platforms. The API key must be entered in Netlify's environment variable settings on the platform dashboard  ✅
- **C.** You need to contact Netlify support directly and then have their team manually configure the API key on their platform servers on your behalf
- **D.** The API key should be pasted directly into one of your source code files so that it gets bundled up and deployed alongside the application

> **Answer:** B

### Q3. You connected your domain to Vercel but visitors see 'DNS not found' after 10 minutes. What's the most likely explanation?

- **A.** Your domain registrar sold you a fundamentally broken domain name, and you should immediately request a full refund from their customer support team
- **B.** DNS changes can take up to 48 hours to propagate globally. Verify your DNS records are configured correctly and allow time for propagation  ✅
- **C.** You need to download and install special DNS resolution software on your local machine before the domain will start working properly
- **D.** Free-tier domains are incompatible with Vercel's hosting infrastructure, so you must purchase a premium domain to get it working

> **Answer:** B

### Q4. A user reports a 'Not Secure' warning in their browser and your URL starts with http instead of https. What should you do?

- **A.** The user's own browser is simply outdated and needs an update; your site's configuration itself is working correctly as it was deployed
- **B.** This warning means that your server currently lacks antivirus software, so you need to install a complete security suite on the hosting platform itself
- **C.** The 'Not Secure' warning is a mobile-only browser quirk and it can be safely ignored since it doesn't affect any of your desktop users
- **D.** Your site lacks an SSL certificate so data is unencrypted. Enable SSL on your hosting platform — Vercel and Netlify handle this automatically  ✅

> **Answer:** D

### Q5. Your deploy fails with 'Module not found: canvas-toolkit.' Your AI tool generated the project. What does this error mean?

- **A.** Your hosting platform's servers simply don't support any canvas-based HTML elements, and you need to switch over to a different hosting provider
- **B.** The canvas-toolkit package exceeds the hosting platform's file size limit, so you need to find a lighter alternative module to use instead
- **C.** Your app references 'canvas-toolkit' but it isn't listed in your project's dependencies, so the hosting platform can't find it during the build  ✅
- **D.** This error indicates a temporary server outage on the hosting platform's side, and you should simply wait a while and then retry the deploy later

> **Answer:** C

### Q6. You have a static marketing site and a complex web app with a database. Should you host both on the same platform?

- **A.** The static site fits Netlify well, while the database app may need Railway or similar. Different projects have different hosting needs  ✅
- **B.** Complex apps with databases simply can't be hosted online at all — they must run on your own personal laptop and be shared out via screen sharing
- **C.** You should always host everything on a single platform to minimize costs, regardless of how complex each project actually is
- **D.** Both projects must go on AWS because it's the only hosting platform that offers any kind of database support for web apps

> **Answer:** A

### Q7. Your deployed app's home page loads fine, but clicking to '/dashboard' gives a 404 error. It works locally. What's the cause?

- **A.** The hosting platform isn't configured for client-side routing — it looks for a real file at /dashboard instead of letting your app handle the route  ✅
- **B.** A 404 error only occurs when your domain registration has expired, so you need to log in to your registrar account and renew the domain right away
- **C.** Each separate page of your application requires its own separate hosting plan and deployment, which you haven't yet set up for the dashboard page
- **D.** The dashboard page's source code was automatically deleted out of your repository by the hosting platform while it executed the most recent deployment

> **Answer:** A

### Q8. A teammate committed a Stripe API key to a public GitHub repo, saying 'nobody will look.' What's the real risk and fix?

- **A.** It's perfectly safe since public repos are only risky when they're private — public visibility actually protects the exposed key from any real misuse
- **B.** Rotate the key immediately, revoke the old one, and store it in your hosting platform's environment variables. Bots scan GitHub for exposed keys  ✅
- **C.** Simply delete the line containing the key in your next commit and the exposed key will be completely erased from GitHub's history
- **D.** Embedding API keys directly in source code is standard industry practice and is how most professional development teams currently handle it

> **Answer:** B

### Q9. You're explaining hosting to a fellow vibecoder who's confused about what it actually means. Which analogy best captures it?

- **A.** Hosting is like installing an app on your phone — once it has been installed it runs forever with absolutely no internet connection needed
- **B.** Hosting and buying a domain name are the exact same thing — the two terms are completely interchangeable in web development
- **C.** Hosting is renting space on a server that's always online so anyone with the link can access your app anytime, from anywhere in the world  ✅
- **D.** Hosting means manually emailing your application files to every single person who wants to use your app so they can run it

> **Answer:** C

### Q10. Your AI tool generated a Next.js app. You're comparing Vercel and Netlify for deployment. Which statement is most accurate?

- **A.** Netlify is the only hosting platform on the market that provides any level of support for deploying Next.js applications
- **B.** Platform selection is irrelevant because every hosting platform handles all types of web applications in exactly the same way
- **C.** Neither Vercel nor Netlify is able to host AI-generated applications — you must instead use AWS or a similar enterprise-grade cloud provider
- **D.** Vercel is an especially strong choice for Next.js apps because it was built by the creators of Next.js with deep framework integration  ✅

> **Answer:** D

### Q11. Your code is on GitHub, connected to Vercel. What happens when you push an update to your GitHub repository?

- **A.** Nothing happens automatically — you still must manually click the Deploy button on Vercel's dashboard every single time you want to push an update
- **B.** Vercel detects the push, automatically rebuilds your app, and publishes the new version — similar to how Dropbox syncs when you save a file  ✅
- **C.** GitHub sends you a confirmation email and you must reply with 'yes' before the hosting platform will begin the deployment process
- **D.** Your previous deployed version is permanently erased from the platform's servers and can never be recovered or rolled back to

> **Answer:** B

### Q12. Your domain is myapp.com. When a user types that into a browser, how does the browser know which server to connect to?

- **A.** The browser uses a best-guess algorithm based on the spelling and structure of the domain name to locate the correct server
- **B.** The user must manually type in both the domain name and also the server's numeric IP address together for the connection to work properly
- **C.** DNS acts like a phone book for the internet — it translates your domain name into the actual server address where your app is hosted  ✅
- **D.** Domain names connect directly to applications with no translation layer or intermediary system required between them at all

> **Answer:** C

### Q13. You keep hearing about the 'build process' during deployment. What does the build step actually do?

- **A.** The build step converts your source code into something browsers can understand. It can fail if there's a missing dependency or configuration error  ✅
- **B.** The build step physically provisions and then fully constructs a brand new dedicated physical server specifically to handle your application's deployment
- **C.** The build step only executes on your very first deployment — after that initial run your app never actually needs to be built ever again
- **D.** The build step is when the hosting platform's review team manually checks your code for quality standards and coding style compliance

> **Answer:** A

### Q14. A vibecoder has their Stripe key and database password hardcoded in source code instead of using environment variables. What's wrong?

- **A.** Nothing at all is wrong with this approach — storing secrets directly in code is the widely accepted standard practice for reasonably small-scale projects
- **B.** It only becomes a security concern if the code is pushed up to GitHub; secrets kept inside local-only code files are always perfectly safe
- **C.** Anyone who sees the code can steal those credentials. Secrets must be stored in the hosting platform's environment variables, encrypted and separate  ✅
- **D.** The only real risk is that embedding secrets makes the code file longer, which reduces its overall readability and its maintenance quality

> **Answer:** C

### Q15. A vibecoder deployed their AI-built app straight to production, skipping any preview or staging step. What's the risk?

- **A.** There's no real risk — deploying directly to production is the fastest possible shipping method and it is recommended for every single project type
- **B.** Staging environments are only truly necessary for large-scale apps with more than one thousand active users on the hosting platform
- **C.** The only downside of skipping staging is a marginally slower overall deployment speed, but the end result is identical either way
- **D.** Deploying straight to production without a staging test means your real users become your beta testers and every bug goes live immediately  ✅

> **Answer:** D

### Q16. A vibecoder's app runs on http, not https, and never set up SSL. A friend says 'not a big deal.' What's the actual consequence?

- **A.** HTTP and HTTPS function identically in every single way — the extra 's' in HTTPS is purely cosmetic and provides no additional security benefit
- **B.** SSL encryption is only required for banking and financial websites — regular applications and small projects don't need it at all
- **C.** Without SSL, browsers show 'Not Secure' warnings that erode user trust, and all data transmitted between users and the app is unencrypted  ✅
- **D.** The only measurable consequence is a marginally slower page load time, but there is no real impact on security or user experience

> **Answer:** C

### Q17. A vibecoder's new domain shows an error 30 minutes after setup. They want to buy a different one. What should you tell them?

- **A.** DNS propagation can take up to 48 hours. They should verify their DNS records are correct and wait before assuming the domain is broken  ✅
- **B.** They should try adding 'www' in front of the domain URL and it will resolve and start working for all visitors right away
- **C.** They're probably right that the domain is defective — they should buy a replacement from a different registrar immediately
- **D.** Domain names are only functional on weekdays because the global DNS servers shut down for maintenance every weekend and on all public holidays

> **Answer:** A

### Q18. A vibecoder's app went down at 1am and they didn't know until 8am when customers complained. No monitoring was set up. What should they have done?

- **A.** They should have stayed awake through the entire night and then manually refreshed the website every single hour to verify it was still running
- **B.** They should have deployed the application to two separate hosting platforms simultaneously to create full failover redundancy
- **C.** There's no way to prevent discovering outages late — all sites go down eventually and customer complaints are how you find out
- **D.** They should have set up uptime monitoring that pings the site automatically and sends alerts the moment it goes down, before customers notice  ✅

> **Answer:** D

### Q19. A vibecoder did one stressful manual deploy and plans to never deploy again, leaving the app as-is forever. What's wrong with this?

- **A.** Deployment is an ongoing process, not a one-time event. Apps need constant updates, so you need a repeatable workflow you can run confidently  ✅
- **B.** They only need to redeploy if the hosting platform sends them an official written notification specifically requesting a complete redeployment
- **C.** Nothing is wrong — once an application is successfully deployed it never needs to be updated, patched, or redeployed ever again
- **D.** They're absolutely correct — the industry best practice is to deploy once, archive the entire project, and move on permanently

> **Answer:** A

### Q20. The Layer 5 checklist asks: 'Can you deploy from GitHub to a hosting platform?' A vibecoder drags files manually. Does this count?

- **A.** Yes, because any method that results in a live application counts toward satisfying the checklist, including manual file uploads
- **B.** Manual file uploads are actually the preferred deployment method over GitHub integration because they offer noticeably better security and control
- **C.** GitHub-based deployment is only a requirement for Tier 3 certification — Tier 1 candidates can use any upload method they prefer
- **D.** No — the checklist specifies deploying from your GitHub repo, meaning you connect the repo so deploys happen automatically on each push  ✅

> **Answer:** D

### Q21. The checklist asks if ALL secrets are in environment variables. A vibecoder has 3 of 4 keys on Vercel but 1 hardcoded. Do they pass?

- **A.** Yes, because having the large majority of your API keys properly stored in environment variables already demonstrates sufficient security awareness
- **B.** No — ALL keys and secrets must be in the hosting platform's environment variables. Even one hardcoded secret is a real security vulnerability  ✅
- **C.** Yes, because configuration files are categorized differently from source code files, making hardcoded keys in configs acceptable
- **D.** No, but the failure is because four API keys is an excessive number for a single project, not because of where they are stored

> **Answer:** B

### Q22. The checklist asks if your live site has SSL working. What two visible signs confirm SSL is active and working correctly?

- **A.** The site loads with consistently fast performance speeds and all of the written content on the page is free of grammatical errors and typos
- **B.** A padlock icon appears in the browser's address bar and the URL begins with https instead of http, confirming encrypted communication  ✅
- **C.** The browser tab background turns green and a security certification badge appears automatically in the footer of your website
- **D.** The site displays a cookie consent banner on first visit and includes a dedicated privacy policy page linked in the footer

> **Answer:** B

### Q23. The checklist asks if you can read a build log to diagnose a failed deploy. Where should a vibecoder look first?

- **A.** Check the build log on the hosting platform's dashboard — it contains the specific error messages explaining exactly why the build failed  ✅
- **B.** Check their email inbox for a detailed failure explanation that the hosting platform's support team sends out after every single failed build
- **C.** Search social media and developer forums to see if other users are currently experiencing the exact same deployment issue
- **D.** Re-run the deploy immediately without investigation, because most build failures are random and resolve on a second attempt

> **Answer:** A

### Q24. The checklist asks about rollbacks. A new deploy broke checkout. What is a rollback, and why does speed matter?

- **A.** A rollback reverts your live site to the previous working version instantly. Speed matters because every minute of downtime directly impacts users  ✅
- **B.** A rollback requires formally contacting your hosting platform's support team so that they can manually restore the old version, a process taking 24-48 hours
- **C.** A rollback means deleting your entire application and then rebuilding it from scratch, which is why you should always test everything first
- **D.** A rollback is the same thing as clearing your browser cache — it simply refreshes the page to display the previously cached version

> **Answer:** A

### Q25. The checklist asks about monitoring for your live site. Which best describes what monitoring should do for your deployed app?

- **A.** Monitoring tracks the running total number of lines of code that your AI tool has generated across every one of your project's source code files
- **B.** Monitoring scans your GitHub repository for spelling errors and grammatical issues found inside your source code comments and docs
- **C.** Monitoring is a manual daily process where you personally visit your own live site once per day to confirm it loads successfully
- **D.** Monitoring automatically pings your live site on a regular schedule and alerts you immediately if it goes down, before your customers notice  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/102901501_
