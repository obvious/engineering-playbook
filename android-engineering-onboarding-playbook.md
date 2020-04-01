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

#### First Principles of Engineering

- We review code before we write code.
  - The code that has been written and is pending review is the one nearest to being able to generate value. It has already had all the efforts put into it being thought about and being written.
  - So we give priority to reviewing any pending PRs before we begin to write code for the day. Once that PR gets merged, the whole codebase starts benefitting from any value that it creates.
- A culture of searching, reading, and writing documentation.
  - Documentation is a very important part of software development and also something not a lot of people are habitual in writing or reading. If a product is documented properly moving around and understanding the codebase becomes really easy.
- Failure is learning what not to do.
- We measure so we can improve.
  - We have very well defined metrics which help us quantitatively calculate everyone’s progress. You can read more about it in [our Playbook](https://playbook.obvious.in/career-growth/engineering-growth-framework).
- Only improvements made at the constraints are of value.
  - This principle follows the [Theory Of Constraints](https://www.leanproduction.com/theory-of-constraints.html). Which as quoted in the article, "The Theory of Constraints is a methodology for identifying the most important limiting factor (i.e. constraint) that stands in the way of achieving a goal and then systematically improving that constraint until it is no longer the limiting factor."
  - Digging deeper into this, let’s say there is a vada making factory and Raj is the owner.
    - There are a few processes through which the raw material has to go through to produce the final product (Obviously).
    - Let’s say the processes are as follows: A (Farmer) -> B(Raw Storage) -> C(Dough Preparation) -> D(Vada Shaper) -> E(Fryer) -> F(Chutney Maker) -> G(Final Packaging).
    - Now, suddenly Raj notices that the vadas that are being produced in his factory is 10% less than the vadas he expected. Now, he needs to figure out what the problem is.
    - Let’s say that this problem is occuring because the Chutney maker is slower than expected. But, Raj or anyone in the factory is unaware about this.
    - Now, if, Raj asks the Farmer to produce more raw products. And asks everyone to be a little faster to be able to make better progress. There will still be a 10% lag in the expected result. Until, he realises that the Chutney maker is what is causing the problem.
    - And increasing the efficiency of any given process won’t actually increase the efficiency of the entire factory. It will just start to create more lag.
    - For example, the manager at E(Fryer) says that he can double his productivity. And can fry twice the number of vadas. The result of this will be, there will be more vadas than there is chutney for at F(Chutney Maker).
    - Which is why, understanding what is it that’s slowing the process is important. And, working hard on that constraint is what’s most important to increase efficiency.

#### Iteration Planning Meetings (IPMs)

Refer to [this](https://engineering.obvious.in/iteration-planning-meetings)

#### Stand-Ups

Refer to [this](https://engineering.obvious.in/daily-standup-meetings)

#### Product Requirements Document (PRD)

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
  - Pure functions
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
