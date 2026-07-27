# 🤖 Capstone · Architecture IA de Pérennis (agents, outils et MCP)

C'est le cœur du projet « AI for Business » : comment le système d'IA est construit —
quels agents, quelles données, quels accès via **MCP** (Model Context Protocol, le
standard qui relie les agents aux données et aux outils **sans vendor lock-in**).

Ce document alimente la Partie 3 (benchmark et choix de la stack) et la Partie 6
(prototype) du dossier.

---

## 🧭 Principe : une chaîne de traitement du deal, avec l'humain dans la boucle

Chaque agent correspond à une étape du cycle de vie d'une affaire. L'orchestrateur
(**n8n**) les relie en une chaîne continue. **Aucune étape n'est publiée ni envoyée au
client sans validation humaine** — c'est une exigence de confiance autant que de conformité.

```
[1] RADAR  →  [2] QUALIF & VALO  →  [3] MATCHING  →  [4] COMMUNICATION
                                                            │
[7] TRANSITION  ←  [6] CONFORMITÉ  ←  [5] DUE DILIGENCE  ←──┘
        (n8n orchestre l'ensemble ; un humain valide chaque décision)
```

---

## 🧩 Les sept agents

### 1. Agent « Radar » — détection des cibles (origination sell-side)

- **Mission :** rechercher en continu les signaux indiquant qu'une entreprise se retrouvera
  bientôt sans successeur.
- **Signaux :** dirigeant de 58 ans ou plus, absence d'héritier repreneur, finances saines,
  secteur, région, absence d'investissement récent ou de recrutement d'un successeur.
- **Outils et données (via MCP) :** registres d'entreprises (Pappers, Infogreffe, BODACC,
  INSEE SIRENE), recherche web (presse, annonces, actualité locale), LinkedIn (avec prudence
  au regard des conditions d'utilisation).
- **Sortie :** une liste de candidats classés par **score de succession**.

### 2. Agent « Qualification & Valorisation »

- **Mission :** écarter les cibles faibles et estimer une fourchette de valeur.
- **Logique :** multiples d'EBITDA par secteur complétés d'un DCF simplifié ; signaux
  vert / rouge.
- **Données (via MCP) :** comptes annuels (Pappers, Infogreffe, Orbis), multiples sectoriels.
- **Sortie :** une fiche cible — fourchette de valorisation, risques, thèse d'investissement.

### 3. Agent « Matching acheteur–vendeur »

- **Mission :** rapprocher le profil d'un repreneur (secteur, budget, géographie, appétence
  au risque) des cibles disponibles.
- **Données (via MCP) :** CRM acheteurs (HubSpot ou Airtable), fiches cibles issues de l'agent 2.
- **Sortie :** une short-list « cette cible ↔ ce repreneur », assortie de la justification
  du rapprochement.

### 4. Agent « Communication multilingue » — le pont des langues

