---
title: "Are Sprints Sustainable"
date: 2016-09-15
tags:
- agile
- scrum
- kanban
---

I’m the scrum master for a small team developing a new service for a government agency. The team has been working in an agile way for 21 months. I have been with them for 16 of those months.

Over the last few months I have been feeling more and more anxious about the sustainability of sprints as we enter a new phase for our service.

We use Scrum as our methodology for delivering software. Scrum at its simplest level defines a way of working to deliver small incremental changes at frequent intervals.
These intervals are called sprints, and the team makes a commitment to deliver a certain amount of work based on how much they have delivered in the past. This commitment is then tracked during the sprint and progress good or bad is reported at the end of the sprint to stakeholders in a ‘show and tell’

Scrum can work, I have seen it work for other teams in our organisation but my team has struggled to get to a point where we can consistently make a commitment that we know we can meet.
As a result, show and tells become extremely demoralising, and our velocity on a sprint by sprint basis looks terrible. Worse still the focus on delivering stories on time has meant we have cut corners in places and our quality has dropped away from where we would like it to be.

Additionally we are entering the ‘beta’ phase of our project. We will be responsible for live support as well as delivering features. Live support by its nature is difficult to plan, you need to be able to respond to unanticipated customer requests, or degradations in your service quickly. Scrum says that if a commitment needs to be changed during a sprint, you should kill the sprint and re-plan.
Stopping and restarting sprints regularly does not feel practical or particularly sustainable. Similarly setting aside a portion of the sprint ‘just in case’ is wasteful.

## So how did we get here?
For the last year we have been in the difficult (although not uncommon) predicament of having a fixed scope and a fixed timescale. As any project manager will tell you if you fix scope and time, quality will drop:

![](/images/iron-triangle.gif "The time, cost, scope, constraint. Changing any of these can affect quality")

This certainly reflects our experience. Our quality has suffered as we struggle to meet delivering a large re-usable payment and account creation function in time for assessment and KPI deadlines.

But could we have done something different?

Scrum and especially point estimation encourages you to commit to work you know you can deliver (no bad thing) but when you are delivering new products using new technologies and new languages, estimation has a tendency to obey Hofstadter’s law:

> It always takes longer than you expect, even when you take into account Hofstadter’s Law.

The outcome therefore tends to be that sprint commitments reduce in size, and therefore deadlines are put at risk.

The team then feels responsible to try to deliver more to meet the deadline, despite the evidence and over commit. Morale then drops when that over commitment isn’t met.

The [agile manifesto](https://agilemanifesto.org/) itself states that:

> Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.

Scrum in the scenario we find ourselves in feels a long way from sustainable. In fact Ron Jeffries, one of the signatories of the agile manifesto has found this to be the case elsewhere and has coined the term [Dark-Scrum](https://ronjeffries.com/articles/016-09ff/defense/).

## What if there could be a different way of approaching this?

Reflecting on the time/cost/scope triangle it becomes apparent Scrum attempts to reduce scope to what is achievable.

However the only true constraint is time. You always have the option to change scope, cost or quality you cannot add time.

It makes sense therefore to focus commitment on improving the time it takes to move a thing from Backlog to Done as quickly as possible rather than fixing scope.

## Enter Kanban.

Kanban is often used within scrum, you regularly see backlog/doing/done boards in scrum teams. However you don’t always see all kanban principles being applied to these boards. These are:

### Limit Work in Progress (WIP) to protect constraints.

The number one rule of kanban is that in order to get things from backlog to done, you need to prevent blockages in the workflow. The best way to prevent blockages is to identify the constraints in your flow and limit the amount of work in progress to however much the slowest part can handle. By doing this it is much more visible to the team where constraints are.

If part of your workflow is blocked, and no other stories can therefore progress, then its extremely apparent that the issue needs resolving. Problems are identified much more quickly by this fact.

In my experience dev teams are much more enthusiastic looking for ways to improve speed of delivery than they are improving their estimation techniques.

### Pull not push.

In order to protect a constraint you want to manage the flow. If you are pushing work, you very quickly build up a pile of work in front of the constraint, making merging and testing more difficult. By pulling branches into the environments; which have WIP limits; you prevent stockpiling of features and your workflow ‘jamming up’. This will be familiar to anyone using git.

### Measure cycle time.

Cycle time is the time it takes for a ‘backlog item’ to get from backlog to done; and by done I mean production! I have seen many definitions of done that define ‘done’ as being signed off by a Product Owner in a test environment. For me this goes against agile principle:

> Working software is the primary measure of progress.

Surely the final acceptance of ‘working’ is that users are using it and are happy rather than tests have passed successfully?

Similarly measuring cycle time and trying to speed it up comes up with tangible realistic improvements that can be implemented rather than scope reduction and managing expectations.

### Make process policies explicit.

This is the quality gate that scrum doesn’t define as well in my opinion. Scrum has a definition of done, but kanban says to define an acceptable level for each part of the workflow not just done. This allows you to cook in the right level and type of testing to the appropriate part of the workflow and it means that stories can’t drift all the way to done without having been through some quality gates. The risk of only defining a definition of done is that the temptation can then be to ship it anyway regardless of the DoD criteria not being met, making the definition pointless.

### What about forecasting how long the backlog will take to deliver?

This is something I have struggled with as a concept in scrum, most teams estimate in points, but then we are expected to forecast delivery in time.

I have often seen this turn into ‘1 point = 1 day’ conversations as a result.

Most product backlogs fall into a standard distribution bell curve. There will be some complex large stories to deliver, there will be some tiny small stories, but most stuff will fall within 1 standard deviation of the average.

![](/images/bell-curve.jpeg "a statistical bell curve")

That being the case, if we know our average speed to deliver a story, and we know how many items are on the backlog we can easily project how long a project will take to complete without the need for points based estimation.

Additionally if we want to produce ranges we can use the standard deviations to project good and bad cases early on in the product.

#### What about quality?

So how does kanban improve quality? Well we set quality constraints on the flow too. In order to proceed to the next step you must have proven x, y, z. This obviously affects cycle time but then the focus for the devs becomes how do we prove our quality targets in the most efficient way possible? Again we wont be tempted to skip quality to meet a sprint commitment because the commitment is on our delivery speed which has a much clearer inverse relationship to quality.

#### What about standups and show and tells?

We still standup every day and talk about what we did yesterday, what we are doing today, what is getting in the way. The key difference is that WIP limits make the ‘what is getting in the way’ question much clearer, its easier for everyone to identify and see blockers and take action accordingly.

## How does this relate to sustainability of sprints?

Sprints can and do work for some teams but if you find that it isn’t working for your team then kanban is worth a look.

Previous scrum planning meetings had been focused on how we could reduce our commitment and still meet our time and scope deadlines (which rarely produced any fruitful ideas and generally led to anxiety and uncertainty). The majority of the team started to hate planning so much that there was an in-joke that everything was a 5 pointer.

When we talked about moving to kanban the meeting was electric, the team immediately started talking about how we could improve our workflow? What would we do if we hit our constraint limit in different environments? How could we improve the automation of our tests and deploys? But most importantly how could we tidy up our code as we go to ensure we pass our quality gates.

Its early days on our kanban journey and of course when you start something new there is initial enthusiasm however I am confident that kanban is a much better focus on the correct constraint (time) and offers a level of flexibility that sprints and points based estimation did not.