---
course: "The Frontier"
module: "Module 4: Context Window Management"
lesson: "Module 4: Context Window Management — Exam"
type: "course_quiz"
post_id: 106161658
space_id: 24391596
source: "https://the-faction.mn.co/posts/106161658"
updated: "2026-08-21T15:23:00Z"
---

# Module 4: Context Window Management — Exam

> Exam for **Module 4: Context Window Management** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A support bot handling 10K conversations a day starts answering refund questions wrong on long chats, politely and confidently, with nothing in the logs. What is the most likely cause?

- **A.** Long conversations pushed the refund policy out of effective attention, so the bot answers confidently from what remains.  ✅
- **B.** The model's weights degraded from heavy traffic volume, so retraining on recent conversations is needed to restore accuracy.
- **C.** The refund policy text contains formatting the model cannot parse, so it falls back to generic answers on longer threads.
- **D.** The bot's temperature setting drifts upward on long chats, making outputs more random once history grows past a few turns.

> **Answer:** A

### Q2. A builder directing a data extraction system expects the model to remember yesterday's calls and stops resending the task spec. Extractions come back generic. What did they misunderstand?

- **A.** The context window is working memory that does not persist between calls, so every call must include what the model needs.  ✅
- **B.** The context window persists per account but resets weekly, so the spec only needs resending after each reset cycle occurs.
- **C.** The model stores prior calls in long-term memory but retrieval from it is unreliable, so specs should be resent sometimes.
- **D.** The spec was remembered but deprioritized, since models weight recent user messages far above older system instructions.

> **Answer:** A

### Q3. A brand-voice content pipeline keeps hitting the context limit even though the input document alone seems small enough to fit. The builder forgot part of the budget. What counts against the context window?

- **A.** Only the user's current message and the retrieved documents, since system prompts are stored separately by the platform.
- **B.** Only the input tokens, because the model's output streams straight to the user and never occupies space in the window.
- **C.** The conversation history alone, since system prompts and outputs are billed separately and tracked outside the window.
- **D.** Everything in the call, including the system prompt, history, retrieved documents, and the model's own output tokens.  ✅

> **Answer:** D

### Q4. An agency's client chatbot works for the first 20 turns, then forgets the client's stated goal and its own persona. The platform truncates silently. What is lost first, and why is that dangerous?

- **A.** The most recent turns get cut first, which is dangerous because the user's latest question disappears before the answer.
- **B.** Random middle turns get dropped, which is dangerous because the losses are unpredictable and cannot be designed around.
- **C.** The oldest turns get cut first, which is dangerous because original instructions and key facts live exactly there.  ✅
- **D.** Retrieved documents get dropped before conversation turns, which is dangerous because the knowledge base disappears.

> **Answer:** C

### Q5. A long-document analysis system buries its critical output-format rules in the middle of a 60K-token assembled context, and formatting compliance drops. What does the module say about position?

- **A.** Position is irrelevant inside the window; once content fits, the model attends to all of it equally regardless of order.
- **B.** Mid-context is the strongest position because the model builds understanding toward the middle before attention tapers.
- **C.** Only the very first tokens get strong attention, so all rules must appear in the opening lines or they are lost.
- **D.** Material buried mid-context gets weaker attention than material at the edges, so critical rules belong at the boundaries.  ✅

> **Answer:** D

### Q6. A builder chunks a 200-page contract every 4,000 characters for a data extraction system, and clauses get misread wherever splits land mid-section. What is the professional chunking approach?

- **A.** Shrink chunks to 1,000 characters each, since smaller pieces give the model less text to misread in any single pass.
- **B.** Split on natural boundaries like sections and clauses, with slight overlap so facts straddling a split are never lost.  ✅
- **C.** Keep 4,000-character chunks but sort them by keyword relevance so the most important sections get processed first in line.
- **D.** Remove chunking entirely and send the whole contract, since modern context windows make splitting documents unnecessary.

> **Answer:** B

### Q7. In a chunking pipeline for long reports, chunks 2 through 9 come back off-task while chunk 1 is perfect. After the first call, each call sends only the chunk text. What did the builder miss?

- **A.** Later chunks need progressively simpler instructions, because the model tires as it processes more pieces of a document.
- **B.** Every chunk must be paired with the complete instruction set, since each call starts fresh with no memory of chunk 1.  ✅
- **C.** Chunks after the first should include the full text of all prior chunks so the model can rebuild the document's flow.
- **D.** The pipeline should process chunks in reverse order, since models attend most strongly to whatever material arrives first.

> **Answer:** B

### Q8. A chunked analysis of a long contract returns per-chunk findings that conflict on dates and party names. The builder ships the raw concatenation. What step does the module's chunking pipeline add?

- **A.** A voting step where the model reruns each chunk three times and keeps whichever finding appears most often across runs.
- **B.** A filtering step that discards any chunk whose findings disagree with chunk 1, treating the opening as the ground truth.
- **C.** A reconciliation pass that merges per-chunk results, resolving conflicts before anything is treated as final output.  ✅
- **D.** A retrieval step that stores findings in a database so downstream calls can look up whichever version they prefer.

