---
space: "The Pit"
author: "Matt Murphy"
post_id: 106365555
reactions: 0
comments: 0
published: "2026-08-24T14:00:02Z"
source: "https://the-faction.mn.co/posts/106365555"
---

# AWS killed Bedrock Agents and renamed it to Classic. Closed to new customers. Ag

AWS killed Bedrock Agents and renamed it to Classic. Closed to new customers. AgentCore is the replacement with a completely different architecture. If you built on Bedrock for the healthcare BAA, your compliance path just changed. Today I walk through building an abstraction layer so vendor changes do not rewrite your application, auditing your BAA coverage after any service migration, and planning a migration runway before Classic becomes a liability. If you are on Bedrock Agents right now, this one is urgent.

**PROMPT:** Direct your AI: "Build a cloud provider migration readiness plan with three components: (1) Abstraction layer audit. Identify every point in my application where business logic directly calls a cloud provider's agent framework SDK. For each integration point, determine whether it is built behind an internal interface or hardwired to the vendor's API surface. For any direct integration, design a refactored architecture where the vendor SDK is wrapped behind an internal interface so the underlying framework can be replaced without changing application code. Estimate the engineering effort to refactor each integration. (2) BAA compliance verification. Map every service in my application stack that touches protected health information. For each service, verify that it is listed as a covered service under my current Business Associate Agreement. Flag any service that has been renamed, deprecated, or migrated to a new service name since the BAA was signed. For any flagged service, determine whether the BAA coverage transfers automatically or requires a new agreement. (3) Migration timeline. For the deprecated or end-of-life services identified, build a migration plan to the supported replacement. Define phases: discovery, refactoring, testing, cutover. Set milestones with dates. Identify the risk of staying on the deprecated service for 3, 6, and 12 months. Prioritize migration of services that touch regulated data."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m14s_

AWS just killed Bedrock Agents. Now everyone who built on it for the health care BAA has a migration path they did not plan for. And if you built your health care app on Bedrock Agents, your compliance path just got rerouted. So agent core is the replacement, but it's a different architecture, a different runtime, and different integration surface altogether. So your existing deployment does not migrate itself.

Here's how you're gonna handle it. Step one, an abstraction layer between your application and any cloud provider's agent framework. Your business logic should never be hardwired to a vendor's SDK. If your agent orchestration is built directly on Bedrock's API surface, every line of that code is now migration liability. So direct your AI to refactor your agent orchestration behind an internal interface.

That way the underlying framework can be swapped without rewriting your application. That's a win. Step two, a BAA audit on every service in your stack after any provider migration. So your BAA covers specific services by name. When the service changes, the BAA coverage may not follow it automatically.

So moving from Bedrock Agents Classic to Agent Core means you need to reverify that every service in your health care data path is covered under the current agreement. Direct your AI to map every service that touches PHI and verify the BAA coverage against the current AWS service list. That's a win. And step three, a migration runway, not a migration emergency. Classic is not shutting down tomorrow.

So it's also no longer receiving any of the new features, which means every month you stay on it, you fall a little further behind the platform providers actually investing in. So direct your AI to build a migration timeline that moves your agent orchestration to the supported framework. That way, before classic becomes a liability instead of a convenience, you're already ahead of it. This way, your cloud provider will always build the next thing, we hear it, but architect your system so the next thing doesn't break what you built.


---
_Source: https://the-faction.mn.co/posts/106365555_
