---
type: doc
status: active
created: 2026-01-14
updated: 2026-01-14
family: F0
scope: repository
---

# 0.OPS (F0)

**F0: Метаэпистема хранилища** — управление знаниями о знаниях в S2R/SRR.

> **Почему OPS?** OPS — коротко, стандартно, прямо означает "операционная логика и порядок работы". Туда естественно ложатся и inbox/archive как операционные корзины.

## Назначение

F0 выполняет три ключевые функции:

1. **Управление хранилищем** — логика организации знаний, стандарты, процессы
2. **Общая онтология** — термины и концепции, применимые ко всем ядрам
3. **Мосты между ядрами** — описание связей между "нашими системами"

## Структура

```
0.OPS/
├── 0.1.Knowledge-Logic/        # Онтология и модель знаний
├── 0.2.Kernels-Bridge/         # Связи между ядрами
├── 0.3.Roles-Matrix-3x3/       # Матрица ролей 3×3
├── 0.4.FPF-Integration/        # Интеграция с FPF
├── 0.5.AI-Reports/             # Автоматические отчёты
├── 0.6.Repository-Processes/   # Процессы и стандарты
├── 0.7.Plans-and-Meetings/     # Планирование
├── 0.9.Inbox/                  # Входящие идеи
└── 0.99.Archive/               # Архив
```

> **Примечание:** `CLAUDE.md` (инструкции для AI) перенесён в корень репозитория.

## Отличие от других семейств

F0 **не делится по ролям** (Предприниматель/Инженер/Менеджер), а организован по функциональным областям. Это единственное семейство, управляющее всеми остальными.

## Ключевые документы

| Документ | Расположение | Описание |
|----------|--------------|----------|
| [01-kernels-model.md](0.1.Knowledge-Logic/01-kernels-model.md) | 0.1 | Модель ядер и правила их создания |
| [02-document-families.md](0.1.Knowledge-Logic/02-document-families.md) | 0.1 | Модель 9 семейств внутри каждого ядра |
| [03-our-systems-map.md](0.1.Knowledge-Logic/03-our-systems-map.md) | 0.1 | Карта "наших систем" |
| [04-ontology.md](0.1.Knowledge-Logic/04-ontology.md) | 0.1 | Общая онтология |
| [05-glossary.md](0.1.Knowledge-Logic/05-glossary.md) | 0.1 | Глоссарий терминов |
| [07-naming.md](0.1.Knowledge-Logic/07-naming.md) | 0.1 | Соглашения об именовании |
| [08-anti-patterns.md](0.1.Knowledge-Logic/08-anti-patterns.md) | 0.1 | Анти-паттерны (типичные ошибки) |
| [09-examples-library.md](0.1.Knowledge-Logic/09-examples-library.md) | 0.1 | Библиотека примеров для AI |
| [01-value-chain.md](0.2.Kernels-Bridge/01-value-chain.md) | 0.2 | Цепочка создания ценности |
| [roles-matrix.md](0.3.Roles-Matrix-3x3/roles-matrix.md) | 0.3 | Матрица ролей 3×3 (полная) |
| [roles-matrix-brief.md](0.3.Roles-Matrix-3x3/roles-matrix-brief.md) | 0.3 | Матрица ролей 3×3 (краткая) |
| [fpf-integration.md](0.4.FPF-Integration/fpf-integration.md) | 0.4 | Интеграция с FPF |
| [01-project-description-template.md](0.6.Repository-Processes/01-project-description-template.md) | 0.6 | Шаблон описания проекта |

## Связи

- Управляет всеми ядрами (A, B, C...)
- Интегрируется с [FPF](0.4.FPF-Integration/fpf/INDEX.md)
