---
course: "The Frontier"
module: "Module 2: System Prompts and Instruction Architecture"
lesson: "Module 2: System Prompts and Instruction Architecture — Exam"
type: "course_quiz"
post_id: 106161295
space_id: 24391596
source: "https://the-faction.mn.co/posts/106161295"
updated: "2026-08-21T15:22:46Z"
---

# Module 2: System Prompts and Instruction Architecture — Exam

> Exam for **Module 2: System Prompts and Instruction Architecture** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. You run a support bot handling 10,000 conversations a day. A refund policy rule keeps getting dropped after a few turns. Where should that rule live?

- **A.** In each user message, restated at the start of every conversation so the model sees it fresh each time it responds
- **B.** In a pinned first message the customer never sees, injected once at the top of every new conversation thread
- **C.** In the system prompt, the persistent instruction layer that governs every interaction the bot handles at any volume  ✅
- **D.** In a fine-tuned model variant, since behavior rules are too important to trust to any prompt layer at production scale

> **Answer:** C

### Q2. You are drafting a system prompt for a brand-voice content pipeline and want the professional structure from this module. Which layer order is correct?

- **A.** Role, then constraints, then output format, then examples, then edge cases, from broad identity down to specifics  ✅
- **B.** Examples first, then role, constraints, output format, and edge cases, since models weight demonstrations most heavily
- **C.** Output format first, then constraints, role, edge cases, and examples, since structure errors are the costliest failures
- **D.** Edge cases first, then constraints, output format, role, and examples, since hostile inputs must be handled first

> **Answer:** A

### Q3. Your client's support bot has 'keep responses short' in its prompt, and response length varies wildly across 10,000 daily chats. What is the professional fix?

- **A.** Add 'be concise and professional' so the model has a second signal reinforcing the intent of the original instruction
- **B.** Move the instruction higher in the system prompt so the model treats it as a priority over later formatting rules
- **C.** Add several long and short example responses and let the model infer the intended length range from demonstrations
- **D.** Replace it with a specification such as 'respond in 2 to 4 sentences, maximum 80 words' so only one reading exists  ✅

> **Answer:** D

### Q4. Your data extraction system feeds a database, and the prompt says 'never invent a field value.' The model still fills gaps with guesses. What is missing?

- **A.** An explicit fallback paired with the prohibition, such as 'if a field is not present in the source text, output null'  ✅
- **B.** A stronger restatement of the rule in capital letters near the top so that the model cannot overlook the core prohibition
- **C.** A lower creativity setting, since hallucinated values are a randomness problem rather than an instruction problem
- **D.** A longer list of banned behaviors covering every specific way the model has been observed inventing field values

> **Answer:** A

### Q5. You are hardening a lead-qualification bot before launch. It handles friendly test inputs perfectly. What does this module say your prompt must also define?

- **A.** A broader role statement so the model can reason its way through any unusual input using its own general judgment
- **B.** More examples of ideal conversations, since strong demonstrations generalize to cover the unexpected inputs too
- **C.** A longer constraints section restating every rule twice, since repetition makes instructions hold up under load
- **D.** Behavior for the inputs you do not want: empty messages, off-topic questions, malformed data, out-of-scope pulls  ✅

> **Answer:** D

### Q6. A builder demos a prompt that produced one flawless output and calls it production ready. Why does this module reject that standard?

- **A.** Because one output cannot show tone, and tone is the main thing clients evaluate when they review AI-written work
- **B.** Because at volume the worst case is guaranteed to happen, so a prompt is judged by its worst output, not its best  ✅
- **C.** Because a single output proves nothing about speed, and response latency is what breaks systems at production scale
- **D.** Because models change over time, so any single successful output becomes unreliable evidence within a few weeks

> **Answer:** B

### Q7. You manage prompts for three agency clients and need a version log that supports real debugging. What should each entry record?

- **A.** The full prompt text only, since storing complete snapshots makes any other metadata redundant during a rollback
- **B.** Version number, date, what changed, why it changed, and the observed effect on behavior after the change shipped  ✅
- **C.** The author and approval sign-off for each edit, since accountability is the main purpose of tracking prompt changes
- **D.** Output samples from before and after each edit, since raw evidence matters more than a written change summary

> **Answer:** B

### Q8. At 2 a.m., your client's support bot starts giving off-brand answers after yesterday's prompt edit. What does versioning discipline buy you right now?

- **A.** A clear audit trail you can hand the client in the morning to prove the failure came from the model, not your edit
- **B.** The ability to rewrite the prompt from memory quickly, since the log refreshes your recall of the old version's text
- **C.** A way to hotfix by adding a new rule on top of the broken prompt, which is faster than reverting the whole thing
- **D.** A five minute rollback to the last known-good version instead of a full rebuild from memory while bad answers ship  ✅

