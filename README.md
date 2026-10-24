# GCC Ledger

**The buyer's side of the GCC market: evidence for the decision, built for the company entering India, not sold to the vendors chasing it.**

GCC Ledger is a strategy proposal and working prototype for a single source of truth on India's Global Capability Centre (GCC) ecosystem. Every number carries its source, its date, what it counts, and how sure we are.

## Live links

| What | Link |
|---|---|
| Prototype (hosted site) | https://gcc-ledger-v2.netlify.app |
| Prototype (Claude artifact) | https://claude.ai/artifact/MKq7LE3ToVydrXj2DLjpwq |
| Deck (Claude artifact) | https://claude.ai/artifact/KbQ3uToR7EKp1mpVFQ7wLk |
| Deck files | [PDF](deck/GCC-Ledger-deck-v2.pdf) · [PPTX](deck/GCC-Ledger-deck-v2.pptx) |

## The problem

India has roughly 1,700 to 2,100+ GCCs, depending on whose report you read (Zinnov–nasscom counts 2,117 companies and 3,728 units as of March 2026; the government and Vestian say about 1,700). Even the city leaderboard disagrees: Bengaluru has 487 GCCs by one count and 880+ by another.

A company setting up a GCC makes a large, rare, hard-to-reverse decision (roughly $4–5M a year for a 150-person centre, 3 to 18 months to go live) with the least neutral information. It has to assemble the truth from advisors, lawyers, auditors, brokers, recruiters, EOR and BOT firms and state governments, most of whom are paid by the outcome. So it falls back on referrals, consultant reports, broker tours and weeks of desk research. The first-time entrant is hurt most, but small capable providers, states, brokers and talent all lose to the same asymmetry.

## Who it is for first

**The India-entry lead**: a VP Strategy or Head of India Entry at a mid-size global company setting up its first GCC. Their job is to get a cited recommendation on city, operating model, cost and partners approved by the board. About 110–165 new GCCs open a year, roughly 40–60 of them mid-market (our estimate).

**Second segment**: existing GCCs opening a second city or scaling up. They come back.

## The solution

A buyer-side ledger built mostly from public data that already exists but is scattered (MCA filings, state GCC policies, press releases, leasing reports, job postings, provider case studies), joined, dated and tiered:

- **Verified**: a filing, or two independent sources agree.
- **Reported**: one credible published source.
- **Claimed**: self-reported, for example by a provider about itself.

Where sources disagree, the Ledger shows all of them and explains why, instead of picking one.

### The six modules

1. **Decision Room**: a living, cited board pack. Every figure links to its source and date, stale figures are flagged, and invited advisors can comment.
2. **Delivery receipts** (Providers & receipts): provider records with client-confirmed delivery facts, moving from Claimed to Verified, plus a confirm form.
3. **Signals**: new GCCs on a filings ladder (rumoured, entity incorporated, space approved, lease, hiring, operational) with a likelihood of going live within 12 months. Six real, linked entries and two labelled illustrative ones.
4. **Entry planner and city compare**: ranks cities, compares EOR, BOT and own-entity models, and estimates annual run-rate cost. Includes state policies and incentives.
5. **GCC directory**: the free foundation, with a source link and date on every record.
6. **Ask the Ledger**: answers only from the Ledger's own data, citing a record for every claim, and says "not in our data" otherwise.

The prototype also has an Overview tab that shows the conflicting GCC counts side by side.

## Positioning

*The only GCC data built for the buyer, not sold to the vendors chasing it.* Buyer-side (no contact lists, no lead fees, no rankings for sale), evidence-based (sources, dates and client-confirmed receipts), and living (the board pack flags a figure when its source changes). Entrants invite their lawyer, auditor and broker into the Decision Room, so other players arrive through the buyer. Rankings and evidence levels are computed, never bought.

## How to run it

No build, no server, no API keys. The prototype is a single self-contained HTML file with the seed data embedded.

- Open [`index.html`](index.html) in any modern browser, or
- open [`prototype/gcc-ledger-v2-standalone.html`](prototype/gcc-ledger-v2-standalone.html) (identical copy).

An internet connection is only used to load Google Fonts; the app works without it.

To host it, turn on **GitHub Pages** for this repo (Settings → Pages → Deploy from branch → `main` / root) and `index.html` will be served as the site.

## Repository layout

```
index.html                          Prototype, served as the site root
prototype/
  gcc-ledger-v2-standalone.html     Same prototype, standalone copy
dataset/
  gcc-ledger-data.json              Full seed dataset (what the app embeds)
  gcc-ledger-dataset.xlsx           Same data as a workbook
  gcc-ledger-dataset-csv.zip        All CSVs zipped
  csv/                              One CSV per table: gccs, gcc_counts, cities,
                                    states_policies, rents, talent_salary,
                                    providers, receipts, signals,
                                    model_parameters, sources
deck/
  GCC-Ledger-deck-v2.pdf
  GCC-Ledger-deck-v2.pptx
```

## Data sources

Every record in the dataset links to an entry in [`dataset/csv/sources.csv`](dataset/csv/sources.csv). The main ones:

- PIB / MeitY note citing nasscom (Dec 2025) and the Lok Sabha reply (Aug 2025): 1,700+ GCCs, 1.9M people, $64.6B
- Zinnov–nasscom India GCC Landscape 2026: 2,117 GCCs, 3,728 units, 2.36M people, $98.4B
- Zinnov blog (Jan 2026) and Zinnov–KDEM mid-market study (Sep 2025)
- Vestian via PTI / The Week (Jul 2025): city counts
- CRE Matrix, India office market Q1 CY26: market rents by city
- CBRE, *The Policy Advantage*, via Entrepreneur India (Aug 2026): state targets and leasing shares
- State GCC policies (Karnataka, Maharashtra, Haryana, Uttar Pradesh, Gujarat, Rajasthan, Madhya Pradesh, Andhra Pradesh, Telangana), via the policy texts and law-firm and advisory summaries (Khaitan & Co, RSM, Rödl & Partner, JLL, India Briefing and others)
- TeamLease and UnearthIQ: new GCC pace
- Company press releases and news reports for individual GCCs, signals and provider receipts

## A note on accuracy

This is a prototype on seed data (52 GCCs, 26 providers), not a complete or audited database. Some figures are **estimates**, and are labelled as such in the app: salary bands, talent pool sizes, Tier-2 rents, the cost model inputs, the signal likelihood weights (set by judgement, not trained), and the FY30 range. Two signals are labelled illustrative. Sourced figures were checked against their sources as of October 2026, but sources change, so check the linked source and its as-of date before relying on any number.
