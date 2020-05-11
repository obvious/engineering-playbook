# Onboarding Guide

## Non-Technical

### Consulting vs Contracting

* Greenfield vs Brownfield
  * Greenfield software is the software that we design and develop from scratch. Brownfield software is one where something already exists and we have to add functionality and/or features to it.
  * Obvious mostly works in greenfield software development but we occasionally work with brownfield stuff too.

### Engineering Philosophy

* [First Principles](../first-principles-of-engineering.md)
* [Iteration Planning Meetings](../meetings/iteration-planning-meetings.md)
* [Daily Standup Meetings](../meetings/daily-standup-meetings.md)
* [Product Requirements Document \(PRD\)](../project-management/product-requirements-document.md)

## Technical

* [Trunk Based Development \(TBD\)](../release-engineering/trunk-based-development.md)
* [Code Reviews & Pull Requests](../release-engineering/code-reviews-and-pull-requests.md)
* Estimation Practices
* Functional programming
  * [Pure functions](lessons/001-function-purity.md)
  * Comparing imperative programming with functional programming
  * Why use functional programming now?

    Writing our business logic using functional programming principles makes it easy for us to unit-test those parts of our code-base.

  * Functional Core and Imperative Shell
    * Boundaries Talk by Gary Bernhardt - [YouTube](https://www.youtube.com/watch?v=yTkzNHF6rMs) / [Original Website](https://www.destroyallsoftware.com/talks/boundaries)
    * Usage of Functional Core & Imperative Shell in above talk - [Video Link](https://www.destroyallsoftware.com/screencasts/catalog/functional-core-imperative-shell)
* Testing
  * Unit, Integration & End-to-End
  * Behavior + Property
* Test-Driven Development
  * Principles
  * YAGNI \(You Aren't Gonna Need It\)
  * The red, green and refactor cycle
* Introduction to State Machines
* Introduction to [Mobius](https://github.com/spotify/mobius)
  * [Mobius Wiki](https://github.com/spotify/mobius/wiki)
  * [First Week of Mobius](https://docs.google.com/document/d/1GHOqVAujkPKeKLh8m_teVFszqD8-UcexMwFqczAtaT0)
  * Examples
    * Counter
    * Login
    * Recreate your take-home assignment with Mobius

