---
tags:
  - table
  - has-formula
  - field-type/formula
  - field-type/multipleRecordLinks
base: "[[bases/expat-student/index|Expat Student]]"
table_id: tblqLbVNQQbE05gU4
---

# Students

> Öğrenci profilleri ve enrollment tracking.

## 📋 Table Info

| Property | Value |
|----------|-------|
| Table ID | `tblqLbVNQQbE05gU4` |
| Base | [[bases/expat-student/index|Expat Student]] |
| Formulas | ✅ Full Name, Age, Total Courses |

## 📊 Fields

### Identity

| Field | Type | Description |
|-------|------|-------------|
| Student ID | [[reference/field-types#singleLineText\|singleLineText]] | Unique ID |
| First Name | [[reference/field-types#singleLineText\|singleLineText]] | Ad |
| Last Name | [[reference/field-types#singleLineText\|singleLineText]] | Soyad |
| Full Name | [[reference/field-types#formula\|formula]] | [[#Formula: Full Name\|Calculated]] |
| Profile Photo | [[reference/field-types#multipleAttachments\|multipleAttachments]] | Profil fotoğrafı |

### Contact

| Field | Type | Description |
|-------|------|-------------|
| Email Address | [[reference/field-types#singleLineText\|singleLineText]] | E-posta |
| Phone Number | [[reference/field-types#singleLineText\|singleLineText]] | Telefon |

### Demographics

| Field | Type | Description |
|-------|------|-------------|
| Date of Birth | [[reference/field-types#date\|date]] | Doğum tarihi |
| Age | [[reference/field-types#formula\|formula]] | [[#Formula: Age\|Calculated]] |
| Nationality | [[reference/field-types#singleLineText\|singleLineText]] | Uyruk |

### Enrollment

| Field | Type | Description |
|-------|------|-------------|
| Enrollment Date | [[reference/field-types#date\|date]] | Kayıt tarihi |
| Courses Enrolled | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/courses\|Courses]] |
| Enrollment Records | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/enrollments\|Enrollments]] |
| Total Courses Enrolled | [[reference/field-types#count\|count]] | Kurs sayısı |
| Current Progress | [[reference/field-types#rollup\|rollup]] | İlerleme |
| Assessments | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/assessments\|Assessments]] |

## 📐 Formulas

### Formula: Full Name

```
{First Name} & ' ' & {Last Name}
```

**Output:** `singleLineText`

### Formula: Age

```
DATETIME_DIFF(TODAY(), {Date of Birth}, 'years')
```

**Output:** `number` (precision: 0)

## 🔗 Relationships

| Linked To | Field | Relationship |
|-----------|-------|-------------|
| [[bases/expat-student/tables/courses\|Courses]] | Courses Enrolled | Many-to-many |
| [[bases/expat-student/tables/enrollments\|Enrollments]] | Enrollment Records | One-to-many |
| [[bases/expat-student/tables/assessments\|Assessments]] | Assessments | One-to-many |

## 📌 Related

- [[bases/expat-student/index|← Back to Expat Student]]
- [[bases/expat-student/tables/enrollments|Enrollments]]
- [[bases/expat-student/tables/courses|Courses]]