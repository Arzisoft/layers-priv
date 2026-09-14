---
course: "The Frontier"
module: "Module 3: Information Retrieval and Selection"
lesson: "Module 3: Information Retrieval and Selection — Exam"
type: "course_quiz"
post_id: 106578133
space_id: 24391596
source: "https://the-faction.mn.co/posts/106578133"
updated: "2026-08-28T16:32:49Z"
---

# Module 3: Information Retrieval and Selection — Exam

> Exam for **Module 3: Information Retrieval and Selection** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A client hears the term RAG and asks whether it is a separate discipline from the context work already underway. How should the builder frame it?

- **A.** RAG is a database technology that replaces context design once a vector store is installed
- **B.** RAG is a fine-tuning method that bakes company documents directly into the model's own weights
- **C.** RAG is a context engineering pattern: one pipeline for getting the right content into the window  ✅
- **D.** RAG is a provider-side feature that must be enabled on each account before documents become searchable

> **Answer:** C

### Q2. A search for refund policy returns a passage about getting money back, though the two share almost no words. What made that match possible?

- **A.** Embeddings encode meaning as vectors, so texts land near each other by sense rather than wording  ✅
- **B.** The search engine expanded the query with synonyms pulled from a maintained dictionary file
- **C.** The passage was manually tagged with the phrase refund policy by the person who indexed the documents
- **D.** The model rewrote the stored passage at query time until it matched the words being searched

> **Answer:** A

### Q3. A builder must pick a chunk size and asks what the tradeoff actually is. Which statement gets it right?

- **A.** Smaller chunks cost more to store, while larger chunks are cheaper but slower to embed at scale
- **B.** Small chunks are precise but lose surrounding meaning; large chunks keep context but dilute the signal  ✅
- **C.** Chunk size only affects indexing speed, so the choice comes down to how often documents change
- **D.** Larger chunks always win, because carrying extra context per chunk gives the model much more to reason over

> **Answer:** B

### Q4. A fact sits at the boundary where one chunk ends and the next begins. Without a specific chunking setting, queries about it fail. Which setting exists for exactly this case?

- **A.** Stemming, which normalizes word endings so boundary terms match across the chunk divide
- **B.** Sharding, which distributes chunks across stores so boundary facts appear in multiple shards
- **C.** Padding, which inserts neutral filler tokens so no fact ever touches the edge of a chunk
- **D.** Overlap, which repeats text across neighboring chunks so boundary facts are never orphaned  ✅

> **Answer:** D

### Q5. Two pipelines chunk the same manual: one splits every 500 characters wherever that falls, one splits at sections and paragraphs. Why does the second reliably retrieve better?

- **A.** Section-based chunks are smaller on average, and smaller chunks always outperform larger ones
- **B.** Character splitting is fine for prose but fails on code, which the manual presumably contains
- **C.** Fixed-length chunks exceed embedding model limits, so parts of the manual were never indexed
- **D.** Splitting at semantic boundaries keeps each chunk a coherent thought that queries can match  ✅

> **Answer:** D

### Q6. Answers keep rambling across irrelevant sources, and the window arrives stuffed with barely related passages. In precision and recall terms, what is the diagnosis?

- **A.** Low precision: much of what is being retrieved is not relevant, and the noise buries the signal  ✅
- **B.** Low recall: the relevant passages exist in the index but are never being returned by search
- **C.** High precision paired with high recall, which overloads the window with too much good content
- **D.** Neither metric is implicated; rambling answers trace to instructions, not to retrieval quality

> **Answer:** A

### Q7. The answer to a user's question sits in an indexed document, yet the passage never appears in any retrieval, and the model improvises instead. Which metric captures this failure?

- **A.** Precision, because the passages that were returned turned out to be loosely related noise
- **B.** Latency, because slow retrievals time out and fall back to answering without documents
- **C.** Recall, because something relevant existed and a retrieval step failed to bring it back  ✅
- **D.** Coverage, because the indexing job skipped the document type that held the answer text

> **Answer:** C

### Q8. A builder fixes a recall problem by raising top-k from 5 to 25, and a week later answers are vaguer than before. What dynamic is at work?

