# 🔗 Chaînage : agent Radar (n8n) → Deal Room (Base44)

Objectif : les entreprises détectées par **Radar** apparaissent automatiquement dans la
rubrique **Cibles** de l'application Deal Room.

**Schéma :** Radar (n8n) → Pappers → calcul du score → requête POST → **fonction backend
Base44** → création d'une fiche Cible.

Fichier du workflow : `prototype/radar-vers-deal-room-n8n.json`.

---

## ÉTAPE 1 — créer le point de réception dans Base44 (fonction backend)

Dans l'application Deal Room, coller ce prompt dans le champ de chat de gauche
(« Que souhaitez-vous créer ? ») puis cliquer sur **Construire** :

```
Crée une fonction backend (endpoint HTTP public) nommée "cibleEntrante" qui reçoit une
requête POST au format JSON et crée un enregistrement dans l'entité "Cible".

Sécurité : la fonction doit vérifier un en-tête "x-webhook-secret" et le comparer à un
secret d'application ; si le secret est absent ou incorrect, renvoyer 401. Utilise
asServiceRole pour créer l'enregistrement (pas d'utilisateur connecté).

Champs acceptés dans le corps JSON et mappés vers l'entité Cible :
nom_code, nom_reel, secteur, region, chiffre_affaires, ebitda, age_dirigeant,
nb_dirigeants, score_succession, valorisation_min, valorisation_max, source, etape.
Ignore tout champ inconnu (ex. "siren").

Réponds en JSON avec { "ok": true, "id": <id créé> } et le statut 200.

Ensuite, DONNE-MOI :
1) l'URL complète de l'endpoint de cette fonction,
2) où définir le secret "x-webhook-secret".
```

Base44 construit la fonction et **fournit l'URL** de l'endpoint (de la forme
`https://votre-app.base44.app/functions/cibleEntrante`) ainsi que l'emplacement où
définir le **secret**. Choisir un secret et l'enregistrer dans Base44.

> Conserver deux informations : l'**URL de la fonction** et le **secret**.
> ⚠️ Le secret ne doit jamais être écrit dans un fichier versionné.

---

## ÉTAPE 2 — configurer n8n

1. **Importer** `radar-vers-deal-room-n8n.json` (⋯ → Import from File).
2. Nœud **« Pappers · Recherche »** → sélectionner le credential contenant la clé Pappers.
3. Nœud **« Envoyer à Deal Room »** :
   - **URL** → coller l'URL de la fonction Base44 (à la place de
     `https://VOTRE-APP.base44.app/functions/cibleEntrante`).
   - En-tête **`x-webhook-secret`** → renseigner le secret défini dans Base44.
4. Cliquer sur **Execute Workflow**.

---

## ÉTAPE 3 — vérifier

- Ouvrir la Deal Room → rubrique **Cibles**. De nouvelles entreprises doivent y apparaître,
  portant le badge **« Sourcé par IA · Radar »**, le statut **Sourcé** et un
  **score de succession** calculé.
- Ouvrir l'une de ces fiches : elle affiche le chiffre d'affaires, l'EBITDA (approché par
  le résultat), l'âge du dirigeant et la fourchette de valorisation.

---

## 🧩 Correspondance des champs (Radar → Cible)

| Cible (Base44) | Origine (Radar / Pappers) |
|---|---|
| nom_code | généré automatiquement : « Projet Chêne », « Projet Sillon »… (confidentialité) |
| nom_reel | raison sociale issue de Pappers |
| secteur | code et libellé NAF |
| region | région ou ville |
| chiffre_affaires | chiffre d'affaires |
| ebitda | résultat (approximation) |
| age_dirigeant | âge du dirigeant |
| score_succession | calcul du Radar (0 à 100) |
| valorisation_min / max | environ résultat × 4 et × 6 (estimation grossière par multiple d'EBITDA) |
| source | « IA · Radar » |
| etape | « Sourcé » |

## ⚠️ Remarques

- Le **secret** protège le point de réception : sans lui, aucun tiers ne peut y envoyer
  de données.
- L'`ebitda` et la `valorisation` restent approximatifs — la recherche Pappers ne renvoie
  pas toujours l'EBITDA complet. Pour des chiffres exacts, un nœud d'enrichissement
  `GET /v2/entreprise?siren=…` sera ajouté ultérieurement.
- Le nœud « Envoyer » est configuré avec `continueOnFail` : si un enregistrement échoue,
  les autres sont tout de même transmis.
- C'est une **démonstration parlante devant le jury** : l'agent Radar alimente réellement
  le CRM de la Deal Room.

## ▶️ Évolutions

- Remplacer le déclencheur par un **Schedule Trigger** → le Radar alimente les Cibles
  chaque jour de façon autonome.
- Envoyer une notification Slack à chaque nouvelle cible ou nouveau repreneur.
