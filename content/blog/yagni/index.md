---
title: You ain't gonna need it
date: "2019-10-10T22:40:32.169Z"
description: Your solution is no one's problem
---

![](./yagni.jpg '"But I like to code!"')

Solving a problem you don't really have currently exposes the codebase to many risks:

1. **Dead code** : Well, big surprise ! You're not solving an actual problem, so nobody uses the solution.
2. **Over engineering** : This is a very common trait amongst software engineers. We want "web scale" solutions for every problems. But not all of them require cutting-edge tech. It's a very costly and toxic behavior to push the team towards complicated solutions every single time. Get the right tool for the right job, man.
3. **Garbage that needs to be re-done (most common)** : If you ended-up in the trap, usually it comes from good intentions. You probably smelled something was coming. But as you may know, the road to hell is paved by good intentions. The issue is not that you foresee something, it's that you took it for granted, made asumptions about it (because you're so smart, right) and spent time coding on it. You probably don't have all the context to provide the best solution. So in the end, you can be sure that it will be re-written.

A few exemples of these kind of fake problems :

- You want to implement a NoSQL database because you're afraid of the JOIN performance, but you have 30 users.
- You're architecting a multi-cloud deployment system to ensure highest availability, but you have 30 users.
- You optimizes a function so that it runs in a few milliseconds less.
- You buy a 400\$ smart watch the day after you sign up for the gym
