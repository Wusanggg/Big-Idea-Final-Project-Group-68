
# Big-Idea-Final-Project-Group-68

This repository contains the final project for **Group 68**  
**Group name:** Procrastinateam  

**Group members:**
- Abdulaziz Abdusamatov  
- Isaac Li  
- Zhenyu Wu  

---

## Project Overview

This project builds a **“Bestness” score for Pittsburgh neighborhoods** using open data.  
We evaluate scores across neighborhoods by their **convenience**. We focus on three infrastructure-related dimensions:

1. **Smart trash coverage** – how well a neighborhood is served by smart trash containers.  
2. **Parking** – overall parking convenience based on a parking score.  
3. **City steps** – availability and quality of public stairways that support walkability.

Our goal is to provide a **transparent, data-driven ranking** of neighborhoods, while also showing the trade-offs between different aspects of urban life.

---

## Research Questions

We aim to answer:

- Which Pittsburgh neighborhoods rank highest when we combine smart trash, parking, and city steps into a single Bestness metric?
- How do neighborhoods differ in the balance of these three dimensions?
- How does **missing parking data** affect the ranking, and what happens when we **impute** those values?

---

## Data Sources

All datasets come from the **Western Pennsylvania Regional Data Center (WPRDC)** and related public sources, including (but not limited to):

- Smart trash container locations  
- Parking-related scores or infrastructure data  
- City steps locations and attributes  
- Neighborhood boundary shapefiles for mapping

Exact dataset links and cleaning steps are documented in the analysis notebooks/report.

---

## Methodology (High-Level)

1. **Data cleaning & preprocessing**
   - Load neighborhood boundaries and join them with smart trash, parking, and steps datasets.
   - Aggregate point data (e.g., containers, steps) to the neighborhood level.
   - Standardize metrics so they are comparable across neighborhoods.

2. **Metric construction**
   - Compute a **smart trash score**, **parking score**, and **steps score** for each neighborhood.
   - Normalize scores to a common scale (e.g., 0–1 or z-scores).

3. **Bestness score**
   - Combine the three metrics into a single score using weights:  
     - Smart trash: **0.25**  
     - Parking: **0.40**  
     - City steps: **0.35**  
   - Produce two rankings:
     - **Without imputation** – only neighborhoods with parking data.
     - **With imputation** – missing parking scores filled with the **mean** parking score.

4. **Visualization**
   - Horizontal bar charts for the top neighborhoods by Bestness.
   - Choropleth maps of Pittsburgh showing Bestness before and after imputation.

---

## Key Findings (Brief)

- **Allentown** and **Upper Lawrenceville** consistently appear near the top of the ranking, even after imputing missing parking data.
- After imputation, more neighborhoods (e.g., **South Side Slopes**, **Polish Hill**, **Middle Hill**) move into the top tier because their strong steps or trash scores are no longer “blocked” by missing parking data.
- Different neighborhoods do well for different reasons: some excel in **parking**, others in **steps** or **smart trash**, highlighting the multi-dimensional nature of “livability.”

---

## Limitations (Summary)

- The notion of “best” is **narrow**: only trash, parking, and steps are included.
- The weighting scheme is **subjective** and reflects our group’s preferences.
- Data coverage and quality depend on what is reported to WPRDC; some neighborhoods have missing or outdated information.
- Analysis is at the **neighborhood level**, ignoring within-neighborhood variation.
- The results are a **snapshot in time** and may not reflect future infrastructure changes.

---

## How to Use This Repository

Typical ways to work with this project:

1. **Clone the repository**

   git clone https://github.com/Wusanggg/Big-Idea-Final-Project-Group-68.git  
   cd Big-Idea-Final-Project-Group-68


2. **Set up a Python environment** (e.g., with `venv` or `conda`) and install the required libraries:

   * `pandas`
   * `geopandas`
   * `matplotlib` / `seaborn` (if used)
   * `numpy`
   * Any additional libraries listed in the notebooks or requirements file (if provided).

3. **Run the analysis**

   * Open the Jupyter notebooks (if included) to reproduce:

     * Data cleaning
     * Score computation
     * Visualizations and maps
   * Exported figures and the final written report can be found in the corresponding folders (e.g., `figures/`, `report/`) if they exist in this repo.

*(Adjust the exact commands and paths based on the actual files in this repository.)*

---

## Project Status

This repository represents the **final submitted version** of the course project.
It can be extended by:

* Adding new dimensions (e.g., safety, transit, green space).
* Trying alternative weighting schemes or multi-criteria decision methods.
* Incorporating temporal data to study changes over time.

---

## Contact

For questions about this project, please reach out to any group member via GitHub or the course communication channels.

**Group 68 – Procrastinateam**
