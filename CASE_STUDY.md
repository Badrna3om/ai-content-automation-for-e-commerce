# Arabic E-commerce Content Automation — Engineering Case Study

## The business problem

A small e-commerce marketing team may need to research products, prepare SEO content, enrich articles with catalog information, assemble social captions, seek editorial review and keep a content queue updated.

## Two workflow branches

| Branch | Input | Automated stages | Human-facing output |
| --- | --- | --- | --- |
| SEO Article Factory | Google Sheets queue | AI Arabic writing, WooCommerce product lookup, Pexels image lookup, HTML assembly | WordPress **draft** and Telegram review notification |
| Product Marketing Generator | Telegram request / selected product | Product filtering, selection rotation and AI caption package | Telegram-delivered angle, copy, CTA, hashtags and image prompt |

The committed public n8n export contains **18 nodes** (inspected 26 Nov 2026). Node counts do not indicate content quality, reach or time saved.

## Proof available in this repository

- [Workflow graph](images/workflow-overview.png) — the two-branch automation graph.
- [Illustrative WordPress article draft](images/wordpress-draft-demo.png) — example formatting and draft structure.
- [Illustrative Telegram content package](images/telegram-content-output-demo.png) — example product output.
- [Sanitized workflow export](workflows/ai-content-automation-public.json) — inspectable n8n configuration.
- [Validation workflow](.github/workflows/validate-workflow.yml) — automated validation infrastructure, not an end-to-end live publishing proof.

## Design choices

- Separate SEO long-form and short-form product marketing concerns.
- Return reviewable drafts rather than presenting AI output as a final approved article.
- Use structured queue and usage history to reduce repeated product selection.
- Keep generated captions and prompts inspectable by an editor.

## Evidence boundary and setup

The screenshots are illustrative demos and the public export is sanitized. There are no independently verified SEO ranking, impressions, sales or labor-hour metrics in this repository. Do not infer automatic publication from the draft-creation branch.

[Animated overview](assets/visual-tour.webp) · [Setup](SETUP.md) · [Security](SECURITY.md)
