---
course: "The Foundation"
module: "Layer 13: Availability & Recovery"
lesson: "Layer 13: Availability & Recovery — Exam"
type: "course_quiz"
post_id: 102901722
space_id: 23777123
source: "https://the-faction.mn.co/posts/102901722"
updated: "2026-08-20T23:50:38Z"
---

# Layer 13: Availability & Recovery — Exam

> Exam for **Layer 13: Availability & Recovery** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your app was down three hours before a customer emailed you. What should you have had in place?

- **A.** A dedicated customer support team monitoring your inbox around the clock so that any downtime complaints get answered quickly
- **B.** A premium server upgrade plan that guarantees your application will achieve perfect uptime and therefore never needs any outage alerting at all
- **C.** Uptime monitoring—a service that checks your app every minute and alerts you instantly via text, email, or Slack when it goes down  ✅
- **D.** A deployment schedule with much more frequent releases so that any server issues quietly resolve themselves automatically in between versions

> **Answer:** C

### Q2. Monitoring says your app is up, but users can't load pages. Your health check only confirms the server responds. What's missing?

- **A.** A deep health check that verifies your app AND its dependencies like the database and external APIs—not just that the server process runs  ✅
- **B.** A faster polling interval on your existing health check so that the monitoring service you already run detects failures a bit sooner
- **C.** Adding several additional monitoring services from different providers so that you can receive redundant uptime alerts about the very same failures
- **D.** Migrating the whole app to a different hosting provider that includes built-in monitoring plus automatic resolution of any failures it happens to detect

> **Answer:** A

### Q3. You set up daily database backups six months ago but never tested a restore. What's the risk?

- **A.** No proof it works. Backups can be corrupt, incomplete, or incompatible with your current setup. An untested backup is one you hope works, not one you know works.  ✅
- **B.** Zero risk, because properly configured automated backups always produce valid and restorable output files no matter what changes in your stack afterward
- **C.** Backups only require verification testing during the initial setup week; once they have run cleanly for a few days you can trust them to keep working reliably after that
- **D.** Your cloud hosting provider automatically validates every single backup it stores and contractually guarantees recoverability, so testing restores yourself would be wasted effort

> **Answer:** A

### Q4. Your database crashes and the most recent backup is 23 hours old. How much data is lost, and what would you change?

- **A.** No data is actually lost, because the database engine will automatically recover every one of the recent transactions from its own in-memory journal
- **B.** Losing 23 hours of data is an acceptable tradeoff, since daily backups are the standard for small apps and customers understand losses
- **C.** Up to 23 hours of data—everything since the last backup. Increase backup frequency to hourly so worst-case loss drops from one day to one hour.  ✅
- **D.** All of the recent transactions can still be recovered by extracting the cached data directly from the server RAM before the machine is rebooted by your provider

> **Answer:** C

### Q5. You deployed a new version and now the app is broken. What's the fastest way to get back online?

- **A.** Start debugging the broken version live in production while your users wait around and keep experiencing error messages on every single page
- **B.** Wait for your hosting platform's automated recovery systems to detect the deployment failure on their own and quietly repair it without your involvement
- **C.** Push the exact same broken code again right away, because deployment glitches of this kind sometimes resolve themselves cleanly on a second attempt at publishing
- **D.** Roll back to the previous working version immediately—most platforms support one-click rollback. Get online in seconds, then debug separately.  ✅

> **Answer:** D

### Q6. You accidentally deleted a critical database table and have no backups. What are your options?

- **A.** Very limited—you may recover from transaction logs if supported, but without backups most data is likely gone permanently. Set up automated backups now.  ✅
- **B.** The database engine will quietly regenerate the deleted table and all of its records from the internal system metadata it keeps for this purpose
- **C.** Submit a support ticket to your hosting provider and wait, because their operations team keeps private copies of customer tables and will restore the deleted one for you
- **D.** Ask your users to carefully re-enter all of their data by hand, since they very likely remember their most recent activity well enough to reconstruct the missing records

> **Answer:** A

### Q7. You want to be notified within two minutes if your app goes down. What do you direct AI to set up?

- **A.** A feedback button on your application's error page so that affected users can manually report outages to you the moment they run into one themselves
- **B.** A scheduled cron job running on the same server that sends you an automated status email every two minutes to confirm the machine is still up and responding
- **C.** An uptime monitor like UptimeRobot that pings your health endpoint every 30-60 seconds and sends instant alerts via Slack, text, or email on failure.  ✅
- **D.** A manual monitoring process in which you personally open and review the server log files on a strict two-minute schedule throughout the day so nothing slips past you

> **Answer:** C

### Q8. Your database backup is stored on the same server as your database. Why is this a problem?

- **A.** If the server dies, both your database AND backup die with it. Store backups on a different server, region, or provider so one failure can't destroy both.  ✅
- **B.** It is not really a problem, because storing the backup physically closer to the database makes the nightly backup process finish noticeably faster
- **C.** Keeping backups on the same server as the database is the industry-standard arrangement recommended by most hosting providers, so no change is needed on your part
- **D.** The operating system automatically replicates every backup file to a secondary location for redundancy, so a single machine failure can never take out both copies at once

