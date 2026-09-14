---
space: "The Pit"
author: "Nicholas Carmona"
post_id: 106080034
reactions: 2
comments: 2
published: "2026-08-17T16:35:27Z"
source: "https://the-faction.mn.co/posts/106080034"
---

# Hey everyone — I’d like to compare notes with teams running RAG systems in produ

Hey everyone — I’d like to compare notes with teams running RAG systems in production.

We’re working with a large, mixed-format corpus split across separate knowledge bases. The retrieval setup itself is fairly conventional: semantic search, keyword search, and query rewriting.

We’re trying to improve a few things:

- Retrieving the right supporting evidence
- Producing grounded answers with reliable citations
- Handling missing or conflicting information
- Identifying outdated sources
- Keeping latency and cost under control as the corpus grows

The area I’m most interested in right now is information freshness.

Ingestion time does not tell us when a source was published, last updated, or actually valid. That becomes a real problem when an older document and a newer document give conflicting guidance.

For anyone working on this in production, I’d love to hear how you approach the following:

Freshness and versioning

- How do you distinguish publication date, source modification date, and ingestion date?
- How do you represent multiple versions of the same document?
- Do you use canonical source IDs, version groups, supersession links, validity dates, or something else?
- Do you apply recency only when the query asks for the “latest” or “current” information? If so, how do you detect that intent?
- When two relevant sources conflict, how do you decide which one is authoritative?

Retrieval quality

- Which chunking, contextualization, metadata, hybrid retrieval, or parent-document strategies have produced measurable improvements?
- Has reranking improved quality enough to justify the additional latency and cost?
- What did you measure before and after adding it?

Evaluation

How do you evaluate retrieval separately from answer generation?

We’re looking at measures such as:

- Recall at K
- Context relevance
- Groundedness and faithfulness
- Citation accuracy
- Abstention accuracy
- Selection of the latest authoritative source

I’m also interested in how teams build and maintain evaluation cases for:

- Outdated documents
- Conflicting versions
- Hard negatives
- Questions with insufficient evidence

Observability and corpus health

- Which retrieval traces have been most useful: query rewrites, selected source IDs, ranking scores, fallback paths, source versions, latency, or final citations?
- How do you monitor ingestion failures, index drift, duplicate sources, removed documents, and stale versions?
- What added complexity or cost without producing a meaningful quality improvement?

Anonymized ranges and before-and-after evaluation results would be especially useful if you can share them.

I’m mainly looking for production evidence and honest tradeoffs—not vendor pitches.

---

## Discussion

**Matt Murphy** · 2026-08-17

> Bro, this is a really good post because you’ve moved past “how do I make RAG work?” and into how do I know the answer came from the right version of reality?
> 
> On freshness, I would not treat recency as simply another ranking weight. I’d treat it as source governance.
> 
> For every canonical document I’d want separate fields for:
> 
> published_at
> 
> effective_at
> 
> source_modified_at
> 
> ingested_at
> 
> canonical_source_id
> 
> version_id
> 
> supersedes_version_id
> 
> authority_level
> 
> valid_from / valid_to
> 
> status = current, superseded, withdrawn, draft, etc.
> 
> In other words, ingestion date tells me when my system learned about the document, not when the document became true.
> 
> Then I’d resolve authority before recency. A newer blog post shouldn’t outrank an older governing policy just because it was published yesterday. But two versions of the same authoritative policy absolutely should resolve toward the currently effective version unless the user explicitly asks a historical question.
> 
> Metadata filtering is increasingly part of the retrieval layer itself, and modern RAG stacks support using those fields to constrain retrieval before generation rather than hoping the model sorts it out afterward.
> 
> For retrieval, I’m still a fan of the boring answer: hybrid first, then prove whether reranking earns its keep**.** Semantic retrieval catches conceptual matches; keyword retrieval catches identifiers, policy numbers, product names, acronyms, and exact terminology. Azure’s current hybrid implementation, for example, runs text and vector retrieval together and combines them before optional semantic reranking.
> 
> I’d make reranking justify itself with evals. If it gives you a meaningful improvement in authoritative-source selection or Recall@K and the latency/cost trade is acceptable, keep it. If it gives you another 250 ms and a prettier demo without changing answer quality, kill it. AWS exposes reranking as a separate retrieval stage for exactly that reason, it doesn’t have to be permanently welded into the pipeline.
> 
> The piece I think matters most in what you wrote is evaluating retrieval independently from generation. I’d maintain a gold set where the expected output isn’t merely “the answer.” It includes the expected source/version:
> 
>  Did we retrieve the authoritative source?
> 
>  Did we avoid the superseded source?
> 
>  Was the correct version inside top K?
> 
>  Did we recognize conflicting evidence?
> 
>  Did we abstain when there wasn’t enough evidence?
> 
>  Did the final citation actually support the claim?
> 
> That separation between retrieval quality, groundedness, answer quality, latency, and cost is also how production RAG evaluation is being approached now.
> 
> And I would trace the hell out of it: original query, rewritten query, filters applied, candidate source IDs and versions, initial scores, reranker scores, final context, citations, latency at each stage, and cost. When somebody says “the RAG gave me the wrong answer,” you want to know whether retrieval failed, governance selected the wrong version, or generation ignored perfectly good evidence.
> 
> My rule would be: don’t let the LLM decide what is current if the data layer can know.
> 
> The model should reason over the evidence. Your system should determine which evidence is eligible to be considered in the first place.
> 
> This is the kind of RAG discussion I’d love to see more of in here. 👊😎

