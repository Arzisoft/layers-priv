---
course: "The Frontier"
module: "Module 6: Context Quality and Debugging"
lesson: "Module 6: Context Quality and Debugging — Exam"
type: "course_quiz"
post_id: 106578141
space_id: 24391596
source: "https://the-faction.mn.co/posts/106578141"
updated: "2026-08-28T16:34:47Z"
---

# Module 6: Context Quality and Debugging — Exam

> Exam for **Module 6: Context Quality and Debugging** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A client reads an assistant's answer and calls it obviously trustworthy: polished, confident, well structured. What does this module say that polish actually proves?

- **A.** Nothing about the input: the model writes fluently over bad context just as easily as good  ✅
- **B.** That the window was assembled correctly, since broken context produces broken prose
- **C.** That retrieval succeeded, because models hedge visibly whenever sources are missing
- **D.** That the system prompt is working, since confidence is a directly instructed behavior

> **Answer:** A

### Q2. A bug report closes with the note: cause was model hallucination. Why does this module reject that as a final diagnosis?

- **A.** Because hallucination is a licensing term that providers reserve for filed incident reports
- **B.** Because current models no longer hallucinate, so another failure must be responsible
- **C.** Because it stops one layer short: the window usually explains why the model invented  ✅
- **D.** Because hallucination only occurs at high temperatures, which production never uses

> **Answer:** C

### Q3. An assistant recommends a service package the company retired last spring. The window contains a document describing that package as current. Which failure family is this?

- **A.** Displacement: newer material was pushed out of the window by older material that outranked it
- **B.** Retrieval miss: the current catalog never made it into the assembled window at all
- **C.** Contradiction: two documents disagree and the model simply chose the wrong one
- **D.** Stale information: the window carries a fact that was once true and no longer is  ✅

> **Answer:** D

### Q4. A system prompt orders formal tone; an injected style memory says the user prefers casual banter. The model wobbles between the two across a session. Which family is this?

- **A.** Stale information, since one of the two conflicting style rules must surely have expired by now
- **B.** Contradictory instructions: parts of the window disagree, and the model resolves it silently  ✅
- **C.** Displacement, since the larger of the style documents is crowding out the smaller one
- **D.** Retrieval miss, since the definitive style guide never entered the assembled window

> **Answer:** B

### Q5. The right passage was retrieved and sits in the window, but it is buried under nine loosely related passages, and the answer misses it. Which family is this?

- **A.** Displacement: relevant content lost the competition for attention to irrelevant content  ✅
- **B.** Retrieval miss: nine bad passages prove the search never really found the right one
- **C.** Stale information: passages buried that deep have usually expired by retrieval time
- **D.** Contradiction: ten passages cannot coexist without disagreeing somewhere inside

> **Answer:** A

### Q6. A user asks about a niche policy, nothing relevant was retrieved, and the model produces a plausible answer anyway. Which family, and what filled the void?

- **A.** Displacement; the policy passage was present but crowded out by the conversation history
- **B.** Retrieval miss; the model filled the gap from its training data, invisibly and fluently  ✅
- **C.** Contradiction; two policy versions clashed and the model blended them together
- **D.** Stale information; an expired policy was retrieved and presented as the answer

> **Answer:** B

### Q7. A builder wants the single foundational capability this module says all context debugging rests on. What is it?

- **A.** A prompt library with version history, so instruction changes can be correlated to bugs
- **B.** An automatic re-run harness that retries failed answers with escalating temperatures
- **C.** A complete log of every assembled window, per layer, with token counts, keyed by request  ✅
- **D.** A quality classifier that scores each output and files low scores into a review queue

> **Answer:** C

### Q8. Two builders debug the same bad output. One reads the logged window; the other reasons about what the window probably contained. What is the second builder doing?

- **A.** Practicing hypothesis-driven debugging, the faster method when logs are large
- **B.** Working at a higher level of abstraction, which scales far better across many incidents
- **C.** Applying prior experience, which this module ranks equal to reading the logs
- **D.** Debugging from imagination, which this module names as the thing logging exists to end  ✅

