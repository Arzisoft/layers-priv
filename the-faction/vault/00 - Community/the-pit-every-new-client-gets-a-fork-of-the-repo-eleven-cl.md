---
space: "The Pit"
author: "Matt Murphy"
post_id: 106195089
reactions: 1
comments: 0
published: "2026-08-20T14:00:11Z"
source: "https://the-faction.mn.co/posts/106195089"
---

# Every new client gets a fork of the repo. Eleven clients means eleven branches a

Every new client gets a fork of the repo. Eleven clients means eleven branches and one developer who cannot remember which client runs which version. Today I walk through tenant-scoped feature flags, configuration inheritance with per-tenant overrides, and tenant-aware routing middleware that resolves the tenant before any business logic runs. If you are building a SaaS product for multiple clients, this is how you stay on one codebase.

**PROMPT:** Direct your AI: "Build a multi-tenant feature management system with three components: (1) Tenant-scoped feature flags. Implement a feature flag system where every flag can be evaluated per tenant. Create a flag store with entries structured as feature key, default value, and a tenant overrides map. When the application evaluates a flag, it checks for a tenant-specific override first and falls back to the default. Build an admin interface or configuration file where flags can be toggled per tenant without code changes. (2) Configuration inheritance. Build a layered configuration system with a base configuration that all tenants inherit by default. Allow per-tenant configuration overrides that merge with the base at runtime. When the base configuration is updated, all tenants receive the update unless they have an explicit override for that key. Store overrides separately from the base so the base can be versioned independently. (3) Tenant resolution middleware. Implement middleware that runs before any business logic on every request. It should extract tenant identity from the request context: subdomain, custom header, JWT claim, or API key lookup. Inject the resolved tenant context into the request so all downstream services can access tenant ID, configuration, and feature flags without additional lookups. Reject requests that cannot be resolved to a valid tenant."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m30s_

Every time a new client signs up for your multitenant system, you fork the entire repository. New branch, new deployment, new set of environmental variables. Client number four wanted dashboard in dark mode. Client number seven wanted to export CSVs instead of PDFs. And client number eleven wants to skip onboarding entirely.

So your AI copied the code base and started customizing. But now you have eleven versions of your product and you cannot remember which client runs which branch. So that's no longer a product, that's actually eleven products wearing the exact same name. Here's how you're going to direct your AI to serve all of those clients without forking your product for each and every one. Step one, feature flags scoped per tenant.

A feature flag is not a global on off switch. It's a per tenant configuration. Client number seven gets those CSV exports, client four gets dark mode, and everyone else gets the default. One code base evaluates the tenant context and renders the right experience. So direct your AI to implement tenant scoped feature flags where every configurable behavior is controlled by tenant ID, not by code branches.

That's a win. Step two, tenant configuration inheritance with override layers. So start with a base configuration every tenant shares. Layer tenant specific overrides on top of that. Client eleven overrides the onboarding flow.

Everyone else inherits the default. So when you update the base, every tenant gets the update unless they have an explicit override. So direct your AI to build a configuration system with base default and per tenant overrides that merge at runtime. That's a win. And step three, tenant aware routing at the application boundary.

The application must know which tenant is making the request before it touches any logic. Subdomain, header, JotClaim, that identity drives which configuration loads, which features will activate, which branding will render. So direct your AI to implement tenant resolution middleware that identifies the tenant on every single request. And then it injects the tenant context before any business logic executes. One code base, eleven clients, zero forks.

So DirectoryAI to build it that way from day one.


---
_Source: https://the-faction.mn.co/posts/106195089_
