# Search log: layer "thinktank_consulting"

> **Nota (02-10-2026).** Questo log documenta la ricerca al momento in cui fu eseguita. Alcune affermazioni sullo stato di verifica sono state superate: i testi completi di Minsait-TEHA 2025, TEHA 2026 (AI Skills 4 Agents), Brey e van der Marel 2024, Chatterjee et al. 2021, Cohen e Levinthal 1990, Baker 2012 e Tornatzky e Fleischer 1990 sono stati ottenuti il 1 ottobre 2026 e le relative schede ri-verificate (`sources/catalog.csv`, campo `verified`, fa fede).


Date of searches: 2026-09-29 / 2026-09-30 (single session).
Output: `sources/extract_thinktank_consulting.jsonl` (26 records, validated with python json).
PDFs saved in `sources/pdf/` (ids as filenames). Page numbers are PDF page numbers unless noted; HTML sources cite section headings.

## Access notes
- mckinsey.com, bcg.com, weforum.org (publication pages) and cepr.org block automated requests (Akamai / Cloudflare 403). Retrieved through the Internet Archive (web.archive.org) where possible; this is flagged in each record's `notes`.
- Registration-gated reports not retrieved at the time of this search: EY Italy AI Barometer 2025 full PDF, Accenture "Europe's AI Reckoning" full report. Minsait-TEHA 2025 was retrieved later and is verified in `sources/catalog.csv`.
- rand.org PDF needed browser headers (first attempt returned CloudFront 403).

## Queries (web search tool unless stated)
1. `RAND report AI adoption manufacturing firms survey 2024 2025` (domain rand.org)
2. `McKinsey "The state of AI in 2025" agents innovation transformation pdf respondents`
3. `Deloitte "State of AI in the Enterprise" 2026 report respondents countries`
4. `Deloitte "AI ROI" paradox rising investment elusive returns Europe 2025 Italia aziende`
5. `Deloitte Italia intelligenza artificiale ROI aziende italiane survey 2025 comunicato stampa`
6. `Deloitte 2026 Manufacturing Industry Outlook AI agentic smart manufacturing survey respondents`
7. `Deloitte "2025 Smart Manufacturing" survey 600 executives agentic AI data analytics results`
8. `McKinsey Global Institute "A new future of work" race to deploy AI raise skills Europe 2024 pdf Italy`
9. `World Economic Forum Global Lighthouse Network 2025 report Italy lighthouse factory AI`
10. `Global Lighthouse Network Italian site Italy plant named lighthouse World Economic Forum stabilimento italiano`
11. `Rold Cerro Maggiore World Economic Forum Lighthouse PMI italiana`
12. `The European House Ambrosetti Microsoft "AI 4 Italy" rapporto pdf imprese manifattura intelligenza artificiale generativa`
13. `The European House Ambrosetti Microsoft 2025 studio intelligenza artificiale imprese italiane adozione survey Cernobbio`
14. `Minsait "The European House" "stato dell'arte dell'Intelligenza Artificiale nelle aziende italiane" 2025`
15. `BCG "AI at Work 2025" momentum builds countries Italy respondents frontline`
16. `EY European AI Barometer 2025 Italy results respondents pdf`
17. `"EY Italy AI Barometer 2025" 539 lavoratori italiani 46% comunicato EY newsroom`
18. `PwC 29th Global CEO Survey 2026 Italia CEO italiani intelligenza artificiale ricavi costi`
19. `Capgemini Research Institute 2025 report manufacturing AI industrial operations survey countries Italy respondents`
20. `Microsoft AI Economy Institute AI diffusion report 2025 country ranking Italy share working-age population using AI`
21. `VoxEU CEPR column AI adoption Italian firms productivity survey 2024 2025` (domain cepr.org)
22. `"Embracing AI in Europe: New evidence from harmonised central bank business surveys" authors`
23. `Bruegel 2025 AI adoption European firms manufacturing policy brief diffusion` (domain bruegel.org)
24. `Accenture Italia ricerca 2025 intelligenza artificiale aziende italiane manifattura reinvention dati Italia`
Direct fetches (curl / Wayback): RAND RR-A2680-1 landing page and PDF; Deloitte global State of AI page (links to global and ERI PDFs); Deloitte CH AI in Manufacturing page and PDF; WEF www3/reports PDFs (GLN 2019, 2025, 2026); arXiv 2511.15080 (Anthropic Economic Index).

## Counts
- Candidates identified: 41
- Screened (opened): 34
- Included: 26
- Excluded after screening: 8
- Identified but not screened (time/priority, or no open access): 7

