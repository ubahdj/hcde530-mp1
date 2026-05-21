# Mini Project 1

**Notebook:** `Mp1.ipynb`  
**Charts:** `figures/` (PNG)

## Dataset

City of Seattle **General Business License** data from the open data API:  
https://data.seattle.gov/resource/wnbq-64tb.json

The analysis keeps Seattle rows whose **trade name** includes coffee, café, or espresso (~309 locations in the filtered extract).

## Analytical questions

1. Which Seattle ZIP codes have the highest concentration of coffee shops?
2. How has the number of new coffee shop openings changed year over year (2000–2024)?
3. Are chain or independent coffee shops more common in Seattle?

## What I built

`Mp1.ipynb` has four sections:

- **Overview** — dataset, motivation, and who would use the findings  
- **Data Profile** — `head()`, `info()`, `describe()`, `isnull().sum()` with short interpretations  
- **Analysis** — three matplotlib charts (titles and labeled axes), each followed by markdown on what the chart argues  
- **Conclusions** — plain-language answers per question  

Static images in `figures/`:

- `Top 10 Seattle Zip codes .png` — horizontal bar chart (Q1)  
- `New seattle Coffee shop openings Per year.png` — line chart with COVID marker (Q2)  
- `Chain vs independent coffee shops.png` — bar chart (Q3)  

## Main findings

**ZIP concentration:** **98122 (Capitol Hill)** leads with **30** licenses, just above downtown **98101** (28) and **98103** (27)—surprising given downtown foot traffic; dense residential neighborhoods may support more coffee businesses.

**Openings over time:** Openings were low through the 2000s, peaked at **22** in **2018**, dropped to **13** in **2020** (COVID), then hit a high of **30** in **2023**.

**Chain vs. independent:** Under a simple rule (same trade name on 2+ licenses = chain), **~82%** of locations look independent (**253**) and **~18%** chain-like (**56**).

## Reflection

This project connected open civic data to questions I care about locally (Capitol Hill, post-COVID openings). License counts are not the same as store openings or foot traffic, but the charts still support neighborhood and policy conversations. Next steps: normalize by population, and manually tag major chains for a cleaner chain/independent split.
