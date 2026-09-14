---
type: transcript
lesson: "If your AI agent fetches URLs based on user input, you have a problem most peopl"
course: "The Pit"
author: "Matt Murphy"
post_id: 106365668
published: "2026-08-25T19:00:01Z"
source_url: "https://the-faction.mn.co/posts/106365668"
duration: "2m11s"
words: 344
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — If your AI agent fetches URLs based on user input, you have a problem most peopl

> If your AI agent fetches URLs based on user input, you have a problem most people never think about. An attacker gives your agent a URL pointing to your cloud credential service. Your agent, running inside your network, happily fetches it and hands back the response. From the outside, through your o

Your AI agent fetches URLs from user inputs. So a hacker just used it to map every service running inside your network. Your AI agent has the same network access that your server has. It can see internal databases, admin panels, and cloud credentials. So when a user gives it a URL to fetch, your agent does not ask whether that URL belongs to you or to someone trying to rob you.

It fetches it from inside your perimeter and it hands the response back. So an attacker just used your own infrastructure to bypass your own firewall. Let's get ahead of it. Step one, your agent needs a boundary. Right now, it'll fetch anything from anywhere.

Internal services, cloud credential endpoints, admin dashboards. It does not know the difference between a legitimate request and an attack. So direct your AI to restrict all outbound fetches to an approved list of external domains. And block any requests targeting your internal network altogether. That's a win.

Step two, a single validation check. That is not enough. Attackers use techniques that pass your domain check on the first look and redirect to an internal target on the actual fetch. So your agent validates the front door and walks right through the back. So direct your AI to pin every URL to a single resolved address and revalidate on every redirect.

This is so the destination cannot change between the check and the fetch. That's a win. And step three, your error messages are giving away the map. Every failed fetch returns a different error. Connection refused means a host exists.

Time out means a service is listening. So an attacker reads those differences and builds a blueprint of your internal network without ever touching it directly. So direct your AI to return one generic error for all failed fetches and log the details where only your team can see them. So your AI agent has the keys to every room in your building. Right?

Make sure strangers cannot tell which doors they open. That's the win.

---
_Source: https://the-faction.mn.co/posts/106365668_
