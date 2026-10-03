# Supplementary search in Scopus and Web of Science: instructions

Purpose: complement the OpenAlex / Semantic Scholar / Crossref search of the peer-reviewed layer with the two subscription databases, so that the Methods can state that Scopus and Web of Science were searched. Run the queries from the university network (institutional access), export the results, place the files in `data/supplementary_search/`, then run `python3 scripts/import_supplementary.py`: the script de-duplicates the exports against the catalog by DOI and normalised title and writes the list of new candidates to screen.

Date window: 2019-2026 (publication year), as for the main search. Theoretical anchors need no supplementary search. Document types: articles, reviews, book chapters, conference papers (exclude editorials, notes, errata).

## Scopus (Advanced search)

Run each query separately, so that the per-query hit counts can be logged in `notes/search_log_supplementary.md`. Export each result set as **CSV** ("Citation information" + "Abstract & keywords" + "Bibliographical information" ticked; or simply "All available information"), named `scopus_S1.csv` ... `scopus_S6.csv`. Scopus exports up to 2,000 records per CSV; if a query exceeds that, sort by relevance and export the first 2,000, noting it in the log.

S1. AI adoption in Italian firms (core query)
```
TITLE-ABS-KEY ( ( "artificial intelligence" OR "machine learning" OR "generative AI" OR "large language model*" ) AND ( adopt* OR diffus* OR implement* OR use OR usage ) AND ( ital* ) AND ( firm* OR enterprise* OR compan* OR SME* OR manufactur* OR industr* ) ) AND PUBYEAR > 2018 AND PUBYEAR < 2027 AND ( LIMIT-TO ( DOCTYPE , "ar" ) OR LIMIT-TO ( DOCTYPE , "re" ) OR LIMIT-TO ( DOCTYPE , "ch" ) OR LIMIT-TO ( DOCTYPE , "cp" ) )
```

S2. Industry 4.0 adoption and effects in Italian firms
```
TITLE-ABS-KEY ( ( "industry 4.0" OR "industria 4.0" OR "impresa 4.0" OR "transizione 4.0" OR "industry 5.0" OR "smart manufacturing" OR "digital technolog*" ) AND ( ital* ) AND ( adopt* OR productivity OR employment OR incentive* OR "hyper-depreciation" OR iperammortamento OR "tax credit*" ) AND ( firm* OR enterprise* OR SME* OR manufactur* ) ) AND PUBYEAR > 2018 AND PUBYEAR < 2027 AND ( LIMIT-TO ( DOCTYPE , "ar" ) OR LIMIT-TO ( DOCTYPE , "re" ) OR LIMIT-TO ( DOCTYPE , "ch" ) OR LIMIT-TO ( DOCTYPE , "cp" ) )
```

S3. Family firms, industrial districts and the Mezzogiorno
```
TITLE-ABS-KEY ( ( "family firm*" OR "family business*" OR "family manag*" OR "industrial district*" OR district* OR "Southern Italy" OR mezzogiorno OR "made in italy" ) AND ( "industry 4.0" OR "artificial intelligence" OR digitali?ation OR "digital technolog*" OR robot* ) AND ( ital* ) ) AND PUBYEAR > 2018 AND PUBYEAR < 2027
```

S4. Cross-country firm-level AI studies including Italy (Eurostat, EIB, CompNet microdata)
```
TITLE-ABS-KEY ( ( "artificial intelligence" OR "AI adoption" OR "AI adopters" ) AND ( "firm-level" OR microdata OR "ICT survey" OR eurostat OR "EIBIS" OR "investment survey" ) AND ( europe* OR "EU" OR "OECD" OR "cross-country" ) AND ( productivity OR adopt* OR determinant* OR complementar* ) ) AND PUBYEAR > 2018 AND PUBYEAR < 2027 AND ( LIMIT-TO ( DOCTYPE , "ar" ) OR LIMIT-TO ( DOCTYPE , "re" ) )
```

