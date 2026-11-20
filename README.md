# HenryCrawl Business & Compliance MCP: Company registries, Sanctions, Laws

EU/UK/Singapore company registries, sanctions + VAT + IBAN checks, law search and World Bank/Eurostat stats for AI agents.

**For:** KYC / compliance teams, B2B sales, analysts and legal research.
**6 tools**, pay per result (no subscription), callable from Claude, ChatGPT, Cursor or any MCP client.

| Tool | Price |
|---|---|
| [EU & UK Company Registry Lookup + VAT & LEI check](https://apify.com/henrycrawl/eu-uk-company-registry) | $0.004 per company profile ($4 per 1,000). Error rows and blocked pages are not charged. |
| [Asia Company Registry Lookup: Singapore ACRA + Taiwan](https://apify.com/henrycrawl/asia-company-registry) | $0.005 per company profile ($5 per 1,000). Error rows and blocked pages are not charged. |
| [Sanctions Screening + EU VAT + IBAN Check (OFAC, UN, UK, EU)](https://apify.com/henrycrawl/sanctions-vat-iban-check) | $0.004 per name screened ($4 per 1,000) |
| [EU & International Law Search: EUR-Lex, DE, AT, NL, ES, JP](https://apify.com/henrycrawl/law-regulation-search) | $0.003 per law found ($3 per 1,000) |
| [Government Statistics API: World Bank + Eurostat Time Series](https://apify.com/henrycrawl/gov-statistics-hub) | $0.002 per time series ($2 per 1,000). Error rows and blocked pages are not charged. |
| [News by Country & Language: 54 Google News Editions](https://apify.com/henrycrawl/news-by-country) | $0.002 per article ($2 per 1,000) |


## Remote MCP server for the whole bundle
Remote URL (Claude "Add custom connector", Cursor, any MCP client):

```
https://mcp.apify.com/?tools=henrycrawl/eu-uk-company-registry,henrycrawl/asia-company-registry,henrycrawl/sanctions-vat-iban-check,henrycrawl/law-regulation-search,henrycrawl/gov-statistics-hub,henrycrawl/news-by-country
```

Claude Desktop (`claude_desktop_config.json`), using your own Apify token: each call is billed to your Apify account at the prices above.

```json
{
  "mcpServers": {
    "henrycrawl-doanh-nghiep-phap-ly": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.apify.com/?tools=henrycrawl/eu-uk-company-registry,henrycrawl/asia-company-registry,henrycrawl/sanctions-vat-iban-check,henrycrawl/law-regulation-search,henrycrawl/gov-statistics-hub,henrycrawl/news-by-country",
        "--header",
        "Authorization:Bearer ${APIFY_TOKEN}"
      ],
      "env": {
        "APIFY_TOKEN": "<your Apify API token>"
      }
    }
  }
}
```


## Key features
- Official company records from UK, EU, Singapore and Taiwan registries
- Sanctions, EU VAT and IBAN checks in one call
- Legislation search with links to official text
- Pay per result; error rows and blocked pages not charged

## Example uses
- Ask Claude: 'check this supplier list against OFAC/UN/UK sanctions and validate their VAT numbers'
- Pull GDP and inflation series for 10 countries into one table for a market report

## FAQ
**How am I billed?**
Each call runs an Apify actor on your own Apify account, billed per result ($2 to $5 per 1,000). No subscription.

**Is the data official?**
Company, sanctions and statistics data come from the official registries and lists (Companies House, EU registries, OFAC, UN, World Bank, Eurostat).

**Is there free usage?** New Apify accounts get monthly free platform credit, enough to try every tool.

---
Built and maintained by **HenryCrawl** ([Apify Store](https://apify.com/henrycrawl)). Issues and feature requests: open a GitHub issue here.
