# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

- **Recruiters and hiring managers** opening a link from a CV, usually on a laptop, sometimes on a phone. They have
  1-3 minutes and are deciding whether the author can turn a business problem into a working, safe system.
- **Technical interviewers** going deeper before or during an interview: architecture, failure handling, trade-offs.

## Product Purpose

A one-page portfolio case study of a platform the author (GitHub `the3ma`) designed and built as architect and
full-stack engineer: it connects an online retailer's Shopify store to a wholesale game-key distributor, keeps the
catalog and prices in sync, buys a key for every paid order (and for scheduled bulk purchases), and delivers it to the
customer through a secure portal, with a full audit trail. Success = the visitor leaves convinced the author
understands the business, makes deliberate decisions, and builds systems that do not lose money, and knows how to
get in touch.

## Positioning

The story is told through failure modes, not features: every decision starts from a money or trust risk (a key bought
twice, a silent supplier, a redelivered webhook, a leaked key) and shows the mechanism that removes it.

## Operating Context

- Linked from a CV and the author's GitHub profile; hosted on GitHub Pages
  (`https://the3ma.github.io/game-key-platform-case-study/`).
- Read top to bottom on first visit; skimmed by section on return or in an interview.

## Capabilities and Constraints

- Static HTML + CSS, no build step; inline SVG diagrams; small inline JS only for the theme toggle.
- **Anonymized:** the client, the supplier, domains and infrastructure providers are never named. Technology names
  (NestJS, Vue, PostgreSQL, Redis/BullMQ, Shopify, Docker, GitHub Actions) are allowed. The source repo is private.
- Terminology: retailer, key distributor / supplier, store, key, operation, bulk order, key storage, audit log.

## Brand Commitments

- Header label is the product purpose, not the author handle: "Game-key fulfilment platform · case study".
- Black-and-white palette with exactly one accent colour; a white theme and a black theme with a visible toggle that
  follows the system setting until the visitor chooses.
- Contact: the3ma@gmail.com, github.com/the3ma.

## Evidence on Hand

- Source documentation (private repo, read 2026-11-02): README, design README, `critical-paths.md` (risk tiers),
  admin `PRODUCT.md` (staff and finance jobs), backend README (queues, buying-keys-safely rules, bulk operation
  states), two draw.io files (architecture C4 pages, application flows).
- Usable as facts: system figures stated in the docs (e.g. 30 s supplier timeout, email retry 30 s doubling over 8
  attempts about 2 h, queue unavailable after 3 s falls back to a direct send, 12 queues, nightly backup, hourly
  health check, Redis alert at 70% memory, re-queue of pending keys after 10 min by a 30-min sweep).
- **Absent, must not be fabricated:** user research, interviews, business metrics (order volumes, revenue, time
  saved, error rates), testimonials, client names. "Discovery" and "research" are reconstructed from the docs'
  risk ranking and user jobs and must be presented as such.

## Product Principles

1. Lead with the business risk, then the mechanism, then the evidence.
2. Every claim is traceable to the source docs; no invented numbers.
3. Skimmable in one minute, deep enough for an interview.
4. Anonymity is non-negotiable.

## Accessibility & Inclusion

WCAG 2.1 AA: contrast in both themes, keyboard access to every control and scrollable diagram, text alternatives for
every diagram, reduced-motion support.
