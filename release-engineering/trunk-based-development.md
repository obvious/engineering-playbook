---
description: From Feature-based Delivery to Timeline-based Delivery.
See [trunkbaseddevelopment.com](https://trunkbaseddevelopment.com/) for the official documentation.
---

# Trunk-based development

{% hint style="info" %}
The Trunk Based Development website says “It is a source-control branching model, where developers collaborate on code in a single branch called `master` \(or “trunk”\), and resist any pressure to create other long-lived development branches. They therefore avoid merge hell, do not break the build, and live happily ever after.”
{% endhint %}

That sounds great but... what exactly is it, and why should you care about it? For a bit, let’s forget about code and branches and use an analogy that is easier to understand -- the transit system of a city.

## When is the next train? 
Imagine a city with lots of different train stations. The network can run using lots of trains at different frequencies. Let’s consider three different scenarios:
- A train passes through each station once every day
- Trains pass through each station six times every day
- Trains pass through each station a hundred times every day

What will be the effect of the three different possibilities on the people living in the city?

**In the first case**, if a person misses the train there is no other way to reach the destination until the next train, which unfortunately will arrive on the next day.

**In the second case**, if a person misses one train they can catch another train in a few hours and won’t have to wait for an entire day to reach their destination. This means people don’t care about the schedule of the trains as much as they do in the first case. It is possible to reach the destination in a few hours -- late, but possible.

**In the last case**, if a person misses a train they can easily catch another train in a few minutes. It’s easy to imagine that people will stop caring about the train schedule altogether and focus on what they want to do at the destination. The transit system becomes an artifact that recedes in the background, letting people concentrate on what they actually want to do -- living their lives and getting things done! 

Now let’s go back to building and delivering software.

## Feature-driven delivery a.k.a. Unpredictability
In a lot of teams, the frequency of releases is determined by “when this Important List of Features gets done”. That leads to unpredictable releases with large delays between deployments. Although such teams try to “fix” a release date and try to cut scope so that the Very Important Date can be met, it rarely works.

Engineers working on different feature branches rush to get their tasks done before The Date. Merging all of those feature branches becomes a painful ritual as people discover all sorts of changes that have happened in the repository over the past few weeks that they were working on their own branch. Merge meetings are scheduled and a War Room is created to tackle issues that stand in the way of meeting The Date. Inevitable, The Date starts to move. Seven “medium priority” bugs that customers have been complaining about need to be fixed. The CEO’s personal favourite feature request has to be part of this release even though the team heard of it a week ago. 

Every little thing is important because who knows when the next release will go out? The entire team -- nay the org -- rallies around The Date even though it has changed three times and the original date has been forgotten. 

There are some themes that emerge in this familiar scenario:

- **Merge hell**, as discussed above, since multiple, long-running feature branches become part of the primary codebase very close to The Date. 
- **Massive changesets** to review, or what happens in reality, no code review at all. Reviewing a three-thousand line diff that has been worked on for two weeks is an exercise in frustration. 
- **Favouring the Rockstar Programmer** over the team, since it is considered acceptable and natural that a great engineer will disappear for a few days or weeks, and come back with all the work done in a branch far, far away from the rest of the codebase. Merging is the team’s collective problem, unfortunately. 
- **Emotional turmoil** and a high probability of burnout for everyone in the team especially as The Date inches closer. 
So what is the solution to this problem? We need to increase the frequency of the trains, of course. Hundreds of them every day!

## Timeline-based Delivery a.k.a. Daily Success
For software engineering, that implies… 
- We increase the frequency of production releases to as frequent as possible -- daily, or even hourly! 
- We drastically reduce the size of changes that are merged into the trunk. As each merge request becomes small, reviewing it becomes far easier. 
- Since each merge integrates only a small number of changes, the possibility of conflicts also rapidly goes down. When conflicts do happen, resolving them is fast and painless. 
- Changes arrive into the codebase on a daily basis, which means the team is aware of the state of work that is in progress. Any impact from the changes being done is felt very early in the process, giving the team ample time to reach a resolution. 


All of this sounds great in theory and it makes sense. How about in practice?
- TBD promotes **short-lived feature branches** and frequent merges with the trunk. A branch usually has only one developer, it doesn’t last more than a day or two before it gets merged into the trunk.
- This automatically pushes teams towards **Continuous Integration**. Every commit that lands on the trunk goes through the CI pipeline, confirming that it is indeed ready for integration. 
- Once continuous integration is in place, it is natural to follow it up with **Continuous Delivery**. Since all commits that land on trunk have been marked “stable” by the CI pipeline, they can be deployed immediately. 
- Since an approved code review means the code will be available on trunk immediately, **teams rally together to review code** as fast and as many times as possible. 
- Not everything can be done within a day, and features can take a long time to build. In those cases, **work-in-progress code is “hidden” behind a feature flag**. Flags ensure that incomplete features can be reviewed and still land on the trunk.
- Flags can also **act as a remote control** for making features available at a later time. Features can be fully developed and be part of the codebase, and then be remotely toggled on (or off). Once a feature has been “enabled”, the alternative code path and flags can be deleted from the codebase. 

All of this comes together to ensure the codebase is releasable on demand. Bug fixes are deployed as soon as the fix is available on the trunk. Teams stop coordinating releases to figure out which commits are “safe” to release.

Developers go back to focusing on what is important – building features and eliminating bugs – rather than being burdened with a release date.

## Daily branches

To ensure that constant integration of code is happening, we prefer making "daily branches". This doesn't strictly mean a branch every day, but branches _rarely last beyond 2 days_ without being raised as a PR. We also ensure that the changeset of a PR doesn't exceed _300-400 lines of code_.

### Conventions

* Daily branches are named as `initials/date/subject`
* For example, if your initials are PK, and you raise a branch on 17th December to update the Android Gradle Plugin, your branch title should be something like `pk/17dec/upgrade-agp`
* No underscores allowed, only dashes

## Releases

In the ideal world of TBD, every commit is stable and release-ready, which is why CD works so well once a team switches to doing TBD.

On a platform like the Web, every commit to `master` should be deployed as soon as possible, and it makes sense because users immediately get the updated resources. However, on mobile platforms like Android and iOS, deploying a commit leads to the creation of an installable binary file. This file is pushed to a Store and it usually takes a few hours to a few days before all devices can see the available update -- and this process is entirely out of our control. Not only that, the user can choose to not install an update for days or weeks on end!

As a result of this, we follow a periodic release cycle -- once a week, or once every two weeks -- for mobile apps, instead of pushing every single commit. To ensure that the binary that is being published is stable, we pursue the following strategy:

* We create a release branch from master; this is titled as `release/yyyy-mm-dd`, where the date in the title is the date this branch will be released to the Store
* The code in the branch is tested till the date of the release
* No one directly commits anything to a release branch. If a bug is found or an urgent change needs to be made, that change is first done on `master` and then cherry-picked onto the release branch

## Associated techniques

* [Feature flags](https://trunkbaseddevelopment.com/feature-flags/)
* [Branch by abstraction](https://trunkbaseddevelopment.com/branch-by-abstraction/)

