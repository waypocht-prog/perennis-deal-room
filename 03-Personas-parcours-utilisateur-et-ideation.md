# 👥 Capstone · Partie 2 — Personas, parcours utilisateur et idéation

**Projet :** Pérennis. Partie 2 du dossier — analyse du besoin et idéation de la solution.

Particularité du marché : il est **bilatéral**. Il y a donc deux personas principaux —
le **cédant** et le **repreneur** — auxquels s'ajoute l'utilisateur interne de la
plateforme, mon analyste.

---

## 👤 Persona 1 — LE CÉDANT

> **Jean-Pierre Rousseau, 64 ans — fondateur et dirigeant d'une PME.**
> Mécanique de précision (fabrication de composants métalliques), région
> Auvergne-Rhône-Alpes. CA ≈ 8 M€, 45 salariés, rentable (EBITDA ≈ 1,2 M€).

- **Rôle :** dirige l'entreprise depuis 35 ans, connaît personnellement chaque client
  et chaque machine.
- **Objectifs :** partir à la retraite d'ici deux à trois ans ; le prix de cession
  constitue son capital retraite ; **préserver les emplois et le savoir-faire** qu'il a
  bâtis toute sa vie.
- **Frustrations :**
  - « Ma fille est médecin au Canada, mon fils ne veut pas de l'usine. Je n'ai
    **personne à qui transmettre**. »
  - « Je **ne sais pas ce que vaut** mon entreprise. J'ai peur de la brader. »
  - « Il ne faut surtout pas que la rumeur circule : clients et salariés paniqueraient.
    J'ai besoin de **silence**. »
  - « Les rares repreneurs français **cassent le prix** d'entrée de jeu. »
- **Ce qu'il attend :** un repreneur sérieux et **solvable**, une confidentialité totale,
  un bon prix, et la continuité pour son équipe.

---

## 👤 Persona 2 — LE REPRENEUR / INVESTISSEUR

> **Timur A., 45 ans — entrepreneur d'Almaty (Kazakhstan), avec une partie de son
> activité à Dubaï.** Capital à placer : 3 à 10 M€.

- **Rôle :** homme d'affaires accompli, à la recherche d'un placement fiable pour son capital.
- **Objectifs :** investir dans une **économie stable de l'UE** ; détenir un actif tangible
  et rentable ; percevoir un revenu régulier ; diversifier son exposition géographique et
  juridictionnelle.
- **Frustrations :**
  - « Je **ne connais pas le marché français**, ni la langue, ni la culture d'affaires. »
  - « **À qui faire confiance ?** Je crains la fraude et les lourdeurs administratives. »
  - « Comment diriger une usine en France si je vis à Almaty et que je ne la connais pas ? »
- **Ce qu'il attend :** un partenaire **parlant sa langue (RU/AR)** et comprenant sa
  mentalité d'affaires ; des cibles **vérifiées** ; un accompagnement clé en main ; et
  surtout un **management de transition**, pour ne pas avoir à déménager ni à diriger
  à l'aveugle dès le premier jour.

> 🔑 C'est précisément la première peur de Timur — « comment vais-je diriger ? » — que
> vient couvrir mon service distinctif de **management de transition**, absent de l'offre
> des courtiers M&A classiques.

---

## 👤 Persona 3 — L'UTILISATEUR INTERNE

> **Léa, 29 ans — analyste M&A dans l'équipe Pérennis.**

- **Objectif :** qualifier le maximum de cibles chaque mois.
- **Douleur actuelle :** un sourcing entièrement manuel — des heures passées dans les
  registres (Pappers, Infogreffe).
- **Avec Pérennis :** l'agent **Radar** effectue le travail de dégrossissage ; Léa se
  consacre aux personnes et aux transactions.

---

## 🛤️ Parcours utilisateur (avant → après)

### Côté cédant

| Étape | ❌ Aujourd'hui | ✅ Avec Pérennis |
|---|---|---|
| Connaître la valeur | ne sait pas, estime au jugé | l'agent **Valorisation** fournit une fourchette argumentée |
| Trouver un repreneur | plus d'un an d'attente, 42 % d'échecs | un repreneur **vérifié** de la CEI ou du Moyen-Orient est apporté |
| Confidentialité | risque de fuite | teaser anonymisé, accès sous NDA |
| Prix | les candidats français négocient à la baisse | la concurrence sur un actif rare soutient le prix |
| Après la vente | il quitte tout, la continuité est fragile | le manager de transition assure la passation |

### Côté repreneur

