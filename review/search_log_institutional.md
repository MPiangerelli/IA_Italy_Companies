# Search log: institutional layer

Layer: official statistics, central bank, international organisations, EU bodies, public bodies, university observatories, industry associations, bank research departments.
Output: `sources/extract_institutional.jsonl` (28 records). Raw Eurostat API extracts: `sources/eurostat/*.json`. PDFs: `sources/pdf/<id>.pdf`.

## Session 1: 2026-09-29/30

Tools: WebSearch, WebFetch, curl + pdftotext (layout mode; page = PDF page, split on form feed), Eurostat dissemination API (JSON-stat), doi.org and Crossref for DOI checks.
Quotes were machine-checked against the extracted source text (accent/quote-insensitive match, then replaced by the exact source span); all 26 verified records pass.

### Queries used (web search unless stated)

1. ISTAT "Imprese e ICT" 2025 intelligenza artificiale statistica report
2. ISTAT "Imprese e ICT" 2024 intelligenza artificiale 8,2%
3. istat.it Statreport "Imprese e ICT" anno 2023 pdf intelligenza artificiale 5,0%
4. Istat "Rapporto sulla competitività dei settori produttivi" 2025 intelligenza artificiale imprese manifatturiere
5. Istat Rapporto annuale 2026 intelligenza artificiale imprese capitolo produttività
6. istat.it "Rapporto annuale 2026" pdf capitolo 4 conoscenza intelligenza artificiale
7. Istat censimento permanente imprese 2023 intelligenza artificiale imprese 3-9 addetti
8. Eurostat Statistics Explained "Use of artificial intelligence in enterprises" (WebFetch) + Eurostat API: isoc_eb_ai (geo IT, EU27_2020, DE, FR, ES; all indicators 2025), isoc_eb_ain2 (NACE C and subsectors; all indicators for C)
9. JRC report artificial intelligence adoption manufacturing SMEs Europe 2024 2025 (surfaced Eurostat KS-01-26-009 statistical report)
10. Banca d'Italia Questioni di Economia e Finanza 946 intelligenza artificiale imprese
11. Banca d'Italia Questioni di Economia e Finanza 1005 2026 intelligenza artificiale
12. Banca d'Italia Questioni di Economia e Finanza n. 1009 2026
13. Banca d'Italia indagine imprese industriali e dei servizi 2025 intelligenza artificiale industria in senso stretto
14. Banca d'Italia Relazione annuale sul 2025 riquadro "Intelligenza artificiale: adozione ed effetti sulle imprese"
15. bancaditalia.it Considerazioni finali del Governatore 2026 intelligenza artificiale imprese
16. OECD 2025 "AI adoption by small and medium-sized enterprises" G7 discussion paper
17. OECD 2025 "Progress in implementing the European Union Coordinated Plan on Artificial Intelligence" Volume 2 AI in manufacturing Italy
18. "AI in manufacturing" OECD 2025 coordinated plan volume 2 pdf
19. Digital Decade 2025 country report Italy artificial intelligence enterprises take-up pdf (surfaced the 2026 report)
20. EIB Investment Survey 2025 Italy country overview artificial intelligence adoption firms manufacturing
21. Osservatorio Artificial Intelligence Politecnico di Milano 2026 mercato AI Italia grandi imprese PMI progetti
22. osservatori.net comunicato stampa Osservatorio Artificial Intelligence febbraio 2026 1,8 miliardi 71% grandi imprese 8% PMI
23. Intesa Sanpaolo Research "intelligenza artificiale" imprese italiane 2025 rapporto manifattura distretti AI adozione
24. Intesa Sanpaolo "Economia e finanza dei distretti industriali" 2025 intelligenza artificiale imprese distrettuali
25. Centro Studi Confindustria indagine intelligenza artificiale imprese associate 2025 quota adozione manifatturiere
26. Unioncamere Excelsior 2025 competenze intelligenza artificiale richieste imprese assunzioni percentuale
27. Anitec-Assinform "Il Digitale in Italia 2025" intelligenza artificiale mercato manifatturiero
28. anitec-assinform.it "Il Digitale in Italia 2025" rapporto pdf intelligenza artificiale spesa imprese
29. Anitec-Assinform "Il Digitale in Italia 2026" rapporto intelligenza artificiale 1,38 miliardi manifattura industria
30. I-Com Istituto per la Competitività rapporto intelligenza artificiale imprese italiane 2025 adozione
31. MIMIT Transizione 5.0 monitoraggio crediti prenotati imprese dati 2025 2026 GSE
32. Legge 23 settembre 2025 n. 132 intelligenza artificiale Gazzetta Ufficiale normattiva
33. Strategia Italiana per l'Intelligenza Artificiale 2024-2026 pdf AgID imprese PMI obiettivi

