# Phase 05 — Search Log
**Date: 2026-05-26**
**Agent: claude-sonnet-4-6**
**Total tool calls used: ~38 (within 40-55 budget)**

## Search Queries Run

### GitHub
1. "GitHub cold start 2008 Tom Preston-Werner Ruby community RailsConf first users history"
2. "GitHub 2008 launch '46000 repositories' 'first year' freemium private repos paid history milestones 1 million"
3. "GitHub RailsConf 2008 launch beta 'show HN' OR 'hacker news' early adopters freemium private repository history"
4. "GitHub 2010 1 million repositories users milestones growth open source community"

### Strava
5. "Strava cold start 2009 Mark Gainey Michael Horvath SF cycling clubs first users growth history"
6. "Strava 'first 100 users' OR 'early users' cycling clubs San Francisco 2009 2010 segments feature launch"
7. "Strava 1 million users 2012 running feature growth milestones premium subscription launch date"

### LinkedIn
8. "LinkedIn early history 2003 Reid Hoffman PayPal mafia first 100 users growth milestones"
9. "LinkedIn Sequoia Series A 2004 funding Recruiter product launch 2008 freemium model history"

### Substack
10. "Substack 2017 founding Hamish McKenzie Chris Best Bill Bishop Sinocism first writers 10% take rate"
11. "Substack 1 million paid subscribers 2021 growth milestones Matt Taibbi early writers recruited"
12. "Substack growth 2018 2019 2020 milestones 100K 500K paid subscribers YC winter 2018"

### Polywork
13. "Polywork startup failure $44.5M raised $1.45B valuation 2021 Peter Johnston sunset 2024 post-mortem"
14. "Polywork Peter Johnston founder post-mortem writeup LinkedIn alternative professional network sunset 2024 2025"

### Read.cv
15. "Read.cv Perplexity acqui-hire 2024 shutdown user reaction HN Twitter"
16. "Read.cv founding 2020 2021 Andy Chung growth community professional portfolio platform"

### Lunchclub
17. "Lunchclub AI networking startup failure 2017 2023 timeline decline"
18. "Lunchclub shutdown 2023 users what happened post-mortem founder statement decline"

### Path
19. "Path social network Dave Morin 2010 2018 failure Daum Kakao acquisition $80M lessons"
20. "Path social network failure analysis $77M raised privacy scandal growth peak users 2012 2013 decline"

### Contra
21. "Contra freelance platform startup 2020 current status active declining revenue model"
22. "Contra freelance platform Ben Huffman 2020 2021 funding Series B growth commission-free model"

## Pages Fetched

1. `https://tom.preston-werner.com/2011/03/29/ten-lessons-from-githubs-first-year.html` — FAILED (certificate error)
2. `https://research.contrary.com/company/substack` — SUCCESS: founding story, Bill Bishop, growth milestones
3. `https://promptledproduct.substack.com/p/what-happened-to-polywork-an-eye` — SUCCESS: Polywork failure analysis
4. `https://news.ycombinator.com/item?id=42742241` — SUCCESS: Read.cv HN user reactions
5. `https://www.antler.co/blog/antler-early-days-episode-1-strava-with-mark-gainey` — SUCCESS: Strava early days with Mark Gainey
6. `https://www.powerin.io/blog/history-of-linkedin` — SUCCESS: LinkedIn growth milestones
7. `https://velo.outsideonline.com/road/road-culture/strava-from-the-beginning/` — FAILED (HTTP 429)
8. `https://x.com/multiplay3r/status/1873859669065978327` — FAILED (HTTP 402 paywall)
9. `https://github.blog/2008-05-28-github-at-railsconf/` — SUCCESS: RailsConf 2008 details
10. `https://github.blog/2010-07-25-one-million-repositories/` — SUCCESS: 1M repos milestone date
11. `https://www.linkedin.com/pulse/quiet-demise-lunchclub-tells-us-something-important-how-tony-shepherd-jvane` — SUCCESS: Lunchclub decline analysis
12. `https://nira.com/github-history/` — SUCCESS: GitHub founding/freemium story
13. `https://techcrunch.com/2025/01/17/perplexity-acquires-read-cv-a-social-media-platform-for-professionals/` — SUCCESS: Read.cv acquisition details

## Data Quality Notes

### High Confidence
- GitHub: Strong sourcing from GitHub Blog primary sources + NIRA history
- LinkedIn: Confirmed milestones from official press releases (Sequoia Series A Nov 2003; Greylock Series B Oct 2004; Recruiter launch March 2008)
- Substack: Confirmed from Contrary Research + Axios + Nasdaq (1M paid subs Nov 2021)
- Read.cv: Confirmed from TechCrunch + HN thread

### Medium Confidence
- Strava 1M users date: not confirmed precisely; likely 2012–2013 after mobile + running launch
- Polywork valuation $1.45B: cited in prompt brief but not confirmed in available public sources (could be inflated rumor); $13M–$28M funding confirmed
- Peter Johnston X post content: URL returned paywall error; content reconstructed from secondary sources quoting the post

### Lower Confidence
- Lunchclub "failure": Platform is technically still live; true shutdown not confirmed; evidence is "gradual fade" not announced closure
- Contra current status: No recent news; appears to be in decline based on Trustpilot reviews and no new funding since Jan 2022
- Path acquisition price: Sources say "undisclosed"; $80M figure in brief not confirmed by any primary source found

## What Was NOT Found
- Tom Preston-Werner's "Ten Lessons" blog post (SSL certificate error on fetch)
- Peter Johnston's exact X post text (paywalled)
- Strava's exact date when 1M users was reached
- Contra's exact fee structure after commission-free reversal
- Lunchclub founder statements on decline
