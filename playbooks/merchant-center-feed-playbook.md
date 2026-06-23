# Merchant Center And Feed Playbook

For ecommerce Google Ads, the feed is the campaign.

Search campaigns can survive a mediocre website for a while because the query
does a lot of the work. Shopping and PMax cannot. They run on product data.

If Merchant Center is messy, Google is making decisions from bad inputs:

- old products
- missing attributes
- generic titles
- stale URLs
- duplicate product families
- weak categories
- missing custom labels
- out-of-stock products
- products that are live on the site but absent from the feed
- products in the feed that should not be advertised

The agent should inspect Merchant Center and product data before assuming the
problem is bidding or budgets.

## Operating Principle

Do not ask the agent to "optimize Merchant Center."

Ask:

```text
What is stopping Google Shopping from spending money on the right products?
```

That question changes the work.

Not every feed issue matters. A missing optional attribute on a product that
has never received a click is not the same as a landing-page error on a hero
product. A shipping warning in a country you do not sell to is not the same as
a primary-market disapproval on a product family you want to scale.

The agent should separate:

- revenue blockers
- eligibility blockers
- cleanup work
- warnings that can wait
- issues outside the primary market
- products that should intentionally be excluded

## Product Truth Table

Build one table that joins product truth across systems.

At minimum:

| Source | Why it matters |
|---|---|
| Store platform | Active products, variants, inventory, product type, tags, cost |
| Sitemap or live URL crawl | Confirms whether the public page exists |
| Merchant Center products | Feed attributes, IDs, titles, descriptions, images, labels |
| Merchant Center statuses | Approval status, destinations, countries, issue codes |
| Google Ads product performance | Spend, clicks, conversions, revenue, search categories |
| Margin / merchandising data | Which products should receive spend |
| Manual rules | Product-family rules, title templates, category rules, label rules |

Each product should end up in one of these states:

| State | Meaning | Action |
|---|---|---|
| Live + eligible | Page is live, in feed, approved, and controllable | Ready for labels, titles, images, and campaign tests |
| Live + broken | Page is live, but feed data or approval blocks serving | Fix first |
| Feed stale | Product is in Merchant Center, but no longer live or intended | Exclude or remove |
| Live missing from feed | Product is live, but absent from Merchant Center | Fix sync or document exclusion |
| Intentionally excluded | Product should not receive paid Shopping traffic | Keep documented exclusion reason |

Without this table, operators end up optimizing campaigns around products that
may not even be eligible to show.

## Daily Feed Triage

Run this before campaign changes.

1. Pull the latest Merchant Center products and product statuses.
2. Pull active store products and variants.
3. Compare Merchant Center parent URLs with live product URLs.
4. Flag live products missing from Merchant Center.
5. Flag Merchant Center products that are no longer live.
6. Flag live in-stock products with disapprovals, limited visibility, or
   missing required attributes.
7. Confirm out-of-stock rows are excluded from paid campaign groups.
8. Confirm feed fetches, supplemental feeds, and rules ran successfully.

The first daily alert should focus on live, in-stock, primary-market products
with errors.

A stale product that is disapproved matters less than a live hero product that
cannot serve.

## Priority Fix Queue

### P0: Live Products Blocked From Serving

Fix these before title tests, campaign restructures, or bid changes.

Examples:

- primary-market disapprovals
- landing-page errors
- price mismatch
- availability mismatch
- image crawl errors
- required apparel attributes missing
- missing shipping or tax settings where required
- destination eligibility issues on products you want to advertise

For apparel, each variant usually needs clean:

- age group
- gender
- color
- size
- material or pattern when relevant
- Google product category
- internal product type

### P1: Classification And Product Types

Campaign control depends on feed taxonomy.

If product types and categories are sloppy, the account cannot separate hero
products, bundles, apparel types, margin tiers, or tests.

Review:

- product type
- Google product category
- brand
- item group ID
- variant attributes
- product family
- URL handle
- collection or category

The agent should identify where products are technically eligible but
operationally unmanageable.

Example pattern:

```text
Products are approved, but several product families share the same generic
product type. This blocks clean Shopping product groups and PMax listing
groups.
```

### P2: Custom Labels

Custom labels are the control panel for Shopping and PMax.

Recommended label allocation:

| Label | Use | Example values |
|---|---|---|
| `custom_label_0` | Product family | `tee`, `hoodie`, `polo`, `short`, `bundle`, `accessory`, `exclude` |
| `custom_label_1` | Pack size / offer type | `single`, `2_pack`, `3_pack`, `6_pack`, `bundle`, `subscription` |
| `custom_label_2` | Margin tier | `high_margin`, `mid_margin`, `low_margin`, `unknown_margin` |
| `custom_label_3` | Sales tier | `hero`, `proven`, `test`, `weak`, `new` |
| `custom_label_4` | Campaign role | `acquisition`, `aov_builder`, `remarketing`, `seasonal`, `exclude` |

Do not overload one label with multiple meanings.

Bad:

```text
custom_label_0 = high_margin_hoodie_new_customer
```

Good:

```text
custom_label_0 = hoodie
custom_label_2 = high_margin
custom_label_4 = acquisition
```

### P3: Titles

Titles influence matching and what shoppers see.

Do not reduce title work to "brand first" versus "brand last."

