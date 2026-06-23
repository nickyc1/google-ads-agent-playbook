# Monday Operating System

Monday should not start with a marketer clicking through Google Ads hoping to
notice something.

The agent should already have pulled the data, compared it to the right
baseline, flagged what changed, and turned the account into a decision memo.

## Inputs

Pull at minimum:

- Google Ads spend, revenue, conversions, CPA, ROAS, impression share, search
  terms, asset performance, product performance, and change history
- Merchant Center product status, item issues, disapprovals, warnings, feed
  freshness, product counts, and custom labels
- ecommerce or CRM revenue, orders, margin, refunds, inventory, and product
  availability
- analytics sessions, conversion rate, landing-page performance, and channel
  overlap
- business context: promos, launches, inventory constraints, email sends, Meta
  activity, creative tests, and merchandising priorities

## Monday Memo Sections

The agent should answer:

- Was the last 7 days profitable or not?
- What changed versus the previous 7 days?
- What won?
- What needs attention?
- What opportunities should get more traffic or budget?
- What moves should happen this week?
- What action items are still pending from Slack and meeting notes?

## Decision Rules

### Hold

Hold when performance moved inside normal variance and no structural issue is
visible.

Do not invent work because a dashboard exists.

### Investigate

Investigate when there is a meaningful metric movement without a clear cause.

Examples:

- spend jumped but conversion volume did not
- conversion rate changed only on one landing page
- product spend moved into a lower-margin category
- CPC rose across non-brand search terms
- PMax shifted spend toward a weak product family

### Fix

Fix before optimizing when something is broken.

Examples:

- purchase conversion action stopped firing
- disapprovals hit revenue-driving products
- out-of-stock products are still receiving spend
- feed prices do not match landing pages
- final URLs are broken

### Test

Test when there is a clear hypothesis, a defined success metric, and enough
traffic to learn.

### Scale

Scale when the account has enough signal, the business can absorb more demand,
and the winner is not just branded or remarketing traffic in disguise.

### Cut

Cut when spend crossed the stop-loss threshold and the leading indicators do
not justify more learning.

## Action Items From Slack And Meeting Notes

The Monday memo should include operational context from Slack and meeting
notes, not only ad-platform data.

Use Slack and Granola MCPs, CLIs, exports, or APIs where available to pull:

- open asks
- blockers
- owner mentions
- promised campaign changes
- tracking or feed issues
- promo, launch, or inventory context
- meeting action items
- unanswered questions

The agent should dedupe these into a short weekly action list with owner,
source, due date, status, and why it matters to Google Ads performance.

## Output

The operator should leave Monday with:

- 0 to 3 account changes
- 0 to 3 investigations
- 0 to 2 new tests
- a short list of feed or tracking fixes
- one written reason for every meaningful decision
- a short list of pending cross-functional action items

If Monday produces 17 recommendations, the agent did not prioritize.
