---
title: Nobody cares about what works on your machine
date: "2019-10-10T22:40:32.169Z"
description: Everybody cares about what works in production
---

![](./works-on-my-machine.jpg "Then I'll guess we'll ship your machine.")

I remember this time where I was programming an Angular client. One of the API route kept crashing. When I asked the developer in charge of the endpoint about it, he didn't take it as a bug because the route was working in his local Postman workspace. As it turned out, he was testing the wrong thing, and there was actually a bug.

I didn't expect him to write bug-free code. I expected him to be humble and to put himself in my shoes. Making a bug report takes a significant amount of time and doesn't deserve a defensive attitude.

When someone uses something you made, if they don't get the output they are expecting, you fucked up somewhere. You misjudged the real need. You didn't cover all the edge cases. You didn't communicate well enough on the possible usage.

Worse, when this user is a developer on your team, the lack of correctness and usability of your work will definitely slow them down. It's damageable for the overall trust and productivity.

Mission is not complete until your code is in production AND all the stakeholders are aware of it and happy with it. Don't expect other people to make it land there for you.