**Nicholas Carmona** · 2026-08-17

> [Matt Murphy](https://the-faction.mn.co/members/39706849) Matt, one important correction to my framing: this is not a system where different users receive different portions of one expert’s knowledge.
> 
> Each assistant represents one creator’s complete body of knowledge, and users of that assistant are supposed to benefit from the full corpus. Structured educational material, public content, group teaching, and conversational or case-based material all need to contribute to better answers.
> 
> So the hard problem is less about user-level access and more about applicability and epistemic scope.
> 
> A recommendation made during an individual consulting situation may contain a broadly useful principle, but it may also depend on that person’s specific business, offer, market, budget, or circumstances. Likewise, something said informally during a discussion may conflict with a structured course—or it may actually be a newer correction to that course.
> 
> How would you model and retrieve from that without either:
> 
> Throwing away valuable case-based knowledge, or
> Allowing one situational recommendation to become universal truth for every user?
> 
> Would you classify extracted knowledge as things like general teaching, conditional recommendation, case-specific advice, example, opinion, experiment, or explicit correction? Would you also capture the conditions under which a recommendation applies?
> 
> The second challenge is that the creator often cannot provide a clean authority map. The actual onboarding experience may simply be: “Here is everything I have.” The corpus is large, mixed-format, inconsistently dated, duplicated in places, and contains advice that evolved over time.
> 
> From reviewing our own situation, physical storage order is not the central issue. We have a sizable mixed-format corpus in an isolated knowledge base and use semantic and keyword retrieval with query reformulation. The more important gap is that source dates, effective dates, versions, applicability, and supersession relationships are sparse or inconsistent. Ingestion time only tells us when the system received something.
> 
> If the creator cannot initially identify what is canonical, what practical workflow would you use to bootstrap it?
> 
> Recover source and event dates with confidence levels?
> Detect duplicates and different representations of the same source?
> Cluster material by topic and recommendation?
> Extract claims with their surrounding conditions and original source passages?
> Detect contradictions and propose possible timelines?
> Infer whether something is formal teaching, a case study, an exception, or a later correction?
> Ask the creator to review only high-impact conflicts rather than manually classify everything?
> 
> What is the minimum useful human input? Would you start with their most important questions, show the sources and conflicting answers retrieved for each, and build the authority model from those decisions?
> 
> How do you handle useful material whose date or applicability remains unknown? Do you keep it available with lower confidence and contextual caveats, exclude it only from “current/latest” questions, or quarantine it until reviewed?
> 
> And how would you evaluate this when no clean gold set exists initially? Would you begin with a small expert-reviewed set that identifies the expected source, version, applicability conditions, and acceptable answer—then expand it from real retrieval failures?
> 
> I’d especially value what you’ve seen work in production: the automated pipeline, the creator-review burden, the metadata that actually mattered, the metrics you used, and the approaches that failed.


---
_Source: https://the-faction.mn.co/posts/106080034_
