---
course: "The Frontier"
module: "Module 5: Dynamic Context Assembly"
lesson: "Module 5: Dynamic Context Assembly — Exam"
type: "course_quiz"
post_id: 106578138
space_id: 24391596
source: "https://the-faction.mn.co/posts/106578138"
updated: "2026-08-28T16:34:05Z"
---

# Module 5: Dynamic Context Assembly — Exam

> Exam for **Module 5: Dynamic Context Assembly** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. An assistant handles refunds, technical faults, and small talk, and every call ships the same giant context regardless. Answers are slow and vague. What is the structural diagnosis?

- **A.** The model is too small for mixed traffic, and a larger model would absorb the variety cleanly
- **B.** Static assembly: every query type pays for every other type's content, and none gets a fitted window  ✅
- **C.** The retrieval threshold is set too low, letting borderline passages pad out each window
- **D.** The system prompt is overloaded, and splitting it into clearly numbered sections would fix the vagueness

> **Answer:** B

### Q2. A builder hears the phrase conditional context and asks what actually changes between two incoming queries. What is the accurate answer?

- **A.** The model changes: each query class is routed to a different model tuned for that workload
- **B.** The temperature changes: factual classes run cold while conversational classes run warmer
- **C.** Only the phrasing changes: the same content is reworded to match each query's vocabulary
- **D.** The contents change: the assembler includes different information for different query types  ✅

> **Answer:** D

### Q3. A team needs to sort incoming queries into classes before assembly. Which set of options does this module put on the table?

- **A.** A rule, a keyword match, or a cheap model call, chosen by what the traffic actually requires  ✅
- **B.** Only a fine-tuned classifier model, since rules cannot handle natural language reliably
- **C.** Manual review, where a human tags each query before the system is allowed to respond
- **D.** Random assignment at first, tightening gradually as misroutes get corrected by users

> **Answer:** A

### Q4. A user asks about their order status, and the model guesses from conversation fragments. The order database sits one API call away. What pattern is missing?

- **A.** Memory recall: past sessions likely mention the order and should be injected at start
- **B.** Retrieval: the order records should be chunked, embedded, and searched like documents
- **C.** Tool output injection: run the lookup, place the result in the window, then let the model answer  ✅
- **D.** Prompt tightening: instruct the model to politely refuse order questions it cannot answer precisely

> **Answer:** C

### Q5. A function result lands in the window as a bare blob of JSON, and the model occasionally mistakes it for user input. What discipline applies to injected tool output?

- **A.** It should be converted to prose first, since models parse sentences more reliably than JSON
- **B.** The same as retrieved documents: labeled, delimited, and budgeted like any other layer  ✅
- **C.** It should be placed after the user message so the model reads the question before the data
- **D.** It should be truncated to a fixed length so no single result can dominate the window

> **Answer:** B

### Q6. A complex task runs as research, then outline, then draft. How should the windows for these steps be built?

- **A.** Purpose-built per step: each gets its own instructions plus the prior output it needs  ✅
- **B.** Identically: one shared window for all steps keeps the model's view consistent throughout
- **C.** Cumulatively: each step appends to the last window so no information is ever lost
- **D.** Minimally: every step gets only the original user request, keeping steps independent

> **Answer:** A

### Q7. By step four of a chain, the window is hauling step one's raw research, step two's discarded drafts, and step three's notes. Quality is sinking. What is the corrective principle?

- **A.** Raise the window budget for later steps, since chains naturally accumulate necessary weight
- **B.** Cut the chain to two steps, since chains beyond that length degrade regardless of content
- **C.** Summarize the entire chain history at every step so all context survives in compressed form
- **D.** Pass forward only what the next step needs; each step's window is built, not inherited  ✅

> **Answer:** D

### Q8. A builder asks what single component decides, before each model call, which sources, tools, and budgets apply. What is this component?

- **A.** The system prompt, which lists the available sources and lets the model choose among them
- **B.** The vector store, which ranks all candidate content and forwards whatever clears threshold
- **C.** The provider's routing layer, which inspects each request and attaches relevant context
- **D.** The orchestration layer: code that runs before the call and assembles that call's context  ✅

