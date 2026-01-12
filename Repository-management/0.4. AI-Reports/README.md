---
system: "Management"
title: "AI-Reports (Improved Template)"
date: "2026-01-12"
tags: [management, ai, reports, automation, template]
status: "active"
related:
  - ../README.md
  - ../0.2.%20Domain/frontmatter-spec.md
fpf_principles:
  - automation
  - transparency
  - clarity
fpf_patterns:
  - B.3      # Trust Calculus
  - B.5      # Cycle ADI
---

# 0.4. AI-Reports (Улучшенный шаблон)

## Purpose of this section

This section contains **automatically generated reports** by AI agents regarding state of repository, document quality, and verification results.

**Key question:** What did AI do? What is the state of the repository? What actions should be taken?

---

## 🎯 Decision Framework: Report Depth

**How AI agents decide between Quick Review vs Detailed Report**

### Priority 1: Explicit User Instructions (Highest Priority)

**Quick Review Requests:**
- Keywords: "quick review", "quick check", "быстро проверь", "кратко", "short summary", "high level"
- Examples:
  - "Quick review of frontmatter"
  - "Быстро проверь документы на ошибки"
  - "Brief summary of recent changes"

**Detailed Report Requests:**
- Keywords: "detailed analysis", "deep dive", "comprehensive", "полный анализ", "подробно", "full report"
- Examples:
  - "Detailed analysis of Planora structure"
  - "Полный анализ соответствия FPF"
  - "Comprehensive comparison with reference project"

### Priority 2: Contextual Signals

**Use Quick Review When:**
- 📅 Daily/repetitive request
- ⚡ Time-sensitive ("ASAP", "срочно")
- 📊 Routine check (e.g., daily status check)
- 🔁 Frequent task (more than once per week)
- ✅ Validation after minor changes

**Use Detailed Report When:**
- 🔬 New area of investigation
- 🎯 Important decision-making ("decide between X and Y")
- 📈 Analyzing problems or incidents
- 🔗 Comparing systems/versions
- 💡 Research for planning
- ⚠️ Critical issues discovered

### Priority 3: Report Type Defaults

| Report Type | Default Depth | When to Override |
|------------|----------------|------------------|
| Document Quality | Quick Review | Critical issues found → Detailed |
| Table Coverage | Quick Review | Significant change (>10% progress) → Detailed |
| Broken Links | Quick Review | Many broken links (>5) → Detailed |
| FPF Compliance | **Always Detailed** | N/A |
| Analysis/Comparison | **Always Detailed** | N/A |
| Changelog/Update | Quick Review | Major release → Detailed |
| System Identification | **Always Detailed** | N/A |

### Priority 4: Volume & Complexity

**Quick Review (≤ 10 files, simple task):**
- Only Executive Summary
- Critical issues only
- Top 3 recommendations
- **Estimated time:** 2-5 minutes

**Medium Report (10-50 files, moderate complexity):**
- Executive Summary
- Main template sections
- Top 5 recommendations
- Basic trends
- **Estimated time:** 5-15 minutes

**Detailed Report (> 50 files, high complexity):**
- Full template structure
- Detailed analysis by sections
- All recommendations with priorities
- Trends, metrics, comparisons
- Risk assessment
- **Estimated time:** 15-30+ minutes

### Decision Algorithm for AI Agents

```
IF user explicitly specifies depth:
    USE specified depth
ELSE IF report type in {FPF Compliance, Analysis, System ID}:
    USE Detailed Report
ELSE IF new analysis or decision-making:
    USE Detailed Report
ELSE IF file count > 50 OR critical issues found:
    USE Detailed Report
ELSE IF significant change in coverage (>10%):
    USE Detailed Report
ELSE:
    USE Quick Review
```

### Examples: Quick vs Detailed Reports

#### Example 1: Document Quality - Quick Review
```
# Document Quality Report

## 📈 Executive Summary
**Total Files Scanned:** 25
**Files Passed:** 23
**Files Failed:** 2
**Critical Issues:** 1

## 🚨 Critical Issues
| File | Issue | Severity | Action Required |
|------|--------|----------|----------------|
| `doc1.md` | FRONTMATTER_MISSING | Critical | Add frontmatter |

## 📝 Recommended Actions (Next 24h)
1. [ ] Add frontmatter to doc1.md
```

