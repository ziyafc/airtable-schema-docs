---
tags:
  - table
  - field-type/checkbox
base: "[[bases/expat-student/index|Expat Student]]"
table_id: tbloZt35vRi7Q5ZUu
---

# Assessments

> Öğrenci değerlendirmeleri.

## 📋 Table Info

| Property | Value |
|----------|-------|
| Table ID | `tbloZt35vRi7Q5ZUu` |
| Base | [[bases/expat-student/index|Expat Student]] |

## 📊 Fields

| Field | Type | Description |
|-------|------|-------------|
| Assessment ID | [[reference/field-types#singleLineText\|singleLineText]] | Unique ID |
| Student | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/students\|Students]] |
| Course | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/courses\|Courses]] |
| Assessment Date | [[reference/field-types#date\|date]] | Tarih |
| Score | [[reference/field-types#number\|number]] | Puan (precision: 2) |
| Feedback | [[reference/field-types#multilineText\|multilineText]] | Geri bildirim |
| Assessment Type | [[reference/field-types#singleSelect\|singleSelect]] | [[#Assessment Types\|Tip]] |
| Completion Status | [[reference/field-types#checkbox\|checkbox]] | Tamamlandı mı |

### Assessment Types

| Option | Color |
|--------|-------|
| Written Exam | 🔵 Blue |
| Oral Exam | 🔵 Cyan |
| Project | 🔵 Teal |
| Participation | 🟢 Green |

## 📌 Related

- [[bases/expat-student/index|← Back to Expat Student]]
- [[bases/expat-student/tables/students|Students]]
- [[bases/expat-student/tables/courses|Courses]]