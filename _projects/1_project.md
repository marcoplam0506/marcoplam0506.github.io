---
layout: page
title: NYC Events Market Analysis
description: Three years of NYC permit data to map seasonality, geographic concentration, and category shifts across all five boroughs.
img: assets/img/7.jpg
importance: 1
category: work
related_publications: false
---

## The question

New York City issues tens of thousands of permits every year — for film shoots, parades, sports events, street fairs, block parties. Together they form a public footprint of where and when the city's events economy actually happens. **Which boroughs are growing? Which categories are shifting? Where is the seasonality, and where is it changing?**

This project pulls three combined datasets to answer those questions in a way that's useful to anyone making operating, marketing, or venue decisions in NYC's events space — including the small humanoid-robot rental business that sparked my curiosity.

## The data

- **NYC Permitted Event Information** (Socrata `tvpp-9vvx`) — ~41,000 rows, a rolling 1–2 month forward-looking snapshot of every permitted event in the city.
- **NYC Film Permits** (Socrata `tg4x-b46p`) — ~17,000 rows, a true 3-year history (Jan 2023 – Feb 2026). This is the dataset that makes year-over-year analysis possible.
- **US Census ZIP-level demographics** for the ~178 NYC ZIP codes, joined on event location for geographic context.

## Approach

I treat this as a Data Analyst case study, not a tutorial:

1. **Profile each dataset honestly.** The Permitted Events file looks historical but is overwhelmingly forward-looking; year-over-year work has to lean on the Film Permits history instead. Findings like this go in the writeup, not in a footnote.
2. **Reduce 100+ raw permit subcategories to ~10 business-meaningful buckets** so charts and conclusions stay readable.
3. **Test specific hypotheses** rather than producing exploratory dashboards in search of a finding.
4. **Caveat aggressively.** 2023 film numbers are depressed by the WGA/SAG strikes; the snapshot file doesn't actually tell us anything about history; small ZIPs are noisy.

## Hypotheses

**H1 — Geographic concentration:** Manhattan dominates permit issuance today (~35% of the snapshot). Has Brooklyn's share grown in the 3-year Film Permits history?

**H2 — Seasonality:** A Q4 dip is expected; the question is whether the dip has gotten deeper or shallower over the strike-adjusted 3-year window.

**H3 — Category mix:** Which subcategories are growing, which are shrinking, and where does that put the addressable market for event-adjacent services?

## Tech stack

`pandas` · `numpy` · `seaborn` / `matplotlib` · `scipy.stats` · `geopandas` for ZIP-level joins · `Jupyter` for analysis and writeup.

## Repository

Full code and writeup at [github.com/marcoplam0506/nyc-events-analysis](https://github.com/marcoplam0506/nyc-events-analysis). *Work in progress — updated as phases complete.*
