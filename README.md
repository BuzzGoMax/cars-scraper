[Cars Scraper](https://apify.com/sovereigntaylor/cars-scraper?fpr=data)

# Cars.com Vehicle Listings Scraper

Scrape Cars.com for new and used vehicle listings across the entire US market. Extract comprehensive vehicle data including pricing, full specifications, dealer information, photos, CARFAX links, price history, and feature lists.

## What does this scraper do?

This actor searches Cars.com and extracts detailed vehicle listing data. It supports all Cars.com search filters including make, model, year range, price range, mileage, body type, fuel type, and location-based search with configurable radius.

**Perfect for:**

- **Automotive dealers** — Monitor competitor pricing, track market trends, source inventory
- **Fleet managers** — Find vehicles matching fleet specifications across multiple markets
- **Market researchers** — Analyze pricing trends by make/model/year/location
- **Car buyers** — Compare deals across dealerships within your area
- **Data analysts** — Build automotive market datasets for pricing models and trend analysis
- **Insurance companies** — Vehicle valuation and market value assessment

## Key features

- Search by make, model, year, price, mileage, body type, fuel type, and location
- Location-based search with configurable radius (10-500 miles)
- Full vehicle specifications extraction (engine, transmission, drivetrain, colors, VIN)
- Dealer information with ratings and contact details
- All vehicle photos extracted
- CARFAX report links when available
- Price analysis badges (Great Deal, Good Deal, Fair Price, etc.)
- Price history tracking
- Feature list extraction (safety, comfort, technology packages)
- Automatic pagination — scrape hundreds or thousands of listings
- Deduplication by VIN, URL, and title+price fingerprint
- Pay-per-event pricing — only pay for vehicles actually scraped

## Output data

Each scraped vehicle includes:

| Field | Description |
| --- | --- |
| `title` | Full listing title (e.g., "2021 Toyota Camry SE") |
| `price` | Listing price in USD |
| `year` | Model year |
| `make` | Manufacturer (Toyota, Ford, BMW, etc.) |
| `model` | Model name (Camry, F-150, 3 Series, etc.) |
| `trim` | Trim level (SE, XLT, Sport, etc.) |
| `mileage` | Odometer reading in miles |
| `exteriorColor` | Exterior color |
| `interiorColor` | Interior color |
| `fuelType` | Fuel type (Gasoline, Diesel, Electric, Hybrid) |
| `transmission` | Transmission type |
| `drivetrain` | Drive configuration (FWD, RWD, AWD, 4WD) |
| `engine` | Engine description |
| `vin` | Vehicle Identification Number (17-character) |
| `dealer` | Dealer name |
| `dealerRating` | Dealer rating (1-5 stars) |
| `dealerPhone` | Dealer phone number |
| `dealerAddress` | Dealer physical address |
| `priceAnalysis` | Price analysis badge (Great Deal, Fair Price, etc.) |
| `images` | Array of all vehicle photo URLs |
| `features` | Array of vehicle features and packages |
| `carfaxUrl` | Link to CARFAX vehicle history report |
| `priceHistory` | Array of historical price changes |
| `url` | Direct link to the listing on Cars.com |
| `description` | Seller notes / vehicle description |

## Example output

```
{
    "title": "2022 Toyota Camry SE",
    "price": 24995,
    "priceFormatted": "$24,995",
    "year": 2022,
    "make": "Toyota",
    "model": "Camry",
    "trim": "SE",
    "mileage": 32456,
    "mileageFormatted": "32,456 mi",
    "exteriorColor": "Midnight Black Metallic",
    "interiorColor": "Black",
    "fuelType": "Gasoline",
    "transmission": "8-Speed Automatic",
    "drivetrain": "FWD",
    "engine": "2.5L 4-Cylinder",
    "vin": "4T1G11AK5NU123456",
    "dealer": "AutoNation Toyota",
    "dealerRating": 4.7,
    "dealerPhone": "(555) 123-4567",
    "dealerAddress": "1234 Auto Mall Dr, Los Angeles, CA 90001",
    "priceAnalysis": "Good Deal",
    "images": [
        "https://images.cars.com/cldstatic/wp-content/uploads/example1.jpg",
        "https://images.cars.com/cldstatic/wp-content/uploads/example2.jpg"
    ],
    "features": [
        "Apple CarPlay",
        "Android Auto",
        "Blind Spot Monitor",
        "Lane Departure Warning",
        "Adaptive Cruise Control",
        "Keyless Entry",
        "Backup Camera"
    ],
    "carfaxUrl": "https://www.carfax.com/VehicleHistory/ar20/...",
    "priceHistory": [
        { "date": "2024-01-15", "price": 26495, "priceFormatted": "$26,495" },
        { "date": "2024-02-01", "price": 24995, "priceFormatted": "$24,995" }
    ],
    "url": "https://www.cars.com/vehicledetail/detail/123456789/overview/",
    "description": "One owner, no accidents, clean title. Full service history available.",
    "source": "cars.com",
    "scrapedAt": "2026-03-01T12:00:00.000Z"
}
```

## Input configuration

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `make` | string | `""` | Vehicle manufacturer (e.g., `toyota`, `ford`, `bmw`) |
| `model` | string | `""` | Vehicle model (e.g., `camry`, `f-150`, `3_series`) |
| `yearMin` | integer | `0` | Minimum model year |
| `yearMax` | integer | `0` | Maximum model year |
| `priceMin` | integer | `0` | Minimum price in USD |
| `priceMax` | integer | `0` | Maximum price in USD |
| `mileageMax` | integer | `0` | Maximum mileage |
| `zipCode` | string | `""` | US zip code for location search |
| `radius` | integer | `50` | Search radius in miles |
| `bodyType` | enum | `""` | Body style filter (sedan, suv, truck, coupe, convertible, van, wagon, hatchback) |
| `fuelType` | enum | `""` | Fuel type filter (gasoline, diesel, electric, hybrid, plug_in_hybrid, flex_fuel, hydrogen) |
| `maxResults` | integer | `500` | Maximum vehicles to scrape (0 = unlimited) |
| `proxy` | object |  | Apify proxy configuration |

## Example input

### Search for Toyota Camry near Los Angeles

```
{
    "make": "toyota",
    "model": "camry",
    "yearMin": 2020,
    "yearMax": 2024,
    "priceMax": 35000,
    "zipCode": "90210",
    "radius": 50,
    "maxResults": 100
}
```

### Search for electric SUVs nationwide

```
{
    "make": "",
    "model": "",
    "bodyType": "suv",
    "fuelType": "electric",
    "yearMin": 2022,
    "maxResults": 500
}
```

### Search for trucks under $30K with low mileage

```
{
    "make": "",
    "model": "",
    "bodyType": "truck",
    "priceMax": 30000,
    "mileageMax": 50000,
    "zipCode": "75001",
    "radius": 100,
    "maxResults": 200
}
```

## Extraction strategies

The scraper uses four extraction strategies in priority order:

1. **Search results cards** — Parses vehicle-card elements from Cars.com listing pages. Extracts title, price, mileage, dealer, image, and basic specs.
2. **Vehicle detail pages** — Visits each listing's detail page for the full dataset: complete specs table, all photos, dealer contact info, price history, CARFAX link, and feature list.
3. **JSON-LD structured data** — Extracts schema.org Vehicle/Car data embedded in page headers. Provides standardized vehicle attributes as a fallback.
4. **Dealer inventory pages** — Handles dealer-specific inventory page layouts that differ from standard search results.

## Pricing

This actor uses pay-per-event pricing at **$0.006 per vehicle scraped**. You only pay for vehicles that are actually extracted and saved to the dataset. Failed requests, duplicates, and filtered-out results are not charged.

## Tips for best results

- **Make and model names**: Use lowercase with hyphens for multi-word names (e.g., `f-150`, `model_3`, `grand_cherokee`). Check Cars.com URLs for the exact format.
- **Location search**: Providing a zip code significantly improves result relevance. Use radius 0 for nationwide search.
- **Proxies**: Datacenter proxies work well for moderate volumes. Switch to residential proxies for 1000+ vehicles or if you encounter blocks.
- **Large datasets**: For scraping 5000+ vehicles, consider running multiple actors with different make/model combinations to parallelize the work.
- **Rate limiting**: The scraper automatically manages request rates. If you encounter blocks, reduce the `maxResults` or enable Apify proxy.

## Limitations

- Cars.com is a US-focused marketplace. International listings are not available.
- Some dealer listings may have limited data if the dealer has not filled in all fields.
- Price history is only available when Cars.com tracks price changes (not all listings).
- CARFAX links require a separate CARFAX subscription to view full reports.
- Very new listings may not yet have price analysis badges.

## Integration — Python

```
from apify_client import ApifyClient

client = ApifyClient("YOUR_API_TOKEN")
run = client.actor("sovereigntaylor/cars-scraper").call(run_input={
    "searchTerm": "cars",
    "maxResults": 50
})

for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(f"{item.get('title', item.get('name', 'N/A'))}")
```

## Integration — JavaScript

```
import { ApifyClient } from 'apify-client';
const client = new ApifyClient({ token: 'YOUR_API_TOKEN' });

const run = await client.actor('sovereigntaylor/cars-scraper').call({
    searchTerm: 'cars',
    maxResults: 50
});

const { items } = await client.dataset(run.defaultDatasetId).listItems();
items.forEach(item => console.log(item.title || item.name || 'N/A'));
```