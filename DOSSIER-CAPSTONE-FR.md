# Projet Capstone — AI for Business (PSTB)
## Pérennis — Plateforme d'agents d'IA et conseil M&A pour la transmission d'entreprises en Europe

**Spécialisation :** AI for Financial Management *(appliquée au conseil M&A et à la
transmission d'entreprises : valorisation, business case, ROI, conformité LCB-FT)*
**Étudiant :** Abdul Gueny Djeirkhanov · **Cohorte :** FR_AI_BIZ#236_FT · Campus France
**Nature :** création d'entreprise réelle (le fondateur est commanditaire et consultant IA)
**Référentiel :** valide les blocs **BC01** (Définition du projet) et **BC04** (Pilotage du projet) du RNCP 40247

---

## Résumé exécutif

L'Europe fait face à une **crise silencieuse de la transmission d'entreprises** : des
centaines de milliers de PME rentables risquent de disparaître, non par échec, mais parce
que leurs dirigeants vieillissent **sans successeur**. En France, près de **500 000
dirigeants** partiront à la retraite (plus de **3 M d'emplois** en jeu) et **une entreprise
sur deux ne trouve pas de repreneur**. Le marché est déséquilibré : **3× plus de vendeurs
que d'acheteurs** — le facteur rare est **l'acheteur solvable et de confiance**.

**Pérennis** relie les deux rives : une **plateforme d'agents d'IA** détecte, valorise et
apparie les entreprises à céder (avec un **guichet de conformité** KYC/AML/sanctions et
l'humain dans la boucle), et un **réseau propriétaire d'acheteurs** de la CEI et du
Moyen-Orient — mon avantage (réseau, langue russe). S'y ajoute un accompagnement A→Z et un
**management de transition**.

**Impact :** sourcing **3,7× plus productif** (coût/cible −65 %), cycle ramené de > 12 mois
à < 6, et, à maturité (~50 M€/an de volume), ~**1,9 M€** de résultat net — dans un cadre
strictement conforme (RGPD, LCB-FT, sanctions, filtrage des IDE, EU AI Act).

---

# PARTIE 1 — Veille stratégique IA et analyse sectorielle

## 1.1 Dispositif de veille IA

**Méthodologie et sources :**
- **Rapports sectoriels :** BPCE L'Observatoire, Bpifrance Le Lab, DGE, CRA, Banque de
  France, KfW, Institut Sapiens, McKinsey/BCG (adoption IA).
- **Presse & experts :** publications M&A, deal sourcing, IA en finance.
- **Veille réglementaire :** EU AI Act, CNIL/RGPD, LCB-FT, **règlement UE de filtrage des IDE**.
- **Outils :** Perplexity/WebSearch, Feedly, Notion, alertes, newsletters spécialisées.
- **Couverture (exigée) :** concurrence (plateformes de deal sourcing), réglementation,
  technologies (agents IA, MCP), tendances sectorielles, et **RSE/éthique** (impact social
  de la transmission : préservation des emplois et du savoir-faire ; lutte anti-blanchiment).

**Conclusions :** l'IA générative est devenue **un standard** du M&A (voir 1.2) ; la
contrainte n'est plus technologique mais organisationnelle (données, conformité, confiance).
Le besoin de transmission est massif et durable, mais le marché est inefficace — ce qui
justifie une solution qui **augmente** la capacité d'un cabinet et **apporte les acheteurs
rares**.

## 1.2 Panorama sectoriel — 5 cas d'usage IA

| # | Acteur | Problème | Solution IA | Résultat mesurable | Leçon pour Pérennis |
|---|---|---|---|---|---|
| 1 | **Cyndx** (deal origination) | trouver des cibles avant qu'elles soient sur le marché | algorithme « Projected to Raise » (NLP + base mondiale) | prédit le besoin de capital avec **~86 % de précision** | → notre agent **Radar** (sourcing prédictif) |
| 2 | **Sourcescrub** | sourcer des PME détenues par leur fondateur | agrégation de signaux (conférences, presse, listes) | pipelines propriétaires pour fonds PE | → sourcer **au-delà des registres** |
| 3 | **Marché M&A (2025)** | efficacité des deals | intégration de la GenAI dans les workflows | **86 %** des responsables l'ont intégrée, **65 %** dans la dernière année | l'approche IA est **dé-risquée**, déjà adoptée |
| 4 | **Cabinets de due diligence** (ex. EthosData) | DD lente, risques manqués | IA qui lit les contrats et signale les anomalies | DD plus rapide, moins d'oublis | → notre agent **Due Diligence** |
| 5 | **RegTech KYC/AML** (ComplyAdvantage, Sanction Scanner) | criblage manuel long et risqué | screening automatisé sanctions & PEP | conformité à l'échelle | → notre agent **Conformité** |

## 1.3 Leviers de performance (AI Traffic Light)

Positionnement : **Innovation** (marché transfrontalier inédit adossé à l'IA) **+
Augmentation** (l'IA démultiplie une petite équipe). Leviers visés : **efficacité
opérationnelle**, **scalabilité**, **qualité** (données ancrées), **conformité** (guichet
automatisé). Ce n'est pas une automatisation intégrale : décisions et relations restent
humaines.

---

# PARTIE 2 — Analyse du besoin et idéation

## 2.0 La commande du commanditaire

- **Commanditaire :** le comité de fondation de Pérennis (moi, fondateur, mandatant le
  consultant IA que je suis également).
- **Mission (une phrase) :** *« Concevoir et prototyper une solution d'IA qui détecte les
  PME européennes à céder sans successeur et les met en relation, en toute conformité, avec
  des acheteurs vérifiés de la CEI et du Moyen-Orient. »*
- **Contraintes :** budget d'amorçage modeste ; conformité stricte (RGPD, LCB-FT,
  sanctions, IDE) ; confidentialité M&A ; humain dans la boucle ; outils no-code/standard.
- **Livrables attendus :** un prototype fonctionnel, un business case, un plan de pilotage.

## 2.1 Analyse du besoin

- **Organisation cible :** cabinet M&A boutique + plateforme, opérant sur le marché européen
  de la cession-transmission (France d'abord).
- **Pain point mesurable :** > 12 mois de recherche, 42 % de cessions échouées faute
  d'acheteur, 3× plus de vendeurs que d'acheteurs.
- **Parties prenantes & attentes :** cédants (prix, discrétion, continuité) · repreneurs
  (cibles vérifiées, langue, gestion à distance) · régulateur (conformité) · équipe interne.
- **Hiérarchisation des besoins (priorité) :** 1) apporter des **acheteurs solvables** ;
  2) **conformité** irréprochable ; 3) **sourcing** efficace ; 4) accompagnement A→Z ;
  5) management de transition.