- **A.** The vector store slows down noticeably at higher k values, and timeouts now truncate the retrieved content
- **B.** Tuning one metric cost the other: recall rose, but precision collapsed and noise buried the signal  ✅
- **C.** Higher k triggers provider-side deduplication, which discards the most relevant passages first
- **D.** The embedding model caps results at 20, so the extra passages arrive empty and pad the window

> **Answer:** B

### Q9. A pipeline retrieves twenty candidates by vector similarity, scores them against the query with a second step, and injects the best five. What is this pattern, and what does it buy?

- **A.** Re-ranking: it raises precision without sacrificing recall by casting wide and keeping the best  ✅
- **B.** Ensembling: it merges results from multiple embedding models to reduce single-model bias
- **C.** Caching: it stores the twenty candidates so repeat queries can skip the vector search entirely
- **D.** Boosting: it retrains the retriever after each query so future searches score similar candidates better

> **Answer:** A

### Q10. A retrieval step returns nothing useful, and nobody notices for three weeks because outputs stayed fluent. Why does this failure mode hide so well?

- **A.** Vector stores log failures only at debug level, which production configurations suppress
- **B.** Users rarely ask questions that depend on documents, so the gap surfaces only in audits
- **C.** Fluent output is cached from earlier successful runs and replayed when retrieval fails
- **D.** The model answers either way, from training data if needed, so nothing visibly breaks  ✅

> **Answer:** D

### Q11. A builder wants retrieval quality to be a number instead of a feeling. What should they direct AI to build first?

- **A.** A dashboard tracking the average similarity scores across every production query from the last several months
- **B.** A test set of real questions, each mapped to the passage that answers it, scored for precision and recall  ✅
- **C.** A user survey asking whether the answers feel grounded in the company's actual documents and policies
- **D.** A weekly export of the ten longest conversations for careful manual review by the client team

> **Answer:** B

### Q12. A teammate defends a bad retrieval by pointing at its high similarity score: the math says it matches. What is the correct correction?

- **A.** Similarity scores are comparable only within one document, not across the whole index
- **B.** Scores below one are inherently unreliable and should be filtered before any injection
- **C.** Nearest means least far away, not relevant; a top result can still be useless for a query  ✅
- **D.** The score proves the match; if the answer was wrong, the fault lies with the prompt wording

> **Answer:** C

### Q13. Questions about parental leave keep failing even though the policy is thoroughly documented. Logs show the crucial table was split across three fragments at indexing. What is the fix?

- **A.** Re-chunk at section boundaries keeping tables whole, so the policy becomes findable as one unit  ✅
- **B.** Add the words parental leave to the system prompt so the model recognizes the topic reliably
- **C.** Raise the top-k setting until all three fragments are retrieved together on every leave-related query
- **D.** Lower the similarity threshold so weaker matches to the fragments can reach the window

> **Answer:** A

### Q14. Even with good retrieval, some questions will fall outside the document set. What instruction protects the system in those moments?

- **A.** Answer only from the provided passages and say the sources do not cover it when they do not  ✅
- **B.** Answer every question fully, drawing on general knowledge whenever the passages fall short
- **C.** Refuse all questions scoring below the similarity threshold, returning a standard error text
- **D.** Redirect uncovered questions to a human agent silently, without telling the user anything

> **Answer:** A

### Q15. Chunks arrive in the window as bare paragraphs, and answers cite facts without any traceable source. What injection practice is missing?

- **A.** Compression, which strips each chunk to one sentence so citations become unambiguous
- **B.** Deduplication, which removes near-identical chunks so that each fact has exactly one source chunk
- **C.** Ranking annotations, which order chunks by score so the model cites the strongest first
- **D.** Delimiters and source labels, so the model knows where each document begins and comes from  ✅

> **Answer:** D

### Q16. A builder is directing AI to implement query-time retrieval and wants the steps in the right order. Which sequence is correct?

- **A.** Re-rank the index, embed the results, search the query, then inject whatever happens to score highest
- **B.** Embed the query, find nearest chunks, re-rank the candidates, inject the top few with labels  ✅
- **C.** Inject the query into the window, retrieve from history, embed the answer, then re-rank it
- **D.** Search by keyword first, embed only the misses, then merge both lists without re-ranking

> **Answer:** B

### Q17. Per this module, a retrieval failure discovered today often traces to a decision made weeks earlier. Which decision, and why?

