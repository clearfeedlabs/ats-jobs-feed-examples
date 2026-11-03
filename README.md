# ATS Jobs Scraper API: Greenhouse, Lever, Ashby & Recruitee: examples

Normalized job postings from companies using supported ATS public APIs (Greenhouse, Lever, Ashby, Recruitee, Personio, Teamtailor, Pinpoint, Polymer). Salary, location, remote flags. Incremental mode returns only new, changed and removed jobs. AI-agent & MCP ready.

This repo shows how to call the [ATS Jobs Feed](https://apify.com/clearfeedlabs/ats-jobs-feed) Apify Actor from JavaScript or Python, and what the output looks like.

## What's new
- README now explains what the $2/1,000 price includes (salary, seniority, lifecycle) vs. bare-bones feeds.

## Use cases
- Job boards and aggregators that need clean, deduplicated listings
- Sales teams tracking which companies are hiring for specific roles
- Recruiters and talent-intelligence dashboards
- AI agents and MCP clients that need structured job data

## Quick start
1. Create a free Apify account and copy your API token from Settings > Integrations.
2. Set it as an environment variable: `export APIFY_TOKEN=...` (never commit it).
3. Edit `input.json`, then run one of:
   - JavaScript: `npm i apify-client && node run.mjs`
   - Python: `pip install apify-client && python run.py`

## Output fields (first of many)
`atsJobId`, `ats`, `company`, `companySlug`, `title`, `department`, `team`, `locations`, `workplaceType`, `isRemote`, `employmentType`, `salary`, `descriptionHtml`, `applyUrl`, `jobUrl`, `postedAt`, `updatedAt`, `sourceUrl`

See `sample-output.json` for one trimmed record.

## Ready-made example tasks
- [Ashby jobs scraper](https://apify.com/clearfeedlabs/ats-jobs-feed/examples/ashby-jobs-scraper)
- [Companies hiring security leaders](https://apify.com/clearfeedlabs/ats-jobs-feed/examples/companies-hiring-security-leaders)
- [Daily new job alerts](https://apify.com/clearfeedlabs/ats-jobs-feed/examples/daily-new-job-alerts)
- [Data science ai ml jobs](https://apify.com/clearfeedlabs/ats-jobs-feed/examples/data-science-ai-ml-jobs)
- [Eu tech jobs europe](https://apify.com/clearfeedlabs/ats-jobs-feed/examples/eu-tech-jobs-europe)
- [Greenhouse jobs scraper](https://apify.com/clearfeedlabs/ats-jobs-feed/examples/greenhouse-jobs-scraper)
- [Job postings with salary data](https://apify.com/clearfeedlabs/ats-jobs-feed/examples/job-postings-with-salary-data)
- [Lever jobs api](https://apify.com/clearfeedlabs/ats-jobs-feed/examples/lever-jobs-api)
- [Remote startup engineering jobs](https://apify.com/clearfeedlabs/ats-jobs-feed/examples/remote-startup-engineering-jobs)
- [Sales go to market jobs](https://apify.com/clearfeedlabs/ats-jobs-feed/examples/sales-go-to-market-jobs)

## Pricing
Pay per result: **$2.00 per 1,000 jobs**, with no subscription. The [Store page](https://apify.com/clearfeedlabs/ats-jobs-feed) always shows current prices and every optional add-on event.

## FAQ
**Is this data official?** Yes. It comes from the public source named above, and each record links back to it.
**Do I need a login or proxy?** No. It uses documented public endpoints only.
**Can I schedule it?** Yes. Use Apify Schedules, the API or integrations (Zapier, Make, webhooks, MCP-compatible AI agents).

## Links
- Actor on the Apify Store: https://apify.com/clearfeedlabs/ats-jobs-feed
- Details & pricing: https://clearfeedlabs.com/actors/ats-jobs-feed/
- Clearfeed Labs: https://clearfeedlabs.com
- Bugs or questions: open an issue on the Actor's Issues tab on Apify.

Data comes from public sources and is provided as-is. Check the original source before relying on it. Not legal, financial or investment advice.

License: MIT
