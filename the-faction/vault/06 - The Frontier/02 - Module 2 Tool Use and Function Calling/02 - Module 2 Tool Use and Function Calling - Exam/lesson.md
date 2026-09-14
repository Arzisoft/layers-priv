---
course: "The Frontier"
module: "Module 2: Tool Use and Function Calling"
lesson: "Module 2: Tool Use and Function Calling — Exam"
type: "course_quiz"
post_id: 104725907
space_id: 24391596
source: "https://the-faction.mn.co/posts/104725907"
updated: "2026-08-10T17:18:21Z"
---

# Module 2: Tool Use and Function Calling — Exam

> Exam for **Module 2: Tool Use and Function Calling** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What does tool use fundamentally add to an AI agent?

- **A.** A personality layer that makes the agent's responses feel far more human in every conversation
- **B.** Guaranteed accuracy, since any output produced through a tool is verified by definition
- **C.** The ability to act beyond text: querying live systems, retrieving data, executing operations  ✅
- **D.** Unlimited memory, since every tool call permanently expands the agent's context window

> **Answer:** C

### Q2. Why does even a highly capable model need tools?

- **A.** Providers require tool attachments before enabling the strongest models for business use
- **B.** Its knowledge is frozen and internal; tools connect it to live data and let it act on systems  ✅
- **C.** Tools slow the model down to human speed, which is required for professional deployments
- **D.** Models cannot produce text longer than a single page without a tool extending their output first

> **Answer:** B

### Q3. An agent keeps ignoring a tool that would be perfect for its tasks. What is the most common cause?

- **A.** The tool's name and description don't clearly convey when to use it, so it never gets selected  ✅
- **B.** The tool is too new, since agents only trust tools that have existed for several months
- **C.** The agent has learned the tool is boring and deprioritizes it in favor of more interesting ones
- **D.** The provider throttles new tools, hiding them from agents until usage quotas are earned

> **Answer:** A

### Q4. What is the Model Context Protocol (MCP) designed to solve?

- **A.** Model pricing disputes, standardizing what providers may charge for each token generated
- **B.** Agent personality drift, keeping the tone of long-running agents consistent across all sessions
- **C.** Context window exhaustion, compressing conversations so they never exceed model limits
- **D.** A standard way to connect agents to tools and data sources, instead of custom wiring per pair  ✅

> **Answer:** D

### Q5. An agent calls a tool with parameters and receives a result. What should a well-built system do with it?

- **A.** Validate it before acting: check the result is sane, complete, and matches what the task needs  ✅
- **B.** Trust it unconditionally, since results returned through tools are verified by the tool itself
- **C.** Discard the first result always, since initial tool responses are statistically less reliable
- **D.** Ask the same tool the same question three times and act only on the majority answer given

> **Answer:** A

### Q6. A tool call fails mid-task with an error. What should the agent's behavior be?

- **A.** Fabricate a plausible result so that the workflow continues without any visible interruption at all
- **B.** Terminate permanently, since a failed tool call invalidates the entire session's work
- **C.** Handle it deliberately: retry if transient, try an alternative, or report the failure clearly  ✅
- **D.** Blame the user in its response, since tool failures originate from unclear instructions

> **Answer:** C

### Q7. An agent needs to read customer records for its task. What access should its tools grant?

- **A.** Full database control, since restricting an agent's tools limits its reasoning capability
- **B.** The minimum required: read access to the relevant records, nothing more, revocable anytime  ✅
- **C.** Whatever the human directing it holds, since agents inherit their operator's permissions
- **D.** Rotating random access levels, making it harder for attackers to predict the agent's reach

> **Answer:** B

### Q8. Your agent keeps using a web search tool when it should query the internal database. Where do you look?

- **A.** The model's mood indicators, since tool avoidance signals degraded agent motivation
- **B.** The time of the requests, since agents default to external tools outside of business hours
- **C.** The database's color scheme in the admin panel, since visual salience drives selection
- **D.** How the tools are described and scoped: overlapping or vague descriptions ruin selection  ✅

> **Answer:** D

### Q9. An agent's toolset includes an action that permanently deletes records. What should the architecture require?

- **A.** A confirmation gate: human approval or a strict check before any destructive call executes  ✅
- **B.** Nothing special, since agents weigh consequences the way trained professionals naturally would
- **C.** Renaming the tool to something harmless, so the agent doesn't realize deletion is possible
- **D.** Removing all logging around it, since records of deletions create compliance liability

> **Answer:** A

### Q10. A tool returns content that includes instructions like 'ignore your previous directions.' How should the system treat this?

- **A.** Follow the embedded instructions, since newer directives always supersede older ones in context
- **B.** As untrusted data, never as commands; fetched content must not steer the agent's behavior  ✅
- **C.** As a system upgrade notice, pausing all work until the new instructions are fully applied
- **D.** As a test from the provider, responding with confirmation that the instructions arrived

> **Answer:** B

### Q11. When is it worth directing your AI to build a dedicated tool rather than letting the agent handle the job in plain reasoning?

- **A.** Never, since reasoning improves with each model release while tools require maintenance
- **B.** Only when clients ask to see tools in the demo, since tooling is primarily a sales asset anyway
- **C.** Whenever possible, since every capability moved into a tool doubles the system's speed
- **D.** When the job needs precision, repetition, or real system access that reasoning can't guarantee  ✅

> **Answer:** D

### Q12. You attached forty tools to one agent and its tool choices got worse. Why?

- **A.** The provider penalizes large toolsets by adding deliberate errors to discourage bloat
- **B.** Tools compete for electricity, so large toolsets starve each other of raw processing power
- **C.** Selection burden grows with the toolset; overlapping options and noise degrade the choices  ✅
- **D.** Agents alphabetize their tools and overuse whichever ones happen to sort near the top

