# From Diversity to Dominance: A Century of Seafood in British Print Media

Code for an MSc dissertation (University of Exeter) examining how British newspapers framed seafood species from 1920 to 2024, and whether the UK's "Big Five" species (cod, haddock, salmon, prawns and tuna) were framed differently from other species.

## Background

About 63% of seafood eaten in the UK comes from just five species. This is often put down to stable consumer preference. This project asks whether media framing may have helped reinforce it, using a corpus of 2,98,331 articles exported from the Gale Digital Scholar Lab (1920–2024).

## Key findings

- **The Big Five and Other species were framed differently:** Articles mentioning the Big Five carried more health (10.1% vs 5.1%), environment (17.9% vs 12.9%) and convenience (10.1% vs 7.1%) framings. Other species carried more economy framing (28.2% vs 22.2%). The difference in overall framing composition was significant (PERMANOVA, p < 0.001).
- **1950 crossover:** A logistic regression with a year × Big Five interaction puts the point where the two groups' framing patterns crossed over in 1950, close to the launch of the UK fish fingers.
- **Events and framing:** Convenience framing rose after the 1955 fish finger launch (6.5% → 11.5%). Tradition/culture framing more than doubled after the 1973 Icelandic cod collapse (13.2% → 27.9%). Environment framing rose after MSC certification in the 1990s (20.3% → 31.4%).
- **Gradual drift.** Framing composition changed gradually over the century. Divergence between decades grew with the gap in years (r = 0.906).

See the dissertation for full results, caveats and discussion: [link to report/repository, if shared].

## Repository contents

| File | Description |
|---|---|
| `[01_data_pipeline.ipynb]` | Corpus assembly, joining article text to metadata, species lexicon matching, noise filtering and topic modelling |
| `[02_analysis_pipeline.ipynb]` | Framing classification, PERMANOVA, logistic regression, historical event analysis and figures |
| `[data/framing_by_decade_export.csv]` | Aggregated framing data by decade (derived data only) |
| `requirements.txt` | Python dependencies |
| `LICENSE` | MIT License |

## Methods in brief

1. **Corpus:** newspaper articles exported from Gale Digital Scholar Lab, then cleaned in several stages (species keyword match, regex correction for false positives, and removal of non-fisheries genres).
2. **Topic modelling:** LDA separated formulaic market-bulletin content from narrative articles. The framing-eligible corpus is 49,753 articles.
3. **Framing analysis:** a keyword-in-context lexicon assigns each article a dominant frame: health, economy, environment, tradition/culture, convenience or none.
4. **Statistics:** PERMANOVA (Bray–Curtis), logistic regression, and chi-squared tests around six historical events.

## Getting started

```bash
git clone [https://github.com/](https://github.com/)[your-username]/[repo-name].git
cd [repo-name]
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

Run the notebooks in order: data pipeline first, then analysis pipeline.

Main libraries: pandas, scikit-learn, statsmodels, scipy, scikit-bio and plotly. [Python version: X.X]

## Data availability

The raw newspaper articles come from Gale Digital Scholar Lab and are **not included**, because they are licensed material. To reproduce the corpus, you need institutional access to Gale Digital Scholar Lab. [Describe the search string and content sets, or point to the section of the report that does.] The aggregated outputs in `data/` are provided so the analysis notebook can be inspected and, where possible, re-run.

## Limitations

- OCR errors in historical scans likely cause under-detection of species mentions.
- Framing uses a keyword dictionary, not a validated multi-coder codebook.
- The publication mix shifts from regional to national titles over time.
- Results apply to English-language UK print archives only.

## Citation

If you use this work, please cite:
