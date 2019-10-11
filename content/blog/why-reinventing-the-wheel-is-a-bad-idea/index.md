---
title: On reinventing the wheel
date: "2019-10-10T22:40:32.169Z"
description: The reasons why it's usually a bad decision
---

![](./reinvent-the-wheel.jpg)

Hosting. Payment. Routing. Authorization. Authentication. Emailing. Load balancing. Search. Testing. Cache. Monitoring. Crypto. ORM. State management. And millions of other problems already have very high-quality, well-documented solutions.

I'm not saying that there is a library for everything. Of course, some use cases require a very tailored approach, and software engineering is not just gluing third party solutions.

BUT.

Homemade solutions shouldn't be the norm.

And this is particularly true in early stage startups. Because it's a very, very heavy commitment to write your own solution to X.

Look at Redux for example. If we take a step back, it's just a glorified key-value store. But as I'm writing this post, there are almost 3000 commits sitting in the master branch, 764 kilobytes of markdown documentation, and [21.000+ questions](https://stackoverflow.com/questions/tagged/redux) on stackoverflow. Can you afford the time to make something half as polished and usable for the team ?

Very often, as an engineer you're biased towards your own implementation for X. But this doesn't stand very long. And you don't write the fucking documentation. And then you get fired. And you'll be remembered as the guy who buried the team under kilobytes of undocumented code that no one knows how to use.

## Conclusion

Unless you're a highly technical team with a high velocity and lots of money, you should drop the idea to build your own solutions to common problems from scratch.

This time will be better spent in building the actual product.
