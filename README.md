# Cornerstone Jobs Scraper & API - All CSOD Career Sites, Remote

Cornerstone jobs scraper and API: search every company's career site on Cornerstone OnDemand (csod.com) at once, live, and get each job's title, company, location, remote flag, posting date, closing date and link, newest first. Turn on full details for the description, the address, the apply link and the time the job's requisition was opened, which replaces the posting date.

Use it as a Cornerstone jobs API or CSOD jobs API, a Cornerstone career site scraper or a daily job feed from the Apify Console, the Apify API, Python, JavaScript, n8n, Make or an AI agent through MCP, and export JSON, CSV or Excel. It is the `site:csod.com` Google dork done at the source, and it reaches jobs the dork cannot: nearly half of these jobs sit on career sites closed to search engines. Available as an [Apify Actor](https://apify.com/anshumanatrey/cornerstone-jobs-search). $0.002 per job ($2.00 per 1,000), $0.003 with full details ($3.00 per 1,000), no start fee, no login, no API key.

**Use it from an AI assistant:**

- **Claude** (claude.ai and the desktop app): [Add Cornerstone Jobs to Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Cornerstone%20Jobs&connectorUrl=https%3A%2F%2Fmcp.apify.com%3Ftools%3Danshumanatrey%2Fcornerstone-jobs-search), click Continue, sign in to Apify, Allow, and ask in plain words.
- **All 18 job boards at once:** [Add Job Boards Search to Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Job%20Boards%20Search&connectorUrl=https%3A%2F%2Fmcp.apify.com%3Ftools%3Danshumanatrey%2Fjob-boards-search): one connector to [Job Boards Search](https://apify.com/anshumanatrey/job-boards-search), which searches this board and 17 more in one run, newest first, each job once.
- **Claude Code:** `claude mcp add --transport http cornerstone-jobs-search "https://mcp.apify.com?tools=anshumanatrey/cornerstone-jobs-search"`, then run `/mcp` to sign in to Apify.
- **Codex:** `codex mcp add cornerstone-jobs-search --url "https://mcp.apify.com?tools=anshumanatrey/cornerstone-jobs-search"`, then `codex mcp login cornerstone-jobs-search`.
- **Any other MCP client:** `https://mcp.apify.com?tools=anshumanatrey/cornerstone-jobs-search`, signed in with Apify or an `Authorization: Bearer <APIFY_TOKEN>` header.

## What does it do?

- **Searches 1,110 career sites of 605 employers at once**, about a minute for all of them. 61,000+ open jobs, at employers such as McDonald's, Henkel, Turner Construction, STRABAG, Linde, Kohler, A.S. Watson, CEVA Logistics, the World Bank Group, and many universities and hospitals.
- **One keyword is enough.** Type a job title and press Start. Leave the form empty for the newest jobs of every kind.
- **Newest first, read live.** Every job comes from Cornerstone at the moment of your run, not from a stored copy.
- **Filters that take what people type.** Germany, EMEA, Remote, last 24 hours, or a pasted Google dork such as `site:newcold.csod.com intext:engineer`.
- **Checks job links.** Paste links and each comes back open, closed or not found.

## How is it different from other Cornerstone scrapers?

- **You do not need to know the companies.** One search covers every career site we have found, so a job title finds employers you had never heard of. Other Cornerstone actors take the career-site links you already have.
- **It reaches what Google cannot.** Of 840 hiring career sites, 259 tell search engines to stay away, and they hold 28,525 of 61,090 open jobs (47%, measured 2026-10-30). McDonald's job pages, for example, are marked `noindex`. A `site:` search does not see those jobs.
- **Live, not a database.** Multi-ATS actors sell a stored index; this one asks Cornerstone at run time, so a job it returns was listed when you ran it.
- **A failed read costs nothing.** You pay per delivered row, and a row whose details could not be read is charged as a plain job.

## When should I use it?

- **Job seekers and job boards:** find new jobs at large employers that never reach Google or LinkedIn, on a daily schedule.
- **Recruiters and sourcing teams:** see who is hiring for a role across hundreds of employers.
- **Sales and market research:** spot companies hiring for a function, by country and date, as a buying signal.
- **Data teams and AI agents:** one clean, stable feed of Cornerstone jobs through the API or MCP.

## How much does it cost to scrape Cornerstone jobs?

Cornerstone Jobs Scraper costs $2.00 per 1,000 jobs, or $3.00 per 1,000 with full details, pay per event. Platform usage is included, and there is no start fee or monthly fee.

| Event | Price | When it is charged |
|---|---|---|
| Job | $0.002 | One saved job, and one checked link that is closed or not found |
| Job with details | $0.003 | One saved job with full details on |

Cornerstone Jobs Scraper's Apify Store header, "from $1.60 / 1,000 jobs", shows the lowest discount-tier price, the GOLD price. Each Apify plan sits in a discount tier: FREE (the Free plan) and BRONZE (Starter) pay the base prices above, $0.002 and $0.003; SILVER (Scale) pays 10% less, $0.0018 and $0.0027 ($1.80 and $2.70 per 1,000); GOLD (Business) and the enterprise tiers above it pay 20% less, $0.0016 and $0.0024 ($1.60 and $2.40 per 1,000).

| Job (Free and Starter price) | Cost |
|---|---|
| 100 newest jobs | $0.20 |
| 100 jobs with full details | $0.30 |
| 1,000 jobs | $2.00 |
| 10,000 jobs with full details | $30.00 |

Apify's free $5 monthly credit covers 2,500 jobs ($5 / $0.002), or 1,666 with full details ($5 / $0.003). Number of jobs (`maxJobs`) sets the most a run can cost, and a run stops at its spending limit with a message saying so.

## How does the price compare with other Cornerstone scrapers?

Every actor on the Apify Store that names Cornerstone or CSOD in its title, description or list of platforms, found by searching "cornerstone", "csod", "cornerstone jobs" and "cornerstone ondemand" on 2026-10-30, ordered by users in the last 30 days. Free-plan prices from each listing.

| Actor | Users, 30 days | Per job | Start fee | Covers |
|---|---|---|---|---|
| fantastic-jobs/career-site-job-listing-api | 1,668 | $0.012 | $0.01 | 54 ATS from its own database; `csod` is one filter |
| memo23/career-site-ats-jobs-api | 85 | $0.004 | $0.03 | 116 ATS, Cornerstone among them |
| gefese/cornerstone-jobs-scraper | 1 | $0.0015 | none | Cornerstone, the career-site links you paste |
| gefese/multi-ats-jobs-scraper | 1 | $0.0015 | none | Several ATS, the career-site links you paste |
| This actor | new | $0.002 | none | Cornerstone, every career site with no links needed |

Where others are cheaper: gefese's actors cost less per job when you already have the career-site links. Where others do more: the multi-ATS actors cover many platforms in one run.

## Which inputs does it take?

Cornerstone Jobs Scraper has no required field. Type a job title and press Start, or press Start with the form empty.

| Field | What it does |
|---|---|
| Job titles to find (`searchTerms`) | One per line. A job matches when its title has every word: frontend also finds Front-End. A pasted Google dork or Cornerstone link works too |
| Where the job is (`location`) | A city, state, country or region: London, United States, EMEA, LatAm. Worldwide finds jobs open everywhere, and Remote asks for remote jobs |
| Remote or onsite (`workType`) | remote or hybrid, read from the title and location, since Cornerstone has no remote field. Onsite finds no jobs here, because nothing on Cornerstone marks a job as onsite |
| Posted in the last (`postedWithin`) | 24 hours, 3 days, 7 days, 30 days, any time, or your own period such as 48 hours |
| Number of jobs (`maxJobs`) | How many, newest first: 100 by default, 0 for every match |
| Full details (`includeDetails`) | Adds the description as text and HTML, reference, apply link, city, region and country. Posted on (`postedAt`) then holds the time the job's requisition was opened, not the posting date |
| Leave out words (`excludeTerms`) | Drops jobs whose title has these words, such as senior or intern |
| Match descriptions (`searchDescriptions`) | Finds your words in the description too, not only the title |
| Only these companies (`companies`) | A name (Henkel), the name in the address (henkel) or a career-site link. Empty searches everyone |
| Job links to check (`jobUrls`) | Paste job links to check whether they are still open, instead of searching |

Example input:

```json
{
  "searchTerms": ["software engineer"],
  "location": ["Germany", "United States"],
  "postedWithin": "7 days",
  "maxJobs": 100
}
```

## What does the output look like?

Cornerstone Jobs Scraper returns one row per job, newest first. These rows are from a run on 2026-10-30, build 1.0.1, searching one company for the word engineer in 1 second:

| Job title (`title`) | Company name (`company`) | Main location (`location`) | Posted on (`postedAt`) | Still open? (`status`) |
|---|---|---|---|---|
| Senior Project Engineer | NewCold | Breda, NL | 2026-07-03 | open |
| Senior Network Engineer | NewCold | Breda, NL | 2026-07-03 | open |
| Project Engineer (HBO) | NewCold | Culemborg, NL | 2026-07-03 | open |
| Project Engineer India | NewCold | IN | 2024-09-18 | open |

One row as JSON:

```json
{
  "title": "Senior Project Engineer",
  "company": "NewCold",
  "location": "Breda, NL",
  "otherLocations": [],
  "workType": null,
  "postedAt": "2026-07-03",
  "expiresAt": null,
  "jobUrl": "https://newcold.csod.com/ux/ats/careersite/5/home/requisition/954?c=newcold",
  "applyUrl": "https://newcold.csod.com/ux/ats/careersite/5/home/requisition/954?c=newcold",
  "status": "open",
  "platform": "cornerstone",
  "companySlug": "newcold/5",
  "jobId": "954",
  "checkedAt": "2026-10-30T11:57:07+00:00"
}
```

Full details add `description`, `descriptionHtml`, `reference`, `city`, `region`, `country` and `countryCode`, and `postedAt` then holds the date and time the company opened the job's requisition in Cornerstone, not the posting date. An open checked job link carries that time too, with Full details on or off. The two dates can be far apart: job 954 above was dated 2026-07-03 by a search (run takgbge7em1qt4MaA) and 2024-09-09T16:30:28Z by a link check (run E4Fwz4hH7zSid7e92), both on 2026-11-03. In a search, Posted in the last (`postedWithin`) and the newest-first order use the posting date, with Full details on or off. A run also writes an `OUTPUT` record: how many career sites were read, how many jobs matched and were saved, and any notes on how your input was read.

## How fast is it?

Cornerstone Jobs Scraper searches every career site in 69 seconds at the default 2 GB of memory (run b24SuuFL58CMyduIh, 2026-10-30, 100 newest jobs). A search of named companies takes seconds, and details add a moment per job. An empty form stops reading once Number of jobs is filled with jobs dated today, because nothing can be newer: the default 100 took 2 seconds of reading (run 6AFdE5CkCJmIJwNXH, build 1.0.5, 2026-10-30).

## Common questions

### How much does it cost per 1,000 jobs?

Cornerstone Jobs Scraper costs $2.00 per 1,000 jobs, or $3.00 per 1,000 with full details, on Apify's Free and Starter plans, with no start fee and platform usage included. Scale pays $1.80 and $2.70 per 1,000, and Business and above $1.60 and $2.40, the "from $1.60" in the Store header. The 100 newest jobs cost $0.20.

### Does it work on the Apify free plan?

Cornerstone Jobs Scraper works on the Apify free plan: the plan's $5 monthly credit pays for 2,500 jobs, or 1,666 with full details, and a run costs only its jobs. Number of jobs (`maxJobs`) caps each run, and when the credit or your spending limit runs out, the run stops with the jobs it paid for and says so.

### Why are these jobs not on Google?

Each company's Cornerstone career site has a setting for search engines. Where it is off, the job pages carry `noindex` and no job markup, so Google leaves them out. On 2026-10-30 that was 259 of 840 hiring sites and 47% of open jobs.

### How does it find every company?

Cornerstone Jobs Scraper's list of career sites comes from the Wayback Machine, which lists every archived page under csod.com: that gave 1,754 career sites, and 1,110 still answer. That is the `site:csod.com` idea run on an archive instead of a search engine. To search a company that is not on the list, paste its career-site link into Only these companies.

### How do I search one company?

To search one company on Cornerstone, type it into Only these companies (`companies`): its name (Henkel), the first words of its name (World Bank finds World Bank Group), the name in its address (henkel from henkel.csod.com) or a career-site link. A name finds every career site of that company, and one company takes seconds. As JSON: `{"companies": ["Henkel"], "searchTerms": ["engineer"]}`.

### How do I check a list of job links?

To check a list of Cornerstone job links, paste them into Job links to check (`jobUrls`), one per line. Career-site job links such as `https://newcold.csod.com/ux/ats/careersite/5/home/requisition/954?c=newcold` work, and so do the older `JobDetails.aspx` links. Each comes back open with the job, closed, or not found (no such job or career site), and an open job's `postedAt` is the time its requisition was opened, not the posting date. An open link is a normal Job row ($0.002, or $0.003 with full details), a closed or not-found link is one Job ($0.002), and a link Cornerstone does not answer is not charged and is counted in the run message. Three links took 11 seconds (run 2eQyLTWVArakcCSB8, 2026-10-30).

### Which fields come back?

Every Cornerstone Jobs Scraper row has `title`, `company`, `location`, `otherLocations`, `workType`, `postedAt`, `expiresAt`, `jobUrl`, `applyUrl`, `status`, `platform`, `companySlug`, `jobId` and `checkedAt`. Full details (`includeDetails`) add `description`, `descriptionHtml`, `reference`, `city`, `region`, `country` and `countryCode`. `postedAt` is the posting date in a search, and the time the job's requisition was opened with Full details on or for a checked link. Cornerstone publishes no salary, job type or department, so none comes back. Export as JSON, CSV or Excel.

### How often should I run it?

Running Cornerstone Jobs Scraper once a day gives a fresh feed: schedule it in Apify with Posted in the last (`postedWithin`) set to 24 hours. Cornerstone gives the day a job was posted, not the hour, so 24 hours also keeps the jobs dated the day before, and two daily runs can share a job: keep `jobUrl` as the key to drop repeats.

### Which Cornerstone scraper should I pick?

The right Cornerstone scraper depends on what you start from (Store listings and free-plan prices on 2026-10-30):

- **A job title, across every employer on Cornerstone:** this actor, $0.002 per job, read live, including the 47% of jobs on career sites closed to Google.
- **Career-site links you already have:** gefese/cornerstone-jobs-scraper costs less, $0.0015 per job.
- **Many ATS in one run:** fantastic-jobs/career-site-job-listing-api ($0.012 per job, $0.01 start, 54 ATS from its own database) or memo23/career-site-ats-jobs-api ($0.004 per job, $0.03 start, 116 ATS).
- **A free Google `site:csod.com` search:** it misses the jobs on career sites closed to search engines, 47% of them.

For Ashby, Workday, Deel, Greenhouse, SmartRecruiters, Workable or Lever, use the sibling actors below.

### Does it need a login or an API key?

Cornerstone Jobs Scraper needs no login and no API key: it reads what each career site shows any visitor, with the anonymous access the page itself uses. You need only an Apify account.

### How do I run it from the API, Python, JavaScript, n8n or an AI agent?

Cornerstone Jobs Scraper runs from the API, Python, JavaScript, n8n or an AI agent with the same JSON input as the form and your Apify token, from https://console.apify.com/settings/integrations.

**API:** one HTTP call that runs the actor, waits for it (up to 300 seconds; a search of every career site takes about 70) and returns the rows. Add `?format=csv` for CSV.

```bash
curl -X POST "https://api.apify.com/v2/actors/anshumanatrey~cornerstone-jobs-search/run-sync-get-dataset-items" \
  -H "Authorization: Bearer <YOUR_APIFY_TOKEN>" \
  -H "Content-Type: application/json" \
  -d '{"searchTerms": ["software engineer"], "maxJobs": 100}'
```

**Python** (`pip install apify-client`, version 3 or later; on 2.x write `run["defaultDatasetId"]`):

```python
from apify_client import ApifyClient

client = ApifyClient("<YOUR_APIFY_TOKEN>")
run = client.actor("anshumanatrey/cornerstone-jobs-search").call(run_input={"searchTerms": ["software engineer"]})
for row in client.dataset(run.default_dataset_id).iterate_items():
    print(row["title"], row["company"], row["location"], row["jobUrl"])
```

**JavaScript** (`npm install apify-client`):

```js
import { ApifyClient } from 'apify-client';

const client = new ApifyClient({ token: '<YOUR_APIFY_TOKEN>' });
const run = await client.actor('anshumanatrey/cornerstone-jobs-search').call({ searchTerms: ['software engineer'] });
const { items } = await client.dataset(run.defaultDatasetId).listItems();
for (const job of items) console.log(job.title, job.company, job.location, job.jobUrl);
```

**n8n:** add the Apify node, choose Run Actor with this actor and the JSON input above, then Get Dataset Items with the run's `defaultDatasetId`. In an n8n AI Agent, add it as the Apify Tool. Make has an Apify app too.

**AI agents (MCP):** point your MCP client at `https://mcp.apify.com?tools=anshumanatrey/cornerstone-jobs-search` and the agent gets this actor as its own tool, signing in with Apify or sending your token as a Bearer header. On the default server, `https://mcp.apify.com`, an agent can find it with `search-actors` and run it with `call-actor`.

### Am I charged for closed jobs?

Cornerstone Jobs Scraper charges for a closed job only when you paste its link: a search returns open jobs only, and a pasted link that turns out closed or not found is one Job row, because it was checked and answered.

### Is it legal to use?

Cornerstone Jobs Scraper reads public job postings. You are responsible for how you use the data, including each site's terms and the privacy laws that apply to you.

## Limitations

- Cornerstone publishes no salary, job type, department or remote field, so none is shown. Remote and hybrid are read from the title and location only, and nothing marks a job as onsite, so the onsite choice of Remote or onsite (`workType`) finds no jobs.
- Titles and descriptions come in the company's own language.
- Company names: Cornerstone publishes only the name in the address, so the big employers are written by hand and the rest are read from that name.
- The list of career sites was built on 2026-10-30. A company that joined later is searched only when you name it.
- Some postings are years old: a company may leave a job open for a long time, and it comes back as open because Cornerstone lists it.

## Who maintains it?

Cornerstone Jobs Scraper is built and maintained by **Anshuman Atrey** ([@AnshumanAtrey](https://github.com/AnshumanAtrey)), who publishes a portfolio of data and OSINT actors on Apify Store, among them [linkedin-harvester](https://apify.com/anshumanatrey/linkedin-harvester) (email to LinkedIn profile, for the people behind a company) and [theharvester-osint](https://apify.com/anshumanatrey/theharvester-osint) (domain to emails and subdomains). For a feature request or a bug, message [LinkedIn](https://linkedin.com/in/anshumanatrey) (fastest), open an issue on the GitHub repo, or write through [atrey.dev](https://atrey.dev).

## Sibling actors

| Actor | What it searches |
|---|---|
| [Ashby Jobs Scraper](https://apify.com/anshumanatrey/ashby-jobs-search) | Jobs from every company on Ashby (jobs.ashbyhq.com), searched live |
| [Workday Jobs Scraper](https://apify.com/anshumanatrey/workday-job-search) | Jobs from every company on Workday (myworkdayjobs.com), searched live |
| [Deel Jobs Scraper](https://apify.com/anshumanatrey/deel-jobs-search) | Jobs from every company on Deel ATS (jobs.deel.com), with pay |
| [Greenhouse Jobs Scraper](https://apify.com/anshumanatrey/greenhouse-jobs-search) | Jobs from every company on Greenhouse (boards.greenhouse.io), searched live |
| [SmartRecruiters Jobs Scraper](https://apify.com/anshumanatrey/smartrecruiters-jobs-search) | Jobs from 2,900+ companies on SmartRecruiters, searched live |
| [Workable Jobs Scraper](https://apify.com/anshumanatrey/workable-job-search) | Jobs from every company on Workable, in one search |
| [Lever Jobs Scraper](https://apify.com/anshumanatrey/lever-jobs-search) | Jobs from 2,300+ companies on Lever (jobs.lever.co), searched live |

## Documentation

- Apify Store: https://apify.com/anshumanatrey/cornerstone-jobs-search
- GitHub repo: https://github.com/AnshumanAtrey/cornerstone-jobs-search (MIT license, see [LICENSE](LICENSE))
- The engine behind it: https://github.com/AnshumanAtrey/ats-jobs-engine

## Last updated

2026-11-03 (version 1.0)
