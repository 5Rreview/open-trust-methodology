# 🔐 Privacy & Data Handling

How the 5R★ platform handles personal data in the context of trust scoring and review management.

## Legal Basis

Review processing operates under **GDPR Article 6(1)(f) — Legitimate Interest**. The platform has a legitimate interest in:
- Providing accurate trust information to consumers
- Detecting and preventing review manipulation
- Maintaining the integrity of 5R★ Trust Scores

This is balanced against individual rights through proportionality assessments.

## What Data Is Used for Scoring

| Data | Used for | Retention |
|------|----------|-----------|
| Review text | Quality scoring, fake detection, sentiment | As long as review exists |
| Rating | 5R★ Trust Score calculation | As long as review exists |
| Account age | Reputation weight | Account lifetime |
| Review count | Reputation weight | Account lifetime |
| Submission metadata | Behavioral analysis | Limited retention |
| Community votes | Reputation weight, quality signal | As long as review exists |

## 🚫 What Data Is NOT Used

- Demographic information (age, gender, ethnicity)
- Location data beyond country-level locale
- Browsing history outside the platform
- Social media profiles
- Financial information
- Personal communications

## Right to Erasure (GDPR Art. 17)

Users can request deletion of their reviews and account data. The platform applies a **balancing test**:

- **Standard case:** Review is deleted, 5R★ Trust Score recalculated
- **Public interest exception:** If the review concerns a matter of significant public interest (e.g., safety), a balancing assessment may apply
- **Anonymization alternative:** In some cases, the review text may be anonymized rather than deleted, removing all personal identifiers while preserving the aggregate signal

All erasure requests are processed and responded to within the legally required timeframe.

## Data Minimization

The scoring pipeline follows data minimization principles:
- Only data necessary for scoring is collected
- Behavioral signals are processed and converted to scores — raw behavioral data is not retained indefinitely
- Internal scores (reputation weight, quality score) are numerical values that cannot be reverse-engineered to identify individuals

## 🌍 Cross-Border Data

For the 20 supported locales, review data may be processed across jurisdictions. All processing complies with applicable data protection regulations including GDPR for EU/EEA users.

## Transparency

- Users can request a copy of all data the platform holds about them
- Users can see their review quality grades
- Companies can see their 5R★ Trust Score breakdown
- The scoring methodology is publicly documented (this repository)
