---
type: name-card
status: active
created: 2026-01-15
updated: 2026-01-15
system: "NDPB"
target_system: "NDPB Environment"
target_family: "F5"  # Description
author: Cline
layer: terminology
scope: project-global
target_audience: [developers, brand-strategists, marketing-team]
related:
  - ../../Systems-Description/A. SoI - Branding Mastery/A2.System-of-Interest-Branding-Mastery/README.md
  - ../0.1. Knowledge-Base-Logic/05-glossary.md
  - ../0.6. FPF-Integration/fpf-integration.md
fpf_principles:
  - clarity
  - cognitive-ergonomics
  - operational-affordance
fpf_patterns:
  - B.5      # ADI Cycle
  - A.7      # Strict Distinction
  - A.1.1    # Bounded Context
---

# Name Card: BrandLoop

## Контекст смысла

**BrandLoop** — это операционная единица NDPB-программы, реализующая трёхфазный цикл развития персонального бренда через LinkedIn. Каждая фаза соответствует этапу когнитивного моделирования в головах внешних агентов, что позволяет ускорить формирование устойчивого бренда.

Формируется на основе паттерна **B.5 — ADI Cycle** из FPF-фреймворка, но переименована для маркетинговой аудитории, поскольку термины "Abduction-Deduction-Induction" слишком сложны для позиционирования продукта.

## Онтологический Kind

**ProcessPattern** — паттерн процесса, который повторяется итеративно для достижения целевого состояния (устойчивого бренда).

## Purpose/Use-Domain

**Personal Brand Development via LinkedIn**

- Используется как модульная единица NDPB-обучающего курса
- Применяется в контексте развития персонального бренда через LinkedIn
- Интегрируется в операционные плейбуки для LinkedIn-активностей

## Минимальное определение (MDS)

**BrandLoop** — это повторяемая последовательность действий: формирование гипотезы (сигнал), проверка через опыт (контент), закрепление паттерна (вовлечение), приводящая к устойчивым изменениям в когнитивных моделях других людей.

## Tech/Plain пара

### Technical Definition
**ADI Cycle Implementation**: Abduction (Signal Generation) → Deduction (Experience Validation) → Induction (Pattern Consolidation)

### Plain Definition
**Трёхшаговый цикл**: показаться → доказать → закрепиться

## Результат лексического NQD‑поиска

### CandidateSet

- "BrandLoop"
- "BrandCycle"
- "BrandFlow"
- "GrowthLoop"
- "BrandArc"
- "ImpactCycle"

### NQD‑front

**BrandLoop**

### Заметки о том, почему альтернативы отсеялись

#### BrandCycle
- **Проблема**: Too generic, "cycle" is overused in marketing
- **Причина отклонения**: Не подчёркивает непрерывную природу процесса
- **Оценка**: Lower cognitive distinctiveness

#### BrandFlow
- **Проблема**: Звучит слишком линейно, ADI — это итеративный процесс
- **Причина отклонения**: "Flow" подразумевает однонаправленное движение, а не цикл
- **Оценка**: Lower semantic fidelity к циклической природе

#### GrowthLoop
- **Проблема**: Неясно, что именно растёт (бренд? сеть? влияние?)
- **Причина отклонения**: Отсутствует явный бренд-фокус
- **Оценка**: Higher operational ambiguity

#### BrandArc
- **Проблема**: Подразумевает линейное повествование с началом и концом
- **Причина отклонения**: ADI — это непрерывный процесс, а не конечная дуга
- **Оценка**: Cognitive dissonance с фактической практикой

#### ImpactCycle
- **Проблема**: "Impact" — слишком широкое понятие, может означать что угодно
- **Причина отклонения**: Отсутствует бренд-специфическая семантика
- **Оценка**: Higher alias risk с другими фреймворками

## CardMode

**MintNew** — создание нового термина, не существовавшего ранее в контексте NDPB.

## Оценка по осям

