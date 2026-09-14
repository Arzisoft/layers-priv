---
type: transcript
lesson: "Your AI wrote Next.js Server Actions that query your database directly. But the"
course: "The Pit"
author: "Matt Murphy"
post_id: 106761869
published: "2026-09-03T14:00:06Z"
source_url: "https://the-faction.mn.co/posts/106761869"
duration: "2m09s"
words: 325
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your AI wrote Next.js Server Actions that query your database directly. But the

> Your AI wrote Next.js Server Actions that query your database directly. But the file also exports client components, so the build process analyzed the imports and shipped your database credentials to the browser. Your connection string is in View Source. Today I walk through using the server-only pa

Your AI put your database credentials in a Next. Js server action. So the build process shipped them to every user's browser. Your AI built your Next. Js, it wrote server functions that query your database directly, but it puts server logic and client components in the exact same file.

So Next. Js analyzed the imports, decided your server dependencies belonged on the client side, and included your database connection string in the code it delivers to your user's browser. So your production secrets are in Vue source right now. That's not a win. So let's fix it.

Step one, install the server only package and mark every sensitive file. This package creates a build error if any server code is accidentally included in what ships to the browser. So direct your AI to add the server only import to every file that touches your database, your API keys, or any of your credentials. If the build succeeds after adding it, your secrets are not exposed. That's a win.

Step two, separate server logic and client components into different files. A single file that exploits both server functions and browser facing components is a boundary your AI should have never crossed. So direct your AI to move every server function into dedicated files so that they share no exports with anything that renders in the browser and verify no server import chain reaches a client entry point. That's a win. And step three, scan your deployed code for leaked secrets.

Every JavaScript file your app delivers is totally public. So direct your AI to run a production build and search the output for your database host name, your API keys, your connection string, and every value in your environmental variables. Any match means that secrets are already visible to every user who opens developer tools on your site. So your server functions run on the server. Your credentials should also stay there.

That's the win.

---
_Source: https://the-faction.mn.co/posts/106761869_
