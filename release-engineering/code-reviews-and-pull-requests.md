---
description: >-
  Regular, team-wide code reviews are important for the health of the software
  being built.
---

# Code reviews & pull requests

Code reviews ensure standards and guidelines are respected and followed, and the larger team learns about the new code being written. Sure, code reviews can \(and do!\) help with catching mistakes early on, but in large codebases, techniques like test-driven-development are far more effective for writing bug-free code.

Core reviews are an opportunity for discussion and evaluation; a chance for novice engineers to get feedback on their ideas from senior ones, and a time for senior engineers to walk the rest of the team through their thought process.

## Most important points

{% hint style="warning" %}
It is the code that is being reviewed, and not the person who wrote it!
{% endhint %}

* Many programming decisions are opinions and not facts. When discussing tradeoffs, ensure it doesn’t lead to bike-shedding and a cost-benefit analysis is done -- “What is the cost of discussing this thing for 60 minutes? What is the benefit or drawback of picking a choice? Is it worth our time?” 
* Ask questions and don’t _demand_ changes. Good questions avoid judgment and avoid assumptions about the author's perspective.
* Don’t use hyperbolic words and avoid all sarcasm. Temper your communication, sit down, stay humble. 

Avoid selective ownership of code. Eventually, it is the team’s code and the entire team has to share the responsibility of maintenance. Team and project standards are much more important than personal opinions. When disagreeing, first commit to using the prevailing standard. Discuss the standard later... right here, in the handbook! Just [open a pull request](https://github.com/obvious/handbook/pulls).

## Assigning a PR

{% hint style="info" %}
You can automate this using [a tool like PullAssigner](https://pullpanda.com/assigner/)!
{% endhint %}

* In a round-robin fashion, assign your PR to a team member. This should be done without asking them. Everyone should be coding and reviewing at all times. 
* If you think your PR is non-trivial and needs more than one pair of eyes, then assign it to two people. If you’re new to the team, assign it to two people.
* If your PR isn’t reviewed in the next 24 hours, talk to the assignee in person and figure out what’s happening. Maybe they're busier than usual and need a helping hand?

## Helpful tips

* It is often easier to follow the author's train of thought by reviewing a PR commit by commit, instead of reading the entire diff file by file.
  * If you're reviewing on github.com itself, there are [handy keyboard shortcuts](https://help.github.com/en/github/getting-started-with-github/keyboard-shortcuts#changes-in-pull-requests) you can use! 

