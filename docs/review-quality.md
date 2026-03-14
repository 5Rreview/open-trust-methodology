# Review Quality Scoring

A five-metric model that evaluates how useful and trustworthy a review is, producing a score from 0 to 100.

## Important Rule

Quality score does **NOT** affect a company's position in search results ([Sacred Rule #1](sacred-rules.md)). It is used only for:
- Moderation prioritization
- Internal analytics
- Reviewer feedback (helping users write better reviews)
- Minor weight contribution to trust score (higher quality = slightly more influence)

## The Five Metrics

### 1. Specificity

Does the review contain concrete, verifiable information?

**Higher scores for reviews that include:**
- Numbers, dates, timeframes
- Monetary amounts and pricing
- Specific feature or product names
- Direct quotes from interactions
- Measurable outcomes

**Lower scores for:**
- Vague language ("great service", "very good", "highly recommend")
- Generic statements without supporting detail
- Absence of any quantitative data

### 2. Humanity

Does the review sound like it was written by a real person?

**Higher scores for:**
- Colloquial language and natural expressions
- Varied sentence structure and rhythm
- Personal anecdotes and specific experiences
- Genuine emotional nuance

**Lower scores for:**
- Language patterns characteristic of AI generation
- Uniform, robotic sentence rhythm
- Overly formal or marketing-like tone

### 3. Helpfulness

Does the review help other users make decisions?

**Higher scores for:**
- Sufficient detail and length
- Structured pros and cons
- Aspect-specific ratings
- Comparisons with alternatives
- Experience dates and context

**Lower scores for:**
- Very short reviews with minimal content

### 4. Readability

Is the review easy to read and understand?

**Higher scores for:**
- Natural sentence length variety
- Clear paragraph structure
- Use of formatting (lists, sections)

**Lower scores for:**
- Extremely long or extremely short sentences
- Monotonous structure (all sentences the same length)
- Single wall of text without breaks

### 5. Credibility

What verification supports the review?

**Higher weight for:**
- Verified purchases (transaction confirmed)
- Registered users with history
- Media attachments (photos, screenshots)
- Multiple verification signals

**Lower weight for:**
- Unverified or imported content
- No supporting evidence

## Grading

| Grade | Score | Meaning |
|-------|-------|---------|
| A | 90-100 | Exceptional — detailed, specific, genuinely helpful |
| B | 80-89 | Good — useful content with solid detail |
| C | 70-79 | Acceptable — some detail, room for improvement |
| D | 60-69 | Below average — mostly vague |
| F | < 60 | Low quality — minimal decision-making value |

## Multi-Language Support

Quality scoring is calibrated per language to account for:
- Different average review lengths across cultures
- Varying writing conventions and formality norms
- Language-specific NLP accuracy differences
- Cultural rating tendencies (conservative vs. polarized)

Currently calibrated for 20 locales.
