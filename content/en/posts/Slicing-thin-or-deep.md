---
title: "Delivery Tactics - Slicing thin or deep?"
date: 2022-07-03
categories: opinion
tags: 
- Delivery tactics
- MVP
---

![A mug of tea in my #shedlife mug](/images/shedlife_mug.jpg)

A key part of agile delivery is working out what small changes can deliver the most value. It can be hard to get agreement on what is small enough to be valuable, getting this balance right is extremely difficult and context specific, hence why MVP’s (minimum viable products) are much maligned. 

There are two main approaches that can be used, you can either ‘slice thin’ deliver a small part of every step of the user journey; or ‘slice deep’ focus your effort on improving one part of the end to end service journey. Deciding which way to go depends on context, below are some things I try and consider with teams and stakeholders.

Agreeing the right approach for your context will enable you to set expectations. Both approaches are designed to allow you to deliver quickly which allows you to establish trust and support for future iterations.

It’s worth noting that in order to make good choices, it pays to have a good understanding of the problem space, a good discovery of user needs is key to this, perhaps I’ll write the next post on what makes a good discovery!

# Thin slice contexts.

A thin slice is usually used when developing a new product. The idea is to develop the bare minimum to each step of an end to end user journey. Just enough to allow someone to complete what it is they are trying to do. A thin slice is usually not very feature rich and focuses on just the core needs of each step. The key point of a thin slice is to enable fast learning, by presenting your users with a basic service you will get faster feedback about what to improve next. Thin slices work best in competitive, innovative spaces, they give you the means to get rapid feedback on new product ideas without a huge commitment to features that may not be needed nor wanted.

For example, you think there is a gap in the market for ‘deliveroo of tea.’ and you have some basic research to suggest customers and businesses are interested (go with me here!). In order to test your idea your service journey looks roughly like:

1. customers can find their preferred tea shop.
2. customers can order and pay for their tea
3. tea shop needs to receive the order and process it.
4. customer wants to track the delivery
5. tea is delivered
6. customer receives tea, tea shop gets paid
7. customer leaves review

If at this early stage of the business your development team produced a really effective find algorithm but none of the other functionality you’re going to go out of business pretty quickly, so the idea is to think about the smallest thing that needs to be done to enable each of these steps.

**For example:**

1. Customers are shown all the tea shops, there is not search because we only have 10 tea shops registered at this early stage.
2. We’re using an existing payment api to take the order.
3. We employ an intern and manually send the order to the tea shop via email for the time being.
4. We don’t enable tracking but give a very rough eta at the order stage, if people definitely want it, they’ll tell us.
5. We’ll use deliveroo to deliver the tea for now.
6. Our intern will manually pay the tea shop one we get acknowledgement the tea has been delivered
7. We use an existing review api service to collect reviews.

The development effort of the above is to build a website showing 10 tea shops with payment and review integration. It’s by no means a done product but its enough to get started and getting feedback that this is a product thats worth while investing in, from there you can develop the product further based on feedback and data about how the product is performing

## Characteristics of when thin-slices are the best approach.

Slicing thin works best in environments with one or more of the following characteristics:

- You’re in a competitive, innovative problem space.
- The whole end to end service journey isn’t being met currently. It’s a new space.
- You don’t have much insight into how to solve the problem, you have a rough sketch of the problem space.
- You have a user group (or a subset of users) who are willing to try an imperfect solution rather than tolerate the problem your solving. Crucially they will also tell you where your thin slice needs to go wider or thicker as you progress.

## Thin slicing with existing services.

Thin slicing can be an effective way to demonstrate how an existing service can be delivered in a modern digital way, but it does require careful management. People will have expectations of how the service will work and they may expect that all the current features are delivered before it is done. You’ll need to be really explicit about how your new service will work alongside the existing one. It pays to find a small group of vocal existing service users to try your thin slice and feedback in much the same way as you would for a new service. 

It may be necessary to project a longer term strategy that shows how the existing service will be phased out as your new service develops. Ideally aim to make those phase out decisions based on achieving objectives or performance metrics rather than arbitrary time forecasts. Phasing out an old service will take longer than you think, even when you account for it taking longer than you think!

# Deep slice contexts.

A deep slice is where you focus on improving just one part of the service journey, it can still be used to seek fast feedback and adapt to what you learn but it is focused on only one small part not the end to end. This approach can work well when the service already exists and is generally working well, but has pain points in a few key areas. Lets go back to our tea example.

Tealiveroo has been operating successfully for a few years now, you’ve iterated your product from its initial thin slice development and the service as a whole is performing well. However you have been getting feedback that the dropout rate on searching for a tea shop is high and so you want to focus on how you might improve this area.

In this example there’s little point in taking a thin slice approach as you know the area that needs focus. You can still try to make small experimental changes in this space and should absolutely stop once you’ve solved the problems you’ve identified, but its focus is in just one part of the service journey.

## Characteristics of when deep-slices are the best approach.

Slicing deep works best when:

- You already have a service that is performing well enough but has some specific pain points.
- You’re focusing on efficiency/ time savings rather than innovation/ new ideas
- You have a burning platform that supports part of your service that you need to get off.
- You work in a large organisation where small marginal gains have a huge impact due to scale.
- Most of the service journey is working well, an end to end service replacement would need to replace the majority of the functionality to be considered ‘MVP’.

# In conclusion.

Choosing the right approach to delivery of the problem you’re faced with can be hard, considering the context you’re operating within and the characteristics of the problem can help you choose the right approach. Regardless of which approach you use there are some principles that apply equally regardless of whether you go thin or deep:

1. Start small
2. Deliver to learn
3. Change plans based on what you learn
4. If you solve the problem you set out to solve, stop! Go onto the next problem.

Let me know what other tactics you use to identify the best approach to delivery.