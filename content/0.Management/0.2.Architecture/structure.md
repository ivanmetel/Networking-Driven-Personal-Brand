---
type: doc
status: active
created: 2026-01-07
updated: 2026-01-07
system: "Management"
role: "Architecture"
layer: architecture
scope: local-edge
target_audience: [ai-agents, administrators, contributors]
related:
  - roles.md
  - standards.md
  - ../0.1.Meaning/principles.md
fpf_principles:
  - systemic-thinking
  - srt-structure
fpf_patterns:
  - A.1      # Holonic Foundation
  - A.1.1    # Bounded Context
---

# Структура хранилища

## Назначение документа

Описание архитектуры хранилища знаний, организации папок и файлов.

## Системная модель

Хранилище организовано на основе **трёхуровневой системной модели**:

```
                    ┌─────────────────────────┐
                    │     1. Supersystem      │
                    │    (Внешняя среда)      │
                    └───────────┬─────────────┘
                                │
                    ┌───────────▼─────────────┐
                    │    2. TargetSystem      │
                    │  (Целевой продукт)      │
                    └───────────┬─────────────┘
                                │
                    ┌───────────▼─────────────┐
                    │   3. CreationSystem     │
                    │  (Система создания)     │
                    └─────────────────────────┘

        ┌───────────────────────────────────────────────┐
        │              0. Management                     │
        │        (Метасистема хранилища)                │
        └───────────────────────────────────────────────┘
```

## Верхнеуровневая структура

```
srd-template/
├── README.md                    # Главное описание проекта
├── CLAUDE.md                    # Инструкции для Claude Code
├── CONTRIBUTING.md              # Правила участия
│
├── .fpf/                        # First Principles Framework
│   ├── INDEX.md                 # Локальные принципы проекта
│   ├── FPF-Spec.md              # Полная спецификация FPF
│   └── FPF-Readme.md            # Обзор FPF
│
└── content/                     # Контент по методу SRT
    ├── 0.Management/            # Метасистема
    ├── 1.Supersystem/           # Надсистема
    ├── 2.TargetSystem/          # Целевая система
    └── 3.CreationSystem/        # Система создания
```

## Структура раздела (системы)

Каждая система имеет три подраздела по ролям:

```
N.SystemName/
├── README.md                    # Обзор раздела
├── N.1.Meaning/                 # Смысл: зачем?
│   ├── README.md                # Шаблон и описание
│   └── [документы].md
├── N.2.Architecture/            # Архитектура: как устроено?
│   ├── README.md
│   └── [документы].md
└── N.3.Operations/              # Операции: как работает?
    ├── README.md
    └── [документы].md
```

## Полная структура content/

```
content/
├── 0.Management/
│   ├── README.md                # О разделе Management
│   ├── 0.1.Meaning/
│   │   ├── README.md            # Шаблон
│   │   ├── principles.md        # Принципы организации
│   │   ├── glossary.md          # Глоссарий
│   │   └── taxonomy.md          # Классификация
│   ├── 0.2.Architecture/
│   │   ├── README.md
│   │   ├── structure.md         # Этот документ
│   │   ├── roles.md             # Роли и ответственность
│   │   └── standards.md         # Стандарты оформления
│   └── 0.3.Operations/
│       ├── README.md
│       ├── workflows.md         # Процессы работы
│       ├── claude-fpf.md        # Интеграция Claude и FPF
│       └── document-creation.md # Создание документов
│
├── 1.Supersystem/
│   ├── 1.1.Meaning/             # Контекст, рынок
│   ├── 1.2.Architecture/        # Окружение
│   └── 1.3.Operations/          # Взаимодействие
│
├── 2.TargetSystem/
│   ├── 2.1.Meaning/             # Требования
│   ├── 2.2.Architecture/        # Архитектура продукта
│   └── 2.3.Operations/          # Реализация
│
└── 3.CreationSystem/
    ├── 3.1.Meaning/             # Принципы разработки
    ├── 3.2.Architecture/        # Инструменты
    └── 3.3.Operations/          # Методология
```

## Принципы именования

### Папки

| Элемент | Формат | Пример |
|---------|--------|--------|
| Система | `N.SystemName` | `2.TargetSystem` |
| Роль | `N.M.RoleName` | `2.1.Meaning` |

### Файлы

| Правило | Пример |
|---------|--------|
| Нижний регистр | `api-design.md` |
| Дефис как разделитель | `user-authentication.md` |
| Описательное имя | `database-schema.md` |
| Расширение `.md` | `requirements.md` |

### Примеры путей

```
content/0.Management/0.1.Meaning/principles.md
content/2.TargetSystem/2.2.Architecture/api-schema.md
content/3.CreationSystem/3.3.Operations/ci-cd-pipeline.md
```

## Таблица подразделов

| Ячейка | Название | Вопрос | Целевая аудитория |
|--------|----------|--------|-------------------|
| 0.1 | Management/Meaning | Зачем управление? | Администраторы |
| 0.2 | Management/Architecture | Как устроено? | Администраторы |
| 0.3 | Management/Operations | Как управлять? | Все участники |
| 1.1 | Supersystem/Meaning | Зачем контекст? | Аналитики |
| 1.2 | Supersystem/Architecture | Как устроено окружение? | Аналитики |
| 1.3 | Supersystem/Operations | Как взаимодействуем? | Все участники |
| 2.1 | TargetSystem/Meaning | Какие требования? | Продуктовые менеджеры |
| 2.2 | TargetSystem/Architecture | Как устроен продукт? | Архитекторы |
| 2.3 | TargetSystem/Operations | Как реализуем? | Разработчики |
| 3.1 | CreationSystem/Meaning | Какие принципы? | Техлиды |
| 3.2 | CreationSystem/Architecture | Какие инструменты? | Разработчики |
| 3.3 | CreationSystem/Operations | Какая методология? | Все участники |

## FPF-связь

Структура отражает паттерны FPF:

| Паттерн | Применение в структуре |
|---------|------------------------|
| **A.1 Holonic Foundation** | Каждая папка — холон (целое и часть) |
| **A.1.1 Bounded Context** | Каждая папка — ограниченный контекст |
| **A.2 Role Taxonomy** | Роли Meaning/Architecture/Operations |
| **A.7 Strict Distinction** | Чёткое разделение типов контента |

## Changelog

| Дата | Изменение | Автор |
|------|-----------|-------|
| 2026-01-07 | Создание документа | Claude |

## Связанные документы

- [Роли и ответственность](roles.md)
- [Стандарты оформления](standards.md)
- [Принципы организации](../0.1.Meaning/principles.md)
