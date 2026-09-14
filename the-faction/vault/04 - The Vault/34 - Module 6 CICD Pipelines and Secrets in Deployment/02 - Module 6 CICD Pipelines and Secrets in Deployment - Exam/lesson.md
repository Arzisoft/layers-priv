---
course: "The Vault"
module: "Module 6: CI/CD Pipelines and Secrets in Deployment"
lesson: "Module 6: CI/CD Pipelines and Secrets in Deployment — Exam"
type: "course_quiz"
post_id: 107142740
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142740"
updated: "2026-09-10T20:02:27Z"
---

# Module 6: CI/CD Pipelines and Secrets in Deployment — Exam

> Exam for **Module 6: CI/CD Pipelines and Secrets in Deployment** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder asks how a GitHub Actions workflow should get a Stripe key. What separation does this module describe?

- **A.** The workflow reads the key from a .env file committed beside it, since files keep the pipeline self-contained
- **B.** The workflow requests the key from Stripe at run start, since providers are the safest source of their own values
- **C.** The workflow file references the name from the encrypted store; the value never appears in the YAML itself  ✅
- **D.** The key is passed as a plain build argument on each run, typed by whoever triggers the deployment that day

> **Answer:** C

### Q2. A teammate pastes a token directly into the workflow YAML "temporarily." How does this module classify that file?

- **A.** The YAML is code, committed and visible to the team: a value pasted there is a committed secret, full stop  ✅
- **B.** The YAML is configuration, so pasted values are acceptable as long as the repository remains private
- **C.** The YAML is ephemeral, since workflow files are consumed at run time and not retained in history
- **D.** The YAML is encrypted at rest by the CI provider, which makes pasted values fully equivalent to stored ones

> **Answer:** A

### Q3. A builder asks when each secret should be available to the pipeline. Which rule does this module give?

- **A.** All secrets available to all of the stages, since missing values are the single leading cause of failed deployments
- **B.** Secrets available only on the final deploy stage, since earlier stages can always run without them
- **C.** Secrets available only on manual runs, since scheduled runs are where the unattended leaks happen most
- **D.** Give each secret to the stage that needs it and no other: build-time and runtime are different exposure windows  ✅

> **Answer:** D

### Q4. A runtime database URL is passed into the build stage unnecessarily. What risk does this module name?

- **A.** Build slowdown, since extra environment variables enlarge the build context the runner must load
- **B.** The secret can be baked into the artifact: what the build embeds, the artifact carries and can publish  ✅
- **C.** Version skew, since build-stage values can differ from the runtime values that later replace them in production
- **D.** Cache invalidation, since environment changes force full rebuilds and multiply the minutes billed

> **Answer:** B

### Q5. A failing job tempts a builder to add a step that prints the environment. What does this module say about that instinct?

- **A.** Never echo env vars for debugging: CI logs are written, stored, and shared, every secret the job holds lands in them  ✅
- **B.** It is safe on GitHub Actions specifically, since the platform strips all environment output from all its stored logs
- **C.** It is fine for jobs that only hold test credentials, since test-mode values sit outside the working leak definition
- **D.** It is acceptable just this once, provided the entire log is deleted immediately after the debugging session concludes

> **Answer:** A

### Q6. A builder trusts log masking to keep secrets safe. What limit does this module put on that trust?

- **A.** Masking works only on the first occurrence per log file, so repeated values appear in clear text after that point
- **B.** Masking is enterprise-only, so most ordinary repositories never receive the replacement behavior at all
- **C.** Masking covers what the store knows: derived values, encoded copies, and echoed config walk straight through  ✅
- **D.** Masking delays log delivery, so busy teams disable it in practice and the protection rarely operates

> **Answer:** C

### Q7. During an audit, a connection string is found in a month-old CI log. What does this module direct?

- **A.** Delete the log and move on, since removing the artifact removes the exposure it represented
- **B.** Treat any secret that appeared in a log as leaked: rotate it now, following the emergency order  ✅
- **C.** Check download counts on the log first, since exposure only counts once someone has retrieved it
- **D.** Restrict log access going forward, since permissions changes address the finding without any rotation at all

> **Answer:** B

### Q8. A Dockerfile copies .env into the image, and a later step deletes the file. What does this module say the image now contains?

- **A.** Nothing sensitive, since the deletion step removed the file from the final filesystem the container sees
- **B.** An encrypted remnant, since Docker encrypts intermediate layers that later steps mark as deleted
- **C.** A harmless reference, since .env files are excluded from layer archives by the container runtime
- **D.** The secret, permanently: the COPY layer remembers forever, and deleting in a later step changes nothing  ✅

