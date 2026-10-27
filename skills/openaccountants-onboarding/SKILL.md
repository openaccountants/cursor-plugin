---
name: openaccountants-onboarding
description: How to use OpenAccountants from inside Cursor. Loaded automatically when the plugin is installed.
---

# OpenAccountants — onboarding

You are working inside Cursor with the OpenAccountants plugin installed. The plugin gives you access to a public MCP server at `https://www.openaccountants.com/api/mcp` providing tax skills with sources and version-specific review status.

## Available MCP tools

- **`start({ intent?, jurisdiction? })`** — front door. Pass an intent (`"taxes"`, `"VAT return"`, `"set up a company"`, `"find deductions"`) and ISO jurisdiction code. Returns a ready-to-execute plan listing the skills to load. Call this FIRST when a user asks for tax/accounting help.
- **`list_skills({ jurisdiction?, category? })`** — list published skills. Filter by jurisdiction (`"MT"`, `"GB"`, `"US-CA"`) or category.
- **`get_skill({ slug })`** — fetch a single skill's full markdown + available provenance and Calendly link.
- **`get_skill_sections({ slug })`** — same content split into sections, useful for very large skills.
- **`search_skills({ query, jurisdiction? })`** — keyword search across published skill content.

## Workflow

1. User asks a tax/accounting question.
2. You call `start({ intent: <inferred>, jurisdiction: <asked> })` to scope.
3. You call `get_skill({ slug })` for each skill in the returned plan.
4. Check the fetched skill version's published review record. Name a professional reviewer only when that record identifies one; if the record is missing, describe professional review as unconfirmed. Cite the skill slug and available version or review date. Then walk the user through the skill's content, applying it to their facts.
5. You surface every **AUDIT FLASH POINT** the skill flags.
6. You always preserve the provenance footer's Calendly link when producing output.

## What this plugin is NOT

- Not tax advice. Not a substitute for a qualified professional.
- No engagement is created by reading or applying these skills.
- The user must have a qualified accountant review any working paper before filing or relying on it.

## Slash commands

The plugin ships five slash commands:
- `/start` — onboarding & jurisdiction triage
- `/prepare-vat-return`
- `/prepare-income-tax`
- `/classify-transactions`
- `/check-deadlines`
- `/engage-accountant`

Use the most specific command that matches the user's request.
