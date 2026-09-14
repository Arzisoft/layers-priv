---
course: "The Mastery"
module: "Module 5 — Deployment & Infrastructure"
lesson: "Module 05: SaaS Deployment Pipelines — Exam"
type: "course_quiz"
post_id: 103821129
space_id: 24191170
source: "https://the-faction.mn.co/posts/103821129"
updated: "2026-08-21T01:50:30Z"
---

# Module 05: SaaS Deployment Pipelines — Exam

> Exam for **Module 5 — Deployment & Infrastructure** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. You deploy a new version. The deployment succeeds but customers report a broken checkout flow. Your team spends 45 minutes debugging. What should have caught this faster?

- **A.** Post-deploy health checks that test critical flows like checkout, login, and API responses on time  ✅
- **B.** Customers finding issues in production is the fastest detection but the worst experience
- **C.** A longer and more thorough manual QA process completed before each deployment reaches production apps
- **D.** Manual testing performed by the developer who authored the change before they deploy it to production

> **Answer:** A

### Q2. Your team deploys on Friday at 4pm. A subtle bug causes data exports to fail. Nobody checks until Monday morning. What practice would have reduced this risk?

- **A.** Deploy only on Mondays when the full engineering team is available to monitor for issues all week
- **B.** Deploy more frequently through the week so each change stays smaller and safer to ship
- **C.** Avoid late Friday deploys — if you must, ensure monitoring catches issues in minutes, not days  ✅
- **D.** Require all team members to be available over the weekend after any Friday deployment is shipped out

> **Answer:** C

### Q3. Your pipeline runs tests, builds, and deploys in a single step. If tests pass but the build fails, the old version is torn down before the new one is ready. What is wrong?

- **A.** The tests caught the build issue so the pipeline is working correctly and there's no real problem
- **B.** The old version was removed before the new one was ready — keep old running until new passes all checks  ✅
- **C.** Revert to the previous commit and fix the failing tests before attempting any redeployment at all
- **D.** Skip the failing tests temporarily and deploy the new version to production without waiting for CI

> **Answer:** B

### Q4. You want to test a new pricing page design with 10% of users before rolling it out to everyone. Your deployment is all-or-nothing. What capability do you need?

- **A.** Feature flags are unnecessary — just deploy directly and fix issues if they come up later
- **B.** Deploy the new design to production for everyone and roll back if customer complaints come in fast
- **C.** Create a completely separate app instance running the new design and redirect selected users there
- **D.** Feature flags — deploy the new design but show it to only 10% of users via a flag, no extra push  ✅

> **Answer:** D

### Q5. Your deploy process involves manually uploading files via FTP. Last week, incomplete files were uploaded and the app crashed. What should replace this?

- **A.** A shared staging server where developers manually upload files to test their changes
- **B.** Automated deployment from Git — push to main, CI runs tests, platform deploys the verified build  ✅
- **C.** FTP uploads directly to the production server with a checklist to verify each file was transferred
- **D.** Email the code changes to the ops team who review and manually deploy during the maintenance window

> **Answer:** B

### Q6. Your feature flags are stored in a JSON config file deployed with the app. Toggling a flag requires a code change, commit, and redeploy. What should change?

- **A.** Keep the JSON file but add detailed comments so developers know exactly what each flag controls
- **B.** Schedule flag changes for the weekly release train so toggles always ship with other code changes
- **C.** Store flags in browser cookies so each user can toggle their own features without any deploys
- **D.** Move flags to a runtime service or database so they can be toggled instantly without a redeploy  ✅

> **Answer:** D

### Q7. A developer accidentally pushes directly to 'main', triggering an unreviewed production deploy. What protection should be in place?

- **A.** Developers should know never to push to main — team discipline matters more than tools
- **B.** Branch protection rules requiring PR reviews before merge — with direct push to main disabled  ✅
- **C.** Create a separate production branch and only deploy from that branch instead of deploying from main
- **D.** Add a manual deployment approval step that runs after the push to main but before going to production

> **Answer:** B

### Q8. You deploy a new feature. Error rates triple in an hour. You need to roll back but have never tested the procedure. It takes 90 minutes to revert. What should have been done?

- **A.** Rollbacks are rare enough that having untested rollback procedures is fine for most engineering teams
- **B.** Document rollback steps more thoroughly in a runbook the team references during incidents
- **C.** Test rollbacks regularly — it should be a one-click operation the team has practiced before crises  ✅
- **D.** Assign one person as the designated rollback operator who handles all rollback procedures for the team

