# Proven. — Tracking Setup Checklist
**Generated:** 2026-04-17

## Priority Order
1. Meta Pixel + CAPI (critical for primary revenue platform)
2. Google Ads Tag + Enhanced Conversions (critical for search intent capture)
3. GA4 (cross-channel source of truth)
4. TikTok Pixel + Events API (testing platform, needed for Smart+)
5. Post-Purchase Survey (fills ~30% attribution gap)

---

## META ADS TRACKING

### Client-Side (Pixel)
- [ ] Meta Pixel base code installed on ALL pages
- [ ] Standard events firing:
  - [ ] `PageView` — all pages
  - [ ] `ViewContent` — product pages
  - [ ] `AddToCart` — add to cart action
  - [ ] `InitiateCheckout` — checkout start
  - [ ] `AddPaymentInfo` — payment step
  - [ ] `Purchase` — order confirmation page (with value + currency)
- [ ] Events verified in Meta Pixel Helper browser extension

### Server-Side (CAPI) — CRITICAL
- [ ] CAPI configured via Shopify native integration or custom server
- [ ] All Pixel events mirrored via CAPI (same event names)
- [ ] `event_id` deduplication implemented (same ID sent both client + server)
- [ ] CAPI payload includes: `email` (hashed), `phone` (hashed), `fbp`, `fbc`, `external_id`
- [ ] Deduplication rate ≥ 90% in Events Manager

### Event Match Quality (EMQ) Targets
| Event | Target EMQ |
|-------|-----------|
| Purchase | 8.5+ |
| AddToCart | 6.5+ |
| PageView | 5.5+ |

**Key EMQ parameters (by impact):**
- Email SHA-256: +4.0 points
- Phone SHA-256: +3.0 points
- External ID: significant
- fbp (browser ID): important
- fbc (click ID): important

### Attribution Settings
- [ ] 7-day click / 1-day view attribution window selected
- [ ] Top 8 events configured in Aggregated Event Measurement (AEM)
- [ ] Purchase event set as Priority 1 in AEM
- [ ] Domain verified in Business Manager

---

## GOOGLE ADS TRACKING

### Client-Side
- [ ] `gtag.js` global site tag installed on ALL pages via Google Tag Manager
- [ ] Conversion actions configured:
  - [ ] Purchase (macro — set as PRIMARY for bidding)
  - [ ] AddToCart (micro — observation only, NOT primary)
  - [ ] InitiateCheckout (micro — observation only)
- [ ] Auto-tagging enabled (gclid appended to URLs)

### Enhanced Conversions
- [ ] Enhanced Conversions enabled in Google Ads account
- [ ] Hashed email sent with Purchase conversion (SHA-256)
- [ ] Hashed phone sent where available
- [ ] Verified working in Google Tag Assistant

### Attribution
- [ ] Data-Driven Attribution (DDA) selected as model (now mandatory default)
- [ ] Conversion window: 30-day click / 1-day view (for e-commerce)
- [ ] Impression-assisted conversions: track but don't optimize toward

### GA4 Integration
- [ ] GA4 property linked to Google Ads account
- [ ] GA4 Purchase event imported into Google Ads as OBSERVATION only
- [ ] Do NOT use GA4 goals as primary bidding signal (only native Google Ads conversion for bidding)

---

## TIKTOK ADS TRACKING

### Client-Side (Pixel)
- [ ] TikTok Pixel base code on ALL pages
- [ ] Standard events:
  - [ ] `ViewContent` — product pages
  - [ ] `AddToCart` — add to cart
  - [ ] `InitiateCheckout` — checkout start
  - [ ] `PlaceAnOrder` — purchase confirmation
- [ ] `ttclid` parameter captured from landing page URL on first page load
- [ ] `ttclid` stored (cookie or session) and sent with all conversion events

### Server-Side (Events API)
- [ ] TikTok Events API configured server-side
- [ ] All Pixel events mirrored via Events API
- [ ] `ttclid` passed back with all server events
- [ ] Advanced Matching enabled: hashed email + phone

---

## GOOGLE ANALYTICS 4

- [ ] GA4 property created and tracking code installed
- [ ] E-commerce enhanced tracking configured
- [ ] Purchase event fires with `transaction_id`, `value`, `currency`, `items`
- [ ] Meta, Google Ads, TikTok UTM parameters consistent across all campaigns
- [ ] UTM convention: `utm_source=meta|google|tiktok`, `utm_medium=paid`, `utm_campaign=[campaign name]`

---

## ATTRIBUTION FRAMEWORK

**Never trust platform-reported ROAS alone.** Cross-reference:

| Source | Trust Level | Use For |
|--------|-------------|---------|
| Platform-reported ROAS | Low (overclaims 20–40%) | Directional only |
| GA4 (last click) | Medium | Cross-channel patterns |
| MER (Total Revenue ÷ Total Spend) | High | Business-level efficiency |
| Post-Purchase Survey | High | Brand discovery, channel credit |
| CRM data | Highest | LTV, repeat purchase, true CAC |

**MER formula:**
```
MER = Total Monthly Revenue ÷ Total Ad Spend (all platforms)
Target: 3.0–5.0× for healthy DTC e-commerce
```

---

## POST-PURCHASE SURVEY

Install on order confirmation page:

> "Before we go — quick question: how did you first hear about Proven.?"
> - Google search
> - Instagram / Facebook ad
> - TikTok
> - Friend / word of mouth
> - Influencer / creator
> - Other

Survey tool options: KnoCommerce, Fairing, Triple Whale Surveys  
This data fills ~30% of attribution gap from iOS privacy changes.

---

## PRE-LAUNCH TRACKING CHECKLIST

Before spending a single dollar:
- [ ] Meta Pixel firing Purchase with value on test order
- [ ] CAPI receiving same Purchase event, deduplication confirmed
- [ ] EMQ for Purchase ≥ 7.0 in Events Manager
- [ ] Google Ads conversion tag firing on purchase confirmation
- [ ] Enhanced Conversions passing hashed email
- [ ] TikTok pixel firing PlaceAnOrder with value
- [ ] GA4 recording purchase with correct revenue
- [ ] All URLs tagged with UTM parameters
- [ ] Post-purchase survey installed and live
- [ ] Test order placed and verified across all platforms