> **Answer:** D

### Q9. A docker build needs an npm registry token. Which pattern does this module direct?

- **A.** A BuildKit secret mount injecting the token without layering, in a multi-stage build discarding the touched stage  ✅
- **B.** A plain ARG passed at build time, since build arguments are stripped from the finished image automatically anyway
- **C.** Hardcoding the token in the Dockerfile with a comment to rotate it later on, since registry tokens are low value
- **D.** Copying the token file in, using it, and deleting it in the same RUN command, since single-layer deletion is clean

> **Answer:** A

### Q10. A builder asks how the running container should receive its database URL. What does this module say, and what backstop goes with it?

- **A.** Baked directly into the image at build time for reliability, with the image registry permissions as the backstop
- **B.** Fetched from a public gist at container start, with the gist URL rotated monthly as the backstop
- **C.** Injected as env at container start, with .dockerignore excluding .env as the backstop against accidental copies  ✅
- **D.** Read from a volume-mounted .env committed to the infra repo, with branch protection as the backstop

> **Answer:** C

### Q11. A pipeline stores long-lived AWS keys in repo secrets for deploys. What modern replacement does this module point to?

- **A.** Encrypting the keys twice before storage, since layered encryption is what the cloud vendors now recommend
- **B.** Moving the keys into the Dockerfile, since image-embedded credentials avoid the CI store entirely and cleanly
- **C.** Rotating the stored keys every week, since raw frequency is the only real lever available for pipeline credentials like these
- **D.** OIDC federation: the pipeline proves its identity and receives short-lived credentials per run, no stored cloud keys at all  ✅

> **Answer:** D

### Q12. A team wants production deploy secrets gated more tightly than the rest. Which mechanism from this module fits?

- **A.** A second repository holding only the production workflows, since repo boundaries are the strongest gate available anywhere
- **B.** Environment-scoped secrets with protection rules: production values only reach production jobs, behind required reviewers  ✅
- **C.** A naming convention marking production secrets, relied on by every workflow author to self-enforce it correctly
- **D.** Manual entry of production values at each deploy, since human-typed secrets never sit in any store at all

> **Answer:** B

### Q13. A maintainer considers enabling secret access for pull requests from forks. What does this module say?

- **A.** The default is safe and stays on: enabling secrets for fork PRs hands your credentials to anyone who opens one  ✅
- **B.** Enable it for trusted contributors only, since fork risk tracks the reputation of the fork author
- **C.** Enable it freely: fork PR jobs run in isolated sandboxes that cannot exfiltrate the values they hold
- **D.** The setting matters only for public repos with over a thousand stars, where fork volume finally gets adversarial

> **Answer:** A

### Q14. One token in a pipeline builds, deploys, and administers everything across all environments. What does this module call this?

- **A.** A root credential pattern, acceptable in CI because pipeline runs are short and supervised by their triggers
- **B.** An efficiency win, since fewer credentials means fewer entries to rotate when offboarding happens
- **C.** A platform default, harmless because CI providers scope tokens automatically behind the scenes
- **D.** A god token: one compromised run compromises everything, which is why scope goes per job, per environment  ✅

> **Answer:** D

### Q15. A builder asks whether the pipeline's own deploy token needs lifecycle management. What does this module answer?

- **A.** No: pipeline credentials are internal machinery, sitting outside the rotation discipline that covers app secrets
- **B.** Yes: the pipeline's own credentials rotate like any other secret, on schedule and at every exposure event  ✅
- **C.** Only after an incident, since deploy tokens are low-value until a compromise proves otherwise to the team
- **D.** No, provided the token is scoped, since narrow permissions substitute for expiry and rotation together

> **Answer:** B

### Q16. You direct AI to write a GitHub Actions workflow. Which instruction matches this module?

- **A.** All secrets referenced from the store, environment-scoped for production, and no step that echoes env vars or prints config  ✅
- **B.** Secrets inlined for readability during review, moved to the store in a cleanup pass right after the launch
- **C.** A debug job that dumps the entire environment on failure, disabled by default but ready whenever it is needed
- **D.** Values duplicated into the workflow as comments, so reviewers can verify the store contents match exactly

> **Answer:** A

### Q17. You direct AI to review an existing workflow file. Which finding list does this module specify?

