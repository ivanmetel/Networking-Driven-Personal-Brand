---
type: doc
status: active
created: 2026-01-07
updated: 2026-01-07
system: "Management"
role: "AutoReports"
layer: operations
scope: local-edge
target_audience: [administrators, ai-agents]
related:
  - ../README.md
  - ../0.5.ValidationSpecs/README.md
fpf_principles:
  - continuous-validation
fpf_patterns:
  - B.3      # Trust Calculus
---

# Автоматические отчёты ИИ (0.4.AutoReports)

## Назначение раздела

Здесь размещаются **автоматически генерируемые отчёты** о состоянии хранилища, качестве документов и результатах проверок.

## Содержимое раздела

| Тип отчёта | Описание | Периодичность |
|------------|----------|---------------|
| Качество документов | Проверка frontmatter, связей | По запросу |
| Покрытие таблицы | Заполненность SRT-ячеек | Еженедельно |
| Битые ссылки | Проверка related и внешних ссылок | По запросу |
| FPF-соответствие | Аудит на соответствие принципам | По запросу |

## Формат отчётов

```markdown
---
type: report
status: active
created: YYYY-MM-DD
generated_by: ai-agent
system: "Management"
role: "AutoReports"
---

# Отчёт: [Название]

**Дата генерации:** YYYY-MM-DD HH:MM
**Агент:** Claude Code

## Резюме

[Краткие выводы]

## Детали

[Подробные данные]

## Рекомендации

[Предложения по улучшению]
```

## Как запустить генерацию

```
Сгенерируй отчёт о [качестве документов / покрытии матрицы / битых ссылках]
и сохрани в 0.4.AutoReports/
```

## Связанные документы

- [Раздел Management](../README.md)
- [ТЗ для автопроверки](../0.5.ValidationSpecs/README.md)