| Ось | Значение | Обоснование |
|-----|----------|-------------|
| **Semantic Fidelity** | 0.95 | Прямо передаёт суть — это цикл (loop) для развития бренда. Слово "loop" акцентирует итеративную природу ADI |
| **Cognitive Ergonomics** | 0.90 | Два слога, простая структура (Brand+Loop), легко запомнить и произнести |
| **Operational Affordance** | 0.85 | Название сразу подсказывает действие — это не статическое понятие, а процесс |
| **Alias Risk** | 0.20 | Достаточно уникальная комбинация, минимизирует риск путаницы |

## Rationale (Обоснование выбора)

BrandLoop выбран как оптимальное компромиссное решение по всем осям FPF:

1. **Semantic Fidelity (0.95)**: Прямо передаёт суть — это цикл (loop) для развития бренда. Слово "loop" акцентирует итеративную природу ADI, что критически важно для понимания процесса.

2. **Cognitive Ergonomics (0.90)**: Два слога, простая структура (Brand+Loop), легко запомнить и произнести. Не вызывает когнитивной нагрузки у маркетинговой аудитории.

3. **Operational Affordance (0.85)**: Название сразу подсказывает действие — это не статическое понятие, а процесс, который можно "запустить", "оптимизировать", "ускорить".

4. **Alias Risk (0.20)**: Достаточно уникальная комбинация, минимизирует риск путаницы с другими брендинговыми фреймворками.

## Рассмотренные альтернативы

### Прямые ADI-термины
- **Отклонены**: Too technical, not marketing-friendly
- **Проблема**: Significantly fails Cognitive Ergonomics axis

### Метафорические названия
- "BrandRocket", "BrandEngine": Too hype, low semantic fidelity
- "BrandSeed", "BrandTree": Growth metaphors, miss ADI specificity

### Action-oriented
- "BuildBrand", "GrowBrand": Too generic, higher alias risk
- "BrandAction", "BrandMove": Miss the cyclical nature

## Заметки по реализации

BrandLoop следует использовать в следующих контекстах:

### Название модулей/уроков программы
- "BrandLoop 1.0: Первое впечатление"
- "BrandLoop 2.0: Укрепление доверия"
- "BrandLoop 3.0: Масштабирование влияния"

### Документация процессов
- "Implementing BrandLoop on LinkedIn"
- "BrandLoop Optimization Techniques"
- "Measuring BrandLoop Effectiveness"

### Метрики прогресса
- "Complete 10 BrandLoops per month"
- "BrandLoop Conversion Rate"
- "BrandLoop Cycle Time"

### Маркетинговые материалы
- "Master the BrandLoop for exponential brand growth"
- "Accelerate your brand with our BrandLoop framework"
- "The BrandLoop: A proven three-step method"

## Связь с FPF паттернами

### B.5 — ADI Cycle
BrandLoop — это маркетинговое название для реализации паттерна B.5:

| BrandLoop Phase | ADI Phase | Action |
|-----------------|-----------|--------|
| **Show Up** | Abduction | Generate signals (profile, headline, content) |
| **Prove It** | Deduction | Validate through experience (quality content, engagement) |
| **Lock It In** | Induction | Consolidate pattern (consistent behavior, repeated value delivery) |

### A.7 — Strict Distinction
BrandLoop чётко различает:
- **Сигнал** (Signal) — входное сообщение/контент
- **Опыт** (Experience) — взаимодействие с контентом
- **Паттерн** (Pattern) — закреплённая когнитивная модель

### A.1.1 — Bounded Context
Каждый BrandLoop привязан к конкретному контексту:
- Локальный (индивидуальный контакт)
- Мезо (социальная группа/сеть)
- Макро (рынок/индустрия)

## Дополнительные ресурсы

- [LinkedIn Branding & Networking Analysis](../0.5. AI-Reports/analysis-linkedin-branding-networking-2026-01-13-ru.md)
- [Personal Brand Definition Analysis](personal-brand-definition-analysis.2026-01-12.md)
- [FPF Integration Guide](../0.6. FPF-Integration/fpf-integration.md)

## Следующие шаги

- [ ] Интегрировать BrandLoop в системное описание NDPB
- [ ] Создать операционные плейбуки для каждого этапа BrandLoop
- [ ] Разработать метрики эффективности BrandLoop
- [ ] Создать маркетинговые материалы с использованием BrandLoop
- [ ] Тестировать BrandLoop с пилотной аудиторией
