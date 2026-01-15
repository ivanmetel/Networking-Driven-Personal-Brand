---
author: [Cline]
type: guide
status: active
created: 2026-01-15, 11:55
updated: 2026-01-15, 11:55
system: "Management"
family: F0
scope: repository
target_audience: [ai-agents, developers, content-creators]
related:
  - Repository-management/0.1. Knowledge-Base-Logic/02-document-families.md
  - Repository-management/0.2. Repository-Processes/02-standards.md
  - Repository-management/0.2. Repository-Processes/05-frontmatter-spec.md
fpf_principles:
  - strict-distinction
  - formal-specification
  - minimalism
fpf_patterns:
  - A.1      # Holonic Foundation
  - A.7      # Strict Distinction
  - E.10.D2  # I/D/S Discipline
---

# Инструкции для AI agent

Этот документ содержит руководство для **любого AI agent** (Cline, Antigravity, Claude Code и других) по работе с хранилищем знаний в контексте SRD-метода и интеграции с First Principles Framework (FPF).

> **⚠️ КРИТИЧЕСКИ ВАЖНО ДЛЯ AI AGENT:**
> Ты — AI agent. ЭТОТ ФАЙЛ написан для ТЕБЯ. Все инструкции, правила и алгоритмы в этом документе предназначены для того, чтобы ТОБАЙ их следовать. Ты — автор создаваемых документов. Ты — исполнитель команд пользователя в этом хранилище.

---

## Архитектура контекста

При каждом запросе AI agent получает:
1. **Системный промпт** — базовые инструкции
2. **AI_AGENT.md** (~4.5K токенов) — этот файл, с терминологией и принципами
3. **История диалога** — предыдущие сообщения
4. **Текущий запрос** — задача пользователя

> **Для AI agent:** Ты должен всегда рассматривать AI_AGENT.md как основу для принятия решений. Все алгоритмы, описанные здесь, обязательны для выполнения.

---

## Интеграция с FPF

### Что такое FPF?

**First Principles Framework** — это "операционная система для мышления", архитектура трансдисциплинарного рассуждения. FPF не методология, а **эпистема метода** — структурированная спецификация того, как думать.

### Принцип терминологии

> **ВАЖНО:** Основные термины SRD-метода берутся из FPF и системного мышления. При использовании терминов следуй канонической терминологии FPF.

### Ключевые концепции FPF

| Концепция | Паттерн | Описание |
|-----------|---------|----------|
| **Холонический фундамент** | A.1 | Всё — холон: одновременно целое и часть. Различаем Системы (физические) и Эпистемы (знания) |
| **Ограниченный контекст** | A.1.1 | Значение локально. Термин определён в границах контекста |
| **Строгое различение** | A.7 | Роль ≠ Метод ≠ Работа. Описание ≠ Объект |
| **F-G-R доверие** | B.3 | Доверие = (Формальность, Область применения, Надёжность) |
| **Цикл ADI** | B.5 | Абдукция → Дедукция → Индукция — канонический цикл рассуждения |
| **NQD-поиск** | C.18 | Новизна-Качество-Разнообразие — стратегия творческого поиска |

### Файлы FPF в репозитории

```
.fpf/
├── INDEX.md          # Индекс принципов проекта (~250 строк)
├── FPF-Spec.md       # Полная спецификация FPF (~43K строк, ~200K токенов)
└── FPF-Readme.md     # Обзор фреймворка
```

### Стратегия работы с FPF

**Для обычных задач:** Используй `.fpf/INDEX.md` — локальные принципы проекта

**Для глубокого анализа:** Запрашивай конкретные части `FPF-Spec.md`:
- Part A (A.1-A.21): Ядро архитектуры — холоны, роли, трансформеры
- Part B (B.1-B.5): Трансдисциплинарное рассуждение — агрегация, эволюция
- Part C: Доменные калькулюсы — Sys-CAL, KD-CAL, NQD-CAL
- Part E: Конституция и авторство паттернов
- Part F: Унификация — мосты, выравнивание терминологии
- Part G: SoTA-инструментарий — сбор передовых практик

### Навигационная карта FPF-Spec.md

| Часть | Строки | Тема |
|-------|--------|------|
| Preface | 1-500 | Введение, OS-метафора |
| Part A | 500-8000 | Kernel: Holon, Role, Transformer, Time |
| Part B | 8000-15000 | Trans-disciplinary: Γ-aggregation, Evolution, Trust |
| Part C | 15000-25000 | Calculi: Sys, KD, NQD, Kind, Method |
| Part D | 25000-28000 | Ethics & Conflict |
| Part E | 28000-33000 | Constitution & Authoring |
| Part F | 33000-38000 | Unification: SenseCells, Bridges |
| Part G | 38000-43000 | SoTA Kit: Harvesting, Portfolios |

