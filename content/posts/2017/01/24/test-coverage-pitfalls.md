---
title: "Test Coverage Pitfalls"
date: 2017-01-24T15:29:02+02:00
draft: false
params:
    author: Sebastian
---

When did I test enough?

While code coverage is a good indicator, you still have to know how code coverage works. Today I was hunting a bug in a Markdown importer I wrote for OpenFastTrace. The class where the bug sits had a whooping 93.1% code coverage and part of that missing coverage was owed to the fact that the JaCoCo coverage tracer can’t mark code that throws exceptions as covered – even though there is a test case for it.

So I wrote a new issue ticket, created a fix branch and wrote a three line test case that reproduced the problem. While the test now failed as expected, the code coverage didn’t go up.

I used the [Mockito](http://mockito.org/) mocking framework to verify that an interaction with a mocked observer happened or in my case due to the bug didn’t.

The error was hiding in a regular expression which read

    "Needs:\\s*(\\w+(?:,\\s*\\w+)+)"

instead of

    "Needs:\\s*(\\w+(?:,\\s*\\w+)*)"

Notice the asterisk in the end.

So while there are a lot test cases waiting to be written for this regular expression, code coverage won’t tell you.

You get what you measure, so be sure you understand what it is you are measuring.

