# LinkedIn Profile Scraper (No Cookies) + Similar Profiles

Turn public LinkedIn profiles of people into clean data: name, location, followers, connections, about, current company, experience, education, websites, publications, organizations and the "similar profiles" LinkedIn shows next to each person. Paste profile URLs or just the usernames.

**[Run it on Apify](https://apify.com/pomlabs/linkedin-profile-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)**: no install, no login, free credit on a new Apify account.

## What you get

- **Who**: full name, profile photo, location and country code
- **Reach**: followers (exact count) and connections ("500+")
- **About** text, when the person made it public
- **Current company** with its LinkedIn page, plus the companies and schools LinkedIn shows on the public page, with dates when visible
- **Websites**, **publications**, **organizations** and the number of recommendations received
- **Similar profiles** (name, headline, location, followers, URL): great for building lead lists by snowball
- **Clear status per profile**: `ok`, `not_found`, `invalid_url` or `blocked`

### What the public page shows, honestly

LinkedIn shows logged-out visitors two versions of a profile. Famous and "creator" profiles show the full version: headline and every job title with dates. Most ordinary profiles show a reduced version: current company, schools, about, followers and connections, but **no job titles or headline**. This Actor returns everything the public page shows and marks it with `fullExperienceVisible` (true when job titles are visible). A full mode with every job title, dates, skills and degrees for every profile is coming soon, billed separately (see Pricing).

## Pricing

**No login, no cookies, no LinkedIn account at risk. You pay only for profiles delivered: $0.002 per profile.** Profiles that don't exist and invalid inputs are listed with the reason and never charged.

That is the free-plan price; Apify paid plans (Bronze, Silver, Gold) pay less per item.

## Call it by API

```bash
curl -X POST "https://api.apify.com/v2/acts/pomlabs~linkedin-profile-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"profiles": ["https://www.linkedin.com/in/williamhgates", "satyanadella"]}'
```

Python:

```python
from apify_client import ApifyClient

client = ApifyClient("YOUR_APIFY_TOKEN")
run = client.actor("pomlabs/linkedin-profile-scraper").call(run_input={"profiles": ["https://www.linkedin.com/in/williamhgates", "satyanadella"]})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Use it from Claude, Cursor or any MCP client

```bash
claude mcp add linkedin-profile "https://mcp.apify.com?tools=pomlabs/linkedin-profile-scraper" -t http
```

## Ready-made examples

- [Get a LinkedIn profile without cookies](https://apify.com/pomlabs/linkedin-profile-scraper/examples/linkedin-profile-without-cookies)
- [Find similar profiles to a LinkedIn profile](https://apify.com/pomlabs/linkedin-profile-scraper/examples/similar-linkedin-profiles)
- [Enrich a list of LinkedIn profile URLs](https://apify.com/pomlabs/linkedin-profile-scraper/examples/enrich-linkedin-profile-urls)

## More Actors by Pom Labs

- [YouTube Transcript Scraper: Translate, No Login · $3/1K](https://apify.com/pomlabs/youtube-transcript-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [Instagram Transcript Scraper: Reels, TikTok, Facebook, Hook](https://apify.com/pomlabs/social-video-transcript?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [Reddit Scraper: Deleted & Removed, Mods, Hidden Profiles](https://apify.com/pomlabs/reddit-posts-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [LinkedIn Company Scraper (No Cookies): Posts, Similar Companies](https://apify.com/pomlabs/linkedin-company-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [YouTube Comments Scraper + Replies, Shorts · No API Key · $1/1K](https://apify.com/pomlabs/youtube-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [Instagram Profile Scraper: Exact Followers, Reels Views](https://apify.com/pomlabs/instagram-profile-data?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [Threads Scraper: Keyword Search, Posts & Profiles · No Login](https://apify.com/pomlabs/threads-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [AliExpress Scraper: Exact Units Sold, Prices, Search · $1/1K](https://apify.com/pomlabs/aliexpress-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [AI Brand Visibility Tracker - ChatGPT, Claude & Perplexity](https://apify.com/pomlabs/ai-brand-visibility?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [Mercado Livre & Amazon BR Coupon Code Checker](https://apify.com/pomlabs/mercadolivre-coupon-checker?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [Page Time Machine · Wayback Diff + AI · No Login · $2.5/1K](https://apify.com/pomlabs/page-time-machine?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [Video Downloader: TikTok No Watermark, Instagram, YouTube, X](https://apify.com/pomlabs/video-downloader?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [NSFW Image Detector & Image Tagger - Moderation + Categories](https://apify.com/pomlabs/image-moderation-tagger?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)
- [Google Trends Scraper: Related Queries, No 429 · $2/1K](https://apify.com/pomlabs/google-trends-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper)

Full documentation, input fields and output format: [LinkedIn Profile Scraper (No Cookies) + Similar Profiles on Apify](https://apify.com/pomlabs/linkedin-profile-scraper?utm_source=github&utm_medium=readme&utm_campaign=linkedin-profile-scraper).