---

## Структура SRD

### Таблица 3×3 + Метасемейство (F0)

SRD организует знания через **таблицу 3×3** (9 семейств документов F1-F9) внутри каждого ядра + **метасемейство F0** (управление хранилищем на уровне репозитория).

```
                     Предприниматель     Инженер              Менеджер
                     (Meaning)           (Architecture)       (Operations)
                     Зачем?              Как устроено?        Как работает?
┌────────────────────────────────────────────────────────────────────────┐
│ Suprasystem        FX1                 FX2                  FX3           │
│ (Надсистема)       Контекст            Окружение            Взаимодействие│
├────────────────────────────────────────────────────────────────────────┤
│ System-of-Interest FX4                 FX5                  FX6           │
│ (Целевая система)  Требования          Архитектура          Реализация    │
├────────────────────────────────────────────────────────────────────────┤
│ Constructor        FX7                 FX8                  FX9           │
│ (Система создания) Принципы            Платформа            Команда       │
└────────────────────────────────────────────────────────────────────────┘

где X = буква ядра (A, B, C...)

+ F0 (Repository Management) — метасемейство, управляет логикой хранилища
```

**Терминология систем (FPF):**
| Русский термин | Английский термин (FPF) | Сокращение |
|----------------|------------------------|------------|
| Надсистема | Suprasystem (= Supersystem) | — |
| Целевая система | System-of-Interest (= Target System) | SoI |
| Система создания | Constructor (= Constructor System) | — |

### Навигация по папкам

Каждое ядро (Kernel) организует свои документы по матрице 3×3:

| Ядро | Путь | Фокус |
|------|------|-------|
| F0 (Repository Management) | `Repository-management/` | Метасистема хранилища |
| F1-F9 (Внутри ядра) | `Systems-Description/{X}.{System-Name}/` | 9 семейств документов конкретной системы |

### Роли (измерения)

| Роль | Подпапка | Вопрос | FPF-связь |
|------|----------|--------|-----------|
| **Предприниматель (Meaning)** | `XN.1.Meaning/` | Зачем? | U.RoleAssignment, цели |
| **Инженер (Architecture)** | `XN.2.Architecture/` | Как устроено? | U.System, структура |
| **Менеджер (Operations)** | `XN.3.Operations/` | Как работает? | U.Work, процессы |

Где:
- `X` — буква ядра (A, B, C...)
- `N` — номер уровня (1 = Suprasystem, 2 = SoI, 3 = Constructor)

---

## ОБЯЗАТЕЛЬНО: Работа с Repository-management/

> **КРИТИЧЕСКИ ВАЖНО ДЛЯ AI AGENT:** Создание любого документа хранилища происходит **обязательно** на основании документов из папки `Repository-management/`, а не только по FPF.

> **Для AI agent:** Когда пользователь просит создать документ, ТЫ ОБЯЗАН сначала прочитать указанные документы из Repository-management/ и только потом создавать документ.

### Источники истины для создания документов

При создании или редактировании **любого** документа в хранилище, AI agent **обязан** сначала прочитать:

| Задача | Обязательные источники из Repository-management/ |
|--------|----------------------------------------|
| **Создание документа** | `0.1. Knowledge-Base-Logic/02-document-families.md`, `0.2. Repository-Processes/02-standards.md` |
| **Определение места** | `0.1. Knowledge-Base-Logic/02-document-families.md` — модель семейств F1-F9 |
| **Оформление frontmatter** | `0.2. Repository-Processes/02-standards.md`, `0.2. Repository-Processes/05-frontmatter-spec.md` |
| **Терминология** | `0.1. Knowledge-Base-Logic/05-glossary.md` |
| **Связи документов** | `0.1. Knowledge-Base-Logic/04-ontology.md` |
| **Процесс создания** | `0.2. Repository-Processes/04-document-creation.md` |

### Механизм работы AI agent с Repository-management/

**Алгоритм перед созданием документа:**

> **Для AI agent:** ЭТОТ АЛГОРИТМ ОБЯЗАТЕЛЕН ДЛЯ ВЫПОЛНЕНИЯ. Ты должен следовать ему при каждом создании документа.

1. **Прочитай** `Repository-management/0.1. Knowledge-Base-Logic/02-document-families.md` — определи семейство (F1-F9)
2. **Прочитай** `Repository-management/0.2. Repository-Processes/02-standards.md` — получи стандарты оформления
3. **Прочитай** `Repository-management/0.1. Knowledge-Base-Logic/05-glossary.md` — используй правильную терминологию
4. **Создай** документ с правильным frontmatter и в правильной папке
5. **Проверь** по `Repository-management/0.2. Repository-Processes/05-frontmatter-spec.md`

