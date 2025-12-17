---
tags:
  - table
  - has-formula
base: "[[bases/expat-student/index|Expat Student]]"
table_id: tbl1ADP4zZllvOkBj
---

# Schedules

> Ders programları ve session yönetimi.

## 📋 Table Info

| Property | Value |
|----------|-------|
| Table ID | `tbl1ADP4zZllvOkBj` |
| Base | [[bases/expat-student/index|Expat Student]] |

## 📊 Fields

### Time

| Field | Type | Description |
|-------|------|-------------|
| Session Date | [[reference/field-types#date\|date]] | Tarih |
| Start Time | [[reference/field-types#singleLineText\|singleLineText]] | Başlangıç |
| End Time | [[reference/field-types#singleLineText\|singleLineText]] | Bitiş |
| Session Duration | [[reference/field-types#formula\|formula]] | [[#Formula: Duration\|Dakika]] |
| Session Status | [[reference/field-types#formula\|formula]] | [[#Formula: Status\|Completed/Upcoming]] |

### Session Info

| Field | Type | Description |
|-------|------|-------------|
| Course | [[reference/field-types#singleLineText\|singleLineText]] | Kurs adı |
| Location | [[reference/field-types#singleLineText\|singleLineText]] | Lokasyon |
| Session Type | [[reference/field-types#singleSelect\|singleSelect]] | [[#Session Types\|Tip]] |

### Links

| Field | Type | Description |
|-------|------|-------------|
| Instructor | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/instructors\|Instructors]] |
| Enrollments | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/enrollments\|Enrollments]] |
| Number of Enrollments | [[reference/field-types#count\|count]] | Kayıt sayısı |

### Lookups

| Field | Type | Source |
|-------|------|--------|
| Course Name | [[reference/field-types#lookup\|lookup]] | - |
| Instructor Name | [[reference/field-types#lookup\|lookup]] | Instructors.Instructor Name |

### Session Types

| Option | Color |
|--------|-------|
| Lecture | 🔵 Blue |
| Workshop | 🔵 Cyan |
| Seminar | 🔵 Teal |

## 📐 Formulas

### Formula: Duration

```
DATETIME_DIFF({End Time}, {Start Time}, 'minutes')
```

### Formula: Status

```
IF(IS_BEFORE({Session Date}, TODAY()), 'Completed', 'Upcoming')
```

## 📌 Related

- [[bases/expat-student/index|← Back to Expat Student]]
- [[bases/expat-student/tables/instructors|Instructors]]
- [[bases/expat-student/tables/enrollments|Enrollments]]