> **Answer:** D

### Q9. A teammate treats the assembly logic as mysterious AI behavior that cannot be verified. What is the correct reframe?

- **A.** It is mysterious, which is why assembly should be handed to the model itself to manage
- **B.** It is semi-deterministic, verifiable only through statistical sampling across many runs
- **C.** It is ordinary code with inputs and outputs, and it can be unit tested like any other module  ✅
- **D.** It is provider-controlled, so verification belongs in the provider's compliance reports

> **Answer:** C

### Q10. A builder wants tests that catch assembly regressions before users do. What shape should those tests take?

- **A.** For each query type, assert which sources must appear in the window and which must not  ✅
- **B.** For each model output, score fluency and flag any response that drops below baseline
- **C.** For each provider release, replay last month's traffic and diff the generated answers
- **D.** For each window, verify the token count stays within ten percent of the historical mean

> **Answer:** A

### Q11. Planning a new assistant, a builder sketches recipes for fourteen query types and six tools before seeing any traffic. What does this module advise instead?

- **A.** Build all fourteen now, since retrofitting recipes after launch is costlier than upfront design
- **B.** Start with two or three classes and one tool, letting real traffic justify added complexity  ✅
- **C.** Skip classification entirely at first and route every query through the largest recipe
- **D.** License a prebuilt taxonomy for the industry and map its categories onto the traffic

> **Answer:** B

### Q12. Six months in, a system maintains twenty query classes; logs show three classes receive 97 percent of traffic and several have never fired. What went wrong at design time?

- **A.** Nothing: rare classes are cheap insurance, and their recipes stand ready for edge cases
- **B.** The classifier was overtrained, collapsing genuine variety into three catch-all buckets
- **C.** The taxonomy was over-engineered ahead of evidence, adding upkeep without adding value  ✅
- **D.** Traffic was sampled during an unrepresentative season, hiding the seventeen quiet classes

> **Answer:** C

### Q13. Mid-assembly, the inventory API times out. Per this module, what should reach the window in place of the missing result?

- **A.** An explicit, labeled failure notice, so the model knows the lookup failed and can say so  ✅
- **B.** Nothing: skipping the layer silently keeps the window clean and the answer focused
- **C.** The raw timeout stack trace, giving the model maximum detail about what went wrong
- **D.** A cached result from the last successful call, since stale inventory beats no inventory

> **Answer:** A

### Q14. One request needs retrieval, a memory lookup, and two API calls before assembly. Latency is now a complaint. How does a well-built orchestrator handle the gathering?

- **A.** Sequentially by priority, so the most important ingredient always arrives before the rest
- **B.** It skips gathering on alternate requests, halving average latency at some quality cost
- **C.** It moves gathering to a nightly batch job and assembles tomorrow's windows in advance
- **D.** In parallel: independent ingredient fetches run concurrently, and assembly waits once  ✅

> **Answer:** D

### Q15. A builder is directing AI to implement the per-request pipeline and wants the stages in order. Which sequence is right?

- **A.** Assemble, classify, call the model, gather ingredients, then log what should have been built
- **B.** Classify, select the recipe, gather ingredients, assemble within budgets, call, then log  ✅
- **C.** Call the model first for a draft, classify the draft, then assemble context for a second pass
- **D.** Gather all possible ingredients, assemble everything, then classify what the window became

> **Answer:** B

### Q16. In a routed system, billing queries and support queries hit different recipes. What does good routing mean for their windows?

- **A.** Both windows share a common core of every source, with routing adding a thin layer on top
- **B.** Billing gets account data and pricing; support gets product docs; neither hauls the other's load  ✅
- **C.** The windows are identical, but the system prompt names the detected query type for the model
- **D.** Support windows stay larger by design, since troubleshooting always needs more context than billing

> **Answer:** B

### Q17. A model keeps stating yesterday's inventory counts for a product that sold out this morning. Retrieval and memory are working fine. What does this module say the window needed?

