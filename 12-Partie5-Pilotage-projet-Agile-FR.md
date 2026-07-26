# 🗂️ Partie 5 — Plan de pilotage et gouvernance du projet (Pérennis)

> 🇷🇺 Это **Часть 5 по официальному référentiel (BLOC 04)** — управление проектом:
> метод Agile, команда и роли, спринты, бэклог, дашборд пилотирования, клоужер + REX.
> Текст на французском (для досье), с русскими подсказками. Валидирует C4.1–C4.4.

---

## 5.1 — Méthode de pilotage

**Choix : Agile hybride — Scrum (produit) + Kanban (flux des affaires).**
*(Scrum для разработки продукта + Kanban для потока сделок.)*

- **Scrum** pour la construction du produit (agents IA + Deal Room) : sprints de **2 semaines**,
  car l'incertitude est forte et il faut itérer avec les retours des utilisateurs (cédants,
  repreneurs, analystes).
- **Kanban** pour le flux métier des affaires (le pipeline de transmission), car les deals
  arrivent en continu et suivent des étapes fixes (Sourcé → … → Closing).
- **Argumentation :** petite équipe, besoin de livrer de la valeur tôt, priorités mouvantes,
  et surtout un impératif de **conformité à chaque incrément** — Scrum permet d'intégrer une
  revue de conformité dans la *Definition of Done*.
- **Contraintes/risques intégrés au choix :** dépendance à l'API Pappers (quota, données
  partielles), cycles de deals longs (6–12 mois) → on **sépare** la cadence produit (rapide,
  agile) de la cadence métier (longue) ; risque réglementaire → un incrément n'est « Done »
  que s'il passe la revue conformité.
- **Budget & ressources :** ~120 k€ d'amorçage (build, structure juridique, données, cadre
  de conformité) ; à maturité, équipe de 4 + partenaires externes (voir 5.2).

---

## 5.2 — Organisation de l'équipe projet

> *(Проект индивидуальный, но описываем идеальную команду для реального внедрения.)*

