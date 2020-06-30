# Mobius onboarding Guide

## **Mobius**

Mobius is our recommended architecture for building Android applications. We also feel that it is much easier to learn Test-Driven Development by starting out to build apps using Mobius.

### Day 1: Introduction to Mobius & TDD \(4:50 hours\)

* Theory: Introduction to Mobius _\(1 hour\)_
  * Eliminating the moving parts using functional programming
  * Pure functions
  * State transition diagrams
  * `Model` & `Event`
* Pairing Activity: The counter app state transition diagram _\(1 hour\)_
  * The `update()` function
  * Introducing the `UpdateSpec` class
  * Test driving the counter `update()` function
  * Wiring the `update()` function to the UI
* Theory: Test-Driven Development _\(30 minutes\)_
  * Principles of TDD
  * [YAGNI](https://martinfowler.com/bliki/Yagni.html) 
  * The red, green, and refactor cycle
  * TDD as a design practice
* Recap _\(20 minutes\)_
  * Key takeaways
  * Reading materials for the next day
    * [https://github.com/spotify/mobius/wiki/Concepts](https://github.com/spotify/mobius/wiki/Concepts)
    * [https://blog.cleancoder.com/uncle-bob/2016/03/19/GivingUpOnTDD.html](https://blog.cleancoder.com/uncle-bob/2016/03/19/GivingUpOnTDD.html) 

### Day 2: Mobius Effects & Effect Handlers \(5:05 hours\)

* Reflection of Day 1 and discussion around reading materials _\(30 minutes\)_
* Pairing Activity: Login Screen `update()` Exercise _\(2 hours\)_
  * Introducing effects & effect handlers
  * Login example state transition diagram
  * Test driving the login update\(\) function
  * Identifying the primitive obsession code smell \(Watch this\)
  * The “What to test?” problem
  * Relationship between the number of execution paths and tests
  * Test driving the `Username` and `Password` classes
  * Modeling async state transitions
  * Completing the `update()` function
* Pairing Activity: Materializing effects using effect handlers _\(1:30 hours\)_
  * State verification vs. behavior verification
  * Introduction to Mockito
  * Low confidence behavior verification tests
  * Writing the first effect handler
  * Using the RxJava `SubtypeEffectHandler`
  * `Action`, `Consumer`, and `ObservableTransformer`
  * Errors of first-class citizens
  * Using `Scheduler` in tests
* Pairing Activity: Introduction to Views and View Renderers _\(45 minutes\)_
  * Using mockito to verify view rendering logic
* Recap _\(20 minutes\)_
  * Key takeaways

### Day 3: Mobius, the final bits \(5:35 hours\)

* Reflection of Day 2 _\(30 minutes\)_
* Pairing Activity: Creating the shell _\(45 minutes\)_
  * Wiring all the Mobius components
  * Saving and restoring model state
  * The `@Parcelize` annotation
  * Caveats of saving data using Android’s `Parcelable` interface
* Pairing Activity: Subtle bugs introduced by async operations _\(45 minutes\)_
  * Handling normal flow of execution using the `init()` function
  * Handling edge cases using the `init()` function
  * Using the `InitSpec` for testing normal flow and edge cases
* Recap _\(20 minutes\)_

### Day 4, 5, and \(possibly 6\): Building the NASA APOD Apps \(14:50 - 22:50 hours\)

* Reflection of Day 3 _\(20 minutes\)_
* Individual Activity: NASA APOD Application _\(8 - 16 hours\)_
  * Step 1: Drawing the state transition diagram
  * Step 2: Writing the `init()`the `update()` tests
  * Step 3: Writing Effect Handler tests
  * Step 4: View and View Renderer Tests
  * Step 5: Wire up the imperative shell
* Code review and addressal _\(1:30 hours\)_
* Recap _\(1 hour\)_

### Points of Confusion

* `Effect` are more closer to intention for side-effect than performing a side-effect
* Representing decision making in state diagram

