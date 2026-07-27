# 🔗 Связка: агент Radar (n8n) → Deal Room (Base44)

Цель: компании, которые находит **Radar**, автоматически появляются в разделе **Cibles**
приложения Deal Room.

**Схема:** Radar (n8n) → Pappers → расчёт score → POST-запрос → **backend-функция Base44**
→ создаёт карточку Cible.

Файл workflow: `prototype/radar-vers-deal-room-n8n.json`.

---

## ЭТАП 1 — создать точку приёма в Base44 (backend-функция)

В приложении Deal Room, в поле чата слева («Que souhaitez-vous créer ?»), вставь этот
промпт и нажми **Construire** :

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

Base44 построит функцию и **выдаст тебе URL** (что-то вроде
`https://ton-app.base44.app/functions/cibleEntrante`) и место, где задать **секрет**.
Придумай секрет (например `perennis-radar-2026`) и сохрани его в Base44.

> Запиши две вещи: **URL функции** и **секрет**.

---

## ЭТАП 2 — настроить n8n

1. **Импортируй** `radar-vers-deal-room-n8n.json` (⋯ → Import from File).
2. Узел **«Pappers · Recherche»** → выбери credential с ключом Pappers (как раньше).
3. Узел **«Envoyer à Deal Room»** :
   - **URL** → вставь URL функции из Base44 (вместо `https://VOTRE-APP.base44.app/functions/cibleEntrante`).
   - Заголовок **`x-webhook-secret`** → впиши свой секрет (тот же, что в Base44).
4. Нажми **Execute Workflow**.

---

## ЭТАП 3 — проверить

- Открой Deal Room → раздел **Cibles**. Там должны появиться новые компании со значком
  **«Sourcé par IA · Radar»**, статусом **Sourcé** и посчитанным **score de succession**.
- Открой любую новую карточку — увидишь CA, EBITDA (≈ résultat), возраст руководителя,
  диапазон оценки.

---

## 🧩 Как мапятся поля (Radar → Cible)
| Cible (Base44) | Откуда (Radar/Pappers) |
|---|---|
| nom_code | автогенерация: «Projet Chêne/Sillon/…» (конфиденциальность) |
| nom_reel | название компании из Pappers |
| secteur | код/название NAF |
| region | регион/город |
| chiffre_affaires | CA |
| ebitda | résultat (приближённо) |
| age_dirigeant | возраст руководителя |
| score_succession | расчёт Radar (0–100) |
| valorisation_min/max | ≈ résultat × 4 и × 6 (грубая оценка EBITDA-мультипликатором) |
| source | «IA · Radar» |
| etape | «Sourcé» |

## ⚠️ Заметки
- **Секрет** защищает точку приёма — без него посторонние не смогут слать данные.
- `ebitda` и `valorisation` — приближённые (у Pappers в поиске часто нет полного EBITDA);
  для точных цифр позже добавим узел-обогащение `GET /v2/entreprise?siren=…`.
- Узел «Envoyer» стоит с `continueOnFail` — если одна запись не прошла, остальные всё равно уйдут.
- Это **эффектная демонстрация для жюри**: «агент Radar реально наполняет CRM Deal Room».

## ▶️ Дальше
- Заменить триггер на **Schedule** → Radar пополняет Cibles каждый день сам.
- Отправлять покупателям/целям в Slack-уведомление (Base44 предлагал «Ajouter alertes Slack»).