For each product family, decide which truthful attribute deserves the earliest
position:

- product category
- pack quantity
- primary benefit
- use case
- material
- fit
- design
- color or size
- brand

The first 70 characters matter because titles are truncated.

Good title testing starts with product-family templates, not one universal
formula.

Example title angles:

| Angle | Pattern |
|---|---|
| Product-first | `{gender} {design} {product_type}, {pack_size} - {benefit}` |
| Pack-first | `{pack_size} {gender} {product_type} - {benefit}` |
| Benefit-first | `{benefit} {gender} {product_type}, {pack_size}` |
| Use-case-first | `{use_case} {product_type}, {pack_size} - {feature}` |
| Design-first | `{design} {product_type} for {audience}, {pack_size}` |

Use supplemental feeds or feed rules so changes are reversible. Keep stable
product IDs.

### P4: Images

Image tests should happen only after the product is eligible, labeled, and
controllable.

Maintain image candidates:

- current main image
- clean product image
- lifestyle image
- bundle or pack image
- variant/color-specific image
- use-case image

Avoid promotional overlays or inaccurate lifestyle images that create policy or
message-match problems.

### P5: Product Page Match

Shopping optimization does not end in Merchant Center.

For important products, check:

- Does the page hero match the feed-title angle?
- Does the page support the search intent implied by the ad?
- Are price, availability, size, color, shipping, returns, reviews, and pack
  contents clear?
- Does the page handle the main objection before the CTA?
- Does structured data match the visible page and feed?

If the title earns a different kind of click than the page can convert, the
test will look like a feed problem when it is actually a page problem.

## Duplicate Product Family Audit

Large catalogs collect history.

Old products, seasonal drops, renamed products, bundles, unpublished pages, and
feed-app quirks can create duplicate or confusing product families.

Ask the agent:

```text
Find products with duplicate or overly generic titles.
Group them by source product ID, item group ID, URL handle, price range,
country, and approval status.
Tell me if these are true variants of one product or separate product families
sharing the same title.
```

The agent should classify:

- true variants of one product
- separate products with lazy titles
- old products still syncing
- active products that need clearer naming
- products that should be excluded

Do not merge or redirect products only because titles look similar. First check
whether the replacement product already exists as an approved listing.

## Landing Page Error Audit

Landing page issues require an action decision, not just a flag.

Ask the agent:

```text
Find all products with landing page errors.
Check current URL status.
If there is a likely replacement page, check whether that replacement already
exists in Merchant Center.
Recommend one of: fix URL, redirect source page, exclude old product, remove
stale product, or investigate.
```

This prevents the common mistake of repointing an old product to a new page
when the new product already exists as its own offer.

## Missing Live Product Audit

Ask:

```text
Find live store products missing from Merchant Center.
Separate products that should be advertised from products intentionally
excluded from paid Shopping.
```

A product that is live but absent from Merchant Center may be:

- accidentally excluded by the feed app
- missing required store fields
- blocked by collection or channel rules
- intentionally kept out of Shopping
- not worth advertising because of margin, inventory, or compliance

The agent should not assume every live product belongs in paid Shopping.

## Zero-Click Product Audit

For products that are live, approved, and in stock but receive no meaningful
traffic, check:

- title clarity
- image quality
- price competitiveness
- product category
- product type
- custom labels
- campaign inclusion
- product group or listing group exclusion
- search demand
- whether the product is too niche to deserve budget

The fix may be title work. It may also be exclusion.

Not every product deserves paid spend.

## Rule Engine

Start with transparent rules, not AI guessing.

Every proposed fix should show:

- field being changed
- current value
- proposed value
- reason
- confidence
- source rule
- approval status

Example deterministic rules:

- URL contains `hoodie` -> product family = `hoodie`
- title contains `6-pack` -> pack size = `6_pack`
- product type is blank and URL contains `shorts` -> product type = `shorts`
- product is gift card, warranty, shipping protection, or donation -> campaign
  role = `exclude`

AI can suggest rules. Humans should approve the rules before write actions.

## Supplemental Feed Workflow

Use supplemental feeds when you want reversible overrides.

Good supplemental feed use cases:

- title tests
- custom label backfills
- product type corrections
- campaign role labels
- test labels

Avoid using supplemental feeds as a messy second source of truth. Document
which system owns each field.

## Weekly Maintenance

1. Review P0 and P1 queues.
2. Confirm all new live products are present in Merchant Center.
3. Confirm removed products are excluded or removed.
4. Update custom labels from latest sales, margin, and inventory data.
5. Review zero-click live products.
6. Review search terms and product-level performance before moving products
   between campaign groups.
7. Re-run title or image tests only on products that remain eligible.

## Monthly Audit

1. Rebuild the full product truth table.
2. Compare store, sitemap, Merchant Center products, Merchant Center statuses,
   and Ads performance.
3. Check product families for copied descriptions or wrong inherited values.
4. Refresh product-title formulas by family.
5. Refresh image candidates and creative notes.
6. Archive or exclude stale offers.
7. Document all feed rules changed during the month.

## Agent Rule

Before recommending a campaign change for Shopping or PMax, confirm whether
the affected products are eligible, in stock, correctly labeled, aligned with
the landing page, and worth advertising.
