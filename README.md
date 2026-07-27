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
| `livrables/Dossier-Capstone-Perennis.pdf` | Export PDF du dossier, prêt à déposer |
| `prototype/perennis-deal-room.html` | Maquette du cockpit M&A |
| `prototype/perennis-pitch.html` | Pitch deck (13 slides) |
| `prototype/perennis-demo.html` | Démo auto-jouée sous-titrée |
| `prototype/radar-pappers-n8n.json` | **Agent Radar** — workflow n8n (API Pappers) |
| `prototype/radar-vers-deal-room-n8n.json` | Chaînage Radar → Deal Room (Base44) |

### Notes de travail

| Fichier | Sujet |
|---|---|
| `01-Бриф-и-Veille-рынка.md` | Brief client et veille de marché |
| `02-ИИ-архитектура-агенты-и-MCP.md` | Architecture IA — 7 agents et MCP |
| `03-Персоны-User-Journey-и-идеация.md` | Personas, user journey, idéation |
| `04-Бенчмарк-инструментов-и-стек.md` | Benchmark des outils et choix de stack |
| `05-Business-Case-ROI-и-KPI.md` | Business case, ROI et KPI |
| `06-План-реализации-атрибуты-бизнеса-и-комплаенс.md` | Plan de réalisation et conformité |
| `07-Прототип-промпты-и-демо.md` | Prompts du prototype et démo |
| `08-Питч-и-рекомендации.md` | Pitch et recommandations |
| `09-Préparation-soutenance-FR.md` | **Préparation de la soutenance** |
| `10-Script-video-demo-FR.md` | Script de la vidéo de démonstration |
| `11-Agent-Radar-n8n-инструкция.md` | Mode d'emploi de l'agent Radar |
| `12-Partie5-Pilotage-projet-Agile-FR.md` | Partie 5 — pilotage de projet Agile |
| `13-Base44-Deal-Room-prompt.md` | Prompt de génération de la Deal Room |
| `14-Radar-vers-Base44-connexion.md` | Connexion agent Radar → Base44 |

### Référence

| Fichier | Description |
|---|---|
| `reference/Требования-курса-к-Capstone.md` | Cahier des charges officiel du Capstone (PSTB) |

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
