# Обзор предшественников: EAV, «гибкие» схемы и low‑code

Этот документ — стартовый каталог работ, относительно которых должна
позиционироваться публикация по IDEAV/Интеграму. Каждая запись содержит
краткое описание, домен, источник и роль для нашей статьи
(`позитивный baseline`, `негативный пример`, `смежная область`).

---

## 1. Классические реализации EAV в медицине

| Система | Описание | Источник | Роль |
|---------|----------|----------|------|
| Regenstrief EMR | Один из первых EMR, ввёл (Patient, Attribute, Timestamp, Value). | McDonald, 1970s; Wikipedia EAV | смежная область |
| HELP (LDS Hospital → 3M) | Клиническая БД, коммерциализированная 3M. | Warner et al. | смежная область |
| TMR (Stead & Hammond) | EAV для устойчивого хранения клинических данных. | Stead, Hammond | смежная область |
| Columbia‑Presbyterian system | Первая EAV‑надстройка над реляционным движком. | Friedman, Hripcsak | смежная область |
| TrialDB | Open‑source менеджмент клинических исследований; несколько EAV‑таблиц по типам. | Nadkarni et al. | смежная область |
| i2b2 | EAV‑data mart для биомедицинских исследований. | Murphy, Kohane | смежная область |
| SenseLab | Нейронаучные данные на EAV/CR. | Nadkarni, Marenco | смежная область |
| VistA / MUMPS | Медсеть VA США, иерархическая БД на MUMPS — функциональный аналог EAV. | US Dept. of Veterans Affairs | смежная область |
| Oracle Clinical, ClinTrial | Коммерческие платформы клинических исследований. | Oracle Health Sciences | смежная область |
| Epic «Flowsheets» | Конфигурируемые power‑user атрибуты. | Epic Systems | смежная область |
| Cerner subschema | EAV‑подсхема в коммерческом EHR. | Cerner / Oracle | смежная область |

---

## 2. Известные провалы и «анти‑паттерны»

| Случай | Что было сделано | Чем закончилось | Источник | Роль |
|--------|------------------|----------------|----------|------|
| **CaRMa / Vision** (1990‑е, спутниковое ТВ) | Единая таблица `DATA` на 240+ колонок, всё хранится как EAV‑подобный универсум; индексов больше, чем данных. | Деградация performance, невозможность сопровождения, проект закрыт в течение нескольких месяцев после go‑live. | Red‑Gate Simple‑Talk, *Bad CaRMa* | негативный пример |
| **Magento 1.x EAV bloat** | Каталоги товаров на EAV (eav_attribute, catalog_product_entity_*). | Замедление каталога при росте SKU, миграция на flat tables в Magento 2 как стандарт оптимизации. | Документация Magento, многочисленные блоги | негативный пример |
| **Drupal 7 → 8 field storage** | Гибкое хранение полей через field tables (по сути EAV). | Замена на сущностные таблицы и BC‑прослойку в Drupal 8/9 ради производительности. | Drupal core changelog | смешанный |
| **Tom Kyte (Oracle) на EAV** | Жёсткая позиция: «избегать в business‑сценариях всегда». | Аргументы про планы запроса, индексирование, безопасность. | AskTom, блог Oracle | негативный пример |
| **Bill Karwin, SQL Antipatterns** | Глава «Entity‑Attribute‑Value» как анти‑паттерн. | Каталог типичных грабель и альтернатив. | Pragmatic Bookshelf, 2010 | негативный пример |
| **Inner Platform Effect** | Общий анти‑паттерн «строим СУБД внутри СУБД». | Описан в коммьюнити C2 wiki и в Karwin. | C2 wiki, Wikipedia | негативный пример |

---

## 3. Современные платформы с пользовательскими сущностями

Эти системы решают ту же задачу, что и Интеграм, но другими средствами.
Их стоит описать и сравнить по: модели хранения, способу эволюции схемы,
порогу масштабирования, лицензии.

