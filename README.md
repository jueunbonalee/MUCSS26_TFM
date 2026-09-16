# Carabanchel in Transition: Material and Narrative Change in Madrid, 2015–2025

This repository contains the analytical workflow for my Master's Thesis in Computational Social Science at Universidad Carlos III de Madrid (UC3M).

The study examines recent urban change in **Carabanchel, Madrid** through two complementary dimensions:

- **Material change:** demographic, socioeconomic, and housing-market change in Carabanchel relative to Madrid's 21 districts.
- **Narrative change:** changes in newspaper representation of Carabanchel between 2015 and 2025.

The main cross-district material comparison covers **2015–2022**, the common period for which all core indicators are available. Several Carabanchel-specific series extend beyond 2022, and the newspaper corpus covers **2015–2025**.

## Repository structure

```text
MUCSS26_TFM/
├── analysis/
│   ├── Rmd/
│   │   ├── 01_part1_material_change.Rmd
│   │   ├── 02_part2_narrative_change.Rmd
│   │   └── 03_robustness_checks.Rmd
│   └── html/
├── data/
│   ├── raw/
│   └── processed/
├── report/
│   ├── final_analysis.Rmd
│   └── final_analysis.html
├── MUCSS26_TFM.Rproj
└── README.md
```

The main analysis files are:

- `report/final_analysis.Rmd` — consolidated analytical workflow and main results.
- `analysis/Rmd/01_part1_material_change.Rmd` — demographic, socioeconomic, and housing-market analysis.
- `analysis/Rmd/02_part2_narrative_change.Rmd` — corpus construction, lexical analysis, Structural Topic Modelling (STM), topic terms and prevalence, and qualitative close reading.
- `analysis/Rmd/03_robustness_checks.Rmd` — robustness and sensitivity checks for the occupational-status definition, STM topic number, and outlet composition.

Rendered HTML versions are provided for easier inspection.

## Data sources

| Dimension | Source |
| --- | --- |
| Population, age, nationality | Madrid Municipal Register (*Padrón municipal histórico*) |
| Income | Madrid City Council household-income distribution data |
| Education | Madrid Data Bank |
| Occupational status | Ayuntamiento de Madrid, *Anuario Estadístico Municipal* |
| Advertised rent | Madrid Data Bank, based on historical Idealista reports |
| Used-housing sale prices | Madrid Data Bank / Colegio de Registradores de España |
| Newspaper coverage | MyNews, supplemented with newspaper websites and ProQuest where required |

The material-analysis source files used in the thesis are included under `data/raw/`.

## Newspaper corpus and data availability

The narrative analysis uses **331 newspaper articles** about Carabanchel published between 2015 and 2025 in *El Mundo*, *El País*, and *elDiario.es*.

The full article texts are **not included in this public repository** because they are copyright-restricted and cannot be redistributed. The analysis code documents the corpus-selection and processing procedure, but reproducing the narrative analysis from raw text requires authorised access to the original articles and a local corpus file at:

```text
data/raw/carabanchel_news.csv
```

Generated NLP files, including downloaded UDPipe models and `lemma_tokens.rds`, are also excluded from version control because they can be recreated locally from the corpus.

## Analytical workflow

### 1. Material change

The material analysis compares Carabanchel with Madrid's other districts using demographic, socioeconomic, and housing-market indicators. The main 2015–2022 comparison includes changes in income, university education, occupational status, advertised rent, and used-housing sale prices, together with demographic context.

### 2. Narrative change

The narrative analysis combines:

- normalised lexical and n-gram trends;
- exploratory TF-IDF analysis;
- a **9-topic Structural Topic Model (STM)**;
- highest-probability and FREX terms for topic interpretation;
- annual topic prevalence; and
- qualitative close reading of representative articles.

### 3. Robustness checks

The robustness analysis examines whether the main findings are sensitive to:

- alternative definitions of higher occupational status;
- the selected number of STM topics; and
- changes in newspaper outlet composition over time.

## Reproducing the analysis

The project was developed in **R** as an RStudio project.

1. Clone this repository.
2. Open `MUCSS26_TFM.Rproj`.
3. Install the required R packages.
4. Run `analysis/Rmd/01_part1_material_change.Rmd` for the material analysis.
5. For the narrative analysis, place an authorised local copy of the newspaper corpus at `data/raw/carabanchel_news.csv`, then run `analysis/Rmd/02_part2_narrative_change.Rmd`.
6. Run `analysis/Rmd/03_robustness_checks.Rmd` for the sensitivity and robustness checks.
7. Run `report/final_analysis.Rmd` for the consolidated analytical report.

Main R packages include `tidyverse`, `lubridate`, `readxl`, `tidytext`, `stopwords`, `udpipe`, `stm`, `quanteda`, `ggrepel`, `patchwork`, `purrr`, and `knitr`.

Random seeds are set where required for the STM analysis to support reproducibility.

## Thesis

**Jueun Lee**  
Master in Computational Social Science  
Universidad Carlos III de Madrid  
2026
