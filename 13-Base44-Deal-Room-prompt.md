# 🅱️ Base44 — construire la vraie app « Pérennis Deal Room »

> Prompt prêt à l'emploi pour construire une **véritable application** (avec base de
> données) dans Base44. Il se colle intégralement à la création d'un nouveau projet, et
> Base44 génère l'application. L'affinage se fait ensuite par le chat (« ajoute… »,
> « change la couleur… »). L'interface produite est en français.

---

## 📋 Prompt à coller dans Base44 (à copier intégralement)

```
Build a professional internal B2B web application called "Pérennis Deal Room" for a
cross-border M&A advisory specialized in business succession (transmission d'entreprise).
IMPORTANT: all UI text, labels and content must be in FRENCH.

CONTEXT / PROBLEM:
Aging European SME owners have no successor; their profitable companies risk disappearing.
There are 3x more sellers than buyers, so vetted buyers (from the CIS and Middle East) are
the scarce resource. The Pérennis team uses this app as their internal cockpit to run deals
end-to-end, with a strict compliance gate and a human validating every step.

DESIGN:
Sober, institutional, trustworthy (private-banking feel). Palette: deep navy (#152238) for
the sidebar and header, warm ivory/white surfaces, a single muted gold accent (#B08A3E).
Clean typography, dense but calm. Left sidebar navigation + a top bar with a confidentiality
banner.

DATA MODEL (create these entities with a database):
1) Cible (target company): nom_code (e.g. "Projet Chêne"), nom_reel (hidden until NDA),
   secteur, region, chiffre_affaires (number, €), ebitda (number, €), age_dirigeant (number),
   nb_dirigeants (number), score_succession (number 0-100), valorisation_min (€),
   valorisation_max (€), source ("IA · Radar" or "Manuel"), etape (pipeline stage).
2) Acheteur (buyer): nom_code (e.g. "Acheteur K-14"), origine (country), ticket_min (€),
   ticket_max (€), secteurs_cibles, appetit_risque, statut_kyc
   (one of: "En attente", "Cleared", "Vérification renforcée", "Bloqué").
3) Affaire (deal): links one Cible and one Acheteur, score_matching (%), etape, notes.
4) Controle_conformite: linked to an Acheteur, with statuses for kyc, origine_des_fonds,
   sanctions_pep, filtrage_ide, and a verdict ("Cleared", "EDD", "Bloqué").

PAGES / SECTIONS (left sidebar):
- Tableau de bord: a KPI strip — "Cibles qualifiées ce mois", "Mandats actifs",
  "Cycle moyen (mois)", "Volume 12 mois (M€)", "Incidents de conformité" (target 0).
- Pipeline: a KANBAN board of Affaires by etape, columns in this order:
  Sourcé → Qualifié → Matché → NDA → Due Diligence → Conformité → Négociation → Closing →
  Transition. Cards show nom_code, secteur, region, an EBITDA tag and a status pill. Allow
  drag-and-drop between columns.
  RULE: an Affaire cannot be moved past the "Conformité" column unless the linked Acheteur's
  compliance verdict is "Cleared" — otherwise show a blocking message.
- Cibles: a table + a detail view. Detail shows the score_succession as a progress meter
  (0-100), the AI valuation range (valorisation_min–valorisation_max), key facts (CA, EBITDA,
  âge du dirigeant, salariés), a "Sourcé par IA · Radar" badge, and a button
  "Générer le mémo de qualification".
- Acheteurs: cards showing origine, ticket range, secteurs, and a color-coded KYC status chip.
- Matching: suggested Cible↔Acheteur pairs with a match score (%) and a one-line rationale,
  plus a button "Préparer le teaser anonyme".
- Conformité: for a selected Acheteur, a checklist (KYC bénéficiaires, Origine des fonds,
  Sanctions & PEP, Filtrage des IDE) and a verdict badge (Cleared / EDD / Bloqué).
- Transition: assign an interim manager to closed deals with a duration (months).

GLOBAL ELEMENTS:
- A confidentiality banner at the top: "Confidentiel — teasers anonymisés uniquement ·
  accès sous NDA".
- A "Humain dans la boucle" badge and a note: "L'IA prépare — un humain valide chaque
  décision."
- Forms to create/edit a Cible and an Acheteur.

SEED DATA (create these example records so the app is populated for a demo):
Cibles:
- "Projet Chêne" — Composants métalliques de précision, Auvergne-Rhône-Alpes, CA 8000000,
  EBITDA 1200000, dirigeant 64 ans, score 82, valo 4800000–6000000, source "IA · Radar",
  étape "Matché".
- "Projet Sillon" — Agroalimentaire, Bretagne, EBITDA 900000, score 74, étape "Sourcé".
- "Projet Lavande" — Cosmétique naturelle, PACA, score 79, étape "Qualifié".
- "Projet Garonne" — Distribution B2B, étape "NDA".
- "Projet Vosges" — Menuiserie industrielle, étape "Due Diligence".
- "Projet Alizé" — étape "Conformité".
- "Projet Méridien" — Services aux entreprises, valo 5400000, étape "Négociation".
- "Projet Ardoise" — Matériaux de construction, étape "Closing".
- "Projet Cévennes" — étape "Transition".
Acheteurs:
- "Acheteur K-14" — origine Kazakhstan, ticket 3000000–7000000, secteurs Industrie,
  statut_kyc "Cleared".
- "Acheteur EAU-07" — origine Émirats arabes unis, ticket 5000000–10000000,
  statut_kyc "Vérification renforcée".
Affaire: "Projet Chêne" ↔ "Acheteur K-14", score_matching 94, étape "Matché".

END GOAL:
The Pérennis team runs more deals with a small team, safely and confidentially. Primary CTA
on a target: "Générer le mémo de qualification". Add autosave, clear status badges, and the
KPI strip on the dashboard.
```

---

## 🪜 Mode d'emploi, étape par étape

1. Se rendre sur **base44.com** et se connecter à son compte.
2. **Create new app / Nouveau projet** → coller l'intégralité du prompt ci-dessus et
   lancer la génération.
3. Patienter : Base44 construit l'application, la base de données, les pages et un jeu de
   données de démonstration.
4. **Affiner par le chat** (en français ou en anglais), par exemple :
   - « Rends la barre latérale bleu marine plus foncée et l'accent doré plus sobre. »
   - « Ajoute un filtre par secteur sur la page Cibles. »
   - « Sur le Pipeline, empêche de dépasser la colonne Conformité si le verdict n'est pas Cleared. »
5. Vérifier le bon fonctionnement du **Pipeline** (kanban), de la fiche **Cible** avec son score, et de la page **Conformité** avec son verdict.

## 📸 Pour le dossier
Prendre trois ou quatre captures d'écran de l'application terminée et les verser en **Annexe C** (vue d'ensemble, fiche cible avec son score, guichet de conformité). C'est le prototype correspondant à la **Partie 6, option C**.

## 🔌 Étape suivante (facultative)
L'**agent Radar (n8n)** peut ensuite être relié à cette application : Radar trouve les
entreprises dans Pappers et **les envoie comme nouvelles Cibles** dans Base44, via un
webhook. On obtient alors un ensemble vivant — le moteur et sa vitrine. La marche à suivre
figure dans le fichier `14`.
