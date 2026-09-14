---
course: "The Vault"
module: "Module 5 — Secrets & Environment Security"
lesson: "Module 5: Secrets & Environment Security — Exam"
type: "course_quiz"
post_id: 104378671
space_id: 24302166
source: "https://the-faction.mn.co/posts/104378671"
updated: "2026-08-27T20:10:51Z"
---

# Module 5: Secrets & Environment Security — Exam

> Exam for **Module 5 — Secrets & Environment Security** (The Vault) — 25 questions. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI generates a payment integration with the Stripe secret key hardcoded directly in the checkout handler. What is your first action?

- **A.** Move the key into an environment variable and update the handler to read from server runtime configuration  ✅
- **B.** Delete the handler and direct the AI to regenerate the full payment integration without any embedded keys
- **C.** Push the code to a private repo since private repositories keep source files hidden from the public
- **D.** Add a code comment marking the key as sensitive so future AI-generated prompts will exclude it from output

> **Answer:** A

### Q2. You find a .env file with database credentials in your AI-built project. What must you verify about .gitignore before anything else?

- **A.** That .gitignore uses a wildcard pattern to exclude all files with a dot prefix from repository tracking
- **B.** That the .env entry existed in .gitignore before the .env file was ever staged or committed to version control  ✅
- **C.** That a .gitignore file exists in every subdirectory of the project that could potentially contain environment config
- **D.** That the .env file has its read permissions restricted to just the application process and no other users

> **Answer:** B

### Q3. A developer deletes a file containing an API key and commits the removal. The key is gone from the current codebase. Is it still at risk?

- **A.** Yes, the original commit with the key persists in Git history and is visible to anyone cloning the repository  ✅
- **B.** No, deleting a file and committing that deletion permanently erases all traces of its content from history
- **C.** Only if the repo is public because private repository platforms purge deleted content after about thirty days
- **D.** Only if the commits were never squashed before the push because squashing discards all intermediate file changes

> **Answer:** A

### Q4. Your AI builds a Next.js app with NEXT_PUBLIC_STRIPE_SECRET_KEY in the environment config. What is the security problem?

- **A.** The variable name exceeds the character limit that Next.js deployment platforms enforce on environment values
- **B.** The NEXT_PUBLIC prefix was deprecated in recent framework versions and will trigger a startup failure in production
- **C.** The NEXT_PUBLIC prefix bundles this value into client-side JavaScript where it is visible in every browser  ✅
- **D.** The underscore positions in the variable name conflict with the framework parser preventing correct loading

> **Answer:** C

### Q5. Your CI/CD pipeline prints all environment variables to the deployment log for debugging. What risk does this introduce?

- **A.** The build will fail because most CI/CD platforms block pipelines that attempt to output secret variable values
- **B.** Other stages in the pipeline lose access to the variables after they have been printed to the output log
- **C.** The deployment log file grows too large for the platform to store and credential entries will be truncated
- **D.** Secret values appear in plain text in log files that are retained for weeks and readable by pipeline users  ✅

> **Answer:** D

### Q6. Your AI-built application uses the same database password for development, staging, and production environments. What should change?

- **A.** Generate unique credentials per environment so a compromise in one does not cascade to any others  ✅
- **B.** Keep the shared password and add a different environment prefix to database names for logical isolation
- **C.** Rotate the shared credential more often to reduce the time window when a compromised key remains valid
- **D.** Consolidate to one environment since sharing a credential across multiple servers multiplies the exposure

> **Answer:** A

### Q7. Your production database password has not been rotated since the project launched eighteen months ago. What is the primary risk?

- **A.** The database engine will automatically reject the credential once it exceeds the platform maximum age policy
- **B.** Every person and system that has ever accessed the credential still holds a working password to production  ✅
- **C.** Older passwords become significantly weaker to brute force as the underlying hashing algorithms degrade
- **D.** The hosting provider will flag the account for a compliance violation and suspend access until rotation

> **Answer:** B

### Q8. A teammate shares the production API key in a Slack channel so another developer can test an integration. What should they have done instead?