> **Answer:** A

### Q9. What is the purpose of uptime monitoring for your app?

- **A.** To optimize your app's response time and make page loads noticeably faster for users across their different regions and devices
- **B.** To count the total number of unique visitors to your app and track detailed user engagement metrics for every page of your application each month
- **C.** To actively prevent server crashes from ever happening by intercepting and resolving errors in the background before they can cause any visible downtime
- **D.** To auto-check your app every minute and alert you instantly when it goes down—so you know in seconds, not hours later from complaints.  ✅

> **Answer:** D

### Q10. What is a health check endpoint and why does your monitoring service need one?

- **A.** A dashboard page that displays your application's real-time analytics, including traffic numbers and error rates, for you to review anytime
- **B.** A public URL where end users can visit at any hour to submit bug reports and describe in their own words the issues they experienced while using your app
- **C.** A URL like /health that returns OK when the app and its dependencies work. Monitoring hits it regularly—if it stops returning OK, you get alerted.  ✅
- **D.** A password-protected admin page showing detailed server hardware specifications, including CPU load, memory consumption, and remaining disk space for the machine

> **Answer:** C

### Q11. Your database backup runs daily at midnight. What are the two critical questions you should be able to answer about backups?

- **A.** How fast the backup job completes each night and how much total disk storage space each of the archived backup files consumes on the server
- **B.** How often backups run (frequency = max data loss) and where they're stored (location = whether one disaster can destroy both data and backup).  ✅
- **C.** Who originally configured the backup automation for the project and what specific file format the nightly export process actually generates on disk
- **D.** How old the backup software itself is and when the backup tool was last patched or updated, since stale tooling is the main cause of most data loss incidents

> **Answer:** B

### Q12. Your database crashes. Backups run daily at midnight and it's now 11 PM. What's your worst-case data loss?

- **A.** No data loss, because the most recent midnight backup is less than 24 hours old and therefore still covers everything
- **B.** Only the data entered during the very last hour would be lost, since all of the recent transactions remain safely in memory
- **C.** Nearly 24 hours—everything from midnight to 11 PM. Recovery time and data loss are directly tied to how often you back up.  ✅
- **D.** The entire database going back to its creation would be permanently lost, with no realistic possibility of even a partial recovery afterward

> **Answer:** C

### Q13. What is the vibecoder availability workflow?

- **A.** Build the app, deploy it, and hope that nothing goes wrong, because you can always fix availability issues later if they ever come up
- **B.** Skip the monitoring setup for now and only configure alerting tools after you have experienced your first real outage and know what alerts you want
- **C.** Manually open your app in a fresh browser tab every single morning to visually confirm that the homepage still loads properly before you start other work
- **D.** Direct AI to set up uptime monitoring, health checks, automated backups, test restoration, and document recovery steps—then sleep easy.  ✅

> **Answer:** D

### Q14. Your app was down for hours and you were the last to know. A free tool would have texted you in 60 seconds. What pitfall is this?

- **A.** Selecting a hosting platform that was too inexpensive and lacked the reliability guarantees that the premium providers advertise
- **B.** A misconfigured server firewall rule that accidentally blocked every outbound alert notification your stack attempted to send you that day
- **C.** Not yet having a large enough base of active users to notice the downtime quickly and report it to you through your normal support channels
- **D.** No uptime monitoring—a free tool like UptimeRobot would have alerted you immediately instead of learning from customer complaints.  ✅

> **Answer:** D

### Q15. You have backups but never tried restoring. During a crash, the backup file is corrupted. What pitfall is this?

- **A.** Choosing the wrong backup software — a package version that was incompatible with your specific database engine release
- **B.** Having backups but never testing them—a backup you've never restored is one you hope works. Hope is not a recovery strategy.  ✅
- **C.** Backups always produce valid restorable files as long as the automated configuration was done properly when first set up
- **D.** Your hosting provider bears the full responsibility for verifying that all automated backups are valid, so the corruption is their problem

> **Answer:** B

### Q16. Your server dies and you realize the backup was stored on it. Both database and backup are gone. What pitfall?

- **A.** Selecting a server with insufficient hardware reliability — one that was simply prone to sudden catastrophic failure from the very beginning
- **B.** The server should have been using a RAID disk array to provide hardware-level redundancy, which would have protected both the database and the backup
- **C.** Not purchasing enough storage capacity on the server to maintain multiple backup recovery points side by side, which left only a single copy to rely on
- **D.** Storing backups in the same place as data—if the server dies, the backup dies too. Backups belong on a different server, region, or provider.  ✅

> **Answer:** D

### Q17. You ship a bad update and the app breaks. Your only option is fixing it live while users see errors. What's missing?

- **A.** A more thorough pre-deployment testing process that would have caught this particular bug well before the update ever reached production
- **B.** A rollback plan—the ability to revert to the previous working version with one click, getting back online in seconds instead of debugging live.  ✅
- **C.** A dedicated staging environment where you could have exercised the update against realistic data before pushing anything out to production users
- **D.** A larger development team with more engineers on call, so that someone would always be available to diagnose and fix production bugs quickly under pressure

