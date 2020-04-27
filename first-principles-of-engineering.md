# First Principles of Engineering

## We review code, before we write code

The code that has been written and is pending review is the one nearest to being able to generate value. It has already had all the efforts put into it being thought about and being written.

So we give priority to reviewing any pending PRs before we begin to write code for the day. Once that PR gets merged, the whole codebase starts benefiting from any value that it creates.

## A culture of searching, reading and writing documentation

Documentation is very important part of software development and also something not a lot of people are habitual in writing or reading. If a product is documented properly, moving around and understanding the codebase becomes really easy.

## Failure is learning what not to do

When we try something out and it does not work as wanted doesn't mean it was a failure, it taught us what not to try the next time. What matters is that we give it the best shot we can at that particular time.

## We measure, so we can improve

We have very well defined metrics which help us quantitatively calculate everyone's progress. Details coming soon.

## Only improvements made at the constraint are of value

This principle follows the [Theory of Constraints](https://www.leanproduction.com/theory-of-constraints.html) which as quoted in the article says "The Theory of Constraints is a methodology for identifying the most important limiting factor (i.e. constraint) that stands in the way of achieving a goal and then systematically improving that constraint until it is no longer the limiting factor".

Digging deeper with an example, let's say there is vada making factory and Raj is the owner.

- There are a few processes through which the raw material has to go through to produce the final product.
- Let's say the processes are as follows:
  - A (Farmer)
  - B (Dough Preparation)
  - C (Vada Fryer)
  - D (Chutney Maker)
  - E (Final Packaging)
- Now suddenly Raj notices that final output of vadas from his factory is 10% less than his expectation. Now he needs to figure out what the problem is.
- Let's say this problem is occurring because the Chutney maker is slower than expected. But Raj or anyone in the factory is unaware about this.
- Now if Raj asks the Farmer to produce more raw products and asks everyone to be a little faster to be able to make better progress. There will still be a 10% lag in the expected result. Until he realises that the Chutney maker is what is causing the problem.
- And increasing the efficiency of any other process won't actually increase the efficiency of the entire factory. It will just start to create more lag.
- For example, the manager at C (Fryer) says that they can double their productivity and can fry twice the number of vadas. The result of this will be that there will be more vadas than there is chutney for at D (Chutney maker).
- Which is why, understanding what is it that's slowing the process is important. And working hard on that constraint is what's most important to increase efficiency.
