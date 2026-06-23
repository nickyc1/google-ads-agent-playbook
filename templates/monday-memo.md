# Google Ads Monday Memo

Use this as the weekly Google Ads operator memo.

The report should answer one question first:

Did the last 7 days make money or not?

Then it should show the few things that matter this week.

```text
📊 Google Ads — Last 7 Days ({start_date} → {end_date})

{profit_status_icon} {profitable_or_unprofitable} week · ${spend} spend → ${profit} profit ({profit_to_spend} P:S)
Date generated: {generated_date}
Main thing to watch: {short_watch_item}

Last 7 Days
• Spend: ${spend} ({spend_delta} vs previous 7 days)
• Gross Sales: ${gross_sales}
• Gross Profit: ${gross_profit}
• Profit : Spend: {profit_to_spend} (target ≥ {target_profit_to_spend})
• Buyers: {buyers_total} ({new_buyers} new / {returning_buyers} returning)
• New Buyer %: {new_buyer_percent} (target {new_buyer_target})
• CAC (New): ${new_cac} (target ≤ ${new_cac_target})
• New Buyer Profit: ${new_buyer_profit} ({new_buyer_profit_percent} of spend, goal {new_buyer_profit_goal})

Month to Date
• Spend: ${mtd_spend}
• Gross Profit: ${mtd_gross_profit}
• Profit : Spend: {mtd_profit_to_spend}
• Buyers: {mtd_buyers_total} ({mtd_new_buyers} new / {mtd_returning_buyers} returning)
• CAC (New): ${mtd_new_cac}
• New Buyer Profit: ${mtd_new_buyer_profit} ({mtd_new_buyer_profit_percent} of spend, goal {new_buyer_profit_goal})
• Pacing: forecast ${forecast_spend_or_profit} vs goal ${goal} ({pacing_delta}, {pacing_delta_percent})
  {days_elapsed}/{days_in_period} days · ${daily_run_rate}/day run rate · {days_remaining} days remaining

────────────────────

🏆 Wins
• {win_1_name} — {win_1_metric} · ${win_1_spend} spend · {why_it_matters}
• {win_2_name} — {win_2_metric} · ${win_2_spend} spend · {why_it_matters}
• {win_3_name} — {win_3_metric} · ${win_3_spend} spend · {why_it_matters}

⚠️ Watch / Worry
• {worry_1_name} — {worry_1_metric} · ${worry_1_spend} spend · {problem}
• {worry_2_name} — {worry_2_metric} · ${worry_2_spend} spend · {problem}

🚀 Opportunities
• {opportunity_1} — {opportunity_1_signal} → {recommended_action}
• {opportunity_2} — {opportunity_2_signal} → {recommended_action}
• {opportunity_3} — {opportunity_3_signal} → {recommended_action}

────────────────────

🎯 This Week's Moves
1. {move_1_icon} {move_1_action} — {move_1_reason}
2. {move_2_icon} {move_2_action} — {move_2_reason}
3. {move_3_icon} {move_3_action} — {move_3_reason}
4. {move_4_icon} {move_4_action} — {move_4_reason}

✅ Action Items From Slack + Granola
1. {action_item_1} — owner: {owner} · source: {slack_or_granola_link} · due: {due_date}
2. {action_item_2} — owner: {owner} · source: {slack_or_granola_link} · due: {due_date}
3. {action_item_3} — owner: {owner} · source: {slack_or_granola_link} · due: {due_date}

Priority for this week:
{one_sentence_priority}

Automated with {workflow_or_agent_link}
```

## Data Requirements

The last 7 days section should come from ad platform, ecommerce, analytics, and
margin data.

The action-items section should come from Slack and meeting notes.

If available, pull:

- open Slack asks, decisions, blockers, and owner mentions
- Granola meeting notes, action items, unanswered questions, and follow-ups
- previous Monday memo action items that remain unfinished
- campaign changes promised in Slack but not yet applied
- tracking, feed, landing-page, creative, or budget issues mentioned in meetings

## Slack + Granola Recap Instructions

Use Slack and Granola MCPs, CLIs, exports, or APIs where available.

Search for:

- Google Ads
- Merchant Center
- campaign names
- product/feed issues
- tracking or attribution issues
- landing-page issues
- budget or pacing conversations
- promo, launch, or inventory context
- explicit phrases like "todo", "follow up", "blocked", "next week", "need to"

For every action item, capture:

- task
- owner
- source
- date mentioned
- due date if available
- status
- why it matters to this week's Google Ads priorities

## Writing Rules

- Replace "yesterday" with "last 7 days."
- Keep the generated date in the header.
- Use real numbers.
- Do not include every campaign. Surface the few that matter.
- Do not include private campaign names in public examples.
- Use generic placeholders when publishing examples.
- Keep the memo short enough to read in Slack.
- End with decisions and action items, not analysis drift.

## Status Icons

Suggested icons:

- 🟢 profitable / on target
- 🟡 mixed / watch
- 🔴 unprofitable / off target
- 🏆 win
- ⚠️ watch or worry
- 🚀 opportunity
- ✂️ cut
- 📈 scale
- 🧪 test
- 🛠️ fix
