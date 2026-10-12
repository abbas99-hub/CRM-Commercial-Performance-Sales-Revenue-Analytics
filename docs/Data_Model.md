# Data Model

## Dimensions

- Date
- Accounts
- SalesReps
- Products
- Campaigns

## Facts

- Opportunities
- OpportunityProducts
- Activities
- Leads
- Targets

## Relationships

```text
Accounts 1 ─── * Opportunities
Accounts 1 ─── * Contacts
Accounts 1 ─── * Leads
Accounts 1 ─── * Activities
SalesReps 1 ─── * Opportunities
SalesReps 1 ─── * Activities
SalesReps 1 ─── * Targets
Opportunities 1 ─── * OpportunityProducts
Products 1 ─── * OpportunityProducts
Campaigns 1 ─── * Opportunities
```

## Modeling note

The CRM data contains duplicate Opportunity IDs. Do not hide this by forcing an invalid one-to-many relationship. Use a data-quality diagnostic and, for a production system, resolve the source-data issue before relying on opportunity-level uniqueness.
