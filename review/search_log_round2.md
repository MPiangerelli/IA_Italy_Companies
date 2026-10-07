# Search log: round 2 (KPMG, IDC, Gartner, McKinsey round 2, BCG/PwC/TEHA updates, Anitec-Assinform, AGCOM, OECD)

> **Nota (02-10-2026).** Questo log documenta la ricerca al momento in cui fu eseguita. Alcune affermazioni sullo stato di verifica sono state superate: i testi completi di Minsait-TEHA 2025, TEHA 2026 (AI Skills 4 Agents), Brey e van der Marel 2024, Chatterjee et al. 2021, Cohen e Levinthal 1990, Baker 2012 e Tornatzky e Fleischer 1990 sono stati ottenuti il 1 ottobre 2026 e le relative schede ri-verificate (`sources/catalog.csv`, campo `verified`, fa fede).


Date of searches: 2026-09-30 (single session).
Output: `sources/extract_round2.jsonl` (24 records, validated with python json; 23 verified=true, 1 verified=false).
Layers: 21 records `thinktank_consulting`, 3 records `institutional` (Anitec-Assinform, AGCOM, OECD).
New PDFs saved in `sources/pdf/` (14 files): kpmg2025pulseq3, kpmg2026pulseq3, kpmg2026techreport, kpmg2026techreport_im, kpmg2025ceoitaly, kpmg2025ceoima, idc2024msftai, mckinsey2024stateai, mgi2024futurework, mgi2024placebets, anitec2026digitale, agcom2026ia, oecd2026eucpai_v2. Page numbers are PDF page numbers (Anitec also gives printed page numbers); HTML sources cite section headings or paragraphs.
No existing file was modified; ids in `extract_thinktank_consulting.jsonl`, `extract_institutional.jsonl` and `extract_peer_reviewed.jsonl` were checked for duplicates (none).

## Access notes
- gartner.com newsroom: Cloudflare challenge (403) for both WebFetch and curl; all five Gartner releases were read through the Internet Archive (`web.archive.org/web/2026id_/<url>` with curl). The 5 August 2026 release on CSCOs unclear about AI ROI is NOT archived and could not be read.
- mckinsey.com and mckinsey.de PDFs: direct curl fails (connection reset); retrieved from Internet Archive snapshots (State of AI early 2024 v3 PDF; MGI "A new future of work" PDF hosted on mckinsey.de; "Time to place our bets" PDF, March 2025 snapshot).
- oecd.org: chapter HTML returns 403; read via Internet Archive (15 Sept 2026 snapshot); the full-report PDF downloaded directly from the oecd.org content server (no block). DOI 10.1787/3ac96d41-en verified on Crossref (issued 2026-02-18).
- bcg.com press pages: WebFetch works, curl is blocked (Akamai). Full Italian text obtained through WebFetch.
- pwc.com/it: WebFetch 403; page read via Internet Archive (April 2026 snapshot); the linked PDF `2026-report-integrazione-ia.pdf` returns 403 and is not archived.
- my.idc.com: WebFetch 403; curl with a browser user agent works. The 2024 European release (prEUR252670624) now returns 404; the March 2025 and September 2026 releases were read in full.
- kpmg.com: open; the KPMG-Ipsos Italy report and the KPMG Italy landing page for the IM sector cut require a lead form, but the global sector-cut PDF is public on the KPMG Ireland site.
- ambrosetti.eu: at the time of this search the AI Skills 4 Agents study PDF was behind a login, so only the landing page and the Microsoft Italia press release were readable. The full PDF was retrieved later and is verified in `sources/catalog.csv`.
- industriaitaliana.it returns HTTP 402 (paywall) to WebFetch.

