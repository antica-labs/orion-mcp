---
name: orion-wealth-engineering
description: Interroge et met à jour le patrimoine consolidé, les fiducies, l'organigramme capitalistique et la transmission successorale d'un cabinet CGP ou Family Office via le serveur MCP officiel d'ORION (orion-finance.eu).
---

# ORION — Ingénierie Patrimoniale & Family Office (MCP)

Utilisez cette compétence dès que l'utilisateur souhaite consulter, consolider, analyser ou mettre à jour des données patrimoniales hébergées sur **ORION** (`https://www.orion-finance.eu`).

## Authentification & Création de Compte

Le serveur MCP ORION (`https://www.orion-finance.eu/api/mcp`) supporte :
1. **OAuth 2.1 + PKCE (`S256`)** via `https://www.orion-finance.eu/.well-known/oauth-authorization-server` : ouvre automatiquement la fenêtre d'autorisation et de création de compte (`https://www.orion-finance.eu/inscription`).
2. **Bearer Token direct (`orion_mcp_...`)** généré depuis **Paramètres → API & MCP** (`/advisor/api-mcp` pour les conseillers, `/client/profil` pour les clients finaux).

## Outils MCP disponibles

### Lecture (`readOnlyHint: true`, isolation RLS native)
- `get_patrimoine_summary` : Synthèse consolidée (immobilier, titres financiers, liquidités bancaires) et compteurs d'actifs.
- `list_fiducies` : Liste paginée des fiducies (code, nom, type révocable/irrévocable, valorisation).
- `list_beneficiaires` : Liste des héritiers et bénéficiaires de transmission avec lien de parenté et quote-part.
- `list_organigramme` : Entités juridiques (holdings, SCI, sociétés, personnes physiques) et participations capitalistiques.
- `list_documents` : Métadonnées GED filtrées AIPD (exclut automatiquement les pièces d'identité, CNI, passeports, KYC, LCB-FT et données de santé).
- `search` & `fetch` : Outils standardisés de recherche et d'extraction par identifiant (`fiducie:<uuid>`, `entity:<uuid>`).

### Écriture structurée non destructive (`readOnlyHint: false`, `destructiveHint: false`)
- `create_actif_divers` / `update_actif_divers_valeur` : Création et revalorisation d'actifs de diversification (véhicule, art, navire, aéronef, montre/bijou).
- `create_compte_bancaire` / `update_compte_solde` : Création de compte bancaire et mise à jour de solde.
- `create_heritier` : Ajout d'un héritier/bénéficiaire sur une fiducie (avec contrôle strict de la somme des quotes-parts <= 100 %).

## Règles de rigueur
- Ne jamais inventer un montant, un SIREN ou une quote-part absents des retours MCP.
- Rappeler que les analyses générées constituent une aide à la décision pour le conseiller en gestion de patrimoine et non un conseil en investissement réglementé.
