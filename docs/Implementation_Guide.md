# Implementation Guide

## Portfolio build

### Step 1 — Load
Import all CSVs from `data/raw/`.

### Step 2 — Transform
Standardize data types, trim text fields, replace invalid stage values into a controlled exception category, and validate keys.

### Step 3 — Model
Build the star schema documented in `powerbi/Semantic_Model.md`.

### Step 4 — Measures
Copy the DAX from `powerbi/DAX_Measures.dax` into the model.

### Step 5 — UX
Apply the theme and create the five report pages.

### Step 6 — QA
Validate:
- totals against source CSVs
- distinct opportunity counts
- closed-won revenue
- target calculations
- duplicate IDs
- missing owners
- missing close dates

### Step 7 — Publish
Publish to a Power BI workspace, configure permissions and refresh.

## Production implementation

Replace CSV ingestion with the Dataverse connector. Microsoft documents direct Power BI connectivity to Dataverse, including Import and DirectQuery options. [Microsoft Learn: Power Query Dataverse connector](https://learn.microsoft.com/en-us/power-query/connectors/dataverse)

For larger environments, consider the modeling and architecture guidance for Power Platform and Dataverse. [Microsoft Learn: Power BI modeling guidance for Power Platform](https://learn.microsoft.com/en-us/power-bi/guidance/powerbi-modeling-guidance-for-power-platform)
