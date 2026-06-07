[Cars Scraper](https://apify.com/voyn/cars-scraper?fpr=data)

#### Cars.com Scraper

Easily extract car listings from [Cars.com](https://cars.com) into structured datasets.

This **Cars.com Scraper** lets you automatically collect vehicle data with all available details.

Simply open [Cars.com](https://cars.com), apply any filters (make, model, year, price, mileage, seller type, etc.), copy the search URL, and paste it into the scraper — results are ready in minutes.

Note: It supports both Cars.com search URLs and individual Cars.com vehicle URLs now. Example:
[https://www.cars.com/vehicledetail/910d58bd-f609-4cbe-8a53-72384e9c6242/](https://www.cars.com/vehicledetail/910d58bd-f609-4cbe-8a53-72384e9c6242/)
[https://www.cars.com/shopping/results/?deal_ratings[]=great&dealer_id=&keyword=&list_price_max=&list_price_min=&makes[]=&maximum_distance=all&mileage_max=&page_size=20&sort=listed_at_desc&stock_type=used&year_max=&year_min=&zip=](https://www.cars.com/shopping/results/?deal_ratings%5B%5D=great&dealer_id=&keyword=&list_price_max=&list_price_min=&makes%5B%5D=&maximum_distance=all&mileage_max=&page_size=20&sort=listed_at_desc&stock_type=used&year_max=&year_min=&zip=)

#### Who Is This For?

- **Car dealers & flippers** → Find undervalued cars before competitors.
- **Market analysts** → Track pricing trends by region, make, and model.
- **Competitor research** → Monitor dealer stock and pricing strategies.
- **Data scientists** → Build car valuation models with clean structured data.

#### Scraped Car Data Will Include:

- Ad Link
- Title of Ad Page
- Full Description
- Year
- Make
- Model
- Trim
- Price
- Mileage
- Average Price (if provided)
- Profit Estimate (if available)
- Profit Estimate Percentage (if available)
- Body Type
- Fuel Type
- Doors
- Cylinders
- Drive-train
- VIN
- Color (Interior / Exterior)
- Transmission
- Engine
- Stock Number
- Features & Options
- Images

#### Output Formats

You can download your results in:

- **CSV / Excel** → for quick analysis
- **JSON / NDJSON** → for developers
- **API** → integrate into Google Sheets, Zapier, Make.com, or BI dashboards

## Sample Data

The scraper returns an array of car data objects. Example:

```
{
  "list_url": [
    "https://www.cars.com/shopping/results/?deal_ratings[]=great&dealer_id=&keyword=&list_price_max=&list_price_min=&makes[]=&maximum_distance=all&mileage_max=&page_size=20&sort=listed_at_desc&stock_type=used&year_max=&year_min=&zip="
  ],
  "record_url": "https://www.cars.com/vehicledetail/910d58bd-f609-4cbe-8a53-72384e9c6242/",
  "name": "2015 Hyundai Sonata Limited",
  "description": "",
  "mileage": "116883",
  "price": "12995",
  "make": "Hyundai",
  "model": "Sonata",
  "trim": "Limited",
  "type": "Used",
  "year": "2015",
  "vin": "5NPE34AF1FH195268",
  "body": "Sedan",
  "cylinders": "4",
  "doors": "4",
  "drivetrain": "Front-wheel Drive",
  "exterior_color": "BLUE",
  "interior_color": "Gray",
  "fuel": "Gasoline",
  "transmission": "6-SPEED A/T",
  "features": [
    "Backup Camera",
    "Blind Spot Monitor",
    "Bluetooth",
    "Brake Assist",
    "Stability Control",
    "Leather Seats",
    "Heated Seats",
    "Heated Steering Wheel",
    "HomeLink",
    "Keyless Start",
    "Lane Departure Warning",
    "Navigation System",
    "Sunroof/Moonroof",
    "Premium Sound System",
    "Rear Cross Traffic Alert",
    "USB Port"
  ],
  "stock_number": "1069",
  "engine": "der Engine",
  "images": [
    null,
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/zeKVAitzIclgVX5di4pZSLpRnnE.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/vvUqPE8oy3IyP8MDMkvdbP5b3wg.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/meN6OGaQBIEuM9c1uXPCAiJrgwY.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/iwzKnIDlPUTZB795dFurgS3Ek8o.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/hIWrCqWPSutncjr_qcbcwePtwzc.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/GeEfrBgrZj0AivFy2-SkLHlxbwY.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/e7Z_uBH89eZgrSqWIvre1C-c6es.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/Y3b8jcctw-bCZSnYcgwm2HDUcAw.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/i80LJgGgYp5tK6LV6WrzmxwGc3o.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/dKCWLOCZ1zN0BGc_o7qkigfym6k.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/5Z1J2FidAPk6Fm4Ef5AiIV3nA8Y.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/9yXl3EyBBgwVaKcRfxBqvusQmbM.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/Qo2-PksPNe4kvqHD5e-Es3hz9gc.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/upS7UxLO09tGH-T9ddSBVBbrlW8.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/Phe1XGKb4YEw4EPcztE34y2Ye_0.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/CJfU2N808gN1hNTvWEYdS6im1ZM.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/MDofEyb_Wzp8g8pgrVQsny7-OaA.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/kTAMR2b4RqeDps7YdJEmQR4A6k4.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/_PLMB89RNXkPDbSOv5BgGybmTl0.jpg",
    "https://platform.cstatic-images.com/xlarge/in/v2/b25160d0-b562-4cca-a2c8-1e7c94dd7dd6/82918e26-6c50-4cdf-86f9-fd5670041a19/G5XKWrsq5AHKmMmtvNIV9sBhHSY.jpg"
  ],
  "profit_estimate": 605,
  "average_price": 13600,
  "profit_estimate_percentage": 4.655636783378222
}
```