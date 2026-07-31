# ME204 Final Project: AI exposure and employment across US industries


| GitHub username                           | LSE ID            |
| ----------------------------------------- | ----------------- |
| `jp-tobin`                              | `250104200`        |

## Overview

To what extent have industries that are more exposed to artificial intelligence experienced different employment outcomes since the widespread availability of large language models? By combining AI exposure scores with US labour market data, this project examines whether highly exposed industries have seen weaker employment growth than less exposed industries.

## Data sources

### API:
- **BLS Public Data API** – industry-level employment data used to calculate employment growth across U.S. industries.

### Static datasets:
- **AI Industry Exposure (AIIE) scores** from Felten, Raj and Seamans (2021), providing industry-level measures of exposure to artificial intelligence. Available at: https://github.com/AIOE-Data/AIOE
- **BLS series metadata files** used to identify valid industry employment series and map them to NAICS industries. Available at: https://www.bls.gov/help/hlpforma.htm#CE

## How to reproduce

Required packages:
pip install openpyxl to read in AIOE excel sheet

[Tell your reader how to get keys, which python commands to run and any other things they need to know when replicating your work (imagine they are people with similar technical skills as yours)]


This project consists of three Jupyter notebooks that should be run sequentially.

### Prerequisites

Install the required Python packages:

```bash
pip install pandas numpy requests python-dotenv plotly statsmodels openpyxl
```

### Obtain an API Key

The project uses the U.S. Bureau of Labor Statistics (BLS) Public API. Register for a free API key via the BLS registration page.

Create a .env file in the project root directory containing:
```python
BLS_API_KEY=your_api_key_here
```
### Required Static Files

Before running the notebooks, download the BLS industry code table from from [BLS Current Employment Statistics](https://download.bls.gov/pub/time.series/ce/ce.industry) and save it as: `data/reference/ce_industry.tsv`

The AI Industry Exposure (AIIE) data from Felten, Raj and Seamans is downloaded automatically by the collection notebook, so no manual download is required.

### Run the Notebooks

Run the notebooks in the following order:

#### 1. NB01-Data-Collection.ipynb

- Downloads the Felten, Raj and Seamans AI Industry Exposure (AIIE) dataset.
- Cleans and expands NAICS codes where necessary.
- Builds a mapping between AIIE industries and BLS employment series.
- Requests employment data from the BLS API.
- Saves raw API responses to data/raw/.
- Creates reference mapping files in data/reference/.

#### 2. NB02-Data-Transformation.ipynb

- Loads raw JSON responses from the BLS API.
- Converts them into tidy tabular format.
- Reattaches industry names, NAICS codes and AI exposure scores.
- Creates sector classifications.
- Writes the cleaned dataset to: `data/processed/employment.csv`

#### 3. NB03-JP-Tobin-Data-Analysis.ipynb

- Loads the processed dataset.
- Checks the coverage of the indicators in the sample.
- Calculates employment growth by industry.
- Evaluates the relationship between AI exposure and employment outcomes.
- Produces the tables, summary statistics, and visualisations used in the final report and website.

### Expected Outputs

Running all three notebooks should populate the below file structure:

```text
.
├── data
│   ├── processed
│   │   └── employment.csv
│   ├── raw
│   │   └── employment
│   │       ├── bls_employment_1.json
│   │       ├── bls_employment_2.json
│   │       ├── bls_employment_3.json
│   │       └── bls_employment_4.json
│   └── reference
│       ├── aiie_bls_map.csv
│       ├── ce_industry.tsv
│       └── industry_code_map.csv
├── docs
│   ├── assets
│   │   ├── emp_growth_ai_anim.html
│   │   ├── emp_growth_ai_static.png
│   │   ├── fed_ai_scenarios.png
│   │   ├── growth_ai_coef.html
│   │   └── growth_ai_coef.png
│   └── index.md
├── notebooks
│   ├── NB01-Data-Collection.ipynb
│   ├── NB02-Data-Transformation.ipynb
│   └── NB03-JP-Tobin-Data-Analysis.ipynb
└── README.md
```