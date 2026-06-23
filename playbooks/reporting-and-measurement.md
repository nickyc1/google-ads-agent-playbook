# Reporting And Measurement Playbook

Reporting is the first Google Ads agent workflow.

Do not let an agent change campaigns until it can explain what happened and
where the numbers came from.

## Reporting Views

### Executive view

Purpose: decide whether the account is moving the business.

Include:

- spend
- revenue
- gross profit or contribution margin when available
- purchases or qualified conversions
- blended CAC or CPA
- in-platform ROAS and true business ROAS side by side
- new-customer performance when available
- budget pacing
- major risks

### Operator view

Purpose: decide what to do next.

Include:

- campaign performance
- asset group performance
- search term movement
- product or listing group performance
- location, device, audience, and time patterns
- conversion action mix
- change history
- Merchant Center issues

### Product view

Purpose: understand what inventory is actually making or wasting money.

Include:

- product ID
- title
- product type
- custom labels
- price
- margin tier
- inventory status
- Merchant Center approval status
- spend
- clicks
- conversions
- revenue
- ROAS
- contribution margin when available

## Required Comparisons

Never report a number without context.

Compare:

- yesterday versus prior day
- last 7 days versus previous 7 days
- last 30 days versus previous 30 days
- current period versus same period last year when seasonality matters
- campaign result versus account baseline
- product result versus product-family baseline

## Measurement Sources

Use multiple views:

- Google Ads
- Google Analytics
- ecommerce platform
- CRM or offline conversion imports
- payment processor
- BI or warehouse
- margin and inventory data

## Conversion Action Checks

Confirm:

- primary versus secondary conversion actions
- purchase action status
- imported conversion freshness
- duplicate conversion risk
- conversion value accuracy
- currency consistency
- attribution model
- attribution window
- enhanced conversions status
- consent mode impact

## ROAS Warnings

ROAS can be misleading when:

- branded demand is mixed with prospecting
- returning customers are counted as acquisition
- view-through or engaged-view conversions influence the story
- refunds and margin are ignored
- email, Meta, organic, and direct overlap with Google
- conversion values do not match actual revenue

## Good Agent Output

Bad:

```text
ROAS is down 18%. Consider lowering budget.
```

Good:

```text
ROAS is down 18% in Google Ads over the last 7 days, but ecommerce revenue
from Google paid sessions is flat. The drop is concentrated in PMax and
started after the conversion action mix changed. Audit tracking before changing
budget.
```

## Reporting Rule

The report should create decisions, not homework.

Every report should end with:

- what to ignore
- what to watch
- what to fix
- what to change
