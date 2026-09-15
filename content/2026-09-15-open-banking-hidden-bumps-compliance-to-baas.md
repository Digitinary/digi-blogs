---
title: 'The Hidden Bumps in Open Banking Implementation: From Compliance to Banking-as-a-Service'
subtitle: 'Compliance was never the finish line. Here are the three hidden bumps institutions hit on the way to a real Banking-as-a-Service platform, and the question worth asking before you build.'
author: 'Salah Abu-Msameh'
authorRole: 'Founder & CEO, Digitinary'
authorBio: 'Founder of Digitinary, focused on digital transformation, APIs, and Open Banking / Finance across the region''s financial and enterprise companies.'
date: '2026-09-15'
excerpt: 'Becoming Open Banking compliant is not the finish line, it is where a bigger challenge starts. Here are the three hidden bumps institutions in the region keep hitting on the way to Banking-as-a-Service.'
coverImage: '/blog-media/open-banking-hidden-bumps-compliance-to-baas/cover.webp'
tags:
  - Open Banking
  - Banking-as-a-Service
  - API Platform
  - MENA
featured: false
slug: 'open-banking-hidden-bumps-compliance-to-baas'
seoTitle: 'The Hidden Bumps in Open Banking Implementation'
seoDescription: 'Compliance is not the finish line for Open Banking. See the three hidden bumps institutions hit on the way to a real Banking-as-a-Service platform.'
seoKeywords:
  - 'Open Banking'
  - 'Banking-as-a-Service'
  - 'API Platform'
  - 'Developer Portal'
  - 'MENA'
coverImageAlt: 'The hidden challenges in Open Banking implementation: from compliance components to Banking as a Service, the roadblocks banks do not see coming'
updatedDate: '2026-09-15'
ogImage: '/blog-media/open-banking-hidden-bumps-compliance-to-baas/cover.webp'
---

Many financial institutions believe they've "made it" once they launch their first API and become compliant with Open Banking requirements.

The truth? That stage was never the finish line. It was the start of a bigger challenge.

Through our work with a number of financial institutions in the region, we've noticed a recurring pattern: an institution starts implementing Open Banking, believes it has laid the foundation, then finds itself months later facing a sprawling mix of separate tools, multiple vendors, and mounting costs.

This article maps out these bumps before you hit them.

The global Open Banking market reached **$31.6 billion in 2024**, and is expected to exceed **$135 billion by 2030**. The institutions building it correctly today are the ones that will capture this growth. [1]

![Global Open Banking market growing from $31.6 billion in 2024 to more than $135 billion by 2030](/blog-media/open-banking-hidden-bumps-compliance-to-baas/global-open-banking-market-2024-2030.webp)

## Problem One: Patching Legacy Systems

Internal API management (internal middleware) has existed in most banks for years. When the decision came to implement Open Banking, the natural call was: "let's build on it."

But legacy API management wasn't built to Open Banking standards. **OAuth 2.0** and the idea of a **consent flow**, explicit customer approval before sharing their data, are new concepts for legacy solutions (systems built more than 15 years ago). **OIDC**, **FAPI profiles**, and **Dynamic Client Registration** were never on that solution's roadmap to begin with.

The result: constant patching. Patches on top of patches.

From our direct experience in the market, some banks in the region needed more than **8 months** just to become compliant, and some took **a year and a half**. Not to build a product, not to generate revenue, just to comply with regulatory requirements.

The reasons for this long timeline are clear: every new requirement runs into the wall of legacy architecture. There's no native support, only workarounds. And every workaround creates a new workaround. Literally, we bring in a solution and keep patching it to force-fit something it was never built for.

## Problem Two: Building In-House — When Innovation Pays the Price of Compliance

Another common scenario in the region: an institution decides not to rely on an external vendor, and decides to build the Open Banking component itself, from scratch. On the surface, the reasoning sounds logical: "we have a team, we'll build it ourselves, we'll have full control."

This decision isn't necessarily wrong. In a very small number of cases, in-house development was a genuine strategic choice: an institution built a fully integrated system, took full ownership, and came out with a real competitive advantage. But these cases are a rare exception, not the rule.

In the vast majority of cases we've seen, what actually happened?

The engineering team, the one that was supposed to be working on the products that set the institution apart from competitors, ended up spending months implementing OAuth 2.0, building consent management, applying FAPI security profiles, and writing integrations with the core banking system.

That's compliance work, not innovation.

And here's the fundamental problem: **Open Banking compliance is not a differentiator**. Every bank in the market will implement it, to the same standards, under the same regulatory requirements. No customer is going to choose a bank because it "built a nicer consent management screen than the others."

> **Note:** You spent your team's energy building something you could have bought, and lost the time you could have spent building something you couldn't buy.

And when you later need to add a developer portal and a monetization engine, the same question comes back: build from scratch again?

## Problem Three: Fragmentation Toward BaaS — When the Platform Itself Becomes the Problem

The most ambitious institutions, the ones that want to build **Banking-as-a-Service** and become financial infrastructure for others, will discover they need far more than just compliance. They need a complete **API platform**.

The components a real API platform needs:

- **Monetization Engine** — API pricing, subscription tiers, consumption tracking, billing.
- **Developer Portal** (Developer Experience) — a fully integrated portal for every TPP and business partner, with no manual work in onboarding or access management.
- **Self-Onboarding** — a complete developer journey with no human intervention.
- **API Guide / API Playbook** — live, interactive documentation, a complete API reference, an environment where a developer can understand and try the API directly.
- **Sandbox** — a real test environment that accurately mirrors the production APIs: same endpoints, same flows, same authentication. A sandbox that's disconnected from production becomes a barrier for every TPP that wants to build on you.
- **Observability** — full visibility into every API call, every TPP, every subscription.
- **Policy Management** — rate limiting, SLA per TPP, consumption quotas, and complete access-policy management.
- And more components and functions that need to be native and integrated, not a collection of separate solutions.

All of these components are necessary. But this is where the real problem starts.

In practice, once an institution starts assembling these components, it finds itself facing a fragmented system. A common shape this takes:

- **Internal API Middleware**: a legacy solution from Vendor A, in place for years.
- **External Open Banking & API Management**: from a different vendor, or the same legacy solution patched to support Open Banking.
- **Monetization Engine**: usually a different vendor again, needing custom integration with the gateway since it doesn't automatically know its data.
- **Developer Portal**: sometimes from the same legacy middleware (not ready for a TPP ecosystem), sometimes a separate Vendor D.
- **Documentation / API Playbook**: from yet another vendor, outdated content, manual sync with the gateway, never automatically linked to updates.

## What Are the Real Consequences of This Fragmentation?

### First: Blurred Responsibility

With every incident or issue, the first question becomes: is this the gateway's responsibility? The Open Banking component's? The monetization engine's? The gray area between vendors causes delays in fixes and conflicting accountability.

### Second: Artificial Integration Between Tools

The monetization engine doesn't automatically know the API gateway. The developer portal is separate from the API catalog, meaning either constant manual syncing or ongoing documentation drift, where the docs stop reflecting the actual APIs. The statistics back this up: **67% of cross-border fintech projects in 2024 suffered delays due to API incompatibility**. [2]

### Third: High Cost, on Two Levels

A license for every tool, and an implementation cost for every integration. Every new tool you add means a new integration to build. Enterprise Open Banking API development costs between **$100K and $500K+**, and once you multiply that by the number of integrations needed between different tools, the picture becomes clear.

### Fourth: The Reality of Developer Portals in the Region

From our visits to a number of institutions in the region, especially in Saudi Arabia and Jordan, we've seen developer portals that don't reflect the institution's real ambition: static pages, outdated documentation, a modest developer experience. Not because the institution doesn't care, but because the portal is the product of patching, not of a strategic decision.

![Example of a bank's Open Banking developer portal in the region: an API product catalog with subscription plans](/blog-media/open-banking-hidden-bumps-compliance-to-baas/developer-portal-api-catalog-example.webp)

![Example of a bank's Open Banking developer portal documentation, showing an account information API specification](/blog-media/open-banking-hidden-bumps-compliance-to-baas/developer-portal-documentation-example.webp)

> **Note:** This doesn't mean there are no success stories, but most fall short of expectations and don't reflect the institution's real ambition.

## The Recommendation — For Institutions Still Evaluating

If your institution is still in the planning or evaluation stage, this is the most valuable moment to act.

**First:** look for a solution built **Open Banking native**, not a solution built as a general API gateway and later "adapted" to support Open Banking. The difference isn't just technical, it's a difference in the underlying architecture, in time-to-compliance, and in total cost of ownership.

**Second:** if your ambition goes beyond compliance, if your goal is BaaS, embedded finance, or turning APIs into a revenue source, you need a **platform**, not a gateway. And the platform decision has to be made from day one, not partway through.

Banks offering BaaS can increase their revenue by **20 to 30%** through infrastructure usage fees, but that requires a real platform, not a collection of assembled tools.

Changing course midway is expensive. More expensive than you'd expect.

## Conclusion: The Question Worth Asking

So, what's the ideal solution?

What if there were a single solution that gave you all of this out of the box:

- **Native Open Banking Support** — built on OAuth 2.0 / OIDC / FAPI from the ground up, not bolted on later.
- **Consent Management** — built in from the start, no separate vendor needed.
- **Monetization Engine** — pricing, billing, and subscription management, ready to go.
- **Developer Portal** — modern, interactive, automatically connected to the API catalog.
- **Observability** — full visibility into every API call, every TPP, every subscription.
- **Self-Onboarding** — a complete developer journey with no human intervention.

The question worth pausing on: is there a tool that genuinely does all of this natively, instead of being assembled from multiple vendors? That's the right question for any institution evaluating its options today.

### References

1. [Grand View Research, Open Banking Market Size Report 2024-2030](https://www.grandviewresearch.com/horizon/outlook/open-banking-market-size/global)
2. SAMi / MindFront Solutions, API Fragmentation Report 2024
3. [Wasl API Platform, A Unified Holistic API Platform with Open Banking Native Support](https://digitinary.com/wasl)