- **A.** Sent the key in a direct message because DMs are encrypted and do not appear in workspace search
- **B.** Posted the key and deleted the message right after the other developer finished copying it out
- **C.** Created a temporary channel for credential sharing that gets archived once the key is distributed
- **D.** Granted the developer access to the secrets manager so they can retrieve the credential on their own  ✅

> **Answer:** D

### Q9. You direct AI to build a Docker image for production. Where should secrets live instead of being embedded in the Dockerfile or image layers?

- **A.** In a private image layer marked restricted so the container registry hides those layers from view
- **B.** In Docker build arguments since build-time args are automatically stripped from the final image output
- **C.** In the runtime environment or a secrets manager so credentials are injected at container startup only  ✅
- **D.** In the Docker Compose file alongside the service definition because compose files stay outside the image

> **Answer:** C

### Q10. Your app crashes on startup in production but works locally. Logs show a missing environment variable. What preventive pattern should you add?

- **A.** A startup validation check that confirms all required environment variables are present before the app serves traffic  ✅
- **B.** Default fallback values for every environment variable so the application never crashes on a missing credential
- **C.** A deployment script that copies local .env files to production ensuring all configuration values are present
- **D.** Hardcoded backup values in the source code so the application functions even without environment settings

> **Answer:** A

### Q11. You want to verify no secrets were committed anywhere in your repository history. Which approach is most thorough?

- **A.** Search current codebase for strings resembling API key patterns using a text editor find tool
- **B.** Review the last twenty commits by reading each diff output and checking for any credential-like strings
- **C.** Inspect only files listed in .gitignore since those entries indicate which files likely held secret data
- **D.** Run GitLeaks or TruffleHog to scan every commit across all branches for known secret patterns in full  ✅

> **Answer:** D

### Q12. Your AI created a .env file with real credentials. You added .env to .gitignore, but the file was already committed two weeks ago. What now?

- **A.** Nothing further is needed since .gitignore now prevents the .env file from appearing in any future commits
- **B.** Rotate every credential in that file because the values are permanently stored in the commit history  ✅
- **C.** Delete the file and force-push to overwrite the remote so the commit holding the secrets is fully removed
- **D.** Run repository garbage collection to purge unreferenced objects and clear old .env content from history

> **Answer:** B

### Q13. A security audit reveals your frontend JavaScript bundle contains your payment processor secret key. How did this most likely happen?

- **A.** The build tool skipped minification and left the secret key visible in readable cleartext in the output
- **B.** The deployment pipeline injected all server-side environment variables into the client bundle at build
- **C.** The secret was stored under a client-side prefix that tells the framework to include it in the bundle  ✅
- **D.** The payment SDK automatically embeds the merchant secret key in frontend code during initialization

> **Answer:** C

### Q14. You push code with an AWS access key to a public GitHub repo. Within minutes the key is used for unauthorized resources. Why so fast?

- **A.** Automated bots continuously scan public repositories for credential patterns and exploit them fast  ✅
- **B.** GitHub tests all detected credentials against cloud providers and that automated test triggers an alert
- **C.** AWS scans public repositories for its own access key format and creates resources to confirm the match
- **D.** A teammate noticed the push notification in the repository feed and tested the credential themselves

> **Answer:** A

### Q15. Your AI builds an API route that connects to a third-party service. Where should the service credentials live in production?

- **A.** In a config file inside the repository that restricts file-level read access to the server process
- **B.** In platform environment variables or a dedicated secrets manager with access controls and audit logs  ✅
- **C.** In a base64-encoded string inside the route file so the credential is obfuscated from casual review
- **D.** In a separate private repository the production server clones at boot to load all required credentials

> **Answer:** B

### Q16. Your pipeline masks secrets in standard log output. A build error stack trace exposes the database connection string. What failed?

- **A.** Masking was applied only to the deploy stage so earlier pipeline steps were not covered by config
- **B.** Stack traces from the language runtime operate fully outside the layer where pipeline masking is applied
- **C.** The connection string was never registered as a secret so the masking system did not recognize it
- **D.** Log sanitization covered standard output but did not extend to error paths where the secret was printed  ✅

> **Answer:** D

