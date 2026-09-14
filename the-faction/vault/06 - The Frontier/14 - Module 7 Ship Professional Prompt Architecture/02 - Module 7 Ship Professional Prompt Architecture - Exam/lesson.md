---
course: "The Frontier"
module: "Module 7: Ship: Professional Prompt Architecture"
lesson: "Module 7: Ship: Professional Prompt Architecture — Exam"
type: "course_quiz"
post_id: 106162168
space_id: 24391596
source: "https://the-faction.mn.co/posts/106162168"
updated: "2026-08-21T15:23:18Z"
---

# Module 7: Ship: Professional Prompt Architecture — Exam

> Exam for **Module 7: Ship: Professional Prompt Architecture** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. You are kicking off your capstone: a support bot handling 10K conversations a day. Before writing a single instruction, what should you produce first?

- **A.** A requirements list covering what the system must do, must never do, its format contracts, and its failure tolerances  ✅
- **B.** A library of proven prompts from similar support bots so you can adapt battle tested wording to your own use case
- **C.** A final model selection and a token budget, since every later architecture decision depends on the exact model chosen
- **D.** A polished first draft of the full system prompt, because real requirements only surface once you see live model responses

> **Answer:** A

### Q2. Your brand voice pipeline crams identity, retrieved docs, and the current task into one prompt block. You rebuild it as a layered system. Where do identity, rules, and format contracts live?

- **A.** In the task layer, restated on every request so the model never loses sight of the format contract during long runs
- **B.** In the stable system layer, so you can edit other layers, rerun the tests, and ship without touching the core rules  ✅
- **C.** In the dynamic context layer, injected fresh on each request next to the retrieved documents and current user data
- **D.** Duplicated across all three layers, so a failure in any one layer still leaves the rules intact in the other two

> **Answer:** B

### Q3. You are wiring retrieval into your layered support bot so answers cite current policy docs. In the three layer architecture, where do retrieved documents and user data belong?

- **A.** In the stable system layer, since policy documents are core rules the model should treat as permanent instructions
- **B.** In the task layer, appended right after the user request so the model reads the freshest material at the very end
- **C.** In a separate fourth layer outside the architecture, kept apart so retrieval failures cannot affect the prompt
- **D.** In the dynamic context layer, injected per request so content changes without touching system rules or the tests  ✅

> **Answer:** D

### Q4. A teammate asks why v2.3.1 of your extraction prompt phrases the refund policy the way it does. In a professional setup, where does the answer live?

- **A.** In your memory and chat history, since the author is the natural source of truth for the reasoning behind wording
- **B.** In the model provider's release notes, which explain why certain phrasings work better after each model update
- **C.** In the repo: the changelog entry for that version plus the eval results that justified shipping the change  ✅
- **D.** In the production dashboard, where metrics show which phrasing variants performed best in live traffic

> **Answer:** C

### Q5. You are writing maintenance docs before handing your prompt system to another builder. Per the module, which four questions must the docs answer?

- **A.** Who wrote each section, when it shipped, which model it targets, and which stakeholders approved the final wording
- **B.** What the business goal is, who the users are, what the budget allows, and when the next scheduled rewrite happens
- **C.** What each section does, why it is written that way, what breaks if you change it, and how to run the test suite  ✅
- **D.** Which layers exist, which files hold them, which branch is live, and which alerts page the on call builder

> **Answer:** C

### Q6. You think your handoff docs are finished. Per the module, what is the standard that proves they actually are?

- **A.** Every section of the prompt has an inline comment, so a reader can trace any instruction back to a requirement
- **B.** The docs pass an AI audit with zero warnings, showing that no section is ambiguous to a fresh model reviewer
- **C.** Your team lead signs off after a walkthrough where you explain each design decision and its history
- **D.** An engineer who has never seen your system can read them and then ship a safe change within a single day  ✅

> **Answer:** D

### Q7. You fixed a nasty failure mode where oversized inputs broke JSON output. Why does the module insist you document that fix in the maintenance docs?

- **A.** Because auditors require a record of every defect before a prompt system can be certified for production traffic
- **B.** Because documenting fixes shows measurable progress that justifies your time investment to project stakeholders
- **C.** Because without the record, the next engineer will not know the trap exists and will reintroduce the fixed bug  ✅
- **D.** Because the changelog needs matching entries or the semantic version numbers will drift out of sync with git

> **Answer:** C

### Q8. Your extraction system just went live. Following the module, what should your production dashboard track continuously?

