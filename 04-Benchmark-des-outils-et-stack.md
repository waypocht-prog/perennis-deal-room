# 🛠️ Capstone · Partie 3 — Benchmark des outils et choix de la stack

**Projet :** Pérennis. Partie 3 du dossier — comparaison des solutions IA et no-code,
puis sélection.

La comparaison est menée couche par couche : où construire l'interface, avec quoi
orchestrer les agents, quel LLM retenir, où trouver les données d'entreprises, comment
couvrir la conformité. Critères retenus : rapidité, coût, qualité des résultats,
hébergement des données dans l'UE (RGPD) et **portabilité — MCP, sans vendor lock-in**.

---

## 🧱 Couche 1 — Interface / tableau de bord CRM

| Outil | Avantages | Limites | Verdict |
|---|---|---|---|
| **Base44** | construit l'application à partir d'un prompt, UI intégrée, très rapide | moins de contrôle sur la logique | 🥇 **retenu pour le prototype** |
| Lovable / Bubble | plus souples, plus soignés | plus longs à assembler | solution de repli |
| CRM du marché (Salesforce) | puissant | coûteux, lourd, surdimensionné | écarté |

## 🔗 Couche 2 — Orchestration des agents

| Outil | Avantages | Limites | Verdict |
|---|---|---|---|
| **n8n** | chaînes de traitement puissantes, agents IA natifs, auto-hébergeable dans l'UE (RGPD) | demande du paramétrage | 🥇 **orchestrateur retenu** |
| Zapier / Make | connexions simples | insuffisants pour la logique d'agents complexes | écartés |
| Développement sur mesure | contrôle maximal | long, coûteux, perd l'avantage du no-code | plus tard, à l'échelle |

## 🧠 Couche 3 — Moteur (LLM)

| Outil | Avantages | Limites | Verdict |
|---|---|---|---|
| **Claude (Sonnet / Opus)** | multilinguisme solide (RU/AR/FR/EN), analyse documentaire, justesse du ton | coût au volume | 🥇 **moteur retenu** |
| ChatGPT (GPT-5.x) | performant, largement connu | — | option de repli |
| Modèles ouverts (Mistral, Llama) | données dans l'UE, coût faible | moins fins sur les nuances | repli pour les traitements sensibles |

## 🗂️ Couche 4 — Données d'entreprises (le cœur de l'agent Radar)

| Source | Apport | Verdict |
|---|---|---|
| **Pappers** | entreprises françaises : dirigeants, âge, comptes, procédures — API et palier gratuit | 🥇 **point de départ (France)** |
| Infogreffe / BODACC / INSEE SIRENE | registres officiels, publications, événements juridiques | 🥇 complètent Pappers |
| **Orbis / Bureau van Dijk** | couverture paneuropéenne, données financières approfondies | 🥈 phase d'échelle (payant) |
| Societe.com | aperçu rapide | solution de repli |

## 🛡️ Couche 5 — Conformité (KYC / LCB-FT / sanctions)

| Source | Apport | Verdict |
|---|---|---|
| **OpenSanctions** | listes de sanctions et de PEP (ONU, OFAC, UE, Royaume-Uni), données ouvertes, API | 🥇 **criblage retenu** |
| Sanction Scanner / ComplyAdvantage | KYC/LCB-FT commercial, plus approfondi | 🥈 au pilote et à l'échelle |

## 🧰 Couche 6 — Outils complémentaires (via MCP)

CRM acheteurs : **HubSpot / Airtable** · messagerie : **Gmail / Outlook** · data room :
**Google Drive / Notion / VDR** · agenda : **Google Calendar** · équipe : **Slack** ·
veille web : **recherche et extraction web** · sourcing de contacts :
**LinkedIn Sales Navigator** (sous réserve des conditions d'utilisation).

---

## ✅ Stack retenue

> **Base44** (interface) + **n8n** (orchestration, auto-hébergée dans l'UE) + **Claude**
> (moteur) + **Pappers / Infogreffe / BODACC** (données françaises, puis Orbis pour l'UE)
> + **OpenSanctions** (conformité) — le tout relié par des **connecteurs MCP**.

**Justification devant le jury :**

- **No-code et modèles standards** = rapide, économique, compatible avec un budget d'amorçage.
- **MCP = portabilité sans vendor lock-in** : le LLM ou la source de données peuvent être
  remplacés sans réécrire le système, et les données peuvent rester dans l'UE, ce qui
  réduit le risque RGPD.
- **Montée en charge progressive des coûts :** au démarrage, paliers gratuits ou peu
  coûteux (Pappers, OpenSanctions, Airtable) ; Orbis et une VDR professionnelle
  n'interviennent qu'en phase d'échelle.
