# Shopify Price Update Scripts

These scripts interact with the Shopify API to bulk update or reset product variant prices.

## Requirements
- Python 3
- [Requests](https://pypi.org/project/requests/)

Install dependencies using:

```bash
pip install -r requirements.txt
```

## Usage

1. **Update prices and create a backup**

   ```bash
   python scripts/update_prices_shopify.py --token <SHOPIFY_TOKEN> --domain <SHOPIFY_DOMAIN> --percent <PERCENT>
   ```

   This script fetches all product variants, saves their current prices to `scripts/shopify_backup.json`, and updates prices by the percentage provided.

2. **Reset prices from backup**

   ```bash
   python scripts/reset_prices_shopify.py --token <SHOPIFY_TOKEN> --domain <SHOPIFY_DOMAIN>
   ```

   The reset script reads the backup file and restores each variant to its original price.

Ensure you run `update_prices_shopify.py` first so that `shopify_backup.json` exists before attempting to reset prices.
