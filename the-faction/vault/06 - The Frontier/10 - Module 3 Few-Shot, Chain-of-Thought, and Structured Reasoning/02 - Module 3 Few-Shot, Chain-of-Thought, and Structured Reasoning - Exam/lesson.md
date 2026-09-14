---
course: "The Frontier"
module: "Module 3: Few-Shot, Chain-of-Thought, and Structured Reasoning"
lesson: "Module 3: Few-Shot, Chain-of-Thought, and Structured Reasoning — Exam"
type: "course_quiz"
post_id: 106161510
space_id: 24391596
source: "https://the-faction.mn.co/posts/106161510"
updated: "2026-08-21T15:22:53Z"
---

# Module 3: Few-Shot, Chain-of-Thought, and Structured Reasoning — Exam

> Exam for **Module 3: Few-Shot, Chain-of-Thought, and Structured Reasoning** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your support bot handles 10K conversations a day and must tag each ticket with your company's custom label taxonomy. Zero-shot instructions keep mislabeling edge cases. What is the strongest next move?

- **A.** Rewrite the instructions in more forceful language so the model treats the taxonomy rules as strict requirements it must follow
- **B.** Switch every request to chain-of-thought so the model reasons step by step before it assigns any label to a ticket
- **C.** Add a few-shot example set that demonstrates the taxonomy on real tickets, including the edge cases that are failing  ✅
- **D.** Lower the pass threshold and route every mislabeled ticket into a human review queue instead of touching the prompt

> **Answer:** C

### Q2. You run a brand-voice content pipeline that must produce posts in a client's distinctive tone, one the model cannot guess from instructions alone. Which strategy fits best?

- **A.** Few-shot prompting, because examples teach a custom pattern like brand voice that plain instructions cannot fully describe  ✅
- **B.** Zero-shot prompting, because tone requests are common tasks the model already handles well without any demonstrations
- **C.** Chain-of-thought prompting, because reasoning step by step lets the model deduce the voice from the client's existing site copy
- **D.** A longer list of adjectives describing the voice, since detailed descriptions replace the need for any worked examples

> **Answer:** A

### Q3. A client asks your agency to summarize plain news articles into three sentences each, a common well-defined task. What should the first version of this prompt use?

- **A.** Few-shot with five worked summaries, since examples always raise quality even on tasks the model performs well by default
- **B.** Chain-of-thought steps so the model justifies which sentences it keeps before it writes the final three-sentence summary
- **C.** Zero-shot instructions only, because common well-defined tasks like summarizing rarely need examples or added reasoning  ✅
- **D.** A combined few-shot plus chain-of-thought stack, since stacking every technique gives the most reliable production output

> **Answer:** C

### Q4. Your data extraction system works decently zero-shot but fails on some invoice layouts. According to the professional workflow in this module, what do you do next?

- **A.** Measure the actual failures first, then add targeted examples that fix only the patterns that are demonstrably breaking  ✅
- **B.** Add ten diverse examples immediately, since more demonstrations always generalize better than a small targeted set does
- **C.** Move straight to chain-of-thought, because reasoning fixes extraction errors more reliably than any example set can
- **D.** Rebuild the prompt from scratch with stricter instructions, since failures mean the original zero-shot framing was wrong

> **Answer:** A

### Q5. You are picking few-shot examples for an intake classifier that sees messy real-world submissions. Which selection approach does the module recommend?

- **A.** Pick the cleanest, most typical inputs so the model learns the ideal pattern without noise from confusing outlier cases
- **B.** Pick examples nearly identical to expected production inputs so the model can match new submissions almost exactly
- **C.** Pick examples that span the real input distribution, deliberately including the ugly edge cases the system will face  ✅
- **D.** Pick as many examples as the context window allows, since coverage grows in direct proportion to raw example count

> **Answer:** C

### Q6. A teammate stuffs ten near-identical examples into your pipeline prompt and results barely improve. What does the module say about example count?

- **A.** Ten is too few for production work; a vetted library should hold at least twenty examples before reliability stabilizes
- **B.** Count is irrelevant here; formatting consistency is the only factor that changes how well the model learns any pattern
- **C.** Three to five well-chosen, diverse examples usually beat ten redundant ones, because variety teaches the real pattern  ✅
- **D.** Ten identical examples are ideal; the results stalled because the instructions above them were written too loosely

> **Answer:** C

### Q7. Your content system keeps making one specific mistake: opening every post with a cliche hook you banned in the instructions. What targeted few-shot fix does the module suggest?

- **A.** Repeat the ban three times across the prompt so the model weights the instruction more heavily than the demonstrations
- **B.** Remove all examples, since the model is clearly copying the banned hook from a demonstration somewhere in your prompt
- **C.** Lower the temperature setting until the model stops improvising openings and sticks to safe, templated phrasing choices
- **D.** Add one contrastive example showing the banned opening labeled as wrong, which can eliminate that whole failure class  ✅

> **Answer:** D

