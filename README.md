# Data and tables for *Broad but shallow: a multivocal review of artificial intelligence adoption in Italian manufacturing*

This repository contains the data and tables used in the paper **Broad but shallow: a multivocal review of artificial intelligence adoption in Italian manufacturing** (M. Piangerelli, 2026). It holds data only; the manuscript and the processing scripts are kept separately.

## Contents

### `data/` : official statistics

| Path | Content | Source |
|---|---|---|
| `eurostat_isoc_eb_ain2.csv` | Use of AI technologies by NACE Rev. 2 activity (manufacturing total and sub-groups, services aggregates, ICT), enterprises with 10 or more persons employed, EU27 and Member States, 2021, 2023, 2024, 2025; all indicators of the dataset (technologies, business functions, barriers, digital-intensity combinations); units: % of enterprises, % of AI-using enterprises, % of enterprises that considered AI | Eurostat, dataset `isoc_eb_ain2` (ICT usage in enterprises survey), downloaded 1 October 2026 via the dissemination API |
| `eurostat_isoc_eb_ai.csv` | Same indicators by enterprise size class (10-49, 50-249, 250+ and aggregates), all activities except the financial sector | Eurostat, dataset `isoc_eb_ai` |
| `eurostat_raw/` | The ten API responses (JSON-stat 2.0) from which the two CSV files are derived, one per dataset and year | Eurostat dissemination API |
| `eurostat_meta.json` | Dataset labels, update timestamps and download time | Eurostat |
| `eurostat_sbs_manufacturing_2023.csv` / `.json` | Number of enterprises, persons employed and value added of manufacturing (NACE C) by country, reference year 2023 | Eurostat, structural business statistics, `sbs_ovw_act` |
| `istat/istat_ai_tables.csv` | Long-format extraction (3,753 cells) of the ISTAT tables on AI: adoption, technologies, business functions and barriers by sector (including nine manufacturing groups), macro-area and size class, 2023-2025; manufacturing by size class and by technology for 2023 and 2024 | ISTAT, see below |
| `istat/Tavole-ICT-imprese_2023.xlsx`, `_2024.xlsx`, `_2025.xlsx` | Data tables attached to the ISTAT releases "Imprese e ICT", years 2023, 2024, 2025 (tables 9a, 9b, 9c on AI) | ISTAT, https://www.istat.it |
| `istat/asi2024/D21/`, `istat/asi2025/D21/` | Tables of chapter 21 of the *Annuario statistico italiano* 2024 and 2025 (tables 21.15 and 21.16: AI by macro-sector x size class x technology, and by economic activity x technology; reference years 2023 and 2024) | ISTAT, https://www.istat.it/storage/ASI/2024/dati/D21.zip and .../2025/dati/D21.zip |
| `istat/SOURCES.md` | Documentation of the ISTAT files: table structure, denominators (adoption rates = % of all enterprises; technology and function shares = % of AI-using enterprises; barriers = % of non-users that considered AI), ATECO aggregates used by ISTAT (C24+C25, C27+C28, C29+C30), and the cells that are not published | |
| `figure_values.csv` | Every value plotted in the figures of the paper, with dataset, indicator code, unit, year and breakdown | derived |
| `adoption_estimates.csv` | The fifteen published estimates of AI adoption in Italy compared in the paper, each with source id, population, definition, reference year and page | derived from the catalog |

### `catalog/` : the review corpus

| Path | Content |
|---|---|
| `catalog.csv` | One row per document of the multivocal review (134 documents: 53 peer-reviewed, 34 institutional, 47 think tank and consultancy): publisher, authors, title, year, type, URL and DOI, population, sample size, sampling method, operational definition of AI adoption, manufacturing coverage, AACODS appraisal score (0-12), conflict-of-interest flag, verification status |
| `findings.csv` | One row per extracted finding (730 rows, 666 quantitative and 61 qualitative): source id, metric, value, unit, reference year, page reference and verbatim excerpt |

### `review/` : search protocol

| Path | Content |
|---|---|
| `extraction_schema.md` | Coding scheme applied to every document (fields, AACODS criteria, conflict-of-interest flag, verification rule) |
| `search_log_*.md` | Search logs of the three layers and of the second consultancy round: databases and queries, dates, records identified, screened, included and excluded with reasons (PRISMA-style counts) |

## Notes on use

- Eurostat and ISTAT disseminate the same survey (the Italian part of the EU survey on ICT usage in enterprises, carried out by ISTAT on a probability sample of about 17,000 enterprises with 10 or more persons employed). Wherever both publish a cell, the values coincide.
- In the ISTAT tables, adoption rates are percentages of all enterprises, while technology and business-function shares are percentages of AI-using enterprises; ISTAT labels the technology items "finalità" although they are technologies and not business functions. See `data/istat/SOURCES.md`.
- The AI technology list of the survey gained an item (generation of images, video or audio) in 2025, so the headline indicator is not strictly comparable between 2024 and 2025; individual technology items are stable.
- Original documents of the review corpus (reports, journal articles) are not redistributed; `catalog.csv` gives the URL or DOI of each.

## Licence and citation

Eurostat and ISTAT data are reused under their open-data licences (Eurostat: free re-use with acknowledgement of the source; ISTAT: CC BY 3.0 IT). Derived files (`istat_ai_tables.csv`, `figure_values.csv`, `adoption_estimates.csv`, `catalog/`) are released under CC BY 4.0. Please cite the paper when using them.
