# Trust Score Calculation

The trust score is a single number (0-100) representing how trustworthy a company is, based on all available signals.

## Approach: Bayesian Averaging

We use Bayesian averaging with a neutral prior to calculate the base trust score. This approach:

- **Prevents cold-start manipulation** — a company with 3 fake 5-star reviews doesn't get a perfect score
- **Converges to true value** — as more reviews accumulate, the prior's influence diminishes
- **Handles sparse data gracefully** — companies with few reviews show a score closer to neutral

Without Bayesian averaging, 3 fake reviews could give a company a perfect rating. With our approach, the score remains conservative until sufficient evidence accumulates.

## Input Signals

The trust score combines multiple weighted signals:

| Signal | Source |
|--------|--------|
| Weighted review ratings | Reviews weighted by [reputation](reputation-weight.md) and [recency](time-decay.md) |
| Response rate | How actively the company responds to reviews |
| Resolution rate | Percentage of reported issues resolved |
| Review volume | Statistical confidence from total review count |
| Review quality | Average [quality score](review-quality.md) of reviews |

Signal weights are dynamic — they adjust based on available data. A company with few reviews weights volume differently than a company with hundreds.

## Confidence & Ranking

For ranking and comparison, we use the Wilson Score Lower Bound — a statistical method that answers: "given the reviews we have, what is the worst this company could plausibly be?"

This means:
- A company with 50 solid reviews at 4.2 ranks higher than a company with 3 reviews at 5.0
- Confidence grows with review count and diversity
- The displayed score reflects the *likely minimum*, not just the average

### Confidence Display

| Reviews | Confidence | Display |
|---------|------------|---------|
| Very few | Low | "Not Yet Rated" — score hidden |
| Some | Medium | Score shown with confidence range |
| Many | Good | Score shown, smaller range |
| Extensive | High | Score shown, high confidence |

## Score Ranges

| Range | Label | Meaning |
|-------|-------|---------|
| 90-100 | Excellent | Consistently high-quality service |
| 75-89 | Good | Generally positive with minor issues |
| 60-74 | Average | Mixed reviews, some concerns |
| 40-59 | Below Average | Significant issues reported |
| 20-39 | Poor | Many unresolved complaints |
| 0-19 | Critical | Serious trust concerns |

## What Does NOT Affect the Score

- Whether the company pays for premium features
- The company's size or age
- The industry or category
- Advertising spend on the platform
- Any business relationship with the platform

This is [Sacred Rule #1](sacred-rules.md).
