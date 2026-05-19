# sci

Материалы и план подготовки научной публикации по модели **IDEAV** и
конструктору **Интеграм** (Integram) — варианту обобщённой Entity–Attribute–Value
(EAV) модели с устранением классических проблем масштабируемости (партиционирование
по диапазонам идентификаторов, индексация, кортежи фиксированной арности).

Цель — опубликоваться в **Journal of Systems and Software** (Elsevier, Scopus Q1)
или в одном из альтернативных Q1‑изданий из списка целевых журналов.

## Содержание

| Документ | Назначение |
|----------|------------|
| [`docs/PLAN.md`](docs/PLAN.md) | Поэтапный план работы до подачи рукописи |
| [`docs/PRIOR-ART.md`](docs/PRIOR-ART.md) | Обзор предшественников и сравнение с IDEAV/Интеграмом |
| [`docs/TARGET-VENUES.md`](docs/TARGET-VENUES.md) | Целевые журналы и конференции с критериями |
| [`docs/PAPER-OUTLINE.md`](docs/PAPER-OUTLINE.md) | Скелет рукописи под требования JSS |
| [`docs/CHECKLIST.md`](docs/CHECKLIST.md) | Чек‑лист готовности к подаче |

### Предыстория (фоновые заметки, послужившие источником материала)

Эти файлы — исходные неструктурированные заметки, которые подкармливают
основные документы выше. Они оставлены в репозитории как первичные источники
тезисов; полезные выводы из них перенесены и систематизированы в
PRIOR‑ART, TARGET‑VENUES, PAPER‑OUTLINE и CHECKLIST с явными
обратными ссылками.

| Заметка | Что использовано в основной документации |
|---------|------------------------------------------|
| [`docs/Scopus.md`](docs/Scopus.md) | Тезисы новизны (3 пункта), патенты RU 2650032 C1 / US 11138174 B2, Future Work с LLM‑агентами — перенесены в `PAPER-OUTLINE.md` и `PRIOR-ART.md` §§4a, 5a. |
| [`docs/CoAuthors.md`](docs/CoAuthors.md) | Список ключевых авторов JSS (Grundy, Holtmann, Ajimati, Paige, Deckers & Lago, Moreno‑Lumbreras) — перенесён в `PRIOR-ART.md` §3a и упомянут в `TARGET-VENUES.md`. |
| [`docs/Patterns.md`](docs/Patterns.md) | «Bad CaRMa» + современные кейсы (WooCommerce, Kustomer 2023, Stack Overflow refactor: 10 c → 40 мс) — перенесены в `PRIOR-ART.md` §2. |
| [`docs/Select journal.md`](docs/Select%20journal.md) | Альтернативный «провокационный» title для bake‑off и desk‑rejection prevention checklist — перенесены в `PAPER-OUTLINE.md` и `CHECKLIST.md`. |

## Источники, послужившие отправной точкой

* Habr, «Предельная унификация», <https://habr.com/ru/articles/982120/>
* Habr, «Измерения предела возможностей», <https://habr.com/ru/articles/900308/>
* Red‑Gate Simple‑Talk, *Bad CaRMa*, <https://www.red-gate.com/simple-talk/opinion/opinion-pieces/bad-carma/>
* Три обсуждения в DeepSeek Chat — ссылки приведены в исходном issue
  (см. ideav/sci#1). На момент подготовки документа shared‑страницы DeepSeek
  возвращают HTTP 403 для внешних читателей, поэтому их выводы пересказываются
  по контексту, известному автору, и помечаются как `(внутренний источник)`.

Полный текст задачи: ideav/sci#1.
