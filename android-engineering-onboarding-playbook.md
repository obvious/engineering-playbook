# Android Engineering Onboarding Playbook

## Non-Technical

### History of Obvious

- 7 High Street
- Edward House
- Primrose Road
- Residency Road

### Consulting vs Contracting

- Greenfield vs Brownfield
  - Greenfield software is the software that we design and develop from scratch. Brownfield software is one where something already exists and we have to add functionality and/or features to it.
  - Obvious mostly works in greenfield software development but we occasionally work with brownfield stuff too.

### Engineering Philosophy

- [First Principles of Engineering](first-principles-of-engineering.md)
- [Iteration Planning Meetings](iteration-planning-meetings.md)
- [Daily Standup Meetings](daily-standup-meetings.md)
- [Product Requirements Document (PRD)](product-requirements-document.md)

## Technical

- Trunk Based Development (TBD)
  - `master` branch should always be stable and daily branches should be used
  - Small PRs
  - Allows for continuous deployment
  - `rebase` instead of `merge`
  - Refer these
    - [Obvious Doc](release-engineering/trunk-based-development.md)
    - [Popular website](https://trunkbaseddevelopment.com/)
- [Code Reviews & Pull Requests](release-engineering/code-reviews-and-pull-requests.md)
- Estimation Practices
- Functional programming
  - [Pure functions](learning/lessons/001-function-purity.md)
  - Comparing imperative programming with functional programming
  - Why use functional programming now
  - Functional Core and Imperative Shell
- Testing
  - Unit, Integration & End-to-End
  - Behavior + Property
- Test-Driven Development
  - Principles
  - YAGNI (You Aren't Gonna Need It)
  - The red, green and refactor cycle
- Introduction to State Machines
- Introduction to [Mobius](https://github.com/spotify/mobius)
  - [Mobius Wiki](https://github.com/spotify/mobius/wiki)
  - Concepts
    - Mobius-Loop
    - Model
    - Event
    - Effect
    - Update
    - EffectHandler
    - EventSource
  - Examples
    - Counter
    - Login