### Q17. You need to give a new team member access to production secrets. What is the safest way to distribute credentials?

- **A.** Send each credential in a separate encrypted email so one compromised message does not reveal all
- **B.** Store credentials in a shared document with access restricted to company domain members
- **C.** Add them to the secrets manager with role-based permissions scoped to only the systems they need  ✅
- **D.** Print the credentials and deliver them in person so no digital trail of the transfer ever exists

> **Answer:** C

### Q18. Your AI uses one environment file for all config including both public settings and secret credentials. What is the concern?

- **A.** A single config file cannot hold more than a platform-set number of entries before the parser overflows
- **B.** Mixing public config and secret values in one file makes auditing which entries need protection harder  ✅
- **C.** The framework treats every entry in the file identically and will bundle all values into the client output
- **D.** Large environment files with many variables degrade application startup performance and increase boot time

> **Answer:** B

### Q19. After a suspected breach, your incident plan calls for immediate credential rotation. What does proper rotation require?

- **A.** Invalidate every potentially compromised credential immediately and issue replacement values to all dependent services  ✅
- **B.** Change only the specific credentials confirmed as accessed during the breach to keep service disruption minimal
- **C.** Update credentials in the secrets manager and wait for the next scheduled deployment to distribute new values
- **D.** Add a second credential set alongside the originals so services can fall back if the new values cause errors

> **Answer:** A

### Q20. Your AI generates a Vite project with VITE_DB_PASSWORD in the environment configuration. What happens with that variable name?

- **A.** Vite will reject that variable at build time because database passwords are blocked from client configuration
- **B.** The variable is available only during the build step and stripped from the final browser output
- **C.** Vite encrypts all variables using its prefix so the password is unreadable despite being included
- **D.** The VITE_ prefix embeds the value in the client bundle where every user can read it in the browser  ✅

> **Answer:** D

### Q21. A junior team member says switching to a private GitHub repository eliminates the risk of exposed secrets in commits. Is this accurate?

- **A.** Yes, private repositories encrypt committed content so secrets in code files are protected from exposure
- **B.** Yes, GitHub scans private repos automatically and redacts detected credentials before anyone views them
- **C.** No, every collaborator with access can view the full commit history including any committed secrets  ✅
- **D.** No, but risk is minimal because private repositories limit access to only the repository owner

> **Answer:** C

### Q22. You direct AI to configure separate development and production environments. What credential separation must you verify?

- **A.** Each environment has unique credentials so a compromise in one does not grant access to the other  ✅
- **B.** Both environments share credentials but point to different database names for logical data separation
- **C.** Development uses hardcoded credentials for speed while production reads from environment variables only
- **D.** Credentials are identical but production enforces an extra authentication layer development does not use

> **Answer:** A

### Q23. Your secrets manager supports automatic credential rotation. What must your application also handle for seamless rotation?

- **A.** The application must fully restart every time the secrets manager rotates a credential to load the value
- **B.** A developer must manually update application environment variables each time a credential gets rotated
- **C.** The secrets manager must pause all currently active database connections during rotation to prevent login errors
- **D.** The application must fetch current credentials from the secrets manager at connection time not from cache  ✅

> **Answer:** D

### Q24. Your AI adds a health check endpoint returning database connection status including host and port details. Is this a security concern?

- **A.** No, host and port are routine infrastructure details that do not qualify as secrets and are safe
- **B.** Yes, revealing database host and port provides attackers with specific targeting information for your systems  ✅
- **C.** Only if the endpoint is unauthenticated since requiring a login prevents any unauthorized access
- **D.** Only if the database host is a public IP because internal hostnames cannot be resolved externally

> **Answer:** B

### Q25. A secrets audit on your AI-built application returns a clean result with zero issues. How often should this audit be repeated?

- **A.** Only after a confirmed incident since a clean audit means the configuration is secure until breached
- **B.** Once per year during an annual review to check whether any new secrets have entered the codebase
- **C.** On a regular schedule and after every major change because new AI-generated code may add exposures  ✅
- **D.** No repeat is needed since a clean result confirms the secrets management setup is permanently sound

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/104378671_
