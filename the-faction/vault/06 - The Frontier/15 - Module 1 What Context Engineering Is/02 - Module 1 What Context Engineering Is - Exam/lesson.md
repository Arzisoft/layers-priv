---
course: "The Frontier"
module: "Module 1: What Context Engineering Is"
lesson: "Module 1: What Context Engineering Is — Exam"
type: "course_quiz"
post_id: 106578125
space_id: 24391596
source: "https://the-faction.mn.co/posts/106578125"
updated: "2026-08-28T16:31:23Z"
---

# Module 1: What Context Engineering Is — Exam

> Exam for **Module 1: What Context Engineering Is** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder's assistant gave a clean answer to a query on Tuesday and a wrong one to the identical query on Thursday. The prompt did not change. What should the builder examine first?

- **A.** The assembled context for each run, since something the model saw on Thursday differed from Tuesday  ✅
- **B.** The model version and temperature settings, since sampling variation is the usual cause of changed answers
- **C.** The phrasing of the prompt, since small wording differences often flip results between separate runs
- **D.** The output token limit, since responses that run long are often cut and rescored on later identical runs

> **Answer:** A

### Q2. A client hears the word context and assumes it means the prompt. The builder corrects them. Which description is accurate?

- **A.** Context is the background knowledge the model absorbed during training, kept fully separate from anything you send
- **B.** Context is everything the model sees in the window: system prompt, history, documents, tool outputs, user data  ✅
- **C.** Context is the metadata attached to an API call, such as the model name, temperature, and token limits
- **D.** Context is the conversation history alone, while documents and tool outputs travel on separate channels

> **Answer:** B

### Q3. A teammate asks how context engineering differs from prompt engineering. Which answer draws the line correctly?

- **A.** Prompt engineering is for chatbots, while context engineering applies only to retrieval and agent systems
- **B.** Prompt engineering is a temporary workaround, while context engineering will replace prompting entirely
- **C.** Prompt engineering shapes the instruction; context engineering designs the information environment around it  ✅
- **D.** Prompt engineering handles output formatting, while context engineering handles model selection and cost

> **Answer:** C

### Q4. A support bot is asked about a warranty term that exists in company files but was never retrieved into the window. What is true for that call?

- **A.** The model will locate the term from training data if the company publishes its warranty terms publicly
- **B.** The model will ask the user to paste the term, since models request missing information by default
- **C.** The model will return a structured missing-context error rather than attempt to answer the question without the term
- **D.** The term does not exist for the model; it cannot fetch what the window lacks and may guess to fill the gap  ✅

> **Answer:** D

### Q5. An old pricing sheet sits in the window next to the user's question. The prices changed last month. How does the model treat the old sheet?

- **A.** As true for this call; whatever the window contains is reality for a model while it answers  ✅
- **B.** As background it will double-check against newer training data before quoting any figure
- **C.** As untrusted input it will flag to the user, since models detect outdated documents by format
- **D.** As optional reference it consults only when the user explicitly asks about pricing history

> **Answer:** A

### Q6. A builder is starting the first context work on a new app. Per the foundation this course sets, what comes before any tuning or restructuring?

- **A.** Rewriting the system prompt from scratch, so every later measurement starts from clean instructions
- **B.** Logging the complete assembled window for every call, so the builder can see what the model receives  ✅
- **C.** Switching to the largest available model, so window limits do not interfere with early experiments
- **D.** Removing conversation history entirely, so retrieved documents never compete with older messages

> **Answer:** B

### Q7. A builder uses a framework that assembles prompts, history, and documents automatically. Outputs are odd, and the builder has never seen the final payload. What should they direct AI to do?

- **A.** Replace the framework with raw API calls right away, since production abstractions like this cannot be trusted
- **B.** Increase the retrieval count so more documents reach the window and the odd outputs average out
- **C.** Tune the temperature downward until outputs stabilize, then lock the framework configuration in place
- **D.** Capture the exact assembled input the framework sends on each call and inspect it before changing anything  ✅

> **Answer:** D

### Q8. After a builder adds a dozen extra reference documents to every call, answer quality drops on questions the system used to handle well. What most likely happened?

