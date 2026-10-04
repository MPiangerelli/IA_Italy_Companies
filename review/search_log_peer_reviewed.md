# Search log: peer_reviewed layer

> **Nota (02-10-2026).** Questo log documenta la ricerca al momento in cui fu eseguita. Alcune affermazioni sullo stato di verifica sono state superate: i testi completi di Minsait-TEHA 2025, TEHA 2026 (AI Skills 4 Agents), Brey e van der Marel 2024, Chatterjee et al. 2021, Cohen e Levinthal 1990, Baker 2012 e Tornatzky e Fleischer 1990 sono stati ottenuti il 1 ottobre 2026 e le relative schede ri-verificate (`sources/catalog.csv`, campo `verified`, fa fede).


MLR on AI adoption in Italian manufacturing firms. Layer: peer-reviewed journal articles, peer-reviewed conference papers, academic books and chapters, plus high-quality academic working papers (NBER, OECD STI, ECB, ministerial research WPs, INAPP) recorded as `working_paper`.
Searches run on 2026-09-29 and 2026-09-30 (Europe/Rome), by one reviewer with four parallel extraction passes that used the same protocol and schema (`notes/extraction_schema.md`).

## 1. Sub-goals and eligibility

- **Sub-goal A (empirical).** Firm-level or regional empirical studies on adoption of AI (or closely related Industry 4.0 / advanced digital technologies) by Italian firms, especially manufacturing and SMEs. Topics: determinants, barriers, effects on productivity, employment and skills, Piano Industria 4.0 / Transizione 4.0 incentives (iper-ammortamento), industrial districts, family firms, North/South gaps. European comparative firm-level studies that include Italy were also eligible.
- **Sub-goal B (anchors).** Canonical theory and method sources: TOE, Diffusion of Innovations, absorptive capacity, MLR guidelines, PRISMA-ScR, AACODS, Industry 4.0/5.0 review, systematic reviews of AI in SMEs and manufacturing, AI productivity evidence.
- **Inclusion criteria.** (i) Peer-reviewed or high-quality academic WP. (ii) For A: Italian firms, or EU cross-country data with Italy in the sample. (iii) Adoption or effects of AI / I4.0 technologies measured at firm, plant or local-system level. (iv) 2017-2026 for A (Piano Industria 4.0 was launched in 2017); no date limit for B.
- **Exclusion criteria.** E1 not about firms' technology adoption (medical, legal, household or individual use, sector-specific engineering applications). E2 no Italian or EU firm data (A only). E3 predatory or low-quality venue, or preprint without peer review when a better source exists. E4 duplicate record (SSRN/RePEc copy of an included article). E5 editorial, book review or guest editorial. E6 covered by another layer (e.g. Banca d'Italia *Questioni di Economia e Finanza*, ISTAT, OECD policy reports go to the `institutional` layer).

## 2. Databases and tools

| Tool | Use | Notes |
|---|---|---|
| OpenAlex API (`api.openalex.org/works`) | main bibliographic search | `search=` (relevance) and `filter=title_and_abstract.search:` / `title.search:` with date filters, `sort=cited_by_count:desc`, 25-40 records screened per query |
| Semantic Scholar Graph API | complementary search, abstracts by DOI | heavily rate-limited (HTTP 429): 2 of 3 queries returned no records |
| Crossref REST API (`api.crossref.org/works/<doi>`) | DOI verification of every included record; bibliographic queries for books | title, authors and year recorded exactly as Crossref returns them (year = `published-print` if present, else `issued`) |
| Unpaywall API | locating OA copies | |
| WebSearch (general web) | known-item and grey-to-peer bridging | 4 queries |
| Open Library API | bibliographic data for books without DOI | Tornatzky and Fleischer (1990), Rogers (2003) |
| ERIC | abstract for Cohen and Levinthal (1990) | JSTOR blocked |

Access limitations: ScienceDirect (HTTP 403), Springer Link, EconStor, JSTOR and several DSpace repositories serve a JavaScript client challenge to non-browser clients, so for some records only the abstract (Crossref, OpenAlex or Semantic Scholar) could be read. Each affected record says so in `notes`.

## 3. Query log

Dates: queries 1 to 28 were run on 2026-09-29 and 2026-09-30. "Hits" is the total the database reported. "Screened" is the number of records whose title, venue and authors were screened: for OpenAlex filter queries, the top records sorted by citation count; for `search=` queries, the top records by relevance.

### OpenAlex

