---
space: "The Pit"
author: "Matt Murphy"
post_id: 106365842
reactions: 4
comments: 1
published: "2026-08-26T19:00:00Z"
source: "https://the-faction.mn.co/posts/106365842"
---

# You installed an npm package and it has been sending your environment variables

You installed an npm package and it has been sending your environment variables to a server you have never heard of. The package name was one character off from the real one. Your AI recommended it and you never checked. Today I walk through auditing every package in your dependency tree including transitive dependencies, isolating environment variables so packages only access the secrets they need, and verifying lockfile integrity in CI so modified upstream packages get caught before deployment. If you have never audited your dependency tree, start today.

**PROMPT:** Direct your AI: "Perform a supply chain security audit on my application with three components: (1) Dependency tree audit. Analyze my complete dependency tree including all transitive dependencies. For each package, report: weekly download count, maintainer history (flag any maintainer change in the last 90 days), presence of postinstall or preinstall scripts, last publish date, and total number of dependencies it pulls in. Flag any package with fewer than 100 weekly downloads as a trust risk. Flag any package with install scripts that execute arbitrary code. Identify any package name that is within one or two characters of a popular package name, indicating potential typosquatting. (2) Environment variable scoping. Audit how environment variables are accessed across my application. Identify every module, package, or service that reads from process.env. Determine which environment variables each module actually needs versus which it has access to. Design a scoped configuration system where each module receives only its required variables through dependency injection or a configuration service, rather than having unrestricted access to the full environment. (3) Lockfile integrity. Configure my CI pipeline to verify lockfile checksums on every build. The pipeline should compare the integrity hashes in the lockfile against the actual downloaded packages. If any checksum does not match, the build should fail and alert. Add a step that compares the current lockfile against the previous committed version and reports any added, removed, or changed packages for review before merge."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m27s_

You installed an NPM package just last week. Since then, it has been sending your environment variables to a server you've never heard of. Your database credentials, your API keys, your Stripe secret, your Jot signing key. All of it read from process dot EMV and posted to an external endpoint every time your application starts up. The package had fifty thousand weekly downloads.

The name was one character off from the real one. So you installed it because your AI recommended it and you never checked. So your dependency list is an attack surface. Every package on it is code you did not write running with full access to your environment. So let's get this cleaned up.

Step one, a dependency audit on every package in your lock file. Not just your direct dependencies, your transitive dependencies, the package your packages installed. A single application can pull in eight hundred packages from a dozen maintainers you have never ever heard of. Direct your AI to run a full dependency tree audit. Flag any package with fewer than a hundred weekly downloads, any package where the maintainer changed in the last ninety days, and any package with post install scripts that execute on install.

Injections are not cool. That's the win if you run that program. Step two, environment variable isolation. Your application should not expose every environment variable to every process. Secrets needed by one module should not be readable by every package in the dependency tree.

So direct your AI to implement scoped secret access where each module receives only the environment variables that it needs, not the full process dot EMV object. That's a win. And step three, lock file integrity verification on CI. Your lock file pins exact versions. If a dependency is modified upstream after you installed it, the checksum will not match.

Your CI pipeline should verify lock file integrity integrity on every build and reject any build where the checksums do not match the expected values. So direct your AI to configure lock file integrity up checks in your CI pipeline that block deployment on any checksum mismatch. Your code is only as trustworthy as your least trusted dependency. So audit the list before the list is auditing you.


---

## Discussion

**Ameen Badri** · 2026-08-27

> this is very important to do today .


---
_Source: https://the-faction.mn.co/posts/106365842_
