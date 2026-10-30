# Central Valley Labor Dynamics & Regional Tech Opportunities
### Exploratory Data Analysis & Economic Business Intelligence in Stanislaus County

This repository explores and analyzes publicly available labor and economic datasets (specifically California EDD / U.S. BLS Quarterly Census of Employment and Wages - QCEW) to understand the underlying employment infrastructure of Stanislaus County and the broader Central Valley.

---

## 🎯 Project Background & Objectives

What started as an exploration of small business dynamics evolved into an applied data analysis project examining regional workforce realities across three interconnected lenses:

1. **Small & Medium Business (SMB) Tech Enablement:**  
   Investigating where local businesses are concentrated and identifying operational bottlenecks (inventory syncing, customer scheduling, internal workflow automation) where practical technology tools and consulting can provide immediate value.
2. **Central Valley Tech Pathways (Computer Science Placement):**  
   Challenging the assumption that software engineering and tech careers only exist at dedicated Big Tech firms. This analysis maps where technology, automation, data systems, and IT infrastructure are embedded inside traditional Valley industries—such as ag-tech, food processing, logistics telematics, public utilities, and healthcare.
3. **Mid-Career & Individual Workforce Navigation:**  
   Analyzing the labor landscape from an individual job seeker's perspective to discover high-stability sectors (e.g., local government, school districts), wage structures, and avenues for career transition supported by local workforce development initiatives (e.g., WIOA training grants).

---

## 🔍 Data Source & Classification Framework

The core analysis uses quarterly regional labor data categorized by the **North American Industry Classification System (NAICS)**.

### Official NAICS Resources
* [U.S. Census Bureau NAICS Overview](https://www.census.gov/naics/)
* [2022 NAICS Reference Manual (PDF)](https://www.census.gov/naics/reference_files_tools/2022_NAICS_Manual.pdf)
* [Quarterly Census of Employment and Wages (QCEW)](https://data.ca.gov/@california-employment-development-department/quarterly-census-of-employment-and-wages)

### Understanding the Data Hierarchy (`NAICS Level`)
To prevent double-counting and extract meaningful aggregates, this analysis distinguishes between macro totals and hyper-specific establishments:

* **Level 0 (Macro Baseline):** Code `10` (*Total, All Industries*) — Represents the macro county baseline across ownership sectors (`Private`, `Local Government`, `State Government`, `Federal Government`, and `Total Covered`).
* **Level 2 (Broad Economic Sectors):** 2-digit codes (e.g., `62` Healthcare, `31-33` Manufacturing, `44-45` Retail Trade, `48-49` Logistics).
* **Level 3 to Level 5 (Subsectors & Industry Groups):** 3- to 5-digit intermediate categories.
* **Level 6 (Detailed National Industries):** 6-digit codes targeting specific business operations (e.g., `311421` Fruit & Vegetable Canning, `722513` Limited-Service Restaurants).

> **A Note on Data Suppression:** Under federal and state disclosure limitation rules (e.g., the 80/3 rule), detailed 6-digit rows dominated by one or two major regional employers (such as large wineries or specialized packaging plants) are withheld from publication at Level 6 to protect proprietary payroll information. These headcounts are preserved at Level 2 and Level 0, which makes multi-level aggregation essential.

---

## 📊 Key Findings from Stanislaus County (Q1 2026 QCEW)

* **Macro Footprint:** Stanislaus County encompasses **195,471 covered payroll jobs** across **18,812 establishments**.
  * **Private Sector:** 161,676 jobs across 18,398 establishments.
  * **Local Government:** 31,216 jobs across 304 entities (over 62% concentrated in K-12 public education).
  * **State & Federal Government:** 2,577 combined jobs (anchored by CSU Stanislaus and the U.S. Postal Service).
* **The Dominant Pillars (Private Level 2):**
  1. *Health Care & Social Assistance (`62`):* 38,082 jobs (predominantly independent clinics, micro-practices, and in-home care agencies).
  2. *Retail Trade (`44-45`):* 22,182 jobs.
  3. *Manufacturing (`31-33`):* 20,765 jobs (led by canning, dairy/cheese production, poultry processing, and corrugated packaging).
  4. *Accommodation & Food Services (`72`):* 17,271 jobs.
  5. *Construction (`23`):* 10,599 jobs.
* **The Industrial Supply Chain Core:** Combining **Manufacturing (`31-33`)**, **Transportation & Warehousing (`48-49`)**, and **B2B Wholesale Trade (`42`)** accounts for **34,935 jobs** across 1,597 facilities—more than 1 in every 5 private-sector jobs in the county.

---

## 💻 Tech Stack & Notebook Contents

* **Language:** Python 3
* **Libraries:** `pandas`, `numpy`, `matplotlib` / `seaborn`
* **Primary Notebook:** [`jobs.ipynb`](jobs.ipynb)
  * Data hygiene and whitespace normalization on NAICS keys.
  * Multi-level hierarchical filtering (`NAICS Level == 0, 2, 6`).
  * Sector grouping, supply-chain clustering, and wage comparisons.
  * Visual ASCII organizational tree breaking down employment across public and private lines.

---

## 🚀 How to Run the Notebook

1. Clone this repository:
   ```bash
   git clone https://github.com/daisymayorga-galtechs/state-open-data.git
   cd state-open-data
   ```
2. Open in Google Colab or your local Jupyter environment:
   ```bash
   jupyter notebook jobs.ipynb
   ```
3. Ensure the regional labor CSV dataset (`qcew-2026-q1.csv` or corresponding quarterly extract) is in the root directory.
