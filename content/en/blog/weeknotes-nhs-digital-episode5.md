---
title: "Weeknotes NHS Digital Episode 5"
date: 2021-07-16
description: "Weeknotes whilst at NHS Digital"
tags: 
- weeknotes
- discovery
---

I'm on the train back from Leeds after kicking off Patient Encounter History with the team. My brain is a bit mushy and so this weeknote may be incoherent and full of typos, apologies!

It was lovely to meet everyone in person for the first time, build relationships, work through our understanding of the project and what we hope to acheive in the next 8 weeks. I still haven't found a better way to start new peices of work (or anything with high levels of uncertainty) than face to face workshops to be honest, for me its the last remaining part of remote work that isn't quite as good as face to face.

# Kickoff

As I mentioned in [Episode 3](blog/weeknotes-nhs-digital-episode3), we are exploring how sharing more information about a patients encounters in urgent and emergency care may improve clinical care and efficiency. One of our stumbling blocks has been what do we mean by an _encounter_ is it every time a patient interacts with one of the many parts of emergency care, or a combination of those interactions to build a picture of the patients condition over time. If the latter, at what point does one encounter end and another start? We've come up with the following distinctions to at least help us be on the same page as we describe the journey:

> An encounter is a patients journey from access point (for example 111 services, GP out of hours, Unheralded arrivals<sup>*</sup> at ED/UTC) to end point (treatment or sign posting<sup>**</sup>)

> An episode is the patient interaction at a given point in the journey (for example talking to a CAS clinician) An encounter can have many episodes.


<sup>*</sup>An unheralded arrival is when someone arrives at the Emergency Department or Urgent Treatment Centre unnanounced, i.e. they haven't been triaged or diagnosed by any other part of the service.
<sup>**</sup>Sign posting is when a patient is advised to take a course of action that doesn't require any further medical expertise, for example, "take some aspirin."

A really simple example of this is a patient phones 111 with a headache, the 111 call handler refers the patient to a CAS (clinical assessment service) clinician. The CAS clincian phones the patient back and reccomends they take some paracetemol (signposts them). That is one encounter with 2 episodes, the 111 call handler and CAS clinician interactions.

The descriptions are a little bit technical, but help us understand what we mean when we are having conversations or describing a user journey in the context of the project. Up until now we haven't been on the same page we've been describing episodes and encounters interchangeably and the lack of differentiation has been causing confusion.


Once we agreed exactly what we meant by an encounter we got into trying to map some user journeys through urgent and emergency care, this was really challenging there are so many regional variations in how services are provided in urgent and emergency care that mapping in detail was difficult. We managed to describe some journeys at a higher level of abstraction and we wouldn't have got half as far as we did without support from Kerry from NHSx, thank you Kerry! I'm a little worried that that higher level view isnt representative of what actually happens, but we're aware of its current limitations and its something we will have to keep returning to as we learn more.

From there we were able to develop our hypotheses to test, they fall into 4 main themes:
1. Patient safety - How could providing encounter data across urgent and emergency care improve patient safety?
2. Routing and alerting - How could patient data be used to alert clincians of patients conditions deteriorating, and how could we use the data to route patients to the right service based on their history?
3. Demand management - Will providing patient encounter data increase or decrease the time it takes to see patients or improve or worsen demand in different parts of UEC.
4. Patient viewpoint - How do patients feel about their history being shared accross UEC settings, how does patient encounter data improve or worsen patient trust/rapport with clinicians and satisfaction with their level of care?

You may recall the confusing term 'risk stratification' that I said needed more work. We spent a lot of time talking about what that meant in our context. When we described all the hypotheses we beleived made up the theme of risk stratification, we ultimately determined that its the balanace of clinical saftey versus demand management, and so bundled the hypotheses under these headings as we felt this was clearer to us.

As usually happens in discovery, we got a little hung up on the right level of measures to apply. Its easy to get stuck thinking about performance measures the service may have once its developed, but in Discovery all we need to prove is that we have enough confidence that this is a worthwhile problem to solve. 
We got there but went down a few rabbit holes. I find giving the team enough space to explore a potential dead end versus staying on track one of the most challenging parts of kick offs. You need to give people the space to wrap their heads around whats _not important_ just as much as what is. I feel like I got this mix about right and was pleased that there were retro comments agreeing too.

Finally we blasted out a plan for the remaining 7 weeks, its a tricky time as demand on Urgent and Emergency Care services is through the roof and the school holidays are about to start. Whether we will be successful in getting to speak to all the people we want to remains to be seen but its better to start than to not. No plan survives contact with reality and we'll never know everything, but hopefully we'll know enough to decide how to progress into Alpha.

# What else?

The week before we seemed to have a lot of external meetings relating to Patient Encounter History, there was a wider programme update where I updated everyone on our plans for disco and the kick off and I got to meet one of my digital heroes, Matt Edgar, face to face. Matt is keen we blog about the project regularly in an official NHS capacity which is exciting, I just need to work out the logistics of _how?_

Streaming and redirection rollout planning is ramping up, we're on coarse for another two sites to go live next week, and the week after that we should get clinical approval for the wider rollout. We've been sharing our rollout forecasts a bit wider to service management colleagues so they have some visibility of whats likely to happen (it's a forecast). I really like how healthy the relationship seems to be between product teams and service management at NHS Digital. There's a level of pragmatism to change and keeping people informed without processes becoming burdensome. Its very much people and interactions _enabled by_ processes and tools rather than _dictated to by_. As someone who lost faith in ITIL a long time ago after seeing the exact opposite far too often its great to see it working well.

We've picked up a little bit of work to help communicate changes to the repeat caller service to 111 providers. The repeat caller service is related to patient encounter history. Its the current solution to give call providers an alert if a patient has called more than once, in order to prompt them to investigate if a patients condition could be deteriorating. It's currently hosted at HM Land Registry's data centre (I worked in the same team that setup the datacentre leasing contract with the NHS many many years ago). On a personal level its strange to see familiar architecture diagrams in a completely different context. I'm pleased that HMLR's plan to consolidate their data centre estate is coming to fruition, but I secretly miss the cold and hum of datacentres. We are migrating the service to the cloud, it's very much a "lift and shift" project being led by our infrastructure team. The long term expectation as it stands is that the solution to patient encounter history will replace it. It's an extra dimension that falls into our patient safety hypotheses, whatever we do, it can't diminish the service thats already there.

# In other news

It's birthday season in Chez Ames, both our girls are July babies. Freya was last weekend and she went to a trampoline park with a small group of friends, only one adult could go so Hannah took her, and I'm taking Phoebe this weekend to an escape room with her friends. I'm looking forward to seeing how a group of strong willed 11 year olds friends tackle solving puzzles and working together, I musn't get too agile coachy!

We watched the football like everyone else, its weird because Phoebe is the same age as I was when Italia 90 was on, and that doesnt seem that long ago! I've been listening to [World in motion by New Order](https://www.youtube.com/watch?v=Re4aDJL3heA) quite a lot, its such a hopeful and positive song compared to the lament of 3 lions, I've been idly wondering how that song and the events of Italia 90 must have shaped Gareth Southgate's moral code? 

