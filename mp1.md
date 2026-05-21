# Mini Project 1

**Notebook:** `Mp1.ipynb`  
**Charts:** `figures/` (PNG)

Competency Claims :

C4 — APIs and Data Acquisition
I pulled data from the Seattle Open Data portal using the Socrata API (data.seattle.gov/resource/wnbq-64tb.json), requesting up to 50,000 business license records in a single call. The endpoint returns structured JSON with fields like trade name, city, ZIP code, and license start date. I filtered the response down to 311 Seattle coffee-related businesses by searching trade names for keywords like "coffee," "cafe," and "espresso." The API is public and requires no key.

C5 — Data Analysis with Pandas
I used pandas to answer three specific questions about Seattle's coffee shop landscape. I first profiled the raw dataset using df.head() to preview the structure, df.info() to check column types, df.describe() to confirm which fields were numeric, and df.isnull().sum() to identify missing values. From there I filtered rows by city and trade name keywords, used .str.contains() for keyword matching, .fillna() to handle missing ZIP codes, pd.to_datetime() to parse license dates, .groupby() to count licenses by ZIP and year, and a name-repeat heuristic to classify chains vs. independents. One finding that surprised me: independents made up about 82% of licenses (253 out of 311), which I noted could be misleading since spelling variants might split one brand into multiple "unique" names.

C6 — Data Visualization 
I built three charts using plotly: a bar chart of licenses by ZIP code, a line chart of new coffee shop openings by year (2000–2024), and a bar chart comparing chain vs. independent counts. I chose bar charts for the ZIP and chain/independent questions because I was comparing discrete categories, and a line chart for the year-over-year question because it shows change over time. The year chart revealed a clear 2020 dip and a 2023 surge, which fits a COVID pattern. All charts are saved as static images to Mp1/figures/ using kaleido, and the notebook includes markdown cells interpreting each finding.

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
