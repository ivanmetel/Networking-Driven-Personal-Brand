---
system: "Management"
role: "Meaning"
title: "Смысл управления: логика и принципы хранилища"
date: "2026-01-07"
tags: [management, meaning, principles, glossary]
status: "active"
related:
  - ../README.md
  - ../0.2.Architecture/README.md
  - ../0.3.Operations/README.md
fpf_principles:
  - minimalism
  - clarity
  - systemic-thinking
---

# Смысл управления (0.1.Meaning)

## Назначение раздела

Здесь документируются **фундаментальные основы** организации хранилища: принципы, терминология, классификация. Это "конституция" репозитория.

**Вопрос раздела:** Зачем? Что значит?

## Содержимое раздела

| Документ | Описание |
|----------|----------|
| [document-families.md](document-families.md) | **Модель семейств документов (F0-F9)** |
| [principles.md](principles.md) | Принципы организации хранилища |
| [glossary.md](glossary.md) | Глоссарий терминов |
| [taxonomy.md](taxonomy.md) | Классификация и теги |

## Что здесь размещается

- **Принципы** — фундаментальные правила организации
- **Терминология** — определения ключевых понятий
- **Классификация** — системы тегов и категорий
- **Ценности** — руководящие идеи проекта

## Связь с FPF

Раздел реализует паттерн **A.1.1 (Bounded Context)** — определяет контекст и терминологию для всего хранилища.

## Шаблон документа

```markdown
---
type: doc
status: draft
created: YYYY-MM-DD
updated: YYYY-MM-DD
system: "Management"
role: "Meaning"
related: []
fpf_principles: []
---

# Название

## Назначение документа

[Краткое описание]

## Основное содержание

[Контент]

## Changelog

| Дата | Изменение | Автор |
|------|-----------|-------|

## Связанные документы

- [Документ](path.md)
```

## Связанные документы

- [Раздел Management](../README.md)
- [Архитектура управления](../0.2.Architecture/README.md)
- [Операции управления](../0.3.Operations/README.md)