| Rôle | Responsabilités |
|---|---|
| **Product Owner / Fondateur** | vision, backlog, priorisation, relations cédants & repreneurs, décisions Go/No-Go |
| **Développeur no-code / automatisation** | Deal Room (Base44), workflows (n8n), intégrations MCP |
| **Data / AI Analyst** | agents IA, prompt engineering, qualité des données, valorisation |
| **Analyste M&A (métier)** | sourcing, qualification, due diligence, relation client |
| **Responsable conformité** | KYC/AML, sanctions, RGPD (externe au départ, internalisé à l'échelle) |
| **Partenaires externes** | notaires, avocats d'affaires, experts-comptables, managers de transition |

**Communication & collaboration :**
- **Daily** de 15 min chaque matin (alignement sur les priorités du jour).
- Outils : **Slack** (temps réel), **Notion** (documentation & backlog), e-mail (externe).
- Canaux dédiés : `#produit`, `#deals`, `#conformité`, `#général`.
- **Revue hebdomadaire** + revue de sprint toutes les 2 semaines.

**Gestion des dépendances** *(кто от чего зависит и как этим управляем) :*

| Livrable | Dépend de | Pilotage |
|---|---|---|
| Agent Matching | CRM acheteurs alimenté (PO) + fiches cibles (Radar) | board de dépendances Kanban |
| Passage d'un deal en Négociation | **feu vert Conformité** (KYC/sanctions) | *Definition of Done* = « conformité validée » |
| Agent Radar | clé API Pappers + Data Analyst | credential partagé, quota surveillé |
| Deal Room | schéma de données stabilisé | gel du modèle avant le sprint UI |

---

## 5.3 — Planification des itérations (sprints)

**Découpage produit — 6 sprints / 12 semaines (MVP) :**

| Sprint (2 sem.) | Objectif principal | Livrable |
|---|---|---|
| **Sprint 1** | Sourcing IA | Agent **Radar** (n8n + Pappers) + score de succession ✅ *(déjà livré)* |
| **Sprint 2** | Données & CRM | enrichissement + écriture des cibles dans Airtable/Sheets |
| **Sprint 3** | Interface | **Deal Room** (Base44) : fiches cibles, pipeline kanban |
| **Sprint 4** | Appariement | Agent **Matching** + profils acheteurs |
| **Sprint 5** | Conformité | **Guichet KYC/AML** + criblage sanctions (OpenSanctions) |
| **Sprint 6** | Communication & démo | Agent multilingue + tests utilisateurs + vidéo-démo |

**Backlog priorisé :**

| Fonctionnalité | Priorité | Sprint |
|---|---|---|
| Agent Radar + scoring | Haute | 1 |
| Guichet de conformité (sanctions/KYC) | Haute | 5 |
| Deal Room (pipeline + fiche cible) | Haute | 3 |
| Agent Matching | Haute | 4 |
| Écriture CRM (Airtable) | Moyenne | 2 |
| Agent Communication multilingue | Moyenne | 6 |
| Enrichissement financier (Orbis) | Basse | post-MVP |
| Management de transition (module) | Basse | post-MVP |

**Indicateurs de suivi :** % de tâches terminées par sprint · fonctionnalités livrées vs
planifiées · **burn-down chart** (travail restant dans le temps) · vélocité de l'équipe.

**Revues de sprint & retours :** en fin de chaque sprint, démo aux « utilisateurs » (un
cédant test et un repreneur de mon réseau) ; les retours sont consignés dans Notion et
**réintégrés au backlog** du sprint suivant.

---

## 5.4 — Tableau de bord de pilotage

*(Макет дашборда пилотирования — можно показать полосу KPI из Deal Room.)*

| Type | Indicateurs |
|---|---|
| **Quantitatif** | avancement des tâches, respect des délais, budget consommé, **tokens/API consommés** (Pappers, Claude) |
| **Qualitatif** | satisfaction utilisateurs (cédant/repreneur), qualité des livrables, performance de l'équipe |

- **Système de communication intégré :** feedbacks Notion, **alertes** (quota Pappers bas,
  correspondance sanctions détectée), reporting hebdomadaire au sponsor.
- **Actions correctives en cas d'écart :** retard de sprint → repriorisation du backlog ;
  qualité des données faible → ajustement des prompts/sources ; dépassement budget API →
  mise en cache et filtres plus stricts.
- **Maintien des compétences (montée en compétences) :** plan de formation (prompt
  engineering, n8n, LCB-FT), **pairing** entre rôles, documentation vivante (le dépôt GitHub
  et Notion servent de base de connaissances).

---

## 5.5 — Clôture et retour d'expérience (REX)

- **Plan de clôture :** transfert de connaissances (documentation, dépôt GitHub `perennis-deal-room`,
  README), passation aux équipes opérationnelles, archivage des décisions.
- **REX — ce qui a bien fonctionné :** l'agent Radar a été livré vite (n8n + Pappers) ;
  l'approche **MCP** rend le système portable et hébergeable dans l'UE.
- **REX — leçons apprises :** les données financières de Pappers sont parfois partielles →
  prévoir un enrichissement par SIREN ; les cycles de deals sont longs → piloter la
  trésorerie via retainers + transition.
- **Points d'amélioration :** automatiser davantage la due diligence ; renforcer le scoring
  avec des signaux supplémentaires.
- **Recommandations pour un déploiement à grande échelle :** voir Partie 7.2 (feuille de
  route 6–12 mois, facteurs clés de succès, conduite du changement).

---

*📄 RNCP — cette partie valide le BLOC 04 : C4.1 (méthode & risques), C4.2 (équipe, rôles,
communication, itérations), C4.3 (indicateurs, revues, clôture/REX), C4.4 (tableau de bord,
indicateurs quanti/quali, performance équipe).*
