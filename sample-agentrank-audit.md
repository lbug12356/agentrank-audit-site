# Sample AgentRank Audit Report

Target: `https://example-saas.test`

Score: `82 / 100`

## Summary

The site is mostly ready for AI crawler workflows. Search crawlers have enough access, sitemap discovery is present, and structured data exists. The highest-value fix is to make customer proof and implementation docs more crawlable.

## Priority Fixes

1. Add an explicit robots.txt policy for `OAI-SearchBot`, `Claude-SearchBot`, and `PerplexityBot`.
2. Add a public customer proof page linked from the homepage.
3. Add `FAQPage` schema to the pricing and product pages.
4. Publish an optional `llms.txt` file that links only canonical docs, pricing, FAQs, and product pages.
5. Re-test after WAF or CDN rule changes to catch unexpected 403/429 responses.

## Suggested robots.txt Patch

```txt
User-agent: OAI-SearchBot
Allow: /

User-agent: Claude-SearchBot
Allow: /

User-agent: PerplexityBot
Allow: /

Sitemap: https://example-saas.test/sitemap.xml
```

## Suggested llms.txt Draft

```txt
# Example SaaS

Example SaaS helps RevOps teams forecast pipeline and revenue.

## Key Pages

- Product: https://example-saas.test/
- Pricing: https://example-saas.test/pricing
- Docs: https://example-saas.test/docs
- Customers: https://example-saas.test/customers
- FAQ: https://example-saas.test/faq
```