- **Mission :** rédiger des messages personnalisés aux cédants (en français, avec le tact
  qu'impose un sujet sensible) et aux repreneurs (RU / AR / EN), dans le bon registre et
  en tenant compte du contexte culturel.
- **Données (via MCP) :** Gmail ou Outlook, modèles, CRM ; moteur : Claude, pour le ton
  et le multilinguisme.
- **Sortie :** des brouillons de courriers et de teasers anonymisés — relus et envoyés
  par un humain.

### 5. Agent « Due Diligence & Data Room »

- **Mission :** construire la checklist de due diligence, synthétiser les documents et
  faire remonter les risques juridiques, financiers et fiscaux.
- **Données (via MCP) :** data room sécurisée (Google Drive, Notion ou VDR dédiée),
  documents de la transaction.
- **Sortie :** une synthèse des risques, la liste des signaux d'alerte et les questions
  à poser au cédant.

### 6. Agent « Conformité KYC/AML & Sanctions » ⚠️ critique

- **Mission :** vérifier le repreneur et l'origine des fonds ; neutraliser le risque
  réglementaire.
- **Contrôles :** KYC (bénéficiaires effectifs), LCB-FT (origine des fonds), **criblage des
  sanctions de l'UE** et des personnes politiquement exposées, **filtrage des IDE** — le
  nouveau règlement européen, applicable depuis décembre 2025, vise le contournement des
  sanctions, l'opacité de la structure de détention et l'identification du bénéficiaire réel.
- **Données (via MCP) :** OpenSanctions et listes de sanctions et de PEP (ONU, OFAC, UE,
  Royaume-Uni), registres des bénéficiaires effectifs.
- **Sortie :** un rapport « pass / vigilance renforcée / stop » — un **guichet obligatoire**
  avant toute poursuite de l'opération.

### 7. Agent « Management de transition »

- **Mission :** sélectionner un dirigeant de transition adapté à l'entreprise pour la
  période charnière.
- **Données (via MCP) :** base de managers de transition (Airtable), profil de l'entreprise.
- **Sortie :** deux à trois candidats, accompagnés d'un plan d'intégration du nouveau
  propriétaire dans l'entreprise.

**Orchestrateur (n8n) :** déclenche la chaîne, tient les statuts à jour, notifie l'équipe
sur Slack et programme les rendez-vous dans Google Calendar. **Chaque étape clé est validée
par un humain.**

---

## 🛠️ Stack et accès (support du benchmark, Partie 3)

| Couche | Outil | Rôle |
|---|---|---|
| Interface / tableau de bord CRM | **Base44** (ou Lovable, Bubble) | pipeline des affaires, fiches, statuts |
| Orchestration / automatisation | **n8n** | relier les agents en une chaîne |
| Moteur de raisonnement et de génération | **Claude (Sonnet / Opus)** | multilinguisme RU/AR/FR/EN, analyse documentaire |
| Données d'entreprises françaises | **Pappers, Infogreffe, BODACC, INSEE SIRENE** | dirigeants, âge, comptes, procédures |
| Données européennes | **Orbis / Bureau van Dijk**, registres nationaux, Eurostat | couverture paneuropéenne |
| CRM acheteurs | **HubSpot / Airtable** | profils et pipeline |
| Messagerie et prise de contact | **Gmail / Outlook, Mailchimp** | contact avec les parties |
| Data room et documents | **Google Drive / Notion / VDR** | documents de transaction |
| Agenda | **Google Calendar** | rendez-vous |
| Équipe | **Slack** | collaboration et notifications |
| Veille web | **recherche et extraction web** | signaux, presse, veille |
| Sourcing de contacts | **LinkedIn Sales Navigator** | repreneurs et cédants (sous réserve des CGU) |
| Conformité | **OpenSanctions / API sanctions & PEP** | KYC, LCB-FT, sanctions |

> 💡 **Argument devant le jury :** tout est branché par des **connecteurs MCP**, et non en
> dur dans le code. D'où la **portabilité et l'absence de vendor lock-in** : le LLM comme
> la source de données peuvent être remplacés sans réécrire le système. C'est à la fois un
> avantage stratégique et une réduction du risque réglementaire, puisque les données
> peuvent rester hébergées dans l'UE.

---

## ⚖️ Principes intégrés dès la conception (gouvernance, Partie 5)

- **Humain dans la boucle :** les agents préparent, l'humain décide et signe.
- **Confidentialité M&A :** teasers anonymisés, accès sous NDA, données hébergées dans l'UE.
- **RGPD :** le système traite des données personnelles → base légale explicite,
  minimisation, durée de conservation, droits des personnes concernées.
- **KYC / LCB-FT / sanctions :** l'agent 6 constitue un guichet obligatoire ; sans « pass »,
  l'affaire ne progresse pas.
- **EU AI Act :** classifier le niveau de risque, assurer la transparence et la supervision
  humaine.

---

## 📎 Accès à ouvrir pour le prototype et le pilote

Pour construire le prototype puis, plus tard, le pilote, les accès suivants sont
nécessaires. Au stade du Capstone, seuls la démonstration et le concept sont présentés ;
les accès complets relèvent de la phase pilote.

- Un compte **Base44** (interface) et **n8n** (orchestration).
- Une clé **API Claude** (moteur).
- Une clé **API Pappers** (données d'entreprises françaises) — un palier gratuit existe
  pour la démonstration.
- **Airtable ou HubSpot** (CRM) — palier gratuit.
- **OpenSanctions** (sanctions et PEP) — données ouvertes disponibles.
- Plus tard, à l'échelle : **Orbis / Bureau van Dijk** (payant) et une **VDR** professionnelle.
