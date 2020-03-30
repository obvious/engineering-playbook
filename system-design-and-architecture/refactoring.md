# Refactoring

Some technical debt is in plain sight. An inadequate data structure might lead to convoluted code. When the requirements keep changing, the code might contain traces of previous approaches. Sometimes the code is written in a hurry or is just sloppy.

This kind of technical debt is easy to discuss because it’s highly visible. It manifests as bugs, performance problems, and difficulties adding features.

There is another, more insidious kind of technical debt. Maybe the test suite is a little bit slow. Not slow to a crawl--but just enough that you don’t bother looking at a bug and add it to the backlog instead. Maybe you don’t trust the deployment script so you skip that extra release. Perhaps the abstraction layers make it too hard to locate a performance regression so you leave a TODO in the code. Sometimes the unit tests are too rigid so you postpone trying an intriguing new idea until after you’ve shipped the planned features.

None of these things are deal breakers. If anything, they might seem like distractions. It feels vain to complain about them. And so these things never get done. They don’t seem important enough by themselves. The friction killed them. Some of these explorations could be of no consequence. Some of them could redefine your project. This is why you must actively reduce friction, like your project’s fate depends on it. Because it does.

## Evolving architecture

> "We build our computer systems the way we build our cities: over time, without a plan, on top of ruins." 
>
> _Ellen Ullman_

When dealing with large, complex systems, a key problem is how to evolve the architecture without just throwing everything up in the air and hoping it lands on time. That approach is a thing of the past in our world of continuous engineering and delivery. In fact, even in the past it was problematic since it deferred many of the trickiest and time-consuming integration tasks and was a source of many a late project.

A big challenge of re-architecting a system is recognising subtle inherent \(or hidden\) requirements since they are often implicit in the way the component is used rather than an explicit part of the API contract.

[Fred Brooks](https://en.wikipedia.org/wiki/Fred_Brooks) differentiates between two different types of complexity: accidental complexity and essential complexity.

* _Accidental complexity_ relates to problems which engineers create and can fix; for example, the details of writing and optimising assembly code or the delays caused by batch processing. 
* _Essential complexity_ is caused by the problem to be solved, and nothing can remove it; if users want a program to do 30 different things, then those 30 things are essential and the program must do those 30 different things.

## References

* [https://overreacted.io/fix-like-no-ones-watching/](https://overreacted.io/fix-like-no-ones-watching/)

