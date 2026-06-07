[Cars Scraper](https://apify.com/glasswing/cars-scraper?fpr=data)

# Cars.com Scraper

Extract structured vehicle data from **Cars.com** — the #1 US automotive marketplace — using search result URLs or direct listing URLs. This Cars.com scraper returns clean, organized records grouped by vehicle, pricing, dealer, media, features and listing metadata.

**Try it free:** Paste any Cars.com search URL and run - results ready in minutes.

---

## What This Scraper Extracts

Each scraped listing returns a clean, structured record with six data groups:

### Vehicle Details

- Year, make, model, trim, body style
- Mileage, drivetrain, fuel type, transmission
- Engine specs, MPG, seating capacity
- EV-specific data (range, battery, charge type) for electric vehicles
- Condition (New / Used / Certified Pre-Owned)

### Pricing & Market Data

- Listed price and monthly payment estimate
- Price vs. market average (great deal / good deal badges)
- CARFAX history link
- Deal rating flags

### Dealer Information

- Dealer name, address, phone number
- Dealer type (franchised, independent, private seller)
- Dealer listing URL
- Private seller personal contact details are **masked** for privacy compliance

### Listing Images

- All listing photo URLs
- Exterior and interior image sets

### Features & Options

- Full equipment list: safety, comfort, tech, packages
- Structured feature categories

### Listing Metadata

- Listing ID, stock number, listing URL
- Days on market
- Stock type (New / Used / CPO)

---

## How to Use Scraper

**Step 1 - Get your URL**
Open Cars.com and apply your filters (make, model, ZIP code, price range, mileage, body style, fuel type, etc.). Copy the search URL from your browser.

**Step 2 - Paste it in**
Add up to **20 URLs** in the `startUrls` input. You can mix search result URLs.

**Step 3 - Set limits**

- `maxItemsPerLink` - how many listings to pull from each URL (default: 5, max: 10,000)
- `maxItemsTotal` - total cap across all URLs (default: 20, max: 100,000)

**Step 4 - Run**
Results appear in the Apify dataset in real time.

---

## Example Input

```
{
  "startUrls": [
    "https://www.cars.com/shopping/results/?zip=60606&maximum_distance=9999&sort=best_match_desc",
    "https://www.cars.com/vehicledetail/c1c9dff3-9eaf-4b75-b7d4-d5362fce38e1/"
  ],
  "maxItemsPerLink": 5,
  "maxItemsTotal": 20
}
```

You can also pass a single direct listing URL to extract full details for one specific vehicle.

---

## Scale Guidance

| Use Case | Recommended Setup |
| --- | --- |
| Quick market sample | 1 URL - maxItemsPerLink: 100 |
| Regional market analysis | 3-5 URLs by ZIP - maxItemsPerLink: 1,000 |
| National brand inventory | 10+ URLs by price band - maxItemsPerLink: 5,000 |

> To exceed 10,000 results in a single market, split into multiple search URLs.

---

## Use Cases

**Car dealers & flippers** - Monitor competitor inventory, track price drops, and identify undervalued vehicles using price-vs-market data and deal ratings.

**Automotive market researchers** - Build datasets across makes, models, ZIP codes, and time periods for pricing analysis, inventory studies, and trend reporting.

**Price comparison tools** - Power real-time vehicle pricing widgets and apps with structured data.

**EV market analysis** - Extract electric vehicle listings with battery range, charge type, and pricing in one structured feed - useful for EV market reports and aggregators.

**Lead generation for dealerships** - Pull dealer contact data from active listings across a region.

**Integration with n8n, Make, or Zapier** - Trigger this scraper on a schedule and pipe results directly into Google Sheets, Airtable, Supabase, or your CRM via Apify webhooks.

---

## Privacy

This actor is built with responsible data collection in mind.

- Private seller personal contact details (name, phone, email) are masked in all output records
- Dealer business contact data (name, phone, address) is retained only when publicly displayed
- No login, authentication, or account credentials are required or used
- Only publicly accessible listing pages are scraped — no private or gated content
- Data collected is intended for lawful business purposes such as market research, pricing analysis
- Users are solely responsible for how they use the extracted data in their jurisdiction

---

## FAQ

**Can I scrape a specific vehicle by its listing URL?**
Yes. Paste the direct listing URL (e.g. `https://www.cars.com/vehicledetail/...`) into `startUrls` to extract full details for that one vehicle.

**Can I scrape multiple cities or ZIP codes in one run?**
Yes. Set up one search URL per ZIP code or region and add them all to `startUrls` (up to 20). Each will be scraped independently up to its `maxItemsPerLink` limit.

**Does it work with Cars.com filter URLs?**
Yes. Apply any filters on Cars.com (make, model, year, price, mileage, body style, fuel type, etc.), copy the URL, and paste it in. The scraper respects your filters.

**How do I get more than 10,000 results from one market?**
Split your search into multiple URLs using different filter buckets - for example, price bands under $20k, $20k-$40k, over $40k - then combine the datasets.