> **Answer:** D

### Q9. The same query produced a great answer Tuesday and a poor one Thursday. Logs exist for both. What is the move this module prescribes?

- **A.** Diff the two assembled windows layer by layer and find what changed between the runs  ✅
- **B.** Re-run the query ten times and keep whichever distribution of answers looks healthier
- **C.** Compare the two model versions, since mid-week provider updates explain most drift
- **D.** Interview the user about phrasing differences too subtle to appear in the logging

> **Answer:** A

### Q10. A retrieval test set was built at launch and passed. Months later, documents have changed and the index was rebuilt twice. What does this module say about that test set now?

- **A.** It should be re-run on a schedule, because retrieval quality decays silently as things change  ✅
- **B.** It is still valid, because test sets measure the pipeline design rather than the data
- **C.** It should be retired, because mature systems are better measured by user ratings
- **D.** It applies only to the original index, so each rebuild needs a brand new test set

> **Answer:** A

### Q11. A builder schedules a monthly review: sample twenty real requests, and for each compare what the window contained against what the recipe says it should contain. What is this practice?

- **A.** A regression test, verifying that code changes have not altered the retrieval quality metrics
- **B.** A context audit, the systematic check for gaps between what is seen and what should be  ✅
- **C.** A load test, confirming the assembly pipeline holds up under production traffic
- **D.** A postmortem, the structured review that follows a user-visible quality incident

> **Answer:** B

### Q12. During an audit, a builder examines one layer of a sampled window. Which checklist does this module give for that examination?

- **A.** Encrypted, deduplicated, compressed, cached, and indexed for the fastest lookup
- **B.** Spell-checked, formatted, sourced, timestamped, and attributed to a document owner
- **C.** Readable, grammatical, concise, well ordered, and free of markup artifacts
- **D.** Present, correct, current, labeled and worth the tokens it occupies in the window  ✅

> **Answer:** D

### Q13. A quality bug lands on a builder's desk. Ranked by this module's debugging ladder, which action belongs at the very end, not the beginning?

- **A.** Pulling the logged window for the failing request and reading it front to back
- **B.** Checking the four failure families against what the logged window contains
- **C.** Editing the prompt, which comes last and only after the context checks out  ✅
- **D.** Reproducing the failure so its exact request ID can be traced in the logs

> **Answer:** C

### Q14. A builder has the failing window open and starts triage. In what order does this module walk the four families?

- **A.** Stale, then contradictory, then present-but-buried, then absent entirely  ✅
- **B.** Absent first, then buried, then contradictory, with staleness checked last
- **C.** Contradictions first since they are quickest, then stale, buried, and absent
- **D.** Whichever order intuition suggests, since the families rarely overlap in practice

> **Answer:** A

### Q15. Triage concludes the needed passage never entered the window. Where does the investigation go next?

- **A.** To the prompt, which most likely failed to tell the model the passage was important
- **B.** Into the retrieval logs, to find where the pipeline lost it: chunking, threshold, or re-ranking  ✅
- **C.** To the provider status page, since ingestion outages explain most missing passages in production
- **D.** To the user's phrasing, which should be rewritten until the passage starts appearing

> **Answer:** B

### Q16. Triage instead finds the passage present in the window, yet the answer ignored it. What does this module say to examine now?

- **A.** The passage's grammar and layout, since models discount text with formatting irregularities
- **B.** The embedding scores, since low-scored passages are ignored even once injected
- **C.** The user's history, since models deprioritize passages users have seen before
- **D.** Its position in the window and what surrounded it, checking for burial and crowding  ✅

> **Answer:** D

### Q17. A root cause is found in the memory layer and corrected. Besides shipping the fix, what does the ladder require before the case is closed?

- **A.** A full re-audit of all layers, since one confirmed bug predicts several undiscovered ones
- **B.** A user notification describing the bug, its duration, and the correction applied
- **C.** Adding the failing case to the regression set so the fix is defended going forward  ✅
- **D.** A rollback plan documenting how to restore the previous memory configuration

