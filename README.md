# Google Ads Agent Playbook

A public playbook for giving an AI agent real Google Ads operating judgment.

Most AI ad workflows start in the wrong place.

They connect the agent to Google Ads, give it API access, and then ask it to
"optimize performance."

That is not enough.

API access gives the agent hands. This repo gives it judgment.

Use this repo to teach an agent how to read Google Ads, Merchant Center,
campaign data, bidding, audiences, reporting, and account changes like a real
operator.

The goal is not to make an agent reckless. The goal is to make reporting,
diagnosis, and decision support faster, more consistent, and easier to audit.

## Start Here

1. [Agent operating system](agent/google-ads-agent-system-prompt.md)
2. [Context loading order](agent/context-loading-order.md)
3. [Monday operating system](playbooks/monday-operating-system.md)
4. [Reporting and measurement](playbooks/reporting-and-measurement.md)
5. [Daily optimization workflow](playbooks/daily-optimization-workflow.md)

## Core Playbooks

- [Google Shopping playbook](playbooks/google-shopping-playbook.md)
- [Performance Max playbook](playbooks/performance-max-playbook.md)
- [Search campaigns playbook](playbooks/search-campaigns-playbook.md)
- [AI Max for Search playbook](playbooks/ai-max-search-playbook.md)
- [Strategic growth principles](playbooks/strategic-growth-principles.md)
- [Demand Gen and YouTube playbook](playbooks/demand-gen-youtube-playbook.md)
- [YouTube creator partnerships playbook](playbooks/youtube-creator-partnerships-playbook.md)
- [Merchant Center and feed playbook](playbooks/merchant-center-feed-playbook.md)
- [Bidding playbook](playbooks/bidding-playbook.md)
- [Audience playbook](playbooks/audience-playbook.md)
- [Reporting and measurement](playbooks/reporting-and-measurement.md)
- [Daily optimization workflow](playbooks/daily-optimization-workflow.md)
- [Safety and change management](playbooks/safety-and-change-management.md)

## Templates

- [Monday memo](templates/monday-memo.md)
- [Daily Slack report](templates/daily-slack-report.md)
- [Change log](templates/change-log.md)
- [Experiment plan](templates/experiment-plan.md)

## How To Use This With An Agent

Give the agent the system prompt first.

Then load only the relevant playbooks for the job.

For example:

- Weekly account review: Monday operating system + reporting + measurement
- Shopping issue: Merchant Center feed + Google Shopping + reporting
- PMax audit: Performance Max + Merchant Center feed + bidding + measurement
- Strategic growth review: strategic growth principles + reporting + relevant campaign playbooks
- YouTube creator partnership test: YouTube creator partnerships + Demand Gen and YouTube + measurement + safety
- Budget decision: reporting + bidding + safety
- Search waste review: Search campaigns + daily optimization + safety

Do not load every file for every task. More context is not always better.

## Operating Principle

An AI agent should not touch ad spend until it can explain the account.

Good Google Ads management is mostly:

- clean measurement
- understanding what demand is being captured
- knowing the difference between brand, non-brand, prospecting, and remarketing
- feed quality
- campaign structure
- bidding discipline
- product-level and query-level control
- budget allocation
- knowing when not to change anything

This repo is designed to give an agent that operating layer.

## What This Repo Is Not

This is not a hacky list of tactics.

This is not a promise that AI should fully manage your account.

This is not a replacement for business judgment.

The agent should surface decisions. A human still owns the strategy, risk, and
taste.

## Decision Format

When the agent recommends a change, it should use this format:

```text
Observation:

Impact:

Evidence:

Recommended action:

Risk:

Confidence:

Rollback:
```

If the agent cannot fill that out, it should not recommend the change.

## License

MIT
