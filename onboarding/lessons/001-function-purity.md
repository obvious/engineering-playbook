# 001 - Function Purity

In this lesson, we will explore the following topics:

* What is a pure function?
* Why are they important?
* Some common examples of impure functions, and how to make them pure.

The code snippets in this topic have been written for the Java Virtual Machine, using the [Kotlin](https://kotlinlang.org/) programming language. The concepts, however, apply across all programming languages and platforms in general.

## What is a pure function?

A pure function has the following characteristics:

### Pure functions are idempotent

An idempotent function is one that has the same result for the same input, no matter how many times it is called. Consider the following function:

```kotlin
fun add(a: Int, b: Int): Int {
  return a + b
}
```

Regardless of whether `add()` is invoked one time, ten times, or a million times with a given value for `a` and `b`, the result of `add()` will never change. However, consider the following function:

```kotlin
var sum = 0

fun add(b: Int): Int {
  sum = sum + b
  return sum
}
```

In this case, `add()` is no longer an idempotent function. Every time it is invoked, it changes the value of the `sum` variable and returns it. Invoking it with the same value of `b` multiple times will return a different result each time.

Another example of a function which is not idempotent is one which depends on values which can change. One example is the following:

```kotlin
fun addDaysToCurrentDate(days: Int): Date {
  val now = Date()
  now.time = now.time + days * MILLIS_IN_DAY

  return now
}
```

The `Date` constructor here implicitly uses the current system time at the millisecond precision for getting the current date. If we invoke this function multiple times with the same input value for `days`, the returned `Date` instance will still be different every millisecond.

There are certain ways a function may seem idempotent, but in reality it is not. For example, consider the following function:

```kotlin
fun addDaysToDate(date: Date, days: Int): Date {
  val now = Date(date.time + days * MILLIS_IN_DAY)

  return now
}
```

On the surface, this might seem to be an idempotent function since it does not use the system time for generating the date. However, someone who has used the `Date` class before might be aware that the actual time of the `Date` can be changed via the `setTime(Long)` method.

This makes the input that is being passed to the `addDaysToDate` function mutable. This will generally be a problem in multi-threaded environments if the `date` instance being passed to the `addDaysToDate` method is modified from another thread while the `addDaysToDate` method is executing.

This is a problem with shared mutable state in general, which we will talk about in another [lesson](001-function-purity.md).

So if we needed to make this function actually idempotent, we could do something like this:

```kotlin
fun addDaysToDate(dateMillis: Long, days: Int): Date {
  val now = Date(dateMillis + days * MILLIS_IN_DAY)

  return now
}
```

### Pure functions do not change the state of the system they are running in

Consider the following function:

```kotlin
fun addDaysToDate(dateMillis: Long, days: Int): Date {
  val now = Date(dateMillis + days * MILLIS_IN_DAY)

  Logger.getLogger("App").log(Level.INFO, "Date: $now")

  return now
}
```

It is a fairly common operation to add log statements to verify logic. However, this ends up changing the nature of the function itself. The function is now doing more than what it is supposed to; it has a "side-effect" on the external state of the system since it also emits something to the system log. Other kinds of side-effects include, but are not limited to:

* Updating the state of UI.
* Pushing events into analytics.
* Making a network call.
* Writing data to storage of some kind.

### Summary

A pure function is a function that is both:

1. Idempotent
2. Has no side effects

## Why pure functions?

There are [many](http://blog.agiledeveloper.com/2015/12/benefits-of-pure-functions.html) benefits to writing pure functions. We won't discuss them all here, but here are some of the reasons which we like:

### Easier to test

Let's revisit the function that we wrote earlier to add a given number of days to the current date \(the impure version\):

```kotlin
fun addDaysToCurrentDate(days: Int): Date {
  val now = Date()
  now.time = now.time + days * MILLIS_IN_DAY

  return now
}
```

What does it take to verify that this function works as expected? We need to be able to do the following things:

1. _Given_ a particular date,
2. _When_ adding a specific number of days to the given date,
3. _Then_ the returned date should be a specific expected date.

If we look at the implementation of the `addDaysToCurrentDate` function, it gets the current date implicitly by creating a new `Date` instance which internally uses the `System.currentTimeMillis()` call to get the current timestamp.

Testing this is hard since the code implicitly calls this method. In some cases, this is unavoidable, and we will look at ways to handle this as a separate lesson on testing.

For now, let us try to test the pure function that we wrote later:

```kotlin
fun addDaysToDate(dateMillis: Long, days: Int): Date {
  val now = Date(dateMillis + days * MILLIS_IN_DAY)

  return now
}
```

What does a test for this function look like?

```kotlin
@Test
fun `test adding days to date works`() {
  // given
  // 2019-11-20T00:00:00Z
  val currentDateMillis = 1574208000000

  // when
  val afterFiveDays = addDaysToDate(currentDateMillis, 5)

  // then
  assertEquals(Date(1574640000000), afterFiveDays)
}
```

This has none of the problems that we saw in the earlier test. Reading the test explains exactly what the method does, and it does not have any unneccessary code that might require the reader to understand the method implementation. In addition, changing the implementation will not affect the test as long as the function contract remains intact.

### Easier to parallelize

Since pure functions neither affect the rest of the system nor use shared mutable state, parallelizing them is extremely easy since we can just invoke these functions on as many number of threads as the system will support. Otherwise, trying to parallelize impure functions is an exercise in frustration since we'll have to consider many things like:

* Take into account all the side effects being generated by the functions and figure out if they can affect the system adversely.
* Consider all the shared state being mutated by the functions and then work on making them work nicely when mutated by different threads, like locking or synchronization, which has performance hits and make the code harder to read and maintain.

## Take away

We should use pure functions as much as possible when we write our software, particularly for defining business logic. It is, of course, impractical to expect _all_ our code to be pure \(After all, side effects pay the bills\). In later lessons, we will explore ways to separate business logic and side effects to build software that is more maintainable.

## Resources

* [https://nofluffjuststuff.com/magazine/2016/11/the\_duality\_of\_pure\_functions](https://nofluffjuststuff.com/magazine/2016/11/the_duality_of_pure_functions)
* [http://blog.agiledeveloper.com/2015/12/two-rules-for-purity.html](http://blog.agiledeveloper.com/2015/12/two-rules-for-purity.html)
* [http://blog.agiledeveloper.com/2015/12/benefits-of-pure-functions.html](http://blog.agiledeveloper.com/2015/12/benefits-of-pure-functions.html)