- **A.** Job names, runner versions, and the marketplace actions used, since dependency hygiene is the core review
- **B.** Total runtime minutes and cache hit rates, since cost is where misconfigured pipelines surface first and loudest
- **C.** Hardcoded values, secrets passed to build steps that only runtime needs, output that could contain secrets, fork PR exposure  ✅
- **D.** YAML formatting, indentation depth, and comment coverage, since maintainability is the leak that compounds

> **Answer:** C

### Q18. You direct AI to convert a Dockerfile for safe secret handling. What confirmation does this module require in the prompt?

- **A.** That the image builds faster than before, since multi-stage conversion is fundamentally an optimization
- **B.** That the image size shrank, since smaller images are the measurable proxy for fewer embedded values
- **C.** That the base image is the latest tag, since up-to-date bases are what remove inherited secrets
- **D.** That no layer in the final image contains the secret, and that .env is excluded via .dockerignore  ✅

> **Answer:** D

### Q19. You set up OIDC between a repo and AWS. What final step does this module include in the prompt?

- **A.** Remove the stored AWS keys from the repo secrets afterward: the federation replaces them, and leftovers are legacy risk  ✅
- **B.** Duplicate the stored AWS keys into the OIDC role, since federation wraps existing credentials rather than replacing them
- **C.** Post the role ARN in the team channel, since OIDC roles are public identifiers meant for team visibility
- **D.** Grant the role administrator access, since narrow roles break deploys in ways that are genuinely hard to debug

> **Answer:** A

### Q20. What does the CI log audit prompt in this module look for, and what follows a finding?

- **A.** Failed jobs from the last month; each failure gets a retry to confirm the pipeline still works
- **B.** Anything that looks like a key, token, or connection string; findings get listed so they can be rotated  ✅
- **C.** Deprecated action versions; each finding gets an upgrade PR to keep the workflow supported
- **D.** Steps with runtimes over five minutes; each finding gets cached to bring the pipeline back under budget

> **Answer:** B

### Q21. In the module's inherited-pipeline scenario, why is the hardcoded Supabase key rotated rather than just moved to the store?

- **A.** Because Supabase requires rotation on any configuration change, as a standing condition of platform support
- **B.** Because the move changes the key format, and reformatted keys stop validating against the old stored records
- **C.** Because it sat in git history and in every log of every run: moving it does not unpublish it, only rotation ends the exposure  ✅
- **D.** Because stored secrets must be created fresh, since the CI store rejects values that existed elsewhere first

> **Answer:** C

### Q22. A builder asks where runtime secrets for a Vercel-deployed app should live. What does this module answer?

- **A.** In the platform env settings: the runtime path for Jamstack deploys, never inside the built artifact  ✅
- **B.** In the repository as an encrypted blob the app decrypts at start, keeping the platform out of the loop
- **C.** In the CDN configuration, since edge distribution is where runtime configuration naturally belongs
- **D.** In the client bundle behind obfuscation, since runtime by definition means the browser environment

> **Answer:** A

### Q23. Beyond images, which build outputs does this module warn can carry embedded secrets?

- **A.** Only compiled binaries, since interpreted-language artifacts are read at run time and hold no baked values
- **B.** Bundles, sourcemaps, and cached dependencies: all can carry embedded values if the build was careless  ✅
- **C.** Only test reports, since assertion output is the one place raw configuration values get written
- **D.** None: modern bundlers strip anything that looks like a credential before writing the output

> **Answer:** B

### Q24. A team runs Doppler and also maintains dozens of scattered GitHub repo secrets by hand. What does this module suggest?

- **A.** Keep both systems, since redundant stores mean the pipeline survives an outage of either one
- **B.** Move everything to repo secrets, since the CI-native store always beats an external manager
- **C.** Alternate between them by quarter, so the team stays practiced in both of the storage systems
- **D.** Use the manager's CI integration: synced, centrally rotated values replace the scattered hand-maintained ones  ✅

> **Answer:** D

### Q25. Looking across this whole module, what is the governing principle of secrets in CI/CD?

- **A.** Pipelines are trusted by definition: whatever runs unattended has already been reviewed, so secrets flow freely inside it
- **B.** Speed is the discipline: the shorter the pipeline, the smaller the exposure, whatever the configuration
- **C.** Secrets flow in at the stage that needs them and never flow out: not into logs, not into artifacts, not into layers  ✅
- **D.** Masking is the foundation: a provider that hides values in logs has solved pipeline secrecy end to end

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/107142740_
