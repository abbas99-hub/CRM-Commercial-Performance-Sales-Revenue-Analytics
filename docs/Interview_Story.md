# Interview Story

## 30-second answer

"I built a Dynamics 365-style CRM commercial analytics solution in Power BI. My focus was not simply to visualize CRM records; it was to answer whether the sales organization had enough quality pipeline, whether the forecast was credible, which opportunities required intervention, and whether the underlying CRM data could be trusted. I built a star-schema model across accounts, opportunities, products, activities, leads and targets, created DAX measures for pipeline, weighted pipeline, win rate and target achievement, and added a dedicated CRM data-quality layer."

## 2-minute answer

"The business problem was that CRM contains a lot of operational data but leadership needs a concise commercial view. I designed five layers. First, an executive page shows won revenue, pipeline, weighted pipeline, win rate, average deal size, target achievement and coverage. Second, a pipeline page explains forecast risk through stage, probability, ageing and expected close. Third, a sales-performance page connects rep activity to commercial outcomes. Fourth, customer and product analytics identify revenue concentration and expansion opportunities. Finally, a data-quality page monitors duplicates, missing owners, missing close dates and invalid values.

I intentionally introduced data-quality issues into the synthetic dataset because in a real CRM project the analyst has to prove that the KPI layer is trustworthy. The key design principle was to move from descriptive reporting to exception-based management: instead of asking managers to inspect thousands of opportunities, the dashboard highlights the opportunities and data records that need action."

## Questions the interviewer may ask

### Why weighted pipeline?
Because nominal pipeline treats every open opportunity equally. Weighted pipeline incorporates the CRM probability field and provides a more decision-oriented forecast view.

### Why a star schema?
It separates reusable dimensions from transactional facts, reduces ambiguous relationships and makes DAX measures more predictable.

### Why include activities?
To connect sales execution with commercial outcomes. Activity volume is not a success KPI by itself; it becomes useful when analyzed alongside pipeline, conversion and revenue.

### Why include data quality?
Because a dashboard can be visually accurate while still being commercially wrong if the underlying CRM has duplicate, incomplete or invalid records.

### What would you do with real Dynamics 365?
Replace the CSV source with Dataverse, use Power Query for transformation, preserve the semantic model, implement security/RLS as required, publish to Power BI Service and integrate the report with the Dynamics 365/model-driven experience where appropriate.
