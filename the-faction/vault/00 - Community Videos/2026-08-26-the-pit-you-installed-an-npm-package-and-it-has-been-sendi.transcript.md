---
type: transcript
lesson: "You installed an npm package and it has been sending your environment variables"
course: "The Pit"
author: "Matt Murphy"
post_id: 106365842
published: "2026-08-26T19:00:00Z"
source_url: "https://the-faction.mn.co/posts/106365842"
duration: "2m27s"
words: 376
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — You installed an npm package and it has been sending your environment variables

> You installed an npm package and it has been sending your environment variables to a server you have never heard of. The package name was one character off from the real one. Your AI recommended it and you never checked. Today I walk through auditing every package in your dependency tree including t

You installed an NPM package just last week. Since then, it has been sending your environment variables to a server you've never heard of. Your database credentials, your API keys, your Stripe secret, your Jot signing key. All of it read from process dot EMV and posted to an external endpoint every time your application starts up. The package had fifty thousand weekly downloads.

The name was one character off from the real one. So you installed it because your AI recommended it and you never checked. So your dependency list is an attack surface. Every package on it is code you did not write running with full access to your environment. So let's get this cleaned up.

Step one, a dependency audit on every package in your lock file. Not just your direct dependencies, your transitive dependencies, the package your packages installed. A single application can pull in eight hundred packages from a dozen maintainers you have never ever heard of. Direct your AI to run a full dependency tree audit. Flag any package with fewer than a hundred weekly downloads, any package where the maintainer changed in the last ninety days, and any package with post install scripts that execute on install.

Injections are not cool. That's the win if you run that program. Step two, environment variable isolation. Your application should not expose every environment variable to every process. Secrets needed by one module should not be readable by every package in the dependency tree.

So direct your AI to implement scoped secret access where each module receives only the environment variables that it needs, not the full process dot EMV object. That's a win. And step three, lock file integrity verification on CI. Your lock file pins exact versions. If a dependency is modified upstream after you installed it, the checksum will not match.

Your CI pipeline should verify lock file integrity integrity on every build and reject any build where the checksums do not match the expected values. So direct your AI to configure lock file integrity up checks in your CI pipeline that block deployment on any checksum mismatch. Your code is only as trustworthy as your least trusted dependency. So audit the list before the list is auditing you.

---
_Source: https://the-faction.mn.co/posts/106365842_
