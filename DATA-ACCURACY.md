# Data-Accuracy Checklist

Every numeric value shown on the site, mapped to the verified source value.
Location key: IM = Impact metric, FC = featured-card headline line, CS = case-study detail, MS = More Systems card.

| Value on site | Where | Verified source | Match |
|---|---|---|---|
| 48,026 | IM, FC(claims), CS(claims) | Total Salesforce claims ingested = 48,026; distinct IDs = 48,026 | ✓ |
| 0 duplicate IDs | FC(claims), CS(claims) | Duplicate claim IDs after validation = 0 | ✓ |
| 23,707 | FC(claims), CS(claims) | Warranty Repair claims modeled = 23,707 | ✓ |
| 10,499 | CS(claims) | Technically ERP-ready = 10,499 (technically ready only; not approved; ERP sending not active; human gate required) | ✓ |
| one row per claim ID | CS(claims) | Fact grain = one row per Salesforce claim ID | ✓ |
| 19M+ / 19,023,845 | IM, FC(AEM), CS(AEM) | Clean raw records = 19,023,845 | ✓ |
| 5,043,094 | CS(AEM) | Recent resolved records | ✓ |
| 12,146,658 | CS(AEM) | Historical resolved records | ✓ |
| 17,189,752 | FC(AEM), CS(AEM) | Total resolved records = 5,043,094 + 12,146,658 = 17,189,752 | ✓ |
| 0 dup keys | FC(AEM), CS(AEM) | Duplicate natural keys after resolution = 0 | ✓ |
| 2026-05-31 | CS(AEM) | Recent reporting range ends 2026-05-31 | ✓ |
| latest source-post date | CS(AEM) | Used to resolve duplicate natural keys | ✓ |
| 4.64M / 4,643,154 | IM, FC(ship), CS(ship) | Total US+CA shipment rows = 4,643,154 | ✓ |
| 4,196,616 | FC(ship), CS(ship) | US rows | ✓ |
| 446,538 | FC(ship), CS(ship) | Canadian rows | ✓ |
| ~461K / ~461,000 | IM, MS(orders) | Approximately 461,000 serialized order-unit records (approximate, shown with ~) | ✓ |
| Order → Order Item → Order Item Unit | MS(orders) | Model structure; grain = one row per Order Item Unit | ✓ |
| 4 | IM, FC(PA), CS(PA) | Total Power Automate workflows created = 4 | ✓ |
| 643 | IM label context, FC(PA), CS(PA) | Dealer master records synchronized = 643 (dealer-master flow) | ✓ |
| 0 duplicate SQL account numbers | CS(PA) | Zero duplicate SQL account numbers | ✓ |
| ~60 min → ~2 min | IM (labeled "Dealer AOR sync runtime"), FC(PA), CS(PA) | AOR row-by-row ~60 min → JSON batch ~2 min (AOR flow only) | ✓ |
| ~1 second | CS(PA) | SQL JSON processing step ~1 second | ✓ |
| ~15 minutes for 643 sequential records | CS(PA) | Dealer-master SQL→SharePoint flow (explicitly a SEPARATE flow from the 60→2 AOR sync) | ✓ |
| ~5.28 million | MS(UCC) | Approximately 5.28M current UCC FactIDs | ✓ |
| one row per registration line item/asset/serial | MS(registration) | Registration grain | ✓ |
| legacy date preferred; migration dates identified; dealer from header; asset branch retained | MS(registration) | Registration modeling rules | ✓ |

## Removed / corrected from prior versions
- REMOVED "1,164 ERP review" and "3,872 manual review" (not in the verified list).
- REMOVED "~89 prospect records" (not in the verified list).
- SEPARATED the ~60→2 min AOR sync from the ~15 min dealer-master flow (previously implied related).
- AEM resolved facts now shown as exact 17,189,752 (was rounded "17.2M").
- Serialized order units shown as "~461K" (approximate marker added).

## Not claimed anywhere (per rules)
- No cost savings, no revenue impact, no full production deployment of the AI agent or ERP sending,
  no automatic/financial approval of claims, no sole-ownership of the entire platform.
