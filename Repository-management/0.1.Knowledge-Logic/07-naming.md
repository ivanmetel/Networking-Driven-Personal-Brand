---
type: doc
status: active
created: 2026-01-14
updated: 2026-01-14
family: F0
scope: repository
---

# Соглашения об именовании (Naming Conventions)

## Общие правила

1. **Папки** — только на английском
2. **Файлы** — могут быть на русском или английском
3. **Используй kebab-case** для файлов: `my-document.md`
4. **Используй PascalCase или числовую нумерацию** для папок

## Именование папок

### Корневой уровень

```
0.OPS/     # Числовой префикс + PascalCase
A.Automobile/                # Буква ядра + имя целевой системы
B.Mobile-App/                # Буква ядра + имя нашей системы
```

### Уровень системы

> **Важно:** X1 — это **физическая система**, не контекст, процесс или область.

```
Хорошо (на примере автомобиля):
A1.Taxi/                     # Надсистема: физическая система (такси)
A2.Automobile/               # Имя целевой системы (SoI)
A3.Assembly-Line/            # Имя конструктора (конвейер)

Хорошо (на примере приложения):
B1.User-Smartphone/          # Надсистема: физическая система (смартфон)
B2.Mobile-App/               # SoI
B3.Dev-Team/                 # Конструктор

Плохо:
A1.Daily-Life/               # ❌ "Повседневная жизнь" — НЕ система
A1.Market/                   # ❌ "Рынок" — НЕ физическая система
A1.Industry/                 # ❌ "Отрасль" — НЕ физическая система
A3.Experience/               # ❌ "Опыт" — НЕ система
A1.Suprasystem/              # ❌ Это роль, не имя системы
A2.System-of-Interest/       # ❌ Абстрактно
A3.Constructor/              # ❌ Не описывает, ЧТО создаёт
```

### Уровень роли

```
X1.1.Meaning/                # X = ядро, 1 = система, .1/.2/.3 = роль
X1.2.Architecture/
X1.3.Operations/
```

> Роли остаются фиксированными: Meaning, Architecture, Operations

### Уровень F0

```
0.1.Knowledge-Logic/         # Онтология и модель знаний
0.2.Kernels-Bridge/          # Связи между ядрами
0.3.Roles-Matrix-3x3/        # Матрица ролей 3×3
0.4.FPF-Integration/         # Интеграция с FPF
0.5.AI-Reports/              # Автоматические отчёты
0.6.Repository-Processes/    # Процессы и стандарты
0.7.Plans-and-Meetings/      # Планирование
0.9.Inbox/
0.99.Archive/
```

## Именование файлов

### Документы

```
requirements.md              # Простое имя
api-specification.md         # kebab-case для составных
team-structure.md
value-chain.md
```

### README файлы

```
README.md                    # Всегда UPPERCASE
```

### Специальные файлы

```
local-ontology.md            # В X0.{System-Name}-Management/
_index.md                    # Если нужен индекс (редко)
```

## Паттерны именования ядер

### Хорошо

```
A.Automobile/                # Конкретная техническая система
B.Mobile-App/                # Описывает систему
C.Backend-Service/           # Технически точно
D.Analytics-Platform/        # Функционально
```

### Плохо

```
A.Target/                    # Слишком абстрактно
B.System2/                   # Неинформативно
C.Module/                    # Размыто
D.Other/                     # Бессмысленно
A.Impressed-Customer/        # ❌ "Клиент" — роль, не система
A.Experience/                # ❌ "Опыт" — процесс, не система
```

## Примеры полных путей

### Хорошо (с именами систем)

```
0.OPS/0.1.Knowledge-Logic/01-kernels-model.md
A.Automobile/A1.Taxi/A1.1.Meaning/market-analysis.md
A.Automobile/A2.Automobile/A2.1.Meaning/requirements.md
B.Mobile-App/B1.User-Smartphone/B1.2.Architecture/device-integration.md
B.Mobile-App/B3.Dev-Team/B3.3.Operations/team-structure.md
C.Backend-Service/C2.Backend-Service/C2.2.Architecture/api-schema.md
```

### Плохо (абстрактные названия)

```
A.Target-System/A2.System-of-Interest/A2.1.Meaning/requirements.md
A.Product/A1.Daily-Life/A1.1.Meaning/context.md           # ❌ Daily-Life — не система
B.Our-System/B3.Constructor/B3.3.Operations/team-structure.md
```

## См. также

- [06-taxonomy.md](06-taxonomy.md) — классификация документов
- [../0.6.Repository-Processes/02-standards.md](../0.6.Repository-Processes/02-standards.md) — стандарты