| Платформа | Модель хранения | Open source | Замечания |
|-----------|----------------|-------------|-----------|
| Airtable | Проприетарный движок поверх MySQL (по слухам). | нет | benchmark недоступен. |
| Bubble | Проприетарная схема. | нет | хороший пример визуального low‑code. |
| Retool | Тонкая обёртка над пользовательскими БД. | частично | не хранит «свои» сущности. |
| Salesforce custom objects | Универсальная EAV‑подобная схема в Oracle (известна по утечкам/реверсу). | нет | классический индустриальный success‑case EAV в масштабе. |
| **NocoDB** | Метаданные + проксирование к пользовательскому SQL. | да (AGPL) | прямой open‑source конкурент Airtable. |
| **Baserow** | PostgreSQL с динамическим DDL (создаёт реальные таблицы). | да (MIT) | альтернативный подход — «настоящие» таблицы. |
| **Directus** | Headless CMS поверх любой SQL‑БД. | да (BSL) | работает со «своими» таблицами пользователя. |
| **AppSheet** | Поверх Google Sheets / Cloud SQL. | нет | важно как индустриальная точка отсчёта. |
| **Knack / Caspio** | Проприетарный SaaS. | нет | EAV‑образное хранение по описаниям. |
| **Strapi** | Headless CMS, динамические content types. | да (MIT) | другая ниша, но релевантный low‑code. |

Для каждого из open‑source кандидатов в этап 4 плана можно поставить
эксперимент в одинаковых условиях нагрузки.

---

## 4. Академические работы, на которые имеет смысл ссылаться

* **Nadkarni, P. M., Marenco, L., Chen, R., Skoufos, E., Shepherd, G., Miller, P.**
  *Organization of heterogeneous scientific data using the EAV/CR
  representation.* JAMIA, 1999.
* **Nadkarni, P. M., Brandt, C.** *Data Extraction and Ad Hoc Query of an
  Entity–Attribute–Value Database.* JAMIA, 1998.
* **Dinu, V., Nadkarni, P.** *Guidelines for the effective use of
  entity–attribute–value modeling for biomedical databases.* JBI, 2007.
* **Anhøj, J.** *Generic design of Web‑based clinical databases.* JMIR, 2003.
* **Codd, E. F.** *A Relational Model of Data for Large Shared Data Banks.*
  CACM, 1970 — фундамент, от которого мы отходим.
* **Karwin, B.** *SQL Antipatterns: Avoiding the Pitfalls of Database
  Programming.* Pragmatic Bookshelf, 2010.
* **Sadalage, P., Fowler, M.** *NoSQL Distilled.* Addison‑Wesley, 2012 —
  для позиционирования относительно document/columnar/KV.
* **Stonebraker, M.** *Schema Later? No Way!* — заметки про schema‑less.
* **Pavlo, A. et al.** *What's Really New with NewSQL?* SIGMOD Record, 2016.
* **Floratou, A. et al.** *Can the elephants handle the NoSQL onslaught?*
  VLDB, 2012 — методология бенчмарков смешанных нагрузок.

---

## 5. Что из этого собственно «новое» в IDEAV / Интеграме?

Это — самый важный раздел, который пока требует доработки автором. Ниже
рабочая гипотеза, которую нужно подтвердить или опровергнуть на этапе 0
плана:

> IDEAV отличается от классической EAV (а) фиксированной арностью кортежа
> (квартет вместо тройки), что даёт возможность партиционировать данные по
> диапазонам идентификаторов и поддерживать B‑Tree‑индексы постоянной
> высоты; (б) разделением *metadata* и *data* на уровне физического
> хранения; (в) типизацией значений на уровне колонок (а не строк), что
> снимает классическую проблему string‑coercion и потери индексируемости.

Если эта гипотеза верна, то в статье есть **измеримое** утверждение —
именно его и нужно эмпирически проверить на этапе 5 плана.
