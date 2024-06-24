---
title: "Improving Test Coverage in log Message"
date: 2018-07-14T20:15:00+02:00
draft: false
params:
    author: Sebastian
---

Log message test coverage for the `java.util.logging.Logger` depends on the log level by default. As an optimization the lambda functions that constitute log messages are only executed if the configured log level is higher or equal the log message level.

In effect this means that for optimum test coverage you would have to set the log level to `FINEST` for your unit tests. But that will spam your console or log files.

Thankfully the designers thought of that issue and provided a means to use multiple log consumers in parallel. Christoph created a `NoOpLoggingHandler` and added it to the list of log consumers in the [`logging.properties`](https://github.com/itsallcode/openfasttrace/blob/develop/src/test/resources/logging.properties) of the JUnit tests.

This makes sure all lambdas are called and we get maximum test coverage.

If you want to learn more check out the documentation of the [`LogManager`](https://docs.oracle.com/javase/8/docs/api/java/util/logging/LogManager.html) class.