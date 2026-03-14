# Community Correction

Users collectively improve review accuracy through flagging and voting mechanisms.

## How It Works

Users can mark any review with one of four signals:

| Signal | Meaning | Effect |
|--------|---------|--------|
| Helpful | This review helped me make a decision | Increases review weight |
| Misleading | This review contains inaccurate information | Triggers moderator review at threshold |
| Suspicious | This review looks fake or paid | Feeds into detection signals |
| Outdated | This information is no longer accurate | Reduces time decay weight further |

## The Correction Loop

```
Community detects issue
    → Algorithm reduces impact
        → Company responds
            → Users update experience
                → Trust score adjusts
```

This creates a self-correcting system where:
1. Low-quality reviews lose influence through community signals
2. Companies have incentive to resolve issues (improves their score)
3. Users see resolution and can update their reviews
4. The trust score reflects the current state, not just the past

## Aggregation

Community signals are aggregated, not individual:
- A single flag does not trigger action
- Multiple independent flags from diverse accounts trigger review
- Flags from high-reputation users carry more weight than flags from new accounts

This prevents a single bad actor from manipulating the correction system.

## Why Not Just Delete?

| Action | Problem |
|--------|---------|
| Delete flagged reviews | Censorship concerns, Streisand effect |
| Reduce weight based on flags | Organic, community-driven, conflict-free |

Community correction complements algorithmic detection. The algorithm catches patterns; the community catches nuance that algorithms miss.