> **Answer:** C

### Q9. Preview deployments use the production database. A developer tests a data migration in preview and corrupts production data. What isolation is missing?

- **A.** Preview deployments should not connect to any database at all — they should be static frontend only
- **B.** Preview environments should be limited to frontend-only changes and never include backend services
- **C.** Developers should be careful when running database migrations in preview environments
- **D.** Preview environments need isolated databases so testing can't affect real customer data or records  ✅

> **Answer:** D

### Q10. Your deployment history shows 47 deploys with no record of what changed in each. A bug appears and you can't correlate it with a specific deploy. What's missing?

- **A.** Deployment logs should only include timestamps and version numbers to keep them clean and readable
- **B.** Verbose logging during deployments causes noise and makes important details harder to find
- **C.** Each deploy should link to its Git commit and PR description so issues trace back to the changes  ✅
- **D.** The team lead should write a manual changelog entry for each deployment in a shared wiki document now

> **Answer:** C

### Q11. Your .env file with production credentials is committed to Git. The repo is private. What's the security issue?

- **A.** Deleting the secrets file from Git and force-pushing removes all traces of exposed credentials now
- **B.** Secrets in Git persist in history even if deleted — anyone with repo access can find them. Use vaults  ✅
- **C.** Hardcoded secrets are acceptable for development environments where security requirements are lower
- **D.** Store secrets in environment variables on the developer's local machine instead of using a vault tool

> **Answer:** B

### Q12. After a major refactor, health checks pass. Two days later, a rarely-used report feature is found broken. Health checks only test login and dashboard. What's the gap?

- **A.** Health checks should cover all critical features — regression suites should run post-deploy everywhere  ✅
- **B.** Rarely-used features don't need automated testing since they won't affect many users if they break
- **C.** The customer should have reported the issue sooner so the team could have caught it before any impact
- **D.** Add the feature to the health check suite only after it breaks — proactive coverage isn't worth the cost

> **Answer:** A

### Q13. Frontend and backend deploy as one unit. A backend API change breaks the frontend deploy, but the backend succeeds. Now they're out of sync. What should change?

- **A.** Deploy frontend and backend together in a single step to ensure they always stay perfectly in sync
- **B.** Use the same codebase for both frontend and backend so they can be deployed together as a single unit
- **C.** Always deploy the backend first and wait a full 24 hours before deploying any frontend updates at all
- **D.** Deploy independently with backward-compatible API changes — failure in one shouldn't break the other  ✅

> **Answer:** D

### Q14. Your hosting provider deprecates your runtime in 30 days. You've never tested upgrading. What ongoing process would have prepared you?

- **A.** Infrastructure should never be updated once it's stable — changes introduce unnecessary risk always
- **B.** Update only when a critical vulnerability appears — proactive updates waste engineering effort
- **C.** Regular dependency and runtime updates tested in staging keep infrastructure current and prepared  ✅
- **D.** Delegate all infrastructure updates to the hosting provider so the team doesn't need to manage them

> **Answer:** C

### Q15. Your CI warns but doesn't block deploys when tests fail. A developer sees a failure, assumes it's a flake, and deploys. The test was catching a real bug. What should the pipeline enforce?

- **A.** Failed tests should block deployment — with a documented process for marking known flakes separately  ✅
- **B.** Warning emails from the CI system are sufficient — developers will read them and fix test failures
- **C.** All test failures should be fully investigated and resolved before any deployment proceeds to production
- **D.** Run the failing tests again automatically to check for flakes before blocking the deployment pipeline

> **Answer:** A

### Q16. You need to deploy a critical payment hotfix. Your standard process takes 45 minutes. Customers are losing money. What should your pipeline support?

- **A.** Skip running the full test suite entirely for speed — hotfixes are small enough to ship safely untested
- **B.** An expedited path for hotfixes — targeted testing on the fix, with full regression running post-deploy  ✅
- **C.** Deploy the hotfix directly from the developer's laptop to avoid the overhead of the full CI/CD pipeline
- **D.** Follow the standard 45-minute CI/CD process regardless of urgency — consistency prevents more errors

> **Answer:** B

### Q17. There's no staging step in your pipeline — tests pass and code deploys directly to production. Where do environment-specific bugs get caught?