- **Conformité du besoin :** traite des données personnelles (dirigeants, acheteurs) →
  base légale RGPD requise ; usage à **risque limité** au sens de l'EU AI Act (voir 4.4).

*(Brief client d'une page — Annexe A.)*

## 2.2 Session d'idéation

**Méthode retenue :** **Design Thinking** (Empathize → Define → Ideate → Prototype →
Test) combiné à l'**AI Opportunity Tree** vu au cours *Stratégie Business & IA*. Le marché
étant **bilatéral**, l'idéation a été conduite sur les deux versants (cédant et repreneur)
avant convergence. Conditions favorisant la créativité : divergence sans censure d'abord,
convergence par grille de critères ensuite ; ancrage systématique sur les frustrations
réelles issues de mon réseau d'acheteurs.

### Étape 1 — Compréhension des utilisateurs

**Persona 1 — Le cédant.** Jean-Pierre Rousseau, 64 ans, fondateur d'une PME de mécanique
de précision en Auvergne-Rhône-Alpes (8 M€ de CA, 45 salariés, EBITDA ~1,2 M€).
*Objectifs :* partir à la retraite d'ici 2–3 ans, la vente constituant son capital
retraite ; **préserver les emplois et le savoir-faire** bâtis en 35 ans.
*Frustrations :* « ma fille est médecin au Canada, mon fils ne veut pas de l'usine —
**personne à qui transmettre** » ; « je **ne connais pas la valeur** de mon entreprise » ;
« si la rumeur sort, clients et salariés paniquent — il me faut le **silence** » ; « les
rares repreneurs français cassent le prix ».

**Persona 2 — Le repreneur.** Timur A., 45 ans, entrepreneur d'Almaty avec une activité à
Dubaï, 3–10 M€ à placer. *Objectifs :* investir dans une **économie stable de l'UE**, un
actif tangible et rentable, diversifier sa juridiction. *Frustrations :* « je ne connais
ni le marché français, ni la langue, ni la culture d'affaires » ; « **à qui faire
confiance ?** » ; « comment diriger une usine en France depuis Almaty ? ». *Attentes :* un
partenaire **parlant sa langue (RU/AR)**, des cibles vérifiées, un accompagnement clé en
main et surtout un **management de transition**.

**Persona 3 — L'utilisateur interne.** Léa, 29 ans, analyste M&A chez Pérennis. Passe ses
journées à fouiller manuellement les registres ; avec l'agent Radar, elle se concentre sur
les personnes et les deals.

**Parcours utilisateur (avant → après) :**

| Étape — **côté cédant** | Aujourd'hui | Avec Pérennis |
|---|---|---|
| Connaître la valeur | ne sait pas, estime au doigt mouillé | l'agent **Valorisation** fournit une fourchette argumentée |
| Trouver un repreneur | > 12 mois d'attente, **42 % d'échecs** | un acheteur **vérifié** de la CEI / du Moyen-Orient est apporté |
| Confidentialité | risque de fuite dans l'entreprise | teaser anonymisé, accès sous NDA |
| Prix | les rares candidats négocient à la baisse | la concurrence sur un actif rare soutient le prix |
| Après la vente | il part, la continuité est fragile | le **manager de transition** assure la passation |

| Étape — **côté repreneur** | Aujourd'hui | Avec Pérennis |
|---|---|---|
| Trouver une cible | marché européen inconnu | l'agent **Matching** sélectionne selon ses critères |
| Confiance & langue | barrière RU/AR, peur de la fraude | interlocuteur dans sa langue, « pont » culturel |
| Vérification | crainte d'être trompé | agent **Due Diligence** + guichet **KYC/AML** |
| Direction à distance | ne sait pas gérer de loin | **management de transition** sur la période charnière |

### Étape 2 — Génération d'idées

**Idée 1 — Pérennis, plateforme hybride** *(IA + conseil + management de transition)*.
Plateforme bilatérale réunissant cédants et repreneurs, agents d'IA pour le sourcing et
l'appariement, accompagnement A→Z et management de transition.
*Outils IA mobilisés :* n8n (orchestration d'agents), Claude (analyse et rédaction
multilingue), API Pappers/Infogreffe (données), OpenSanctions (conformité), Base44 (UI).
*Avantages :* impact maximal, exploite pleinement mon fossé (réseau + langue + transition),
effet plateforme, démonstration très parlante.
*Limites :* périmètre large → nécessite un lancement par phases pour rester réaliste.

**Idée 2 — SaaS de sourcing sell-side** *(outil seul)*. Une IA détecte les entreprises sans
successeur et revend les « leads » à d'autres conseils M&A.
*Outils IA mobilisés :* n8n + API Pappers + scoring, sans couche conseil.
*Avantages :* simple, purement technologique, rapide à construire.
*Limites :* n'exploite **pas** mon fossé (ni le réseau, ni la langue, ni la transition ne
servent), marge faible, je deviens fournisseur de leads et non auteur de la transaction.

