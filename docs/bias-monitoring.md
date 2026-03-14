# Bias Monitoring

How the 5R Trust platform monitors and mitigates bias in trust scoring across languages, cultures, and industries.

## The Problem

Trust scoring can introduce systematic bias through multiple channels:
- **Language bias** — NLP tools perform differently across languages
- **Cultural bias** — rating norms differ (conservative vs. polarized cultures)
- **Industry bias** — some industries naturally receive more extreme reviews
- **Volume bias** — companies with more reviews get more stable scores
- **Detection bias** — AI phrase lists may have different sensitivity per language

## Per-Language Calibration

The platform supports 20 locales. Each locale has calibrated scoring parameters:

- **Rating normalization** — adjusting for cultural rating tendencies (e.g., some cultures rate conservatively, others polarize between 1 and 5 stars)
- **Quality score normalization** — accounting for language-specific NLP accuracy
- **Length calibration** — adjusting review length expectations per language (compact vs. verbose languages)

### Known Challenges

| Language Group | Challenge | Mitigation |
|---------------|-----------|------------|
| CJK (Chinese, Japanese, Korean) | No spaces between words; character-based | Character-based metrics instead of word-based |
| Arabic, Hebrew | Right-to-left; complex word boundaries | Specialized text processing |
| Thai | No spaces between words | Language-specific tokenization |
| Low-resource languages | Limited NLP model coverage | Conservative scoring, wider confidence intervals |

## Fairness Metrics

The platform tracks these metrics across locale segments:

| Metric | What it measures | Goal |
|--------|-----------------|------|
| Score distribution per locale | Are scores systematically higher/lower for certain languages? | Uniform distribution |
| Detection rate per locale | Are fake reviews detected more/less in certain languages? | Proportional detection |
| Quality grade distribution | Are certain languages graded more harshly? | Consistent grading |
| False positive rate | Are genuine reviews flagged more often in certain languages? | Minimize disparity |

## Industry Fairness

Different industries have different review profiles:
- **High-emotion industries** (restaurants, travel) — more polarized ratings
- **Technical industries** (SaaS, B2B) — more moderate, detail-oriented reviews
- **Service industries** (healthcare, legal) — fewer reviews, privacy concerns

The scoring model accounts for these differences through industry-specific calibration of time decay and confidence thresholds.

## Continuous Monitoring

Bias monitoring is an ongoing process:
1. **Collect** — aggregate scoring data across locale and industry segments
2. **Compare** — identify statistical deviations between segments
3. **Investigate** — determine if deviations represent genuine differences or systematic bias
4. **Calibrate** — adjust parameters when bias is identified
5. **Validate** — confirm that calibration improved fairness without reducing accuracy

## Transparency

- Calibration parameters are reviewed periodically
- Significant methodology changes are documented in the [CHANGELOG](../CHANGELOG.md)
- Community feedback on perceived bias is welcomed through GitHub issues