- **A.** Production is the only truly reliable test environment — staging never catches environment-specific bugs
- **B.** Environment-specific bugs are rare enough to handle in production when customers report them
- **C.** Developers should test locally using production settings copied to their development environment config
- **D.** Add a staging step between testing and production — staging mirrors production to catch env issues  ✅

> **Answer:** D

### Q18. You deploy a change that drops a database index. Queries go from 50ms to 12 seconds. Your pipeline has no performance benchmarks. What should trigger an alert?

- **A.** 12-second queries will eventually be noticed by customers and reported to the support team
- **B.** Performance monitoring is a separate concern from deployment and should be handled by a different team
- **C.** Automated performance thresholds — if response times exceed limits post-deploy, alert and rollback  ✅
- **D.** Ask customers to report slow performance through support channels so the team can investigate manually

> **Answer:** C

### Q19. Your single-service app is splitting into frontend and backend services. Your single pipeline can't handle independent deploys. What do you need?

- **A.** Separate CI/CD pipelines per service with API versioning to ensure cross-service compatibility works  ✅
- **B.** Keep everything in one monolithic service to avoid the complexity of multiple pipelines
- **C.** Deploy both services simultaneously in a single coordinated step to guarantee they always stay in sync
- **D.** One service should explicitly depend on the other service's deployment completing before it can start

> **Answer:** A

### Q20. Infrastructure-as-code files were written 6 months ago. Manual server changes have drifted actual config from what the files describe. What prevents this?

- **A.** Manual configuration by the ops team ensures each environment is set up exactly as intended
- **B.** Enforce all changes through config files and regularly verify infrastructure matches defined state  ✅
- **C.** Infrastructure drift is expected and normal — teams should fix discrepancies when they cause issues
- **D.** Document the ideal server configuration in a wiki and trust the team to follow it during every setup

> **Answer:** B

### Q21. Your migration renames name to full_name. You deploy migration and code together. For 30 seconds some servers read name while the database has full_name. What is the safe pattern?

- **A.** Add full_name alongside name first, deploy code that handles both, migrate data, then drop the old  ✅
- **B.** Deploy faster so the window between old schema and new schema is as short as possible for users
- **C.** Rename the database column back to its original name if any errors occur during the migration step
- **D.** Schedule all database migrations during planned maintenance windows to avoid disrupting live users

> **Answer:** A

### Q22. Your staging environment uses the same Stripe API keys as production. A developer tests a refund in staging and refunds a real customer. What caused this?

- **A.** Staging environments should not have any access to live payment processing systems at all times
- **B.** The developer who triggered the refund should have been more careful with the test credentials
- **C.** Staging must use Stripe test-mode keys so test operations don't affect real customers or charges  ✅
- **D.** Stripe's built-in safeguards automatically prevent test-mode refunds from affecting real charges

> **Answer:** C

### Q23. Your CI runs 240 tests taking 18 minutes. Developers avoid deploying because feedback is too slow. Deploys accumulate into large, risky batches. What should you optimize?

- **A.** Parallelize tests, cache dependencies, and identify slow tests — fast CI enables frequent deploys  ✅
- **B.** 20-minute CI runs are normal for mature SaaS applications and don't need to be optimized further
- **C.** Remove the slowest tests from CI and run them manually before major releases to save pipeline time
- **D.** Switch to a faster CI provider — the slow pipeline is likely caused by the current provider hardware

> **Answer:** A

### Q24. Your app serves US and EU customers from a single US region. EU customers see 300ms latency. What deployment architecture would fix this?

- **A.** 300ms latency is acceptable for EU customers and doesn't warrant any infrastructure changes or spend
- **B.** Cache all API responses at the CDN layer to reduce latency regardless of where the user is located
- **C.** Ask EU customers to use a VPN that routes through the US region for a faster connection experience
- **D.** Multi-region deployment with region-aware routing so each customer hits the nearest server location  ✅

> **Answer:** D

### Q25. After deploys, the team manually clicks around for 2 minutes and declares it working. A payment bug is found 3 hours later by a customer. What's the gap?

- **A.** Automated synthetic monitoring should test critical flows continuously after deploys, not manually  ✅
- **B.** Two minutes of manual testing after each deploy is thorough enough to catch most critical issues
- **C.** Add a 24-hour waiting period after each deploy before considering it successful and fully complete
- **D.** Ask customers to report issues after each deployment through a dedicated feedback form on the site

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/103821129_