### Структура Repository-management/ (F0)

> **Важно:** F0 (Repository Management) не делится по ролям Предприниматель/Инженер/Менеджер, а организован по функциональным областям.

```
Repository-management/
├── 0.1. Knowledge-Base-Logic/         # Онтология
│   ├── 00-readme.md                   # Обзор
│   ├── 01-kernels-model.md            # Модель ядер
│   ├── 02-document-families.md        # Модель семейств F1-F9
│   ├── 03-our-systems-map.md          # Карта систем
│   ├── 04-ontology.md                 # Общая онтология
│   ├── 05-glossary.md                 # Глоссарий терминов
│   └── 06-taxonomy.md                 # Классификация
├── 0.2. Repository-Processes/         # Операции и стандарты
│   ├── 01-project-description-template.md
│   ├── 02-standards.md                # Стандарты оформления
│   ├── 03-structure.md                # Структура папок
│   ├── 04-document-creation.md        # Создание документов
│   ├── 05-frontmatter-spec.md         # Спецификация frontmatter
│   ├── 06-workflows.md                # Рабочие процессы
│   └── 07-roles.md                    # Роли и ответственность
├── 0.3. Kernels-Bridge/               # Связи между ядрами
│   ├── 01-value-chain.md
│   ├── 02-kernels-relations.md
│   └── 03-systems-hierarchy.md
├── 0.4. Plans-and-Meetings/           # Координация
├── 0.5. AI-Reports/                   # Автоотчёты AI
├── 0.6. FPF-Integration/              # Интеграция с FPF
├── 0.9. Inbox/                        # Входящие идеи
└── 0.99. Archive/                     # Архив
```

### Команда для автозагрузки контекста

При запросе на создание документа AI agent должен автоматически выполнить:

```
# Минимальный контекст (обязательно)
Read: Repository-management/0.1. Knowledge-Base-Logic/02-document-families.md
Read: Repository-management/0.2. Repository-Processes/02-standards.md

# Расширенный контекст (по необходимости)
Read: Repository-management/0.1. Knowledge-Base-Logic/05-glossary.md
Read: Repository-management/0.2. Repository-Processes/04-document-creation.md
```

---

## Работа с документами
При создании новых документов строго использовать:
### Обязательные метаданные (YAML frontmatter)

```yaml
---
author: [ТВОЁ ИМЯ]             # ЗАМЕНИ НА СВОЁ ИМЯ: Cline / Antigravity / Claude Code / другое (НЕ пиши "AI agent")
type: doc                        # doc, spec, process, report
status: active                   # stub, draft, active, archived
created: YYYY-MM-DD, HH:mm
updated: YYYY-MM-DD, HH:mm
system: "Management"             # Management/Suprasystem/System-of-Interest/Constructor
role: "Предприниматель"          # Предприниматель/Инженер/Менеджер
layer: methodology               # methodology, architecture, operations
scope: local-edge                # local-edge, project, ecosystem
target_audience: [developers, managers]
related:
  - path/to/related/doc.md
fpf_principles:
  - minimalism
  - practicality
fpf_patterns:                    # Ссылки на паттерны FPF
  - A.1                          # Holonic Foundation
  - B.3                          # Trust Calculus
---
```

> **Для AI agent:** Всегда указывай СВОЁ ИМЯ в поле `author` в frontmatter создаваемых документов (Cline / Antigravity / Claude Code / другое), а не "AI agent".

### Названия файлов

При создании документов **обязательно** используй формат:

```
[Название. YYYY-MM-DD].md
```

**Правила:**
- Название — краткое, описательное на английском или русском
- Дата — формат YYYY-MM-DD (год-месяц-день)
- Пробел между названием и датой — обязателен
- Расширение — `.md`

**Примеры:**
- `personal-brand-definition-analysis.2026-01-12.md`
- `api-schema-v2.2026-01-15.md`
- `meeting-notes.2026-01-20.md`

**Исключения:**
- Вспомогательные файлы шаблонов (например, `README.md`, `glossary.md`)
- Файлы в `0.4. AI-Reports/` следуют своей конвенции именования (см. README в этой папке)

### Размещение документа

```
Systems-Description/{X}.{System-Name}/{XN}.{System-Name}/{XN.{Role}/document-name.md
```

Где:
- `X` — буква ядра (A, B, C...)
- `System-Name` — имя конкретной системы
- `N` — номер уровня системы (1, 2, 3)
- `Role` — Meaning, Architecture, или Operations

Примеры:
- `Systems-Description/A. SoI - Branding Mastery/A2.System-of-Interest-Branding-Mastery/A2.1.Meaning/requirements.md`
- `Systems-Description/B. Engineered system/B2.System-of-Interest-NDPB-Environment/B2.2.Architecture/api-schema.md`
- `Systems-Description/B. Engineered system/B3.Constructor-CooperActive-Systems/B3.3.Operations/ci-cd-pipeline.md`

