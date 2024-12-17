# Business Names Registration Data Explorer

This Python script retrieves business names registration data from the [data.gov.au](https://data.gov.au) CKAN API, applies user-defined filters, and generates visualizations. The script supports table views, pie charts, and trend charts for analyzing and displaying the retrieved data.

---

## Features
- **Data Retrieval**: Fetches business registration data based on filters like status, registration date range, state, and similar business names.
- **Filters**:
  - Business status (e.g., Registered, Deregistered)
  - Start and end registration dates
  - State of registration (e.g., VIC, NSW, ACT)
  - Matches similar business names (partial or exact match)
  - Custom result limit
- **Visualizations**:
  - Table View: Displays results in tabular format.
  - Pie Chart: Shows the percentage/No. of businesses with and without an ABN.
  - Trend Chart: Shows trend of No. of business registrations over a period.

---

## Prerequisites

1. **Python 3.x**
2. **Required Libraries**:
   - `pandas`
   - `matplotlib`
   - `ckanapi`
   - `argparse`
   - `json`

Install dependencies using pip:
```bash
pip install -r requirements.txt
```

---

## Usage

### Command-line Arguments

| Argument                         | Description                                                       | Example                                  |
|----------------------------------|-------------------------------------------------------------------|------------------------------------------|
| `--filter-status`                | Filter by Business Status (e.g., Registered/Deregistered)         | `--filter-status Registered`             |
| `--filter-registration_date_from`| Start date for business registration (DD/MM/YYYY)                | `--filter-registration_date_from 01/01/2020` |
| `--filter-registration_date_to`  | End date for business registration (DD/MM/YYYY)                  | `--filter-registration_date_to 31/12/2023` |
| `--filter-registration_state`    | Filter by state of registration (e.g., VIC, NSW, ACT)            | `--filter-registration_state VIC`        |
| `--filter-match_similar_business_names` | Search for similar business names                              | `--filter-match_similar_business_names ABC` |
| `--filter-visual_type`           | Type of visualization: `table`, `pie chart`, or `trend`          | `--filter-visual_type trend`             |
| `--filter-limit`                 | Limit the number of results returned                             | `--filter-limit 500`                     |

---

### Example Commands

#### 1. Display a Table of Registered Businesses in NSW
```bash
python search_business_names.py --filter-status Registered --filter-registration_state NSW --filter-visual_type 'table'
```

#### 2. Show a Pie Chart for Businesses with/without ABN in VIC with a matching name wine cellars
```bash
python search_business_names.py --filter-registration_state VIC --filter-match_similar_business_names 'wine cellars --filter-visual_type 'pie chart'
```

#### 3. Generate a Trend Chart of Registrations from 2021 to 2023
```bash
python search_business_names.py --filter-registration_date_from 01/01/2021 --filter-registration_date_to 31/12/2023 --filter-visual_type trend
```

---

## Outputs
- **Table View**: Displays the results in a structured table format in the terminal.
- **Pie Chart**: Visualizes the proportion of businesses with and without ABN.
- **Trend Chart**: Plots the number of business registrations over time.

---