> **Answer:** C

### Q9. A support bot compresses long chats into rolling summaries, but downstream calls start refunding the wrong invoices. The summary reads like a friendly recap. What must a rolling summary preserve?

- **A.** The full verbatim text of every customer message, since paraphrasing any turn risks losing exact phrasing.
- **B.** Decisions, commitments, identifiers, and constraints, while pleasantries and dead ends are deliberately discarded.  ✅
- **C.** The emotional tone of the conversation above all, since sentiment drives how the next agent should approach the customer.
- **D.** Only the last three turns in full detail, because recent context always matters more than older decisions or commitments.

> **Answer:** B

### Q10. A support bot must answer from a 500-page help center. Pasting all of it into each call is too costly and degrades accuracy. What approach does the module recommend for this situation?

- **A.** Summarize the entire help center down to two pages once, then send that fixed summary with every single customer query.
- **B.** Fine-tune the model on the help center so the knowledge lives in its weights and calls need no reference text at all.
- **C.** Store the knowledge base outside the model and retrieve only the passages relevant to each query at call time.  ✅
- **D.** Split the help center across ten sequential calls per query so every page is eventually seen by the model.

> **Answer:** C

### Q11. A retrieval-backed extraction system confidently outputs field values that appear nowhere in the source documents. Retrieval sometimes misses the right passage. What safeguard does the module prescribe?

- **A.** Instruct the model to answer only from provided material, and treat retrieval quality as the system's real ceiling.  ✅
- **B.** Raise the model's creativity settings so it can reason its way to correct values when the right passage is not retrieved.
- **C.** Add more documents to every call as backup context, since a bigger retrieval set guarantees the right passage appears.
- **D.** Have the model rate its own confidence and accept answers above 80 percent, filtering fabrications automatically.

> **Answer:** A

### Q12. A brand-voice pipeline stuffs every style guide, past post, and example into each call. Costs triple and output quality actually drops slightly. What principle explains the quality drop?

- **A.** More context always helps quality, so the drop must come from the model version and not from the size of the input.
- **B.** Quality drops only when the window is fully exceeded, so the pipeline must be silently truncating past the hard limit.
- **C.** Past a point, irrelevant context degrades quality by diluting attention, so the target is minimum sufficient context.  ✅
- **D.** Style guides inherently conflict with examples, so pipelines must always choose one or the other and never send both.

> **Answer:** C

### Q13. An agency team's prompts balloon over months as everyone adds instructions, and nobody can say where the tokens go. Which toolkit practice does the module prescribe for this?

- **A.** Freeze the prompts permanently after launch so no one can add instructions without a full rebuild of the entire pipeline.
- **B.** Assign an explicit token budget to each prompt section and enforce it, turning context bloat into a reviewable diff.  ✅
- **C.** Switch to the largest available context window so growth in prompt size never becomes a practical constraint again.
- **D.** Rotate prompt ownership weekly so each teammate personally feels the cost of bloat and trims instructions voluntarily.

> **Answer:** B

### Q14. A builder must cut a 6,000-token prompt roughly in half without hurting output quality for a content system. What does the module's prompt compression pass involve?

- **A.** Delete the second half of the prompt, since instructions near the end contribute least to how the model performs.
- **B.** Strip redundant phrasing, collapse repeated instructions, convert prose rules to tight lists, and cut stale examples.  ✅
- **C.** Replace instructions with shorthand codes the model infers from patterns, halving tokens while keeping every rule intact.
- **D.** Move most instructions into the user message, where tokens are billed at a lower rate than in the system prompt section.

> **Answer:** B

### Q15. A builder is deciding whether a document workflow should run as one large call or several smaller calls. What does the module say should drive that architecture choice?

- **A.** Always prefer a single call, because every extra call adds latency and multi-call designs cost more in every situation.
- **B.** Always prefer multiple calls, because smaller contexts are more accurate and failures never span multiple steps.
- **C.** Weigh quality, cost, and failure isolation together, choosing whichever architecture the tradeoffs actually favor.  ✅
- **D.** Follow the platform default, since providers tune their models for one architecture and deviating degrades the output.

> **Answer:** C

### Q16. A content pipeline generates each section of a brand report in separate calls to save context. The sections come back reading as if different brands wrote them. What went wrong?

- **A.** The model randomizes tone between calls by design, so multi-call pipelines can never produce a consistent brand voice.
- **B.** The task was split without sharing the context each call needed, so calls lacking what the others knew drifted apart.  ✅
- **C.** The brand guidelines were too long to fit into any call, so the pipeline needs a bigger model, not a redesign.
- **D.** Sections must always be generated in one single call, since splitting writing tasks across calls violates best practice.

> **Answer:** B

### Q17. A profitable support pipeline at 10K conversations a day quietly becomes a money loser after a teammate adds a large reference document to every call. What does the module say about this?

