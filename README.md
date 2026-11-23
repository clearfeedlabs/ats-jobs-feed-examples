# ATS Jobs Scraper API: Greenhouse, Lever, Ashby & Recruitee: examples

Normalized job postings from companies using supported ATS public APIs (Greenhouse, Lever, Ashby, Recruitee, Personio, Teamtailor, Pinpoint, Polymer). Salary, location, remote flags. Incremental mode returns only new, changed and removed jobs. AI-agent & MCP ready. This is not a LinkedIn or Indeed scraper. No login and no proxies.

This repo shows how to call the [ATS Jobs Feed](https://apify.com/clearfeedlabs/ats-jobs-feed) Apify Actor from JavaScript or Python, and what the output looks like.

## First run

Start with one known board and a low `maxItems`. A tested official-API input from 23 November 2026 (2:29 PM CT) is:

```json
{
  "companies": ["greenhouse:airbnb"],
  "maxItems": 2,
  "includeDescription": false
}
```

That run returned 2 of 196 open jobs (descriptions off). The [published sample](https://clearfeedlabs.com/samples/ats-jobs-feed/) is those two rows. Other safe first inputs used in public examples include `https://jobs.lever.co/spotify` and `https://jobs.ashbyhq.com/ramp`.

1. Open the [Actor on Apify](https://apify.com/clearfeedlabs/ats-jobs-feed) and add one known board (`greenhouse:airbnb` or a jobs URL). Set `maxItems` to 2–10.
2. Run it. If you passed nothing, current builds succeed with a message telling you how to add companies — that is not a failed run.
3. If a company does not resolve, read `COMPANY_REPORT` in the run's key-value store. The run can still succeed with zero jobs.
4. Turn on incremental mode only after a first snapshot-style run has worked. If incremental history cannot be stored, build 0.1.25 continues without history and says so, instead of failing.

A step-by-step walkthrough is in the [first-run guide](https://clearfeedlabs.com/guides/ats-jobs-feed/). Product page and pricing: [clearfeedlabs.com/actors/ats-jobs-feed](https://clearfeedlabs.com/actors/ats-jobs-feed/).

**Billing** (23 November 2026): job event **$0.002** each ($2.00 per 1,000; as low as $1.40 on Gold), plus a start fee. Worked example: 2 jobs ≈ **$0.004** plus start. The $2 per 1,000 list price is for normalized job rows (including salary, seniority and lifecycle fields when the board publishes them), not a bare title-and-URL feed. The [Store page](https://apify.com/clearfeedlabs/ats-jobs-feed) always shows current prices.

Zero jobs with a successful status usually means the board was not found, the filters excluded everything, or the name probe missed. That is often a coverage or input issue, not a crash.

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

See `sample-output.json` for one trimmed record, or the [published sample CSV](https://clearfeedlabs.com/samples/ats-jobs-feed/) for two official Greenhouse rows with descriptions omitted.

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

## Related Clearfeed Labs Actors
- [Internship & New Grad Jobs Feed](https://apify.com/clearfeedlabs/entry-jobs-feed): internships and new-grad roles with H-1B history
- [SEC Form D Funding Feed](https://apify.com/clearfeedlabs/form-d-funding-feed): newly funded companies from SEC Form D
- [Company Contact Enrichment](https://apify.com/clearfeedlabs/company-contact-enrichment): emails, phones and socials for a list of domains ([site](https://clearfeedlabs.com/actors/company-contact-enrichment/), [sample](https://clearfeedlabs.com/samples/company-contact-enrichment/))
- [All Clearfeed Labs Actors](https://apify.com/clearfeedlabs)

## FAQ
**Is this data official?** Yes. It comes from public, official job-board APIs, and each record links back to the board.
**Do I need a login or proxy?** No. It uses documented public endpoints only.
**Can I schedule it?** Yes. Use Apify Schedules, the API or integrations (Zapier, Make, webhooks, MCP-compatible AI agents). Turn on incremental mode only after a first snapshot-style run has worked.

## Links
- Actor on the Apify Store: https://apify.com/clearfeedlabs/ats-jobs-feed
- Details & pricing: https://clearfeedlabs.com/actors/ats-jobs-feed/
- First-run guide: https://clearfeedlabs.com/guides/ats-jobs-feed/
- Sample CSV: https://clearfeedlabs.com/samples/ats-jobs-feed/
- Clearfeed Labs: https://clearfeedlabs.com
- Bugs or questions: open an issue on the Actor's Issues tab on Apify, or use https://clearfeedlabs.com/contact/

Data comes from public sources and is provided as-is. Check the original source before relying on it. Not legal, financial or investment advice.

License: MIT
