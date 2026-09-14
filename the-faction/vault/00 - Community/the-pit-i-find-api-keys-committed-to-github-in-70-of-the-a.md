---
space: "The Pit"
author: "Matt Murphy"
post_id: 105392798
reactions: 3
comments: 0
published: "2026-08-01T14:31:27Z"
source: "https://the-faction.mn.co/posts/105392798"
---

# I find API keys committed to GitHub in 70% of the apps I audit. Database credent

I find API keys committed to GitHub in 70% of the apps I audit. Database credentials. Stripe secrets. Service tokens. All public. Your AI put them there because it does not think about what happens when code goes public. Today I walk through how to move your secrets to environment variables, rotate every key that has ever been committed, and install a pre-commit hook that blocks it permanently.

**ORCHESTRATION PROMPT**

Direct your AI: "Perform a secrets audit on my codebase with three steps: (1) Scan every file in the repository for hardcoded strings that match API key patterns, tokens, passwords, database connection strings, and secret keys. List every match with file path and line number. (2) For each exposed secret, generate the replacement using environment variables, verify the .env file is listed in .gitignore, and confirm the secret is not present in any previous git commit using git log search. (3) Configure a pre-commit hook using a secrets detection tool that blocks any commit containing patterns matching API keys, tokens, or credentials. Test it by attempting to commit a dummy secret and confirming the push is rejected."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m31s_

Seven of my last ten audits had API keys committed to GitHub. Database credentials, secret Stripe keys, third party service tokens, all of them sitting in a public repository where anyone with a browser can find them. This is not a hypothetical. I saw this in seventy percent of the apps that we reviewed just last week. Your AI does not know the difference between a config file and an environmental variable.

Period. So it puts everything in the code and it pushes everything to that repo. Public, private, it's in there. And here are the three things you direct your AI to fix before someone finds your keys before you do. Number one, move every secret into environmental variables and verify nothing's hard coded.

Simple as that. Your AI knows how to use dot EMV files. It will never move your key on its own because it does not think about what happens when code goes public. So direct your AI to scan your entire code base for hard coded strings that match API key patterns and then move every one of them into environmental variables. Then verify your .env file is in your .gitignore file.

Because if it's not, you just moved your keys from one committed file to another committed file. That's not a win. Step two, rotate every key that has ever been committed. If your keys have been in a public repo for even more than an hour, assume they're compromised because they are. It does not matter that you deleted the file.

Git history is permanent and being crawled by bots nonstop. Anyone can pull a previous commit and see exactly what you removed. So direct your AI to generate new keys for every single service. Revoke the old ones and update your environmental variables. The old keys, they're burned.

Treat them exactly that way. And step three, install a pre commit hook that blocks secrets from ever being pushed out again. Your AI can configure tools that scan every commit pattern and what it looks like and stop API keys, tokens, and credentials and reject pushing out before it reaches the repo. This is a five minute setup that prevents the problem permanently. Without it, you're one careless commit away from doing this all over again.

We find this in seventy percent of the apps we audit. So do not let yours be the next one. Direct your AI to fix it today.


---
_Source: https://the-faction.mn.co/posts/105392798_
