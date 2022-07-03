---
title: "Product Prioritisation is triage"
date: 2022-02-09
tags:
- product management
- agile
description: "Practical tips for product prioritisation from triage."
---


[Triage](https://en.wikipedia.org/wiki/Triage) is used in medicine when acute care cannot be provided for lack of resources. The process rations care towards those who are most in need of immediate care, and who
benefit most from it. More generally it refers to prioritisation of medical care as a whole. I have some personal experience of using triage from my time as a mountain rescue volunteer. 

We would often train for scenarios where the number of casualties was more than our capacity to treat them all. Most of the volunteers weren't medical professionals (myself included) so our processes were simple. Our priority was to stabilise casualties and transport them to medical care as quickly and safely as possible.

I often see a lot of overlap between triage and product backlog refinement, after all picking the most important thing to work on is an exercise in prioritising effort when there is more work than can be done (there's always more work than can be done). I’m currently working with the 111 online team at NHS Digital. 111 online is a triage tool for patients, you describe your symptoms, and it works out what service can help you get diagnosed and treated at an appropriate level of priority. 

As is common with most other product teams we regularly refine and prioritise the backlog of work we have to do. Prioritising what to work on next is always a challenge, do we deliver a new feature we know will help? Do we remove some tech debt? Do we start some research into a problem area within the service? Inevitably prioritising one thing over another means someone loses out, this is particularly acute in healthcare and can make for tough conversations.

The similarities between triage and product prioritisation have become really apparent to me, and I believe there are some tactics product owners can use to prioritise effectively:

## Assess the landscape.

Before even going into a casualty site, a Mountain rescue team will assess for danger to casualties and to themselves, similarly product teams should know the landscape they are working in. If you’re at the beginning, run a [discovery](https://www.gov.uk/service-manual/agile-delivery/how-the-discovery-phase-works) to assess the landscape, at the very least you should be able to answer:

- What problem are we solving?
- What risks and constraints do we face?
- Who are our competitors?
- Is this worth pursuing?

## Have a simple scale for comparing changes.

Triage often uses a scale to compare patients and identify who to treat first, there are various ones in use depending on the care setting, in mountain rescue we used the AVPU scale. This was a simple guide that could be used by people who weren’t medical professionals.

Is the casualty:

**A**lert - In which case they’ll probably be fine, they are the lowest priority (this can include patients screaming in pain).

Responding to **V**oice - The casualty may not be fully alert, but they are responding to questions such as whats your name. Second lowest priority

Responding to **P**ain -  The casualty appears unresponsive, but does move or respond if you apply a small amount of pain, such as a squeeze or pinch, Second highest priority.

**U**nresponsive - casualty isn’t responding, deal with them first.

In reality making these kind of decisions is incredibly hard when faced with real casualties, but having a scale (and training for it) helps to treat the people that need your help the most with minimal effort spent discussing who to treat next.

Similarly, in product management assessments of a change or feature can quickly fall into opinion and circular arguments if there isn’t a simple way to compare one change to another.  Developing a simple priority checklist similar to the AVPU scale gives a mechanism to objectively compare things and get consensus on what to work on next, it avoids teams chasing multiple priorities, and reduces circular conversations.

 

An example may be:

### Impact

For every yes answer below, add 1.

1. Does it improve clinical safety?
2. Does it improve outcomes for a large number of users (to be defined)?
3. Does it have a significant improvement for a small number of users?
4. Does it improve NHS's reputation?
5. Does it save money?
6. Does it reduce technical complexity?
7. Is this going to be fun to do?

### Difficulty

For every yes answer below, add 1.

1. Problem is vague and not well researched
2. Requires policy change
3. Requires IG
4. Requires pathways change
5. Needs local services to implement
6. We've never done this before

Take away Difficulty from Impact, whichever is biggest wins.

Your questions will vary depending on your sector, company goals, and team so work towards developing them together and iterating as you use it. Try to avoid falling into the trap of making your product prioritisation framework complex and unwieldy. The process should be quick, simple to follow and easy to change if needed, so avoid if statement’s or variable scores based on volume or other measures.

An additional bonus to this approach is that it gives the team the ability to make assessments without needing product owner input all the time, which helps to empower them and free’s up product owners busy schedules.

## Workout how best to use the team?

Different casualties present Mountain Rescue teams with different demand on their skills. For example an unconscious patient thats fallen from a cliff and has a suspected broken spine will require the whole team to carry the patient off. Other scenarios, it may be ok to break into smaller groups to treat more casualties. The same is  true with a backlog, just because something is the highest priority, doesn't necessarily need the whole team to solve it, or it might! Assess each item and work out:

- Does the highest priority thing, need the whole team to solve?
- Is this likely to change as we learn more?
- If we start other things in parallel, is there any chance they can prevent achieving our main priority? Are they safe to leave?

## Practice!

Theory is nice, but its hard to tell someone you’re not going to treat them when they’re clearly in pain. Mountain rescue teams train regularly so that mistakes can be made, disagreements can be aired and teams can learn in a space that doesn't compromise casualty safety. It’s safe to fail.

Making priority calls takes practice too, but most product teams don’t have the luxury of practice (unfortunately). Sprint planning and refinement are the nearest equivalent for most teams to have discussion about the problems they are being asked to solve, ensure teams have the time and space in these sessions to air their views and work through disagreement. The team won’t always agree on whats the most important thing. If there’s disagreement, thats normal, get comfortable with it, if everyone is always in agreement about whats the most important thing is then you’re probably not being ruthless enough with your prioritisation. It’s better to have these conversations in advance rather than when in the weeds of the work so make regular time for planning and refinement sessions.

## Make space to process decisions.

After every training session with the mountain rescue team (and some callouts) the team would decamp to the nearest pub for a cooldown. This gave the team the space to process what could often be quite traumatic experiences and to process it together, you don’t want people to go home and stew on a poor decision they may have made alone, and story telling after an event is a great way to reinforce learning. 

I’m not suggesting a pub is always a suitable environment for an inclusive product delivery team but what is important is to give the team the space to process the decisions that have been made. In any team with a complex and important mission hard decisions will need to be made and mistakes will be made, giving people space to process this together reinforces learning and grows trust. Well run retrospectives can be this mechanism, but less formal breakouts or team meetups can be equally effective