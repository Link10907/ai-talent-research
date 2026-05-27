# Phase 3 Operations — Open Questions for Human Review

These are the questions/uncertainties I could not resolve via desk research that the
team should consider before product decisions on the Operations vertical.

## High-stakes inferences (need primary research to confirm)

1. **Will ops people actually publish?** The entire thesis depends on whether
   BizOps/CoS/RevOps practitioners would *publicly* share AI workflows / playbooks
   when given a polished venue. I have no direct data — only the negative signal
   that WizOps (9,400 members) shows no public AI positioning [P3OPS-007] and ops
   thought leaders are scarce. Recommend 10-20 user interviews before commitment.

2. **Employer IP constraint severity.** Senior ops people's most valuable AI work
   is built on proprietary frameworks and customer data. How much can they
   credibly *sanitize and publish*? If the answer is "almost nothing," the
   product fundamentally cannot work for this segment.

3. **AI-CoS / AI-BizOps title is the right wedge?** The role exists [P3OPS-004,
   P3OPS-005] but is still small (50 listings via Evan Lee, hundreds globally).
   Is this the right MVP segment, or should we target the broader "ops generalist
   wanting to upskill" market (much larger, much fuzzier)?

## Data gaps

4. **Raw JD scrape needed.** Evan Lee's 50-job roundup [P3OPS-005] doesn't publish
   full JDs. A direct LinkedIn/Greenhouse scrape of 30-50 AI-CoS / BizOps roles
   would let us build a real skill-frequency map.

5. **Cross-consulting-firm layoff data.** McKinsey's 200 cuts + 10%-by-2027 is one
   data point [P3OPS-009]. BCG, Bain, Deloitte, Accenture comparable signals would
   strengthen (or weaken) the "junior ops compression" thesis.

6. **Geographic split.** All sources US-centric. European/APAC ops norms around
   self-promotion and public writing may differ materially.

## Product-design questions

7. **Should ops have its own vertical product or live inside a multi-industry one?**
   Ops sociology (private Slack, anti-self-promotion, fragmented sub-roles) differs
   enough from designers/engineers that a dedicated UX may be warranted — but the
   smaller TAM may not support a standalone product.

8. **What's the *unit of artifact* for an ops portfolio?** Candidates: (a) an n8n /
   Zapier workflow with anonymized data, (b) a Notion AI Workflow OS template
   [P3OPS-018], (c) a "personal AI CoS" markdown KB [P3OPS-006], (d) a case-study
   write-up with before/after metrics, (e) a Loom of a working agent. We need to
   pick a hero artifact for MVP and I don't have enough user evidence to choose.

9. **How do we prevent the product from looking like a vendor-marketing site for
   Zapier/n8n/Notion templates?** If the artifact unit is "automations," the
   product risks reducing to a template marketplace rather than an identity venue.
