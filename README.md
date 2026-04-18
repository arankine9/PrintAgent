# PrintAgent

# Statement of Work: Printing Company Sales Assistant Chatbot

**Date:** 4/17/26
**Version:** 1.0
**Client:** Premier Printing Solutions

## 1. Overview

This project delivers a conversational assistant that handles the buying process end to end: identifying what the customer needs, collecting specs in plain language, validating artwork, generating a quote, and handing off to checkout. The goal is to reduce sales team load on routine quotes and convert more first-time visitors without requiring them to already understand print terminology.

## 2. Objectives

- Let a non-expert customer go from "I need something printed" to a valid order in one conversation
- Deflect routine quote and spec questions away from the sales inbox
- Keep quote accuracy within a defined tolerance of the current pricing engine
- Surface order status information without requiring a login lookup
- Hand off cleanly to a human when the bot is out of its depth

## 3. Scope of Work

The chatbot will handle the following flows:

**Product discovery.** Ask clarifying questions to identify the product category (cards, large format, marketing collateral, signage, etc.) when the customer isn't sure what to call what they need.

**Spec collection.** Walk the customer through quantity, size, paper stock, finish, color mode, and sided-ness using plain language with explanations available on request. Defaults offered where sensible.

**Artwork handling.** Accept file uploads, run basic preflight checks (resolution, bleed, color mode, page count), and flag issues with clear guidance on how to fix them. Offer a "I don't have a file yet" branch that routes to design services or templates.

**Quote generation.** Pull live pricing from the existing pricing engine or MIS and return an itemized quote with turnaround options.

**Order placement.** Collect shipping details, turnaround preference, and hand off to the existing checkout and payment flow. The bot does not process payment directly.

**Order status.** Look up existing orders by order number and email, return current production stage and estimated ship date.

**Human escalation.** Detect frustration, complex custom jobs, or unsupported intents and route to a live sales rep with full conversation context.

## 4. Deliverables

1. Requirements document and conversation flow diagrams
2. Trained chatbot deployed to [staging + production]
3. Web widget embed (responsive, mobile-friendly)
4. Admin dashboard for reviewing conversations, tuning intents, and exporting transcripts
5. Integration with [ecommerce platform / MIS / CRM]
6. Preflight file validation service
7. Technical documentation and admin training session
8. 30 days of post-launch support

## 5. Technical Approach

- LLM-backed conversational agent with retrieval over the product catalog, pricing rules, and FAQ content
- Stateful conversation memory scoped per session, with optional persistence for returning customers
- Preflight checks run on uploaded files server-side before quote generation
- Integration points: website (embed widget), pricing engine / MIS, order management system, email/SMS for handoff notifications
- Admin dashboard hosted on [Vendor infra or Client infra, TBD]
- Guardrails: bot never quotes outside the configured pricing rules, never commits to turnaround times the MIS hasn't confirmed, never promises discounts

## 6. Timeline

| Phase | Duration | Outcome |
|---|---|---|
| 1. Discovery and requirements | 2 weeks | Signed-off requirements, flow diagrams, intent list |
| 2. Design and prototype | 3 weeks | Clickable prototype, happy-path demo |
| 3. Build and integration | 4-6 weeks | Feature-complete bot in staging |
| 4. Testing and UAT | 2 weeks | Passing test suite, client sign-off |
| 5. Launch and training | 1 week | Production launch, admin team trained |
| 6. Post-launch support | 4 weeks | Bug fixes, tuning, transition to maintenance |

Total: approximately 16-18 weeks from kickoff.

## 7. Assumptions

- Client provides complete product catalog, pricing logic, and turnaround rules at kickoff
- Client provides sandbox or test credentials for the MIS, ecommerce platform, and any other systems we integrate with
- Client designates a single point of contact for approvals and weekly reviews
- Brand assets, tone guidelines, and FAQ content are available in usable form
- Client handles legal review of any bot disclosures (privacy, terms, AI disclosure)

## 8. Out of Scope

- Custom graphic design or artwork creation for customers
- Payment processor setup or PCI work
- Rebuilding or replacing the existing website, MIS, or pricing engine
- Languages beyond English (can be added via change order)
- Voice or phone channel (web chat only at launch)
- Physical kiosk or in-store deployment

## 9. Pricing and Payment

**Option A: Fixed fee.** $[X] total, billed [30/40/30] across kickoff, midpoint, and launch.

**Option B: Time and materials.** $[Y]/hour, estimated [Z] hours, not to exceed $[cap] without written approval.

Post-launch support beyond the included 30 days: $[rate]/month retainer or $[hourly rate] T&M.

## 10. Acceptance Criteria

- Chatbot correctly identifies and handles the top 15 intents with at least 90% accuracy on a held-out test set
- Generated quotes match the pricing engine within [1%] on all test cases
- End-to-end happy path completes without escalation on all configured product categories
- Preflight flags correctly identify the defined failure cases (low DPI, missing bleed, wrong color mode)
- Handoff to human agent delivers full conversation context in under [30 seconds]
- Admin dashboard documentation delivered and training session completed

## 11. Change Management

Any change to scope, deliverables, or timeline is handled through a written change order signed by both parties before work begins. Minor clarifications inside the agreed scope do not require a change order.

## 12. Signatures

**[Client Name]**
Name: ___________________________
Title: ___________________________
Date: ___________________________

**[Vendor Name]**
Name: ___________________________
Title: ___________________________
Date: ___________________________

---

Swap the bracketed placeholders for real names, pricing, and integration targets. If you want a version tailored to a specific client (Hoffman, Papé, or a new one), tell me the specifics and I'll cut it down.