> **Answer:** D

### Q9. You tweak one constraint in a content pipeline prompt that has run cleanly for months. Before shipping, what does the module tell you to run?

- **A.** A full evaluation suite with hundreds of scored cases, since anything smaller cannot certify a change as shippable
- **B.** The single input that motivated the change, since a targeted fix only needs verification against its own trigger
- **C.** A regression spot-check: a fixed set of 5 to 10 test inputs, including known edge cases, to confirm nothing broke  ✅
- **D.** A fresh round of live traffic monitoring, since only real production inputs reveal how a changed prompt behaves

> **Answer:** C

### Q10. You are reviewing a teammate's system prompt for a booking assistant before it goes live. What question does the Ambiguity Audit ask of every instruction?

- **A.** Is this instruction in the correct hierarchy layer, since misplaced rules are the leading cause of drifting behavior
- **B.** Could this be read more than one way, with any yes rewritten using numbers, definitions, or explicit conditions  ✅
- **C.** Would a new team member understand this in one pass, since human readability predicts model interpretation too
- **D.** Does this duplicate another rule elsewhere in the prompt, since redundancy causes contradictory outputs at scale

> **Answer:** B

### Q11. A brand client asks for 'a professional tone' and your builder pastes that phrase straight into the system prompt. What risk does this module flag?

- **A.** The model will default to a stiff corporate voice, which reads as robotic and hurts engagement with the audience
- **B.** Every open judgment call is a coin flip run thousands of times, since 'professional' means ten different things  ✅
- **C.** Tone instructions get overridden by user messages, so the phrase will be ignored in conversations with pushback
- **D.** The phrase wastes context space that should hold examples, the only reliable way to control tone at real volume

> **Answer:** B

### Q12. You open the Instruction Hierarchy Template to start a system prompt for a research assistant. What job does the role layer do?

- **A.** It lists the hard boundaries the assistant must never cross, so violations are caught before output is produced
- **B.** It specifies the exact structure every response must follow, so downstream tools can parse the output reliably
- **C.** It demonstrates the quality bar with worked samples, so the model can pattern-match instead of interpreting rules
- **D.** It establishes the model's core identity and scope, the broad frame that every later layer narrows into behavior  ✅

> **Answer:** D

### Q13. Your team keeps pasting formatting rules, banned phrases, and persona notes into individual chat requests for a client bot. How does this module divide the layers?

- **A.** Everything the model must always do goes in the system prompt; user messages carry the requests flowing through it  ✅
- **B.** Stable rules can go in either layer, since modern models merge system and user content into one context anyway
- **C.** User messages should carry the rules because they are more recent in context, and recency drives instruction weight
- **D.** The system prompt should stay minimal and abstract, with concrete behavior rules repeated inside user messages

> **Answer:** A

### Q14. A six month old client prompt has been edited by four builders with no tracking, and the bot now follows some rules and ignores others. What happened?

- **A.** Untracked edits let contradictory instructions accumulate until the model started choosing which rules to follow  ✅
- **B.** The model was updated by the provider, and newer models tend to deprioritize older system prompt phrasing styles over time
- **C.** The prompt grew past the context limit, so the model is truncating and only reading the first part of the rules
- **D.** Too many builders caused tone drift, and inconsistent voice makes a model distrust the entire instruction set

> **Answer:** A

### Q15. You are filling out the examples layer for a brand-voice content pipeline. According to this module, what are the examples there to do?

- **A.** Pad the prompt with volume, since longer system prompts are weighted more heavily and produce steadier behavior overall
- **B.** Replace the constraints section, since demonstrations communicate boundaries better than written rules could
- **C.** Cover rare hostile inputs, since examples are the layer where adversarial handling rules are supposed to live
- **D.** Demonstrate the standard, showing concretely what correct output looks like so quality is not left to inference  ✅

> **Answer:** D

### Q16. A builder drafts a system prompt with role, constraints, and edge cases but skips the output format layer entirely. What does the module say the output format layer demands?

- **A.** A general instruction to keep answers brief, since length control is the primary purpose of an output format
- **B.** A list of banned phrases and words so the model avoids language that conflicts with the desired brand voice
- **C.** An exact structural contract, stating JSON schema or section headings, field names, and types the output must follow  ✅
- **D.** A temperature and token limit pairing, since format control is ultimately a sampling parameter problem not a prompt one

> **Answer:** C

### Q17. A reviewer reads a system prompt and asks whether it was designed for the best output or the worst. What mindset does the module say a professional prompt reviewer should adopt?

