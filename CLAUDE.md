# Embark Price Tracker — Agent Instructions

## Purpose
This project tracks daily prices of Embark dog DNA test kits from shop.embarkvet.com and records them in `embark_price_tracker.csv`.

## Git Setup (run at the start of every session before pushing)
If `GITHUB_TOKEN` is set, configure git to use it:
```bash
git remote set-url origin https://$GITHUB_TOKEN@github.com/ken-ck-yu/embark-price-tracker.git
```

## Scheduled Task

### Products to track
1. **Breed + Health Dog DNA Test** — `https://shop.embarkvet.com/products/breed-and-health-dog-dna-test-kit`
2. **Breed + Health Test 2-Pack** — `https://shop.embarkvet.com/products/2-pack-embark-breed-health-kit`

### Important
- Do **not** visit the Embark URLs directly (you will be blocked). Use web search to find the current prices from search engine results, Google Shopping snippets, or third-party retailer listings that reflect the official Embark site price.
- Search for prices on `shop.embarkvet.com` specifically.

### Steps
1. Search for the current price of each product using web search.
2. Record prices in `embark_price_tracker.csv` by appending a new row.
3. Calculate the **lowest price of the day**: the lower of (single kit price) vs (2-pack price ÷ 2).
4. Set **price ≤$119** to `true` if either the single price OR the 2-pack per-kit price is ≤ $119, otherwise `false`.
5. Commit and push directly to `main`.

### CSV format
```
Date,Breed + Health Dog DNA Test,Breed + Health Test 2-Pack,lowest price of the day,price <=$119
10-May-26,00:35,$129 ,$255 ,$127.50 , false
```
- Date format: `DD-Mon-YY` (e.g. `10-May-26`)
- Time 24 hours format hours:minute
- Prices include `$` sign
- Branch: `main`