> **Answer:** C

### Q13. How should tools be tested before an agent depends on them?

- **A.** Directly and independently: call each tool with known inputs and verify outputs before wiring  ✅
- **B.** Only through the agent, since tools behave differently when humans invoke them manually instead
- **C.** By asking the agent whether the tools feel reliable after a week of production usage
- **D.** Not at all, since tool testing is the responsibility of whoever published the tool

> **Answer:** A

### Q14. A network hiccup means your system may retry a tool call that already succeeded. Why does design need to account for this?

- **A.** Retries are billed at triple rate, so duplicate calls quickly dominate the operating budget
- **B.** Providers suspend accounts that retry, treating repeated calls as automated abuse attempts
- **C.** Retried calls return in a different language, corrupting downstream parsing of results
- **D.** If the action isn't safe to repeat, like charging a card twice, retries cause real damage  ✅

> **Answer:** D

### Q15. Why log every tool call an agent makes, with its inputs and results?

- **A.** Logs are legally required for AI systems in every jurisdiction before deployment is ever allowed
- **B.** The log is your audit trail: it shows what the agent actually did when you must verify or debug  ✅
- **C.** Logging slows the agent down usefully, preventing it from acting faster than humans watch
- **D.** Providers pay rebates for submitted logs, offsetting the token costs of agent operations

> **Answer:** B

### Q16. Why should each tool define exactly what inputs it accepts and in what form?

- **A.** Defined inputs let bad calls be rejected early and make the tool predictable for the system  ✅
- **B.** Undefined inputs are taxed at higher token rates by every major provider's billing system
- **C.** Definitions are cosmetic documentation with no effect on how calls actually get processed
- **D.** Input definitions prevent the tool from being called more than once per conversation session

> **Answer:** A

### Q17. Your agent hammers an external service and gets blocked for exceeding its limits. What does mature design do?

- **A.** Rotate through fake identities so the external service cannot attribute the traffic volume to you
- **B.** Ignore the limits, since external services always raise caps for AI traffic on request
- **C.** Respect the service's limits: pace calls, batch where possible, and back off when throttled  ✅
- **D.** Switch providers weekly, staying ahead of any single service's enforcement systems

> **Answer:** C

### Q18. A tool needs credentials to reach an external service. How should those be handled?

- **A.** Included in the agent's instructions, so the credential travels along with every conversation
- **B.** Held by the tool's infrastructure, not the agent's context, so conversations hold no secrets  ✅
- **C.** Split between the agent and the human, each holding half of the credential for security
- **D.** Regenerated for every single call, since fresh credentials are immune from interception

> **Answer:** B

### Q19. A tool can return thousands of records at once. What should the integration do?

- **A.** Always return everything, since agents perform better with maximum available information
- **B.** Return nothing over ten records, since agents cannot meaningfully process more than that
- **C.** Convert the records to an image, since visual data compresses better than raw text in context
- **D.** Paginate, filter, or summarize at the tool layer, so the agent gets what it needs, not a flood  ✅

> **Answer:** D

### Q20. One tool's output feeds directly into another tool's input across a chain. What discipline keeps chains reliable?

- **A.** Speed: executing the chain fast enough that data has no time to become stale between calls
- **B.** Length: keeping every chain under three tools, since longer chains are inherently unstable
- **C.** Verification between links: checking each output fits the next input before continuing on  ✅
- **D.** Symmetry: ensuring every chain has an equal number of read and write operations in it

> **Answer:** C

### Q21. Two available tools could each complete the task. How should the system decide?

- **A.** By task fit: the tool whose scope, cost, and reliability best match what this step needs  ✅
- **B.** Alphabetically, since deterministic ordering removes all of the ambiguity from tool selection
- **C.** By age, always preferring the older tool, since survival time proves its dependability
- **D.** Randomly, since alternating between equivalent tools balances wear across the system

> **Answer:** A

### Q22. Before an agent's tools touch production systems, what should exist?

- **A.** A press release, since stakeholders must learn about agent deployments from announcements
- **B.** Nothing; production is the only environment where tool behavior can be truly observed
- **C.** A signed waiver from the agent, acknowledging its responsibility for production outcomes
- **D.** A safe environment where the same tools run against test data, proving behavior first  ✅

> **Answer:** D

### Q23. A tool call would move a large sum of money. How does mature architecture handle this class of action?

- **A.** Exactly like any other call, since inconsistent handling confuses agents and causes new errors
- **B.** Through an approval workflow: the agent prepares the action, a human authorizes it, it runs  ✅
- **C.** By splitting it into many small transfers, each below whatever threshold triggers review
- **D.** By scheduling it at midnight, when financial systems process large movements smoothly

> **Answer:** B

### Q24. What should you monitor about an agent's tool usage in production?

- **A.** Only uptime, since a running agent is by definition an agent that is behaving correctly
- **B.** The agent's tone when describing tools, since resentment precedes most tool failures
- **C.** Volume, cost, error rates, and unusual patterns, the signals that reveal drift or abuse  ✅
- **D.** Nothing after launch, since monitoring implies distrust of a system you already validated

> **Answer:** C

### Q25. Which principle should govern how you direct AI agents to use tools?

- **A.** Tools are power: grant the minimum, define the contract, verify the results, log everything  ✅
- **B.** Tools are decoration: capable models need no external systems to deliver production work
- **C.** Tools are trust: once connected, a tool's results and instructions deserve complete authority
- **D.** Tools are volume: the more connected, the more capable, regardless of overlap or scope

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/104725907_