## Queries (web search tool unless stated)
1. `KPMG Italia intelligenza artificiale imprese italiane survey 2025 adozione barriere`
2. `KPMG "AI Quarterly Pulse Survey" 2025 pdf respondents agents deployment`
3. `IDC Italia comunicato stampa 2025 intelligenza artificiale spesa Italia imprese manifatturiero`
4. `Gartner press release survey "manufacturing" AI adoption 2025 respondents supply chain generative AI`
5. `KPMG CEO Outlook 2025 Italia CEO italiani intelligenza artificiale investimenti percentuale comunicato`
6. `KPMG "Global Tech Report 2025" survey respondents countries AI adoption value pdf`
7. `KPMG 2025 industrial manufacturing survey AI "manufacturing" CEOs executives report pdf "Global Manufacturing Prospects" OR "Intelligent manufacturing"`
8. `IDC EMEA 2025 2026 press release AI adoption Italy "Italian" organizations survey percent generative AI spending Italia`
9. `IDC "Italia" intelligenza artificiale 2026 mercato spesa miliardi previsione "IDC" comunicato imprese italiane AI adozione`
10. `IDC blog press release 2026 "AI" spending Europe manufacturing "discrete manufacturing" Worldwide AI Spending Guide` (domains idc.com, my.idc.com, blogs.idc.com)
11. `IDC Microsoft "AI opportunity" OR "Business Opportunity of AI" 2024 2025 Italy Italian organizations ROI survey respondents`
12. `IDC "European" AI spending "$470 billion" 2030 agentic press release September 2026 manufacturing Italy`
13. `McKinsey "The state of AI in early 2024" gen AI adoption spikes pdf 1,363 participants`
14. `McKinsey Global Institute "Time to place our bets" Europe's AI opportunity 2024 pdf`
15. `McKinsey Italia intelligenza artificiale manifattura "Made in Italy" 2025 OR 2024 report imprese italiane produttivita IA generativa`
16. `McKinsey Global Institute "A new future of work" race to deploy AI raise skills Europe 2024 pdf Italy`
17. `Anitec-Assinform "Il Digitale in Italia 2026" intelligenza artificiale mercato imprese pdf`
18. `AGCOM "Intelligenza Artificiale" rapporto tecnico-economico 2026 imprese adozione pdf`
19. `The European House Ambrosetti 2025 2026 intelligenza artificiale imprese italiane studio survey adozione manifattura "TEHA"`
20. `OECD "artificial intelligence" manufacturing chapter 2025 2026 firm adoption "Measuring AI adoption" OR "AI in manufacturing" report iLibrary`
21. `"62,9 miliardi" intelligenza artificiale manifattura italiana competenze "86,7%" Ambrosetti OR TEHA`
22. `TEHA Ambrosetti Microsoft "AI Skills 4 Agents" OR "AI 4 Italy" 2025 Cernobbio studio imprese italiane survey risultati percentuale adozione`
23. `PwC Italia 2025 OR 2026 manifattura intelligenza artificiale survey imprese manifatturiere italiane "PwC" industrial manufacturing AI adozione percentuale`
24. `Bain Italia OR "Bain & Company" 2025 2026 intelligenza artificiale aziende italiane survey manifattura adozione risultati CEO italiani`
25. `BCG Italia 2025 OR 2026 "AI Radar" OR "AI at Work" Italia aziende italiane percentuale valore scalare intelligenza artificiale comunicato stampa`
26. `Accenture Italia 2026 ricerca intelligenza artificiale imprese italiane manifattura "Pulse of Change" OR "Reinvention" Italia risultati percentuale`
27. `newsroom.accenture.it 2026 "Pulse of Change" intelligenza artificiale leader europei 81% investimenti 22% valore`
28. `KPMG "Global tech report 2026" "industrial manufacturing" 258 tech leaders pdf kpmg.com/xx`
Direct fetches: Gartner newsroom (5 releases via Wayback), KPMG US Pulse article and press page, KPMG Italy CEO Outlook press PDF, KPMG IM&A CEO Outlook PDF, KPMG Global tech report PDF and IM cut PDF (Ireland mirror), IDC releases (my.idc.com, idc.com), IDC-Microsoft InfoBrief PDF (hubspot mirror of the Microsoft-distributed file), McKinsey/MGI PDFs (Wayback), Anitec-Assinform PDF (matricedigitale.it mirror), AGCOM Part I and Part II PDFs, OECD Volume 2 PDF, TEHA landing page, Microsoft Italia press release, BCG press pages, PwC insight page (Wayback), Accenture Italia newsroom index (empty listing).

## Counts
- Candidates identified: 46
- Screened (opened, at least landing page): 36
- Included: 24
- Excluded after screening: 9
- Identified but not screened / not accessible: 13 (some overlap with excluded, see tables)

