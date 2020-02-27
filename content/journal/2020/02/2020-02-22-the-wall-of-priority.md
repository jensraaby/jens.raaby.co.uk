---
template: post
draft: true
title:  "The Wall of Priority"
date:   2020-02-22 22:33:25
slug: "the-wall-of-priority"
category: agile
tags: 
- work 
- agile
---

- all software projects have a need to balance priorities and make sure important technical problems (tech debt) don't build up too much
- developers often raise tickets to postpone addressing issues, usually because the amount of effort required is non-trivial
- but it is often frustrating being one of those developers. if you aren't involved in prioritisation (it's often just the tech lead and product manager) then you might feel like the debt is growing and you may be right - but you probably also lack insight into what all the business value tasks might be.
- We raised this issue at work a couple of years ago and our product manager came up with an great solution - visualising the entire backlog on a wall in the office, so we could at a glance see what was most important, and what was most urgent.
- This 2D representation captures something which you can't quite get in JIRA or Trello with a simple ordering.

How does it work?

- we work in fortnightly sprints. At the start of a sprint, we sit around the wall of priority and go through any new tickets (which are at the bottom of the backlog). There is some discussion about where to position them, with some debate. It helps a lot to have to spatial context - we can see what tickets are similar, and do a relative estimate.
- After the prioritisation, we estimate tickets. Previously we used a Fibonacci scale (1,2,3,5...) but we found that too fine grained and shifted to just using 2 and 4. This correlates with our time-limits - stories are reviewed after 2 days to see what work is left, and again at 4 days. This review isn't that frequent, but it gives an incentive to keep productivity up and stop things dragging on. Sometimes a technical debt ticket is raised at this stage which then feeds in to the next sprint planning.

Findings:

- We found there tend to be clusters of tickets. The bottom left of the wall is referred to as the boneyard. We realised that the line separating this from the rest of the stories is actually quite high up. Occasionally an issue comes up while we're working on a story, and we move it to the bottom of the backlog so it will get reprioritised at the next planning meeting. This helps somewhat with tech debt.
- Refactors that get raised as tickets tend to be prioritised a bit lower on the killer-feature scale, but still quite high on the "do this soon" axis. They tend to linger as feature work or time-sensitive issues take priority. Again, we sometimes re-prioritise based on upcoming work
- We have decided to declare some tickets as "dev picks". These are physically starred. If towards the end of a sprint we have run out of work, these can get picked up as nice-to-haves. Sometimes they are picked up by an engineer during 10% time. This bypass of priority can help when an engineer has a personal bugbear 
