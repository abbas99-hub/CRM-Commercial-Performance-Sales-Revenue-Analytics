# Power BI semantic model

Accounts (1) ─── (*) Opportunities
Accounts (1) ─── (*) Contacts
Accounts (1) ─── (*) Leads
Accounts (1) ─── (*) Activities

SalesReps (1) ─── (*) Opportunities
SalesReps (1) ─── (*) Activities
SalesReps (1) ─── (*) Targets

Opportunities (1) ─── (*) OpportunityProducts
Products (1) ─── (*) OpportunityProducts
Campaigns (1) ─── (*) Opportunities

Date[Date] → Opportunities[CreatedDate]
Date[Date] → Opportunities[ExpectedCloseDate]
Date[Date] → Opportunities[ActualCloseDate]
Date[Date] → Activities[ActivityDate]
Date[Date] → Leads[CreatedDate]
Date[Date] → Targets[Month]

Recommended star-schema approach:
- Dimensions: Date, Accounts, SalesReps, Products, Campaigns
- Facts: Opportunities, OpportunityProducts, Activities, Leads, Targets
- Keep opportunity-level measures on Opportunities.
- Keep product-level revenue on OpportunityProducts.
- Avoid many-to-many relationships caused by duplicate Opportunity IDs; use the Data Quality page to expose the intentional issue.