| Étape | ❌ Aujourd'hui | ✅ Avec Pérennis |
|---|---|---|
| Trouver une cible | marché européen inconnu | l'agent **Matching** sélectionne selon ses critères |
| Confiance et langue | barrière RU/AR | un interlocuteur dans sa langue, le « pont » culturel |
| Vérification | crainte d'être trompé | agent **Due Diligence** et guichet **KYC/LCB-FT** |
| Direction à distance | ne sait pas gérer de loin | **manager de transition** sur la période charnière |
| Rendement | risque et incertitude | un actif rentable dès le premier jour, sous contrôle |

> ⏱️ Effet avant/après : le délai de recherche passe de **plus de 12 mois à quelques
> semaines** ; côté repreneur, l'entrée sur un marché inconnu se fait **sans barrière
> linguistique ni barrière de gestion**.

---

## 💡 Idéation — trois pistes de solution

**Méthode employée :** Design Thinking (Empathize → Define → Ideate → Prototype → Test),
combiné à l'**AI Opportunity Tree** vu au cours *Stratégie Business & IA*. Divergence
sans censure d'abord, convergence par grille de critères ensuite.

### Idée 1 — 🏛️ Pérennis : plateforme d'IA hybride, conseil et management de transition *(recommandée)*

Une plateforme bilatérale réunissant cédants et repreneurs, des agents d'IA pour le
sourcing et l'appariement, un accompagnement complet de la transaction et un management
de transition.

- *Outils IA :* n8n, Claude, API Pappers et Infogreffe, OpenSanctions, Base44.
- ✅ Impact maximal, fossé concurrentiel unique (pont Est ↔ Ouest et transition),
  démonstration très parlante.
- ⚠️ Périmètre plus large → nécessite un lancement par phases pour rester réaliste.

### Idée 2 — 🔍 SaaS de sourcing sell-side *(outil seul)*

L'IA détecte les entreprises sans successeur et revend les « leads » à d'autres conseils M&A.

- *Outils IA :* n8n, API Pappers et scoring, sans couche conseil.
- ✅ Plus simple, produit purement technologique.
- ⚠️ N'exploite pas mon fossé (ni le réseau, ni la langue, ni la transition n'y servent),
  marge faible, je deviens fournisseur de leads plutôt qu'auteur de la transaction.

### Idée 3 — 🎯 Conciergerie buy-side pour les repreneurs de l'Est

Des mandats de recherche sur mesure : je prends le brief d'un acheteur de la CEI ou du
Moyen-Orient et je cherche la cible pour lui.

- *Outils IA :* agent Radar pour le sourcing sur critères, Claude pour les mémos.
- ✅ Exploite mon fossé, forte valeur par client, mise en œuvre rapide.
- ⚠️ Ne passe pas à l'échelle sans base sell-side, dépend du flux de repreneurs,
  effet plateforme plus faible.

---

## 🏆 Sélection argumentée (critères notés de 1 à 5)

| Critère | 🏛️ Pérennis (hybride) | 🔍 SaaS de sourcing | 🎯 Conciergerie buy-side |
|---|---|---|---|
| Impact sur le problème | 5 | 3 | 4 |
| Exploite mon fossé (réseau / langue / transition) | 5 | 1 | 5 |
| Différenciation | 5 | 2 | 4 |
| Effet de démonstration | 5 | 3 | 4 |
| Faisabilité | 3 | 4 | 4 |
| Coût de lancement *(bas = mieux)* | 3 | 4 | 4 |
| **Total** | **26** 🥇 | 17 | 25 |

> **Conclusion :** l'hybride **Pérennis** l'emporte — c'est la seule option qui exploite
> pleinement mon avantage (réseau, langue russe, management de transition) et qui produit
> un effet plateforme. La conciergerie buy-side (idée 3) arrive juste derrière : elle
> devient donc la **phase MVP**.
>
> 🚀 **Lancement par phases, pour concilier ambition et réalisme :**
> - **Phase 1 (MVP) :** conciergerie buy-side — je travaille avec deux ou trois repreneurs
>   de la CEI et du Moyen-Orient, l'agent Radar source les cibles pour eux. Rapide, peu
>   coûteux, et mon fossé sert dès le premier jour.
> - **Phase 2 :** ajout de la base sell-side et du matching → la plateforme bilatérale complète.
> - **Phase 3 :** le management de transition devient une ligne de revenus autonome.
>
> Cette progression neutralise la faiblesse de l'hybride sur la faisabilité : la grande
> vision est démontrée, mais le démarrage reste tenable.
