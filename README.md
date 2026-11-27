# ORION Finance — Official B2A & Enterprise MCP Connector (`v1.2.0`)

Deterministic B2A wealth engineering, corporate holding & trust (fiducie) governance, tax simulations, and sealed GED audit via ORION Finance (www.orion-finance.eu).

## Sovereign Endpoints & Discovery
| Surface | URL |
| :--- | :--- |
| **MCP Streamable HTTP** | `https://www.orion-finance.eu/api/mcp` |
| **MCP Discovery & SLA Beacon** | `https://www.orion-finance.eu/.well-known/mcp.json` |
| **Perplexity Connector Manifest** | `https://www.orion-finance.eu/.well-known/mcp-connector.json` |
| **A2A Agent Card** | `https://www.orion-finance.eu/.well-known/agent-card.json` |
| **OAuth 2.1 Protected Resource (RFC 9728)** | `https://www.orion-finance.eu/.well-known/oauth-protected-resource` |
| **OAuth 2.1 Authorization Server (RFC 8414)** | `https://www.orion-finance.eu/.well-known/oauth-authorization-server` |
| **OpenAPI 3.1.0 Spec** | `https://www.orion-finance.eu/openapi.json` |
| **Agent Index (`llms.txt`)** | `https://www.orion-finance.eu/llms.txt` |

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

## Guarantees
- **Zero Data Retention (`ZDR`)**: `X-Data-Retention: zero`, `X-Training-On-Payloads: false`, EU sovereign processing (`EU-FR-LU`).
- **AST Prompt-Injection Defense**: 6-layer deterministic sanitizer (`X-Prompt-Injection-Sanitized: ast-v2`).
- **Cryptographic Opposability**: `SHA-256` payload digest + dual qualified `RFC 3161` timestamps + `0,00 EUR` counterparty verification at `https://www.orion-finance.eu/verify/<proof_id>`.