| # | Query (field) | Date filter | Hits | Screened |
|---|---|---|---|---|
| 1 | `search=artificial intelligence adoption Italian firms` | from 2017 | 28,739 | 25 |
| 2 | `search=Industry 4.0 adoption Italian manufacturing firms` | from 2017 | 15,043 | 25 |
| 3 | `search=artificial intelligence Italy manufacturing SMEs` | from 2017 | 12,096 | 25 |
| 4 | `title_and_abstract.search:artificial intelligence Italian firms` | from 2017 | 143 | 40 |
| 5 | `title_and_abstract.search:artificial intelligence Italy firm-level` | from 2017 | 67 | 40 |
| 6 | `title_and_abstract.search:Industry 4.0 Italian firms productivity` | from 2017 | 25 | 25 |
| 7 | `title_and_abstract.search:hyper-depreciation Italy` | from 2017 | 4 | 4 |
| 8 | `title_and_abstract.search:Industry 4.0 tax incentives Italy` | from 2017 | 6 | 6 |
| 9 | `title_and_abstract.search:digital technologies Italian firms employment skills` | from 2017 | 59 | 29 |
| 10 | `title.search:artificial intelligence Italian` | from 2018 | 217 | 27 |
| 11 | `title.search:AI adoption Italy` | from 2018 | 17 | 17 |
| 12 | `title_and_abstract.search:AI adopters firm characteristics productivity countries` | from 2020 | 15 | 15 |
| 13 | `title_and_abstract.search:family firms Industry 4.0 Italian` | from 2017 | 13 | 13 |
| 14 | `title_and_abstract.search:robots employment Italy local labour markets` | from 2018 | 8 | 8 |
| 15 | `title.search:portrait of AI adopters` (known item) | none | 1 | 1 |
| 16 | `title.search:artificial intelligence firm-level productivity` | from 2019 | 19 | 19 |
| 17 | `title_and_abstract.search:artificial intelligence adoption SMEs systematic literature review` | from 2020 | 186 | 21 |
| 18 | `title_and_abstract.search:artificial intelligence adoption manufacturing TOE` | from 2019 | 89 | 21 |
| 19 | `title_and_abstract.search:AI adoption European firms Eurostat` | from 2019 | 24 | 21 |
| 20 | `title_and_abstract.search:Southern Italy Industry 4.0 firms` | from 2017 | 8 | 8 |
| 21 | `title_and_abstract.search:industrial districts digital technologies Italy` | from 2017 | 26 | 21 |
| 22 | `title_and_abstract.search:generative AI Italian firms` | from 2023 | 22 | 21 |
| 23 | `title_and_abstract.search:Industry 4.0 adoption Italian SMEs barriers` | from 2017 | 9 | 9 |
| 24 | `title.search:Industry 4.0 technological trajectories traditional manufacturing regions` (known item) | none | 1 | 1 |
| 25 | `title.search:Intelligent technologies and productivity spillovers` (known item) | none | 1 | 1 |

### Semantic Scholar

| # | Query | Hits | Screened |
|---|---|---|---|
| 26 | `artificial intelligence adoption Italian manufacturing firms` | n/a (HTTP 429 after 4 retries) | 0 |
| 27 | `AI adoption Italian SMEs determinants` | 106 | 25 |
| 28 | `Industry 4.0 Italy incentives firm performance` | n/a (HTTP 429) | 0 |

### Web search

