---
title: "How Our Digital Team Works"
date: 2017-10-06
tags:
- agile
- government
- continuous improvement
- continuous delivery
- user research
---

I’m the Delivery Team Lead for a small multi-disciplinary team in government. We are developing the service in an agile way following the [digital service standards developed by our colleagues at the Government Digital Service (GDS)](https://hmlandregistry.blog.gov.uk/2017/6/27/working-with-gds-to-develop-our-find-property-information-service/).

We recently added the ability to keep a copy of the title summary (basic information about a property). It’s a great example of what this way of working looks like in practice.
Because we can continually develop the service, we aim to deliver the features that deliver most value quickly, rather than waiting for the whole service to be finished. This allows us to validate that the things we are building are delivering the value we expect and make better decisions about whether to improve a feature further, or move onto something new, based on feedback.

Recently we added the option to download a summary. User research and Live feedback was telling us that this was a feature user’s expected from the service.

![](/images/what_users_were_saying.jpg "A direct quote from a user: 'My document didnt print! I dont know why I regularly use my printer. You should have a save button to save the document in such cases.'")

## Minimum Viable Feature.

Research told us that users wanted to keep the summary, the question was how could we deliver that functionality as quickly and simply as possible to learn more. This is the concept of Minimal Viable Product (MVP) taken down a level to each feature. Deliver a simple feature quickly to learn more about how to expand and develop it further based on feedback. When developing software it can be really easy to slip into ‘edge cases’ or ‘scope creep’. 

It takes a lot of discipline to maintain focus on just the small valuable parts.
When considering ‘keeping the summary’ we discussed logging back in; seeing previous purchases; emailing the summary to users; but ultimately we went with the simplest option, generate a pdf based on the content of the summary screen.

![](/images/mvp.jpg "MVP — deliver small amounts of value early, you’ll learn more about what users actually want. Credit: Henrik Kniberg")

## Building services for all

This decision wasn’t without its challenges. PDF’s are not a popular choice in government due to their closed source, in-accessible nature. As civil servants, we need to ensure our services are usable by all members of the public so we take accessibility seriously.

We discussed what we were planning to do with the Open Standards Lead for government to ensure we were meeting acceptable standards. We learnt that our pdf needed to be standalone, (i.e. didn’t depend on any 3rd party servers to generate the content) and it had to meet accessibility standards.

When testing the pdf with a screen-reader we found our recent rebranding to HM Land Registry had some unexpected results. Screen-readers read HM as hmmm. Whilst amusing it’s a good example of the effort we put into ensuring our service is clear and concise for all users. We corrected the error and have informed our other content and development colleagues to check any references are appropriately abbreviated.

## T-Shaping

One of the core tenets of agile working is the ‘pizza team’ i.e. if you can’t feed the team with two pizza’s it's too big. The reason for this is all about communication and our [cognitive capacity](https://en.wikipedia.org/wiki/Cognitive_load). Lines of communication between team members increases exponentially, and the more lines of communication there are, the more noise and lost messages impact the team’s ability to deliver. This has been well understood in psychology for 60 years, yet many organisations assume large complex software projects require large teams to deliver.

But small teams still need to do all the roles required to deliver a successful service, that means cross-skilling, also known as T shaping.

Our team has been working hard to develop this. All of our developers test each other’s work, and for the example of download, our tester Heather took the lead in the development of the feature.

In order to deliver it, she developed new skills to build a Java based pdf generator. Delivery is a team sport and the whole team contributed to its success but it was a great example of the benefits of T-shaping and instilling the right mindset. Developers who think like testers deploy fewer defects and testers who think like developers can help identify where problems are in the code speeding up defect resolution.

## Starting Continuous Delivery.

Agile delivery is all about making feedback cycles between the user and the development team as small as possible. In the past, we would release every 6 weeks leading to the vicious cycle below.

![](/images/releases.jpg "The big batch release conundrum. Releases go wrong, so we won’t do it often, but this results in more change being bundled into the release, increasing the likelihood of it going wrong, and the effort to test.")

We are now able to deploy to production at least once a sprint, and we don’t say our work is done until it is in production delivering value. When we delivered download, we deployed it at 9 o’clock in the morning with no downtime, within a minute of it being deployed we were able to see users using the feature. The sense of satisfaction to see the work you have delivered bringing value to people immediately was immeasurable.

## Continuous Improvement.

Hopefully, that gives you a little bit of an insight into how we are starting to build, deliver, and maintain services. We have come a long way on our journey delivering in an agile way, but this isn’t the end. We are always looking at how we can continuously improve our service. Initial feedback for pdf download is positive, and therefore we have moved onto delivering the next important feature in the service, moving sign-in further back in the user journey.

We don’t stand still after a feature is delivered we regularly do a ‘show and tell’ to describe how the service is performing to our product owner and we do ‘retrospective’s’ to identify where we can improve as a team, we never stop looking for ways we can improve as a team to ensure we deliver the maximum value to you our users.