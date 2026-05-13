# Audit qualité DCT — SupEvents

**Audité par** : audit individuel (étudiante seule)
**Date** : 2026-05-13
**Version DCT** : main

---

## Catégorie 1 — Structure

| N°  | Critère                     | Score | Commentaire                                 | Action recommandée                     |
| --- | --------------------------- | ----- | ------------------------------------------- | -------------------------------------- |
| 1   | Page de garde présente      | 2     | Conforme au template                        | —                                      |
| 2   | Historique des révisions    | 2     | Présent mais peu détaillé                   | Ajouter versionnage plus fin           |
| 3   | Glossaire ≥ 15 termes       | 1     | Présent mais certains termes peu développés | Enrichir définitions (RGPD, SSO, etc.) |
| 4   | Arborescence DCT complète   | 2     | Structure conforme TP1.2                    | —                                      |
| 5   | Navigation inter-sections   | 1     | Liens parfois implicites                    | Ajouter liens internes                 |
| 6   | Respect du découpage §1→§10 | 2     | Sections bien séparées                      | —                                      |

**Total : 10 / 12**

---

## Catégorie 2 — Complétude

| N°  | Critère               | Score | Commentaire            | Action recommandée            |
| --- | --------------------- | ----- | ---------------------- | ----------------------------- |
| 1   | C4 Context présent    | 2     | OK TP 1.3              | —                             |
| 2   | C4 Containers présent | 2     | OK avec protocoles     | —                             |
| 3   | Diagrammes composants | 1     | présent mais simplifié | détailler dépendances modules |
| 4   | Séquences complètes   | 2     | inscription + échec OK | —                             |
| 5   | ADR présents          | 2     | 3 ADR présents         | —                             |
| 6   | STRIDE complet        | 2     | flux complets          | —                             |
| 7   | Matrice traçabilité   | 2     | 21 exigences couvertes | —                             |

**Total : 13 / 14**

---

## Catégorie 3 — Cohérence

| N°  | Critère                      | Score | Commentaire                   | Action recommandée |
| --- | ---------------------------- | ----- | ----------------------------- | ------------------ |
| 1   | Cohérence noms modules       | 2     | stable (TicketModule etc.)    | —                  |
| 2   | Cohérence API ↔ modules      | 1     | quelques endpoints implicites | aligner §8 et §7   |
| 3   | Cohérence événements         | 2     | RabbitMQ cohérent             | —                  |
| 4   | Cohérence RGPD ↔ stockage    | 2     | OK                            | —                  |
| 5   | Cohérence ADR ↔ décisions    | 2     | bien relié                    | —                  |
| 6   | Pas de contradiction majeure | 2     | globalement stable            | —                  |

**Total : 11 / 12**

---

## Catégorie 4 — Lisibilité

| N°  | Critère                         | Score | Commentaire                | Action recommandée   |
| --- | ------------------------------- | ----- | -------------------------- | -------------------- |
| 1   | Paragraphes lisibles            | 2     | globalement clair          | —                    |
| 2   | Diagrammes lisibles             | 2     | Mermaid correct            | —                    |
| 3   | Syntaxe homogène                | 2     | bon standard               | —                    |
| 4   | Sections bien structurées       | 2     | OK                         | —                    |
| 5   | Trop de texte dense             | 1     | certaines sections longues | découper paragraphes |
| 6   | Mise en évidence (gras, titres) | 2     | bien utilisé               | —                    |

**Total : 11 / 12**

---

## Catégorie 5 — Maintenabilité

| N°  | Critère                 | Score | Commentaire                         | Action recommandée           |
| --- | ----------------------- | ----- | ----------------------------------- | ---------------------------- |
| 1   | CODEOWNERS présent      | 2     | conforme                            | —                            |
| 2   | CI workflow présent     | 2     | GitHub Actions OK                   | —                            |
| 3   | Lint Markdown configuré | 2     | présent                             | —                            |
| 4   | Traçabilité corrections | 1     | pas toujours explicite dans commits | mieux structurer commits     |
| 5   | Liens internes vérifiés | 1     | quelques liens faibles              | vérifier navigation complète |

**Total : 8 / 10**

---

# Synthèse

**Total général : 53 / 60 (88%)**

---

## Top 5 des défauts les plus impactants

1. **Glossaire incomplet / définitions trop superficielles**
   → impact : compréhension globale du système

2. **Diagramme de composants pas assez détaillé**
   → impact : compréhension architecture interne

3. **Quelques incohérences mineures API ↔ modules**
   → impact : confusion implémentation backend

4. **Navigation interne entre fichiers insuffisante**
   → impact : lisibilité du DCT en lecture rapide

5. **Commits de correction pas toujours explicites**
   → impact : maintenabilité Git du projet

---

# Plan de correction

1. Enrichir le glossaire (SSO, OIDC, RBAC, webhook)
2. Compléter dépendances internes du backend (API → modules)
3. Ajouter liens internes entre sections (§7 ↔ §8 ↔ §10)
4. Simplifier certaines sections longues en paragraphes courts
5. Améliorer messages de commit avec références de critères

---

# Conclusion audit

La DCT est globalement cohérente et exploitable par un développeur externe.
Les améliorations restantes concernent principalement la précision documentaire et la maintenabilité à long terme.
