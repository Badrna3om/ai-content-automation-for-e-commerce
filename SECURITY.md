# Security

This repository contains a sanitized workflow intended for portfolio review and controlled reuse.

## Removed from the Public Export

- API keys
- n8n credential IDs
- Google Sheet IDs and direct URLs
- Telegram chat IDs
- Webhook IDs
- n8n instance and workflow identifiers
- Private infrastructure details

## Deployment Rules

- Never commit real API keys or exported credentials.
- Store credentials in n8n's credential manager or a secure secrets system.
- Restrict Google Sheets, WooCommerce, WordPress, and Telegram permissions to the minimum required.
- Rotate any credential that has appeared in an exported file or public repository.
- Keep WordPress creation set to `draft` until editorial review is complete.
- Validate model output before inserting HTML into a CMS.
- Apply rate limits, retries, timeouts, and execution alerts in production.
- Avoid sending private customer or product data to an LLM unless your data policy permits it.

## Reporting a Security Issue

Please contact the repository owner privately rather than opening a public issue containing sensitive details.
