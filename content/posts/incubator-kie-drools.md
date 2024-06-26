---
title: incubator-kie-drools
date: 2023-09-20T12:17:52+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1673235966910-f2a443bdbaaf?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTUxODMzMTR8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1673235966910-f2a443bdbaaf?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTUxODMzMTR8&ixlib=rb-4.0.3
---

# [apache/incubator-kie-drools](https://github.com/apache/incubator-kie-drools)

An open source rule engine, [DMN engine](https://drools.org/learn/dmn.html) and complex event processing (CEP) engine for Java™ and the JVM Platform.

Drools is a business rule management system with a forward-chaining and backward-chaining inference based rules engine, allowing fast and reliable evaluation of business rules and complex event processing. A rule engine is also a fundamental building block to create an expert system which, in artificial intelligence, is a computer system that emulates the decision-making ability of a human expert.

Be sure to check out the Drools' project [website](https://drools.org) and [documentation](https://drools.org/learn/documentation.html)!

Developing Drools and jBPM
==========================

**If you want to build or contribute to a kiegroup project, [read this document](https://github.com/kiegroup/droolsjbpm-build-bootstrap/blob/main/README.md).** 

**It will save you and us a lot of time by setting up your development environment correctly.**
It solves all known pitfalls that can disrupt your development.
It also describes all guidelines, tips and tricks.
If you want your pull requests (or patches) to be merged, please respect those guidelines.


Test execution tip
==================

Some test are meant to be executed on machine with _en_US_ locale.
A specific profile is provided to execute them on machines with different locale, namely `test-en`.
There are two ways to activate such profile during maven build:
1. `-Ptest-en` (profile-id based)
2. `-DTestEn` (property based)

The following two commands will execute tests on machine with locale different than _en_US_:

1. `make test -Ptest-en`
2. `make test -DTestEn`