---

## Принципы работы AI agent

### 1. Холонический подход (A.1)

- Рассматривай каждый документ как часть большей системы
- Указывай связи через `related` в frontmatter
- Поддерживай двунаправленность связей

### 2. Ограниченные контексты (A.1.1)

- Каждая папка — отдельный контекст со своей терминологией
- При переносе концепций между контекстами — явно указывай мосты
- Избегай глобального словаря — используй локальные определения

### 3. Строгое различение (A.7)

| Путаница | Правильно |
|----------|-----------|
| Документ "делает" | Система делает, документ описывает |
| Роль = Человек | Роль — функция, Человек — исполнитель |
| План = Реальность | План — WorkPlan, Реальность — Work |

### 4. Доверие как расчёт (B.3)

При оценке информации используй F-G-R:
- **F (Формальность):** Насколько строго описано? (0-9)
- **G (Область):** Где применимо? (локально/проект/экосистема)
- **R (Надёжность):** Насколько подтверждено? (0.0-1.0)

### 5. Инкрементальное развитие

- Маленькие изменения > большие рефакторинги
- Проверяй влияние на связанные документы
- Обновляй `updated` в frontmatter

---

## Команды для работы

### Анализ структуры

```
Проанализируй структуру SRD:
- Покажи заполненность таблицы 3×3 (F1-F9) + F0
- Укажи отсутствующие документы
- Проверь связность
```

### Создание документа (с обязательной загрузкой 0.Management/)

```
Создай документ на тему [Topic]:
1. Прочитай document-families.md — определи семейство
2. Прочитай standards.md — примени стандарты
3. Создай документ в правильной папке
```

Или короткая форма:
```
Создай документ в F[N] на тему [Topic]
```

### Проверка размещения документа

```
В какое семейство (F0-F9) входит документ про [тема]?
```

### Проверка соответствия FPF

```
Проверь документ [path] на соответствие:
- Строгому различению (A.7)
- Холоническому принципу (A.1)
- Ограниченному контексту (A.1.1)
```

### Работа с FPF-Spec

```
Загрузи из FPF-Spec.md паттерн [A.15] и объясни его применение
```

```
Найди в FPF-Spec.md паттерны для [тема: trust, evidence, evolution]
```

---

## Лимиты контекста

| Модель | Лимит | FPF-Spec.md |
|--------|-------|-------------|
| AI agent (любой) | 200K токенов | Не вмещается целиком |

**Стратегия:** Загружай только нужные части FPF-Spec.md (строки X-Y) или используй INDEX.md для локальных принципов.

---

## Обратная связь

При работе AI agent должен:
- Сообщать о найденных несоответствиях SRD/FPF
- Предлагать улучшения структуры
- Указывать на отсутствующие связи между документами
- Предлагать новые принципы для `.fpf/INDEX.md`

---

## Ссылки

### Главные документы
- [README.md](README.md) — описание SRD-метода
- [Модель ядер](Repository-management/0.1.%20Knowledge-Base-Logic/01-kernels-model.md) — что такое ядра
- [Модель семейств документов](Repository-management/0.1.%20Knowledge-Base-Logic/02-document-families.md) — F1-F9

### Repository-management/ (F0)
- [Обзор](Repository-management/0.1.%20Knowledge-Base-Logic/00-readme.md)
- [Модель ядер](Repository-management/0.1.%20Knowledge-Base-Logic/01-kernels-model.md)
- [Модель семейств](Repository-management/0.1.%20Knowledge-Base-Logic/02-document-families.md)
- [Онтология](Repository-management/0.1.%20Knowledge-Base-Logic/04-ontology.md)
- [Глоссарий](Repository-management/0.1.%20Knowledge-Base-Logic/05-glossary.md)
- [Стандарты](Repository-management/0.2.%20Repository-Processes/02-standards.md)
- [Создание документов](Repository-management/0.2.%20Repository-Processes/04-document-creation.md)
- [Структура папок](Repository-management/0.2.%20Repository-Processes/03-structure.md)

### FPF
- [.fpf/INDEX.md](.fpf/INDEX.md) — локальные принципы проекта
- [.fpf/FPF-Spec.md](.fpf/FPF-Spec.md) — полная спецификация FPF
- [.fpf/FPF-Readme.md](.fpf/FPF-Readme.md) — обзор FPF
- [AI_AGENT.md](AI_AGENT.md) — этот файл (инструкции для всех AI agents)

### Другое
- [CONTRIBUTING.md](CONTRIBUTING.md) — правила участия