- **A.** A stronger recency instruction telling the model to prefer the newest figures it can find
- **B.** A larger history slice, so this morning's sell-out conversation stays visible to the model
- **C.** Live tool output: fresh data fetched at request time because some context must be created  ✅
- **D.** A daily re-index of the catalog, so retrieval reflects each morning's opening inventory

> **Answer:** C

### Q18. In a research, outline, draft chain, the draft step produces text. What should its window contain when it runs?

- **A.** Its own drafting instructions plus the outline it must follow, and little else  ✅
- **B.** The complete research dump, since the draft is where all evidence finally lands
- **C.** Only the original user request, so the draft stays uncontaminated by earlier steps
- **D.** The outline plus every candidate outline that was considered and rejected earlier

> **Answer:** A

### Q19. A bad answer surfaces from last Tuesday, and the builder needs to know which recipe fired and what it packed into the window. What makes this a five-minute question?

- **A.** The provider dashboard, which retains full request payloads for thirty days by default
- **B.** The classifier's confusion matrix, which shows how Tuesday's queries were distributed
- **C.** User session replays, which capture what the user saw at the moment of the answer
- **D.** The assembly log: each request records its class, recipe, ingredients, and final layout  ✅

> **Answer:** D

### Q20. After assembly gained unit tests, a string of mysterious AI bugs turned out to be a misrouted class and a budget typo. What is the general lesson?

- **A.** Most bugs blamed on the model are ordinary logic bugs in the code that builds its input  ✅
- **B.** Unit tests on assembly catch routing bugs but structurally cannot catch budget bugs
- **C.** Mysterious bugs cluster in the model layer, and assembly bugs are the rare exception
- **D.** Bugs found by tests were never real user-facing issues, or users would have reported them

> **Answer:** A

### Q21. A keyword rule routes queries containing the word bill to the billing recipe. Users writing about a bill of materials keep landing there too. When does the classifier deserve an upgrade?

- **A.** Never: keyword rules should be patched with exclusion lists rather than replaced outright
- **B.** Immediately at launch: rules should never have shipped in place of a trained model
- **C.** Now: when rules misroute real traffic, a cheap model call is the standard next step up  ✅
- **D.** Only when misroutes exceed half of traffic, the threshold where retraining pays off

> **Answer:** C

### Q22. Choosing between an orchestration framework and plain code that builds message arrays, a builder asks what the real tradeoff is. Which answer is honest?

- **A.** Frameworks are strictly better: they encode hard lessons from thousands of production deployments
- **B.** Frameworks manage chains for you but add abstraction; plain code is easier to log and test  ✅
- **C.** Plain code is strictly better: frameworks exist mainly for teams that cannot write code
- **D.** There is no tradeoff: both compile to identical calls, so the choice is pure preference

> **Answer:** B

### Q23. After moving from one static mega-window to per-class recipes, a team measures the change. Which outcome pattern should they expect from this module's case evidence?

- **A.** Windows shrink sharply, answers get faster and sharper, and per-call cost drops with them  ✅
- **B.** Windows shrink but quality dips slightly, the standard price of leaving content behind
- **C.** Quality holds steady while latency rises, since classification adds a step to every call
- **D.** Costs drop but debugging gets harder, since each class now fails in its own novel way

> **Answer:** A

### Q24. A builder is wiring the call, inject result, respond loop by hand with retries and glue code. What does this module point to as the right default?

- **A.** A cron-based poller that refreshes tool results into a cache which the assembler reads from
- **B.** A custom middleware layer, since hand-rolled loops outperform vendor abstractions
- **C.** A second model that watches the first and injects tool results when it detects a need
- **D.** The native tool-use APIs from providers, which handle that loop as a supported feature  ✅

> **Answer:** D

### Q25. One principle runs through every pattern in this module: recipes, tools, chains, and tests. Which statement is it?

- **A.** Context should be maximized: the safest window is always the one containing everything available
- **B.** Context should be static: a single well-designed window outperforms per-task variation
- **C.** Context is assembled at runtime to fit the task, by an orchestration layer you design and test  ✅
- **D.** Context should be minimized: the best window is always the smallest one that parses

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106578138_
