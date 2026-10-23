# STOCKRESCUE-AI
https://pixel-perfect-snapshot-8505.lovable.app 
Stock Rescue helps businesses recover value from inventory at risk of becoming waste. It analyzes stock levels, sales velocity, and expiry dates to flag slow-moving, overstocked, or near-expiry items, then recommends the best action for each: markdown, bundling, transfer to a higher-demand location, return to supplier, or donation
# 📦 Stock Rescue

Stock Rescue helps businesses recover value from inventory that is at risk of
becoming waste. It identifies slow-moving, overstocked, or near-expiry items
and recommends the best action to rescue them before they turn into a loss.

## The Problem

Unsold stock ties up cash, takes up storage space, and often ends up written
off or thrown away. Most small and mid-sized businesses spot these items too
late, and have no clear plan for what to do with them.

## The Solution

Stock Rescue analyzes inventory and sales data to:

- **Detect** at-risk items using days-of-cover, sell-through rate, and expiry dates
- **Score** each item by urgency and potential financial loss
- **Recommend** a rescue action:
  - Markdown / discount
  - Bundle with fast-moving products
  - Transfer to a higher-demand location
  - Return to supplier
  - Donate or liquidate

## Features

- CSV import for inventory and sales history
- Risk scoring (Critical / High / Medium / Low)
- Action recommendations with estimated recovery value
- Interactive dashboard with filters by category, location, and risk level
- Exportable reports (CSV / PDF)

## Quick Start

    git clone https://github.com/<your-username>/stock-rescue.git
    cd stock-rescue
    pip install -r requirements.txt
    streamlit run app/dashboard.py

Try it with the included `data/sample_inventory.csv`.

## Input Data Format

| Column        | Description                     |
|---------------|---------------------------------|
| sku           | Unique product ID               |
| name          | Product name                    |
| quantity      | Units on hand                   |
| unit_cost     | Cost per unit                   |
| unit_price    | Selling price                   |
| expiry_date   | Optional expiry date            |
| avg_daily_sales | Average units sold per day    |
| location      | Store or warehouse              |

## How Risk Is Scored

    days_of_cover = quantity / avg_daily_sales
    risk = f(days_of_cover, days_to_expiry, capital_tied_up)

Items whose days of cover exceed their remaining shelf life are flagged as critical.

## Roadmap

- [ ] Demand forecasting (seasonality-aware)
- [ ] Automated discount optimization
- [ ] Integrations (Shopify, Zoho, Tally)
- [ ] Email/WhatsApp alerts for critical items
- [ ] Multi-warehouse transfer suggestions

## Contributing

Pull requests are welcome. Please open an issue first to discuss major changes.
