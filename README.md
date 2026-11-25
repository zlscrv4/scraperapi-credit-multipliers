# Web Scraping Proxy API: ScraperAPI Plans, Credit Multipliers, and Which Plan Fits Your Targets (Full Price Table + Billing Comparison)

ScraperAPI starts at **$49 a month** for 100,000 API credits, and you can test it with **1,000 free credits a month** or a **7-day trial that gives you 5,000 credits without a card**. You pay for successful requests only, bandwidth is unmetered, and the uptime guarantee is 99.9%. The limitation that rules out more projects than price does: it cannot scrape pages behind a login.

That is the short version for anyone shopping for a web scraping proxy API. The rest of this article covers the full plan table, the credit multipliers that decide your real monthly bill, what happens inside a single request, and the jobs where a different tool is the better buy.

> **Quick pick:** start on Hobby at **$49/month** (100,000 credits, 20 concurrent threads) after burning the 5,000-credit trial on your actual URLs. A plain HTML page costs 1 credit, so 100,000 credits is 100,000 pages. Google and Bing cost 25 credits per request, which turns the same plan into 4,000 queries.
>
> 👉 [Start the free trial and check current Hobby pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## ScraperAPI plans and prices

Prices are in USD, before tax, as listed on the official pricing page at the time of writing. Annual billing is 10% lower and paid for the year upfront. The full year's credits are issued at once, so you can spend them on any schedule.

| Plan | Credits per month | Monthly price | Annual billing | Get started |
| --- | --- | --- | --- | --- |
| Free | 1,000 | $0 | n/a | [Start free](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Hobby | 100,000 | $49 | 10% off, paid yearly | [Choose Hobby](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | 1,000,000 | $149 | 10% off, paid yearly | [Choose Startup](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | 3,000,000 | $299 | 10% off, paid yearly | [Choose Business](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | 5,000,000 | $475 | 10% off, paid yearly | [Choose Scaling](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | 10,500,000 | $975 | 10% off, paid yearly | [Choose Professional](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | 21,500,000 | $1,975 | 10% off, paid yearly | [Choose Advanced](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | Quote | Quote | [Request Enterprise pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

Two details sit outside the table. The free plan caps concurrency at 5 connections and Hobby at 20. Concurrency for the higher tiers is not shown in the published pricing table, so confirm it with sales if you plan to run hundreds of parallel jobs. Also, **credits reset every billing cycle and do not roll over**. An unused balance disappears at renewal.

The per-credit price falls sharply between the first two paid plans: $0.49 per 1,000 credits on Hobby, $0.149 on Startup, then roughly $0.10 on Business and slightly less as you move up. Hobby is the cheap way to start. It is not the cheap way to scale.

## What one request actually goes through

You send a URL to the API endpoint or the proxy port. ScraperAPI picks an IP from its pool, rotates it on every request, retries failed attempts, and handles CAPTCHAs before returning the page HTML. Four parameters change what happens inside that pipeline:

- `render=true` runs the page through a headless browser, so content injected by JavaScript appears in the response.
- `session_number=123` pins a sequence of requests to the same IP, which you need for pagination, carts or any flow where the server expects continuity.
- `country_code=us` chooses the proxy country. Twelve countries are standard, including the US, UK, Germany, France, Brazil, India, Japan and Australia. Another 50 are available on request.
- `premium=true` routes the request through the residential pool instead of the standard pool.

ScraperAPI's homepage advertises **40M+ IPs** across datacenter, residential and mobile sources, with infrastructure spanning 20 ISPs. A separate residential page, which is older, describes 4M+ residential IPs and says the pool is kept at a minimum of 5M. Those are different measurements. Do not read the residential figure as the size of the total pool.

The standard pool already keeps residential IPs as backups and calls them only when a request needs one. ScraperAPI says that arrangement averages a 97% success rate and costs 75% less than routing everything through residential proxies. For ordinary product pages, articles and listings, `premium=true` is usually unnecessary. Test it on the free plan before you make it your default.

## The credit multipliers decide your real bill

A standard page costs 1 credit. The domain decides whether that stays true.

| Target | Credits per request |
| --- | --- |
| Standard HTML page | 1 |
| Amazon | 5 |
| Google or Bing, including subdomains | 25 |
| LinkedIn | 30 |
| Any page behind Cloudflare, DataDome or PerimeterX | +10 on top of the base cost |

These multipliers are public, and the dashboard includes a Domain Cost Estimator plus a `max_cost` parameter that caps a single request. Use both before you pick a plan. A 100,000-credit Hobby plan buys 100,000 plain pages, 20,000 Amazon pages, 4,000 Google results or 3,333 LinkedIn pages. A Cloudflare-protected page at 1 + 10 credits gives you about 9,090 pages on the same plan.

This is where headline credit counts stop being useful. A team that scrapes 80,000 plain pages a month fits Hobby with room to spare. A team that runs 10,000 Google queries a month needs 250,000 credits, which pushes it past Hobby and Startup into Business. Same request count, different plan.

👉 [Compare the plans against your own credit estimate](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Three providers, three different billing models

ScraperAPI charges by successful request. Proxy rotation, CAPTCHA solving, retries and bandwidth are part of that credit. Difficulty is priced through domain multipliers: Amazon 5x, Google 25x, bot-protected pages +10.

Oxylabs also bills per successful result for its Web Scraper API, but its other two products use a different meter. Web Unblocker and Agent Browser bill by traffic in GB, which means the product you choose changes the billing unit, not just the price. Oxylabs includes Custom Parser and Scheduler at no extra cost and accepts batch jobs of up to 5,000 URLs in one POST, with results kept for at least 24 hours.

Geekflare prices the proxy as a surcharge. A standard request is 1 credit. When a proxy is used, that is **4 additional credits, 5 total**. Its free plan does not include proxy routing at all. The `proxyMode: "auto"` setting tries the request directly first and only falls back to a paid proxy when the site blocks it, which is a sensible default for lists that are mostly open pages.

Shifter bundles credits and concurrency into each plan. Starter is $44 for 100,000 credits and 20 concurrent requests, but it limits you to datacenter proxies and US/EU geotargeting. Residential and mobile proxies plus all geolocations start on Growth at $134 for 1,000,000 credits and 50 concurrent requests.

The cheapest headline plan is not always the cheapest bill. ScraperAPI Hobby at $49 and Shifter Starter at $44 look close, but Shifter Starter excludes residential proxies and most countries, while ScraperAPI Hobby uses a standard pool with residential fallback. On the other side, Geekflare charges 5 credits for any proxied request, while ScraperAPI charges 1 credit for a plain page no matter which IP it rotates through. Model your target list, not the plan name.

## Where ScraperAPI stops working

Login pages are out. ScraperAPI's support note is direct: "we can't help with requests about scraping behind login pages, because Scraper API doesn't support that." If your workflow needs a logged-in session, a multi-step checkout or form fills across pages, this is the wrong category of tool.

Residential proxies are also not intended for social media automation or product purchasing bots. ScraperAPI positions them for difficult public sites that block datacenter IPs, not for account-based automation.

Proxy control is coarse by design. You choose a country, a session and an IP tier. You do not choose a specific IP, ASN or city. Teams that need that level of control usually buy raw proxies instead of a scraping API.

One more caution applies to every provider in this category: no one publishes a complete list of unreachable domains. Oxylabs, for example, documents that a small number of domains are internally blocked and reviewed case by case. Put your exact target URLs through the trial before you commit to an annual plan.

👉 [Test your target domains on the free trial](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## How it compares with Oxylabs, Geekflare and Shifter

Oxylabs is the strongest fit when you want structured data from named sources. Its Web Scraper API has dedicated parsers for Google Search, Google Ads, Google Trends, Google Lens, Google Scholar, Bing, ChatGPT, Perplexity, Amazon, Walmart, eBay, Etsy, Best Buy, Target, Costco, Alibaba, AliExpress, Lazada, Flipkart and MercadoLibre, plus a `universal` source for any public URL. It can return rendered HTML, a Base64 screenshot via `render=png`, Markdown, or structured JSON with `parse: true`. `browser_instructions` supports clicks, typing, scrolling and waits. Geotargeting goes down to state and city. Custom Parser and Scheduler are free. The trade-off is a larger product surface: Web Scraper API, Web Unblocker and Agent Browser solve different problems and bill differently.

Geekflare is the low-friction option for small jobs. Free is $0 for 500 credits and 1 request per second. Starter is $19 for 10,000 credits and 5 requests per second, Growth $69 for 100,000 credits and 25 requests per second, Business $349 for 1,000,000 credits and 50 requests per second. All prices are monthly. Its `proxyMode: "auto"` logic and `proxyCountry` parameter are easy to reason about, and the 5-credit proxied request is transparent once you know it exists.

Shifter competes on network reach and concurrency. It claims residential coverage in 195+ countries and 205M+ residential IPs, with plans from $44 to $719 a month and concurrency from 20 to 500 requests. JavaScript rendering and CAPTCHA solving are included on every tier. If you need residential IPs in dozens of countries and a hard concurrency number written into the plan, it is worth pricing next to ScraperAPI's higher tiers.

## Which plan should you buy?

Use your monthly credit burn, not your page count.

- **Under 100,000 plain pages a month, few Google or Amazon requests:** Hobby at $49. It has the worst per-credit price in the lineup, but at this volume the difference is about $100 a month, not $1,000.
- **100,000 to 1,000,000 credits with mixed targets:** Startup at $149. The per-credit price drops by about two-thirds compared with Hobby.
- **Google or Bing at volume:** calculate at 25 credits per request. 10,000 queries is 250,000 credits, which means Business at $299 or higher.
- **Amazon catalog monitoring:** 5 credits per product page. 1,000,000 credits covers 200,000 pages, so Startup is the first plan that fits a serious catalog.
- **Heavy bot protection:** add 10 credits to the base cost. A protected standard page is 11 credits, and 100,000 credits covers roughly 9,000 pages.
- **Login flows, multi-step forms, checkout testing:** none of these scraping APIs. A remote browser product is the right category. Oxylabs Agent Browser is one example, billed by GB of traffic.
- **Specific IPs, ASNs or city-level targeting:** a raw proxy provider, not a scraping API.

## FAQ

**Is the free tier enough to test properly?**
The free plan gives 1,000 credits a month and 5 concurrent connections. The 7-day trial gives 5,000 credits with no card. That is enough for 5,000 plain pages, 1,000 Amazon pages or 200 Google queries. It is a test budget, not a production budget.

**Do I pay for blocked or failed requests?**
No. ScraperAPI charges for successful requests. The catch is that unused credits do not roll over, so size the plan for a real month.

**Can I choose the country of the proxy?**
Yes, with `country_code`. Twelve countries are standard and 50 more are available on request.

**Does it return JSON?**
The plan feature list includes JSON auto-parsing. For sites without a dedicated parser, you get HTML back and extract the fields yourself.

**Can it scrape a page behind a login?**
No. ScraperAPI states that it does not support scraping behind login pages.

**What happens when credits run out?**
Lower plans can auto-upgrade to the next tier. Higher plans can use pay-as-you-go with a monthly spending cap. Without either setting, requests pause until the next billing cycle.

**Is there a refund?**
Yes, a 7-day no-questions refund. You can cancel from the dashboard at any time.

## Before you order

Two settings deserve a look before you enter a card. Check whether auto-upgrade is on, because it can move you to a higher plan mid-cycle when credits run out. And check whether annual billing suits you, since the year's credits are issued upfront and do not roll over.

The 7-day refund gives you a clean exit if your target list behaves differently at volume than it did in testing. Run the URLs that cost 5, 25 or 30 credits through the trial first. The plan that fits is the one priced on those numbers.

👉 [Start with 5,000 free trial credits, no card required](https://www.scraperapi.com/pricing/?fp_ref=coupons)
