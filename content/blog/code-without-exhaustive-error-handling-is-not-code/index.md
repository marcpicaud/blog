---
title: Code without exhaustive error handling and tests is not code
date: "2019-11-10T22:40:32.169Z"
description: An opinionated set of rules to apply in order to not fuck up your codebase.
---

Lack of control over errors and exceptions is one of the main reasons for which a software product feels very low-quality to the end user and not enjoyable for the team.

![](./error-handling.jpg)

It's very common when you're a young developer to only focus on the happy path of the thing you're trying to implement. It's one of the root cause of the infamous "But it works on my machine" excuse.

I guess the lesson to learn here is to not rush into the implementation of thing you're trying to build. I've been there, I know it's exciting, I know you're smart, but keep in mind that programming is a very humbling discipline. When you rush something, the mental representation you have of the problem isn't derived from the reality of the problem.

Keep in mind that in software engineering, more often than not, fast is slow.

When you shape your local setup so that the code always takes the happy path, future instability is introduced. It's like being an overprotective parent in a sense. And as soon as your code hits QA (or worse: production), the outside world becomes hostile and fucks with your baby, and you pay for the lack of preparation for edge case scenarios.

During development, you should definitely shoot your code in the face and see how many bullets it can take. Well, that's where the parent/child analogy ends I guess.

Below is a bunch of low-hanging fruits when it comes to error management.

## Don't take your assumptions for granted

Database connection might be lost. A file might not exist. User defined inputs can be invalid or malicious. Your database query might not return an actual result. A variable might be undefined. Some function call might throw. Promises can be rejected.

```js
// Missing promise rejection handling. Bad programmer 💩
app.get('/path/to/something', async (req, res) => {
	const answer = await foo.myMethodThatThrowsOrRejects();
	res.json(answer); // <-- Never reached + unhandled promise rejection.
}

// Error are handled. Good programmer 🦄
app.get('/path/to/something', async (req, res) => {
	try {
		const answer = await foo.myMethodThatThrowsOrRejects();
		res.json(answer);
	} catch (e) {
		res.status(500).end();
	}
}
```

Internet connectivity can be lost. Http requests might not return 2XX responses. Http responses might not arrive in the same order.

## Rely on the protocols and language constructs to handle the errors

In high-level programming languages and protocols, errors (in the broad sense) are first-class citizens:

- HTTP status codes
- TCP error codes
- Exceptions
- Errors
- Promise rejections
- OS process exit statuses
- ...

If your project relies on in-house structures and/or boolean flags to pass errors, it means you're reinventing the wheel. Worse, it also a signal that you don't know how to get the best out of your stack.

Doing this is longer to implement and harder to maintain. It paves the way for instability and pointless complexity.

Don't add your personal secret sauce to the many existing ways to handle and notify others about errors.

Here's one exemple of "good VS bad" error handling with a JavaScript function:

```js
// Bad 💩
// The function will be resolved with an object abstracting an Error
// It's contradictory and confusing for the caller
async function doSomething(foo) {
  const ok = await myConditionsToDoSomething(foo)

  if (!ok) {
    return { success: false }
  }
  // ...
}

// Good. doSomething will be rejected with a standard error.
async function doSomething(foo) {
  const ok = await myConditions(foo)

  if (!ok) {
    throw new Error("Something went wrong")
  }
  // ...
}
```

Here's another exemple of "good VS bad" HTTP response design.

```http
// Bad 💩There's a contradiction between the HTTP status and the payload
HTTP/1.1 200 OK
Date: Sun, 18 Oct 2009 08:56:53 GMT
Content-Length: 40
Content-Type: application/json

{ success: false, message: 'Forbidden' }

// Good 🦄 The HTTP status is enough to carry the information
HTTP/1.1 403 Forbidden
Date: Sun, 18 Oct 2009 08:56:53 GMT
Content-Length: 0
```

## You don't know what you don't know

You also need to keep track of errors. You need to know when an exception is thrown, when a process crashes, when a TCP connection is lost, when the server returns HTTP 500 errors.

So, the team should, somehow, be notified by runtime errors. Be it an email, a slack message, Sentry, whatever. But it should be in a firefighter mindset, and analyse errors as they happen.

One persone per error is sufficient. If the whole team start working on the same error each times a notification pops up, it's not very efficient. Elect one firefighter and rotate periodically.

## Writing tests is not an option

![](./test.jpeg)

## Conclusion

Don't reinvent the wheel.

Consider the edge cases.

Don't hide the errors by making them silent.

Love them and treat them as part of the process.

They're here to help you build a better product.
