---
title: Should I use Expo for my mobile app ?
date: "2021-09-19T21:38:32.169Z"
description: Expo? Or React Native? Or Flutter ? Or Java ? Or Kotlin ? Or Swift ? Oh my...
---

Let's go back in 2009 for a few seconds and list a few things that happened during this year :

- Uber is founded (Today's value : \$74 billions)
- Airbnb joined Y Combinator (Today's value: \$104 billions) ,
- The Bitcoin blockchain came to life (Today's value: \$760 billions)
- Apple launched the iPhone 3GS (Today's value: 2.4 trillions)

Do these facts show that I should have invested my money better back in the days ? Yes. I know that.

**What I want to highlight is that it's the beginning of the "There's an app for that" tsunami, a business trend that all the startup founders will want to surf from now on :**

<iframe width="560" height="315" src="https://www.youtube.com/embed/szrsfeyLzyg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

But this trend brought a new set of problems to software teams : portability.

Writing a program once is a tough and expensive exercise. Writing it twice for both Android and iOS is as bad as it sounds.

That's why solutions like React Native and Expo exist today.

## Should I use Expo for my mobile app ?

Well... the hard truth is that nobody can give you a perfect answer because _it depends on the project_. There are a few general things to consider though :

Expo, like all the solutions aiming to transform a hard problem into a more simple one, will save you time at the beginning, at the price of making you loose time later on, when the hard problem [starts leaking](https://www.joelonsoftware.com/2002/11/11/the-law-of-leaky-abstractions/). This is exactly why all the web agencies love to work with these. They can surf on the upside (fast time-to-hello-world), and they are not around to pay for the downside (slow updates due to bloated software).

React Native is not an exception to the rule. But it's one abstraction level below so you will carry on less bloat downstreamm, in exchange of more efforts at the beginning.

Native development is the lowest level possible, it's as lean as you can get, but you will need a lot more a craftmanship and initial investment to ship something meaningful.

My opinion is that cross platform development is a big challenge. Even solid teams are forced to back off and throw away years of work (See stories of [Airbnb](https://medium.com/airbnb-engineering/sunsetting-react-native-1868ba28e30a), [Dashlane](https://www.dashlane.com/en/marketing/introducing-web-first), [Udacity](https://engineering.udacity.com/react-native-a-retrospective-from-the-mobile-engineering-team-at-udacity-89975d6a8102)). So the first thing is to ask yourself : is it vital for the project to have mobile apps ?

If it is vital, my preference would be to use Expo, ship a prototype, learn as much as possible, and keep in mind that this shortcut will have to be paid **in full** later.
