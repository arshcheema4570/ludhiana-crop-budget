# Ludhiana Crop Budget

A bilingual (English / Punjabi) offline-first crop budgeting tool for farmers in and around Ludhiana, Punjab.

The calculator estimates **cost per acre, break-even price, expected return, and margin** using crop, land, yield, price, labor, input, irrigation, and machinery assumptions. It also includes lightweight soil-health guidance, crop-rotation notes, and optional live mandi-price and weather lookups.

## Features

- English and Punjabi language toggle.
- Crop presets for common rice–wheat heartland crops.
- User-entered yield and market price with live per-acre and whole-field net-profit calculations.
- Per-acre cost, break-even price, gross revenue, and net-profit calculations.
- Farm-size totals for fertilizer and pesticide costs based on each per-acre rate.
- Seed-count yield estimator for wheat and rice using farm area, plant density, seeds per plant, survival rate, and 1,000-seed weight.
- Responsive offline chart comparing revenue, each expense category, and profit or loss.
- Historical Punjab market-price trend chart for wheat, paddy/rice, maize, and potato.
- Installable PWA with home-screen icons and an offline service-worker app shell.
- WhatsApp share button that sends a concise crop-budget and yield estimate to family or advisors.
- GPS-aware pre-sowing simulator comparing model profit, whole-farm return, water pressure, sowing readiness, and estimated harvest date.
- Soil-health input guidance for pH, organic carbon, phosphorus, and potassium.
- Crop-rotation planner with nitrogen-balance suggestions.
- Optional live mandi-price and weather data, with cached results when available.
- Local persistence through `localStorage`; figures remain on the device.
- Responsive layout for phones, tablets, and desktop screens.
- Print-friendly styling.

## Run locally

This is a self-contained static HTML application. Open `index.html` directly in a browser, or serve the project with any static web server:

```bash
python3 -m http.server 8000
```

Then visit <http://localhost:8000>.

## Install on a phone

Open the deployed website in a mobile browser. On Android Chrome, use **Install app** or **Add to Home screen** from the browser menu. On iPhone Safari, use **Share → Add to Home Screen**. The service worker caches the app shell so the calculator remains available when the connection is weak or unavailable; live mandi and weather updates continue to use the app’s cached-data fallbacks.

To share an estimate, enter the crop-plan values and tap **Share on WhatsApp**. The app opens WhatsApp with the current crop, acreage, yield, market price, per-acre profit, whole-farm profit, and any seed-count estimate already calculated. The farmer reviews the message and chooses the family member or advisor before sending.

## Whole-farm livestock and residue planning

The setup also asks whether the farmer keeps cattle or buffalo and how many. Based on the selected crop, area, and leftover plan, the app estimates total residue, usable residue after broad field/drying/storage losses, approximate cattle-feed days, and possible sale value. Farmers can compare **feed**, **sale**, **soil return/mulch**, or a split plan. The tool does not treat residue value as guaranteed profit: buyers, moisture, transport, weighing, and local prices must be confirmed. It also warns against burning and unsafe feed; moldy, wet, contaminated, or unsuitable residue must not be fed, and ration balance should be checked with a veterinary or livestock adviser.

## Guided setup flow

The top of the app now presents an eight-step setup for farmers who want a simpler starting point: **location**, **soil test**, **crop choice**, **farm size and irrigation**, **fertilizer and pesticide approach**, **harvest and selling costs**, **result check**, and **recommendation**. The guided answers sync into the detailed calculator, crop comparison, weather panel, soil guide, and WhatsApp report so the farmer does not need to enter the same information twice.

## Pre-sowing planning

The simulator compares wheat, rice/paddy, maize, and potato using the entered farm size and planning assumptions. It uses GPS, when permitted, to request a seven-day forecast for the farm’s actual coordinates; otherwise it falls back to Ludhiana. The comparison flags whether the selected sowing date is within a broad Punjab crop window, estimates a harvest date from a crop duration, and turns forecast rain into an irrigation or field-work caution. Because weather cannot reliably be forecast months ahead, the harvest date is a planning target: recheck the local forecast and official warnings in the week before harvest, and arrange drying, storage, transport, and insurance in advance.

The regional crop-window and water-saving guidance is informed by Punjab Agricultural University’s [Rabi Package of Practices](https://pau.edu/content/ccil/pf/pp_rabi.pdf) and [Kharif Package of Practices](https://pau.edu/content/ccil/pf/pp_kharif.pdf). The tool remains an estimate; farmers should confirm decisions with their soil test, field conditions, local PAU/KVK advice, and official weather alerts.

## Data and assumptions

The included crop, soil, weather, and price values are intended as **starting assumptions**, not official recommendations. Replace them with your own soil-lab report, local mandi quote, farm records, and advice from a qualified agricultural extension professional before making production or financial decisions.

Net profit is calculated as **(yield per acre × market price) − total cost per acre**. The whole-field figure multiplies the per-acre profit by the entered acreage. Fertilizer and pesticide whole-farm totals are calculated as **per-acre rate × farm acres**.

The seed-count estimator uses **square feet × plants per square foot × harvestable-plant rate × seeds per plant** to estimate total seeds, then converts that count to kilograms using the entered 1,000-seed weight. The displayed values are potential grain-count estimates, not guaranteed harvests. For better accuracy, count a representative field sample and weigh 1,000 seeds from the farmer’s own crop rather than relying on a reference value.

The app is designed to work without a network connection. When network access is available, the optional live-data lookups may update the displayed mandi price, historical trend, and weather information; successful trend responses are cached on the device for later viewing. The calculator itself does not require an account or backend.

## Project structure

```text
.
├── index.html   # Complete application: markup, styles, and JavaScript
├── LICENSE      # MIT License
└── README.md    # Project documentation
```

## License

This project is released under the [MIT License](LICENSE).
