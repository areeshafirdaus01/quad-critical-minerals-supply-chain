# QUAD Critical Minerals — Supply Chain Resilience Analysis

**Can QUAD build critical mineral supply chain resilience fast enough before China locks in leverage permanently?**

This project examines graphite, cobalt, and lithium import dependency across all four QUAD members (India, USA, Japan, Australia) using six years of UN Comtrade trade data. The central finding: China can weaponize export controls in months; QUAD's alternative supply infrastructure is still years away from operational status.

---

## Key Findings

| QUAD Member | Mineral | China Dependency (2024) |
|---|---|---|
| Japan | Graphite | 87.2% |
| USA | Graphite | 67.4% |
| Australia | Cobalt | 60.0% |
| India | Lithium | 39.4% |

- **No QUAD-collective mineral project has reached operational scale.** The earliest operational dates for any active project are 2027–2028.
- **The QUAD Minerals Framework (announced May 2026) has not yet secured its first investment.**
- **Australia's lithium paradox:** The world's largest lithium miner still exports raw spodumene to China for refining, then re-imports refined lithium — because it lacks domestic refinery capacity.
- **China's 2023 playbook:** Gallium export restrictions (August 2023) caused a 56% price spike within 2 months. Graphite licensing requirements (Oct–Dec 2023) forced emergency stockpiling across QUAD. Three years later, no QUAD member has a credible alternative in place.

---

## Repository Structure

```
quad-critical-minerals-supply-chain/
│
├── raw-data/
│   ├── p3_minerals_quad_china.xlsx       # Raw UN Comtrade import data (China → QUAD, 2019–2024)
│   ├── p3_minerals_quad_world.xlsx       # Raw UN Comtrade import data (World → QUAD, 2019–2024)
├── cleaned-data/
│   └── Minerals_QUAD_Dependency.xlsx     # Cleaned dependency table with CAGR (output)
│
├── notebooks/
│   └── 03data_cleaning.ipynb             # Python: data cleaning, dependency %, CAGR calculation
│
├── dashboard/
│   └── QUAD_dashboard.png                # Power BI dashboard export
│
├── brief/
│   └── Can_QUAD_Build_Critical_Mineral_Supply_Chain_Resilience_Fast_Enough_Before_China_Counteracts.docx
│
└── README.md
```

---

## Methodology

### Data Sources
- **UN Comtrade Database** — Annual import data, 2019–2024, for all four QUAD reporters
- **HS Codes:** `2504` (Natural Graphite), `2822` (Cobalt Oxides & Hydroxides), `282520` (Lithium Oxide & Hydroxide)
- **USGS Mineral Commodity Summaries 2024** — Global production benchmarks
- **Project-level sources:** Ardea Resources DFS reports, METI bilateral tracker, Quad Foreign Ministers' Joint Statement (2026)

### Python Pipeline (`03data_cleaning.ipynb`)
1. Load China-origin and World-origin import datasets separately
2. Concatenate and filter to relevant columns (`refYear`, `reporterDesc`, `partnerDesc`, `cmdCode`, `cifvalue`)
3. Convert CIF values from USD to USD millions
4. Compute **China Dependency %** = China imports / World imports × 100, per country-mineral-year
5. Compute **CAGR (2019–2024)** on dependency percentage to identify trajectory direction

### Visualization
Dashboard built in **Power BI**, featuring:
- KPI cards for peak 2024 dependency figures
- Horizontal bar chart of China import dependency by mineral and QUAD member
- Geopolitical event timeline (2023 export restrictions, 2026 framework announcement)
- Project lifecycle tracker across six active QUAD-adjacent mineral initiatives

---

## Project Lifecycle Snapshot (as of mid-2026)

| Project | Coalition | Status |
|---|---|---|
| QUAD Minerals Framework | US / AUS / JPN / IND | Policy Formulation — no investment secured |
| Alaska Graphite (Graphite One) | US Only | Permitting / Pilot Phase |
| Sumitomo Metal (Nickel/Cobalt) | JPN / US / AUS | Early Construction |
| Alcoa Gallium (Wagerup Refinery) | AUS / US / JPN | Advanced Engineering |
| Kalgoorlie Nickel (Ardea Resources) | AUS / US / JPN | DFS Finalization Phase |
| ATLAS Neves Lithium | BRA / JPN / US | Mechanical Assembly |

*No project has reached operational status at scale. The gap between policy announcement and physical output remains 4–6 years minimum.*

---

## Tools & Skills Demonstrated

- **Python** — `pandas` (data cleaning, merging, aggregation, CAGR modelling)
- **Power BI** — dashboard design, KPI cards, horizontal bar charts, event timelines
- **UN Comtrade** — API-sourced trade data extraction and HS code filtering
- **Geoeconomic analysis** — export control risk, supply chain chokepoint identification, multilateral resilience gap analysis
- **Policy brief writing** — structured analytical writing for a non-technical audience

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/quad-critical-minerals-supply-chain.git
cd quad-critical-minerals-supply-chain

# Install dependencies
pip install pandas openpyxl jupyter

# Open the notebook
jupyter notebook notebooks/03data_cleaning.ipynb
```

The notebook reads from `data/` and exports the cleaned dependency table to `Minerals_QUAD_Dependency.xlsx`.

---

## Context

This is **Project 2** in a geoeconomic risk analysis portfolio. Project 1 examined the India–Korea semiconductor supply chain using bilateral Comtrade data and built a disruption cost model estimating $307M in monthly losses at a 25% supply reduction scenario.

Both projects follow the same pipeline: raw Comtrade data → Python cleaning → analysis → Power BI visualization → written brief.

---

## Author

**Areesha Firdaus** — Geoeconomic Risk Research  
*BBA graduate building a portfolio at the intersection of trade data, supply chain risk, and Indo-Pacific policy.*

[LinkedIn](www.linkedin.com/in/areesha-firdaus1055) · [Substack](https://areeshafirdaus.substack.com/) 

---

*Data sourced from UN Comtrade (public). All analysis and views are the author's own.*
