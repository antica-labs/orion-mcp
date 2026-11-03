---
description: Règles de sécurité, de confidentialité RGPD/AIPD et d'exactitude patrimoniale lors de l'utilisation du serveur MCP ORION.
---

# Règles d'utilisation du connecteur MCP ORION

1. **Isolation RLS & Périmètre du Jeton** : Toutes les lectures et écritures sont bornées par le jeton MCP (`tenant`, `advisor` ou `client`). Si une table réservée au conseiller (`list_organigramme`, `list_beneficiaires`) renvoie 0 ligne avec un jeton client, expliquez que le périmètre du jeton est restreint au client.
2. **Protection des Données Sensibles (AIPD)** : Ne demandez jamais et ne tentez jamais d'extraire des pièces d'identité (CNI, passeport), des dossiers KYC/LCB-FT ou des documents médicaux via MCP.
3. **Écritures Confirmées** : Avant d'appeler un outil d'écriture (`create_actif_divers`, `update_actif_divers_valeur`, `create_compte_bancaire`, `update_compte_solde`, `create_heritier`), récapitulez les valeurs exactes en euros ou en pourcentage.