> **Answer:** C

### Q18. Instead of fixing a known stale-document problem, a builder keeps adding prompt lines like ignore outdated pricing wherever it appears. What is the predictable result?

- **A.** Instruction clutter accumulates, often breeding new contradictions while the root cause remains  ✅
- **B.** The prompt hardens into a robust filter that reliably screens stale content at inference
- **C.** Cost falls slightly, since instruction tokens are billed at a discounted internal rate
- **D.** The model learns the pattern across sessions and begins ignoring stale data unprompted

> **Answer:** A

### Q19. A builder hits regenerate until a wrong answer comes out right, then closes the ticket. What has actually been accomplished?

- **A.** A verified fix, since a correct answer proves that the underlying context has healed itself
- **B.** A useful workaround that buys time while the root cause is separately pursued
- **C.** A data point for the provider, whose sampling telemetry now flags the variance
- **D.** Nothing durable: the cause is untouched and unlearned, and the failure will return  ✅

> **Answer:** D

### Q20. Two injected sources quietly disagree about a client's renewal date, and answers stay fluent while alternating between dates. Why do these bugs live so long in production?

- **A.** Renewal dates change often enough that users assume the variation must be intentional
- **B.** Models flag contradictions in a metadata field that most logging setups discard
- **C.** The output never looks broken: the model just picks a side without telling anyone  ✅
- **D.** Contradiction bugs self-resolve as sessions age out and old sources drop away

> **Answer:** C

### Q21. An assistant quoted a discount that expired last quarter; the logged window shows the old and new pricing sheets were both indexed and both retrieved. What is the root-cause fix?

- **A.** Add a prompt instruction telling the model to prefer the newer of two conflicting pricing documents
- **B.** Purge superseded documents and filter retrieval by a currency flag so only current ones surface  ✅
- **C.** Lower top-k to one so that only the single strongest pricing document ever gets injected
- **D.** Fine-tune the model on the current pricing so stale retrievals stop influencing its quotes

> **Answer:** B

### Q22. A team is picking between Langfuse, LangSmith, and a plain JSONL log for tracing. Per this module, what is the non-negotiable requirement any choice must meet?

- **A.** Full input capture per call, keyed to a request ID findable from a user complaint  ✅
- **B.** Real-time alerting with paging integration for any drop in output quality scores
- **C.** Self-hosting, since third-party tracing services cannot store client context legally
- **D.** Automatic redaction of all user data before any window is written to storage

> **Answer:** A

### Q23. Every individual bug gets fixed promptly, yet a quarterly review finds the system quietly degraded across the board. What does this module say per-bug fixing structurally misses?

- **A.** Provider regressions, which arrive silently and affect every layer of the system at once
- **B.** User drift, as query patterns slowly evolve away from the original design assumptions
- **C.** Hardware variance, which accumulates in the embedding math over many months of operation
- **D.** Slow rot: systemic decay that only scheduled audits sample broadly enough to catch  ✅

> **Answer:** D

### Q24. A model follows a formatting instruction most of the time but drops it on certain queries. Logs show those queries pull in a particular document set. What should the builder search for?

- **A.** A token limit collision, since long documents force the model to abbreviate formats
- **B.** A competing instruction inside those documents that contradicts a formatting rule  ✅
- **C.** A sampling anomaly, since instruction-following varies naturally between queries
- **D.** A retrieval miss, since the formatting rule likely failed to enter those windows

> **Answer:** B

### Q25. One conviction underlies every practice in this module, from logging to diffing to audits. Which statement is it?

- **A.** Most output problems are model problems, so escalation to the provider comes first
- **B.** Quality is subjective, so debugging should follow user sentiment rather than logs
- **C.** Context failures produce output that looks right, so you must see what the model saw  ✅
- **D.** Debugging is wasteful, since regenerating answers is cheaper than investigation

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106578141_
