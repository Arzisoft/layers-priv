---
course: "The Frontier"
module: "Module 1: The Prompting Maturity Model"
lesson: "Module 1: The Prompting Maturity Model — Exam"
type: "course_quiz"
post_id: 106161003
space_id: 24391596
source: "https://the-faction.mn.co/posts/106161003"
updated: "2026-08-21T15:22:41Z"
---

# Module 1: The Prompting Maturity Model — Exam

> Exam for **Module 1: The Prompting Maturity Model** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your support bot handles 10,000 conversations a day and the prompt is right 92 percent of the time. According to the module, what does that 8 percent miss rate mean at production scale?

- **A.** It is an acceptable annoyance, since 92 percent accuracy is strong and most customers never notice one bad reply
- **B.** It mainly signals the model is too weak for support work, so moving to a stronger model should be the first fix
- **C.** It is chiefly a staffing question, because human reviewers spot checking outputs will absorb the misses affordably
- **D.** It is a liability with a dollar figure attached, roughly 800 failures a day like wrong refund policies quoted  ✅

> **Answer:** D

### Q2. A builder keeps a library of reusable prompts with fill in variables for client work, swapping in names and topics. Nothing is tested or versioned. Where does this practice sit on the Prompting Maturity Model?

- **A.** Level 1 Conversational, because swapping variables by hand still counts as improvising each prompt fresh in the moment
- **B.** Level 2 Templated, because the prompts are reusable with variables but remain untested and completely unversioned  ✅
- **C.** Level 3 Structured, because a saved template implies a defined role and a consistent output format underneath
- **D.** Level 4 Engineered, because maintaining a shared library is itself a form of versioning and quality control

> **Answer:** B

### Q3. An agency stores every client prompt in version control and runs each change against a saved evaluation set before it ships. There is no automated monitoring yet. What maturity level is this?

- **A.** Level 2 Templated, since the prompts are reusable assets that the team simply fills in with client specific variables
- **B.** Level 3 Structured, since roles, constraints, and formats are clearly the focus of the team's prompt reviews
- **C.** Level 5 Systematized, since version control and evaluation sets are the defining marks of the highest level
- **D.** Level 4 Engineered, since the prompts are versioned and tested as production assets but lack automated monitoring  ✅

> **Answer:** D

### Q4. A builder's chat prompts work great because she reads each output and corrects the next turn. She now wants the same prompt running unattended 10,000 times a day. Why does the module say her approach breaks?

- **A.** Production has no next turn, so every correction she would make live must be encoded in the prompt up front  ✅
- **B.** Models become less accurate as daily volume grows, so quality decays no matter how the prompt is written
- **C.** Unattended prompts hit context window limits faster, which silently truncates her carefully written instructions
- **D.** Chat interfaces use different models than production endpoints, so her results simply will not transfer over

> **Answer:** A

### Q5. A content pipeline keeps producing slightly different structures for the same brief, and the team spends hours fixing outputs. Which set names the three costs of ambiguity from the module?

- **A.** Higher latency, degraded model reasoning, and slow drift away from the brand voice the client originally approved
- **B.** Hallucinated facts, prompt injection exposure, and compliance risk from unreviewed outputs reaching customers
- **C.** Wasted tokens, human rework cycles, and output inconsistency that makes downstream automation impossible  ✅
- **D.** Larger context windows, heavier example sets, and rising API spend as prompts grow longer to cover the gaps

> **Answer:** C

### Q6. A data extraction prompt keeps mislabeling invoice dates. The builder adds one worked example and the failure disappears completely. What does the module's diagnostic conclude?

- **A.** The prompting was the bottleneck, since the failure vanished once the task was specified with an example  ✅
- **B.** The model was the limitation, and the example is a fragile patch that will break on the next input variation
- **C.** The example merely masked a model weakness, so the team should still budget for a model upgrade soon
- **D.** The result is inconclusive until the team reruns the original prompt on a newer model for comparison

> **Answer:** A

### Q7. A brand voice prompt has grown to 800 tokens of earnest description, yet outputs still drift. How does the module distinguish specificity from verbosity?

- **A.** Longer prompts are inherently more specific, so the fix is expanding the description until drift stops
- **B.** Verbosity helps until the context fills, so the team should trim history rather than the instructions
- **C.** A tight 200 token spec beats a rambling 800 token wish, because specificity comes from structure, not word count  ✅
- **D.** Specificity and verbosity rise together naturally, so the real lever is a model with better instruction following

> **Answer:** C

### Q8. A builder suspects her lead qualification prompt underspecifies the task but wants evidence before rewriting it. What is the Variance Test procedure from the module?

