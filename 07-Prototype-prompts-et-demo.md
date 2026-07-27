# 🖥️ Capstone · Partie 6 — Prototype (Base44), prompts des agents et vidéo de démonstration

**Projet :** Pérennis. Partie 6 du dossier. On y trouve tout le nécessaire pour construire
le prototype — la **« Pérennis Deal Room »**, tableau de bord du pipeline des affaires —
et pour enregistrer la démonstration.

Le prototype ne montre pas un « générateur de texte » mais une véritable **chaîne de
traitement M&A** : cible → valorisation → repreneur → guichet de conformité →
accompagnement → management de transition, avec l'humain dans la boucle.

---

## 🅱️ Prompt Base44 (cadre BASE) — construire la Deal Room

*Les prompts sont rédigés en anglais : c'est la langue d'entrée la plus fiable pour ces
outils. Le résultat produit, lui, est en français.*

```
Build a professional B2B web app called "Pérennis Deal Room" for a cross-border M&A
advisory that helps aging European SME owners (no successor) sell their businesses to
vetted investors from the CIS and the Middle East. Sober, trustworthy, institutional
design (deep navy, warm ivory, a single gold accent), clean typography, dense but calm.

BE SPECIFIC:
The app is the internal cockpit for the Pérennis team to run deals end-to-end. Main
sections: (1) Pipeline — kanban of deals by stage; (2) Targets — companies for sale;
(3) Buyers — investor profiles; (4) Matching — suggested target↔buyer pairs;
(5) Compliance — KYC/AML/sanctions gate; (6) Transition — interim-manager mandates.

ADDRESS THE PROBLEM:
Today M&A sourcing is manual and slow (analysts spend hours in company registries),
one target in two never finds a buyer, and cross-border buyers face a language and trust
barrier. Pérennis uses AI agents to source and qualify targets, match them with buyers,
and enforce compliance — while a human approves every key step.

STRUCTURE THE WORKFLOW:
1. TARGETS: each Target card shows Company, sector, region, revenue & EBITDA, a
   "Succession Score" (0–100, likelihood the owner needs to transmit), an AI valuation
   RANGE (€), and status flags (green/amber/red). A "Sourced by AI · Radar" badge.
2. BUYERS: each Buyer card shows origin (e.g. Kazakhstan, UAE), ticket range (€), target
   sectors, risk appetite, and a KYC status chip (Pending / Cleared / Enhanced / Blocked).
3. MATCHING: a "Suggested matches" list pairs a Target with a Buyer and shows a short
   AI rationale ("sector fit, ticket fit, geography"). Button: "Prepare anonymous teaser".
4. PIPELINE (kanban): stages = Sourced → Qualified → Matched → NDA → Due Diligence →
   Compliance → Negotiation → Closing → Transition. Drag a deal between stages.
5. COMPLIANCE GATE: a deal CANNOT move past "Compliance" until the KYC/AML/sanctions
   check shows "Cleared". Show a compliance panel with checklist and a green/red verdict.
6. TRANSITION: for closed deals, assign an interim manager for a defined period, with a
   simple handover checklist.

ESTABLISH THE END GOAL:
Run more deals with a small team, safely and confidentially. Primary CTA on a Target:
"Generate qualification memo". Include across the app: a confidentiality banner
("Confidential — anonymized teasers only; access under NDA"), a human-in-the-loop rule
("AI drafts, a human approves every client-facing action"), autosave, and clear status
badges. Add a top-level KPI strip: qualified targets this month, active mandates,
average deal cycle time, deals volume (€), compliance incidents (target: 0).
```

---

## 🧠 Prompts système des agents clés (dans n8n / Claude)

### Agent « Radar » — détection des cibles