## Included (26)
| id | reason for inclusion |
|---|---|
| rand2024failure | Target source; barriers/root causes; flags misattributed ">80% fail" figure |
| mckinsey2025stateai | Target; global benchmark with manufacturing function/industry cuts, scaling and EBIT |
| deloitte2026stateai | Target; Italy n=75 disclosed; adopters-only design (methodological red flag) |
| deloitte2026stateai_eri | Industrials cut of the same survey (closest Deloitte manufacturing proxy) |
| deloitte2025airoi | Target; European ROI survey incl. Italy |
| deloitte2026stateai_it | Deloitte Italia press release with Italy-specific figures |
| deloitte2026aimanuf | Manufacturing-only Deloitte survey 2026 (use cases, barriers) |
| deloitte2025smartmfg | US large-manufacturer benchmark (AI/ML at facility scale) |
| mgi2026agents | MGI Europe report with Italy dashboard, manufacturing share of automation value |
| wef2025gln | Lighthouse network AI use-case shares, selection-bias case |
| wef2026gln | Latest Lighthouse white paper (gen AI 9% to 23% of top use cases) |
| wef2019beacons | Only Italian lighthouse cases (Rold SME, Bayer Garbagnate) |
| teha2023ai4italy | Target (TEHA with Microsoft); Italy gen AI survey and +18% GDP upper bound |
| minsaitteha2025aiitaly | Italy large-firm survey (280 firms); full PDF retrieved later and verified in `sources/catalog.csv` |
| bcg2024value | Target; 4% / 22% / 74% value tiers; barriers |
| bcg2025aiatwork | Target; Italy n=1,011 employees; manufacturing workflow redesign |
| ey2025aibarometer | European worker barometer incl. Italy; manager vs employee perception gap |
| ey2025italybarometer | Italy-specific results (n=539) |
| pwc2026ceoitaly | Italy vs global CEO comparison (n=118 Italy) |
| capgemini2025genai | Target; manufacturing gen AI maturity; Italy ~5% of sample |
| microsoft2026aidiffusion | Contains Italy country data (individual gen AI diffusion) |
| voxeu2026centralbanksai | Harmonised Bank of Italy/Bundesbank/Banco de Espana surveys; Italy vs DE/ES incl. manufacturing |
| voxeu2026bickgap | Worker gen AI adoption, Italy lowest of 7 countries; management practices |
| voxeu2026aldasoro | Causal EU firm-level productivity/employment effects (EIBIS) |
| bruegel2021aiadoption | Measurement divergence 7% vs 42% explained by response rates and taxonomy (RQ5 anchor) |
| accenture2025aireckoning | Accenture Italia release; large-firm scaling gap; Italy behind on capabilities |

## Excluded after screening (8)
| candidate | reason |
|---|---|
| Deloitte 2026 Manufacturing Industry Outlook (US) | Relays third-party US surveys (NAM, MLC); no primary AI data; US only |
| Capgemini-Microsoft "The New AI Imperative in Manufacturing" (2025 whitepaper) | Vendor whitepaper, no survey methodology, figures from own experience (PDF downloaded then removed) |
| Anthropic Economic Index report "Uneven geographic and enterprise AI adoption" (Sept 2025, arXiv 2511.15080) | No Italy or manufacturing data found in text (PDF downloaded then removed) |
| RAND commentary "AI Is Making Jobs, Not Taking Them" (2025) | US-only commentary, no firm adoption data for Italy/manufacturing |
| RAND RR-A5043-1 (AI developer firms dataset) | Supply side (AI developers), not adopters |
| WEF "Adopting AI at Speed and Scale" (2023) | Superseded by 2025/2026 GLN white papers; no Italian site |
| Accenture Technology Vision 2025 (Italy coverage) | Vision/trend piece; Italian figures (33%, 88%) not traceable to disclosed sample |
| Sky TG24 article (March 2026) on Accenture | Secondary press; used only to identify the Accenture study; the "8% of projects at scale" claim not verified in a primary document |

## Identified but not screened / not accessible (7)
| candidate | status |
|---|---|
| McKinsey State of AI early 2024 and March 2025 editions | Not retrieved (mckinsey.com blocks automated access); trend n values cited from 2025 edition p.9 |
| MGI "A new future of work" (May 2024) and "Time to place our bets: Europe's AI opportunity" (2024) | Not screened; superseded for Italy by MGI 2026 country dashboard |
| KPMG (global/Italy AI surveys) | Not screened (time); to consider in a later pass |
| IDC / Gartner | Mostly paywalled market estimates; not screened |
| Brookings | No Italy/manufacturing-specific item identified in time |
| Microsoft AI Diffusion Report Q1 2026 (May 2026) | Identified; H2 2025 edition used instead |
| EY Italy AI Barometer 2025 full report; Minsait-TEHA full PDF; Accenture "Europe's AI Reckoning" full PDF | Registration-gated; press releases / publisher pages used |

## Main methodological red flags noted across the layer (for RQ5)
- Adopters-only sampling (Deloitte State of AI 2026, Deloitte AI ROI 2025): no prevalence can be inferred.
- Large-firm frames (Capgemini >USD 1bn; Deloitte smart manufacturing >USD 500m; Accenture >EUR 1bn; Minsait >250 employees) vs an Italian manufacturing base dominated by SMEs.
- Individual-level usage (BCG AI at Work, EY Barometer, Microsoft diffusion, Bick et al.) vs firm-level adoption (Istat/Eurostat, central-bank surveys): levels differ by an order of magnitude.
- Undisclosed response rates and recruitment; Bruegel shows a 7% response rate can inflate AI adoption from about 7% to 42%.
- Self-reported impact (EBIT, ROI, productivity) by AI-involved executives; EY shows managers report productivity gains far more often than employees (57% vs 35%).
- Definitional slippage: "physical AI" and Industry 4.0/IoT cases counted as AI (Deloitte ERI, WEF Rold case).
- Small Italian cells: Deloitte n=75, PwC n=118, Capgemini about 55 organisations.
- Internal inconsistencies: Deloitte Italy agentic AI use (~70%) above gen AI use (62%); EY Italy "+34%" is a percentage-point change.
