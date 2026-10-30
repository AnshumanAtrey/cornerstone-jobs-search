# Cornerstone Jobs Scraper & API - All CSOD Career Sites, Remote

Cornerstone jobs scraper and API: search every company's career site on Cornerstone OnDemand (csod.com) at once, live, and get each job's title, company, location, remote flag, posting date, closing date and link, newest first. Turn on full details for the description, the exact posting time, the address and the apply link.

Use it as a CSOD jobs API, a Cornerstone career site scraper or a daily job feed from the Apify Console, the Apify API, Python, JavaScript, n8n, Make or an AI agent, and export JSON, CSV or Excel. It is the `site:csod.com` Google dork done at the source, and it reaches jobs the dork cannot: nearly half of these jobs sit on career sites closed to search engines. Available as an [Apify Actor](https://apify.com/anshumanatrey/cornerstone-jobs-search). $0.002 per job, $0.003 with full details, no start fee, no login, no API key.

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

Pay per event. Platform usage is included, and there is no start fee or monthly fee.

| Event | Price | When it is charged |
|---|---|---|
| Job | $0.002 | One saved job, and one checked link that is closed or not found |
| Job with details | $0.003 | One saved job with full details on |

On paid Apify plans these are 10% less on Scale ($0.0018 and $0.0027) and 20% less on Business and above ($0.0016 and $0.0024).

| Job (Free and Starter price) | Cost |
|---|---|
| 100 newest jobs | $0.20 |
| 100 jobs with full details | $0.30 |
| 1,000 jobs | $2.00 |
| 10,000 jobs with full details | $30.00 |

Apify's free $5 monthly credit covers about 2,500 jobs. Number of jobs (`maxJobs`) sets the most a run can cost, and a run stops at its spending limit with a message saying so.

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

Nothing is required. Type a job title and press Start, or press Start with the form empty.

| Field | What it does |
|---|---|
| Job titles to find (`searchTerms`) | One per line. A job matches when its title has every word: frontend also finds Front-End. A pasted Google dork or Cornerstone link works too |
| Where the job is (`location`) | A city, state, country or region: London, United States, EMEA, LatAm. Worldwide finds jobs open everywhere, and Remote asks for remote jobs |
| Remote or onsite (`workType`) | remote, hybrid or onsite. Cornerstone has no remote field, so this reads the title and location |
| Posted in the last (`postedWithin`) | 24 hours, 3 days, 7 days, 30 days, any time, or your own period such as 48 hours |
| Number of jobs (`maxJobs`) | How many, newest first: 100 by default, 0 for every match |
| Full details (`includeDetails`) | Adds the description as text and HTML, exact posting time, reference, apply link, city, region and country |
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

One row per job, newest first. These rows are from a run on 2026-10-30, build 1.0.1, searching one company for the word engineer in 1 second:

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

Full details add `description`, `descriptionHtml`, `reference`, `city`, `region`, `country` and `countryCode`, and replace the posting date with the exact time. A run also writes an `OUTPUT` record: how many career sites were read, how many jobs matched and were saved, and any notes on how your input was read.

## How fast is it?

Every career site in 69 seconds at the default 2 GB of memory (run b24SuuFL58CMyduIh, 2026-10-30, 100 newest jobs). A search of named companies takes seconds, and details add a moment per job.

## Common questions

### Why are these jobs not on Google?

Each company's Cornerstone career site has a setting for search engines. Where it is off, the job pages carry `noindex` and no job markup, so Google leaves them out. On 2026-10-30 that was 259 of 840 hiring sites and 47% of open jobs.

### How does it find every company?

The Wayback Machine lists every archived page under csod.com, which gave 1,754 career sites; 1,110 still answer. That is the `site:csod.com` idea run on an archive instead of a search engine. To search a company that is not on the list, paste its career-site link into Only these companies.

### Does it need a login or an API key?

No. It reads what each career site shows any visitor, with the anonymous access the page itself uses. You need only an Apify account.

### How do I run it from Python or an AI agent?

Through the Apify API, with your Apify token:

```python
from apify_client import ApifyClient

client = ApifyClient("<YOUR_APIFY_TOKEN>")
run = client.actor("anshumanatrey/cornerstone-jobs-search").call(run_input={"searchTerms": ["software engineer"]})
for row in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(row["title"], row["company"], row["location"], row["jobUrl"])
```

AI agents can call it through the Apify MCP server at https://mcp.apify.com, and n8n and Make have Apify nodes.

### Am I charged for closed jobs?

A search returns open jobs only. A pasted link that turns out closed or not found is one Job row, because it was checked and answered.

### Is it legal to use?

It reads public job postings. You are responsible for how you use the data, including each site's terms and the privacy laws that apply to you.

## Limitations

- Cornerstone publishes no salary, job type, department or remote field, so none is shown. Remote and hybrid are read from the title and location only.
- Titles and descriptions come in the company's own language.
- Company names: Cornerstone publishes only the name in the address, so the big employers are written by hand and the rest are read from that name.
- The list of career sites was built on 2026-10-30. A company that joined later is searched only when you name it.
- Some postings are years old: a company may leave a job open for a long time, and it comes back as open because Cornerstone lists it.

## Who maintains it?

Built and maintained by **Anshuman Atrey** ([@AnshumanAtrey](https://github.com/AnshumanAtrey)), who publishes a portfolio of data and OSINT actors on Apify Store. For a feature request or a bug, message [LinkedIn](https://linkedin.com/in/anshumanatrey) (fastest), open an issue on the GitHub repo, or write through [atrey.dev](https://atrey.dev).

## Sibling actors

| Actor | Use case |
|---|---|
| [ashby-jobs-search](https://apify.com/anshumanatrey/ashby-jobs-search) | Every job on every Ashby board, searched live |
| [linkedin-harvester](https://apify.com/anshumanatrey/linkedin-harvester) | Email to LinkedIn profile, for the people behind a company |
| [theharvester-osint](https://apify.com/anshumanatrey/theharvester-osint) | Domain to emails and subdomains |

## Documentation

- Apify Store: https://apify.com/anshumanatrey/cornerstone-jobs-search
- GitHub repo: https://github.com/AnshumanAtrey/cornerstone-jobs-search (MIT license, see [LICENSE](LICENSE))
- The engine behind it: https://github.com/AnshumanAtrey/ats-jobs-engine

## Last updated

2026-10-30 (version 1.0)
