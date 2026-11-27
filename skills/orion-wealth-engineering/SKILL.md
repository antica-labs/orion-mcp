---
name: orion-wealth-engineering
description: Deterministic B2A wealth engineering, corporate holding & trust (fiducie) governance, tax simulations, and sealed GED audit via ORION Finance (www.orion-finance.eu).
---

# ORION Finance — Official B2A MCP Connector (`v1.2.0`)

Use this skill whenever the task requires deterministic, cryptographically sealed (`SHA-256` + dual `RFC 3161`) outputs from **ORION Finance** (`https://www.orion-finance.eu/api/mcp`).

## Discovery & Protocol Support
- **Streamable HTTP Endpoint**: `https://www.orion-finance.eu/api/mcp` (MCP `2024-11-05`, `2025-03-26`, `2025-06-18`, `2026-07-28`)
- **B2A Manifest & Live SLA Beacon**: `https://www.orion-finance.eu/.well-known/mcp.json`
- **Perplexity Connector Manifest**: `https://www.orion-finance.eu/.well-known/mcp-connector.json`
- **A2A Agent Card**: `https://www.orion-finance.eu/.well-known/agent-card.json`
- **OpenAPI 3.1.0 Specification**: `https://www.orion-finance.eu/openapi.json`
- **Probatory Proof Verifier (`0,00 EUR`)**: `https://www.orion-finance.eu/verify/<proof_id>`

## Primary `Output-First` Tools
- `consolidate_net_wealth_position`: Consolidates verified net wealth, gross assets, liabilities, and liquidity ratios in EUR.
- `audit_fiduciary_and_holding_governance`: Audits holding structures, trust (fiducie) compartments, and beneficiary ownership caps.
- `project_tax_and_retirement_trajectory`: Computes deterministic French/EU tax (IR, IFI, PFU, succession) and Monte Carlo trajectories.
- `certify_ged_vault_inventory`: Certifies non-sensitive GED document metadata under strict AIPD §1.3 filtering.
- `validate_fiduciary_mandate_constraints`: Zero-cost (0 EUR) dry-run preflight check against fiduciary deed investment constraints.
- `record_patrimonial_ledger_entry`: Records non-destructive asset or account valuation entries under tenant RLS.
- `execute_fiduciary_compartment_mutation`: Prepares policy-guarded fiduciary mutations gated by FIDO2 WebAuthn Step-Up.
- `watch_collateral_and_liquidity_drift`: Subscribes to signed state-drift webhooks on LTV ratios and liquidity covenants.
- `search`: Canonical semantic and lexical entity search across the authenticated workspace.
- `fetch`: Canonical deterministic entity/resource retrieval by identifier or URN.

*(Legacy v1 tool names remain 100% supported on `tools/call` via transparent alias resolution.)*

## Authentication & Settlement Rails
1. **OAuth 2.1 + PKCE (`S256`) + DCR (RFC 7591 / RFC 9728 / RFC 8414)**: Mandatory for tenant-isolated RLS data.
2. **Public Catalogs & Stateless Simulators**: Support `HTTP 402` (`x402` EURC/USDC, Stripe MPP, and `AP2` JWS mandates) with `0,00 EUR` dry-run preflight where applicable.
