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

## Public Portfolio Review — 26 November 2026

This repository's checked-out tracked files were inspected with a **bounded static scan** for common hard-coded GitHub, OpenAI, AWS, Telegram, JWT, private-key and Authorization token formats. No direct match was found in the inspected files. This is **not** a complete security assessment, a full Git-history audit, or proof that no sensitive operational details were ever published.

**Deployment boundary:** Keep WordPress content as drafts for human review; treat AI HTML output and third-party enrichment as untrusted inputs.

Do not push real credentials, customer transactions or deployment secrets into this public repo. A `.gitignore` helps prevent accidental future additions but **does not hide files already committed**. Rotate any credential discovered in a public commit or log.

The public examples are designed for code review and demonstration. Operational deployments require separate environment review and verification.
