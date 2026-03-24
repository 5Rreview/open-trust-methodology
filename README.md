<p align="center">
  <a href="https://5rrrrr.com">
    <img src="assets/banner.svg" alt="5★★★★★.com — Reviews You Can Trust" width="100%">
  </a>
</p>

<p align="center">
  <a href="https://5rrrrr.com"><img src="https://img.shields.io/badge/🌐_5rrrrr.com-live-F7A610?style=for-the-badge&labelColor=141416" alt="Website"></a>
  <a href="https://github.com/5Rreview/docs"><img src="https://img.shields.io/badge/docs-platform_docs-3B82F6?style=for-the-badge&labelColor=141416" alt="Docs"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-CC_BY--SA_4.0-71717A?style=for-the-badge&labelColor=141416" alt="License"></a>
</p>

<div align="center">

# 5R★ Open Trust Methodology

**Trust is Measurable.&nbsp;&nbsp;The Methodology is Open.**

<sub>How we measure trust, detect manipulation, and ensure fairness — published openly.</sub>

</div>

---

> [!IMPORTANT]
> This repository describes our **methodology** — principles, approaches, and signal categories.<br>
> Implementation details (exact parameters, thresholds, model weights) are kept internal to prevent gaming.

## Why Open?

Most review platforms are black boxes. We publish our methodology to prove:

- 🔒 Rankings are **never** influenced by payment
- ⚖️ Detection is applied **uniformly** to all companies
- 📐 The scoring model is **fair** and **evidence-based**

---

## 🏗️ Architecture

```
                    ┌─────────────────────────────┐
                    │     5R★ Trust Score          │
                    │        (0 – 100)             │
                    └──────────┬──────────────────┘
                               │
          ┌────────────────────┼────────────────────┐
          │                    │                     │
   ┌──────┴──────┐    ┌───────┴───────┐    ┌───────┴───────┐
   │  Weighted    │    │   Company     │    │  Confidence   │
   │  Reviews     │    │   Behavior    │    │  Adjustment   │
   │              │    │              │    │               │
   │ • Ratings    │    │ • Response   │    │ • Volume      │
   │ • Quality    │    │   rate       │    │ • Recency     │
   │ • Reputation │    │ • Resolution │    │ • Diversity   │
   │ • Recency    │    │   rate       │    │               │
   └──────────────┘    └──────────────┘    └───────────────┘
          │
   ┌──────┴──────────────────────────────────┐
   │       🔍 Integrity Layer                │
   │                                          │
   │  • Fake Detection (rule-based pipeline)  │
   │  • Quality Scoring (5 metrics)           │
   │  • Behavioral Analysis                   │
   │  • Community Correction                  │
   └──────────────────────────────────────────┘
```

> [!NOTE]
> The entire pipeline operates autonomously using **deterministic, rule-based algorithms**.<br>
> No external AI service is required. AI enhances detection as an optional layer only.

---

## 📚 Documentation

<table>
<tr>
<td width="50%" valign="top">

### 🛡️ Trust Model
| Doc | Description |
|-----|-------------|
| [Trust Score](docs/trust-score.md) | How the 5R★ Trust Score is computed |
| [Reputation Weight](docs/reputation-weight.md) | How reviewer credibility works |
| [Time Decay](docs/time-decay.md) | Why recent reviews matter more |

### 🔍 Integrity
| Doc | Description |
|-----|-------------|
| [Integrity & Detection](docs/integrity.md) | Multi-level manipulation detection |
| [Review Quality](docs/review-quality.md) | Five-metric quality model |
| [Community Correction](docs/community-correction.md) | Crowd-powered accuracy |

</td>
<td width="50%" valign="top">

### 📜 Principles
| Doc | Description |
|-----|-------------|
| [Sacred Rules](docs/sacred-rules.md) | 5 inviolable principles |
| [Separation Architecture](docs/separation-architecture.md) | Trust vs. business layers |
| [Resolution Loop](docs/resolution-loop.md) | Response → resolution → trust |

### ⚖️ Governance
| Doc | Description |
|-----|-------------|
| [Privacy & Data](docs/privacy.md) | GDPR, data handling, erasure |
| [Bias Monitoring](docs/bias-monitoring.md) | Fairness across 20 locales |

</td>
</tr>
</table>

---

## ⭐ Sacred Rules

> [!CAUTION]
> These rules **cannot** be overridden by any business decision, revenue target, or partnership agreement.

| &nbsp; | Rule | Description |
|:---:|------|-------------|
| 🔒 | **Ranking Independence** | Trust scores are <kbd>never</kbd> influenced by payment |
| 📝 | **No Silent Deletion** | Weight reduction over deletion — always |
| 💬 | **Right to Respond** | Every company can respond publicly to any review |
| ✅ | **Resolution Visibility** | Resolved issues are shown publicly |
| 🤖 | **AI Transparency** | AI-detected content is always labeled |

<div align="center">

### Priority Hierarchy

```
User Trust  >  Company Satisfaction  >  Revenue
```

<sub>This isn't aspirational — it's operational.</sub>

</div>

---

<details>
<summary><strong>🔄 Changelog</strong></summary>

<br>

### `2025.06` — Initial Publication

- 5R★ Trust Score calculation (Bayesian averaging)
- Confidence intervals &amp; Wilson Score ranking
- Exponential time decay (industry-tunable)
- Reputation weight system (7 factors)
- Two-level integrity pipeline
- Five-metric review quality model
- Community correction mechanisms
- Sacred Rules (5 principles)
- Separation Architecture
- Resolution Loop
- GDPR compliance
- Bias monitoring for 20 locales

</details>

---

## 🤝 Contributing

We welcome discussion and feedback. Open an issue to:

| Action | Example |
|--------|---------|
| 🐛 Report bias | "Scores seem systematically lower for Japanese reviews" |
| 💡 Suggest improvement | "Consider adding review age as a quality factor" |
| ❓ Ask a question | "How does time decay work for seasonal businesses?" |
| 📊 Propose metrics | "Track false positive rates per locale" |

---

<p align="center">
  <sub>Made with ⭐ by the <a href="https://5rrrrr.com">5R★</a> team · <a href="LICENSE">CC BY-SA 4.0</a></sub>
</p>
