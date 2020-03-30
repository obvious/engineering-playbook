---
description: See trunkbaseddevelopment.com for the official documentation.
---

# Trunk-based development

{% hint style="info" %}
A source-control branching model, where developers collaborate on code in a single branch called `master` \(or “trunk”\), and resist any pressure to create other long-lived development branches. They therefore avoid merge hell, do not break the build, and live happily ever after.
{% endhint %}

TBD promotes short-lived feature branches and frequent merges with the trunk. A branch usually has only one developer, it doesn’t last more than a day or two, flows through Continuous Integration \(CI\) and code review, and finally gets merged into `master`.

TBD is a key enabler of CI and by extension Continuous Deployment \(CD\). When individuals on a team are committing changes to `master` multiple times a day, it becomes easy to satisfy the core requirement of CI that all team members commit to trunk at least once every 24 hours.

This ensures the codebase is always releasable on demand and helps to make CD a reality. Every commit to `master` should be release-ready, and it shouldn't require coordination between teams to figure out which commit is "safe to release".

This also means that TBD is the opposite of models like Git Flow, where features are developed in parallel to `master`, living in long-running branches.

{% hint style="warning" %}
**"Branches create distance between developers and we do not want that."**  
_Frank Compagner, Guerrilla Games_
{% endhint %}

Frank’s "distance" is about the distance to the integration of code from multiple components/modules/sub-teams for a binary that could be deployed or shipped. The problematic distance is to code not present in `master`, that might:

* ... break something unexpected once merged
* ... be difficult to merge in
* ... not show that work was duplicated until it is merged
* ... not show problems of incompatibility/undesirability that does not break the build

TBD is a model that reduces the "distance" to the minimum, and there are two ways it can be accomplished:

1. In large companies which have developer experience teams \(like Google\), everyone commits directly to the `master` branch. The commits do not become part of the repository immediately -- they're usually held in a staging server, where code review happens, and CI tools are run. Once everything looks good, the commits are applied to `master` and become visible to the rest of the team.
2. Smaller teams \(like ours\) can accomplish the same thing by using Pull Requests. We create short-lived daily branches and raise a PR, usually at the end of the work day. The PR is used for CI \(formatting, lint, tests, etc.\), and it allows developers to engage in eager and continuous code review.

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

