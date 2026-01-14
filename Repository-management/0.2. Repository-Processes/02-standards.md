---
type: spec
status: active
created: 2026-01-14
updated: 2026-01-14
family: F0
scope: repository
---

# Стандарты оформления (Standards)

## Формат документа

Все документы в формате **Markdown** с **YAML frontmatter**.

```markdown
---
type: doc
status: active
created: 2026-01-14
updated: 2026-01-14
family: FA4
kernel: A
system: System-of-Interest
role: Meaning
---

# Заголовок документа

Содержимое...
```

## Обязательные поля frontmatter

| Поле | Тип | Описание |
|------|-----|----------|
| `type` | string | doc, spec, process, report, template |
| `status` | string | stub, draft, active, archived |
| `created` | date | Дата создания (ISO 8601) |
| `updated` | date | Дата обновления (ISO 8601) |

## Рекомендуемые поля frontmatter

| Поле | Тип | Описание |
|------|-----|----------|
| `family` | string | Код семейства (FA1, FB5...) |
| `kernel` | string | Буква ядра (A, B, C...) |
| `system` | string | Suprasystem, System-of-Interest, Constructor |
| `role` | string | Meaning, Architecture, Operations |
| `scope` | string | local-edge, project, ecosystem |
| `related` | list | Связанные документы |
| `fpf_patterns` | list | Коды паттернов FPF |

## Форматирование Markdown

### Заголовки

```markdown
# H1 — только один на документ (название)
## H2 — основные разделы
### H3 — подразделы
#### H4 — детали (редко)
```

### Списки

```markdown
- Маркированный список
- Второй пункт

1. Нумерованный список
2. Второй пункт
```

### Таблицы

```markdown
| Заголовок 1 | Заголовок 2 |
|-------------|-------------|
| Значение 1  | Значение 2  |
```

### Код

```markdown
Инлайн: `code`

Блок:
\`\`\`language
code block
\`\`\`
```

### Ссылки

```markdown
[Текст ссылки](path/to/document.md)
[Внешняя ссылка](https://example.com)
```

## Правила контента

1. **Один документ — одна тема** (SSOT)
2. **Заголовок = имя файла** (по возможности)
3. **Начинай с сути** — не с вводных слов
4. **Используй таблицы** для структурированных данных
5. **Ссылайся на другие документы** через `related` и inline-ссылки

## Язык документов

- **Папки:** только английский
- **Файлы:** могут быть на русском
- **Содержимое:** на языке команды (обычно русский)

## См. также

- [frontmatter-spec.md](frontmatter-spec.md) — детали метаданных
- [document-creation.md](document-creation.md) — процесс создания
