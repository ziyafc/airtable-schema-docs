---
tags:
  - table
  - has-ai
  - field-type/aiText
  - field-type/multipleRecordLinks
base: "[[bases/expat-student/index|Expat Student]]"
table_id: tbllHRWQNJvVjdsbW
---

# Courses

> Kurs kataloğu - AI-powered summaries ile.

## 📋 Table Info

| Property | Value |
|----------|-------|
| Table ID | `tbllHRWQNJvVjdsbW` |
| Base | [[bases/expat-student/index|Expat Student]] |
| AI Fields | ✅ Course Summary, Suggested Improvement |

## 📊 Fields

| Field | Type | Description |
|-------|------|-------------|
| Course Name | [[reference/field-types#singleLineText\|singleLineText]] | Kurs adı |
| Course Level | [[reference/field-types#singleSelect\|singleSelect]] | [[#Level Options\|Seviye]] |
| Course Photo | [[reference/field-types#multipleAttachments\|multipleAttachments]] | Görsel |
| Total Enrollments | [[reference/field-types#count\|count]] | Otomatik sayım |
| Enrollments | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/enrollments\|Enrollments]] |
| Course Summary | [[reference/field-types#aiText\|aiText]] | 🤖 [[#AI: Course Summary\|AI Summary]] |
| Suggested Improvement | [[reference/field-types#aiText\|aiText]] | 🤖 [[#AI: Suggested Improvement\|AI Suggestions]] |
| Students | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/students\|Students]] |
| lessons | [[reference/field-types#singleLineText\|singleLineText]] | Ders bilgisi |
| Assessments | [[reference/field-types#multipleRecordLinks\|multipleRecordLinks]] | → [[bases/expat-student/tables/assessments\|Assessments]] |

### Level Options

| Option | Color |
|--------|-------|
| Beginner | 🔵 Blue |
| Intermediate | 🔵 Cyan |
| Advanced | 🔵 Teal |

## 🤖 AI Fields

### AI: Course Summary

**Prompt:**
> Provide a summary of the course, including the course name, the level, and the instructor's qualifications. Focus on details relevant to expat students.

**Referenced Fields:** Course Name, Course Level, Instructor Qualifications

### AI: Suggested Improvement

**Prompt:**
> Based on the total number of enrollments and the instructor's qualifications, suggest improvements to enhance the course's appeal and effectiveness for expat students.

**Referenced Fields:** Total Enrollments, Instructor Qualifications

## 🔗 Relationships

```
                    ┌─────────────────┐
    ┌──────────────►│    COURSES      │◄──────────────┐
    │               └────────┬────────┘               │
    │                        │                        │
    ▼                        ▼                        ▼
┌─────────┐           ┌─────────────┐          ┌────────────┐
│Students │           │ Enrollments │          │Assessments │
└─────────┘           └─────────────┘          └────────────┘
```

| Linked To | Field | Relationship |
|-----------|-------|-------------|
| [[bases/expat-student/tables/enrollments\|Enrollments]] | Enrollments | One-to-many |
| [[bases/expat-student/tables/students\|Students]] | Students | Many-to-many |
| [[bases/expat-student/tables/assessments\|Assessments]] | Assessments | One-to-many |

## 📌 Related

- [[bases/expat-student/index|← Back to Expat Student]]
- [[bases/expat-student/tables/enrollments|Enrollments]]
- [[bases/expat-student/tables/students|Students]]