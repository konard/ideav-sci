# Целевые издания

Основная цель — **Journal of Systems and Software** (Elsevier).
В таблице ниже — приоритезированный список с альтернативами на случай
отказа или несоответствия скоупа.

## Основной таргет

### Journal of Systems and Software (JSS)

* Издатель: **Elsevier**.
* Индексация: **Scopus Q1**, Web of Science (SCIE).
* Формат: full‑length research (≤ 36 страниц single‑column / 18 двух‑колоночных),
  Applied Research Reports, Practitioner Insights (≤ 4 стр., первый автор из
  индустрии), New Ideas and Trends Papers (NITP), систематические обзоры,
  репликации.
* Обязательно: Abstract ≤ 250 слов, 3–5 Highlights, ключевые слова (1–7),
  Author Contributions (CRediT), Data Availability Statement, депозит данных
  и кода в публичный репозиторий.
* Этический режим: декларация использования GenAI; никаких GenAI‑сгенерированных
  изображений; single‑blind review.
* Open Access: опциональный (через APC), либо subscription + Share Link.
* Pre‑print: разрешён, рекомендуется SSRN.
* Submission portal: Editorial Manager.

Почему подходит нам:

* Скоуп явно включает «системы и ПО», что покрывает базу данных + платформу.
* Принимаются NITP — хорошая запасная подача для «New Ideas» с
  предварительными результатами.
* Поддержка систематических обзоров — можно отдельной работой опубликовать
  результат этапа 1.
* JSS в последние годы **целенаправленно публикует работы по
  codeless / low‑code / model‑driven engineering** (источник: фоновая заметка
  [`CoAuthors.md`](CoAuthors.md); пример — статья J. Grundy 2026 г. о
  сравнении традиционного и LLM‑основанного low‑code‑программирования). Это
  означает, что наша тема не «выпадает из скоупа» — наоборот, продолжает
  активную для журнала линию.
* Список ключевых JSS‑авторов в смежных темах (Grundy, Holtmann, Ajimati,
  Paige, Deckers & Lago, Moreno‑Lumbreras) — см.
  [`PRIOR-ART.md`](PRIOR-ART.md), §3a. Этот список — кандидаты в
  *Suggested Reviewers* в Editorial Manager и опорные точки раздела
  Related Work.

## Запасные Q1‑журналы (Elsevier / Springer / IEEE / ACM)

| Журнал | Издатель | Профиль | Когда выбирать |
|--------|----------|--------|---------------|
| **Information Systems** | Elsevier | Базы данных, информационные системы | Если ревью JSS сочтёт работу слишком «db‑heavy». |
| **Information and Software Technology (IST)** | Elsevier | Software engineering, эмпирика | Близкий аналог JSS, удобный fallback. |
| **Empirical Software Engineering (EMSE)** | Springer | Эмпирические исследования | Если усилим статистическую часть. |
| **Data & Knowledge Engineering (DKE)** | Elsevier | Моделирование данных | Хорошо ложится на формализацию модели. |
| **The VLDB Journal** | Springer | СУБД, performance | Если бенчмарки станут основным вкладом. |
| **ACM Transactions on Database Systems (TODS)** | ACM | Фундаментальная теория БД | Долгий цикл, но высокий престиж. |
| **Software: Practice and Experience** | Wiley | Инженерный опыт реальных систем | Удобно для «case study Интеграма». |
| **IEEE Transactions on Knowledge and Data Engineering (TKDE)** | IEEE | Знания + данные | Если усилим knowledge‑модель. |

## Конференции‑альтернативы (если предпочтём conference‑first)

* **VLDB** (industry / research track) — для эмпирических работ с
  сильными бенчмарками.
* **ACM SIGMOD** — теория и индустрия БД.
* **IEEE ICDE** — Data Engineering, проще принимает industry‑case‑studies.
* **EDBT** — европейская площадка, более лояльный цикл.
* **ICSE / ESEC‑FSE** (industry track) — если статья про инженерный опыт
  платформы Интеграм.

## Локальные журналы для русскоязычной аудитории (промежуточные публикации)

* **Программирование** (РАН), Q2/Q3 — для теоретической части.
* **Программные продукты и системы** — для case study.
* Habr (научно‑популярная публикация) — уже частично сделано; полезно как
  предварительная апробация перед научной подачей.

## Декомпозиция: одна тема → несколько публикаций

Чтобы не «терять» материал в одной статье, разумная декомпозиция:

1. **Systematic Mapping Study** по EAV‑подобным платформам → IST/EMSE.
2. **Formal Model + Reference Implementation** (IDEAV/Интеграм) → JSS.
3. **Empirical Study at Scale** (31B records, etc.) → VLDB Journal / DKE.
4. **Industry Case Study** → Software: Practice and Experience.

Это даёт три‑четыре статьи из одного исследовательского ядра без
self‑plagiarism, если каждая фокусируется на собственном исследовательском
вопросе и явно ссылается на остальные.
