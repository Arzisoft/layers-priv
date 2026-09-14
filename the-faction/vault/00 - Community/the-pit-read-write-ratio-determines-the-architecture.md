---
space: "The Pit"
author: "Matt Murphy"
post_id: 103947988
reactions: 0
comments: 0
published: "2026-06-30T12:11:58Z"
source: "https://the-faction.mn.co/posts/103947988"
---

# Read-write ratio determines the architecture.

Read-write ratio determines the architecture.

Schema change strategy determines survivability.

Ecosystem lock-in determines flexibility.

Choose the database by the workload.

Not the tutorial.

[#database](https://the-faction.mn.co/spaces/23777071/search?term=%23database) [#neon](https://the-faction.mn.co/spaces/23777071/search?term=%23neon) [#planetscale](https://the-faction.mn.co/spaces/23777071/search?term=%23planetscale) [#cloudflare](https://the-faction.mn.co/spaces/23777071/search?term=%23cloudflare) [#production](https://the-faction.mn.co/spaces/23777071/search?term=%23production)

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m49s_

You need to pick your next database platform. You came to the right spot. Here are three things you're gonna evaluate right now before you make that decision. Step one, your read write ratio. If your application is ninety percent reads, an edge database like Cloudflare d one gives you sub millisecond reads globally.

If your writes are heavy and concurrent, you likely need a platform designed for write throughput. So PlanetScale handles this with horizontal sharding. Neon handles it with auto scaling compute that adjusts for the load. Right? So maybe if you use d one at the edge for read heavy, PlanetScale or Neon behind the API for write heavy, this way the workload determines the architecture, not the brand you're using.

That's a win. Step two, schema change strategy under traffic. Your production database has active users. You need to add a column. PlanetScale and Neon both offer branching.

Copy production, test the change, merge safely, no downtime at all. However, Cloudflare d one handles migrations differently because the SQLite has different locking behavior at the edge. Ask how each platform handles schema changes under production traffic before you commit to anything. And step three, ecosystem commitment versus portability. Cloudflare d one is the most powerful inside the Cloudflare stack.

So workers, r two, k v, and queuing. Right? That ecosystem is compelling. It also is a big commitment. Neon and PlanetScale run standard Postgres and MySQL.

Far more portable, easier to migrate away from if that's what you're gonna do. Know whether you were choosing a database or choosing a platform. Both are valid decisions that you're definitely gonna have to make at some point, but they are not the same decision. So take your time with it.


---
_Source: https://the-faction.mn.co/posts/103947988_
