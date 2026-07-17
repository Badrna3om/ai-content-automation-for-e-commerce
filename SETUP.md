# Setup Guide

## Prerequisites

- n8n instance with the required standard and LangChain nodes
- OpenAI API access
- Google Sheets OAuth2 connection
- WooCommerce REST API connection
- WordPress API connection
- Telegram bot
- Pexels API access

## Import

1. Download `workflows/ai-content-automation-public.json`.
2. In n8n, select **Import from File**.
3. Reconnect every credential node to your own account.
4. Replace every value beginning with `YOUR_`, `REPLACE_WITH_`, or `PUBLIC_`.

## Content Queue Sheet

Prepare a Google Sheet containing the fields used by the article branch:

| Column | Purpose |
|---|---|
| `title` | WordPress article title |
| `keyword` | SEO topic and draft slug source |
| `related_product` | Product search term for WooCommerce |
| `status` | Use `queued` for items awaiting processing |
| `wordpress_post_id` | Filled after draft creation |
| `created_at` | Filled after draft creation |
| `row_number` | Row identifier used for updates |

## Product Catalog Sheet

Prepare a product catalog containing:

| Column | Purpose |
|---|---|
| `product_name` | Product display name |
| `category` | Product category |
| `short_desc` | Short product description |
| `image_url` | Product image |
| `product_url` | Store link |
| `price` | Current price |
| `offer` | Optional promotion |
| `style_note` | Brand/style guidance |
| `active` | `yes`, `true`, or `1` for eligible products |
| `last_used_at` | Last content-generation timestamp |
| `times_used` | Number of times selected |

## Required Configuration

- Replace both Google Sheet IDs.
- Select your own n8n credential for each Google Sheets node.
- Connect OpenAI credentials and verify the selected models.
- Connect WooCommerce and WordPress credentials.
- Store the Pexels key securely; do not leave a real key in an exported workflow.
- Connect Telegram credentials and replace the chat ID.
- Replace `YOUR_STORE_DOMAIN` in the WordPress review link.
- Let n8n generate new production webhook IDs when the workflow is imported.

## Testing

1. Keep the workflow inactive.
2. Use test Google Sheets and a staging WordPress site.
3. Test the article branch with one queued row.
4. Confirm that WordPress creates a draft—not a published post.
5. Test Telegram with `post` and `post Product Name`.
6. Confirm that product usage fields update correctly.
7. Add error workflows and alerts before production activation.
