# Integrity & Detection

A multi-level detection pipeline that identifies manipulated reviews without false-positive censorship.

## Philosophy

- Detection does **not** automatically block publication
- Only high-confidence detections are flagged for human moderator review
- Weight reduction is preferred over deletion — neutralizes manipulation without confrontation
- The system operates autonomously without AI dependencies; AI analysis is an optional enhancement

## Approach: Weight Reduction Over Deletion

| Approach | Problem |
|----------|---------|
| Delete suspicious reviews | Creates conflict, legal risk, user frustration |
| Reduce weight silently | Neutralizes manipulation without confrontation |

The review stays visible, but its influence on the trust score is minimized. The reviewer doesn't know their weight was reduced, removing the incentive to create a new account and try again.

## Level 1 — Rule-Based Detection (Instant)

Runs on every review submission. Produces a risk score based on multiple independent signals.

### AI Fingerprint Detection

AI-generated reviews share characteristic phrases and structural patterns. We maintain curated phrase lists per language (currently covering 20 locales) and update them regularly.

**What we detect:**
- Phrases characteristic of large language model output
- Overuse of superlatives and generic praise without specifics
- Marketing-like language patterns
- Language patterns that differ between human and AI writing

### Structural Analysis

AI and template-based reviews show measurable structural uniformity:
- **Sentence rhythm** — genuine reviews have natural variation in sentence length; AI-generated text tends toward uniformity
- **Organization patterns** — artificially perfect structure (intro-body-conclusion) is uncommon in genuine reviews
- **Sentence complexity** — unnaturally long or uniform sentences are flagged

### Duplicate Detection

Multiple methods to catch copied content:
- **Exact matching** — hash-based comparison for identical content
- **Fuzzy matching** — similarity analysis for near-duplicate reviews
- **Cross-subject detection** — identifying the same review text applied to different companies

### Behavioral Analysis

Signals based on how the review was submitted:
- **Submission timing** — unusually fast writing relative to review length
- **Network patterns** — multiple reviews from the same source in a short period
- **Account patterns** — new accounts with suspicious first-review behavior
- **Session analysis** — limited platform interaction before review submission

### Technical Markers

Detection of invisible characters and encoding artifacts sometimes inserted by automated tools.

### Sentiment Consistency

Cross-checking whether the rating matches the sentiment expressed in the review text.

## Level 2 — AI-Enhanced Analysis (Optional)

When Level 1 produces a medium-risk or higher score, an optional AI analysis can be triggered asynchronously. This is a supplementary signal — the system never depends on it for decisions.

**Evaluates:**
- Authenticity probability
- Specific reasons for concern
- Confidence level of the assessment

> Level 2 is not required for system operation. All production decisions can be made on Level 1 alone.

## Risk Levels

Reviews are categorized by risk level, each with appropriate automated actions:

| Level | Action |
|-------|--------|
| Critical | Held for immediate moderator review, minimal scoring weight |
| High | Flagged for moderator review, significantly reduced weight |
| Medium | Soft flag, reduced weight, optional AI analysis |
| Low | Minor weight reduction, noted in admin |
| Clean | No action, full weight |

## Signal Categories

Each detection produces categorized signals for transparency:

1. **Language patterns** — AI-characteristic phrases and structure
2. **Content duplication** — exact, fuzzy, and cross-subject matches
3. **Behavioral signals** — timing, network, and account anomalies
4. **Technical markers** — encoding artifacts and invisible characters
5. **Consistency checks** — rating vs. sentiment alignment
6. **AI analysis** — optional Level 2 assessment

## Company Abuse Protection

When a company receives an unusual spike of reviews (positive or negative), the system uses statistical change detection to identify anomalous patterns:

- Trust score is temporarily paused during investigation
- A message indicates unusual activity has been detected
- Reviews during the anomaly period receive reduced weight
- Normal scoring resumes after review by moderator or after the pattern normalizes

This protects companies from coordinated campaigns while preserving genuine reviews.
