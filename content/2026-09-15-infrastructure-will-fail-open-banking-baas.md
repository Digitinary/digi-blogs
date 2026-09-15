---
title: 'Your Infrastructure Will Fail Your Open Banking (and BaaS) Project — And You Have Not Noticed Yet'
subtitle: 'Everyone focuses on APIs, consent, and authentication. Almost no one asks whether the middleware underneath can survive the traffic Open Banking, BaaS, and AI agents are about to send its way.'
author: 'Salah Abu-Msameh'
authorRole: 'Founder & CEO, Digitinary'
authorBio: 'Founder of Digitinary, focused on digital transformation, APIs, and Open Banking / Finance across the region''s financial and enterprise companies.'
date: '2026-09-15'
excerpt: 'Most Open Banking projects pass compliance on time by fixing the API layer. But the legacy middleware carrying that traffic underneath was never built for it. Here is why that gap gets expensive, and what the right architecture looks like.'
coverImage: '/blog-media/infrastructure-will-fail-open-banking-baas/cover.webp'
tags:
  - Open Banking
  - Banking-as-a-Service
  - Middleware
  - API Gateway
  - Microservices
featured: false
slug: 'infrastructure-will-fail-open-banking-baas'
seoTitle: 'Your Infrastructure Will Fail Your Open Banking Project'
seoDescription: 'Open Banking, BaaS, and AI agents bring API traffic legacy middleware was never built for. Why compliance alone is not enough, and what the right architecture looks like.'
seoKeywords:
  - 'Open Banking'
  - 'Banking-as-a-Service'
  - 'Middleware'
  - 'API Gateway'
  - 'Microservices'
  - 'Legacy Systems'
coverImageAlt: 'Infographic showing legacy middleware as a barrier between API traffic from fintechs, third-party providers, the partner ecosystem, and AI agents on one side, and core banking systems on the other, listing the risks of legacy middleware and the solution: modern, scalable, resilient middleware'
updatedDate: '2026-09-15'
ogImage: '/blog-media/infrastructure-will-fail-open-banking-baas/cover.webp'
---

## The Question Nobody Asks

When you hear about an Open Banking project at any financial institution, the first thing people talk about is the APIs, then Consent Management, then Strong Customer Authentication. That makes sense, these are the regulator's requirements.

But in all of these conversations, there is one question almost nobody asks:

> "Is your infrastructure ready for what's coming?"

Not ready for the APIs. Ready for the traffic those APIs will bring in from the partner ecosystem. And that traffic is fundamentally different from anything your infrastructure has handled so far.

## The Forgotten Layer: What Is Middleware, and Why Does It Matter?

Inside every financial institution, there is something like an internal "backbone," known as middleware, or the integration layer. Its job is to create a single, unified layer between all the external channels and the internal core systems.

Behind the scenes, it deals with a genuinely messy reality: some data arrives over REST APIs, some over SOAP services, some straight from databases. Some core systems are very old and speak different protocols entirely. Middleware hides all of that complexity, hands channels a unified contract to work with, and manages security and governance across every access point into the core systems. And for a long time, it did that job well.

![High-level enterprise layered diagram showing channels (banking, partners, and Open Banking modules) connecting through a unified middleware and integration layer down to core banking and data systems](/blog-media/infrastructure-will-fail-open-banking-baas/img1-layered-architecture.webp)

## The Ticking Time Bomb: When Open Banking Arrived

The problem didn't start when the middleware was built. It started when the regulator decided Open Banking was now mandatory.

Suddenly, that same middleware started receiving traffic from outside the institution: from the partner ecosystem, and from third-party providers licensed under Open Banking regulation.

And the difference is enormous. Because now you are not dealing with a person tapping a button on an app. You are dealing with systems and applications calling your APIs directly, around the clock, at a volume that is multiples of whatever your internal channels ever generated.

And do not forget what comes next. Today we are talking about the partner ecosystem and third-party providers, but the near future carries a bigger wave. Institutions will soon have to open these same APIs to AI agents. An AI agent doesn't tap a button and wait, it fires off thousands of requests automatically and continuously. All of this traffic, from partners, from third-party providers, and from AI agents, eventually lands on the very same middleware.

And that old middleware, the giant monolithic box, was never built for this load. It doesn't have the scalability this requires, or the agility to keep up with a partner ecosystem that keeps changing. And any outage in it means everything stops.

## The Compliance Trap: When the Regulator Pushed the Deadline