| # | Query | Purpose |
|---|---|---|
| W1 | `Bratta Romano Acciari Mazzolari hyper-depreciation Industry 4.0 journal article published` | check publication status of the MEF WP (WP only; led to Antonazzo et al. 2026) |
| W2 | `"artificial intelligence" adoption Italian firms ISTAT microdata determinants productivity journal 2024 2025` | Italian AI-adoption papers (led to Crespi et al. 2026; Banca d'Italia QEF 1005 went to the institutional layer) |
| W3 | `Tyndall AACODS checklist Flinders University 2010 grey literature pdf` | known item |
| W4 | `Cohen Levinthal 1990 "absorptive capacity" ... pdf` | known item (led to the ERIC abstract) |

### Other lookups

- **Crossref.** Every DOI of an included record was verified at `api.crossref.org/works/<doi>`: 49 DOIs, all resolved. Two bibliographic queries for the books found no DOI (the Tornatzky and Fleischer query returned only a 1991 book review, 10.1007/bf02371446).
- **Unpaywall and OpenAlex `locations`.** Used to find OA copies (IRIS repositories, LSE eprints, Lirias, NBER, OECD, ECB, finanze.gov.it, INAPP).
- **Snowballing (backward, from included papers).** Garlatti Costa et al. 2026 (a sibling of the 2025 paper), Corò et al. 2021, Venturini 2022, Ferrando et al. 2026, Cette et al. 2026 and Calabrese et al. 2025 were added in a second round, after the first-round screening.

## 4. PRISMA-style flow

| Stage | n |
|---|---|
| Records screened by title/venue (not de-duplicated across queries; 443 OpenAlex + 25 Semantic Scholar + about 20 web results) | about 488 |
| Records assessed for eligibility (abstract and/or full text) after de-duplication and title screening | 71 |
| Excluded at eligibility (reasons below) | 19 |
| **Included** | **52** (A: 35; B: 17) |
| of which full text read (version of record, accepted manuscript or WP version) | 38 |
| of which abstract only | 11 |
| of which metadata only (no content extracted) | 3 (Tornatzky and Fleischer 1990, Rogers 2003, Baker 2012) |

Note on the full-text count: shah2026aitransform and leoni2022aikm were read as publisher HTML through a fetch tool and are counted as full text, but they are marked `verified=false` because their figures passed through a summarising fetch tool. brey2024humancap combines the journal abstract with the authors' ECIPE precursor paper.

### Excluded at eligibility (n = 19), with reasons

| Record | Reason |
|---|---|
| Bertomeu, Lin, Liu (2025) J. Account. Econ., ChatGPT ban in Italy | E1: analysts' information processing, not firm adoption |
| Branzoli, Rainone, Supino (2024) J. Financ. Stab. | E1: banks' technology and credit, not manufacturing adoption |
| Ferri, Maffei, Spanò (2023) Management Decision | E1: individual risk professionals' intentions |
| Loschiavo, Moscatelli (2025) SSRN, GenAI in Italian households | E1: households |
| Colombelli, D'Amico, Paolucci (2023) J. Technol. Transf., AI start-ups and universities | E1: AI supply side (start-ups), not adoption |
| Lepore, Frontoni, Micozzi et al. (2022) Health Policy | E1: healthcare ecosystems |
| Saracco (2022) Discover AI, Italian AI strategy | E5/E3: perspective piece, no data |
| Muto, Luongo, Percuoco et al. (2024) Systems | E3: conceptual, no firm data |
| Ferretti, Romano, Pietrangeli (2026) Int. J. Foreign Trade Int. Bus. | E3: venue with predatory characteristics |
| Marchetti-Valerio (2025) Law and Economy | E3: venue with predatory characteristics |
| Bencivelli, Formai, Mattevi (2025) Research Square / SSRN, cloud and AI in Italian firms | E6: Banca d'Italia research, belongs to the institutional layer; preprint under review |
| Banca d'Italia QEF 1005 (2026), economic impact of AI in Italian firms | E6: institutional layer |
| Calvino et al. (2022) OECD, "Closing the Italian digital gap" | E6: OECD policy paper, institutional layer (flagged to that layer) |
| Montresor and Vezzani SSRN 4094997 | E4: duplicate of montresor2023twin |
| Bettiol et al. SSRN 3982295 | E4: precursor of bettiol2024productivity |
| Czarnitzki et al. SSRN 4049824 | E4: duplicate of czarnitzki2023productivity |
| Dottori SSRN 3680743 | E4: duplicate of dottori2021robots |
| Neirotti, Ricci, Tubiana INAPP WP 116 (2024) | E4: precursor of neirotti2026family |
| Fontanelli and Calvino CEP DP 2055 (2024), human capital and AI in French firms | E2: France only |

### Relevant but not retrieved (candidates for an update round)

**Resolution (4 October 2026).** Calabrese 2024, Agostini 2019 and Cucculelli 2026 were also found by the supplementary search and entered the corpus once their full texts were obtained; Avarello 2026, Calabrese 2022 and Jegerson 2026 are among the supplementary reports not retrieved. Of the remaining six: Pisano et al. 2026 is a report not retrieved (no full text and no abstract obtainable; `sources/catalog_not_retrieved.csv`); Capone et al. 2026 was excluded on its abstract (cultural and creative industries, outside manufacturing); Diletta et al. 2025 was excluded on the full text (156 employees of unspecified agri-food companies, no food-manufacturing breakdown, adoption intention only); Romanello and Veglio 2022 was excluded on the full text (single-company case study, the rule applied in the supplementary search); Garlatti Costa et al. (IJVCM) and Forgione and Migliardo 2026 (IJIS) were excluded because no version of record was published by 3 October 2026 (forthcoming article; journal pre-proof), under the inclusion criterion added on that date. Coding and reasons in `sources/excluded_after_eligibility.jsonl`.


Not included because they could not be accessed or verified in this round. Where a DOI is given, Crossref was not checked.

- Pisano, Lombardo, Bognetti (2026) *AI Adoption by Italian Startups: A Measurement Framework*, LNNS, 10.1007/978-3-032-23684-5_74.
- Avarello, Cava, Marozzo (2026) *AI Adoption in Sicilian SMEs*, LNNS, 10.1007/978-3-032-23684-5_39. Southern Italy, possibly useful for the North/South gap.
- Capone, Oliva, Innocenti (2026) *GenAI Adoption and Business Model Innovation in the Creative Industries in Italy* (Florence repository, no DOI).
- Diletta, Quaglieri, Mercuri (2025) *Assessing the Adoption of Gen-AI in the Italian Agri-Food Industry*, Springer Proceedings, 10.1007/978-3-031-80692-6_3.
- Garlatti Costa, Pugliese, Venier (2026) Int. J. Value Chain Manag., 10.1504/ijvcm.2027.10078507. Third paper on the same survey as garlatticosta2025doi and garlatticosta2026readiness.
- Calabrese and Falavigna (2022) Int. J. Automot. Technol. Manag. 10.1504/ijatm.2022.126843; Calabrese, Falavigna, Ippoliti (2024) J. Policy Model. 10.1016/j.jpolmod.2024.01.007.
- Romanello and Veglio (2022) Br. Food J. 10.1108/bfj-09-2021-1056 (I4.0 in food processing).
- Agostini and Filippini (2019) Eur. J. Innov. Manag. 10.1108/ejim-02-2018-0030.
- *Firm adoption of Industry 4.0 technologies in times of economic turmoil: the role of enabling factors* (2025) J. Technol. Transf. 10.1007/s10961-025-10263-1. Italian context not checked.
- Jegerson, Passacantilli, Belfanti (2026) Eur. J. Innov. Manag. 10.1108/ejim-05-2026-0720 (routinised GenAI use in SMEs).
- Forgione and Migliardo (2026) Int. J. Innov. Stud. 10.1016/j.ijis.2026.100208 (AI and market power, difference-in-differences).

## 5. Extraction and verification procedure

1. Crossref metadata (title, authors, year, DOI) was stored per record in a scratch file and copied into the extraction exactly. Year = Crossref `published-print` year if present, else `issued`. Online-first year and version read are stated in `notes` where they differ.
2. Full texts were saved under `sources/pdf/<id>*.pdf` whenever an OA copy was reachable. Suffixes mark non-VoR versions: `_wp`, `_preprint`, `_qef572`, `_nberw*`, `_ecbop395`, `_tpiwp077`, `_ecipe2023`. Page numbers are PDF page numbers of the file actually read (printed page in brackets where it differs).
3. Automated check: every `quote` of a record with a local PDF was string-matched against `pdftotext` output. All prose quotes matched, allowing only for hyphenation and line-order artefacts (one British/US spelling slip was corrected). Quotes taken from tables are row reconstructions: cells are concatenated with "..." and the table number is given in `page`.
4. `verified=true` means every figure was seen in the document or abstract actually opened. Where only the abstract was accessible, `page` = "abstract" and `notes` say so. `verified=false` is used for: figures passed through a summarising HTML fetch tool (shah2026aitransform, leoni2022aikm); abstract-only records where the abstract gives no figures; and metadata-only records.
5. AACODS scores (0/1/2) apply Tyndall (2010) to peer-reviewed items: authority and accuracy are generally 2 for peer-reviewed journals and lower for convenience samples or abstract-only access. `coi.flag` is true where authors are from the policy owner (for example the MEF evaluation of hyper-depreciation) or disclose financial relationships (Brynjolfsson et al.).
6. No em-dashes in any text written. The Crossref title of Xu et al. (2021) contains one and is rendered with a colon in the JSONL and with `---` in BibTeX.

## 6. Outputs

- `sources/extract_peer_reviewed.jsonl`: 52 records, validated with `json.loads` on every line.
- `sources/peer_reviewed.bib`: 52 entries, key = id, fields from Crossref. For the three items without a DOI, metadata come from Open Library or the document itself and are marked in `note`. calvino2023portrait takes author names from the paper because Crossref lists none.