- **A.** Total token spend and daily request volume, since cost is the only metric that changes meaningfully after launch
- **B.** Format compliance, accuracy on sampled outputs, escalation rates, latency, and the cost of every single request  ✅
- **C.** User satisfaction survey scores gathered monthly, which capture quality better than automated measurement does
- **D.** Model provider status pages and uptime, because output quality is stable once a prompt has passed evaluation

> **Answer:** B

### Q9. Your dashboard shows healthy overall averages, but the module says to keep sampling real traffic continuously. Why?

- **A.** Because aggregates hide drift; a growing failure in one slice of traffic can vanish inside a healthy average  ✅
- **B.** Because sampling is cheaper than aggregates, letting you cut monitoring cost while keeping coverage
- **C.** Because users complain long before dashboards move, so manual reading of raw outputs beats automated tracking
- **D.** Because providers throttle accounts that query aggregate metrics too often, so sampling avoids the rate limits

> **Answer:** A

### Q10. Overnight, malformed JSON from your extractor rises from near zero to 2 percent of requests. How does the module say to treat this?

- **A.** As a rounding error to log and review at the next sprint, since 98 percent compliance still beats most systems
- **B.** As a fire alarm: investigate immediately, because a small format drift can silently corrupt downstream data  ✅
- **C.** As a retry problem: add automatic reruns for malformed outputs and revisit the prompt only if reruns also fail
- **D.** As a user input problem: tighten upstream validation, since prompts rarely change behavior on their own

> **Answer:** B

### Q11. Your support bot's sampled quality scores sag this week. You shipped no prompt changes and traffic looks normal. What does the module say to suspect?

- **A.** A regression suite gap, meaning a recent green test run masked a prompt edit that actually broke production
- **B.** Seasonal user behavior, which shifts scores in ways no monitoring or architecture decision can meaningfully catch
- **C.** An upstream model update quietly changing behavior underneath you, which continuous monitoring exists to catch  ✅
- **D.** Evaluator decay, since sampled quality scoring drifts on its own and should be recalibrated on a fixed schedule

> **Answer:** C

### Q12. Your bot keeps misreading a format rule and fumbling an edge case you never specified. Failures look instruction shaped. What does the module prescribe?

- **A.** Change the model, since format misreads signal a capability ceiling that no amount of prompt work can cross
- **B.** Refactor the prompt: instruction shaped failures mean clearer rules and coverage for the missing edge case  ✅
- **C.** Add a review pass with the same model, letting it catch its own format misreads before output ships
- **D.** Lower the quality bar temporarily and gather more production data before deciding on any structural change

> **Answer:** B

### Q13. Your best three prompt candidates all plateau below the quality bar on the same eval set. Per the module's framework, what is the right move?

- **A.** Change the model: the shared plateau signals a capability ceiling, and more rewording just burns shipping time  ✅
- **B.** Merge the three candidates into one hybrid prompt, since each variant likely solves a different failure slice
- **C.** Expand the eval set first, because three plateaus usually mean the test cases are too hard rather than the model
- **D.** Keep iterating wording, since three candidates is a small sample and the next variant may clear the quality bar

> **Answer:** A

### Q14. A stakeholder wants a one word tone tweak in your live support prompt, shipped today. What must happen before that change deploys?

- **A.** A quick manual spot check of five sample conversations, since a single word cannot alter structured output rules
- **B.** A staged rollout to 5 percent of traffic, because production data is the only trustworthy test of a tone change
- **C.** The full regression suite runs and passes, because even a one word tweak can silently break format compliance  ✅
- **D.** An architecture decision record documenting the tweak, so the changelog explains the stakeholder request context

> **Answer:** C

### Q15. You built a strong eval suite in Module 5. Now you are shipping the capstone. How does that suite carry into production, per the module?

- **A.** It retires at launch, replaced by live monitoring, since production traffic makes offline test cases redundant
- **B.** It becomes the regression gate: a fixed set of representative and adversarial cases run before any change ships  ✅
- **C.** It becomes training material for the next model, seeding few shot examples drawn from your best scoring runs
- **D.** It runs quarterly as an audit, providing a periodic health check that is independent from daily deployments

> **Answer:** B

### Q16. A fellow builder ships one giant prompt that handles everything for their app. It works today. What does the module warn is the real cost?

- **A.** Every future change risks everything at once, and no one but the original author can safely maintain the system  ✅
- **B.** Token spend, since monolithic prompts always cost more per request than the same content split across layers
- **C.** Latency, because long prompts slow every response even when most of the content is irrelevant to the request
- **D.** Model lock in, since giant prompts exploit the quirks of one model and cannot transfer to a different one later

> **Answer:** A

### Q17. You inherit a prompt folder full of files named final_v2_REAL and final_v2_REAL_fixed. Per the module, what has this versioning style actually destroyed?