Eyal Sivan, Head of Strategic Platforms at CIBC (one of Canada's largest banks), makes this point precisely in his talk on Open Banking architecture:

> "In regulated environments, institutions poured all their resources into fixing the API layer, because there was a deadline and the regulator was pushing. But they didn't have the resources left to work on the layers underneath that stack." [1]

This is exactly what happened, and keeps happening, in our region. The institution buys an Open Banking solution, launches its APIs on time, and passes the regulator's compliance check. But the core infrastructure underneath those APIs? Nobody touched it.

And what's worse, and this is something we see often, some of the vendors offering Open Banking solutions build them on top of that same legacy middleware. You end up paying twice: once for the legacy platform, and again for the Open Banking extension bolted on top of it. The result: compliance debt and technical debt, at the same time.

## The Problem Isn't New, It Just Keeps Coming Back Under a Different Name

This pattern has history. Before it was called a "giant middleware," it was called an ESB, an Enterprise Service Bus, and before that EAI, and before that ERP. Every time, the same promise: "give me your spaghetti, and I'll put it in an organized bowl."

As Eyal Sivan describes it:

> "Give me your spaghetti, put it in my giant spaghetti bowl. In reality, what you end up with is just a bowl of spaghetti. It's proprietary, impossible to maintain, a single point of failure, and it doesn't scale." [1]

And according to a Retail Banker International report, Paul Payne, CTO at SaaScada, sums up the problem in one sharp line:

> "A monolith in the cloud remains a monolith." [2]

Moving the problem to a new environment doesn't solve it. And the numbers back this up: more than 55% of banks and large institutions admit that legacy system constraints are the biggest obstacle standing between them and their business goals. [3]

## From the Region: Two Cases We Have Seen

### Case One: When the Bank Caught Itself in Time

A bank in the region was running on legacy middleware from one of the major vendors. When it moved toward Open Banking, it went to the same vendor for an Open Banking solution, an extension installed on top of that same legacy platform. Legacy on top of legacy.

But the difference here is that the bank recognized the problem early: this architecture would not let it scale as its partner ecosystem grew. So it chose a different path entirely, removing the legacy vendor, removing the Open Banking extension on top of it, and building on a modern microservices architecture with an Open Banking solution that supports microservices natively from day one.

### Case Two: When the Bank Paid the Price of Waiting

Another bank in the region was in the exact same position: legacy middleware. Instead of addressing the foundation, it brought in a systems integrator working with the same major vendor to install an Open Banking solution on top of the legacy platform. They spent more than a year and a half trying to make that setup work.

The result? After a year and a half of wasted time and money, they arrived at the conclusion that was possible from day one: this architecture was not the right one. They decided to remove all of the legacy stack and start building a microservices architecture with Open Banking support natively, from scratch.

A year and a half. Right back to square one.

## The Right Path: What Should You Actually Build?

The solution is not some complicated technical secret. But it does require a bold decision that goes beyond "compliance at the lowest possible cost." The right architecture rests on three pillars:

1. **Remove the giant monolithic middleware.** Replace it with a microservices architecture. Every service stands on its own, can scale independently, and a change to one service does not affect the rest.
2. **Add a lightweight perimeter gateway** whose only job is governance and managing external traffic, not business logic, not complex transformation. As Eyal Sivan puts it: "It should be lightweight, not a heavy layer." [1]
3. **Choose a lightweight gateway that supports Open Banking and compliance natively, built in from the start.** Do not pick a lightweight gateway and then bolt an extra layer on top of it for Open Banking, because that just recreates the same problem at a smaller scale. The gateway itself needs native support for Open Banking standards and regulatory compliance from day one.

![Digitinary infographic summarizing the three architecture pillars: replace monolithic middleware with microservices, add a lightweight perimeter gateway for governance, and choose a gateway with native Open Banking and compliance support](/blog-media/infrastructure-will-fail-open-banking-baas/img2-three-pillars.webp)

## Conclusion: Ask the Question Nobody Asks

Before you sign any Open Banking contract, before you start any compliance project, ask one question:

"Is our infrastructure, the middleware and the integration layer, able to absorb the volume of traffic coming from the partner ecosystem?"

If the answer is "we don't know" or "we're building on top of what we already have," you are on one of two paths:

1. You catch the problem early and pay the cost of fixing it now, which is far lower.
2. Or you discover it a year and a half from now, and pay a double price: time, money, and trust.

The choice is yours. But at least now, you know.

### References

1. [Eyal Sivan — "Future Ready Open Banking Architecture" (CIBC)](https://www.youtube.com/watch?v=ULHpbFFUZoY)
2. [Paul Payne, SaaScada — "From monolith to molecular" (Retail Banker International)](https://www.retailbankerinternational.com/comment/why-core-banking-must-evolve/)
3. [Legacy Systems in Digital Transformation: Risks & Challenges](https://www.impactmybiz.com/blog/blog-legacy-systems-digital-transformation-risks-challenges/)
