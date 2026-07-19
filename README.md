# Project Impact Lense
### Do polarising political ads win on social media? A Meta Ads analysis of the 6 major German parties (2019–2023)

**Le Wagon Data Analytics Bootcamp — Batch group project, December 2023**
Team: Patrick, Friedrich, Manon, Nikolaus, Jakob

---

## Context

Germany faced a "super election year" in 2024. This project analysed how CDU/CSU, SPD, GRÜNE, FDP, AfD, and DIE LINKE used paid Facebook & Instagram advertising between 2019 and 2023 — where they spent, how much, and what emotional register their ad copy used.

**Data source:** Meta Ad Library (public archive of political/social issue ads), extracted as CSV per party.

## Three questions, three answers

| Question | Method | Finding |
|---|---|---|
| **Does money buy reach?** | Spend vs. impressions per party, 2019–2023 | Budget matters, but is not sufficient on its own — fresh content correlates with reach independently of spend |
| **Does polarising content get more attention?** | Sentiment/emotion classification of ad copy | Ads scoring higher on polarising emotional registers outperform on engagement |
| **Who gets the best return on ad spend?** | Impressions-per-euro by party | DIE LINKE and AfD had the strongest impressions-to-budget ratio of the six parties |

Full walkthrough and recommendations (individual + regulatory level): see `Presentation/DA_ImpactLense_Final.pdf`.

## Methodology

**1. Data pipeline (BigQuery + Python)**
- Meta Ad Library exports ingested and cleaned per party
- Joins and aggregation in Google BigQuery
- Demographic and regional distribution scripts: `demographic_distributions.py`, `regions_distributions.py`

**2. Sentiment / emotion analysis (NLP)**
- Ad copy (byline + body) translated and cleaned with NLTK (tokenisation, lemmatisation, stopword removal)
- Emotion classification via Hugging Face's [`SamLowe/roberta-base-go_emotions`](https://huggingface.co/SamLowe/roberta-base-go_emotions) model, top-10 emotion scores extracted per ad
- Aggregated by party; four emotions retained for cross-party comparison: **love, caring, disgust, fear**
- Full pipeline: `notebooks/sentiment_analysis.ipynb`

**3. Exploratory analysis**
- Budget, impressions, and demographic exploration: `notebooks/exploratory_analysis.ipynb`

## Repo structure

```
Project_Impact_Lense/
├── README.md
├── notebooks/
│   ├── exploratory_analysis.ipynb       # BigQuery extraction, demographic/regional exploration
│   └── sentiment_analysis.ipynb         # NLTK cleaning + Hugging Face emotion classification
├── scripts/
│   ├── demographic_distributions.py
│   └── regions_distributions.py
├── data_notes/
│   ├── Demographic_Splitting.txt
│   ├── Region_Splitting.txt
│   └── Impressions.txt
└── Presentation/
    └── DA_ImpactLense_Final.pdf          # Final jury presentation, incl. conclusions & recommendations
```

## Tools

Meta Ad Library · Google BigQuery · Google Colab · Python (Pandas, NLTK) · Hugging Face Transformers · Seaborn/Matplotlib · Looker · Google Sheets · GitHub

## Limitations

This was a 2-week bootcamp project with a real but limited dataset (~57,000 ads). Findings on sentiment and reach are correlational, not causal, and the emotion classifier was applied to translated text, which introduces some translation-layer noise. Two of the four original team hypotheses (ad timing relative to elections, center vs. fringe polarisation) were explored but not brought to statistical conclusion within the project timeline — the final presentation focuses on the three findings above, which were fully worked through.

---
*Built in 5 days as part of Le Wagon's Data Analytics bootcamp (Berlin, Dec 2023).*
