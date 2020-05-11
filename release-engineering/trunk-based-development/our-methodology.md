---
description: >-
  Following "pure" TBD is difficult without a lot of tooling, so here's the
  lightweight approach that we follow that relies on team discipline.
---

# Our methodology

## Daily branches

To ensure that constant integration of code is happening, we prefer making "daily branches". This doesn't strictly mean a branch every day, but branches _rarely last beyond 2 days_ without being raised as a PR. We also ensure that the changeset of a PR doesn't exceed _300-400 lines of code_.

### Conventions

* Daily branches are named as `initials/date/subject`
* For example, if your initials are PK, and you raise a branch on 17th December to update the Android Gradle Plugin, your branch title should be something like `pk/17dec/upgrade-agp`
* No underscores allowed, only dashes

## Releases

In the ideal world of TBD, every commit is stable and release-ready, which is why Continuous Deployment works so well once a team switches to doing TBD.

On a platform like the Web, every commit to `master` should be deployed as soon as possible, and it makes sense because users immediately get the updated resources. However, on mobile platforms like Android and iOS, deploying a commit leads to the creation of an installable binary file. This file is pushed to a Store and it usually takes a few hours to a few days before all devices can see the available update -- and this process is entirely out of our control. Not only that, the user can choose to not install an update for days or weeks on end!

As a result of this, we follow a periodic release cycle -- once a week, or once every two weeks -- for mobile apps, instead of pushing every single commit. To ensure that the binary that is being published is stable, we pursue the following strategy:

* We create a release branch from master; this is titled as `release/yyyy-mm-dd`, where the date in the title is the date this branch will be released to the Store
* The code in the branch is tested till the date of the release
* No one directly commits anything to a release branch. If a bug is found or an urgent change needs to be made, that change is first done on `master` and then cherry-picked onto the release branch

