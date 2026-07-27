# 🛰️ Agent Radar — mise en place dans n8n avec une clé Pappers

Workflow prêt à l'emploi : **`prototype/radar-pappers-n8n.json`** — il s'importe en un
seul fichier. L'agent interroge l'API Pappers pour trouver des entreprises rentables
dont le dirigeant vieillit, et calcule un **score de succession (0 à 100)**.

---

## Étape 1 — Lancer n8n (au choix)

- **Le plus simple, en local et gratuit :** dans le Terminal, exécuter
  ```
  npx n8n
  ```
  L'interface s'ouvre sur `http://localhost:5678`. *(Node.js est requis ; à défaut,
  l'installer depuis nodejs.org.)*
- **Ou dans le cloud :** créer un compte sur **n8n.io** → Cloud (un essai gratuit existe).
- **Ou n8n Desktop** — l'application pour Mac.

## Étape 2 — Obtenir une clé API Pappers

1. Se rendre sur **pappers.fr** → rubrique **API** → créer un compte.
2. Récupérer la **clé API** (un palier gratuit avec quota de crédits permet de tester).
3. Copier la clé.

## Étape 3 — Importer le workflow

Dans n8n : **⋯ (menu) → Import from File** → sélectionner `radar-pappers-n8n.json`.
Quatre nœuds apparaissent : une note, « Lancer Radar », « Pappers · Recherche » et
« Score de succession ».

## Étape 4 — Renseigner la clé (credential)

1. Dans le menu de gauche : **Credentials → New → « Header Auth »**.
2. Remplir :
   - **Name (nom de l'en-tête) :** `api-key`
   - **Value :** votre clé Pappers
3. Enregistrer.
4. Ouvrir le nœud **« Pappers · Recherche »** et sélectionner le credential `api-key`
   qui vient d'être créé. *(Il est normal que le nœud demande de choisir un credential
   après l'import.)*

## Étape 5 — Ajuster les filtres (facultatif)

Dans le nœud **« Pappers · Recherche »**, section *Query Parameters*, les valeurs
suivantes sont déjà en place :

| Paramètre | Valeur | Signification |
|---|---|---|
| `chiffre_affaires_min` | 1000000 | chiffre d'affaires à partir de 1 M€ |
| `resultat_min` | 50000 | résultat positif → l'entreprise est **rentable** |
| `age_dirigeant_min` | 60 | dirigeant proche de la retraite |
| `entreprise_cessee` | false | uniquement les entreprises en activité |
| `par_page` | 20 | nombre de résultats retournés |

D'autres paramètres peuvent être ajoutés (bouton *Add Parameter*) :

- `code_naf` — le secteur d'activité (par exemple `25.62B`) ;
- `departement` — le département (par exemple `69` pour le Rhône) ;
- `code_postal`, `region`.

## Étape 6 — Exécuter

Cliquer sur **Execute Workflow**. Le nœud « Score de succession » affiche la liste des
entreprises, triée par score décroissant :

```
score_succession · nom · siren · dirigeant_age · chiffre_affaires · resultat · lien_pappers
```

---

## 🧮 Calcul du score de succession

- Âge du dirigeant : 70 ans et plus → +50 · 65 à 69 → +42 · 60 à 64 → +32 · 55 à 59 → +20
- Résultat positif → +20
- Chiffre d'affaires ≥ 2 M€ → +12 · ≥ 1 M€ → +8
- Dirigeant unique âgé de 60 ans ou plus (pas de successeur apparent) → +10
- Le score est plafonné à 100.

## ⚠️ En cas d'erreur

- **401 / 403** → clé incorrecte, ou credential non sélectionné (étape 4).
- **Aucun résultat** → assouplir les filtres (baisser `chiffre_affaires_min` ou
  `age_dirigeant_min`).
- **Données financières incomplètes** → la recherche Pappers ne renvoie pas toujours le
  chiffre d'affaires et le résultat pour chaque entreprise ; les filtres garantissent
  néanmoins la rentabilité. Pour des comptes complets, un nœud d'enrichissement sera
  ajouté ultérieurement (`GET /v2/entreprise?siren=…`).
- Attention au **quota de crédits** Pappers : chaque requête le consomme.

## ▶️ Évolutions prévues de l'agent

- Remplacer le déclencheur par un **Schedule Trigger** → le Radar tourne alors chaque jour
  de façon autonome.
- Ajouter un nœud **Airtable ou Google Sheets** → écrire les cibles trouvées directement
  dans le CRM du pipeline.
- Ajouter un nœud **Claude** → rédiger une courte thèse d'investissement pour chaque cible.
- Puis développer l'agent **Matching** (rapprochement avec les repreneurs) et l'agent
  **Conformité** (OpenSanctions).
