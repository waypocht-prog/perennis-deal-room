# 💰 Capstone · Partie 4 — Business case, ROI et KPI

**Projet :** Pérennis. Partie 4 du dossier — cadrage, modèle économique, ROI et KPI.
Hypothèse cible : environ **50 M€ par an** de volume cumulé de transactions accompagnées.

---

## 🎯 Périmètre

- **Inclus :** sourcing des cibles, valorisation, appariement acheteur/vendeur,
  accompagnement de la transaction de A à Z, management de transition. Un humain valide
  chaque étape clé.
- **Exclu :** la clôture automatisée d'une opération sans intervention humaine ; la
  signature juridique (qui relève du notaire ou de l'avocat) ; toute garantie de
  performance de l'entreprise après la cession.

---

## 💶 Modèle de revenus (trois sources)

1. **Honoraires de succès (success fee)** — un pourcentage du montant de la transaction,
   selon une formule de type Lehman (taux plus élevé sur les petites opérations). Pour
   des deals de 2 à 10 M€, la moyenne retenue est d'environ **4 %**.
2. **Honoraires de mandat (retainer)** — une rémunération mensuelle pour un mandat actif
   (recherche pour un repreneur ou préparation d'un cédant), soit environ **4 000 €/mois**
   par mandat.
3. **Management de transition** — la mise à disposition d'un dirigeant de transition sur
   la période charnière ; la contribution nette pour le cabinet est d'environ
   **50 000 € par an** et par mandat.

> Ce modèle est classique en M&A boutique : le success fee porte l'essentiel du revenu,
> le retainer couvre les charges courantes, et le management de transition constitue
> une ligne complémentaire distinctive.

---

## 📊 ROI n° 1 — le gain d'efficacité apporté par l'IA

La valeur opérationnelle principale de l'IA réside dans l'**effet de levier sur le
sourcing** : une petite équipe traite un volume de cibles bien supérieur.

| Indicateur | ❌ Manuel (courtier classique) | ✅ Avec les agents IA de Pérennis |
|---|---|---|
| Cibles qualifiées par analyste et par mois | ~40 | ~150 |
| Temps par cible (sourcing + premier filtrage) | ~3 à 4 heures | ~30 à 40 minutes (l'agent prépare, l'humain vérifie) |
| Coût d'une cible qualifiée | ≈ 125 € | ≈ 40 € |

> 📉 **Débit multiplié par 3,7 ; coût par cible réduit de 65 %.** C'est exactement le
> propos de « AI for Business » : le même collaborateur produit trois fois plus de
> pipeline qualifié, donc davantage d'opérations se concluent **à taille d'équipe
> constante** — c'est la scalabilité.

---

## 📈 ROI n° 2 — l'économie de l'entreprise (compte de résultat)

### Régime cible (année 2-3, volume d'environ 50 M€/an)

**Produits :**

- Honoraires de succès : 50 M€ × 4 % = **2 000 000 €**
- Retainers : 6 mandats actifs × 4 000 € × 12 mois = **288 000 €**
- Management de transition : environ 4 mandats × 50 000 € = **200 000 €**
- **Total des produits ≈ 2 490 000 € par an.**

**Charges :**

- Équipe (le fondateur et trois collaborateurs : analyste, deal manager, conformité
  à temps partiel) ≈ **350 000 €**
- Technologies et données (Base44, n8n, API Claude, Pappers puis Orbis, VDR) ≈ **60 000 €**
- Conformité et conseil juridique externes (KYC/LCB-FT, transactions) ≈ **60 000 €**
- Développement commercial, déplacements, marketing relationnel ≈ **80 000 €**
- Bureau et administration ≈ **50 000 €**
- **Total des charges ≈ 600 000 € par an.**

**📊 Résultat net en régime cible ≈ 1 890 000 € par an** (marge d'environ 76 % ; le conseil
M&A est fortement margé une fois les opérations conclues).

### Année 1 (montée en charge — le décalage des deals, dit franchement)

- Volume d'environ 15 M€ → honoraires de succès ~600 000 € et retainers ~150 000 €,
  soit environ **750 000 € de produits**.
- Charges (équipe plus réduite) ≈ **450 000 €**.
- Investissements de démarrage non récurrents (construction de la plateforme, structure
  juridique, cadre de conformité, premiers abonnements aux données) ≈ **120 000 €**.
- **Année 1 ≈ +180 000 € avant investissement ; le retour sur l'investissement initial
  intervient dans le courant de l'année 1.**

> ⚠️ **En toute honnêteté :** le revenu de success fee est irrégulier — une opération se
> conclut en 6 à 12 mois, ce qui rend l'année 1 heurtée. Le retainer et le management de
> transition lissent la trésorerie. Ces chiffres sont des hypothèses prudentes, à valider
> au pilote au moyen des KPI ci-dessous.

---

## 📊 KPI — les indicateurs de succès

| KPI | Cible |
|---|---|
| Cibles qualifiées par mois et par analyste | ≥ 150 (3 à 4 fois le manuel) |
| Coût d'une cible qualifiée | −65 % |
| Mandats actifs (buy-side et sell-side) | ≥ 6 |
| Durée moyenne d'une opération | < 6 mois (contre plus de 12 sur le marché) |
| Volume de transactions accompagnées | → 50 M€ par an |
| Mandats de management de transition réussis | ≥ 80 % de propriétaires satisfaits |
| Incidents de conformité (KYC / LCB-FT / sanctions) | **0** — KPI critique |

---

## 🚦 Porte de décision

L'élargissement de l'équipe et le passage à la phase 2 (plateforme complète) ne seront
engagés **que si** le pilote atteint : un pipeline d'au moins 100 cibles qualifiées par
mois, au moins une opération conclue (ou deux à un stade avancé), une durée d'opération
inférieure à 6 mois, et **zéro incident de conformité**.

---

## ✅ Suite

- Partie 5 — plan de pilotage (méthode Agile, équipe, sprints, tableau de bord) et
  **bloc conformité**, qui constitue l'atout maître du projet.
- Partie 6 — prototype et maquette (prompt Base44) ainsi que le script de la vidéo de
  démonstration.
- Partie 7 — pitch et recommandations.
