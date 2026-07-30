# Pérennis — Deal Room

**Plateforme d'IA et conseil M&A pour la transmission d'entreprises en Europe.**
Projet Capstone — AI for Business (PSTB). *Valide les blocs BC01 et BC04 du RNCP 40247.*

> Pérennis détecte, valorise et met en correspondance les PME rentables à céder (dirigeants
> sans successeur) avec des acheteurs vérifiés de la CEI et du Moyen-Orient — via des agents
> d'IA, un guichet de conformité (KYC/AML, sanctions) et l'humain dans la boucle.

## 📦 Contenu du dépôt

### Livrables — à rendre et à présenter

| Fichier | Description |
|---|---|
| `DOSSIER-CAPSTONE-FR.md` | **Dossier complet** (7 parties) — livrable principal |
| `DOSSIER-CAPSTONE-FR-imprimable.html` | Version mise en page → impression PDF |
| `livrables/Dossier-Capstone-Perennis.pdf` | **Export PDF du dossier**, captures incluses, prêt à déposer |
| `livrables/Perennis-Pitch-Deck-FR.pptx` | **Pitch deck PowerPoint** (15 slides) |
| `captures/` | Captures d'écran du prototype (Annexe C) |
| `prototype/perennis-deal-room.html` | Maquette du cockpit M&A |
| `prototype/perennis-pilotage.html` | **Tableau de bord de pilotage projet** (Partie 5.4) |
| `prototype/perennis-pitch.html` | Pitch deck, version web (13 slides) |
| `prototype/perennis-demo.html` | Démo auto-jouée sous-titrée |
| `prototype/radar-pappers-n8n.json` | **Agent Radar** — workflow n8n (API Pappers) |
| `prototype/radar-vers-deal-room-n8n.json` | Chaînage Radar → Deal Room (Base44) |

> ⏳ **Reste à produire :** la vidéo de démonstration (3–5 min) — script de tournage prêt
> dans `15-Script-video-prise-unique-FR.md`, support visuel dans `prototype/perennis-demo.html`.

### Notes de travail

| Fichier | Sujet |
|---|---|
| `01-Brief-et-veille-strategique.md` | Brief du commanditaire et veille stratégique |
| `02-Architecture-IA-agents-et-MCP.md` | Architecture IA — les sept agents et le MCP |
| `03-Personas-parcours-utilisateur-et-ideation.md` | Personas, parcours utilisateur, idéation |
| `04-Benchmark-des-outils-et-stack.md` | Benchmark des outils et choix de la stack |
| `05-Business-case-ROI-et-KPI.md` | Business case, ROI et KPI |
| `06-Plan-de-realisation-attributs-et-conformite.md` | Plan de réalisation, attributs et conformité |
| `07-Prototype-prompts-et-demo.md` | Prompts du prototype et script de démonstration |
| `08-Pitch-et-recommandations.md` | Pitch et recommandations |
| `09-Préparation-soutenance-FR.md` | **Préparation de la soutenance** — questions du jury |
| `10-Script-video-demo-FR.md` | Script de la vidéo de démonstration |
| `11-Agent-Radar-n8n-mode-emploi.md` | Mode d'emploi de l'agent Radar |
| `12-Partie5-Pilotage-projet-Agile-FR.md` | Partie 5 — pilotage de projet Agile |
| `13-Base44-Deal-Room-prompt.md` | Prompt de génération de la Deal Room |
| `14-Radar-vers-Base44-connexion.md` | Chaînage agent Radar → Base44 |
| `15-Script-video-prise-unique-FR.md` | **Script de tournage** — version prête à lire, une seule prise |
| `16-Questions-reponses-soutenance.md` | **Questions du jury et réponses** — 14 questions préparées |

### Référence

| Fichier | Description |
|---|---|
| `reference/Cahier-des-charges-Capstone-PSTB.md` | Cahier des charges officiel du Capstone (PSTB) |

## 🧠 Architecture IA

Sept agents orchestrés par **n8n**, reliés aux données via **MCP** :
Radar → Qualification & Valorisation → Matching → Communication → Due Diligence →
**Conformité (KYC/AML/sanctions)** → Management de transition.

## 🛠️ Stack

Base44 · n8n · Claude · API Pappers · OpenSanctions — hébergement UE, sans vendor lock-in.

## ▶️ Lancer l'agent Radar

1. Démarrer n8n (`npx n8n`) ou n8n Cloud.
2. **Import from File** → `prototype/radar-pappers-n8n.json`.
3. Créer un credential **Header Auth** (`api-key` = clé Pappers) et le sélectionner.
4. **Execute Workflow** → liste de cibles triées par *score de succession*.

> ⚠️ La clé API Pappers n'est **jamais** committée (voir `.gitignore`).

## 👀 Ouvrir les maquettes

Les trois maquettes sont des fichiers HTML autonomes : il suffit de les ouvrir
dans un navigateur, aucune installation n'est nécessaire.

## ⚖️ Conformité

RGPD · LCB-FT (KYC/AML) · criblage sanctions & PEP · filtrage des IDE (UE) · EU AI Act.
Aucune donnée personnelle ni clé secrète n'est publiée dans ce dépôt.

---

*Auteur : Abdul Gueny Djeirkhanov — Cohorte FR_AI_BIZ#236_FT, Campus France.*