### PRISMA-style counts (institutional layer)

| Stage | n |
|---|---|
| Records identified (distinct institutional documents/pages surfaced by queries 1-33 and by citation chasing) | 55 |
| Duplicates / superseded editions removed before full-text screening | 9 |
| Records screened (full text or official landing page opened) | 46 |
| Excluded after screening | 18 |
| Included | 28 (26 verified, 2 recorded as verified=false because full text could not be opened) |

Identification count includes news/aggregator pages that only pointed to an official source (not counted separately when the official source was retrieved).

### Included (28)

istat2025ict, istat2024ict, istat2023ict, istat2026ra, eurostat2026isocebai, eurostat2026aiuse, bdi2025qef946, bdi2026qef1005, bdi2026qef1009, bdi2026invind, bdi2026cf, oecd2025smeai, g7italy2024aimsme, oecd2025cpaiit, ec2026ddcrit, eib2025eibisit, polimi2026osservatorioai, polimi2026osservatoriopmi, isp2025aiimprese, isp2026distretti, srm2025contship, csc2025lavoro, csc2026lavoro, excelsior2025digit, law1322025, agid2024strategia, oecd2026cpaimanuf (verified=false), anitec2026digit (verified=false).

### Duplicates / superseded (removed before screening, 9)

- ISTAT Rapporto annuale 2025 (superseded by 2026 edition; AI content only via key4biz summary).
- ISTAT Censimento permanente delle imprese 2023, primi risultati (reference year 2022, AI 6.2% for 10+; superseded by ICT 2023-2025 series).
- EC Digital Decade 2024 and 2025 country reports Italy (superseded by 2026 report, published 24 Aug 2026).
- Osservatorio AI PoliMi 2024 press release (market +58%, EUR 1.2 bn; superseded by Feb 2026 release).
- Anitec-Assinform Il Digitale in Italia 2025 (superseded by 2026 edition; only third-party mirror found).
- Confindustria Tavole di riepilogo 2025 (PDF link returned HTML; the Nota CSC 4/25 with the same AI data was used).
- Eurostat Statistics Explained page "Use of artificial intelligence in enterprises" (Dec 2025): merged into the eurostat2026isocebai record (definitions, EU context) rather than a separate record.
- BdI Relazione annuale sul 2025, box on AI (content reproduced in QEF 1009 and in the Considerazioni finali; not opened separately).

### Excluded after screening (18) with reasons

