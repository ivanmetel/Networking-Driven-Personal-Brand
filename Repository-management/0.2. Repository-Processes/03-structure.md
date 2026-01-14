---
type: doc
status: active
created: 2026-01-14
updated: 2026-01-14
family: F0
scope: repository
---

# Структура репозитория (Structure)

## Верхнеуровневая структура

```
s2r/
├── 0.OPS/     # F0: Метаэпистема хранилища
├── A.SOI-Name/                  # Ядро A: Целевая система
├── B.Our-System-Name/           # Ядро B: Наша система
├── C.../                        # Ядра C, D... (по необходимости)
├── README.md                    # Описание проекта
└── CONTRIBUTING.md              # Правила участия
```

## Структура F0 (Repository Management)

```
0.OPS/
├── README.md
├── CLAUDE.md                    # Инструкции для AI
├── 0.1.Knowledge-Logic/         # Онтология и модель
│   ├── 00-readme.md
│   ├── 01-kernels-model.md
│   ├── 02-document-families.md
│   ├── 03-our-systems-map.md
│   ├── 04-ontology.md
│   ├── 05-glossary.md
│   ├── 06-taxonomy.md
│   └── 07-naming.md
├── 0.2.Repository-Processes/    # Процессы и стандарты
│   ├── README.md
│   ├── 01-project-description-template.md
│   ├── 02-standards.md
│   ├── 03-structure.md
│   ├── 04-document-creation.md
│   ├── 05-frontmatter-spec.md
│   ├── 06-workflows.md
│   └── 07-roles.md
├── 0.3.Kernels-Bridge/          # Связи между ядрами
│   ├── README.md
│   ├── 01-value-chain.md
│   ├── 02-kernels-relations.md
│   └── 03-systems-hierarchy.md
├── 0.4.Plans-and-Meetings/      # Планирование и совещания
├── 0.5.AI-Reports/              # Автоматические отчёты
├── 0.6.FPF-Integration/         # Интеграция с FPF
│   ├── fpf/                     # Копия спецификации FPF
│   ├── fpf-integration.md
│   └── fpf-patterns-map.md
├── 0.9.Inbox/                   # Входящие идеи и предложения
└── 0.99.Archive/                # Архив
```

## Структура ядра (Kernel)

> **Важно:** Папки именуются по именам систем, не по ролям.

```
X.{System-Name}/
├── README.md                        # Описание ядра
├── X0.{System-Name}-Management/     # FX0: Управление (опционально)
│   ├── README.md
│   └── local-ontology.md
├── X1.{Suprasystem-Name}/           # Надсистема
│   ├── X1.1.Meaning/                # FX1
│   │   └── README.md
│   ├── X1.2.Architecture/           # FX2
│   │   └── README.md
│   └── X1.3.Operations/             # FX3
│       └── README.md
├── X2.{System-Name}/                # Целевая система (SoI)
│   ├── X2.1.Meaning/                # FX4
│   │   └── README.md
│   ├── X2.2.Architecture/           # FX5
│   │   └── README.md
│   └── X2.3.Operations/             # FX6
│       └── README.md
└── X3.{Constructor-Name}/           # Система создания
    ├── X3.1.Meaning/                # FX7
    │   └── README.md
    ├── X3.2.Architecture/           # FX8
    │   └── README.md
    └── X3.3.Operations/             # FX9
        └── README.md
```

где `X` = A, B, C... (буква ядра)

## Внешние данные и первичка

> **Принцип:** Хранилище содержит **знания о системах**, а не первичные данные.

### Что хранится ВНЕ этого репозитория

| Тип данных | Где хранится | В репозитории указываем |
|------------|--------------|-------------------------|
| **Первичка** (документы, счета) | 1С, ERP, DMS | Ссылку и краткое описание |
| **Финансовые показатели** | BI-система, таблицы | Ссылку и структуру метрик |
| **Базы данных** | СУБД, хранилища | Схему и назначение |
| **Код** | Git-репозитории | Ссылку и описание |
| **Медиа-файлы** | CDN, хранилища | Ссылку и описание |

### Как указывать внешние данные

В документах хранилища указывайте:

```markdown
## Внешние источники данных

| Источник | Тип | Расположение | Описание |
|----------|-----|--------------|----------|
| CRM | База данных | `db.company.com/crm` | Клиентская база |
| 1С | ERP | `1c.company.com` | Финансовая первичка |
| Analytics | BI | `bi.company.com/dashboard` | Метрики продукта |
```

### Шаблон описания внешнего источника

```markdown
### [Название источника]

**Тип:** База данных / ERP / BI / Файловое хранилище
**Расположение:** [URL или путь]
**Владелец:** [@username]
**Доступ:** [описание прав доступа]

**Содержимое:**
- [Что хранится]
- [Структура данных]

**Связь с хранилищем:**
- Используется в: [ссылки на документы]
- Для: [назначение]
```

## Навигационная таблица

| Путь | Семейство | Содержимое |
|------|-----------|------------|
| `0.OPS/` | F0 | Метаэпистема хранилища |
| `X.../X1.{Supra}/X1.1.Meaning/` | FX1 | Контекст, рынок |
| `X.../X1.{Supra}/X1.2.Architecture/` | FX2 | Окружение, интерфейсы |
| `X.../X1.{Supra}/X1.3.Operations/` | FX3 | Партнёрства |
| `X.../X2.{SoI}/X2.1.Meaning/` | FX4 | Требования, ценность |
| `X.../X2.{SoI}/X2.2.Architecture/` | FX5 | Архитектура |
| `X.../X2.{SoI}/X2.3.Operations/` | FX6 | Реализация |
| `X.../X3.{Constr}/X3.1.Meaning/` | FX7 | Принципы команды |
| `X.../X3.{Constr}/X3.2.Architecture/` | FX8 | Платформа |
| `X.../X3.{Constr}/X3.3.Operations/` | FX9 | Команда, методология |

## См. также

- [../0.1.Knowledge-Logic/01-kernels-model.md](../0.1.Knowledge-Logic/01-kernels-model.md) — модель ядер
- [../0.1.Knowledge-Logic/07-naming.md](../0.1.Knowledge-Logic/07-naming.md) — именование