- **A.** Best output mindset, since a prompt should be judged by the quality ceiling it can reach on ideal inputs
- **B.** Average output mindset, since means are the only stable metric across thousands of production runs daily
- **C.** Worst output mindset, asking if the floor is acceptable, since production exposes every weakness at scale  ✅
- **D.** Fastest output mindset, since latency compounds into real cost and slow prompts get abandoned by end users

> **Answer:** C

### Q18. A team tests their lead qualification system prompt only with polite, well-formed sample leads and declares it ready. What is the pitfall the module identifies?

- **A.** The prompt will be too rigid, rejecting valid but unusually phrased leads that real users submit every day
- **B.** Testing only the happy path, since real traffic includes empty messages, off-topic inputs, and hostile probes  ✅
- **C.** The sample size is too small, and the team needs at least a thousand test leads before any conclusion holds
- **D.** The team forgot to test with a weaker model, since system prompts must degrade gracefully across engine tiers

> **Answer:** B

### Q19. The module prescribes a specific layer hierarchy for system prompts: role first, then constraints, output format, examples, and edge cases. What is the rationale for ordering broad to specific?

- **A.** Earlier text gets higher attention weights in the transformer, so the most important layer should come first
- **B.** The model processes instructions sequentially like a script, so dependencies must be declared before they are used
- **C.** Each layer narrows the space the next one operates in, so broad identity naturally scopes the rules that follow  ✅
- **D.** Alphabetical ordering is a convention that makes prompts easier to audit, and broad to specific happens to match it

> **Answer:** C

### Q20. A support bot's system prompt defines the role, constraints, and output format perfectly but says nothing about what to do when a user sends an empty message. What does the module predict?

- **A.** The model will improvise a response, and that improvisation will vary unpredictably across thousands of daily runs  ✅
- **B.** The model will safely ignore the empty message and wait for the next one, since silence is the natural default
- **C.** The model will echo the system prompt back, since an empty input triggers a fallback to the instruction text itself
- **D.** The model will throw an API error, since empty messages are rejected at the endpoint before reaching the prompt

> **Answer:** A

### Q21. You cannot personally read the 10,000 responses your client's bot sends each day. Why does this module call the system prompt your leverage point?

- **A.** Because it is the only part of the stack a builder can edit without engineering help, making it the fastest lever
- **B.** Because it is cheaper than review labor, and cost per conversation decides where quality control should live
- **C.** Because it filters bad outputs after generation, catching failures before they reach a customer conversation
- **D.** Because you cannot review every response, but you can control the one instruction layer that shapes all of them  ✅

> **Answer:** D

### Q22. A client says their bot's answers 'got worse a few weeks ago.' The prompt was edited in place many times with no history. What position are you in?

- **A.** Debugging blind: with no versions you cannot compare, roll back, or prove what changed, so you rebuild from scratch  ✅
- **B.** A quick fix away: simply re-running the prompt through the ambiguity audit will reveal exactly which edit hurt quality
- **C.** A data problem: pulling a few weeks of transcripts will pinpoint the faulty edit without any version history
- **D.** A model issue: quality shifts over weeks usually trace to provider updates, so prompt edits are unlikely causes

> **Answer:** A

### Q23. You are writing the constraints layer for a healthcare-adjacent support bot. What does this layer contain, per the module?

- **A.** The hard boundaries: what the model must always do and never do, with prohibitions paired to explicit fallbacks  ✅
- **B.** The tone and persona guidance shaping voice, since boundaries emerge naturally from a well-defined character
- **C.** The formatting rules for responses, since structure is the strongest boundary a prompt places on real model behavior
- **D.** The escalation contacts and business hours, the operational facts the bot needs to route sensitive questions

> **Answer:** A

### Q24. You are starting your fifth client system prompt this month and keep forgetting to include edge case handling. What toolkit item solves this?

- **A.** The Regression Spot-Check, a fixed input set that flags any missing behavior before a prompt ships to clients
- **B.** The Ambiguity Audit, a review pass that catches vague wording before it becomes inconsistent production behavior
- **C.** The Instruction Hierarchy Template, a reusable skeleton with labeled sections so nothing critical gets omitted  ✅
- **D.** The Prompt Version Log, a changelog showing which sections past prompts included so you can copy them forward

> **Answer:** C

### Q25. Which statement best captures the governing principle of Module 2?

- **A.** Great prompting is iterative conversation: refine outputs through dialogue until the model converges on intent
- **B.** A system prompt is engineered architecture: structured, unambiguous, versioned, and judged by its worst output  ✅
- **C.** Model capability is the ceiling: past a baseline of clarity, outcomes depend on choosing the strongest model
- **D.** Constraints limit creativity: the best system prompts stay minimal so the model applies its intelligence freely

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/106161295_
