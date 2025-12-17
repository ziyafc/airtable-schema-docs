---
tags:
  - table
  - has-formula
base: "[[bases/expat-student/index|Expat Student]]"
table_id: tblber3wEWGjCNdU6
---

# Instructors

> Eğitmen profilleri.

## 📋 Table Info

| Property | Value |
|----------|-------|
| Table ID | `tblber3wEWGjCNdU6` |
| Base | [[bases/expat-student/index|Expat Student]] |

## 📊 Fields

### Profile

| Field | Type | Description |
|-------|------|-------------|
| Instructor Name | [[reference/field-types#singleLineText\|singleLineText]] | İsim |
| Photo | [[reference/field-types#multipleAttachments\|multipleAttachments]] | Fotoğraf |
| Qualifications | [[reference/field-types#multilineText\|multilineText]] | Yetkinlikler |

### Contact

| Field | Type | Description |
|-------|------|-------------|
| Email | [[reference/field-types#singleLineText\|singleLineText]] | E-posta |
| Phone Number | [[reference/field-types#singleLineText\|singleLineText]] | Telefon |
| Contact Info | [[reference/field-types#formula\|formula]] | [[#Formula: Contact\|Combined]] |

### Assignments

| Field | Type | Description |
|-------|------|-------------|
| Assigned Courses | [[reference/field-types#singleLineText\|singleLineText]] | Atanan kurslar |
| Total Courses Assigned | [[reference/field-types#count\|count]] | Kurs sayısı |
| Average Course Level | [[reference/field-types#rollup\|rollup]] | Ortalama seviye |
| Schedules | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/schedules\|Schedules]] |
| Upcoming Sessions | [[reference/field-types#rollup\|rollup]] | Yaklaşan dersler |

## 📐 Formulas

### Formula: Contact

```
{Email} & ' / ' & {Phone Number}
```

## 📌 Related

- [[bases/expat-student/index|← Back to Expat Student]]
- [[bases/expat-student/tables/schedules|Schedules]]