- **A.** The model hit a training data conflict between the new documents and its internal knowledge base
- **B.** The provider silently switched to a smaller model to handle the larger payload within rate limits
- **C.** The additions displaced or buried the content that mattered, since every inclusion competes for space  ✅
- **D.** The new documents changed the tokenizer's segmentation, corrupting the older documents' encoding

> **Answer:** C

### Q9. A standing instruction to answer in the client's brand voice worked until long documents began getting injected above the final question. Now the voice slips. What should the builder check?

- **A.** Where the instruction sits in the window and whether the injected pages bury or crowd it  ✅
- **B.** Whether the client's brand voice conflicts with the model's default persona from its base training
- **C.** Whether the documents contain enough voice examples for the model to imitate reliably
- **D.** Whether the instruction needs stronger wording, such as adding must and always markers

> **Answer:** A

### Q10. A user asks the assistant which subscription tier they are on, and the model answers with a guess. The account data lives in the app's database. Why did this happen?

- **A.** The model chose not to query the database because the user's question lacked an explicit request
- **B.** The database schema was too complex for the model to parse inside a single reasoning pass
- **C.** Nothing placed the account data into the window, so the model had no access to it during the call  ✅
- **D.** The user's phrasing did not match any stored tier names, so the semantic account lookup returned nothing

> **Answer:** C

### Q11. A system tests perfectly in short QA sessions but degrades in production conversations that run past twenty messages. What explains the gap?

- **A.** The model allocates less attention to users who send many messages within a single session
- **B.** The context differs by then: grown history and shifting content change what the model sees  ✅
- **C.** Production traffic runs on rate-limited endpoints that shorten responses in longer sessions
- **D.** Longer sessions accumulate sampling randomness until answers drift from the tested baseline

> **Answer:** B

### Q12. A teammate insists that packing every available document into each call can only help accuracy. What is the correct pushback?

- **A.** Extra documents help only when the model has been fine-tuned on those same document formats
- **B.** Accuracy gains from added documents are real but too expensive to justify at production scale
- **C.** Models cap how many documents they read per call, so extras past the cap are harmlessly skipped
- **D.** Irrelevant content competes with relevant content for space and attention, so more can mean worse  ✅

> **Answer:** D

### Q13. A builder is deciding how to order layers in the window. Which layout reflects the standard this course teaches?

- **A.** Standing rules first, long-lived data next, then delimited documents and history, with the question last  ✅
- **B.** The user's question first so the model reads it before anything else, with instructions closing the window
- **C.** Documents first in order of size, then instructions, with history interleaved between document sections
- **D.** Alphabetical by layer name, a neutral convention that keeps assembly code simple and reproducible

> **Answer:** A

### Q14. The system prompt says quote only current rates, while an injected document still lists last year's rates. The model quotes the old ones without comment. What is the lesson?

- **A.** System prompts always lose to injected documents, so rate rules belong inside the documents themselves
- **B.** The model flagged the conflict internally and chose the document because it appeared later
- **C.** Instruction wording was too soft; an emphatic warning would have forced the current rates
- **D.** Contradictions get resolved silently, so the builder must audit the window for conflicting claims  ✅

> **Answer:** D

### Q15. A returning user references decisions from last week's session, and the assistant draws a blank. The builder is surprised. What did they misunderstand?

- **A.** Retention is disabled by default in the API settings and must be enabled per user before sessions can persist
- **B.** Every call starts blank; the system must re-supply past decisions in the window for the model to know them  ✅
- **C.** The model remembers sessions but only within thirty days, and the recall window had already expired
- **D.** Cross-session recall requires a matching conversation ID, and the app generated a fresh one

> **Answer:** B

### Q16. A builder has verified the window contains correct, current, well-ordered content, yet the tone of answers is off. When is a prompt rewrite the right move?

- **A.** Never: tone problems always trace to context, so the builder should keep auditing the window
- **B.** Only after switching models, since tone is a model property before it is an instruction property
- **C.** Now: once the context checks out, refining how the instruction is phrased is the correct next lever  ✅
- **D.** Only after adding more example documents, since tone is learned from injected samples alone

> **Answer:** C

### Q17. An assistant confidently describes a feature the product does not have. The window contains no feature list at all. What is the model doing?

- **A.** Filling the gap from training, since nothing in the window constrained it; the fix is supplying the facts  ✅
- **B.** Signaling low confidence through detail, a known pattern where fabrication marks missing input
- **C.** Retrieving a competitor's feature list from its training data and quietly misattributing it to this product
- **D.** Testing the user with a deliberate error, a behavior some models show under vague instructions

> **Answer:** A

### Q18. A vibecoder needs a full map of every text source reaching the model in a client app. What is the right way to work?

- **A.** Read every line of the app by hand first, since mapping context is too delicate to delegate to AI
- **B.** Skip the map and rely on the framework docs, which list what standard pipelines send by default
- **C.** Ask the client's developers to describe the flow from memory and treat that account as the map
- **D.** Direct AI to trace the app and produce the diagram and logging, then review its findings personally  ✅

> **Answer:** D

### Q19. Retrieved passages are being pasted into the window as bare text, and the model sometimes blends them with user messages. What practice fixes this?

- **A.** Paraphrase every retrieved passage before injection so it can no longer resemble a user message
- **B.** Move all retrieved passages below the user message so the model reads the question before sources
- **C.** Delimit and label each injected document so the model can tell where sources begin and end  ✅
- **D.** Trim retrieved passages to one sentence each so they are too short to blend into the dialogue

> **Answer:** C

### Q20. Asked to define the discipline in one line for a client deck, which line captures context engineering?

- **A.** Writing instructions so precisely that the model cannot misread them regardless of surrounding input
- **B.** Deciding what enters the model's window, in what order, and with what priority for the task at hand  ✅
- **C.** Selecting the best model and settings for each request based on benchmarks and per-token pricing
- **D.** Compressing every input to the fewest possible tokens to cut cost while preserving exact wording

> **Answer:** B

### Q21. A builder wonders whether learning context engineering makes prompt skills obsolete. What is the accurate framing?

- **A.** They are companions: instructions still need crafting, and they operate inside a designed environment  ✅
- **B.** Prompt skills matter only for consumer chat products, while context engineering owns all production work
- **C.** Context engineering is a rebranding of prompt engineering, so the skills are interchangeable
- **D.** Prompt skills become obsolete once retrieval works, since documents replace the instructions

> **Answer:** A

### Q22. After three inconsistent runs, a builder writes in the project channel that the model is simply unreliable. What did the builder skip?

- **A.** Filing a provider support ticket, which is the standard escalation path for reproducible model regressions
- **B.** Checking whether the inputs varied: history, retrievals, or tool outputs likely differed across runs  ✅
- **C.** Raising the temperature to smooth the variance, which stabilizes outputs across repeated calls
- **D.** Rewriting the prompt with numbered steps, which removes ambiguity that causes inconsistency

> **Answer:** B

### Q23. A context audit is beginning on an inherited app. What is the first deliverable to direct AI to produce?

- **A.** A rewritten system prompt reflecting best practices, giving the audit a clean baseline to measure
- **B.** A cost report by endpoint, since spending patterns reveal which calls carry the heaviest windows
- **C.** A benchmark of the current model against alternatives, showing whether context work is needed
- **D.** An inventory of every text source that reaches the model from system prompt through tool outputs  ✅

> **Answer:** D

### Q24. A builder wants to add a helpful FAQ section to every window and sees no downside since space remains. What principle applies?

- **A.** FAQ content is uniquely safe to include because its question format matches how users phrase their queries
- **B.** Additions are free until the window is 90 percent full, the threshold where displacement begins
- **C.** Inclusion always costs exclusion eventually; every addition must earn its place against alternatives  ✅
- **D.** Static additions are fine; only dynamic content like history and retrievals competes for space

> **Answer:** C

### Q25. One principle underlies this entire module and every technique built on it. Which statement expresses it?

- **A.** The window is a model's entire reality: control what fills it and you control the quality that comes out  ✅
- **B.** The model is the system's entire intelligence: choose the strongest model and quality follows naturally
- **C.** The prompt is the system's entire interface: perfect the instruction and surrounding input follows along
- **D.** The user is the system's entire variable: train users to ask better questions and outputs improve to match

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106578125_
