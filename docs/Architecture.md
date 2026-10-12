# Architecture

```mermaid
flowchart TB
    subgraph Source[CRM Source]
        D365[Dynamics 365 Sales]
        DV[Microsoft Dataverse]
    end
    subgraph Prep[Data Preparation]
        PQ[Power Query]
        DQ[Data Quality Rules]
    end
    subgraph BI[Analytics Layer]
        SM[Power BI Semantic Model]
        DAX[DAX KPI / Calculation Layer]
    end
    subgraph UX[Decision Layer]
        EX[Executive Overview]
        PF[Pipeline & Forecast]
        SP[Sales Performance]
        CP[Customer & Product]
        QC[CRM Data Quality]
    end
    D365 --> DV --> PQ --> DQ --> SM --> DAX
    DAX --> EX
    DAX --> PF
    DAX --> SP
    DAX --> CP
    DQ --> QC
    EX --> DEC[Commercial Decisions]
    PF --> DEC
    SP --> DEC
    CP --> DEC
    QC --> FIX[CRM Remediation]
```

## Source layer

Dynamics 365 Sales uses Dataverse for its application data. Typical Sales entities/tables include accounts, contacts, leads, opportunities and products. citeturn0search5

## Preparation layer

For a portfolio implementation, CSVs simulate Dataverse tables. In production, use the Dataverse connector in Power BI. Microsoft identifies the Dataverse connector as the current Power BI path for analytics workloads involving Dataverse data. [Microsoft Learn: Power Query Dataverse connector](https://learn.microsoft.com/en-us/power-query/connectors/dataverse)

## Semantic layer

The semantic model separates dimensions and facts so that KPI calculations remain reusable across the report.

## Decision layer

The dashboard is designed around decisions, not chart types:

- Forecast / pipeline decisions
- Sales manager interventions
- Account prioritization
- Target management
- CRM remediation
