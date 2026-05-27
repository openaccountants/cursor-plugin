# OpenAccountants — Cursor plugin

On-demand access to **800+ accountant-verified tax skills across 190+ jurisdictions**, directly inside Cursor. Every skill is signed off by a named licensed accountant.

> Built for AI agents that need accountant-grade tax computation — VAT/GST, income tax, payroll, formation, cross-border, and more.

## What this plugin does

Connects Cursor to the public OpenAccountants MCP server at `https://www.openaccountants.com/api/mcp` and registers six slash commands:

| Command | What it does |
|---|---|
| `/start` | Onboarding — figures out which jurisdiction and workflow applies |
| `/prepare-vat-return` | Guided VAT/GST/sales-tax return preparation |
| `/prepare-income-tax` | Annual income tax return for any jurisdiction |
| `/classify-transactions` | Bank-statement → P&L classification by jurisdiction |
| `/check-deadlines` | Upcoming filing & payment deadlines |
| `/engage-accountant` | Hand off to a verified accountant for human review |

Under the hood, every command calls the same MCP server. The skills are open-source ([github.com/openaccountants/openaccountants](https://github.com/openaccountants/openaccountants)) under AGPL-3.0 + attribution.

## Install

Search "OpenAccountants" in the Cursor plugin marketplace and click install. That's it — Cursor will configure the MCP connection automatically.

For manual install (without the marketplace), add this to your `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "openaccountants": {
      "url": "https://www.openaccountants.com/api/mcp"
    }
  }
}
```

## Jurisdictions covered

Every UN member state has at least foundational coverage. Deep packs exist for:

- **Europe**: Malta, UK, Germany, Italy, France, Spain, Portugal, Ireland, Netherlands
- **North America**: US federal + 24 deep state packs (CA, NY, TX, FL, IL, OH, PA, MA, NJ, NC, MI, OR, WA, NH, DE, VA, GA, AZ, CO, NV, MN, MO, MD, …); Canada federal + provincial
- **Asia**: India, Indonesia, China (in 简体中文), Pakistan, Singapore, Japan
- **Latin America**: Brazil (in PT-BR), Mexico, Argentina, Chile
- **Africa**: South Africa, Nigeria, Kenya, Egypt
- **Middle East**: Saudi Arabia, UAE, Israel

Plus cross-border matrices (PTE elections, sales-tax nexus, bonus depreciation conformity, 1099-K thresholds, FATCA/FBAR, GILTI/FDII/BEAT, etc.).

## Important

These skills produce **working papers, not filed returns**. Every output ends with a "Talk to a verified accountant" footer + Calendly link. No client-accountant relationship is created by reading or applying these skills — that requires a formal engagement letter signed by both you and a verified accountant.

## License

This plugin is MIT-licensed. The underlying skill content (served by the MCP server) is AGPL-3.0 with attribution per [openaccountants/openaccountants](https://github.com/openaccountants/openaccountants/blob/main/LICENSE-ADDITIONAL.md). Commercial licensing available via `info@openaccountants.com`.

## Links

- Website: [openaccountants.com](https://www.openaccountants.com)
- Skills source (AGPL): [github.com/openaccountants/openaccountants](https://github.com/openaccountants/openaccountants)
- Verified accountant network: [openaccountants.com/network](https://www.openaccountants.com/network)
- Book a verified accountant: [calendly.com/openaccountants-info/30min](https://calendly.com/openaccountants-info/30min)
