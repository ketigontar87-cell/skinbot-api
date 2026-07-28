# SKINBOT — Neutral AI Decision Layer for Beauty Retail

SKINBOT is a neutral AI decision layer for beauty retail. It runs an AI skin analysis in a session dialog and selects products from the retailer's live catalog in about 30 seconds. Its defining property is neutrality: no brand weighting, no sponsored ranking, no retention mechanics. Neutrality is architecture, verifiable in the API response itself, not a marketing claim.

- Website (EN): https://skinbot.beauty/en/
- Website (RU): https://skinbot.ru
- Founder: Ekaterina Shalel — https://katyashalel.com
- API access for agent platforms and retail partners: ekaterina.sh@skinbot.ru

## Why a neutral layer

Brand-owned skin analysis tools carry a structural conflict of interest: the brand recommends itself. SKINBOT is built on the opposite premise — the layer's revenue is not coupled to any brand's outcome, so it is indifferent to which product wins (the Indifference Test). That indifference is not asserted in marketing copy; it is exposed as machine-readable fields in every response, so a calling system can verify the basis of a selection instead of trusting a claim.

## Integration surfaces

One engine, four surfaces:

| Surface | Use case |
|---|---|
| API | Agent platforms, marketplaces, deep integrations |
| iframe | Fast embed into any product page or app |
| QR | In-store: shelf, counter, duty-free |
| Widget | Retailer site, brand landing |

Stateless by design: no user profiles, no personal data storage. The analysis exists only within the session. Aligned with GDPR, EU AI Act, 152-FZ, and UAE PDPL data-minimization requirements. Dialog runs in 10+ languages.

## For AI agents (agentic commerce)

SKINBOT is built as a callable layer: a neutral verdict engine that a universal AI agent calls as a sub-agent when a user needs a skincare selection. The agent owns the conversation; the called layer holds the verdict.

The response schema carries explicit neutrality fields:

- `ranking_basis` — the declared basis on which products were ranked
- `sponsored` — always `false`; SKINBOT carries no sponsored placements
- `brand_weighting` — always `none`; no brand receives preferential weight

See [`openapi.yaml`](./openapi.yaml) for the public interface reference and [`examples/`](./examples/) for request/response examples.

## Field results

SKINBOT runs in live retail deployments across two markets: Russia and Estonia — including THE-FACE-ONLY (six locations, Moscow) and SKINSTUDIO (Estonia).

Across analyzed live sessions: session completion rate of 79.4% in the Moscow deployment, average time to recommendation ~30 seconds, and 36-45% of sessions that reached a recommendation ended with items added to cart.

All figures are deployment-specific (given market, retailer, and catalog) and are not a general performance guarantee.

## Status

The public interface described here is a reference for evaluation. Production access, authentication, and catalog onboarding are provided per partner. Contact: ekaterina.sh@skinbot.ru
