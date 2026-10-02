# ISTAT sources in this folder (downloaded 2026-09-30)

All tables come from the ISTAT survey "Rilevazione sulle tecnologie dell'informazione e della comunicazione nelle imprese" (the Italian part of the Eurostat ICT-ENT survey), enterprises with 10 or more persons employed, NACE C-N excluding K, including 95.1. Values coincide with the Eurostat dissemination (isoc_eb_ai, isoc_eb_ain2) wherever both publish the cell.

| File | Release | Reference year | Tables used | Breakdowns |
|---|---|---|---|---|
| `Tavole-ICT-imprese_2023.xlsx` | Imprese e ICT, anno 2023 (Dec 2023), https://www.istat.it/wp-content/uploads/2023/12/Tavole-ICT-imprese_2023.xlsx | 2023 | 9a (technologies), 9b (business functions), 9c (barriers) | sector incl. 9 manufacturing groups; macro-area and size class economy-wide only |
| `Tavole-ICT-imprese_2024.xlsx` | Imprese e ICT, anno 2024 (Jan 2025), https://www.istat.it/wp-content/uploads/2025/01/Tavole-ICT-imprese_2024.xlsx | 2024 | 9a, 9b | as above (no 9c in 2024) |
| `Tavole-ICT-imprese_2025.xlsx` | Imprese e ICT, anno 2025 (Dec 2025), https://www.istat.it/wp-content/uploads/2025/12/Tavole-ICT-imprese_2025.xlsx | 2025 | 9a, 9b, 9c | as above; 9a has 8 technologies (media generation added) |
| `asi2024/D21/C21_Tavole_2024.xlsx` | Annuario statistico italiano 2024, cap. 21, https://www.istat.it/storage/ASI/2024/dati/D21.zip (PDF chapter: `sources/pdf/asi2024_c21.pdf`, tables pp. 797-799) | 2023 | 21.15 (macro-sector x size class x technology), 21.16 (activity x technology) | manufacturing x 4 size classes (10-49, 50-99, 100-249, 250+) |
| `asi2025/D21/C21_Tavole.xlsx` | Annuario statistico italiano 2025, cap. 21, https://www.istat.it/storage/ASI/2025/dati/D21.zip (PDF chapter text: `sources/pdf/asi2025_c21.pdf`) | 2024 | 21.15, 21.16 | as above |

`istat_ai_tables.csv` (built by `scripts/extract_istat.py`) holds every cell in long format with: source, year, breakdown (sector / area / size / macro_sector_x_size), label, ATECO scope, size, area, family (adoption / technology / function / barrier / consideration / intensity), variable, denominator, value.

## Denominators (critical)
- `adoption` (`ai_any`) and `intensity` (`ai_ge2`, `ai_ge3`): % of all enterprises (10+) in the row population.
- `technology`: % of enterprises **using AI** in the row population (ISTAT header says "valori percentuali sul totale delle imprese con 10 addetti e oltre" but the technology columns are shares of AI users, as the ISTAT text states: "Le tecnologie più diffuse tra le imprese che utilizzano IA"; the Eurostat ratios E_AI_Txx / E_AI_TANY reproduce them exactly).
- `function` (tables 9b): % of enterprises **using AI** in the row population (header: "valori percentuali sul totale delle imprese con almeno 10 addetti che utilizzano sistemi di IA").
- `barrier` (tables 9c): % of non-AI enterprises **that considered AI**; `considered_ai`: % of non-AI enterprises.

## Terminology
In the Annuario and in the 2023 release ISTAT calls the seven Eurostat AI technology items "finalità"; they are technologies (text mining ... autonomous machines), not the business functions ("aree aziendali") of tables 9b. `workflow_automation` (RPA / decision support) is a technology; `production_processes` is a business function. In 2023 both happen to be 52.4-52.5% of manufacturing AI users; they are different variables.

## ATECO aggregates used by ISTAT (never split)
C10-C12; C13-C15; C16-C18; C19-C23; C24+C25 (metallurgy and metal products); C26; C27+C28 (electrical equipment and machinery n.e.c.); C29+C30 (transport equipment); C31-C33. C28 alone is not published by ISTAT; Eurostat published C27 and C28 separately for Italy only in 2021 (C28: 12.1%).

## Cells not published (checked 2026-09-30)
- manufacturing x size class for 2025 (ASI 2026 not yet published; release tables give size classes economy-wide only);
- manufacturing x macro-area (any year): release tables give macro-areas economy-wide only;
- manufacturing x size class x business function, manufacturing x size class x barriers (any year);
- C28, C24, C25, C27, C29, C30 separately (2023-2025).