```
You are the sourcing analyst for "Pérennis", a cross-border M&A advisory focused on
European SME succession. Goal: find profitable SMEs whose owner is likely to transmit
soon and has no obvious successor.
USE ONLY verified data from official registries (Pappers, Infogreffe, BODACC, INSEE) and
reputable press. Never invent facts. For each candidate output:
- Company, sector, region, revenue, EBITDA (if available)
- Succession Score 0–100 with the 2–3 signals behind it (director age, no successor,
  financial health, no recent handover)
- A short neutral note and any red flags.
Rank by Succession Score. Flag anything uncertain as "to verify by a human".
```

### Agent « Matching » — rapprochement des deux parties

```
You match Pérennis targets with buyers. Inputs: a target card and a set of buyer profiles.
Output the top buyer matches with a one-line rationale each, scoring on: sector fit,
ticket/valuation fit, geography, risk appetite. NEVER propose a match if the buyer's KYC
status is "Blocked" or "Enhanced-pending". Confidentiality: refer to the target by its
anonymized codename, not its real name.
```

### Agent « Communication » — prise de contact multilingue, le pont des langues

```
You draft first-contact messages for Pérennis. Two audiences:
(1) SELLERS in FRENCH — respectful, discreet, never pushy; acknowledge that transmission
    is a sensitive, personal decision; emphasize confidentiality and continuity for staff.
(2) BUYERS in RUSSIAN, ARABIC or ENGLISH — clear, trustworthy; emphasize vetted targets,
    full A→Z support, transition management, and clean/compliant deals.
RULES: use only facts provided; anonymize the target until an NDA is signed; keep the
Pérennis voice (institutional, sincere, trustworthy). Output is a DRAFT for human review,
never sent automatically.
```

### Agent « Conformité » — guichet KYC / LCB-FT / sanctions

```
You are the compliance gate for Pérennis. For a given buyer, run a structured check:
KYC (beneficial owners), source of funds plausibility, sanctions & PEP screening
(UN/OFAC/EU/UK via OpenSanctions), and EU FDI-screening exposure (sensitive sector?
threshold?). Output a verdict: CLEARED / ENHANCED DUE DILIGENCE / BLOCKED, with the
reasons. If any sanctions/PEP hit or opaque ownership — do NOT clear; escalate to a human.
```

---

## 🎬 Script de la vidéo de démonstration (3 à 5 minutes)

1. **0:00–0:40 — Le problème.** « En Europe, des centaines de milliers d'entreprises
   rentables risquent de fermer : leurs dirigeants vieillissent et n'ont pas de successeur.
   Or les repreneurs disposant de capitaux sont trois fois moins nombreux. Voici Pérennis. »
2. **0:40–1:10 — L'idée du pont.** « Nous relions les cédants européens à des repreneurs
   vérifiés de la CEI et du Moyen-Orient — dans leur langue, avec un accompagnement complet. »
3. **1:10–3:00 — Démonstration de la Deal Room.** Montrer : une fiche cible avec son score
   de succession et sa valorisation (sourcée par l'agent Radar) → le Matching qui propose
   un repreneur → le **guichet de conformité** (KYC et sanctions) → le pipeline de
   l'affaire → l'affectation d'un manager de transition.
4. **3:00–4:00 — Conformité et humain dans la boucle.** Souligner qu'aucune affaire ne
   franchit l'étape sans un verdict « Cleared » : l'IA prépare, l'humain décide.
5. **4:00–4:40 — Conclusion.** « Plus rapide, plus sûr, plus propre. Nous sauvons
   l'entreprise, les emplois et le savoir-faire — et nous offrons aux capitaux une entrée
   légitime dans l'économie européenne. »

---

## ✅ Marche à suivre pour assembler le prototype

1. Base44 → créer l'application et coller le prompt BASE (Deal Room).
2. Connecter Claude et installer les prompts système des agents (Radar, Matching,
   Communication, Conformité).
3. *(Facultatif)* n8n : relier les agents, Pappers et OpenSanctions en une chaîne.
4. Alimenter avec deux ou trois cibles de démonstration et deux repreneurs, puis dérouler
   un cas complet.
5. Enregistrer l'écran (QuickTime) en suivant le script → la vidéo de démonstration.
   Prendre trois ou quatre captures d'écran.
