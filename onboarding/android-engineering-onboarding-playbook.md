
# Onboarding Guide

## Non-Technical

### Consulting vs Contracting

* Greenfield vs Brownfield
  * Greenfield software is the software that we design and develop from scratch. Brownfield software is one where something already exists and we have to add functionality and/or features to it.
  * Obvious mostly works in greenfield software development but we occasionally work with brownfield stuff too.

### Engineering Philosophy

* [First Principles](../first-principles-of-engineering.md)
* Documentation practices (ADR, project documentation etc.)

## Technical

* [Trunk Based Development \(TBD\)](../release-engineering/trunk-based-development/)
    * Use of feature flags for features that span over multiple PRs
    * Habit of raising PRs everyday
    * Prioritising review over writing new code (dropping everything to review a PR)
    * Show the Simple repo for daily branches, continuous integration and Github Actions for having checks in place

* [Code Reviews & Pull Requests](../release-engineering/code-reviews-and-pull-requests.md)
  * Read the [Google code review guide](https://google.github.io/eng-practices/review/reviewer/) and highlight some important practices that we follow as a team
  
* Estimation Practices
  * How engineers get estimations wrong?
  * Estimation based on complexity and not time

* Testing
  * [Testing pyramid](https://martinfowler.com/articles/practical-test-pyramid.html) 
     * Unit and Integration testing
     * Importance of testing
  * [Covariance and contra-variance in tests](https://www.javacodegeeks.com/2011/11/principles-for-creating-maintainable.html)
  * Testing codelabs for beginners: 
    * [Testing basics]( https://codelabs.developers.google.com/codelabs/advanced-android-kotlin-training-testing-basics/index.html#0)
    * [Test doubles and dependency injection](https://codelabs.developers.google.com/codelabs/advanced-android-kotlin-training-testing-test-doubles/index.html#0)
  * [Test doubles](https://obvious.in/blog/testing-production-code/): Fakes, mocks and Stubs 

### Mobius
* Functional Core and Imperative Shell 
  * [Pure functions](lessons/001-function-purity.md)
  * Imperative and functional programming basics
  * Boundaries Talk by Gary Bernhardt - [YouTube](https://www.youtube.com/watch?v=yTkzNHF6rMs) / [Original Website](https://www.destroyallsoftware.com/talks/boundaries)
    * Usage of Functional Core & Imperative Shell in above talk - [Video Link](https://www.destroyallsoftware.com/screencasts/catalog/functional-core-imperative-shell)

* Introduction to State Machines

* Introduction to [Mobius](https://github.com/spotify/mobius/wiki)
  * [Mobius onboarding](../onboarding/first-week-mobius.md)
    * Pairing activity using Counter example
    * Test-driven development
    * Introduce the login example
    * Pair on drawing the state diagram for login screen
    * Introduce `Effect` and `EffectHandler`
    * Introduce to Views and View Renderers
    * Introduce `Init` and wire Mobius loop
  * Individual Activity: Re-write the take-home exercise in Mobius