S5. AI adoption in manufacturing SMEs: theory and reviews (TOE, diffusion, absorptive capacity)
```
TITLE-ABS-KEY ( ( "artificial intelligence" OR "AI" ) AND adopt* AND ( SME* OR "small and medium" OR manufactur* ) AND ( "TOE" OR "technology-organization-environment" OR "technology organisation environment" OR "diffusion of innovation*" OR "absorptive capacity" OR "systematic review" OR "literature review" ) ) AND PUBYEAR > 2019 AND PUBYEAR < 2027 AND ( LIMIT-TO ( DOCTYPE , "ar" ) OR LIMIT-TO ( DOCTYPE , "re" ) )
```

S6. Italian-language literature (Scopus indexes some Italian journals; Italian terms)
```
TITLE-ABS-KEY ( ( "intelligenza artificiale" OR "industria 4.0" OR "trasformazione digitale" ) AND ( imprese OR PMI OR manifattur* OR industria* ) AND ( adozione OR diffusione OR produttivit* OR incentiv* ) ) AND PUBYEAR > 2018 AND PUBYEAR < 2027
```

## Web of Science (Core Collection, Advanced search)

Same six queries in WoS syntax (TS = topic: title, abstract, author keywords, Keywords Plus). Set the timespan to 2019-2026 in the interface and refine document types to Article, Review Article and Proceedings Paper (book chapters are indexed only if the subscription includes the Book Citation Index; if a 'Book Chapters' type appears in the Document Types filter, include it, otherwise ignore it). Export as **"Excel"** or **"Tab delimited file"**, "Full Record" content, named `wos_W1.xls` ... `wos_W6.xls` (or `.txt`). WoS exports 1,000 records at a time; export in batches if needed (`wos_W1_a.xls`, `wos_W1_b.xls`).

W1
```
TS=(("artificial intelligence" OR "machine learning" OR "generative AI" OR "large language model*") AND (adopt* OR diffus* OR implement* OR use OR usage) AND ital* AND (firm* OR enterprise* OR compan* OR SME* OR manufactur* OR industr*))
```
W2
```
TS=(("industry 4.0" OR "industria 4.0" OR "impresa 4.0" OR "transizione 4.0" OR "industry 5.0" OR "smart manufacturing" OR "digital technolog*") AND ital* AND (adopt* OR productivity OR employment OR incentive* OR "hyper-depreciation" OR "tax credit*") AND (firm* OR enterprise* OR SME* OR manufactur*))
```
W3
```
TS=(("family firm*" OR "family business*" OR "family manag*" OR "industrial district*" OR district* OR "Southern Italy" OR mezzogiorno OR "made in italy") AND ("industry 4.0" OR "artificial intelligence" OR digitali$ation OR "digital technolog*" OR robot*) AND ital*)
```
W4
```
TS=(("artificial intelligence" OR "AI adoption" OR "AI adopters") AND ("firm-level" OR microdata OR "ICT survey" OR eurostat OR EIBIS OR "investment survey") AND (europe* OR EU OR OECD OR "cross-country") AND (productivity OR adopt* OR determinant* OR complementar*))
```
W5
```
TS=(("artificial intelligence" OR AI) AND adopt* AND (SME* OR "small and medium" OR manufactur*) AND (TOE OR "technology-organization-environment" OR "technology organisation environment" OR "diffusion of innovation*" OR "absorptive capacity" OR "systematic review" OR "literature review"))
```
W6
```
TS=(("intelligenza artificiale" OR "industria 4.0" OR "trasformazione digitale") AND (imprese OR PMI OR manifattur* OR industria*) AND (adozione OR diffusione OR produttivit* OR incentiv*))
```

## Google Scholar (optional, manual)

Google Scholar cannot be exported in bulk. If you want it in the log, run the two short strings below, screen the first 100 results each by title, and note in `notes/search_log_supplementary.md` the date and any relevant paper not already in the catalog (title + DOI). The import script accepts a hand-made CSV with columns `title,doi,year,source` named `gscholar_manual.csv`.
```
"artificial intelligence" adoption Italian manufacturing firms
"industria 4.0" OR "intelligenza artificiale" imprese manifatturiere adozione produttività
```

## What to record for the search log

For each query: database, query id, date, number of hits, number exported. The import script computes identified / already in catalog / new candidates; screening decisions (included / excluded with reason) are then added to `notes/search_log_supplementary.md` and the PRISMA counts in the Methods updated.
