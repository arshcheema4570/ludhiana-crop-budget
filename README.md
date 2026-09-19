# Ludhiana Crop Budget

A bilingual (English / Punjabi) offline-first crop budgeting tool for farmers in and around Ludhiana, Punjab.

The calculator estimates **cost per acre, break-even price, expected return, and margin** using crop, land, yield, price, labor, input, irrigation, and machinery assumptions. It also includes lightweight soil-health guidance, crop-rotation notes, and optional live mandi-price and weather lookups.

## Features

- English and Punjabi language toggle.
- Crop presets for common rice–wheat heartland crops.
- User-entered yield and market price with live per-acre and whole-field net-profit calculations.
- Per-acre cost, break-even price, gross revenue, and net-profit calculations.
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

## Data and assumptions

The included crop, soil, weather, and price values are intended as **starting assumptions**, not official recommendations. Replace them with your own soil-lab report, local mandi quote, farm records, and advice from a qualified agricultural extension professional before making production or financial decisions.

Net profit is calculated as **(yield per acre × market price) − total cost per acre**. The whole-field figure multiplies the per-acre profit by the entered acreage.

The app is designed to work without a network connection. When network access is available, the optional live-data lookups may update the displayed mandi and weather information; the calculator itself does not require an account or backend.

## Project structure

```text
.
├── index.html   # Complete application: markup, styles, and JavaScript
├── LICENSE      # MIT License
└── README.md    # Project documentation
```

## License

This project is released under the [MIT License](LICENSE).
