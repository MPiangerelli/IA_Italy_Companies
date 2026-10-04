# Search log: supplementary search in Scopus and Web of Science (3 October 2026)

Purpose: complement the open-database search of the peer-reviewed layer (OpenAlex, Semantic Scholar, Crossref; see `search_log_peer_reviewed.md`) with the two subscription databases. Queries were run by the author from the university network with the strings in `supplementary_search_scopus_wos.md`; exports were de-duplicated against the catalog with `scripts/import_supplementary.py`; screening of titles and abstracts was done in four batches by assistant passes with a common protocol, with unsure cases resolved by the author's reviewer; included papers were coded with the standard extraction schema (`sources/extract_supplementary_*.jsonl`).

## Queries and exports

| Database | Query | Topic | Hits reported | Records exported |
|---|---|---|---|---|
| Scopus | S1 | AI adoption in Italian firms | 289 | 289 |
| Scopus | S2 | Industry 4.0 adoption and effects in Italy | 246 | 246 |
| Scopus | S3 | Family firms, districts, Mezzogiorno | 271 | 271 |
| Scopus | S4 | Cross-country firm-level AI studies on official microdata | 47 | 47 |
| Scopus | S5 | Theory and reviews, AI in manufacturing SMEs | 486 | 486 |
| Scopus | S6 | Italian-language terms | 0 | 0 |
| WoS Core Collection | W1 | as S1 | 352 | 470 (export includes early-access records) |
| WoS Core Collection | W2 | as S2 | 179 | 180 |
| WoS Core Collection | W3 | as S3 | 128 | 131 |
| WoS Core Collection | W4 | as S4 | 52 | 53 |
| WoS Core Collection | W5 | as S5 | 291 | 431 (as W1) |
| WoS Core Collection | W6 | as S6 | 2 | 2 |

Date filters: 2019-2026 (Scopus `PUBYEAR > 2018 AND PUBYEAR < 2027`; WoS timespan 2019-2026). Document types: article, review, book chapter, conference paper (Scopus); article, review article, proceedings paper (WoS). A first WoS export (12:04-12:27) contained only the first 50 records per query and was replaced by complete exports (13:51-13:55); the 411 records added by the complete exports were screened as batch D.

## PRISMA-style counts

| Step | n |
|---|---|
| Raw records across the 11 export files | 2,606 |
| Unique records (by DOI, else normalised title) | 1,765 |
| Already in the review catalog (matched by DOI or title) | 28 |
| Candidates screened on title and abstract | 1,732 (batch A, Italy and AI/Industry 4.0 and firms: 461; batch B, international theory and microdata: 438; batch C, residual: 422; batch D, complete WoS exports: 411; 5 further records were duplicates of screened items under a different key) |
| Excluded after screening | 1,659 |
| Met the inclusion criteria | 73 (batch A 63 incl. 6 resolved from unsure; B 4 incl. 2 resolved; C 3; D 3 incl. 1 resolved) |
| Reports not retrieved (full text not obtainable; PRISMA 2020) | 16 (six book chapters, two conference papers, three Italian-language journal articles, five other journal articles; list in `sources/catalog_not_retrieved.csv`) |
| Included in the corpus | 57 |

Exclusion reasons (recorded per record in `data/supplementary_search/screened_all.csv`): technical or engineering applications of AI to a process; healthcare, agriculture, public administration, tourism, finance; non-Italian single-country samples and convenience perception surveys; individuals, consumers or workers as unit; single-company cases; conceptual, legal or bibliometric papers; Italian link only through author affiliation; aggregate country-level panels redundant with the direct use of Eurostat data; duplicates.

Unsure cases resolved by the lead reviewer as include: Bratta et al. 2023 (journal version of the 2020 working paper already in the catalog), Antonietti et al. 2023, Chiarini and Kumar 2022, Cassetta et al. 2020, Pagano et al. 2021, Cimini et al. 2021 (batch A); Omrani et al. 2024, Marioni et al. 2024 (batch B); Horvat et al. 2026 (batch D, German manufacturing survey kept as EU comparator). All other unsure cases were excluded (methodological papers using Italian surveys only as illustration, samples below 20 firms, outcomes unrelated to adoption, aggregate data).

## Extraction

The 73 included papers were coded in four batches (`sources/extract_supplementary_1.jsonl` to `_4.jsonl`, BibTeX in `sources/supplementary_*.bib`). Full texts were obtained where open access or available through institutional repositories, the Wayback Machine or publisher CC-BY copies; the network used for extraction is blocked by bot protection at ScienceDirect, Taylor and Francis, Wiley, Emerald and the Italian IRIS repositories, so a number of papers were at first coded only from the abstract (`verified=false` in the catalog, with the reason in `notes`). On 3 October 2026 the author retrieved 36 of these full texts through institutional access; the records were re-coded from the full text (755 excerpts, each machine-matched to the PDF page; 17 differed only by ligatures, mathematical glyphs or interleaved footnotes and were confirmed by hand), so that 57 of the 73 eligible records are in the corpus, all coded on the full text (after the removal of two duplicate institutional records and the addition of one OECD volume, see `search_log_institutional.md`, the corpus counts 189 documents). Following PRISMA 2020 the 16 supplementary records (plus Rogers 2003, a monograph of the open search whose 2009 restatement is in the corpus) whose full text could not be obtained are classified as reports not retrieved and kept outside the corpus, with their abstract-level coding, in `sources/catalog_not_retrieved.csv` and `sources/findings_not_retrieved.csv` (decision of 3 October 2026). The 17 documents still coded from abstracts (list in `data/supplementary_search/unverified_full_texts_wanted.csv`) are not cited in the manuscript. Corrections found at re-coding: Agostini and Filippini 2019 identify three clusters, not two as the abstract suggests; Di Maria et al. 2022 analyse 189 adopters, not 1,200 respondents; Benedetti et al. 2025 exclude AI, cloud and IoT from their deprivation index; Agostino et al. 2026 (MET survey) have no AI item; Ferraro et al. 2025 label as "artificial intelligence" two Likert items on digitalisation and innovation management; Zheng et al. 2020 use four-level knowledge and use scales, not the six-technology five-level scale of the 2023 paper.

## Finding of the supplementary search relevant to the paper

None of the Italian firm-level studies added by the supplementary search measures AI adoption on its own in manufacturing before 2023: all use the Industry 4.0 bundle, digital-maturity classes or a list in which AI is one item (the closest are Cugno et al. 2025, where AI is one of the technologies in a 2022 Unioncamere survey of manufacturing SMEs, and Chiarini et al. 2026, a 2025-26 opt-in survey on AI in production). This confirms gap (i) of the research agenda.