## Included (24)
| id | layer | reason for inclusion |
|---|---|---|
| gartner2024genaiabandon | thinktank_consulting | The much-quoted "30% of gen AI projects abandoned" figure: a forecast, not a measurement; self-reported benefit averages (n=822) |
| gartner2025aimaturity | thinktank_consulting | Persistence of AI projects in production (45% vs 20%), barriers by maturity; n=432, six countries (no Italy) |
| gartner2025mfgstrategy | thinktank_consulting | Manufacturing-only survey (n=128): two-thirds not redesigning operations for AI/robotics |
| gartner2026aisupplychain | thinktank_consulting | Barriers to scaling AI (legacy integration 56%, talent 50%); n=140, revenue >= USD 250m |
| gartner2026scorchestration | thinktank_consulting | Depth indicator: 17% transformational vs 83% incremental AI use (same panel) |
| kpmg2024italyai | thinktank_consulting | Target: KPMG-Ipsos survey of 150 large Italian firms (43% with AI projects) |
| kpmg2025ceoitaly | thinktank_consulting | Target: KPMG CEO Outlook 2025 Italian release with Italy cut (64% AI priority, 38% AI in operations) |
| kpmg2025ceoima | thinktank_consulting | Target: industrial manufacturing CEO cut (n=120 IM), Italy among 11 markets, agentic AI expectations |
| kpmg2026techreport | thinktank_consulting | Target: KPMG global tech report; at-scale AI with ROI fell 31% to 24% while 68% expect top maturity by 2026 |
| kpmg2026techreport_im | thinktank_consulting | Target: industrial manufacturing cut (n=258, >USD 1bn): 49% active AI value; use cases; data contradiction 83% vs 76% |
| kpmg2026pulseq3 | thinktank_consulting | Target: AI Quarterly Pulse (US, USD 1bn+): agent deployment and ROI trend; n undisclosed |
| idc2024msftai | thinktank_consulting | Target (IDC, Microsoft-sponsored): 3.7x ROI claim with disclosed cell sizes incl. manufacturing and Western Europe |
| idc2025europeai | thinktank_consulting | Target (IDC EMEA, Milan): European AI spending forecast; 87% of European firms allocating up to 30% of AI budget to GenAI |
| idc2026europeai | thinktank_consulting | Target (IDC EMEA, Milan, Sept 2026): USD 470bn by 2030; forecast revision vs 2025 |
| mckinsey2024stateai | thinktank_consulting | Target: State of AI early 2024 for time comparison (72% adoption, 8% in 5+ functions, manufacturing function 4%) |
| mgi2024futurework | thinktank_consulting | Target: MGI 2024; Italy in model and survey (n=201 of 1,128); manufacturing employment scenario |
| mgi2024placebets | thinktank_consulting | Target: MGI/QuantumBlack 2024; EU-US 45-70% adoption gap defined through spending; USD 575bn potential |
| bcg2026aiatwork_it | thinktank_consulting | BCG Italy 2026: worker-level use 62% Italy vs 74% global; agents; redesign effect |
| bcg2026airadar_it | thinktank_consulting | BCG Italy 2026: 1.7% of revenue in AI; industry lowest (0.8%); 100 Italian executives but no Italian figures |
| pwc2026ceoitaly_ai | thinktank_consulting | PwC Italy 2026 AI focus: only 1% of Italian CEOs see economic benefits; 82% no revenue change; roadmap 24% vs 51% |
| teha2026aiskills | thinktank_consulting | TEHA-Microsoft 2026 update: manufacturing 62.9 bn EUR potential; 86.7% skills shortage; full PDF retrieved later and verified in `sources/catalog.csv` |
| anitec2026digitale | institutional | Target (retry succeeded): Italian AI market 1.38 bn EUR (+47.6%); industrial CIO survey (AI 70.5%); AI-project objectives (n=108) |
| agcom2026ia | institutional | Target: AGCOM 2026 technical-economic report; no firm adoption data (documented gap); Italy private AI investment 1.3 bn USD |
| oecd2026eucpai_v2 | institutional | Target (retry succeeded): OECD "AI in manufacturing" chapter; EU manufacturing 7% to 11% (2021-2024); sub-industry pattern; sourcing of AI |

## Excluded after screening (9)
| candidate | reason |
|---|---|
| AGCOM Intelligenza Artificiale 2026, Part II (Comitato IA, 194 pp.) | Screened by keyword: no firm-adoption, SME or manufacturing data; governance and rights focus |
| IDC Italy landing page (idc.com/eu/italy) | Lists only global infrastructure figures; no Italy-specific adoption or spending release |
| IDC blog "Worldwide AI and Generative AI Spending: Industry Outlook" | Global market model without Europe/Italy/manufacturing detail in the open text |
| Accenture "Pulse of Change" (Sept 2026 and Jan 2026 waves, European C-suite) | No primary Accenture document accessible (newsroom index empty, industriaitaliana paywalled); only secondary press (teleborsa, digitalworlditalia) with 81% / 22% figures; not included per the round-1 rule on secondary press |
| ai4business.it article on TEHA/ANIE "Verso una nuova competitivita industriale europea" | Secondary press; figures are skills/green-skills statistics, not AI adoption |
| Microsoft Italia press release "Microsoft Elevate" (5 Sept 2025) | Used only as supporting source for teha2026aiskills (adoption 51% to 84.7%, agentic 2.3%); not a standalone record |
| mark-up.it and inno3.it articles on McKinsey 2024 / MGI 2026 | Secondary press; primary documents already in the corpus (mckinsey2024stateai, mgi2026agents) |
| KPMG US AI Pulse press page (Q4 2024, Jan 2025) | Superseded by the Q3 2025 and Q3 2026 PDFs; used only to document the sample size (100 US leaders) in notes |
| helpnetsecurity / pressreleasepoint copies of the IDC Sept 2026 release | Secondary; replaced by the primary idc.com release |