> **Answer:** B

### Q18. Your recovery plan was never tested. During a real emergency, the runbook references a server that no longer exists. What pitfall?

- **A.** The specific emergency was completely unpredictable, and no reasonable amount of advance preparation could have helped you respond to it any faster
- **B.** Recovery runbooks become outdated so quickly in a moving codebase that keeping them accurate is effectively impossible, and writing them is wasted effort
- **C.** Testing recovery only during a real outage—if the first time you follow your runbook is a real emergency, you find gaps at the worst time. Run drills.  ✅
- **D.** Only large enterprise companies with dedicated operations teams need to schedule regular recovery drill exercises; a solo builder gains nothing from rehearsing recovery

> **Answer:** C

### Q19. Your app goes down and users have no idea what's happening. They tweet complaints and some think you shut down. What was missing?

- **A.** A dedicated public relations team retained to handle your customer communications during any kind of service disruption event
- **B.** A social media monitoring tool that continuously scans the public platforms to detect negative user sentiment about your app in real time
- **C.** Users should simply understand that no application can promise 100% uptime and that occasional outages are normal events for any modern service
- **D.** User communication during outages—a status page or message saying 'we know and we're fixing it' builds trust even during failures.  ✅

> **Answer:** D

### Q20. Do you have uptime monitoring that notifies you within minutes when your app goes down?

- **A.** Uptime monitoring is an unnecessary expense for small applications that have not yet built up a large base of daily users worth protecting
- **B.** This is checklist item one. You need a monitoring service checking your app and alerting you instantly. If not, set one up now—free tools exist.  ✅
- **C.** Checking your application manually once per day by loading the homepage in a browser is a sufficient monitoring routine for an app of your current size
- **D.** Your hosting provider's built-in dashboard systems already handle all of the monitoring for you and will alert you automatically whenever anything at all goes down

> **Answer:** B

### Q21. Do you have automated database backups running? Do you know their frequency and storage location?

- **A.** Database backups are an optional precaution for most apps of this size and can safely be skipped until you have genuinely reached meaningful scale
- **B.** You should have automated backups, know their frequency (= max data loss), and storage location (should be separate from your DB server). Check now.  ✅
- **C.** Running monthly database backups provides completely sufficient protection for any application regardless of how much data its users create between the runs
- **D.** Cloud-hosted databases do not actually need separate backups, because the provider replicates the data and guarantees that absolutely zero loss can ever occur

> **Answer:** B

### Q22. Have you ever actually restored from a backup to prove it works?

- **A.** Restore from a backup at least once to verify. An untested backup might be corrupt, incomplete, or incompatible. Test while calm, not in an emergency.  ✅
- **B.** If the automated backup job completes without reporting any errors, then the resulting backup file is effectively guaranteed to restore correctly
- **C.** Restoration testing is an enterprise practice, and for solo builders or small apps it is unnecessary overhead that adds nothing beyond the backups themselves
- **D.** Your hosting provider already runs automated restoration tests against every backup it stores and formally guarantees recoverability, so testing again would be redundant

> **Answer:** A

### Q23. Do you have a written recovery plan listing what to do when your app goes down?

- **A.** Written recovery plans are only really necessary for large companies with dedicated operations teams and formal compliance obligations to satisfy
- **B.** Even a simple doc: who to contact, how to check logs, how to restore from backup, how to redeploy. Write it while calm so you have it when panicking.  ✅
- **C.** You will naturally remember exactly what steps to take during an emergency, because the adrenaline of a real outage sharpens your focus when it matters most
- **D.** Your AI tool will figure out the correct recovery steps on the fly during the outage itself, so no advance preparation or written documentation is actually needed

> **Answer:** B

### Q24. If you deployed a bad update right now, could you roll back to the previous version in under five minutes?

- **A.** You should be able to roll back to the last working version quickly—most platforms support this. Set up rollback capability now before you need it.  ✅
- **B.** Rolling back to a previous deployment version is not technically possible with modern cloud platforms once a new release has finished going out
- **C.** Five minutes is an unrealistic goal — one full hour is the accepted standard recovery time for most applications, and users generally tolerate that window
- **D.** Best practice is to always fix the broken code and push forward with a new release rather than reverting, because reverting hides the bug instead of solving it

> **Answer:** A

### Q25. Do you know how much data you'd lose if your database crashed right now, based on backup frequency?

- **A.** Know this number. Daily backups = 24hr worst-case loss. Hourly = 1hr. Know your number and decide if it's acceptable or if you need more frequent backups.  ✅
- **B.** Data loss is essentially impossible with modern cloud databases, because they replicate everything automatically across multiple machines as you go
- **C.** Data loss only occurs in poorly built applications, and a well-built system with clean code is inherently protected from losing records in a crash of any kind
- **D.** Your AI tool can reconstruct and recover any lost database records after a crash by regenerating them from cached state, so the backup schedule makes very little difference

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/102901722_