### Q8. In your example library, one demonstration uses lowercase labels and a stray inline comment while the others are uniform. What does the module warn this teaches the model?

- **A.** Nothing significant, since models average across all their examples and one small deviation is diluted by the consistent majority
- **B.** That format is optional, because the model imitates formatting as strongly as content, and your parser pays for the drift  ✅
- **C.** That lowercase is preferred, so all future outputs will switch entirely to the lowercase style of the one odd example
- **D.** That comments are required, so the model will append an explanatory comment to every structured output it returns

> **Answer:** B

### Q9. Your extraction examples were copied almost verbatim from the exact documents the system will process. The module flags this as which pitfall?

- **A.** Teaching the answer instead of the pattern, so the model memorizes surface features and fails on anything truly novel  ✅
- **B.** Example overload, where too many demonstrations crowd the limited context window and dilute the core task instructions above
- **C.** Format drift, where near-duplicate examples cause the model to progressively loosen its output structure over time
- **D.** Reasoning leakage, where the model copies scratchpad content from examples directly into its final stored answers

> **Answer:** A

### Q10. A support bot must decide refunds by checking the issue, the policy, and account history. Why does the module prefer prescribed steps over a generic think step by step line?

- **A.** Generic triggers are deprecated, and modern models simply ignore the phrase think step by step in production settings
- **B.** Prescribed steps give you repeatable reasoning you can inspect and debug when a decision goes wrong at real scale  ✅
- **C.** Prescribed steps use fewer tokens than generic reasoning, cutting cost while accuracy stays exactly the same either way
- **D.** Generic triggers only work on math problems, and refund decisions are policy tasks outside their effective range

> **Answer:** B

### Q11. You are triaging tasks in a client build and wondering where chain-of-thought earns its tokens. Which task types does the module say it measurably improves?

- **A.** Math, logic, and multi-criteria decisions, where working through steps before answering raises measured accuracy  ✅
- **B.** Simple sentiment classification, where reasoning lets the model justify each label before it finally commits to one
- **C.** Short translations, where stepwise reasoning catches idioms that a direct zero-shot pass would consistently miss
- **D.** Basic summarization, where thinking through every sentence first prevents the model from dropping key details

> **Answer:** A

### Q12. Your invoice pipeline needs JSON your code can parse every single time. What does full structured output direction include, per the module?

- **A.** A clear sentence asking for JSON plus a reminder at the end of the prompt, since repetition is what locks a format in
- **B.** The exact schema, a filled-in example, an explicit rule for missing values, and a ban on prose outside the object  ✅
- **C.** A schema alone, since adding a filled example risks the model copying its values into real production outputs
- **D.** Post-processing code that repairs malformed output, since no prompt can hold a format steady at production scale

> **Answer:** B

### Q13. Your extraction system meets an invoice with no vendor phone number. Without explicit direction, what does the module warn happens, and what is the fix?

- **A.** The model returns an error message; direct it to skip the whole record so your parser never sees any partial data
- **B.** The model confidently invents a value; direct it to use null for missing fields, since hallucinated data is worse than none  ✅
- **C.** The model leaves the field blank; direct it to guess from the context, since a plausible value beats an empty one downstream
- **D.** The model halts the whole batch; direct it to flag the document for manual review before continuing to the next one

> **Answer:** B

### Q14. You are assembling a prompt with instructions, examples, input data, and an output slot, and the pieces keep bleeding together. What does the module call especially reliable for separation?

- **A.** Blank lines between sections, since whitespace is the separator that models respect most consistently at scale
- **B.** All-caps section headers, which signal importance strongly enough that the model never confuses the regions
- **C.** Repeating the instructions again after the input, so the most recent text always overrides anything that came earlier
- **D.** XML tags that wrap each section, cleanly separating instructions, examples, input data, and the expected output  ✅

> **Answer:** D

### Q15. A junior builder writes respond in JSON and ships the prompt. Production breaks weekly on JSON-ish output. What does the module prescribe instead?

- **A.** Wrap the request in stronger language like you must respond in valid JSON, since emphasis is what was missing here
- **B.** Ask for XML instead, since XML is forgiving of small errors and parsers recover easily from malformed structures
- **C.** Specify the exact schema, show a filled example, state the null rule, and forbid any prose outside the structure  ✅
- **D.** Retry each failed call up to three times, since occasional JSON-ish output is unavoidable at production volume

> **Answer:** C

### Q16. You want one production prompt that delivers pattern fidelity, reasoning quality, and parseable output together. What stacking approach does the module recommend?

- **A.** Few-shot examples that each walk through the reasoning steps and then end in the exact required output format  ✅
- **B.** Separate prompts for reasoning and formatting, chained so each model call handles exactly one job at a time
- **C.** A single instruction block, since stacking examples with reasoning confuses the model about which to imitate
- **D.** Examples of finished outputs only, since showing reasoning in examples teaches the model to output its thinking

> **Answer:** A

### Q17. Your pipeline runs chain-of-thought on all 10K daily calls, and most are trivial lookups. Token spend has doubled. What does the module tell you to do?

