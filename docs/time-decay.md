# Time Decay

Old reviews gradually lose influence on trust scores. This ensures that companies can recover from past problems and that current service quality is reflected accurately.

## Why Decay?

Without time decay, a rating becomes a life sentence. A company that had terrible service years ago but improved dramatically would still carry the weight of old negative reviews. This discourages improvement and makes trust scores inaccurate.

## Approach: Exponential Decay

We use exponential decay — the most natural model for diminishing relevance over time:

- **Recent reviews** carry full weight
- **Older reviews** carry progressively less weight
- The decay is smooth and continuous, not step-based

### Industry Tuning

Different industries change at different rates. The decay curve is tuned per industry category:

| Industry Type | Decay Speed | Rationale |
|---------------|-------------|-----------|
| Fast-changing (restaurants, hotels) | Faster | Staff and management change frequently |
| Medium-changing (retail, e-commerce) | Standard | Product lines and service evolve |
| Slow-changing (SaaS, professional services) | Slower | Core product evolves gradually |

## Decay Does NOT Mean Deletion

Old reviews remain fully visible and readable. Only their mathematical contribution to the trust score decreases. Users can still read and find every review ever written.

## Interaction with Volume

A company with many reviews (spanning years) and a company with few reviews (all recent) are treated differently:

- **High volume + decay** = stable, confidence-weighted score
- **Low volume + decay** = score may fluctuate more, displayed with lower confidence

## Edge Cases

**Company with only old reviews:**
When all reviews have aged significantly, the trust score displays a "limited recent data" indicator rather than showing a potentially misleading number.

**Sudden review burst after long silence:**
Handled by the [Company Abuse Protection](integrity.md#company-abuse-protection) mechanism — unusual spikes trigger investigation regardless of whether reviews are positive or negative.
