# B-Side Feedback Fit — 23andMe and LinkedIn Case Studies

## 23andMe: Private Data + B2B Pharma Monetization

### Timeline
- 2006: Founded by Anne Wojcicki; consumer DNA testing
- 2018: GSK invests $300M for equity stake + 4-year exclusive drug discovery collaboration
  - Source: CNBC July 25, 2018; GSK press release; Fortune
  - Deal terms: equal split of IP/funding; 5M 23andMe customers (80% opted into research)
  - Extension 2023: GSK paid $50M to extend 1 more year
- Peak users: ~15M customers (2024 bankruptcy filings cite "15M customers")
  - Some earlier sources cite "14M" (pre-bankruptcy growth)
- Oct 2023: Data breach — 6.9 million user records exposed (credential stuffing)
  - Led directly to trust collapse and revenue decline
- Nov 2024: 23andMe shuts down therapeutics division entirely
- Mar 23, 2025: Chapter 11 bankruptcy filed in Delaware
- Auction outcome: TTAM Research Institute (Anne Wojcicki's nonprofit) wins at $305M
  - Court approved sale July 14, 2025
- Congressional investigation: April 2025, bipartisan coalition of 28 AGs argued against data transfer without renewed opt-in consent

### The B2B Model
- ~80% of 23andMe users opted into research program (de-identified data sharing)
- GSK used this for drug target discovery: 40+ therapeutic programs in 4 years
- Clinical advancement: CD96 antibody for immuno-oncology
- The B2B value was REAL: GSK paid $350M total ($300M equity + $50M extension) for access
- BUT: therapeutics pipeline required additional billions to realize → company ran out of runway

### What the Bankruptcy Reveals
- User opt-in (80%) does NOT protect company if business model fails
- Data as "asset" in bankruptcy = users' genetic data treated as property → privacy violation in spirit
- The consent obtained was for "research" not "sale of company assets" → legal gray zone
- Harvard Gazette analysis: "What happens to your genetic data if 23andMe collapses?" (Mar 2025)
- HKS analysis: "23andMe's bankruptcy raises concerns about privacy in the era of big data"
- NIH/PMC analysis (2025): "The precarious future of consumer genetic privacy"

### User Perception
- Pre-breach (2018–2022): broadly positive; B2B deal with GSK NOT widely known to consumers
- Post-breach (2023–2025): trust collapse; 40% of users deleted accounts
- Bankruptcy (2025): panic; Axios guide on how to delete data published same day as filing
- Key lesson: opaque B2B monetization of sensitive private data + corporate failure = worst-case scenario

### Regulators
- PIPEDA (Canada) + UK ICO: joint investigation into data breach, findings 2025
- Washington My Health My Data Act (eff. March 2024): requires opt-in for health data
- 28 AGs coalition: demanded courts block data sale without renewed user consent

---

## LinkedIn: Public Data + Recruiter B2B

### Timeline
- 2003: Founded; professional network
- 2011: IPO; Hiring Solutions already = 50% of revenue ($84.9M in Q4 2011)
- 2016: Acquired by Microsoft for $26.2B
- 2024: $17.1B total revenue; Talent Solutions = 60%+ = ~$10B

### The B2B Model
- User creates public profile → LinkedIn indexes and surfaces to recruiters
- LinkedIn Recruiter: $8K–$100K+/year subscription for employers; full access to profile database
- LinkedIn Sales Navigator: similar model for sales intelligence
- User gets free platform access; employer pays for search/outreach capability
- Salary Insights: user-submitted private salary data → aggregated → sold back to recruiters as market data

### User Perception
- Generally accepted: users understand LinkedIn is "for professional visibility"
- The implicit trade is known: "I want to be found by recruiters"
- However: 2024 backlash when LinkedIn updated TOS to use posts for AI model training
  - Users did not consent to AI training use; perceived as overreach
  - LinkedIn backtracked: offered opt-out for AI training
- Lesson: even accepted B2B monetization hits resistance when expanded to new data uses

### Comparison to 23andMe

| Factor | 23andMe | LinkedIn |
|---|---|---|
| Data sensitivity | Very high (genetic) | Medium (career history) |
| User awareness of B2B use | LOW (opaque) | MEDIUM (implicit in platform purpose) |
| User opt-in | 80% research opt-in | Implicit via public profile creation |
| B2B buyer | Pharma (GSK) | Employers, recruiters |
| Revenue from B2B | $350M over 5yr (GSK deal) | ~$10B/year ongoing |
| Failure mode | Business collapse → data sale | AI training backlash (partial) |
| Regulatory risk | HIGH (genetic privacy laws) | MEDIUM (professional data norms) |
| User recourse | Delete account (data persists in research) | Delete account (data removed from Recruiter) |

### Key Insight for Our Product
1. Sensitivity matters most: career/work data (LinkedIn) is FAR more acceptable for B2B monetization than genetic/health data (23andMe)
2. Transparency helps but is not sufficient: LinkedIn's 2024 AI training backlash shows even "public" data use requires explicit disclosure when repurposed
3. Corporate risk: if company fails, private data becomes contested asset. LinkedIn's Microsoft backing provides structural safety that 23andMe lacked.
4. The 23andMe model (private data → secret B2B deal) is HIGH risk. The LinkedIn model (public data → openly labeled B2B product) is LOW risk.

## Sources
- cnbc.com/2018/07/24/glaxosmithkline-23andme-team-up-on-genetics-driven-drug-research (GSK $300M)
- genomeweb.com/cancer/23andme-gets-50m-payment-gsk-extends (GSK $50M extension)
- fiercehealthcare.com/regulatory/23andme-bankruptcy-sparks-genetic-data-privacy-concerns-its-15m-customers
- elevenflo.com/blog/23andme-chapter-11-deep-dive (bankruptcy detail: $305M sale)
- news.harvard.edu/gazette/story/2025/03 (Harvard Gazette analysis)
- hks.harvard.edu/centers/mrcbg/programs/growthpolicy/23andmes-bankruptcy-raises-concerns (HKS)
- axios.com/2025/03/24/23andme-bankruptcy-what-does-that-mean-data
- sec.gov Form 8-K LinkedIn FY2011, FY2012
- techcrunch.com/2025/01/29 (LinkedIn $2B premium revenue)
- iapp.org/news/a/us-officials-question-23andmes-ability-to-navigate-data-protection-during-bankruptcy
