# Untitled Base

**Base ID:** `appg5FhzhGeUrEjve`  
**Permission Level:** Create

## Overview

Development/staging version of the learning platform database. Simplified structure compared to the main app base.

---

## Tables

### 1. Users

**Table ID:** `tbl1r15vHh4nW3Xjo`

| Field | Type | Notes |
|-------|------|-------|
| Name | `singleLineText` | - |
| Notes | `multilineText` | - |
| Assignee | `singleCollaborator` | - |
| Status | `singleSelect` | Todo, In progress, Done |
| Courses | `multipleRecordLinks` | -> Courses |
| Email | `singleLineText` | - |
| Progress | `multipleRecordLinks` | -> Progress |
| Lessen | `lookup` | Lessons from Courses |

---

### 2. Courses

**Table ID:** `tblmSLMsyy2GxPVO7`

| Field | Type | Notes |
|-------|------|-------|
| Name | `singleLineText` | - |
| Notes | `multilineText` | - |
| Assignee | `singleCollaborator` | - |
| Status | `singleSelect` | Todo, In progress, Done |
| Linked Users | `multipleRecordLinks` | -> Users |
| Email (from Linked Users) | `lookup` | - |
| Lessons | `multipleRecordLinks` | -> Lessons |

---

### 3. Clients

**Table ID:** `tbloGxTg8v8s6OsZx`

| Field | Type | Notes |
|-------|------|-------|
| Name | `singleLineText` | - |
| Notes | `multilineText` | - |
| Assignee | `singleCollaborator` | - |
| Status | `singleSelect` | Todo, In progress, Done |

---

### 4. Progress

**Table ID:** `tblfGcMDhdUQux6KH`

| Field | Type | Notes |
|-------|------|-------|
| Notes | `multilineText` | - |
| Finished | `checkbox` | - |
| Finished time | `lastModifiedTime` | Tracks when Finished toggled |
| Users | `multipleRecordLinks` | -> Users |
| Les | `multipleRecordLinks` | -> Lessons |
| Name (from Lessons) | `lookup` | - |
| Les notitie | `lookup` | Lesson notes |

---

### 5. Lessons

**Table ID:** `tblBH8VGXZ4wGKXpH`

| Field | Type | Notes |
|-------|------|-------|
| Name | `singleLineText` | - |
| Notes | `multilineText` | - |
| Assignee | `singleCollaborator` | - |
| Status | `singleSelect` | Todo, In progress, Done |
| Progress | `multipleRecordLinks` | -> Progress |
| lesson | `multipleRecordLinks` | -> Courses |

---

## Entity Relationships

```
+---------+     +---------+     +---------+
|  Users  |<--->| Courses |<--->| Lessons |
+----+----+     +---------+     +----+----+
     |                               |
     +----------->+----------+<------+
                  | Progress |
                  +----------+

+---------+
| Clients | (standalone)
+---------+
```

---

## Notes

- This appears to be a simplified/development version of the main app database
- Clients table is not linked to other tables
- Missing: Tests, Chats, Events, User Groups compared to main base