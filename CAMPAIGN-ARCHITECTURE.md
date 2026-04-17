# Proven. — Campaign Architecture
**Generated:** 2026-04-17

## Naming Convention
```
[PLATFORM]_[OBJECTIVE]_[AUDIENCE]_[GEO]_[YYYYQQ]
```
Examples:
- `META_CONV_ASC-Broad_US_2026Q2`
- `GOOG_SEARCH_Brand_US_2026Q2`
- `TIKTOK_CONV_SmartPlus_US_2026Q2`

---

## META ADS

```
Meta Account (Proven.)
│
├── META_CONV_ASC-Broad_US_2026Q2          [Advantage+ Sales Campaign — PRIMARY]
│   └── ASC Ad Set (Broad, algorithmic)
│       ├── Creative Set A: Gummy Upgrade (BAB format)         [Video 15s]
│       ├── Creative Set B: Ingredient Transparency (PAS)      [Carousel]
│       ├── Creative Set C: Taste Reaction UGC                 [Spark-style]
│       ├── Creative Set D: Clean vs. Dirty Supplement         [Static]
│       └── Creative Set E: Recovery Self-Respect              [Video 30s]
│           NOTE: Load 5+ diverse creatives; Andromeda penalizes
│           similarity score >60% across creatives.
│
├── META_CONV_Interest-CBO_US_2026Q2       [Manual CBO — TESTING]
│   ├── Ad Set 1: Fitness & Gym (Interest)
│   │   └── Ages 22–40 | Gym, Fitness, Workout, Weight Training
│   ├── Ad Set 2: Sports Nutrition (Interest)
│   │   └── Ages 22–40 | Protein Supplements, Pre-workout, Sports Nutrition
│   └── Ad Set 3: Clean Living (Interest)
│       └── Ages 25–40 | Organic food, Clean eating, Whole30, Biohacking
│
├── META_CONV_Retargeting_US_2026Q2        [Retargeting — ALWAYS ON]
│   ├── Ad Set 1: Website Visitors 7d (exclude purchasers)
│   │   └── Creative: PAS urgency angle, offer-led
│   ├── Ad Set 2: Website Visitors 8–30d (exclude purchasers)
│   │   └── Creative: Ingredient proof / social proof carousel
│   ├── Ad Set 3: Cart Abandoners 7d
│   │   └── Creative: Direct offer + testimonial, strong CTA
│   ├── Ad Set 4: Video Viewers 50%+ 30d (exclude purchasers)
│   │   └── Creative: FAB — feature-benefit close
│   └── Ad Set 5: Purchasers 90d (Upsell)
│       └── Creative: Star-Story-Solution, upsell to bundle
│
└── META_CONV_LAL-Scale_US_2026Q2          [Lookalike — Month 3+]
    ├── Ad Set 1: 1% LAL from Purchasers
    └── Ad Set 2: 1–3% LAL from Purchasers
```

**Meta Budget Guardrails:**
- ASC: 70% of Meta budget (primary revenue engine)
- Manual CBO interest: 15% (testing new angles)
- Retargeting: 15% (high ROAS, protect from decay)
- Never increase a Meta budget >20% in one change (resets learning phase)

---

## GOOGLE ADS

```
Google Account (Proven.)
│
├── GOOG_SEARCH_Brand_US_2026Q2            [Brand — ALWAYS ON]
│   └── Ad Group: Brand Terms
│       ├── KWs: [proven supplements], [proven performance], [tryprovenperformance]
│       └── RSA: Brand protection copy, sitelinks to product categories
│
├── GOOG_SEARCH_NonBrand-Purchase_US_2026Q2   [High Intent — PRIMARY]
│   ├── Ad Group 1: Pre-Workout Gummies
│   │   ├── KWs: "pre workout gummies", "gummy pre workout", "preworkout gummies"
│   │   └── RSA: Gummy format + clean ingredients angle
│   ├── Ad Group 2: Performance Supplements
│   │   ├── KWs: "best performance supplements", "clean pre workout", "science backed supplements"
│   │   └── RSA: Science-backed + taste angle
│   ├── Ad Group 3: Recovery Supplements
│   │   ├── KWs: "recovery supplement", "post workout gummies", "muscle recovery supplement"
│   │   └── RSA: Recovery + clean ingredients angle
│   └── Ad Group 4: Competitor Terms (Month 3+)
│       ├── KWs: [competitor brand] alternative, [competitor brand] vs
│       └── RSA: Comparison angle, format + taste differentiators
│
├── GOOG_PMAX_Shopping_US_2026Q2           [Performance Max — SECONDARY]
│   ├── Asset Group 1: Gummies Collection
│   │   └── Images, headlines, descriptions, product feed
│   ├── Asset Group 2: Powder Collection
│   │   └── Images, headlines, descriptions, product feed
│   └── Asset Group 3: Bundles / Starter Packs
│       └── Images, headlines, descriptions, product feed
│       NOTE: Exclude brand terms from PMax via brand exclusions.
│       Segment by product category for better optimization signals.
│
└── GOOG_DEMANDGEN_YouTube_US_2026Q2       [Demand Gen — Month 5+]
    └── Asset Group: Awareness Video
        └── 15s and 30s video creatives on YouTube + Discover + Gmail
```

**Google Bidding Progression:**
- Month 1–2: Maximize Clicks (build conversion data)
- Month 3: Switch to Maximize Conversions (once 15+ conv/month)
- Month 4+: Target ROAS (once 30+ conv/month, stable CPA data)

---

## TIKTOK ADS

```
TikTok Account (Proven.)
│
├── TIKTOK_CONV_SmartPlus_US_2026Q2        [Smart+ — PRIMARY]
│   └── Smart+ Catalog Campaign
│       └── Product feed connected, algorithmic audience
│
├── TIKTOK_CONV_InFeed-Prospecting_US_2026Q2   [In-Feed — TESTING]
│   ├── Ad Group 1: Fitness Interest (Ages 18–35)
│   │   └── Native-feel UGC video, hook in first 2 seconds
│   └── Ad Group 2: Health & Wellness Interest (Ages 22–38)
│       └── Ingredient education content, short-form
│
└── TIKTOK_REACH_SparkAds_US_2026Q2        [Spark Ads — AMPLIFY UGC]
    └── Boost top-performing organic/creator posts
        └── Select creators in gym, fitness, sports nutrition niches
        NOTE: Spark Ads show +30% completion, +142% engagement vs standard.
        Prioritize Spark over standard in-feed where possible.
```

**TikTok Creative Rules:**
- Hook in first 1–2 seconds (swipe-up environment)
- Vertical 9:16 only, no letterboxed content
- Captions always on (80%+ watch without sound)
- Native feel > polished brand ads (people detect ads and skip)
- Rotate creative every 7–10 days (high fatigue rate vs Meta)