- **A.** The model choice, because retrieval quality is mostly a property of the generating model
- **B.** The threshold setting, because it drifts upward automatically as the index grows larger
- **C.** Chunking at indexing time, because how documents were split determines what search can find  ✅
- **D.** The prompt template, because instruction wording shapes which chunks the store returns

> **Answer:** C

### Q18. A team switches to a new embedding model with better benchmarks and immediately retrieval breaks everywhere. What did they skip?

- **A.** Updating the system prompt to name the new embedding model so the LLM can adapt its queries
- **B.** Raising top-k to compensate for the new model's tighter clustering of similar passages
- **C.** Warming the cache, since new embedding models start with empty similarity lookup tables
- **D.** Re-embedding the entire index: query vectors from one model do not match chunks from another  ✅

> **Answer:** D

### Q19. A builder wants retrieval failures to announce themselves instead of hiding. Which pair of signals should the logging watch for?

- **A.** Similarity scores falling below threshold, and answers that cite no injected source at all  ✅
- **B.** Rising average response length, and users rephrasing their questions within a session
- **C.** Vector store disk usage growth, and embedding API latency crossing one second per call
- **D.** Token counts per window trending upward, and cost per conversation rising week over week

> **Answer:** A

### Q20. Retrieval feels off, and a builder opens the settings file to start adjusting chunk size, top-k, and thresholds by intuition. What should happen instead?

- **A.** Adjust one setting at a time by intuition, but keep notes so changes can be reversed later
- **B.** Build the test set first and measure, because tuning blind cannot tell better from worse  ✅
- **C.** Reset everything to framework defaults, which represent the tested baseline for most stacks
- **D.** Swap the embedding model first, since model quality dominates every parameter being tuned

> **Answer:** B

### Q21. A solo builder already running Postgres needs a vector store for a modest document set. Which reasoning fits this module's guidance?

- **A.** Choose a managed service regardless of stack, because self-hosted vector search cannot scale
- **B.** Build a custom similarity engine, since off-the-shelf stores hide too much of the pipeline
- **C.** Use pgvector in the existing database, adding a managed store only if scale demands it  ✅
- **D.** Skip the vector store and grep the documents, since small sets never need semantic search

> **Answer:** C

### Q22. After top-k gets cranked far higher to stop missed answers, the window now arrives at its limit every call and answers cite marginal passages. What is the corrective pattern?

- **A.** Keep the high k but double the window budget so marginal passages stop displacing good ones
- **B.** Retrieve wide but re-rank and inject only the best few, restoring precision within the budget  ✅
- **C.** Drop to k of one so only the single strongest passage ever reaches the model's window
- **D.** Alternate high and low k by request so precision and recall average out across traffic

> **Answer:** B

### Q23. Precise questions against a long report keep retrieving giant chunks that mention the topic but bury the detail. What is the likely root cause?

- **A.** Chunks are too large, so each one carries so much surrounding text that the signal is diluted  ✅
- **B.** Chunks are too small, so no single chunk contains enough context to satisfy precise queries
- **C.** The report was indexed twice, and duplicate chunks are crowding out the detailed passages
- **D.** The queries are too short for embedding math to work, and need padding with extra words

> **Answer:** A

### Q24. Queries containing exact product codes like SKU-4471 keep failing while natural language queries work fine. What does this reveal about the retrieval stack?

- **A.** The codes were stripped at indexing by a tokenizer setting that discards alphanumeric strings
- **B.** The vector store is case sensitive, and product codes are stored in a different case than queried
- **C.** The embedding model is undertrained on this industry and needs fine-tuning on the catalog
- **D.** Semantic similarity handles meaning, not exact identifiers; keyword search should complement it  ✅

> **Answer:** D

### Q25. One principle governs this module: chunking, metrics, re-ranking, and failure detection all serve it. Which statement is it?

- **A.** Retrieval should return as much as possible, because the model is the best judge of relevance
- **B.** Retrieval is an optimization detail; a strong enough model compensates for weak search
- **C.** Retrieval quality is the ceiling on answer quality; the model cannot cite what never arrived  ✅
- **D.** Retrieval is a solved problem; modern defaults make tuning and measurement unnecessary

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106578133_