#### Example 2: Document Quality - Detailed Report
[Use full template from section #1 below]

---

## 📋 Quick Reference: Report Types

| # | Type | Description | When to Use | Default Depth | Template |
|---|------|-------------|--------------|---------------|----------|
| 1 | **Document Quality** | Frontmatter, relationships, completeness | On request | Quick | [Quality Template](#1-document-quality-report) |
| 2 | **Table Coverage** | SRT matrix completion (F1-F9) | Weekly/Monthly | Quick | [Coverage Template](#2-table-coverage-report) |
| 3 | **Broken Links** | Related and external links check | On request | Quick | [Links Template](#3-broken-links-report) |
| 4 | **FPF Compliance** | Adherence to principles/patterns | On request | **Detailed** | [Compliance Template](#4-fpf-compliance-report) |
| 5 | **Analysis/Comparison** | System analysis, comparison, research | On request | **Detailed** | [Analysis Template](#5-analysiscomparison-report) |
| 6 | **Changelog/Update** | Bulk updates, status changes | Daily/Weekly | Quick | [Changelog Template](#6-changelogupdate-report) |
| 7 | **System Identification** | Verification of system definitions | On request | **Detailed** | [System ID Template](#7-system-identification-report) |

---

## ✅ Universal Frontmatter Template

**ALL reports MUST include this frontmatter:**

```yaml
---
type: report
status: active
created: YYYY-MM-DD, hh:mm
updated: YYYY-MM-DD, hh:mm  # when modified (required for AI agents)
system: "Management"
role: "Analyst"  # or: "Manager", "Validator", "Auditor"
layer: operations
scope: project
target_audience: [administrators, contributors, developers]
related:
  - ../README.md
  - ../0.1.%20Core/glossary.md
  - ../0.1.%20Core/document-families.md
fpf_principles:
  - documentation-first
  - traceability
  - clarity
fpf_patterns:
  - B.4    # Canonical Evolution
  - [A.1, A.7]  # Add relevant patterns
author:
  - Cline
  - Antigravity
---
```

---

## 📊 Report Templates

### 1. Document Quality Report

**Use when:** Validating frontmatter, checking completeness, verifying relationships.

```markdown
# Document Quality Report

## 📅 Metadata
**Date:** YYYY-MM-DD
**Scope:** [Path or "All files in content/"]
**Author:** [AI Agent Name]

---

## 📈 Executive Summary

**Total Files Scanned:** X
**Files Passed:** X
**Files Failed:** X
**Critical Issues:** X
**Warnings:** X

**Overall Status:** ✅ Good / ⚠️ Needs Attention / ❌ Critical

---

## 🚨 Critical Issues

| File | Issue | Severity | Action Required |
|------|--------|----------|----------------|
| `path/to/file.md` | FRONTMATTER_MISSING | Critical | Add frontmatter |
| `path/to/file.md` | TYPE_INVALID | Critical | Fix type field |
| `path/to/file.md` | SYSTEM_MISMATCH | High | Update system field |

---

## ⚠️ Warnings (Non-Critical)

| File | Issue | Severity | Suggestion |
|------|--------|----------|------------|
| `path/to/file.md` | DATE_OLD | Medium | Update updated field |
| `path/to/file.md` | RELATED_MISSING | Low | Add related links |

---

## ✅ Validation Results by Rule

### Rule 1: Frontmatter Presence
- ✅ Passed: X files
- ❌ Failed: X files

### Rule 2: Type Field Validity
- ✅ Passed: X files
- ❌ Failed: X files
  - Invalid values found: `xyz`, `abc`

[... continue for all rules ...]

---

## 🔍 Detailed Findings

### File Analysis
[Group by directory or issue type]

#### content/1.System/
- ✅ `README.md` — All fields valid
- ⚠️ `doc1.md` — Missing `updated` field
- ❌ `doc2.md` — Invalid system: "Management" (should be "System-of-Interest")

#### content/2.System-of-Interest/
[...]

---

## 📝 Recommended Actions

### Immediate (Next 24h)
1. [ ] Fix frontmatter for X critical files
2. [ ] Update system fields for X files
3. [ ] Add missing related links

### Short-term (This Week)
1. [ ] Document all missing files
2. [ ] Create frontmatter templates for new files

### Long-term (This Month)
1. [ ] Implement automated checks
2. [ ] Create documentation for common issues

---

## 📎 Related Documents
- [Frontmatter Spec](../0.2.%20Domain/frontmatter-spec.md)
- [Document Families](../0.1.%20Core/document-families.md)
```

---

### 2. Table Coverage Report

**Use when:** Measuring progress on SRT matrix (F1-F9 coverage).

```markdown
# SRT Matrix Coverage Report

## 📅 Metadata
**Date:** YYYY-MM-DD
**Period:** [Last week / This month / Since start]
**Total Documents:** X

---

## 📊 Executive Summary

**Overall Coverage:** X% (Y/Z cells filled)
**New Documents This Period:** X
**Progress vs Last Report:** +X documents

**Coverage by System:**
- F1-F3 (Suprasystem): X%
- F4-F6 (System-of-Interest): X%
- F7-F9 (Constructor): X%

---

## 📈 Coverage Matrix

| System | Meaning | Architecture | Operations | Total |
|--------|---------|-------------|------------|-------|
| **F1-F3** (Suprasystem) | X/Y (X%) | X/Y (X%) | X/Y (X%) | X/9 (X%) |
| **F4-F6** (SoI) | X/Y (X%) | X/Y (X%) | X/Y (X%) | X/9 (X%) |
| **F7-F9** (Constructor) | X/Y (X%) | X/Y (X%) | X/Y (X%) | X/9 (X%) |
| **Total** | X/9 (X%) | X/9 (X%) | X/9 (X%) | **X/27 (X%)** |

---

## 🎯 Family-Level Detail

### F1-F3: Suprasystem

#### F1: Suprasystem × Entrepreneur (Context)
- ✅ `README.md` — Basic description
- ✅ `market-analysis.md` — Market research
- 🔲 `competitors.md` — Missing
**Status:** X% complete

#### F2: Suprasystem × Engineer (Environment)
[...]

#### F3: Suprasystem × Manager (Partnerships)
[...]

### F4-F6: System-of-Interest
[...]

### F7-F9: Constructor
[...]

---

## 🆕 New Documents This Period

| Path | Family | Description | Impact |
|------|---------|-------------|--------|
| `path/to/new-doc.md` | F4.1 | User requirements | High |
| `path/to/new-doc.md` | F5.2 | API architecture | Medium |

---

## 📈 Trends

### Coverage Over Time

| Period | F1-F3 | F4-F6 | F7-F9 | Total |
|--------|-------|-------|-------|-------|
| Week 1 | 10% | 15% | 5% | 10% |
| Week 2 | 20% | 25% | 10% | 18% |
| Week 3 | 30% | 35% | 20% | 28% |
| **Current** | **X%** | **X%** | **X%** | **X%** |

---

## 🎯 Goals vs Actual

| Goal | Target | Current | Gap | Status |
|------|--------|---------|-----|--------|
| Meaning cells (F1, F4, F7) | 9/9 filled | X/9 | Y | 🔲 Not Met |
| Architecture cells (F2, F5, F8) | 9/9 filled | X/9 | Y | 🔲 Not Met |
| Operations cells (F3, F6, F9) | 9/9 filled | X/9 | Y | 🔲 Not Met |

---

## 📝 Recommended Next Steps

1. **Priority 1:** Fill empty Meaning cells (F1.1, F4.1, F7.1)
2. **Priority 2:** Create missing F4.2 documents (Architecture)
3. **Priority 3:** Document F7.3 (Operations)

---

## 📎 Related Documents
- [Document Families](../0.1.%20Core/document-families.md)
- [Project Roadmap](../0.3. Plans-and-Meetings/)
```

---

### 3. Broken Links Report

**Use when:** Checking `related` fields and external links.

```markdown
# Broken Links Report

## 📅 Metadata
**Date:** YYYY-MM-DD
**Total Links Checked:** X
**Broken Links:** X
**Broken External Links:** X

---

## 🚨 Broken Internal Links

| Source File | Link | Target | Error | Fix |
|-------------|------|--------|-------|-----|
| `doc1.md` | `../glossary.md` | Not found | Create or remove link |
| `doc2.md` | `./missing.md` | Not found | Update path |

---

## ⚠️ Broken External Links

| Source File | URL | Error | Last Checked | Fix |
|-------------|-----|-------|--------------|-----|
| `doc1.md` | `https://example.com` | 404 | 2026-01-12 | Update URL |
| `doc2.md` | `https://dead.link` | Timeout | 2026-01-12 | Remove or fix |

---

## 🔍 Orphaned Documents

Documents with NO `related` links pointing TO them:

| Document | Suggested Links From |
|----------|-------------------|
| `island-doc.md` | Should be linked from: `doc1.md`, `doc2.md` |

---

## 📝 Recommended Actions

### Immediate
1. [ ] Fix X broken internal links
2. [ ] Remove/fix X broken external links
3. [ ] Add related links to orphaned documents

### Preventive
1. [ ] Set up automated link checking in CI/CD
2. [ ] Document URL management policy
```

---

### 4. FPF Compliance Report

**Use when:** Auditing adherence to FPF principles and patterns.

```markdown
# FPF Compliance Audit

## 📅 Metadata
**Date:** YYYY-MM-DD
**Scope:** [All documents / Specific path]
**Total Audited:** X documents

---

## 📊 Compliance Summary

| Principle | Compliant | Partial | Non-Compliant | Coverage |
|-----------|-----------|----------|----------------|----------|
| A.1 (Holonic Foundation) | X | Y | Z | X% |
| A.1.1 (Bounded Context) | X | Y | Z | X% |
| A.3 (Transformer Constitution) | X | Y | Z | X% |
| A.7 (Strict Distinction) | X | Y | Z | X% |
| B.3 (Trust Calculus) | X | Y | Z | X% |

**Overall FPF Compliance:** X%

---

## 🔍 Detailed Analysis

### A.1: Holonic Foundation

**Requirement:** System boundaries clearly defined, nested levels identified

#### ✅ Compliant Documents
- `doc1.md` — Clear system boundaries
- `doc2.md` — Proper holon structure

#### ⚠️ Partially Compliant
- `doc3.md` — System defined but suprasystem unclear
  - **Issue:** Suprasystem described as "market" (should be specific system)
  - **Recommendation:** Define actual suprasystem (e.g., "Professional Environment")

#### ❌ Non-Compliant
- `doc4.md` — No system definition found
  - **Issue:** Missing system boundaries
  - **Action:** Add system definition section

[... continue for each pattern ...]

---

## 📈 Trends

### FPF Compliance Over Time

| Date | A.1 | A.1.1 | A.3 | B.3 | Overall |
|------|-----|-------|-----|-----|---------|
| 2026-01-01 | 60% | 50% | 40% | 70% | 55% |
| 2026-01-08 | 70% | 65% | 50% | 75% | 65% |
| 2026-01-12 | **X%** | **X%** | **X%** | **X%** | **X%** |

---

## 📝 Improvement Plan

### Priority 1: Critical FPF Violations
1. [ ] Fix A.1 violations in X documents
2. [ ] Add suprasystem definitions to Y documents

### Priority 2: Pattern Documentation
1. [ ] Create FPF pattern templates
2. [ ] Add FPF examples to glossary

---

## 📎 Related Documents
- [FPF Spec](../../.fpf/FPF-Spec.md)
- [System Identification](../0.1.%20Core/system-identification.md)
```

---

### 5. Analysis/Comparison Report

**Use when:** Comparing versions, systems, reference repositories, or conducting research.

```markdown
# Analysis: [Title]

## 📅 Metadata
**Date:** YYYY-MM-DD
**Type:** [Comparison / Research / Deep Dive]
**Analyst:** [Name]
**Duration:** [e.g., "2 hours"]

---

## 📝 Executive Summary

**Objective:** [What was analyzed and why]

**Key Findings:**
1. [Finding 1 — 1 sentence]
2. [Finding 2 — 1 sentence]
3. [Finding 3 — 1 sentence]

**Conclusion:** [One paragraph summary]

---

## 🔬 Research Scope

**What was analyzed:**
- [ ] Document structure
- [ ] System definitions
- [ ] Frontmatter patterns
- [ ] Folder organization
- [ ] [Other aspects]

**Sources:**
- Source A: [Link or description]
- Source B: [Link or description]
- [Additional sources]

---

## 📊 Comparison Matrix

| Aspect | Option A | Option B | Winner / Notes |
|---------|----------|----------|----------------|
| Structure | Description | Description | Option A |
| Complexity | High | Low | Option B |
| Scalability | High | Medium | Option A |
| Maintenance | Difficult | Easy | Option B |

---

## 🔍 Deep Dive Analysis

### Topic 1: [Aspect Name]

**Observation:**
[Detailed description of what was observed]

**Implications:**
[What this means for the project]

> 💡 **FPF Insight:** (Optional) Link to FPF principle
> Pattern A.1 applies here because...

**Examples:**
- Example from Source A: [description]
- Example from Source B: [description]

### Topic 2: [Aspect Name]
[Continue structure...]

---

## 🎯 Critical Decisions Required

| Decision | Options | Recommendation | Rationale |
|----------|---------|----------------|------------|
| Choice 1 | A vs B vs C | Option A | Because... |
| Choice 2 | X vs Y | Option Y | Because... |

---

## 📝 Recommendations

### Immediate Actions
1. **[Action 1]:** [Details and why urgent]
2. **[Action 2]:** [Details and why urgent]

### Short-term Plan
1. **[Action 3]:** [Timeline and resources]
2. **[Action 4]:** [Timeline and resources]

### Long-term Considerations
1. **[Strategic Point 1]:** [Rationale]
2. **[Strategic Point 2]:** [Rationale]

---

## 🚦 Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|---------|------------|
| Risk 1 | High | High | [Mitigation strategy] |
| Risk 2 | Medium | Low | [Mitigation strategy] |

---

## 📎 References & Sources
- [Document A](path/to/doc)
- [Document B](path/to/doc)
- [External Source](URL)

## 🔗 Related Analyses
- [Previous Analysis](./report-previous.md)
- [Complementary Report](./related-report.md)
```

---

### 6. Changelog/Update Report

**Use when:** Reporting daily/weekly progress, bulk updates, or status changes.

```markdown
# Changelog: [Update Name or Period]

## 📅 Metadata
**Date:** YYYY-MM-DD
**Period:** [Daily / Weekly / Specific update]
**Author:** [Name]
**Type:** [Progress / Bulk Update / Status Change]

---

## 📊 Executive Summary

**Overview:** [1-2 sentence summary of what changed]

**Key Stats:**
- Files Updated: X
- New Documents Created: X
- Bugs/Issues Fixed: X
- Improvements: X

---

## 📝 Detailed Changes

### Section 1: [Category Name]

#### ✅ Completed
- [x] **File A:** [Description of change]
  - Impact: [High/Medium/Low]
  - Related: [Link or issue]

- [x] **File B:** [Description of change]
  - Impact: [High/Medium/Low]

#### 🔲 In Progress
- [ ] **Task C:** [Status and blockers]
  - ETA: [Date]

#### ❌ Blocked
- [ ] **Task D:** [Reason for blockage]
  - Blocked by: [Resource/Decision/External]

### Section 2: [Category Name]
[Continue structure...]

---

## 📈 Before vs After

### Structure Changes
If terminology or structure changed significantly:

| Aspect | Before | After | Impact |
|---------|--------|-------|--------|
| Folder Name | `Old-Name` | `New-Name` | Breaking change for links |
| System Definition | Old definition | New definition | Aligns with FPF |

### Metrics Comparison
If measurable:

| Metric | Before | After | Change |
|--------|--------|-------|--------|
| Document Count | 50 | 55 | +10% |
| Frontmatter Compliance | 70% | 90% | +20% |
| Coverage | 40% | 45% | +5% |

---

## 🎯 Achievements This Period

1. **[Achievement 1]:** [Impact and significance]
2. **[Achievement 2]:** [Impact and significance]
3. **[Achievement 3]:** [Impact and significance]

---

## ⚠️ Issues & Blockers

### Issues Discovered
| Issue | Severity | Owner | Status |
|-------|----------|--------|--------|
| Issue description | High/Med/Low | [Name] | Open/In Progress |

### Blockers
| Blocker | Impact | Required Action |
|---------|--------|-----------------|
| Blocked by X | Can't proceed with Y | Need decision/resource |

---

## 📝 Next Steps (Action Items)

### Immediate (Next 24h)
1. [ ] [Action item] - [Owner]
2. [ ] [Action item] - [Owner]

### This Week
1. [ ] [Action item] - [Owner]
2. [ ] [Action item] - [Owner]

### This Month
1. [ ] [Action item] - [Owner]
2. [ ] [Action item] - [Owner]

---

## 📎 Related Documents
- [Previous Changelog](./changelog-previous-date.md)
- [Affected Documents](../path/to/docs/)
```

---

### 7. System Identification Report

**Use when:** Verifying system definitions comply with system-identification.md rules.

```markdown
# System Identification Audit

## 📅 Metadata
**Date:** YYYY-MM-DD
**Auditor:** [AI Agent Name]
**Documents Checked:** X

---

## 📊 Compliance Summary

| System | Status | Issues | Severity |
|---------|--------|---------|----------|
| System-of-Interest | ✅ Compliant / ⚠️ Needs Review / ❌ Non-Compliant | X | High/Med/Low |
| Suprasystem | ✅ / ⚠️ / ❌ | X | High/Med/Low |
| Constructor | ✅ / ⚠️ / ❌ | X | High/Med/Low |

---

## 🔍 Detailed Audit

### System-of-Interest

**Definition Found:** [Quote from document]

#### ✅ Checks Passed
- [x] Physical object or state (not a process)
- [x] Can be measured or "touched"
- [x] Not confused with creator
- [x] Clear boundaries defined

#### ⚠️ Issues Found
- [ ] Issue 1: [Description]
  - **Example from doc:** [Quote]
  - **Rule violated:** [Reference to system-identification.md]
  - **Recommendation:** [How to fix]

#### ❌ Critical Violations
- [ ] Issue 2: [Description]
  - **Example from doc:** [Quote]
  - **Rule violated:** [Reference]
  - **Must Fix:** [Urgent action required]

---

### Suprasystem

**Definition Found:** [Quote from document]

#### ✅ Checks Passed
- [x] SoI is part of it (composition)
- [x] Not confused with market or context
- [x] Interaction interface described
- [x] Clear system boundaries

#### ⚠️ Issues Found
[Use same structure as SoI section]

---

### Constructor

**Definition Found:** [Quote from document]

#### ✅ Checks Passed
- [x] Composition clear: people + tools + methods
- [x] Result of work is clear
- [x] Realistic capabilities

#### ⚠️ Issues Found
[Use same structure as SoI section]

---

## 📈 Glossary Compliance

**Terminology Check:**
- [ ] Uses terms from [glossary.md](../0.1.%20Core/glossary.md)
- [ ] Systems correspond to variables: `Constructor → Product → User → Result → Environment`
- [ ] No invented terms without definition

### Term Mismatches Found
| Term Used | Correct Term | Location | Suggestion |
|-----------|-------------|----------|------------|
| "Market" | "Suprasystem Context" | doc1.md | Update to be precise |
| "Creator" | "Constructor" | doc2.md | Use standard term |

---

## 💡 FPF Pattern Alignment

### Pattern A.1: Holonic Foundation
- ✅ SoI, Suprasystem, Constructor all defined
- ⚠️ Holon relationships need clarification
- Recommendation: [Specific suggestion]

### Pattern A.1.1: Bounded Context
- ✅ System boundaries clear
- ❌ Context vs Suprasystem confusion
- Recommendation: [Specific suggestion]

[Continue for other relevant patterns...]

---

## 📝 Recommendations

### Critical (Must Fix Before Proceeding)
1. **[Issue]:** [Details and why critical]
   - Affected documents: [List]
   - Expected impact: [If not fixed]

### Important (Should Fix This Week)
1. **[Issue]:** [Details]
2. **[Issue]:** [Details]

### Nice to Have (Next Iteration)
1. **[Improvement]:** [Details]

---

## 📎 References
- [System Identification Rules](../0.1.%20Core/system-identification.md)
- [Glossary](../0.1.%20Core/glossary.md)
- [FPF Spec](../../.fpf/FPF-Spec.md)
```

---

## 🎯 Best Practices for AI Agents

### Before Writing a Report

1. **Understand the Goal:**
   - What is the report's purpose?
   - Who will read it?
   - What action should they take?

2. **Gather All Information:**
   - Read all relevant documents
   - Check for existing related reports
   - Note patterns and trends

3. **Choose the Right Template:**
   - Match template to report type
   - Don't force-fit into wrong template
   - Can mix elements if needed

### While Writing the Report

4. **Use Visual Structure:**
   - 📅 Metadata sections clearly marked
   - 📊 Use tables for comparisons
   - ✅ Use checklists for status
   - 🚨 Highlight critical issues
   - 💡 Use callouts for insights

5. **Be Specific:**
   - Include exact file paths
   - Quote problematic sections
   - Provide concrete recommendations

6. **Prioritize Actions:**
   - Distinguish Immediate vs Short-term vs Long-term
   - Assign ownership where possible
   - Include impact level

7. **Link Everything:**
   - Use `related:` in frontmatter
   - Link to related documents in text
   - Reference FPF patterns when applicable

### After Writing the Report

8. **Self-Review Checklist:**
   - [ ] Frontmatter complete and valid?
   - [ ] Executive summary clear?
   - [ ] Critical issues highlighted?
   - [ ] Recommendations actionable?
   - [ ] Related documents linked?
   - [ ] Tables properly formatted?
   - [ ] No broken internal links?

9. **File Naming Convention:**
   ```
   type-author-date-sequence.md
   
   Where:
   - type: Report type (quality, coverage, links, fpf, analysis, changelog, system-id)
   - author: AI agent name (cline, antigravity, etc.)
   - date: YYYY-MM-DD format
   - sequence: Three-digit counter (001, 002, etc.) for same day reports
   
   Examples:
   - quality-cline-2026-01-12-001.md
   - coverage-cline-2026-01-12-002.md
   - fpf-antigravity-2026-01-12-001.md
   - analysis-cline-2026-01-13-001.md
   - changelog-cline-2026-01-13-daily.md  # Special case for recurring reports
   
   IMPORTANT: Always check existing files in the directory to avoid conflicts!
   Use the next available sequence number for the same author/date/type combination.
   ```

10. **Update Coverage Report:**
    - If new documents created, update coverage stats
    - Link from coverage report to new report

---

## 🔄 Automated Commands

### For AI Agents

```
# Quality Check
Check all documents in content/ for frontmatter compliance
and generate a quality report in "0.4. AI-Reports/"

# Coverage Analysis
Generate a table coverage report showing progress
for all SRT families (F1-F9)

# Link Verification
Check all related and external links in the repository
and report broken ones

# System Identification Audit
Verify all system definitions comply with
system-identification.md rules

# FPF Compliance
Audit documents for FPF principle and pattern compliance
```

---

## 📎 Related Documents

- [Management Section](../README.md)
- [Frontmatter Spec](../0.2. Domain/frontmatter-spec.md)
- [Document Families](../0.1. Core/document-families.md)
- [System Identification](../0.1. Core/system-identification.md)
- [Glossary](../0.1. Core/glossary.md)
- [FPF Spec](../../.fpf/FPF-Spec.md)

---

## 📝 Changelog

| Date | Change | Author |
|------|--------|--------|
| 2026-01-08 | Initial template | Original |
| 2026-01-12 | Major improvements: Added 7 specific templates, visual structure, best practices | Cline |

---

*Template Version: 2.0 | Last Updated: 2026-01-12*