1. ISTAT Rapporto sulla competitività dei settori produttivi 2026 (PDF downloaded: `sources/pdf/istat2026comp.pdf`): no AI adoption data; AI only mentioned as a STEP strategic technology.
2. Banca d'Italia Temi di discussione n. 1476 (AI and relationship banking): about banks' credit assessment, not firm adoption.
3. Banca d'Italia QEF n. 1006 (AI and the US economy): not Italy.
4. Banca d'Italia QEF n. 1001 (agentic AI for internal economic reports): not firm adoption.
5. Governor's speech 2 July 2026 "La finanza per l'innovazione e l'IA": duplicate of CF figures, finance-focused.
6. EIB Investment Survey 2025 EU overview: EU-level; the Italy overview was included instead.
7. EC State of the Digital Decade 2025 report: EU-level; Italy country report included.
8. G7 Ministerial Statement on the SME AI Adoption Blueprint (Dec 2025): declaration without data.
9. MIMIT Piano Transizione 5.0 web pages: no accessible take-up statistics (only budget cut from EUR 6.3 bn to 2.5 bn and exhaustion notices reported by secondary sources); T5.0 take-up evidence taken from INVIND (qualitative) and OECD country note (budget).
10. I-Com articles (Apr 2025, Jan 2026, May 2026): secondary re-elaborations of ISTAT/Eurostat figures; no new primary data.
11. Intesa Sanpaolo macro note "intelligenza-artificiale-europa-crescita" (2026): EU macro commentary, no Italian firm data.
12. JRC publications (JRC139772 EDIH readiness; JRC143418 in-house GenAI tools): not Italy- or manufacturing-specific.
13. OECD Progress in implementing the EU Coordinated Plan on AI, Volume 2, overview chapter: not manufacturing-specific (manufacturing chapter recorded as unverified).
14. Unioncamere Excelsior "Previsioni dei fabbisogni occupazionali 2025-2029": occupational forecasts, no firm-level AI adoption data (the Excelsior digital-skills report was included).
15. Osservatorio "IA nelle PMI" (Sardinia, Sept 2026 news): regional initiative announcement, no data.
16. AGCOM "Intelligenza Artificiale, Rapporto tecnico-economico 2026, I parte": surfaced late; screened title/abstract only, market/regulatory focus; flagged for possible inclusion in a later pass.
17. OECD "Closing the Italian digital gap" (Calvino et al., 2022): pre-GenAI, general digital policy paper; better covered by the peer-reviewed/think-tank layers.
18. Secondary press coverage (ANSA, Il Sole 24 Ore, key4biz, digitalworlditalia; counted as one screened record): news coverage of included primary sources, no primary data.

### Could not verify at first pass (records later removed as duplicates, 3 October 2026)

- oecd2026cpaimanuf: OECD page returned HTTP 403 to both WebFetch and curl. Snippet claims (EU manufacturing AI adoption 11% in 2024; Italy 5.2%) not recorded as findings. On 3 October 2026 the author supplied the full PDFs of both volumes: the chapter is part of the report already catalogued as oecd2026eucpai_v2 (identical PDF), so the chapter record was removed; Figure 4.3 shows Italy at about 8% in 2024 (consistent with Eurostat isoc_eb_ain2: 8.0%), so the 5.2% snippet figure was wrong. Volume 1 (Member States' Actions, doi 10.1787/533c355d-en) was added as oecd2026eucpai_v1 (policy stock-taking, RQ3).
- anitec2026digit: official PDF link returned an HTML page. The report was later obtained and catalogued as anitec2026digitale (verified); the duplicate record anitec2026digit was removed.

### DOI checks

- 10.1787/426399c1-en (OECD SME AI): found in Crossref.
- 10.32057/0.QEF.2025.946, 10.32057/0.QEF.2026.1009, 10.2867/9018006 (EIBIS Italy), 10.2785/9221093 (Eurostat 2026 report), 10.2908/ISOC_EB_AI: not in Crossref but resolve via doi.org (other registration agencies); kept.
- 10.32057/0.QEF.2026.1005: printed in the PDF but did not resolve at doi.org on 2026-09-30; set to null.

### Notes for synthesis (RQ5)

- AI definitions differ sharply: ISTAT/Eurostat (8-technology list, 10+ employees, excludes conventional automation); BdI INVIND (includes experimental use, 20+); BdI SIGE (AI "e.g. cloud computing, predictive and/or generative AI, robotics", 50+); Excelsior (>=1 employee, OECD definition); Confindustria (members; 2025 includes pilots, 2026 regular use only); PoliMi (at least one project started; supply-side market); EIBIS (big data and AI bundled; GenAI systematic use; value-added weighted, 5+); Intesa (relationship-manager proxy judgements).
- Barrier measurement diverges by design: ISTAT/Eurostat multi-response among considerers (skills 58.6%) vs Excelsior single main reason among all non-users (lack of staff 2.2%, lack of know-how on how to introduce AI 71.8%).
- Productivity effects diverge: BdI QEF 1005 DiD on SIGE (VA per employee +5.2%) vs BdI QEF 1009 staggered DiD on INVIND (no significant short-run effects).