## Identified but not screened / not accessible (13)
| candidate | status |
|---|---|
| Gartner "Majority of Chief Supply Chain Officers Unclear on AI Investment Returns" (5 Aug 2026) | Not archived by the Internet Archive; gartner.com blocked |
| Gartner "55% of Supply Chain Leaders Expect Agentic AI to Reduce Entry-Level Hiring" (Feb 2026, n=509) and "AI and GenAI Top Digital Supply Chain Investment Priorities" (Oct 2024) | Identified; not screened (time); employment-expectation and priority surveys, no manufacturing adoption figures in the snippets |
| Gartner "54% of I&O Leaders Adopting AI to Cut Costs" (Oct 2025) | Not screened; IT-operations focus |
| KPMG-IKN "AI Maturity & Ambition" survey (Italy) | Identified; not screened (IKN event page, no methodology visible) |
| KPMG CEO Outlook 2025 global report PDF (full) | Not retrieved; methodology taken from the IM&A sector PDF (same survey) |
| KPMG-Ipsos "L'IA nelle aziende italiane" full report | Lead-form gated (connect.kpmg.it); landing page used |
| PwC Italy "Hopes and Fears 2026" (53% of Italian workers use AI) and "AI, la grande ricerca" PDF | Not screened (worker-level; time) |
| PwC "2026-report-integrazione-ia.pdf" | 403 and not archived; page used instead |
| Bain & Company Italy | No Italy/manufacturing survey document found for 2023-2026 (only a 2023 global AI market release) |
| BCG "AI at Work 2026" and "AI Radar 2026" full reports | Not retrieved; Italian press releases used (bcg.com publication pages block automated access) |
| TEHA "AI Skills 4 Agents Observatory" study PDF | Login-gated on ambrosetti.eu |
| Anitec-Assinform official PDF on anitec-assinform.it | Landing page only; press mirror PDF used (identical title, 227 pp.) |
| McKinsey Operations / Global Lighthouse Network manufacturing AI pieces with Italian sites | Not searched again this round (covered by wef2019beacons, wef2025gln, wef2026gln in round 1) |

## Main methodological red flags noted this round (for RQ5)
- Forecast-as-fact: Gartner's "30% of gen AI projects abandoned" is a prediction with no disclosed method; RAND's ">80% fail" (round 1) is likewise second-hand.
- Sample size not disclosed: KPMG AI Pulse PDFs (US, about 100), TEHA 2026, Anitec CIO Survey industrial cell (about 44 by inference), KPMG Italy CEO Outlook Italian cell; IDC 2024 European survey behind the 87% figure.
- Country cells announced but not reported: BCG AI Radar 2026 (100 Italian executives, zero Italian figures); MGI 2024 (201 Italian executives, no Italian results); KPMG IM&A (Italy among 11 markets, no cut).
- Revenue thresholds far above the Italian manufacturing base: KPMG tech report > USD 100m (main) but > USD 1bn (IM cut; internal inconsistency); KPMG CEO Outlook > USD 500m; KPMG Pulse > USD 1bn; Gartner supply chain >= USD 250m.
- Unit of analysis: BCG 62% of Italian frontline workers use AI regularly and TEHA 84.7% "adoption at any level" versus Istat 16.4% of firms; IDC's 78% "adoption" is among AI decision-makers.
- Self-reported ROI: IDC-Microsoft 3.7x per USD 1 (respondent estimate), KPMG 2x average tech ROI, versus PwC Italy where only 1% of CEOs see economic benefits and 82% see no revenue change.
- Depth versus breadth within the consultancy family itself: KPMG at-scale AI with ROI fell from 31% to 24% (2024 to 2025) while 68% expect the top level by 2026; McKinsey 2024 shows 72% adoption but 8% in 5+ functions and manufacturing function use at 4%; Gartner 17% transformational vs 83% incremental.
- Definitional drift over time: McKinsey adoption definition changed in 2017, 2018-19 and 2020; TEHA counts individual use as company adoption; KPMG-Ipsos counts "projects launched".
- Self-assessment contradictions: KPMG IM cut 83% "strong data foundations" vs 76% "unreliable data is a top risk"; KPMG IM&A 74% "employees have right skills" vs 33% "skills gap is the top talent challenge".
- Manufacturing suppressed for small base: McKinsey 2024 does not report manufacturing impact data (p.10); Gartner manufacturing survey n=128.
- Institutional gap: AGCOM's 2026 AI report (332 pages over two parts) contains no measure of enterprise adoption; Anitec-Assinform relies on Istat for adoption and on vendor interviews for spending.


## Note (7 October 2026)
Under the publication cutoff of 31 August 2026 adopted on 7 October 2026, kpmg2026pulseq3 (released 25 September 2026) and idc2026europeai (17 September 2026) were removed from the corpus; reasons in `sources/excluded_after_eligibility.jsonl`.
