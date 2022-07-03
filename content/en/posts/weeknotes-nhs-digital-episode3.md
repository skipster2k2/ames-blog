---
title: "Weeknotes NHS Digital Episode 3"
date: 2021-06-27
description: "Weeknotes whilst at NHS Digital"
tags: 
- weeknotes
- discovery
---

Been a while since the last weeknotes, its been pretty busy we've been getting going on a new Discovery which has been filling my brain up as Disco's always do. I'm going to use this weeknotes to capture what I understand so far, quick reminder that weeknotes are for me to reflect what I know, this doesn't mean that this is exactly correct, there are holes in my knowledge, the NHS is a vast complex system, I probably understand about 1% of it, writing stuff down helps my understanding though.

***
## Bit of background

From the outside its not unreasonable to think of the NHS as one great big entity, but when you're one of the biggest organisations in the world the reality can be very different. Any large organisation ultimately has to break down into smaller parts in order to be manageable. The part I'm currently working for is Digital Urgent and Emergency Care (DUEC) in England.

Urgent and Emergency Care is the part of the NHS that tries to fix you if you have an accident. It covers amongst other things, Accident and Emergency Departments (generally called ED - Emergency Department internally), Urgent Treatment Centres (UTC), and Minor Injury Units (MIU). In terms of information, these areas are interested in data that supports diagnosing and treating the immediate need of the patient.

As with any system there are blurred lines around the edges. 111 is a prime example. 111 telephony and 111 online are triage and streaming services, we help identify the severity of a patients issue, diagnose if possible, and refer to the relevant service for treatment. Sometimes that is urgent and emergency care services, sometimes its primary care services, 111 services need to be able to refer patients successfully to both.

Primary care are services that provide more long term care, primarily GP's. In terms of information, a longer term understanding of a patients medical history allows clinicians to look for   and treat continuing conditions. Confusingly GP out of hours services often fall under the remit of Urgent and Emergency Care.

***
## Why does this matter?

The challenge is that each of these care settings use different care systems but patients often transition between care settings. An emergency may be treated, but have long term care needs. A patient may be discharged from hospital but deteriorate, resulting in them contacting urgent and emergency care. If patient information isn't available as they transition through these settings bad things happen. 

In 2010 [Penny Campbell](https://www.independent.co.uk/life-style/health-and-families/health-news/death-at-the-hands-of-the-nhs-the-tragedy-of-penny-campbell-419460.html) died from a Group A Streptococcus (GAS) infection. She had had a routine treatment for haemorrhoids, she had unknowingly been a GAS carrier and the bacteria entered her bloodstream as a result of the injection. As her condition deteriorated she called her out of hours GP service twice. The GP's that diagnosed her didn't have any access to previous information about her previous interactions with GP out of hours and failed to identify that her condition was deteriorating. In response to the tragedy the repeat caller service (RCS) was delivered which flagged to call handlers to 111 telephony whether a person has rung before in the previous 96 hours as a response to the tragedy.

Whilst RCS helps clinicians identify that a patients condition could be deteriorating, it doesn't help with providing access to information about what previous clinicians may have diagnosed and when. This information could potentially be useful to get to a diagnosis and treatment faster. This is what our discovery is all about.
***
## Our goal

In Urgent and Emergency care, everything is a trade off between speed and quality. If you spend ages diagnosing someone with a critical condition their risk of death or life changing outcomes increases, if you treat too early without some confidence that you know what's wrong with the patient, the outcome can also be fatal or life changing. I have nothing but respect for clinicians who walk this tightrope day in, day out.

This is important in deciding what level of information can support a speedy diagnosis. If a clinician has to wade through reams of poorly structured information to reach a diagnosis then chances are it would be quicker for them to simply ask the patient and hope they gather enough history that way.

Therefore we have framed our goal as:

**Does having access to all patient encounters within UEC lead to; improved clinical decision making and better, safer patient outcomes?"**

We have four key themes we want to explore:

**What information is useful, and over what timescale?** We suspect that this will depend on the care setting, we are grouping services into three distinct areas to help us identify people we need to speak to as the discovery progresses. This is a developing model, and we're not sure if its useful yet:

| Triage | Consultation | Treatment |
|--------|--------------|-----------|
| 111 Telephony | Clinical Assessment Services | Emergency Departments|
| 111 Online | GP out of hours | Urgent Treatment Centres |
| | | GP (Primary Care) |

**Can previous encounter information be used to get to an encounter quicker, and what are the risks?** This is a key question, if getting the right information to clinicians helps them to diagnose and treat patients faster and earlier in the process, then this has the potential to help with demand on services that are already at stress, get it wrong and we risk stressing the system further. 

There are also some interesting clinical questions we need to answer. Doctors are accountable for the diagnosis and treatment they give to patients, often triage and consultation is done multiple times as a result in order for that doctor to have confidence they are doing the right thing. This may mean that providing information could improve the quality of the outcome, but not necessarily the speed.

**How do we get encounter information and from where?** Patient data is distributed over multiple systems in England, there is no central source. Additionally systems in use in different care settings vary wildly too. There are technical and policy constraints we need to understand if we prove that there is a need, understanding these constraints early will help us move into alpha if the discovery proves to be viable.

We also need to understand how data sharing affects patients, how do they consent to their data being shared across care settings and what clinical, technical and legal risks does this introduce?


**Risk stratification.** This theme needs work, as with all discoveries some things are better defined and understood than others! Risk stratification is a medical term relating to the management of risk in a clinical setting, its a key part of the speed/quality trade off I talked about earlier, but there are multiple layers to it:

- **Individual,** the risk of the patient coming to avoidable harm
- **Population,** events presenting harm to the population as a whole (Covid, Flu etc)
- **Service,** the information available in the service being unsafe
- **System overload,** the risk of balancing demand versus safety

We need to define how what we are exploring improves the management of risk in each of these categories. The questions we ask and the hypothesis we make need better refinement to clarify expectations around this theme.

***
## Delivery!

We've had some challenges in getting a team together to get the discovery started, currently our Product Manager, and I have been doing some early engagement and exploration before we start properly, next week we hopefully have two user researchers joining us and will be supported by designers in the 111 online team. We also have clinical support in the team which has been invaluable so far.

When we start as a full team, the Disco is planned for 8 weeks, we are very much fixing time and flexing scope. Discoveries never get all the answers, we just need to get enough answers to be confident this is a viable thing thats worth exploring further in Alpha.

Inevitably with a discovery theme that crosses all of Urgent and Emergency Care (and overlaps into parts of Primary care), we have a wide range of stakeholders from NHS Digital, NHS England, and NHSx, we've been working hard to establish show and tells early. As the primary form of governance, we need stakeholders to come on the journey with us and use their expertise to course correct based on what we learn. 8 weeks isn't long and the shorter the feedback loop between us and organisational decision makers, the more likely we'll get to a successful discovery outcome.

***

So that summarises my last few weeks, this has taken me nearly two days to write as I churn through all the things I have learnt so far and try to form it into some sort of coherent narrative, this is why I love weeknotes, my thoughts feel more ordered, the process of writing this down has helped my own understanding, and the limits of my knowledge. Let me know if anything isn't clear dear person coming into this with zero context as that helps me identify my blindspots.