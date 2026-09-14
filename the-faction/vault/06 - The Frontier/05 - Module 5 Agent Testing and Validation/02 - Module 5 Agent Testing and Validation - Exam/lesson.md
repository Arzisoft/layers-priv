---
course: "The Frontier"
module: "Module 5: Agent Testing and Validation"
lesson: "Module 5: Agent Testing and Validation — Exam"
type: "course_quiz"
post_id: 104725956
space_id: 24391596
source: "https://the-faction.mn.co/posts/104725956"
updated: "2026-08-10T17:18:21Z"
---

# Module 5: Agent Testing and Validation — Exam

> Exam for **Module 5: Agent Testing and Validation** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Why does testing an AI agent differ fundamentally from testing traditional software?

- **A.** Agents cannot be tested at all, since machine intelligence is inherently beyond measurement
- **B.** The same input can produce different outputs, so you measure behavior in rates, not single passes  ✅
- **C.** Agent tests are illegal to automate, requiring careful manual human execution of every case
- **D.** Traditional software has no bugs by comparison, which makes agent testing the far easier discipline overall

> **Answer:** B

### Q2. Your agent passed a test once. What does professional validation require before trusting it?

- **A.** Nothing more; a single pass is proof, since agents perform consistently by design
- **B.** A celebration, since passing any test at all is the truly meaningful milestone for AI systems
- **C.** The agent's own confirmation that it would pass again if the test were repeated later
- **D.** Many runs of the same scenario, so you know the success rate rather than one lucky outcome  ✅

> **Answer:** D

### Q3. What is a hallucination in the context of agent outputs?

- **A.** Confident output that is fabricated or wrong — invented facts, sources, or results presented as real  ✅
- **B.** Any output that is longer than the input, since expansion necessarily introduces some invented content
- **C.** A visual glitch in the interface where the agent's text renders in the wrong color or font
- **D.** The agent expressing uncertainty, since doubt indicates the reasoning process has failed

> **Answer:** A

### Q4. What is the reliable way to catch hallucinated facts in agent output?

- **A.** Reading the output twice, since fabrications become visible on a second careful pass
- **B.** Checking the output’s confidence wording, since hallucinations always hedge themselves
- **C.** Verifying claims against ground truth: the actual data, documents, or systems referenced  ✅
- **D.** Asking the same agent whether it hallucinated, since models audit themselves quite accurately

> **Answer:** C

### Q5. What is a golden dataset in agent testing?

- **A.** A curated set of inputs with known correct outputs, used to score the agent’s answers against truth  ✅
- **B.** The most expensive training data available, purchased specifically to maximize the model’s quality
- **C.** The agent’s best outputs from production, archived as trophies for future stakeholder demos
- **D.** A dataset stored on premium infrastructure, since storage quality directly affects the validity of your tests

> **Answer:** A

### Q6. Beyond judging quality, what mechanical validation should run on every agent output?

- **A.** A word count check only, since length is the strongest available proxy for correctness
- **B.** Structure and bounds checks: right format, required fields present, values within sane ranges  ✅
- **C.** A profanity scan only, since tone is the primary risk in professionally deployed agent systems
- **D.** No mechanical checks, since automated validation cannot understand meaning at all

> **Answer:** B

### Q7. Why deliberately feed an agent malformed, hostile, and weird inputs during testing?

- **A.** To punish the agent for earlier failures, since pressure improves future performance
- **B.** To exhaust the testing budget, since unspent QA funds get cut in the next annual planning cycle
- **C.** Because production will do exactly that, and you want to learn the failure behavior first  ✅
- **D.** To generate amusing outputs for the team channel, which sustains morale during QA

> **Answer:** C

### Q8. You improved the agent's instructions to fix one problem. What must happen before shipping the change?

- **A.** Nothing, since instruction improvements can only add quality, never subtract it elsewhere
- **B.** A vote among stakeholders, since instruction changes are governance rather than engineering decisions
- **C.** A month of waiting, since instruction changes need time to fully settle before any evaluation
- **D.** Rerun the existing test suite; fixes routinely break other behaviors, and regressions hide silently  ✅

> **Answer:** D

### Q9. You use a second AI model to grade your agent's outputs at scale. What must you keep in mind?

- **A.** The judge is fallible too: calibrate it against human judgment and spot-check its scores  ✅
- **B.** The judge is infallible, since evaluation is a strictly easier task than generation
- **C.** The judge must be the identical model, since only twins can understand each other's work
- **D.** Judging is free of cost, so unlimited judge calls should be attached to every output

> **Answer:** A

### Q10. What role does human review keep in a mostly automated validation pipeline?

- **A.** None once automation exists, since human review is exactly what the automation replaced
- **B.** Regular sampling: humans inspect a slice of outputs to catch what automated checks miss  ✅
- **C.** Total coverage forever, since every single output must have human eyes on it before release
- **D.** Ceremonial signoff, reviewing nothing but signing everything for the permanent compliance record

> **Answer:** B

### Q11. How is agent reliability meaningfully expressed?

- **A.** As a feeling the team shares after working with the agent for a couple of weeks
- **B.** As the agent's own self-assessment, gathered through structured interview prompts
- **C.** As the size of the model behind it, since parameter count determines dependability
- **D.** As measured rates: how often it succeeds, fails, or degrades across many real runs  ✅

> **Answer:** D

### Q12. Testing passed and the agent shipped. What does validation look like after launch?

- **A.** It ends; production is the reward for passing tests, not a place for more measurement
- **B.** It moves to lawyers, since post-launch quality is a contractual rather than technical matter
- **C.** Continuous monitoring: production outputs get sampled, scored, and alarmed on drift  ✅
- **D.** Annual audits only, since more frequent measurement destabilizes a working system

