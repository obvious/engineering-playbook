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

### Trunk Based Development

- `master` branch should always be stable and daily branches should be used
- Small PRs
- Allows for continuous deployment
- Rebases instead of merging
- Code reviews & Pull Requests

Refer to these links

- [Obvious Doc](https://engineering.obvious.in/release-engineering/trunk-based-development)
- [Popular website](https://trunkbaseddevelopment.com/)

## Technical

- Introduction to functional programming
  - Comparing imperative programming with functional programming
  - Why use functional programming now
  - [Pure functions](https://engineering.obvious.in/learning/lessons/001-function-purity)
    - Introduction
      - No matter how many times the function is called using the same input parameters the output will always remain the same
      - `Input` -> `Function` -> `Output`
    - Advantages
      - Pure functions are small, precise, simple, safe and straight-forward to reuse.
      - A pure function guarantees that they will not modify anything outside their body.
      - You can use them with confidence because you know that they take input and give output.
      - They do not surprise you.
    - Example
      - If there is a function which returns the addition of 2 numbers, no matter how many times you send in the same 2 numbers the output will remain always the same.
  - Functional Core and Imperative Shell
- Introduction to State Machines
- Introduction to [Mobius](https://github.com/spotify/mobius)
  - [Mobius Wiki](https://github.com/spotify/mobius)
  - Concepts
    - MobiusLoop
    - Model
    - Event
    - Effect
    - Update
    - EffectHandler
    - EventSource
  - TDD with Mobius
    - Principles
    - YAGNI (You Aren't Gonna Need It)
    - The red, green and refactor cycle
  - Examples
    - Counter
    - Login
