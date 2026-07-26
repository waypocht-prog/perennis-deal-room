# Pérennis — Deal Room

**Plateforme d'IA et conseil M&A pour la transmission d'entreprises en Europe.**
Projet Capstone — AI for Business (PSTB). *Valide les blocs BC01 et BC04 du RNCP 40247.*

> Pérennis détecte, valorise et met en correspondance les PME rentables à céder (dirigeants
> sans successeur) avec des acheteurs vérifiés de la CEI et du Moyen-Orient — via des agents
> d'IA, un guichet de conformité (KYC/AML, sanctions) et l'humain dans la boucle.

## 📦 Contenu du dépôt

| Fichier | Description |
|---|---|
| `DOSSIER-CAPSTONE-FR.md` | Dossier complet (7 parties) |
| `DOSSIER-CAPSTONE-FR-imprimable.html` | Version imprimable → PDF |
| `prototype/perennis-deal-room.html` | Maquette du cockpit M&A |
| `prototype/perennis-pitch.html` | Pitch deck (13 slides) |
| `prototype/perennis-demo.html` | Démo auto-jouée sous-titrée |
| `prototype/radar-pappers-n8n.json` | **Agent Radar** — workflow n8n (API Pappers) |
| `01…11-*.md` | Notes de travail (7 parties, architecture, agents, soutenance) |

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

## ⚖️ Conformité

RGPD · LCB-FT (KYC/AML) · criblage sanctions & PEP · filtrage des IDE (UE) · EU AI Act.
Aucune donnée personnelle ni clé secrète n'est publiée dans ce dépôt.

---

*Auteur : Abdul Gueny Djeirkhanov — Cohorte FR_AI_BIZ, Campus France.*