> **Answer:** C

### Q13. Your agent fails in several different ways. Why categorize the failures instead of just counting them?

- **A.** Different failure types have different fixes: a format bug, a knowledge gap, and a tool error need different work  ✅
- **B.** Categories make the reports longer, which demonstrates real thoroughness to all of the stakeholders
- **C.** Counting is mathematically invalid for AI systems, which leaves categorization as the only usable option available
- **D.** Categorization lets you blame each failure type on a different vendor or a different teammate entirely

> **Answer:** A

### Q14. An agent states an answer with complete confidence. What does that confidence tell you about accuracy?

- **A.** Everything, since models are engineered to express exactly as much confidence as they have earned
- **B.** Little; fluent certainty and correctness are separate things, so verification still applies  ✅
- **C.** It guarantees accuracy for factual questions, though not for creative or open-ended ones
- **D.** It signals the opposite, since confident answers are statistically the least accurate

> **Answer:** B

### Q15. An agent's job includes calling tools. What extra layer does testing need beyond judging its text?

- **A.** Nothing extra, since tool behavior is the tool vendor's responsibility rather than the agent's
- **B.** Voice testing, since tool-using agents are typically deployed in spoken interfaces
- **C.** Penmanship review, since tool calls are handwritten into logs by the serving layer
- **D.** Verifying the calls themselves: right tool, right parameters, right handling of the results  ✅

> **Answer:** D

### Q16. What does setting an acceptance threshold mean for an agent system?

- **A.** Deciding what reliability the stakes require — an internal draft tool and a customer-facing action need different bars  ✅
- **B.** Choosing the maximum price the client will accept for the system's ongoing monthly operation and support
- **C.** Setting the minimum typing speed the agent must sustain during the peak usage hours of the business day
- **D.** Selecting the age threshold that users must exceed before they are permitted to interact with the deployed system at all

> **Answer:** A

### Q17. The model behind your agent gets upgraded by the provider. What does disciplined validation do?

- **A.** Nothing, since upgrades are strictly improvements and testing them insults the provider
- **B.** Downgrades immediately, since any change to a validated system is an unacceptable risk
- **C.** Re-runs the evaluation suite on the new model before trusting it with the same work  ✅
- **D.** Asks the new model whether it is better than the old one and records the answer

> **Answer:** C

### Q18. How should real user feedback relate to your validation system?

- **A.** It shouldn't; users lack the expertise to evaluate agent output in any genuinely useful way
- **B.** It replaces testing entirely, since production users are the ultimate evaluation suite available
- **C.** It should be ignored unless legally required, since raw feedback biases the quality metrics
- **D.** It feeds the loop: complaints and corrections become test cases the suite runs forever after  ✅

> **Answer:** D

### Q19. What rule governs the data used in agent test suites?

- **A.** Only synthetic data is ever allowed, since realistic data makes tests too easy to pass
- **B.** Real customer secrets and live credentials stay out; test data is representative, not sensitive  ✅
- **C.** Production passwords should be included, since realistic secrets produce the most realistic tests
- **D.** Test data must be purchased from certified vendors to be admissible in validation

> **Answer:** B

### Q20. You run the same prompt ten times and get answers that vary wildly in quality. What is this measuring?

- **A.** The weather's effect on inference, which providers acknowledge but cannot control
- **B.** Nothing useful, since variance across identical runs is pure random noise that should be ignored
- **C.** Consistency — and high variance on identical input is itself a reliability problem to fix  ✅
- **D.** The agent's creativity score, which enterprise deployments should try to maximize

> **Answer:** C

### Q21. The agent nailed the demo for the client. What is the trap in treating that as validation?

- **A.** A demo is one run on friendly input; production is thousands of runs on hostile input  ✅
- **B.** There is no trap; a successful demo is the strongest form of evidence that exists
- **C.** Demos legally bind you to identical future performance, creating real contract exposure for you
- **D.** Clients distrust successful demos, so a failed demo would have validated the system better

> **Answer:** A

### Q22. How should a new agent system reach full production traffic?

- **A.** Instantly at one hundred percent, since partial rollouts produce misleading signals
- **B.** Never fully, since agent systems should permanently stay in a pilot configuration
- **C.** Only on weekends at first, since weekend errors damage fewer business relationships
- **D.** Gradually: a small slice first, watched closely, expanding as the metrics hold up  ✅

> **Answer:** D

### Q23. Your validated agent still has known weaknesses. What do you do with that knowledge?

- **A.** Conceal it entirely, since documented weaknesses become powerful ammunition in any future legal dispute
- **B.** Fix everything before any launch, since known limitations mean the system simply isn't finished
- **C.** Document the limitations and design around them: guardrails where it's weak, humans where it fails  ✅
- **D.** Publish it as marketing, since transparency about flaws is the strongest sales angle available

> **Answer:** C

### Q24. Who should design and judge the validation of an agent system?

- **A.** Nobody, since validation emerges naturally from usage without any designated owner
- **B.** Someone other than only its builder: independent eyes catch what the maker's pride skips  ✅
- **C.** The agent itself, since self-evaluation removes the bias humans bring to judging
- **D.** The client's interns, since fresh juniors are the least contaminated by any prior expectations

> **Answer:** B

### Q25. Which principle should anchor how you validate systems that think?

- **A.** Trust rates, not runs: measure across volume, verify against truth, and keep watching after launch  ✅
- **B.** Trust the vibe: extended casual use reveals more than any structured evaluation ever could
- **C.** Trust the vendor: model providers already validate deeply enough that builders need never repeat the work
- **D.** Trust the demo: a system that performs under observation performs everywhere else just as well

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/104725956_
