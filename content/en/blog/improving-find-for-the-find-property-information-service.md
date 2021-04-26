---
title: "Improving 'Find' for the Find Property Information Service"
date: 2018-01-31
tags:
- software development
- agile
- government
- product management
- user research
description: "How my team identified an improved our address based search at HM Land Registry."
---
[Find Property Information](https://search-property-information.service.gov.uk/) is a GOV.UK service being developed by HM Land Registry which aims to provide a simple summary of property information. Recently we have improved our ‘postcode search’ functionality.

## Why did we do this?

Our first iteration of searching was developed over a year ago, we knew the limitations of it, but it was ‘good enough’ for the early stages of the service. This allowed us to move onto developing other features. Since then the quality of search has crept up the list of user issues.

## What were the problems with the old search?

There was a mixture of design and technical issues with our old search:

- When users come to the service they think in terms of addresses, but our search results displayed land titles. This meant the results were jarring, it was especially unclear if there was more than one ‘title’ for a given address.
- We hadn’t updated the address information we get from Ordnance Survey for over a year, so new builds wouldn’t show in the service.
- Search results were confusing because of the order of the displayed addresses.
- We limited search results to a maximum of 50 on the false assumption this was the terms of the Ordnance Survey Addressbase licence.

![](/images/search_results_before.jpg "Search results before improvement, results were ‘titles’ rather than addresses - which the user searched for - causing confusion.")

## How did we improve it?

Based on feedback we’d been collecting we had a good handle on the types of problems people had, and a strong hypothesis that people would be more successful if we flipped the results. We aimed to stop showing what we have got (how we’ve documented the world), and start showing a familiar model of places (how user’s think of the world).

People are familiar with what a postcode is, and what it contains — they use this all the time, when they are getting a parcel delivered, or sending a letter, or using their satnav.
There is a point at which we, currently, ask people to pick a particular property record.

So we now do that as a separate steps. previously we had wrapped multiple decisions into one step, which was too much.

So whilst we still need, currently, to introduce the concept of titles and tenures, we do this in one place.

![](/images/search_results_after.jpg "The new search results are much clearer and align to what our users expect to see next.")

## How did we build it?

The Find Property Information team consists of 12 people from different disciplines, we sometimes struggled to communicate effectively and stay focused due to the sheer numbers of communication pathways between team members. We had a hunch that the size of the team was slowing down our delivery so we decided to use postcode search as a good opportunity to test it. We separated out 4 people to focus solely on delivering improved search.

The team came up with a number of technical approaches and chose the one that would deliver the most value. There were other potentially better solutions, but would have taken longer to implement. Building services is always a trade off between building what’s needed now, and envisioning future use cases. There are risks to both approaches, too bare bones and it can be difficult to change the solution in future, too blue sky and time and energy can be wasted on features and functions that aren’t actually needed.

On the whole we saw a lot of benefits from the small team. The small size meant that our processes could be much more lightweight, much less time was spent planning and discussing work, if a problem came up or a change needed to happen, it was much easier to solve as it was just a quick chat to discuss the problem, think of how to solve it and move on.
The team progressed well and improved our address search component, built a title-api for retrieving titles per address, and ‘plugged into’ an audit-api for collating what was happening within the service for troubleshooting and audit needs.

But we reached a point where we needed to ‘plug-in’ what had been built back into the service. We needed to consider how we could deliver the functionality that had been built iteratively into the service without getting in the way, or breaking any of the other work being done by the rest of the team.

## Agile doesn’t equal No Planning

We had a reached a point where we needed to get the team back together and consider how to move postcode into the service.

We came up with a high-level plan to deploy each of the new api’s in a way that wouldn’t impact the service or cause any downtime. It was also an iterative plan so by breaking the releases down into small chunks we could de-risk the change and rollback easily if any particular part did go wrong.

![](/images/whiteboarding.jpg "Planning agile style, team members gathered around a whiteboard")

We also wanted to assure ourselves that the search was as good as we thought it would be so we included: a comprehensive set of automated acceptance tests; manual eyeballing; and tests to verify our hypothesis of what we expected to happen when the changes were in production.
The hardest part of testing was finding a decent baseline to ‘prove our search was good. We knew our existing search was inconsistent so it made for a very poor baseline. We had other services that also had search functionality so we did some investigation into these services to test their viability as baselines.

What we found was that whilst on the whole they were good enough as a baseline, they all had slight discrepancies or weird results mainly due to data quality either from us or from our address suppliers. The Addressbase dataset has over 28 million address points, and our register data is over 24 million titles. Both of these datasets change daily and when they are as large as that even a 1% error rate can equal hundreds of thousands of data rows.

Improving the quality of these two datasets wasn’t going to be possible so instead we attempted to understand the problems a bit better so that at least if users did encounter issues we could offer them an onward journey or understand why. We produced a ‘wall of weird’ of postcodes we knew behaved strangely in existing services and added these to our test baseline to see what happened in our service.

![](/images/wall_of_weird.jpg "The wall of weird, a whiteboard where we captured all the strange search behaviour we identified, so that we could validate we had fixed them as we improved the service.")

## How did we release it?

So we had a test and deploy plan that was detailed enough to give us direction, but lightweight enough to change when things inevitably changed or went wrong. And a few things did go wrong.

1. We hoped to release an updated address index into the service as a standalone iteration. However, when testing it, we found it had more of an impact on the user experience than we were comfortable with, so we had to bundle the change in with the ‘main’ release.
2. As a result the main release became bigger than expected and we had to schedule in downtime, adding a number of additional steps and approvals.
3. We found the title-api performed within thresholds but not as well as we would like, we found that search results had spikes of long response times. Whilst only affecting 2% of users, scaling up to actual usage volumes could equal hundreds of unsatisfied people.

That final problem was the biggest challenge we faced, we hadn’t seen it in any of our lower test environments, but then again our pre-prod environment is the one that most resembles live. At first we didn’t have a good handle on exactly how big the issue was so we created some performance scripts to allow us to monitor response times whilst under heavy load. The scripts confirmed the scale of what we were seeing, but didn’t give us any further clues as to what was causing it.

Finally we decided that the benefits of the new search functionality exceeded the risks of some users having slow performance. We came up with a plan for measuring production performance and agreed to set some time aside to improve it should we see it happening in PROD.

Finally we were in a position where we were ready to release. We had to turn the service off for an hour but pre-warned users of the downtime. The change itself went very smoothly and we were deployed and tested within 50 minutes.

## How do we know whether it has been successful?

The measure of success that was most pressing was whether PROD would see the same performance issues that we saw in the test environment. It took a few days to build a sample of traffic but sure enough we did see the same problem. By then however we had given a bit more thought as to a plan for improving the performance. After the first release the refactored code went into production, drastically improving performance times.

![](/images/before_performance.jpg "Initial performance times, good but not excellent. Most responses within 2 seconds")

Initial performance times, good but not excellent.

![](/images/after_performance.jpg "Production responses following improvements, most responses in under 0.1 seconds!")

Production responses following improvements, note the change in scale!

All of our hypotheses of what would happen in Production have so far played out to be true:

1. From the sample we tested our search is as good as existing HMLR services.
2. Addresses changed in the past year now return in our search results.
3. Our new audit-api is collecting audit data successfully.

The most important change is that search is dropping down our ‘Top issues for our users’ chart.

## Whats next?

We will continue to learn more about how search is performing in the service, shipping to Production is the only true point where you really start to learn about how people use your service and how it works at scale so I’m sure we will need to make a few changes based on feedback.

We also have some work we want to do, to replace our address component with an address-api that is being built by colleagues in another team. This ‘common component’ will reduce maintenance overhead and ensure more consistency between services in the future.