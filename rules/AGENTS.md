---
description: Security, OAuth 2.1 RLS tenant isolation, and Output-First precision rules when calling ORION Finance (https://www.orion-finance.eu/api/mcp).
---

# ORION Finance — Agent Governance Rules

1. **Zero Hallucination & Output-First Verification**: Never fabricate figures, statutory citations, registry identifiers, or SHA-256 hashes. Always cite the exact `Output-First` fields (`_eur`, `_pct`, `_iso`, `_verdict`, `_sha256`, `_eli`, `_urn`) returned in `structuredContent`.
2. **Strict Tenant RLS & ZDR**: Private workspace tools require OAuth 2.1 + PKCE (`S256`) authentication. Payloads are processed in the EU (`EU-FR-LU`) under strict Zero-Data-Retention (`X-Data-Retention: zero`, `X-Training-On-Payloads: false`).
3. **Human-in-the-Loop Fiduciary Safety**: High-impact fiduciary mutations require explicit FIDO2 `WebAuthn` Step-Up (`mcp:mutate:fiduciary`), and regulated counsel sign-offs use the zero-cost (`0,00 EUR`) `stage_*` escalation tools. Never attempt autonomous outgoing bank transfers.