**Idée 3 — Conciergerie buy-side** *(mandats pour acheteurs de l'Est uniquement)*. Je prends
le brief d'un acheteur de la CEI / du Moyen-Orient et cherche la cible sur mesure.
*Outils IA mobilisés :* agent Radar pour le sourcing sur critères, Claude pour les mémos.
*Avantages :* exploite mon fossé, forte valeur par client, mise en œuvre rapide.
*Limites :* ne passe pas à l'échelle sans base sell-side, dépend du flux d'acheteurs,
effet plateforme faible.

### Étape 3 — Sélection et argumentation

**Critères de choix** (notés de 1 à 5) : impact sur le problème, exploitation de mon
avantage concurrentiel, différenciation, effet de démonstration, faisabilité et coût de
lancement.

| Critère | Pérennis (hybride) | SaaS de sourcing | Conciergerie buy-side |
|---|---|---|---|
| Impact sur le problème | 5 | 3 | 4 |
| Exploite mon fossé (réseau / langue / transition) | 5 | 1 | 5 |
| Différenciation | 5 | 2 | 4 |
| Effet de démonstration | 5 | 3 | 4 |
| Faisabilité | 3 | 4 | 4 |
| Coût de lancement *(bas = mieux)* | 3 | 4 | 4 |
| **Total** | **26 ✅** | 17 | 25 |

**Décision argumentée :** l'hybride **Pérennis** l'emporte — c'est la seule option qui
exploite entièrement mon avantage (réseau, langue russe, management de transition) tout en
créant un effet plateforme. Sa seule faiblesse est la faisabilité, corrigée par un
**lancement en trois phases** : *Phase 1* — conciergerie buy-side (l'idée 3, arrivée
deuxième) avec 2–3 acheteurs et l'agent Radar, rapide et peu coûteuse ; *Phase 2* — ajout
de la base sell-side et du matching, donnant la plateforme bilatérale ; *Phase 3* —
management de transition en ligne de revenus autonome. La grande vision est ainsi
démontrée, mais le démarrage reste réaliste.

## 2.3 Définition de la solution retenue

- **Nom & pitch :** *Pérennis — « Assurer la pérennité des entreprises qui ont fait l'Europe. »*
- **Description :** plateforme d'agents d'IA (sourcing, valorisation, matching, conformité,
  communication, due diligence, transition) + conseil M&A humain.
- **Utilisateurs & bénéfices :** cédants (vendre vite, bien, discrètement) · repreneurs
  (entrer sur le marché UE en confiance) · équipe (démultipliée par l'IA).
- **Type d'IA mobilisée :** **agents d'IA** (orchestrés par n8n) + **IA générative** (Claude,
  multilingue, analyse documentaire) + **automatisation** ; scoring à base de règles.
- **Données nécessaires & disponibilité :** registres publics (Pappers, Infogreffe, BODACC,
  INSEE — **disponibles via API**), CRM acheteurs (interne), listes sanctions/PEP
  (OpenSanctions — **ouvertes**), documents de deal (fournis, sous NDA).

---

# PARTIE 3 — Benchmark des outils IA / No-Code

## 3.1 Benchmark comparatif

| Outil | Catégorie | Fonctionnalités clés | Performance | Interopérabilité | Coûts | Limites |
|---|---|---|---|---|---|---|
| **Base44** | App no-code | app depuis un prompt, UI, CRM | rapide | API/webhooks, MCP | freemium | moins de contrôle logique |
| **n8n** | Automatisation / agents | workflows, AI Agent, auto-hébergé UE | fiable | **connecte Claude, Pappers, Airtable…** (natif) | open-source / cloud | courbe d'apprentissage |
| **Claude** | LLM | multilingue RU/AR/FR/EN, documents | qualité élevée | API, **MCP**, appelable par n8n | à l'usage (tokens) | coût au volume |
| **Pappers** | Données entreprises | dirigeants, âge, finances | temps réel | **API REST** (branchée à n8n) | 100 crédits gratuits puis packs | finances parfois partielles |
| **OpenSanctions** | Conformité | sanctions & PEP (UN/OFAC/EU/UK) | à jour | API / données ouvertes | gratuit/pro | nécessite interprétation |

*Interopérabilité — exemple concret :* dans n8n, un nœud HTTP interroge **Pappers**, le
résultat est scoré, puis envoyé à **Claude** pour rédiger un mémo, et écrit dans **Airtable**
— tout est relié via API/**MCP**, sans vendor lock-in.

## 3.2 Stack retenue & architecture

> **Base44** (interface) + **n8n** (orchestration, UE) + **Claude** (moteur) +
> **Pappers/Infogreffe** (données) + **OpenSanctions** (conformité), reliés par **MCP**.

```mermaid
flowchart LR
  subgraph Sources["Données (via MCP/API)"]
    P[Pappers / Infogreffe]
    O[OpenSanctions]
    C[CRM acheteurs]
  end
  R[Agent Radar] --> Q[Agent Qualif & Valo]
  Q --> M[Agent Matching]
  M --> OUT[Agent Communication]
  OUT --> DD[Agent Due Diligence]
  DD --> K[Guichet Conformité KYC/AML]
  K --> T[Agent Transition]
  P --> R
  P --> Q
  C --> M
  O --> K
  N[(Orchestrateur n8n)] -.pilote.- R & Q & M & OUT & DD & K & T
  H{{Humain valide chaque étape}} -.-> K
```

---

# PARTIE 4 — Cadrage du projet et Business Case

## 4.1 Note de cadrage

- **Périmètre — inclus :** sourcing, valorisation, matching, conformité, accompagnement
  A→Z, management de transition. **Exclu :** clôture automatisée, signature juridique
  (notaire), détention de fonds (séquestre).
- **Objectifs SMART :**
  - Livrer un **agent Radar fonctionnel** (n8n + Pappers) — *fait* ✅.
  - Atteindre **≥ 150 cibles qualifiées/mois** par analyste d'ici la fin du MVP (mois 6).
  - Signer **2–3 mandats acheteurs** en Phase 1 (mois 6–15).
  - **1ʳᵉ transaction** conclue au **mois 9–15**.
  - **0 incident de conformité** dès le premier jour.
- **Parties prenantes :** sponsor (fondateur), utilisateurs (analystes, cédants, repreneurs),
  équipe projet, partenaires (notaires, avocats, banques).
- **Contraintes :** techniques (quotas API), budgétaires (amorçage), humaines (petite
  équipe), temporelles (cycles longs).
- **Risques & atténuation :** voir tableau 4.4 et Partie 5.

## 4.2 Business Plan IA

**Coûts (régime cible, annuel) :** équipe ~350 k€ · **coûts IA/outils ~60 k€** · conformité
externe ~60 k€ · BD/déplacements ~80 k€ · admin ~50 k€ → **~600 k€**.

**Coûts IA spécifiques (détail) :**

| Poste | Estimation |
|---|---|
| API Pappers (crédits de recherche) | 100 gratuits, puis ~€/pack selon volume |
| Claude API (tokens : mémos, matching, rédaction) | ~200–500 €/mois au MVP |
| n8n (hébergement UE) + Base44 | ~50–150 €/mois |
| OpenSanctions | gratuit → pro à l'échelle |
| **Total IA au MVP** | **~300–800 €/mois** |

**Bénéfices :** gain de temps (sourcing ×3,7), moins d'erreurs (grounding), nouveaux revenus
(honoraires), satisfaction (cycle < 6 mois).

**ROI à 6 et 12 mois :**
- **6 mois :** phase d'investissement (build + pipeline) ; ROI **opérationnel** déjà visible
  via l'efficacité — **coût par cible qualifiée −65 %** ; premiers mandats signés.
- **12 mois :** 1ʳᵉ(s) transaction(s) en cours de closing → premiers **honoraires de succès**
  + retainers ; retour vers l'**équilibre** de l'investissement d'amorçage (~120 k€).
- À maturité (an 2–3) : produits ~2,49 M€, charges ~0,6 M€ → **~1,9 M€ net** (marge ~76 %).

**Pourquoi maintenant :** la vague de transmission est à son pic (2025–2035), l'IA en M&A
vient d'atteindre l'adoption de masse, et l'instabilité géopolitique pousse les capitaux de
l'Est vers l'UE. La fenêtre est ouverte.

## 4.3 Macroplanning (jalons & charges)

| Phase | Période | Jalons | Charge (j-h) |
|---|---|---|---|
| **Cadrage & Fondations** | Mois 0–6 | structure, marque, conformité, **MVP** | ~120 |
| **MVP buy-side & tests** | Mois 6–15 | mandats signés, **1ʳᵉ transaction** | ~180 |
| **Plateforme bilatérale** | Mois 15–30 | base sell-side, matching, équipe, CNCFA | ~260 |
| **Échelle & transition** | Mois 30–48 | Orbis, réseau interim, nouveaux marchés | ~300 |

```mermaid
gantt
  dateFormat  YYYY-MM
  axisFormat  %m/%y
  section Fondations
  Cadrage & MVP           :2026-09, 6M
  section MVP buy-side
  Mandats & 1re transaction :2027-03, 9M
  section Plateforme
  Sell-side & matching    :2027-12, 15M
  section Echelle
  Scale & transition      :2029-03, 18M
```

## 4.4 Conformité éthique et réglementaire

- **RGPD :** données de dirigeants et d'acheteurs traitées → **base légale** (intérêt
  légitime / consentement), minimisation, hébergement **UE**, registre des traitements, DPO,
  droits des personnes.
- **EU AI Act — classification :** système à **risque limité** (recherche, appariement,
  génération assistée) → obligations de **transparence** et de supervision humaine. Nous
  appliquons **volontairement** une gouvernance de niveau supérieur (documentation, logs,
  human-in-the-loop) vu les enjeux financiers. Aucune notation de crédit de particuliers
  (usage à haut risque) n'est réalisée.
- **Analyse des biais & mitigation :** risque de biais du sourcing (sur-pondérer certains
  secteurs/régions) et de la valorisation → **mitigation** : ancrage sur données officielles,
  sources diversifiées, seuils revus par un humain, suivi des écarts.
- **Principes éthiques :** transparence (brouillons IA signalés), équité, **human-in-the-loop**
  (aucune action client sans validation), « uniquement des fonds licites ».
- **Limites de l'IA :** hallucinations (chiffres inventés), données périmées, excès de
  confiance dans un score, dépendance → gérées par grounding + validation humaine.

**Risques principaux & atténuation :**

| Risque | Mesure |
|---|---|
| Sanctions / réputation (capitaux CEI) | KYC strict, refus au moindre doute, origine des fonds documentée |
| Réglementaire (IDE, secteurs) | vérification juridique en amont, notification si requis |
| Confidentialité | NDA, teasers anonymisés, VDR |
| Trésorerie (deals longs) | retainers + transition |
| Erreurs IA | grounding + humain |
| Dépendance au fondateur | institutionnalisation (équipe, CNCFA, marque) |

---

# PARTIE 5 — Plan de pilotage et gouvernance

*(Détail complet : fichier `12-Partie5-Pilotage-projet-Agile-FR.md`. Synthèse ci-dessous.)*

## 5.1 Méthode de pilotage
**Agile hybride** : **Scrum** (produit, sprints de 2 semaines) + **Kanban** (flux des
affaires). Choix justifié par l'incertitude produit, la petite équipe et l'impératif de
conformité (intégrée à la *Definition of Done*).

## 5.2 Organisation de l'équipe
Rôles : Product Owner/Fondateur · Dév no-code/automatisation · Data/AI Analyst · Analyste
M&A · Responsable conformité · partenaires externes. **Communication :** daily 15 min,
Slack + Notion, canaux `#produit #deals #conformité #général`. **Dépendances** pilotées via
un board (ex. : un deal ne passe pas en Négociation sans feu vert Conformité).

## 5.3 Itérations
6 sprints / 12 semaines : Radar ✅ → CRM → Deal Room → Matching → Conformité →
Communication+démo. **Backlog priorisé** (Haute/Moyenne/Basse), **burn-down**, revues de
sprint avec un cédant et un repreneur test, retours réintégrés au backlog.

## 5.4 Tableau de bord de pilotage

**Maquette fonctionnelle réalisée** — `prototype/perennis-pilotage.html`
*(capture : `captures/01-tableau-de-bord-pilotage.png`)*. Elle réunit sur un seul écran :

- **Indicateurs quantitatifs :** avancement global (47 %, 57/120 points), respect des délais
  (92 %), budget consommé (46 k€ / 120 k€) et **coût IA — API & tokens** (412 €/mois contre
  un plafond de 800 €), suivis d'un **burn-down** du travail restant par sprint.
- **Indicateurs qualitatifs :** satisfaction du cédant test (4,2/5) et du repreneur test
  (4,6/5), qualité des livrables au regard de la *Definition of Done* (89 %), performance de
  l'équipe (vélocité vs engagement, 96 %) et **0 incident de conformité**.
- **Système de communication intégré :** alertes automatiques (correspondance sanctions
  détectée → deal bloqué ; quota API Pappers bas), calendrier des revues de sprint et
  reporting hebdomadaire au sponsor via Slack et Notion.
- **Actions correctives en cas d'écart** : quatre écarts types et la réponse associée.
- **Maintien et montée en compétences :** formation suivie (75 %), sessions de pairing
  (8/12), documentation à jour (94 %) — détail du dispositif en regard.

## 5.5 Clôture & REX
Transfert de connaissances (GitHub, README, Notion) ; REX (Radar livré vite ; MCP portable ;
données Pappers partielles → enrichissement ; cycles longs → trésorerie) ; recommandations
de passage à l'échelle (Partie 7.2).

---

# PARTIE 6 — Prototype et démonstration technique

## 6.1 Prototype réalisé

Deux livrables fonctionnels : **(A) Agent Radar** — un workflow **n8n** connecté à l'**API
Pappers** qui détecte des PME rentables à dirigeant âgé et calcule un **score de succession**
(prototype de type *Workflow automatisé + Agent IA*, réellement exécutable) ; **(C) « Pérennis
Deal Room »** — maquette d'app no-code (pipeline kanban, fiche cible, guichet de conformité).

## 6.2 Documentation technique

- **Architecture :** voir schéma 3.2 (agents orchestrés par n8n, données via MCP/API).
- **Outils & justification :** n8n (orchestration, UE), Pappers (données FR), Claude
  (rédaction/multilingue), OpenSanctions (conformité), Base44 (UI).
- **Prompts clés documentés :** prompt de construction Base44 (cadre BASE) ; prompts système
  des agents **Radar, Matching, Communication, Conformité** (fichier
  `07-Prototype-prompts-et-demo.md`). Le code de
  scoring du Radar est dans `prototype/radar-pappers-n8n.json`.
- **Captures d'écran du prototype en fonctionnement** *(dossier `captures/`, Annexe C)* :
  cockpit Deal Room (`02`), démo auto-jouée (`03`), tableau de bord de pilotage (`01`) et
  quatre slides clés du pitch (`04`–`07`).
- **Difficultés & solutions :** doc Pappers protégée (403) → paramètres validés via
  dépôts open-source ; finances parfois absentes → filtres `resultat_min`/`chiffre_affaires_min`
  garantissant la rentabilité + code défensif.
- **Limites & améliorations :** enrichissement financier par SIREN, passage en Schedule
  Trigger (Radar quotidien), écriture directe dans un CRM, agent Matching.

## 6.3 Vidéo de démonstration (3–5 min)

Script prêt à enregistrer (`10-Script-video-demo-FR.md`) : problème → pont → démo Deal Room (fiche cible →
matching → **guichet de conformité** → pipeline) → conformité & humain dans la boucle →
conclusion. Une **démo auto-jouée sous-titrée** existe (`prototype/perennis-demo.html`).

---

# PARTIE 7 — Pitch final et recommandations

## 7.1 Pitch Deck (15 slides)

Titre · Problème · Marché · Insight (3×) · Solution · Mon avantage · Sept agents IA ·
Technologie/MCP · ROI de l'IA · Modèle économique · **Équipe & gouvernance** · Conformité
(avantage) · **Prototype en action** · Feuille de route · Vision.

*Livrable : `livrables/Perennis-Pitch-Deck-FR.pptx` (PowerPoint, 16:9). Une version web
navigable au clavier existe également : `prototype/perennis-pitch.html`.*

## 7.2 Recommandations de déploiement

- **Feuille de route 6–12 mois :** MVP buy-side (2–3 acheteurs + Radar) → 1ʳᵉ transaction →
  base sell-side.
- **Facteurs clés de succès :** conformité irréprochable, réseau d'acheteurs actif, réseau de
  partenaires (notaires/avocats/banques), confiance des cédants.
- **Conduite du changement :** formation de l'équipe (prompt engineering, n8n, LCB-FT),
  positionnement de l'IA comme **assistant** (pas remplaçant), documentation vivante.
- **Indicateurs post-déploiement :** volume de transactions, cycle moyen, taux de conversion
  mandat→closing, satisfaction cédant/repreneur, **0 incident de conformité**.

---

# ANNEXES

- **Annexe A — Brief client (1 p.) :** commanditaire, mission (une phrase), contraintes,
  livrables (voir 2.0).
- **Annexe B — Personas :** Jean-Pierre (cédant), Timur (repreneur), Léa (analyste).
- **Annexe C — Captures d'écran** *(dossier `captures/`)* :
  `01-tableau-de-bord-pilotage.png` — tableau de bord de pilotage projet (Partie 5.4) ·
  `02-deal-room-cockpit.png` — cockpit Deal Room : bandeau de KPI et pipeline des
  transmissions de *Sourcé* à *Transition*, avec l'étape **Conformité** ·
  `03-demo-auto-jouee.png` — démo auto-jouée sous-titrée ·
  `04` à `07` — slides clés du pitch (titre, solution, sept agents IA, conformité).
- **Annexe D — Prototype technique :** `prototype/radar-pappers-n8n.json` (agent Radar,
  workflow n8n exécutable) et `prototype/radar-vers-deal-room-n8n.json` (chaînage vers la
  Deal Room) ; prompts des agents documentés dans `07-Prototype-prompts-et-demo.md`.
- **Annexe E — Sources :** BPCE L'Observatoire · Bpifrance Le Lab · DGE · CRA · Banque de
  France · KfW · Institut Sapiens · EthosData/IMAA (IA en M&A) · Cyndx/Sourcescrub ·
  Freshfields (filtrage des IDE).

---

*Ce dossier valide les blocs BC01 et BC04 du RNCP 40247 — formation AI for Business, PSTB.*
