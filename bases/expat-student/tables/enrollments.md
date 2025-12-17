---
tags:
  - table
  - junction-table
  - has-formula
  - field-type/formula
base: "[[bases/expat-student/index|Expat Student]]"
table_id: tbl3LE5BoyxQ60WkA
---

# Enrollments

> Junction table: Students ↔ Courses many-to-many ilişkisi.

## 📋 Table Info

| Property | Value |
|----------|-------|
| Table ID | `tbl3LE5BoyxQ60WkA` |
| Base | [[bases/expat-student/index|Expat Student]] |
| Type | Junction Table |

## 📊 Fields

### Core

| Field | Type | Description |
|-------|------|-------------|
| Enrollment ID | [[reference/field-types#singleLineText\|singleLineText]] | Kayıt ID |
| Student | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/students\|Students]] |
| Course | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/courses\|Courses]] |
| Enrollment Date | [[reference/field-types#date\|date]] | Kayıt tarihi |

### Progress

| Field | Type | Description |
|-------|------|-------------|
| Progress | [[reference/field-types#number\|number]] | 0-100 arası |
| Progress Percentage | [[reference/field-types#formula\|formula]] | [[#Formula: Progress Percentage\|Calculated]] |
| Completion Status | [[reference/field-types#singleSelect\|singleSelect]] | [[#Status Options\|Durum]] |
| Is Completed | [[reference/field-types#formula\|formula]] | [[#Formula: Is Completed\|Boolean]] |
| Days Since Enrollment | [[reference/field-types#formula\|formula]] | [[#Formula: Days Since\|Gün sayısı]] |

### Lookups

| Field | Type | Source |
|-------|------|--------|
| Student Name | [[reference/field-types#lookup\|lookup]] | Students.First Name |
| Course Name | [[reference/field-types#lookup\|lookup]] | Courses.Course Name |

### Schedule

| Field | Type | Description |
|-------|------|-------------|
| Schedule | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/schedules\|Schedules]] |

### Status Options

| Option | Color | Meaning |
|--------|-------|--------|
| Not Started | 🔵 Blue | Başlanmadı |
| In Progress | 🔵 Cyan | Devam ediyor |
| Completed | 🔵 Teal | Tamamlandı |

## 📐 Formulas

### Formula: Progress Percentage

```
{Progress} * 100
```

### Formula: Days Since Enrollment

```
DATETIME_DIFF(TODAY(), {Enrollment Date}, 'days')
```

### Formula: Is Completed

```
IF({Completion Status} = 'Completed', TRUE(), FALSE())
```

## 🔗 Relationships

```
┌──────────┐         ┌─────────────┐         ┌─────────┐
│ Students │◄───────►│ ENROLLMENTS │◄───────►│ Courses │
└──────────┘         └──────┬──────┘         └─────────┘
                            │
                            ▼
                     ┌───────────┐
                     │ Schedules │
                     └───────────┘
```

## 📌 Related

- [[bases/expat-student/index|← Back to Expat Student]]
- [[bases/expat-student/tables/students|Students]]
- [[bases/expat-student/tables/courses|Courses]]
- [[reference/patterns#User-Course Enrollment Pattern|Enrollment Pattern]]