# Carabanchel: Material and Narrative Change, 2015–2025

This repository contains the analytical workflow for my master's thesis on recent urban change in **Carabanchel, Madrid**.

The study combines:

* **Material change:** demographic, socioeconomic, and housing-market change across Madrid's 21 districts.
* **Narrative change:** changes in newspaper representation of Carabanchel between 2015 and 2025.

The main cross-district material comparison covers **2015–2022**, while several Carabanchel-specific indicators and the newspaper corpus extend beyond this period.

## Analysis

The main files are:

* `report/final_analysis.Rmd` — consolidated analysis and main results
* `analysis/Rmd/01_part1_material_change.Rmd` — demographic, socioeconomic, and housing-market analysis
* `analysis/Rmd/02_part2_narrative_change.Rmd` — lexical analysis, topic modeling, and qualitative close reading
* `analysis/Rmd/03_robustness_checks.Rmd` — sensitivity and robustness checks

Rendered HTML versions are available in `report/` and `analysis/html/`.

## Data sources

| Dimension                    | Source                                                   |
| ---------------------------- | -------------------------------------------------------- |
| Population, age, nationality | Madrid Municipal Register (*Padrón municipal histórico*) |
| Income                       | Madrid City Council                                      |
| Education                    | Madrid Data Bank                                         |
| Occupational status          | Ayuntamiento de Madrid, *Anuario Estadístico Municipal*  |
| Advertised rent              | Madrid Data Bank / historical Idealista reports          |
| Used-housing sale prices     | Madrid Data Bank / Colegio de Registradores de España    |
| Newspaper coverage           | MyNews, newspaper websites, and ProQuest                 |

## Newspaper corpus

The narrative analysis uses **331 newspaper articles from 2015–2025** from *El Mundo*, *El País*, and *elDiario.es*.

Full article text is not included in this public repository because of copyright and redistribution restrictions. The repository contains the analysis code and derived outputs, but reproducing the full narrative analysis requires access to the original corpus.

Generated NLP files, including UDPipe models and processed lemma-token objects, are also excluded from version control.

## Reproducing the analysis

The project was developed in **R** and organised as an RStudio project.

1. Clone the repository.
2. Open `MUCSS26_TFM.Rproj`.
3. Install the required R packages.
4. Run the files in `analysis/Rmd/`.
5. Run `report/final_analysis.Rmd` for the consolidated report.

Main packages include `tidyverse`, `lubridate`, `readxl`, `tidytext`, `udpipe`, `stm`, `quanteda`, `ggrepel`, and `patchwork`.

## Author

**Jueun Lee**
MUCSS 2026 TFM project