- **A.** Token costs are flat per call regardless of size, so the loss must come from added latency and infrastructure charges.
- **B.** Reference documents are cached free after first use on every platform, so the document cannot be causing the loss.
- **C.** Cost per call is negligible at any scale, so the team should look at staffing and tooling before touching the prompts.
- **D.** Tokens are billed on every call, so bloated context multiplied across thousands of daily runs becomes a money leak.  ✅

> **Answer:** D

### Q18. A builder's long-running assistant slowly loses its persona and task rules as conversations grow, while recent chit-chat survives every truncation. What do professional systems do instead?

- **A.** Pin what must survive, like the system prompt, task spec, and critical entities, and compress or drop everything else.  ✅
- **B.** Restart every conversation at 20 turns, since no design can keep instructions alive once history begins to truncate.
- **C.** Repeat the full system prompt inside every user message so at least one recent copy always survives any truncation.
- **D.** Store the persona in the model's settings page, where platform memory keeps it outside the context window entirely.

> **Answer:** A

### Q19. In a contract extraction system, a chunk containing a penalty clause gets misinterpreted because the defined terms it relies on live in a different chunk. Which failure mode is this?

- **A.** Retrieval failure, since the model fabricated an answer after the search step returned the wrong passage from storage.
- **B.** Summary poisoning, since a rolling summary dropped a load-bearing fact that every downstream call then trusted fully.
- **C.** Output overflow, since the model's own response tokens crowded the clause text out of the available context window.
- **D.** A chunk stripped of needed context, the classic chunking failure where a clause is severed from its defined terms.  ✅

> **Answer:** D

### Q20. A coaching bot holds conversations spanning weeks. The full history no longer fits, but past decisions and commitments must inform every reply. Which strategy fits this situation best?

- **A.** A rolling summary that compresses history into dense state, preserving decisions, identifiers, and constraints.  ✅
- **B.** Chunking the conversation history and processing every chunk on each new message before generating the final reply.
- **C.** Dropping all history each session and asking the user to restate anything important at the start of each one.
- **D.** Raising the context limit with a larger model tier, since strategy changes only matter when no bigger window exists.

> **Answer:** A

### Q21. A data extraction system fed a 200-page contract in one call returns plausible values for fields in the middle sections that turn out to be fabricated. What does the module say happened?

- **A.** The model effectively skimmed the middle and hallucinated plausible values for the sections it lost, with no warning.  ✅
- **B.** The contract's middle sections used legal language the model was never trained on, so it mistranslated them.
- **C.** The platform refunded the unprocessed tokens and returned partial output, which the pipeline mistook for a full result.
- **D.** The model processed everything fully, but the extraction schema had typos that corrupted the middle fields specifically.

> **Answer:** A

### Q22. A new agency hire argues the team should paste entire client documents into every prompt because it is simpler than building a pipeline. How does the module characterize this approach?

- **A.** A valid professional default, since completeness beats efficiency whenever accuracy matters more than the token bill.
- **B.** Correct for documents under 100 pages, with pipelines only becoming worthwhile once inputs pass that threshold size.
- **C.** A reasonable prototype tactic that also scales fine to production as long as documents fit inside the window limit.
- **D.** The mark of a hobbyist, since cost scales with document size instead of task size and mid-document quality drops.  ✅

> **Answer:** D

### Q23. A builder's chunking pipeline splits cleanly on section boundaries but still loses facts that sit right at the split points between sections. What does the module add to prevent this?

- **A.** A second model pass that guesses what likely appeared near each boundary and reinserts it into the neighboring chunks.
- **B.** Larger chunks overall, since any pipeline losing boundary facts is simply using pieces that are too small to be safe.
- **C.** Slight overlap between adjacent chunks, so facts straddling a boundary appear whole in at least one of the pieces.  ✅
- **D.** A rule that documents must be reformatted before processing so no fact ever sits near a section boundary at all.

> **Answer:** C

### Q24. An ops lead asks why the support bot's context problems never showed up in error monitoring before customers complained. What does the module say about context failures in production?

- **A.** They always raise truncation warnings in the API response, so the monitoring simply was not parsing the right field.
- **B.** They only occur during traffic spikes, so monitoring tuned to normal load will catch them once thresholds adjust.
- **C.** They surface as obvious gibberish output, so any human spot-check of transcripts would have caught them immediately.
- **D.** They are silent; the system keeps answering politely and confidently while wrong, so customers find out before logs.  ✅

> **Answer:** D

### Q25. Which statement best captures the governing principle of Module 4, Context Window Management?

- **A.** Exactly the right information in front of the model and nothing else; minimum sufficient context drives cost, speed, and accuracy.  ✅
- **B.** Maximize the information the model sees on every call, since more context reliably improves output quality at any scale.
- **C.** Choose the model with the largest context window available, since window size is the main driver of production quality.
- **D.** Avoid multi-call architectures whenever possible, since single calls are always cheaper and easier to debug in production.

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106161658_
