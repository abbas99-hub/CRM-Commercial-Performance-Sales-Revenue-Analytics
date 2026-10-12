# Business Case

## Business context

A B2B sales organization uses Dynamics 365 Sales as its CRM. The sales organization has visibility into individual CRM records but leadership lacks a consistent commercial operating view.

## Business problems

### 1. Pipeline fragmentation
Opportunity information is spread across stages, sales reps, territories, industries and expected close dates.

**Analytics response:** centralized pipeline and stage reporting.

### 2. Forecast uncertainty
Nominal pipeline assumes every open opportunity has equal value, which is commercially unrealistic.

**Analytics response:** probability-weighted pipeline.

### 3. Opportunity ageing
Open opportunities can remain in the CRM long after their expected progression date.

**Analytics response:** ageing buckets and stale-opportunity exception reporting.

### 4. Sales productivity blind spots
Activity counts alone do not show whether sales effort is connected to commercial outcomes.

**Analytics response:** activities per opportunity alongside win rate, deal size and revenue.

### 5. CRM data trust
Duplicate IDs, missing owners and missing close dates can distort management reporting.

**Analytics response:** data-quality KPIs and exception lists.

## Decision framework

| Observation | Commercial question | Action |
|---|---|---|
| High pipeline, low probability | Is pipeline overstated? | Review qualification |
| High-value ageing opportunity | Why has the deal stalled? | Manager intervention |
| Strong activity, low conversion | Is activity quality effective? | Review sales process |
| Low activity, high pipeline | Is the opportunity neglected? | Rep follow-up |
| High win rate, low deal size | Is the rep under-selling? | Account expansion |
| Missing owner | Who is accountable? | CRM remediation |
| Missing close date | Can it enter forecast? | Enforce CRM discipline |
