# Extraction schema (one JSON object per line in sources/extract_<layer>.jsonl)

Paper: multivocal literature review (MLR) on AI adoption in Italian manufacturing firms.
RQ1 breadth and depth of AI adoption in Italian manufacturing vs EU peers
RQ2 business functions / use cases
RQ3 barriers and enablers (skills, data, leadership, cost, culture, policy)
RQ4 measured effects (productivity, employment, ROI), causal vs self-reported
RQ5 convergence/divergence across source families (definitions, populations, methods)

Fields:
- id: short key, e.g. "istat2025ict", "rand2024failure" (also used as BibTeX key)
- layer: "institutional" | "thinktank_consulting" | "peer_reviewed"
- org: publishing organisation (or journal for peer-reviewed)
- authors: string ("Surname, N.; Surname, N." or organisation)
- title, year (int), doc_type (statistical_release | working_paper | survey_report | policy_report | journal_article | book_chapter | conference_paper | web_page)
- url: canonical landing page (must have been fetched successfully)
- doi: string or null (verify at https://api.crossref.org/works/<doi> when present)
- pdf_local: path under sources/pdf/ if downloaded, else null
- population: who is measured (e.g. "Italian firms with >=10 employees, NACE C-N excl. K")
- sample_n: int or null; geography; fieldwork_period
- method: census | probability_sample_survey | opt_in_survey | exec_survey_commercial | interviews | econometric | case_study | review | market_estimate
- ai_definition: how "AI adoption/use" is operationalised (verbatim or close paraphrase)
- manufacturing_coverage: "explicit_NACE_C" | "sector_breakdown_incl_manufacturing" | "manufacturing_only" | "none"
- findings: list of {metric, value, unit, ref_year, page, quote}. A finding may be qualitative (a definition, a methodological statement, a verbatim assessment): then value/unit/ref_year may be empty and build_catalog.py labels it evidence_type=qualitative in findings.csv. `quote` = short verbatim excerpt (<=40 words) containing the number. `page` = PDF page number or section heading if HTML.
- rq: list, e.g. ["RQ1","RQ3"]
- aacods: {authority, accuracy, coverage, objectivity, date, significance} each 0/1/2
- coi: {flag: bool, note: string} (commercial interest, vendor-sponsored, self-promotional)
- notes: free text (limitations, bias, why relevant)
- verified: true only if you actually opened the document and saw each figure in it; else false and explain in notes

Hard rules: never invent a source, number, DOI, author or page. If you cannot open a document, record it with verified=false. Do not use em-dashes (—) in any text you write.