- **A.** Run the prompt on ten different leads and check whether the quality holds steady across the varied inputs
- **B.** Run the prompt through ten different models and keep whichever engine produces the most reliably consistent answers
- **C.** Run the same prompt ten times on the same input and diff the outputs to see how much they vary between runs  ✅
- **D.** Run two phrasings against live traffic for a week and compare which version generates fewer complaints

> **Answer:** C

### Q9. A builder runs her summarization prompt ten times on one identical document and gets noticeably different structures each run. Per the module, what does this high variance signal?

- **A.** The prompt underspecifies the task, forcing the model to guess, and guesses naturally vary across runs  ✅
- **B.** The model is fundamentally unreliable for summarization and should be replaced before further testing
- **C.** The document itself is ambiguous source material, so the inputs need cleaning before prompts are judged
- **D.** The variance is normal sampling behavior, so only the average quality across the ten runs actually matters

> **Answer:** A

### Q10. A team already versions its prompts and tests every change against evaluation sets. They ask what separates the top maturity level from where they are now. What defines Level 5 Systematized?

- **A.** Defined roles, explicit constraints, output formats, and worked examples embedded within every production prompt
- **B.** Automated evaluation, regression testing, monitoring, and controlled rollout, managed like critical software  ✅
- **C.** A dedicated prompt owner on staff who reviews every change and signs off before anything reaches customers
- **D.** Fine tuned models replacing prompts entirely, so quality no longer depends on instruction wording at all

> **Answer:** B

### Q11. A builder is turning a messy chat prompt into a professional specification for an unattended pipeline. Which components does the module say a prompt specification must cover?

- **A.** Task, inputs, constraints, output contract, and edge case behavior, written so two readers expect the same output  ✅
- **B.** Persona, tone, politeness, and encouragement, since models tend to mirror the attitude of the instructions they receive
- **C.** Model choice, temperature, token limits, and retry logic, since sampling settings drive most output variance
- **D.** A greeting, background context, the core request, and a closing summary restating what matters most to you

> **Answer:** A

### Q12. Two competent teammates read a builder's extraction prompt and describe different expected outputs. According to the module, what follows from that disagreement?

- **A.** Nothing serious, because the model reads more carefully than people and resolves such gaps consistently
- **B.** The prompt only needs another example appended, since disagreements between readers concern edge cases alone
- **C.** The prompt needs a human review step in production so a person can arbitrate whenever outputs differ
- **D.** The model will produce different outputs too, so the ambiguity must be closed before it runs unattended  ✅

> **Answer:** D

### Q13. An agency realizes prompts are scattered across chats, docs, and automations, and nobody knows what runs where. What is the Prompt Inventory the module prescribes?

- **A.** A collection of each prompt's best outputs, saved as references so future outputs can be graded against them
- **B.** An archive of full chat transcripts, preserved so the original intent behind every prompt can be recovered
- **C.** A single document listing every prompt you rely on, where it runs, its maturity level, and its named owner  ✅
- **D.** A shared library of proven phrasings and clever wordings that teammates can copy into their own prompts

> **Answer:** C

### Q14. A support bot produces occasional bad answers, and the team argues from memory about what went wrong last month. What is the Failure Log the module recommends?

- **A.** A dashboard tracking model outages and API errors, so infrastructure problems are separated from prompt issues
- **B.** A record of customer complaints routed to the prompt owner, so real user pain drives the fixes that get made
- **C.** A spreadsheet of token spend per conversation, revealing which prompt versions are quietly burning budget
- **D.** A running record of every bad output with the prompt version that produced it, turning anecdotes into data  ✅

> **Answer:** D

### Q15. A brand voice content pipeline is being upgraded from loose templates. What additions would move it to Level 3 Structured on the maturity model?

- **A.** Fill in variables for topic and audience, so one master template can serve every single client without rewriting
- **B.** Version numbers on each template plus a saved evaluation set that every proposed change must pass first
- **C.** Automated monitoring with regression tests and a controlled rollout process for each new prompt release
- **D.** Defined roles, explicit constraints, specified output formats, and worked examples built into the prompt itself  ✅

> **Answer:** D

### Q16. A builder demos one spectacular output from a chat session and declares the prompt ready for the client's automation. Which pitfall from the module is this?

- **A.** Confusing a good session with a good prompt, since one great output proves nothing about repeatability  ✅
- **B.** Skipping the inventory, since the prompt was never catalogued with an owner before being promoted to production
- **C.** Blaming the model first, since the builder credits the engine for quality the prompt structure produced
- **D.** Adding words instead of structure, since demo prompts tend to be padded with persuasive but vague language

> **Answer:** A

### Q17. Output quality on a document processing system disappoints, and the team's first instinct is paying for a stronger model. What does the module advise before swapping the engine?

