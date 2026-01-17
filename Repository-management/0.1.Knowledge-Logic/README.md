---
type: doc
status: active
created: 2026-01-14
updated: 2026-01-14
family: F0
scope: repository
---

# 0.1. Knowledge Logic

Онтология и модель организации знаний в хранилище.

## Содержимое

| № | Документ | Описание |
|---|----------|----------|
| 01 | [01-kernels-model.md](01-kernels-model.md) | Модель ядер: что такое ядро, как создавать новые |
| 02 | [02-document-families.md](02-document-families.md) | 9 семейств документов внутри каждого ядра |
| 03 | [03-our-systems-map.md](03-our-systems-map.md) | Карта "наших систем" и их позиция в цепочке |
| 04 | [04-ontology.md](04-ontology.md) | Общая онтология для всех ядер |
| 05 | [05-glossary.md](05-glossary.md) | Глоссарий терминов |
| 06 | [06-taxonomy.md](06-taxonomy.md) | Система классификации документов |
| 07 | [07-naming.md](07-naming.md) | Соглашения об именовании |
| 08 | [08-anti-patterns.md](08-anti-patterns.md) | Анти-паттерны (типичные ошибки) |
| 09 | [09-examples-library.md](09-examples-library.md) | Библиотека примеров для AI |

## Принцип

Знания организованы иерархически:

```
Хранилище
└── Ядро (Kernel)
    └── Система (Suprasystem / SoI / Constructor)
        └── Роль (Meaning / Architecture / Operations)
            └── Документ
```
