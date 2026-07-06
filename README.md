# CitiBike Financial Gap Analysis

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue)](#tools--technologies)
[![DuckDB](https://img.shields.io/badge/DuckDB-SQL-yellow)](#tools--technologies)
[![GeoPandas](https://img.shields.io/badge/GeoPandas-Geospatial-green)](#tools--technologies)
[![Tableau](https://img.shields.io/badge/Tableau-Dashboard-orange)](https://public.tableau.com/app/profile/adrian.lee8470/viz/TableauCitiBikeGapAnalysis/Dashboard1)

## Project Overview

This project analyzes where CitiBike expansion would create the highest mobility, equity, and financial value across New York City. The core question to answer is: 

> **Which underserved neighborhoods have the strongest latent demand for bike share, and can expansion into those areas be financially justified?**

To answer this, I built an end-to-end analytics workflow that combines live CitiBike station data, historical trip data, MTA bus stop locations, NYC neighborhood boundaries, Census ACS demographics, geospatial coverage analysis, demand scoring, and a 10-year financial projection model. The final output is a Tableau dashboard designed to communicate expansion opportunities to both technical and non-technical stakeholders.

**Public Tableau Dashboard:** [CitiBike Financial Gap Analysis](https://public.tableau.com/app/profile/adrian.lee8470/viz/TableauCitiBikeGapAnalysis/Dashboard1)

---

## Why This Project Matters

Bike share systems are often evaluated through ridership alone, but that can reinforce existing service concentration in already-covered, higher-demand neighborhoods. This project takes a broader analytics approach by combining:

- **Mobility access:** identifying neighborhoods without nearby CitiBike coverage.
- **Transit dependence:** prioritizing areas with high public transit and car-free household rates.
- **Equity:** incorporating income and demographic context into expansion scoring.
- **Financial viability:** estimating whether proposed expansion sites can generate enough long-term revenue to offset capital and operating costs.
- **Executive storytelling:** translating spatial and financial modeling into a Tableau dashboard for decision-making.

The result is a data-driven expansion framework that balances public service goals with operational sustainability.

---

## Key Business Questions

This analysis was designed around five stakeholder-facing questions:

1. **Coverage Gap:** Which neighborhoods and Census tracts are currently outside CitiBike’s service footprint?
2. **Demand Opportunity:** Which uncovered neighborhoods have the strongest indicators of bike share demand?
3. **Equity Impact:** Are lower-income, transit-dependent, or car-free communities underserved by the current network?
4. **Expansion Prioritization:** Which neighborhoods should CitiBike prioritize for new stations?
5. **Financial Feasibility:** Under conservative, base, and optimistic ridership scenarios, how quickly could proposed stations break even?

---

## Executive Summary

### Coverage Findings

The analysis identified major CitiBike coverage gaps across NYC using Census tract and neighborhood-level spatial joins.

| Metric | Value |
|---|---:|
| Census tracts analyzed | 2,242 |
| Gap-zone tracts | 1,127 |
| Covered tracts | 1,115 |
| Population in gap zones | 3.83M |
| Neighborhoods analyzed | 197 |
| Gap-zone neighborhoods | 95 |
| Covered neighborhoods | 102 |

At the borough level, Queens and Brooklyn contain the largest uncovered populations, while Staten Island has no CitiBike coverage in the modeled data.

| Borough | Gap Population | % of Borough Population in Gap | Gap No-Vehicle % | Gap Transit Commute % |
|---|---:|---:|---:|---:|
| Staten Island | 492,925 | 100.0% | 16.7% | 25.1% |
| Queens | 1,526,931 | 64.7% | 24.7% | 36.5% |
| Brooklyn | 1,195,051 | 44.6% | 41.6% | 44.8% |
| Bronx | 591,598 | 41.0% | 42.8% | 45.4% |
| Manhattan | 28,105 | 1.7% | 76.7% | 42.4% |

### Expansion Findings

The top 15 expansion candidates represent a portfolio of high-demand, uncovered neighborhoods across the Bronx, Brooklyn, and Queens.

| Portfolio Metric | Value |
|---|---:|
| Top expansion neighborhoods modeled | 15 |
| Proposed new stations | 50 |
| Proposed docks | 1,150 |
| Gap population served by top 15 candidates | 549,466 |
| Total estimated upfront capex | $3.75M |
| Combined estimated 10-year NPV | $15.1M |
| Financially viable neighborhoods | 15 / 15 |
| Modeled break-even timing | Year 3 for all top 15 candidates |

### Top Expansion Candidates

| Rank | Neighborhood | Borough | Demand Score | Gap Population | Proposed Stations | Proposed Docks |
|---:|---|---|---:|---:|---:|---:|
| 1 | Parkchester | Bronx | 0.6699 | 30,221 | 2 | 46 |
| 2 | Brownsville | Brooklyn | 0.6210 | 30,769 | 4 | 92 |
| 3 | East Flatbush-Remsen Village | Brooklyn | 0.5695 | 23,985 | 2 | 46 |
| 4 | Soundview-Bruckner-Bronx River | Bronx | 0.5537 | 46,157 | 4 | 92 |
| 5 | Allerton | Bronx | 0.5393 | 30,576 | 2 | 46 |
| 6 | Cypress Hills | Brooklyn | 0.5309 | 37,786 | 3 | 69 |
| 7 | East New York-City Line | Brooklyn | 0.5229 | 49,066 | 4 | 92 |
| 8 | Jamaica | Queens | 0.4892 | 58,368 | 6 | 138 |
| 9 | East New York-New Lots | Brooklyn | 0.4777 | 53,067 | 6 | 138 |
| 10 | East New York (North) | Brooklyn | 0.4745 | 37,370 | 3 | 69 |
| 11 | Westchester Square | Bronx | 0.4513 | 15,793 | 2 | 46 |
| 12 | Pelham Parkway-Van Nest | Bronx | 0.4478 | 29,915 | 2 | 46 |
| 13 | Soundview-Clason Point | Bronx | 0.4382 | 31,934 | 4 | 92 |
| 14 | Brighton Beach | Brooklyn | 0.4377 | 25,031 | 2 | 46 |
| 15 | Williamsbridge-Olinville | Bronx | 0.4260 | 49,428 | 4 | 92 |

---

## Dashboard Preview

The Tableau dashboard contains interactive views for:

- NYC CitiBike coverage and gap-zone geography.
- Neighborhood-level demand scoring.
- Top expansion candidate ranking.
- 10-year cumulative profit and loss projections.
- NPV and break-even comparisons.
- Sheepshead Bay / Southern Brooklyn deep-dive context.

**View the dashboard here:** [Tableau Public Link](https://public.tableau.com/app/profile/adrian.lee8470/viz/TableauCitiBikeGapAnalysis/Dashboard1)

The packaged Tableau workbook is included as:

```text
Tableau CitiBike Gap Analysis(1).twbx
```

---

## Tools & Technologies

| Category | Tools |
|---|---|
| Programming | Python |
| Data Manipulation | pandas, NumPy |
| SQL / Analytical Engine | DuckDB |
| Geospatial Analysis | GeoPandas, Shapely |
| Data Ingestion | requests, zipfile, JSON, CSV pipelines |
| Data Storage | DuckDB database, CSV exports |
| Visualization | Tableau Public |
| Notebook Environment | Google Colab / Jupyter Notebook |
| Data Sources | CitiBike GBFS, CitiBike historical trip data, MTA GTFS bus stops, NYC boundaries, Census ACS |

---

## Repository Structure

```text
.
├── CitiBike_Financial_Gap_Analysis.ipynb
├── Tableau CitiBike Gap Analysis(1).twbx
├── income_coverage_distribution.csv
├── financial_cashflows.csv
├── brooklyn_station_demand.csv
├── tract_demographics_coverage.csv
├── sheepshead_bay_bus_stops.csv
├── financial_scenarios.csv
├── financial_roi_summary.csv
├── financial_assumptions.csv
├── sheepshead_bay_nearest_stations.csv
├── nta_demand_scores.csv
├── gap_zone_borough_summary.csv
├── top15_expansion_candidates.csv
├── stations_with_demand.csv
├── sheepshead_bay_profile.csv
└── README.md
```

Recommended expanded structure for future versions:

```text
.
├── data/
│   ├── raw/
│   │   ├── citibike_trips/
│   │   ├── citibike_stations/
│   │   ├── mta_gtfs/
│   │   ├── census_acs/
│   │   └── geo_boundaries/
│   ├── processed/
│   └── tableau_exports/
├── notebooks/
│   └── CitiBike_Financial_Gap_Analysis.ipynb
├── tableau/
│   └── Tableau CitiBike Gap Analysis.twbx
├── README.md
└── requirements.txt
```

Large raw CitiBike trip files are not required to be committed to GitHub because the notebook downloads and processes them programmatically.

---

## Data Sources

This project combines multiple public datasets into one analytical pipeline.

| Dataset | Source | Purpose |
|---|---|---|
| CitiBike GBFS station feed | CitiBike / GBFS | Current station locations, capacity, and live station metadata |
| CitiBike historical trip data | CitiBike trip data S3 archive | Ridership patterns, member mix, trip counts, and station-level demand |
| MTA bus stops | MTA GTFS feeds | Transit dependency and bus-access density proxy |
| NYC neighborhood boundaries | NYC Planning / NTA boundaries | Neighborhood-level aggregation and mapping |
| NYC borough / tract boundaries | Census TIGER / Census geographies | Spatial joins and Census tract coverage analysis |
| ACS 5-Year Estimates | U.S. Census Bureau | Population, income, vehicle access, commute mode, and bike/transit commute features |

---

## Methodology

The project is organized into four main analytical phases.

### Phase 1: Data Collection & Ingestion

The notebook first creates a repeatable data pipeline for collecting and organizing raw inputs:

- Downloads CitiBike live station data from the GBFS feed.
- Downloads historical CitiBike trip data from public monthly CSV archives.
- Pulls MTA bus stop data from GTFS files.
- Loads NYC borough, tract, and NTA geographic boundaries.
- Pulls Census ACS demographic indicators.
- Stores structured tables in DuckDB for reproducible SQL exploration.

Key engineering decisions:

- DuckDB is used as a lightweight analytical database inside the notebook.
- Raw files are cached to avoid unnecessary re-downloads.
- CSV exports are generated for Tableau, making the dashboard easy to refresh.

### Phase 2: SQL Exploration & Demand Profiling

DuckDB is used to profile station demand, trip behavior, and neighborhood-level patterns.

Examples of Phase 2 outputs:

- `stations_with_demand.csv`: station-level trip counts, member share, average duration, and trips per dock.
- `brooklyn_station_demand.csv`: ranked Brooklyn station demand table.
- `tract_demographics_coverage.csv`: Census tract demographics with CitiBike coverage status.
- `gap_zone_borough_summary.csv`: borough-level summary of uncovered population and commute characteristics.
- `sheepshead_bay_profile.csv`: demographic profile for the Southern Brooklyn focus area.

### Phase 3: Geospatial Gap Scoring Model

The core analytical feature of the project is the **Demand Proxy Score**, which estimates latent CitiBike demand in neighborhoods that do not currently have adequate service.

The score combines five normalized components:

| Component | Weight | Rationale |
|---|---:|---|
| Transit commute share | 35% | High transit usage indicates reliance on non-car transportation and potential first/last-mile demand. |
| No-vehicle household rate | 25% | Car-free households are more likely to depend on alternate transportation modes. |
| Population density | 20% | Denser neighborhoods offer more potential trips per station. |
| Bus stop density | 10% | Dense bus infrastructure signals transit-oriented movement patterns. |
| Inverse income | 10% | Lower-income areas receive an equity weighting to avoid prioritizing only high-income neighborhoods. |

Formula:

```text
Demand Score =
  0.35 * normalized_transit_commute_share
+ 0.25 * normalized_no_vehicle_rate
+ 0.20 * normalized_population_density
+ 0.10 * normalized_bus_stop_density
+ 0.10 * normalized_inverse_income
```

All components are min-max normalized from 0 to 1 before weighting. Gap-zone neighborhoods are then ranked by their final demand score.

### Phase 4: Financial Projection Model

After identifying the highest-priority expansion candidates, the notebook models whether each recommendation is financially viable.

The financial model estimates:

- Proposed station count.
- Proposed dock count.
- Annual steady-state trips per station.
- Blended revenue per trip.
- Capital installation cost.
- Annual operating expense.
- 10-year net present value.
- Break-even year.
- Low, mid, and high ridership scenarios.

Key financial assumptions:

| Assumption | Value |
|---|---:|
| Installation cost per station | $75,000 |
| Annual OpEx per station | $20,000 |
| Average docks per station | 23 |
| Revenue per member trip | $3.50 |
| Revenue per casual trip | $5.50 |
| E-bike surcharge, member | $0.19/min |
| E-bike surcharge, casual | $0.30/min |
| E-bike share | 64% |
| New-station member mix | 60% |
| Discount rate | 8% |
| Projection horizon | 10 years |
| Year 1 ramp-up | 40% of steady-state ridership |
| Year 2 ramp-up | 70% of steady-state ridership |
| Year 3+ ramp-up | 100% of steady-state ridership |

Ridership scenarios are anchored to the observed network baseline of approximately **19,227 annual trips per station**:

| Scenario | Multiplier | Description |
|---|---:|---|
| Low | 50% | Conservative adoption case |
| Mid | 70% | Base-case adoption case |
| High | 90% | Optimistic adoption case |

The final neighborhood-level trip estimate also incorporates the demand score using the following interpolation:

```text
Projected trips per station = network_average_trips * (0.40 + 0.60 * demand_score)
```

This avoids applying the same ridership assumption to every neighborhood and ties the financial model directly to the geospatial demand model.

---

## Financial Results

All top 15 modeled neighborhoods are financially viable under the project’s base assumptions, with each reaching break-even by Year 3.

| Rank | Neighborhood | Borough | Stations | Annual Revenue at Steady State | 10-Year NPV | Break-Even Year |
|---:|---|---|---:|---:|---:|---:|
| 1 | Parkchester | Bronx | 2 | $197,662 | $747,276 | 3 |
| 2 | Brownsville | Brooklyn | 4 | $380,864 | $1,409,274 | 3 |
| 3 | East Flatbush-Remsen Village | Brooklyn | 2 | $182,817 | $659,731 | 3 |
| 4 | Soundview-Bruckner-Bronx River | Bronx | 4 | $360,943 | $1,291,792 | 3 |
| 5 | Allerton | Bronx | 2 | $178,343 | $633,346 | 3 |
| 6 | Cypress Hills | Brooklyn | 3 | $265,650 | $939,019 | 3 |
| 7 | East New York-City Line | Brooklyn | 4 | $351,841 | $1,238,115 | 3 |
| 8 | Jamaica | Queens | 6 | $512,802 | $1,768,948 | 3 |
| 9 | East New York-New Lots | Brooklyn | 6 | $507,725 | $1,739,010 | 3 |
| 10 | East New York (North) | Brooklyn | 3 | $253,151 | $865,309 | 3 |
| 11 | Westchester Square | Bronx | 2 | $165,332 | $556,612 | 3 |
| 12 | Pelham Parkway-Van Nest | Bronx | 2 | $164,819 | $553,588 | 3 |
| 13 | Soundview-Clason Point | Bronx | 4 | $326,792 | $1,090,393 | 3 |
| 14 | Brighton Beach | Brooklyn | 2 | $163,319 | $544,743 | 3 |
| 15 | Williamsbridge-Olinville | Bronx | 4 | $323,177 | $1,069,074 | 3 |

The strongest NPV opportunities are Jamaica, East New York-New Lots, Brownsville, Soundview-Bruckner-Bronx River, and East New York-City Line. These neighborhoods combine high gap populations, transit dependency, and enough modeled ridership to support the proposed station investment.

---

## Sheepshead Bay / Southern Brooklyn Deep Dive

Although the expansion ranking is citywide, the project also includes a focused Southern Brooklyn case study to examine an area with meaningful transit dependence and limited bike share access.

Sheepshead Bay profile outputs:

| Metric | Value |
|---|---:|
| Census tracts profiled | 42 |
| Population profiled | 140,930 |
| Weighted no-vehicle household rate | 43.1% |
| Weighted public-transit commute share | 41.7% |
| Weighted bike commute share | 0.8% |
| Bus stops identified | 225 |
| Nearest existing CitiBike station distance | 6.32 km |
| Average distance to 15 nearest existing stations | 6.60 km |

This deep dive demonstrates how the framework can be applied to a specific neighborhood even when the final investment ranking prioritizes other higher-scoring NTAs first.

---

## Output Files & Data Dictionary

### Tableau Export Files

| File | Description |
|---|---|
| `nta_demand_scores.csv` | Full neighborhood-level table with demand scores, coverage status, normalized model features, demographics, and centroid coordinates. |
| `top15_expansion_candidates.csv` | Top 15 gap-zone neighborhoods ranked by demand score with proposed stations and docks. |
| `financial_roi_summary.csv` | Neighborhood-level financial summary with NPV, break-even year, annual revenue, and viability flag. |
| `financial_cashflows.csv` | Year-by-year net cash flow and cumulative P&L for each modeled expansion neighborhood. |
| `financial_scenarios.csv` | Low, mid, and high ridership scenario comparison by neighborhood. |
| `financial_assumptions.csv` | Transparent reference table for model parameters used in the financial analysis. |
| `tract_demographics_coverage.csv` | Census tract-level demographics and CitiBike coverage status. |
| `gap_zone_borough_summary.csv` | Borough-level summary of gap population, gap tracts, vehicle access, and transit commute rates. |
| `income_coverage_distribution.csv` | Coverage gap summary by median-income bracket. |
| `stations_with_demand.csv` | Station-level demand, trip count, duration, member share, capacity, and trips per dock. |
| `brooklyn_station_demand.csv` | Brooklyn-focused station demand ranking. |
| `sheepshead_bay_profile.csv` | Census tract demographic profile for the Sheepshead Bay / Southern Brooklyn focus area. |
| `sheepshead_bay_bus_stops.csv` | Bus stop locations used in the Southern Brooklyn deep dive. |
| `sheepshead_bay_nearest_stations.csv` | Nearest existing CitiBike stations and distances from the focus area. |

### Important Fields

| Field | Meaning |
|---|---|
| `coverage_status` | Indicates whether a tract or neighborhood is modeled as covered or in a gap zone. |
| `demand_score` | Weighted composite score estimating latent CitiBike demand. |
| `expansion_rank` | Rank among gap-zone neighborhoods, where 1 is the highest-priority candidate. |
| `gap_population` | Population living in uncovered areas within a neighborhood. |
| `no_vehicle_rate` | Share of households without vehicle access. |
| `transit_share` | Share of commuters using public transit. |
| `bus_stop_density` | Bus stops per square kilometer. |
| `proposed_stations` | Recommended number of CitiBike stations for the neighborhood. |
| `proposed_docks` | Estimated dock count, assuming 23 docks per station. |
| `trips_per_stn_yr` | Modeled annual steady-state trips per station. |
| `ann_revenue_ss` | Annual revenue at steady-state ridership. |
| `total_10yr_cost` | Total modeled 10-year cost including capex and operating expenses. |
| `npv_10yr` | Net present value over the 10-year model horizon. |
| `breakeven_year` | First year when cumulative P&L becomes positive. |
| `viable` | Financial viability flag based on positive 10-year NPV. |

---

## How to Run This Project

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### 2. Create a Python Environment

```bash
python -m venv .venv
source .venv/bin/activate   # Mac/Linux
# .venv\Scripts\activate    # Windows
```

### 3. Install Dependencies

```bash
pip install pandas numpy geopandas shapely duckdb requests pygris matplotlib jupyter
```

Optional: create a `requirements.txt` file with the same dependencies.

### 4. Run the Notebook

Open:

```text
CitiBike_Financial_Gap_Analysis.ipynb
```

The notebook is organized into four phases:

1. **Data Collection & Ingestion**
2. **SQL Exploration with DuckDB**
3. **Gap Scoring and Demand Modeling**
4. **Financial Projection Modeling**

If running in Google Colab, update the project root path if needed:

```python
PROJECT_ROOT = Path('/content/drive/MyDrive/citibike_project')
```

You may also need a free Census API key for the ACS ingestion step.

---

## Analytical Skills Utilized

### Data Engineering

- Programmatic API and file-based data ingestion.
- Processing large public CSV datasets.
- Persistent analytical storage with DuckDB.
- Clean data exports for dashboard consumption.

### SQL Analytics

- Table validation and schema checks.
- Aggregation by station, borough, tract, and neighborhood.
- Demand profiling through grouped queries.
- Preparing analysis-ready outputs for downstream modeling.

### Geospatial Analytics

- Spatial joins between station locations, tracts, and NTAs.
- Coverage-gap identification using station geography.
- Neighborhood aggregation from tract-level data.
- Bus stop density and centroid-based mapping.

### Feature Engineering

- Demand proxy score construction.
- Min-max normalization.
- Composite weighted scoring.
- Transit dependence and equity-oriented features.
- Station count and dock count estimation.

### Financial Modeling

- 10-year cash flow projection.
- Capex and OpEx modeling.
- Discounted cash flow and NPV analysis.
- Scenario modeling under low, mid, and high ridership cases.
- Break-even analysis and downside sensitivity.

### Data Visualization & Storytelling

- Interactive Tableau dashboard design.
- Map-based coverage storytelling.
- KPI summary views.
- NPV and payback visualizations.
- Executive-facing recommendations.

---

## Limitations

This project is intended as a portfolio-grade analytical model, not an audited infrastructure plan. Key limitations include but are not limited to:

- **Trip data seasonality:** The financial model annualizes partial historical trip data using a seasonal multiplier.
- **Station siting:** Proposed station counts are estimated at the neighborhood level and do not account for block-level curb space, permitting, safety, or DOT constraints.
- **Coverage definition:** Coverage is based on geospatial proximity to existing stations and does not fully capture station availability, bike rebalancing, or service quality.
- **Financial assumptions:** Cost and revenue inputs are directional estimates and should be validated with internal CitiBike/Lyft financial data before implementation.
- **ACS data quality:** Some Census ACS fields can contain missing, suppressed, or coded values. A production model should explicitly recode invalid income estimates before scoring.
- **Demand proxy:** The demand score is interpretable and transparent, but it is not a trained causal model of future ridership.
- **Equity weighting:** The inverse-income feature is one way to incorporate equity, but alternative policy priorities could produce different rankings.

---

## Future Improvements

Potential next steps include:

- Replace proxy scoring with a supervised ridership prediction model trained on existing station performance.
- Incorporate subway entrances, bike lanes, schools, parks, and commercial corridors.
- Include station rebalancing costs and e-bike charging infrastructure costs.
- Validate projected ridership against historical CitiBike expansion rollouts.
- Use clustering to identify expansion corridors instead of evaluating neighborhoods independently.

---

## Project Takeaway

This project demonstrates how public datasets can be combined into a structured decision-support model for urban mobility planning. By linking geospatial coverage gaps, demographic need, observed bike share behavior, and financial feasibility, the analysis moves beyond descriptive mapping and creates an actionable expansion prioritization framework.

The core recommendation is that CitiBike expansion should prioritize high-transit, high-car-free, uncovered neighborhoods such as Parkchester, Brownsville, East Flatbush-Remsen Village, Soundview-Bruckner-Bronx River, and Allerton, while using financial scenario analysis to phase investments responsibly.