- **A.** Team morale, since messy file names signal sloppy work and make new engineers distrust the whole prompt system
- **B.** Nothing critical yet, since file contents matter more than names and a cleanup pass can restore order anytime
- **C.** Prompt quality itself, because untracked edits accumulate contradictions that gradually degrade model output
- **D.** The ability to roll back, diff versions, or tie a production incident to the specific change that caused it  ✅

> **Answer:** D

### Q18. You just made a major design call: splitting extraction into two stages instead of one. What does the module say belongs in an architecture decision record?

- **A.** What you decided, why you decided it, and which alternatives you considered and rejected along the way  ✅
- **B.** The full prompt text of both stages, so the record doubles as a backup if the repo history is ever lost
- **C.** The eval scores of the winning design only, keeping records lean by omitting options that did not ship
- **D.** A meeting transcript with every stakeholder comment, preserving the complete context of the discussion

> **Answer:** A

### Q19. Your system tested perfectly at launch, so a teammate suggests scaling back monitoring to save budget. What does the module say about this?

- **A.** Reasonable: once a regression suite guards every change, live monitoring duplicates coverage you already have
- **B.** Reasonable if you keep cost tracking, since spend is the only metric that moves without a prompt change landing
- **C.** Wrong for new systems only: mature prompt systems stabilize after a quarter and can drop most monitoring
- **D.** Wrong: model updates and shifting traffic degrade systems that tested perfectly, so operations need monitoring  ✅

> **Answer:** D

### Q20. One prompt in your pipeline classifies the ticket, extracts fields, and drafts the reply, and quality is wobbling on all three. What is the architectural fix from the module?

- **A.** Add stronger emphasis and repetition for each duty inside the prompt so the model weights all three equally
- **B.** Split the work into stages, giving each task its own prompt so each piece can be tested and shipped alone  ✅
- **C.** Move all three duties into the system layer, where stable placement gives the model more consistent focus
- **D.** Route the whole prompt to a larger model, since juggling several duties is purely a capability question

> **Answer:** B

### Q21. During a pre ship audit, you find a test that still passes when the instruction it targets is deleted from the prompt. What does the module say this means?

- **A.** The test asserts nothing real; it gives false confidence and the instruction is effectively shipping unguarded  ✅
- **B.** The instruction is redundant and should be deleted, since the model behaves identically without it in place
- **C.** The test is extra safe, since passing under both conditions shows the behavior is robust to prompt changes
- **D.** The eval set is too large and needs pruning, because overlapping tests mask which instruction owns a behavior

> **Answer:** A

### Q22. Your audit reveals the bot has no defined behavior for empty, adversarial, off topic, or oversized inputs. What does the module direct you to do?

- **A.** Ship now and let production traffic reveal which of those inputs actually occur before spending design time
- **B.** Add a disclaimer to the docs noting the gap, so the next engineer knows those input cases remain intentionally open
- **C.** Rely on the model's defaults, since modern models already handle unusual inputs more gracefully than rules do
- **D.** Define the expected behavior for each input class and back it with tests before the system is allowed to ship  ✅

> **Answer:** D

### Q23. Six months from now, someone will ask why v3.1.0 of your prompt shipped at all. Per the module, what should every shipped version be tied to?

- **A.** The names of every engineer who reviewed the release, creating accountability for each line of prompt text
- **B.** A rollback script tested in staging, proving the version can be reverted within minutes of a live incident
- **C.** The eval results that justified shipping it, stored with the version so the evidence lives in the repo  ✅
- **D.** A cost projection for the quarter, showing the version fits the budget the application was approved under

> **Answer:** C

### Q24. You are planning your capstone from scratch. Per the module, what is the correct order for the full ship pipeline?

- **A.** Drafting, deployment, requirements, evaluation, monitoring, architecture, with docs added wherever they fit
- **B.** Architecture, drafting, requirements, monitoring, evaluation, deployment, so structure exists before goals
- **C.** Evaluation, requirements, architecture, drafting, deployment, monitoring, so tests exist before any build
- **D.** Requirements, architecture, drafting, evaluation, deployment, monitoring, each stage feeding the one after  ✅

> **Answer:** D

### Q25. Which statement best captures the governing principle of Module 7?

- **A.** A professional prompt system is a product: versioned, tested, documented, and monitored so others can maintain it  ✅
- **B.** A professional prompt system is a work of craft: enough skilled wording will eventually solve any quality problem
- **C.** A professional prompt system is a moving target: rebuild it from scratch whenever a new model generation arrives
- **D.** A professional prompt system is a secret asset: its value comes from wording competitors cannot easily replicate

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106162168_
