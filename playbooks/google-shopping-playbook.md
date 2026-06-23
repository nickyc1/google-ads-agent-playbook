# Google Shopping Playbook

Shopping campaigns are built on product data, not keywords.

The feed decides what can show. Product groups decide what the campaign can
control. Measurement decides whether the account is learning the right thing.

If Search is query-first, Shopping is catalog-first.

## When To Use Standard Shopping

Use Standard Shopping when you need:

- product-level control
- cleaner feed, title, or image tests
- margin or product-family segmentation
- campaign priority controls across Standard Shopping campaigns
- more direct bid control
- a clearer view than PMax provides
- a controlled comparison against PMax

Standard Shopping is not automatically better than PMax. It is more
controllable. That matters when the account needs a clean test or when PMax is
blending too much product, brand, and remarketing behavior together.

## Shopping Mental Model

Shopping campaigns have no keywords.

The matching chain looks like this:

```text
Merchant Center feed
→ product attributes
→ Shopping campaign
→ ad group
→ product groups
→ bids / exclusions
→ eligible Shopping ads
```

If the feed is too generic, the campaign cannot be specific.

If custom labels are missing, the campaign cannot separate margin, inventory,
sales tier, or campaign role.

If product IDs change, history breaks.

If product groups are stale, approved products may still not serve.

## Product Group Basics

Product groups are how Standard Shopping campaigns include, subdivide, bid on,
or exclude inventory.

Common subdivisions:

- item ID
- brand
- product type
- Google product category
- condition
- channel
- custom labels

The lowest-level product groups are where bids or exclusions apply. If a
parent product group is subdivided, the parent is only a container.

## Product Group Failure Modes

### Product is in Merchant Center but not available in the campaign

Check:

1. Is the product approved for Shopping ads?
2. Is it in stock?
3. Is it included in an active product group?
4. Is it excluded at a parent or child level?
5. Is a campaign inventory filter blocking it?
6. Did the feed taxonomy or item ID change?
7. Is the product in the right country and destination?

### Product group structure is too blunt

If everything sits under `All products` or one generic product type, the
campaign cannot separate:

- heroes
- bundles
- low-margin products
- seasonal items
- product tests
- stale products
- acquisition products
- AOV builders

Fix feed taxonomy and labels before rebuilding campaign structure.

### Product groups no longer match the feed

Changing Merchant Center attributes does not automatically rebuild existing
Google Ads product groups.

If product types, categories, or custom labels change, review the product group
tree.

## Campaign Structure Options

Choose structure based on the business decision you need to make.

### Simple structure

Use when:

- catalog is small
- conversion volume is low
- feed labels are immature
- you need clean learning before segmentation

Example:

```text
Shopping - Core Products
```

### Product-family structure

Use when product families have different economics or roles.

Example:

```text
Shopping - Apparel
Shopping - Accessories
Shopping - Bundles
Shopping - Clearance
```

### Margin-tier structure

Use when ROAS targets should differ by economics.

Example:

```text
Shopping - High Margin
Shopping - Mid Margin
Shopping - Low Margin / Controlled
```

### Test structure

Use when you are isolating feed, title, image, or landing-page experiments.

Example:

```text
Shopping - Title Test - Control
Shopping - Title Test - Treatment
```

Only split when the test can get enough traffic and when other variables are
controlled.

## Campaign Priority

Campaign priority applies to overlapping products across Standard Shopping
campaigns.

It does not make a PMax campaign the high-priority tier of a Shopping
waterfall.

Use campaign priority carefully. It can help route traffic in controlled
Standard Shopping structures, but it can also create confusing behavior if
products overlap unintentionally.

## Bidding

Shopping can use manual or automated bidding depending on the account stage.

### Manual CPC

Useful when:

- conversion data is limited
- you need tight bid control
- you are running a small test

Risk:

- does not use auction-time signals fully
- can be tedious at scale

### Target ROAS / Max Conversion Value

Useful when:

- revenue tracking is clean
- conversion volume is adequate
- product economics are reasonably consistent or segmented

Risk:

- platform revenue may not equal profit
- low-margin products can look good on ROAS but bad for the business
- targets can starve learning if set too tight

## Title Tests

Title testing is one of the highest-leverage Shopping tests because titles
influence both matching and shopper understanding.

Test by product family.

Do not test five title formulas across the whole catalog at once.

Recommended sequence:

1. Fix eligibility and labels.
2. Pick 10-20 comparable products or matched product pairs.
3. Choose one hypothesis.
4. Override treatment titles through supplemental feed or feed rules.
5. Keep product IDs stable.
6. Keep image, price, promotion, bidding, and campaign membership stable.
7. Review first 70 characters before launch.
8. Judge on business metrics, not CTR alone.

Example title angles:

- product-first
- pack-first
- benefit-first
- use-case-first
- design-first

Primary metrics:

- contribution-margin ROAS
- new-customer CAC
- revenue per click

Diagnostic metrics:

- non-brand impressions
- search category relevance
- CTR
- CPC
- conversion rate

## Image Tests

Test clean product images against accurate lifestyle or in-context images.

Keep the product prominent and avoid inaccurate overlays or promotional claims.

Run image tests separately from title tests when possible. If both change at
once, you will not know which change drove the result.

## Product Page Message Match

The product page has to confirm the promise that earned the click.

For each important product family, ask:

- Does the page hero match the Shopping title angle?
- Does the page explain the use case?
- Does it show price, availability, variants, returns, shipping, and reviews?
- Does it help the shopper build a cart or choose the right variant?
- Does it support the claim made in the feed?

Good Shopping work often becomes product-page work.

## Merchant Center Promotions

Use Merchant Center promotions when the offer is economically sound and useful
to the shopper.

Test:

- free shipping
- gift with purchase
- bundles
- threshold offers
- limited-time offers

Do not assume permanent percent discounts are the only lever.

## Shopping Versus PMax

Use a Standard Shopping versus PMax experiment when the question is control
versus automation.

Do not conclude PMax is "better" only because it captured brand or remarketing
demand.

Separate:

- brand
- non-brand
- returning customers
- new customers
- remarketing
- product family
- margin tier

## Weekly Shopping Review

1. Check Merchant Center P0 issues.
2. Review product-level spend and revenue.
3. Review product groups for stale or missing products.
4. Review zero-click eligible products.
5. Review high-spend no-conversion products.
6. Review title and image test cohorts.
7. Review spend share by margin and sales tier.
8. Decide which products to scale, fix, test, exclude, or hold.

## Agent Rule

Do not call Shopping performance a bidding problem until you have checked feed
quality, product eligibility, product groups, custom labels, landing-page
match, measurement, and product economics.