- **A.** Upgrade anyway, since newer models resolve most quality issues and the prompt can be tuned afterward
- **B.** Upgrade and restructure simultaneously, since isolating one variable at a time slows the team down needlessly
- **C.** Run the diagnostic first, since at Levels 1 through 3 most quality problems are prompt problems wearing a model costume  ✅
- **D.** Add a human review layer instead, since no prompt change or model change fully removes production errors

> **Answer:** C

### Q18. Two builders compare philosophies. One tunes prompts until a single brilliant output appears. The module says professionals optimize for something else. What is it?

- **A.** The most impressive single output achievable, since it demonstrates the ceiling the prompt can reach
- **B.** The worst output across a thousand runs, asking whether that floor is acceptable for production use  ✅
- **C.** The average quality across many runs, since means are more stable and easier to report than extremes
- **D.** The fastest acceptable output, since latency compounds into real cost at ten thousand runs per day

> **Answer:** B

### Q19. A builder has solid reusable templates and wonders what the module means by the shift from Level 2 to Level 4 thinking. What captures that shift?

- **A.** Writing richer templates with more variables, so a single master prompt can flex across far more situations
- **B.** Judging prompts by their worst day at volume, backed by versioning and testing rather than reuse alone  ✅
- **C.** Moving work from chat interfaces to API calls, since programmatic access is what defines engineering
- **D.** Delegating prompt drafting to a stronger model, since machine written prompts outperform hand tuned ones

> **Answer:** B

### Q20. An agency feels professional because every service runs on polished reusable templates, none of which have been tested. What does the module warn about treating templates as the finish line?

- **A.** Untested templates make the same mistake consistently at scale, so reuse alone is not the finish line  ✅
- **B.** Templates grow too rigid over time, so mature teams eventually return to flexible conversational prompting
- **C.** Templates are safe once a senior builder writes them, so the real risk is junior edits made without review
- **D.** Templates mainly fail through variable typos, so an input checker closes most of the remaining quality gap

> **Answer:** A

### Q21. A builder's prompt pleads with the model to be very careful, extremely accurate, and truly thorough, yet errors persist. What does the module say about adding words instead of structure?

- **A.** Politeness measurably improves compliance, so the pleading should be moved to the top of the prompt
- **B.** More descriptive adjectives sharpen intent, so the builder should name the desired qualities more precisely
- **C.** Longer prompts signal importance to the model, so padding is wasteful but essentially harmless at scale
- **D.** Constraints, formats, and examples do the work adjectives cannot, and pleading language often adds ambiguity  ✅

> **Answer:** D

### Q22. A solo builder adopts the Maturity Self-Audit for her prompt portfolio and asks how often to run it. What cadence and scope does the module prescribe?

- **A.** Run it once when first adopting the maturity model, since a baseline reading is what makes growth visible
- **B.** Run it quarterly and after every production incident, scoring structure, versioning, testing, and repeatability  ✅
- **C.** Run it daily on production prompts, since anything less frequent lets silent regressions slip through unseen
- **D.** Run it whenever output quality visibly drops, since auditing healthy prompts wastes limited builder time

> **Answer:** B

### Q23. A freelancer improvises every prompt live in chat, nudging outputs turn by turn until something looks right. Results depend entirely on the day. Where is this on the maturity model?

- **A.** Level 1 Conversational, because the practice is improvised and depends on live human correction in the moment  ✅
- **B.** Level 2 Templated, because repeating similar requests from memory is effectively an informal template system
- **C.** Level 3 Structured, because the freelancer implicitly applies roles and constraints while steering the chat
- **D.** Outside the model entirely, because the framework only measures automated pipelines, not interactive work

> **Answer:** A

### Q24. A data extraction system occasionally invents a value for a missing field. When the builder defines a strict output format with an explicit rule for missing data, it stops. What was the problem?

- **A.** A model limitation, since inventing values is inherent hallucination that no instruction reliably removes
- **B.** A source data issue, since malformed inputs push models to fill gaps regardless of the prompt's wording
- **C.** A prompting bottleneck, because the failure disappeared once the output contract was defined explicitly  ✅
- **D.** Random variance, since occasional failures at low rates fall inside normal sampling noise for any model

> **Answer:** C

### Q25. Which statement best captures the governing principle of Module 1, The Prompting Maturity Model?

- **A.** Model capability is the ultimate ceiling on quality, so choosing the strongest engine matters more than wording
- **B.** Professional prompting is engineering: prompts are versioned, tested specifications judged by worst case output at scale  ✅
- **C.** Great prompting is skilled conversation, refining outputs turn by turn until the desired quality emerges
- **D.** Scale should wait for perfection, since automation multiplies every flaw a prompt still quietly carries

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/106161003_