- **A.** Shorten the reasoning to a single sentence per call, keeping the accuracy benefit while halving the token cost
- **B.** Cache reasoning from similar past calls and paste it into new requests so the model skips thinking altogether
- **C.** Accept the spend, since removing reasoning from any production call risks accuracy drops you cannot predict
- **D.** Route simple inputs to a cheap zero-shot prompt and reserve chain-of-thought for genuinely complex decisions  ✅

> **Answer:** D

### Q18. Your reasoning outputs are useful for debugging, but you do not want them stored with final answers. What scratchpad approach does the module describe?

- **A.** Direct reasoning into a marked scratchpad section that your parser strips out before the answer reaches storage  ✅
- **B.** Tell the model to reason silently and output only answers, since hidden reasoning works just like written reasoning
- **C.** Store full reasoning with every record, since audit trails always justify the extra storage and retrieval cost
- **D.** Run each call twice, once with reasoning for quality and once without it to produce the clean stored answer

> **Answer:** A

### Q19. You added chain-of-thought to a classification prompt and costs rose, but you have not checked results. What does the module say decides whether the reasoning stays?

- **A.** Vendor guidance, since model providers publish which task types benefit from added reasoning steps and which do not
- **B.** Team consensus, since experienced builders can usually judge from the outputs whether reasoning is helping
- **C.** Prompt length, since reasoning earns its place whenever the prompt is complex enough to justify extra steps
- **D.** Measurement: if reasoning does not actually move your accuracy metric on real inputs, you cut it from the prompt  ✅

> **Answer:** D

### Q20. An agency teammate adds think step by step to every prompt in a high-volume build, including trivial reformatting tasks. What pitfall is this, per the module?

- **A.** Underspecification, since a generic reasoning trigger is too vague to change model behavior in either direction
- **B.** Chain-of-thought on everything: reasoning tokens on trivial tasks add cost and latency with zero accuracy gain  ✅
- **C.** Format drift, since reasoning text will eventually bleed into structured outputs and break downstream parsers
- **D.** Example dilution, since reasoning instructions compete with few-shot examples and weaken the taught pattern

> **Answer:** B

### Q21. Your team keeps improvising examples on the fly for each new client task, and quality swings wildly. Which toolkit item from the module fixes this?

- **A.** A Cost-Accuracy Ledger: a running log that compares token spend and accuracy numbers across all of your prompt variants
- **B.** A Reasoning Scaffold Template: a reusable block that prescribes numbered thinking steps before a final answer
- **C.** A Schema Contract: the exact output structure your downstream code expects, embedded with a filled-in example
- **D.** An Example Set Builder: a maintained library of vetted, format-consistent examples drawn from real inputs per task  ✅

> **Answer:** D

### Q22. You want inspectable logic on every complex call in a client system, with numbered thinking steps followed by a final answer section. Which toolkit item is this?

- **A.** The Example Set Builder, which stores worked demonstrations that show the model how each task should be solved
- **B.** The Reasoning Scaffold Template, a reusable prompt block prescribing numbered steps inside a thinking section  ✅
- **C.** The Schema Contract, which locks the reasoning format to the exact structure your downstream parser expects
- **D.** The Cost-Accuracy Ledger, which records each reasoning chain alongside its token cost for later inspection

> **Answer:** B

### Q23. Your agency debates prompting technique choices by gut feel and seniority. Which module tool replaces habit with evidence?

- **A.** The Cost-Accuracy Ledger, logging accuracy and token spend per prompt variant so data decides the technique  ✅
- **B.** The Example Set Builder, since a big enough example library removes the need to choose between techniques
- **C.** The Reasoning Scaffold Template, since prescribed steps make every technique perform identically in production
- **D.** The Schema Contract, since locking the output format makes strategy selection a purely cosmetic decision

> **Answer:** A

### Q24. Your parser expects one JSON shape, but the prompt's schema description has slowly diverged from the code over months. Which module tool prevents this?

- **A.** The Cost-Accuracy Ledger, which tracks parsing failures over time so drift shows up in weekly accuracy numbers
- **B.** The Example Set Builder, which refreshes examples monthly so schema changes propagate through demonstrations
- **C.** The Schema Contract: the exact structure embedded in the prompt with a filled example, never allowed to drift from your parser  ✅
- **D.** The Reasoning Scaffold Template, which makes the model restate the schema in its thinking before every output

> **Answer:** C

### Q25. Across everything in Module 3, which overarching principle governs few-shot, chain-of-thought, and structured reasoning?

- **A.** More context always wins: stack every technique in every prompt, because layered direction compounds reliability
- **B.** Reasoning is king: chain-of-thought should anchor every production prompt because accuracy outranks token cost
- **C.** Formatting is cosmetic: focus on strategy selection first, because structure can always be repaired after generation
- **D.** Show the model how, not just what: deploy the cheapest technique that measurably delivers accurate, exactly formatted output  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/106161510_
