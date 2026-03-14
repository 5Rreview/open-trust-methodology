# Sacred Rules

These are inviolable principles that govern the 5R Trust platform. No business decision, revenue target, or partnership agreement can override them.

## The Rules

### 1. Ranking Independence

A company's trust score, search position, and visibility are **never** influenced by payment status. Premium features provide analytics and tools — never ranking advantages.

```
Paid features = Tools (analytics, CRM, response tools, branding)
Free features = Trust (ranking, reviews, scores, search results)
```

### 2. No Silent Deletion

Reviews are never quietly removed. When a review's influence needs to be reduced:
- Weight reduction is preferred over removal
- If removal is necessary (legal, policy violation), the reviewer is notified
- Moderation decisions are logged and auditable

### 3. Right to Respond

Every reviewed entity has the ability to publicly respond to any review. Responses are visible to all users and factor into the trust score calculation (response rate).

### 4. Resolution Visibility

When a company resolves an issue raised in a review:
- The resolution is shown publicly on the review
- The reviewer can update their rating
- Resolved issues improve the company's trust profile
- The resolution rate is a visible metric

### 5. AI Transparency

- AI-generated content is always labeled
- AI-detected manipulation is flagged (not silently applied)
- The detection methodology is published (this repository)
- Users can see why a review was flagged

## Separation Architecture

The platform maintains strict separation between:

| Trust Layer | Business Layer |
|-------------|----------------|
| Ranking algorithm | Analytics dashboard |
| Review scoring | CRM tools |
| Trust score | Response management |
| Search results | Branding features |
| Fake detection | Competitor comparison |

No data flows from the Business Layer into the Trust Layer. A company's use of paid tools never generates signals that affect scoring. See [Separation Architecture](separation-architecture.md) for details.

## Priority Hierarchy

When any decision creates a conflict between stakeholders:

```
User Trust  >  Company Satisfaction  >  Revenue
```

This means:
- If showing a negative review hurts a paying company but helps users — show the review
- If a detection rule creates false positives — tune the rule, don't disable it
- If revenue would increase by relaxing detection — never relax detection

## Enforcement

These rules are enforced through:
1. **Code architecture** — trust and business modules are physically separated
2. **Code review** — changes to trust logic require additional review
3. **Public documentation** — this repository serves as a public commitment
4. **Audit trail** — all scoring and moderation decisions are logged
