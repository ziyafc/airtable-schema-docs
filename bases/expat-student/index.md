---
tags:
  - base
  - has-ai
base_id: appAe8WSfkPmp8P8I
permission: create
---

# Expat Student Course Management

> Comprehensive student enrollment and course management system for expat education programs.

## 📋 Base Info

| Property | Value |
|----------|-------|
| Base ID | `appAe8WSfkPmp8P8I` |
| Permission | Create |
| Tables | 6 |
| AI Fields | ✅ Yes |

## 📑 Tables

### Core Tables
- [[bases/expat-student/tables/courses|Courses]] - Kurs kataloğu
- [[bases/expat-student/tables/students|Students]] - Öğrenci bilgileri
- [[bases/expat-student/tables/instructors|Instructors]] - Eğitmenler

### Junction & Tracking
- [[bases/expat-student/tables/enrollments|Enrollments]] - Kayıt junction table
- [[bases/expat-student/tables/schedules|Schedules]] - Ders programları
- [[bases/expat-student/tables/assessments|Assessments]] - Değerlendirmeler

## 🔗 Relationship Map

```
┌──────────┐     ┌─────────────┐     ┌──────────┐
│ Students │◄───►│ Enrollments │◄───►│ Courses  │
└────┬─────┘     └──────┬──────┘     └────┬─────┘
     │                  │                 │
     │                  ▼                 │
     │           ┌──────────┐             │
     │           │Schedules │◄────────────┤
     │           └────┬─────┘             │
     │                │                   │
     │                ▼                   │
     │         ┌────────────┐             │
     │         │Instructors │             │
     │         └────────────┘             │
     │                                    │
     └────────►┌────────────┐◄────────────┘
               │Assessments │
               └────────────┘
```

## 📌 Related

- [[reference/api-ids|API IDs]]
- [[reference/patterns#User-Course Enrollment Pattern|Enrollment Pattern]]
- [[diagrams/overview|Architecture Overview]]