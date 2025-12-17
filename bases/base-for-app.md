# !!Base for App!!

**Base ID:** `apptQsmAbTKpeV2z0`  
**Permission Level:** Create

## Overview

Main application database for the Dutch language learning platform. Contains users, courses, lessons, progress tracking, assessments, chat system, and more.

---

## Tables Summary

| # | Table | Purpose | Records Link To |
|---|-------|---------|----------------|
| 1 | Users | User accounts | Courses, Progress, Clients, Chats, User Groups, Tests |
| 2 | Clients | Client organizations | Users |
| 3 | Courses | Course catalog | Users, Lessons, Course_enrollment, Events |
| 4 | Lessons | Course content modules | Courses, Tasks |
| 5 | Task | Individual learning activities | Lessons, Progress, Questions |
| 6 | Task Progress | User task completion | Users, Tasks |
| 7 | Questions | Quiz questions | Tasks |
| 8 | Events | Scheduled sessions | Courses |
| 9 | Answers | Quiz answers | - |
| 10 | Scores | Assessment scores | - |
| 11 | MTP_TESTS | Multiple choice tests | Users |
| 12 | AUDIO_TESTS | Speaking/audio tests | Users, Chats |
| 13 | WRITING_TESTS | Writing assessments | Users, Chats |
| 14 | Chats | Communication system | Users, Messages, Tests |
| 15 | Messages | Chat messages | Chats |
| 16 | User Groups | Student groupings | Users, Activities |
| 17 | Activities | Group activities/events | User Groups |
| 18 | Content Database | Content storage | - |
| 19 | Course_enrollment | User-Course assignments | Users, Courses |

---

## Detailed Table Schemas

### 1. Users

**Table ID:** `tbl1r15vHh4nW3Xjo`

| Field | Type | Notes |
|-------|------|-------|
| Email | `singleLineText` | Primary identifier |
| Name | `singleLineText` | Display name |
| Notes | `multilineText` | - |
| Assignee | `singleCollaborator` | - |
| Status | `singleSelect` | Todo, In progress, Done |
| Courses | `multipleRecordLinks` | -> Courses |
| Progress | `multipleRecordLinks` | -> Task Progress |
| Lessen | `lookup` | From Courses |
| Questions Progress | `singleLineText` | - |
| Clients | `multipleRecordLinks` | -> Clients |
| Chats | `multipleRecordLinks` | -> Chats |
| User Groups | `multipleRecordLinks` | -> User Groups |
| WRITING_TESTS | `singleLineText` | Legacy |
| WRITING_TESTS 2 | `multipleRecordLinks` | -> WRITING_TESTS |
| AUDIO_TESTS | `multipleRecordLinks` | -> AUDIO_TESTS |
| Course_enrollment | `multipleRecordLinks` | -> Course_enrollment |
| Startdate | `lookup` | From Course_enrollment |
| Current Lesson Week | `formula` | Week calculation from start |
| Teacher | `lookup` | From Course_enrollment |
| Closedate | `lookup` | From Course_enrollment |
| Magic link | `url` | Authentication link |
| MTP_TESTS | `multipleRecordLinks` | -> MTP_TESTS |
| Aantal Writing tests | `count` | Count of writing tests |
| Aantal Audio tests | `count` | Count of audio tests |
| Certificates | `multipleAttachments` | Completion certificates |
| Teacher_ | `lookup` | - |

**Views:**
- Grid view
- All current A1 Part 1
- Current A1 part 1 Jamila
- Current A1 part 1 Anne E.

---

### 2. Courses

**Table ID:** `tblmSLMsyy2GxPVO7`

| Field | Type | Notes |
|-------|------|-------|
| Name | `singleLineText` | Course name |
| Notes | `multilineText` | - |
| Teacher | `singleCollaborator` | Assigned instructor |
| Status | `singleSelect` | Online, Offline |
| Linked Users | `multipleRecordLinks` | -> Users |
| Email (from Linked Users) | `lookup` | - |
| Lessons | `multipleRecordLinks` | -> Lessons |
| Tests | `singleLineText` | - |
| Course_enrollment | `multipleRecordLinks` | -> Course_enrollment |
| Events | `multipleRecordLinks` | -> Events |

**Views:**
- Grid view
- All Online Modules

---

### 3. Lessons

**Table ID:** `tblBH8VGXZ4wGKXpH`

| Field | Type | Notes |
|-------|------|-------|
| Name | `singleLineText` | English name |
| Naam | `singleLineText` | Dutch name |
| Notes | `multilineText` | English notes |
| Notitie | `multilineText` | Dutch notes |
| Creator | `singleCollaborator` | - |
| Status | `singleSelect` | Todo, In progress, Done |
| Course | `multipleRecordLinks` | -> Courses |
| Task | `multipleRecordLinks` | -> Task |
| Video | `multipleAttachments` | Lesson video |
| Module ID | `autoNumber` | - |
| Lesson_Id | `autoNumber` | - |
| writing_url | `url` | Writing exercise link |
| speaking_url | `url` | Speaking exercise link |
| reading_url | `url` | Reading exercise link |
| dialogue_url | `url` | Dialogue exercise link |
| Speak_Audio_url_1_GoogleDrive | `url` | Audio file 1 |
| Speak_Audio_url_2_GoogleDrive | `url` | Audio file 2 |
| Speak_Audio_url_3_GoogleDrive | `url` | Audio file 3 |
| Speak_Audio_Text_1 | `multilineText` | Transcript 1 |
| Speak_Audio_Text_2 | `multilineText` | Transcript 2 |
| Speak_Audio_Text_3 | `multilineText` | Transcript 3 |

---

### 4. Task

**Table ID:** `tblSyEAVZAYExNBSu`

| Field | Type | Notes |
|-------|------|-------|
| Name | `multilineText` | Task description |
| Lesson | `multipleRecordLinks` | -> Lessons |
| Module_Dialoog | `singleLineText` | - |
| Module_Speaking | `singleLineText` | - |
| Module_Conversation | `singleLineText` | - |
| Status | `singleSelect` | Todo, In progress, Done |
| Progress | `multipleRecordLinks` | -> Task Progress |
| Teacher Check | `checkbox` | Reviewed by teacher |
| Notes | `multilineText` | - |
| Questions | `multipleRecordLinks` | -> Questions |
| Module_icon | `multipleAttachments` | Visual icon |
| Introduction | `multilineText` | - |
| ID | `autoNumber` | - |
| Module ID -> Lesson | `lookup` | - |
| Course (from Lesson) | `lookup` | - |
| Video | `multipleAttachments` | - |
| Bijlage | `multipleAttachments` | Attachments |
| Test Url | `url` | - |
| Flashcard url | `url` | - |

---

### 5. Task Progress

**Table ID:** `tblfGcMDhdUQux6KH`

| Field | Type | Notes |
|-------|------|-------|
| Notes | `multilineText` | - |
| Finished | `checkbox` | Completion flag |
| Finished time | `lastModifiedTime` | When finished was toggled |
| Users | `multipleRecordLinks` | -> Users |
| Task | `multipleRecordLinks` | -> Task |
| Name (from Lessons) | `lookup` | - |
| Les notitie | `lookup` | Lesson notes |
| Clients (from Users) | `lookup` | - |

---

### 6. Questions

**Table ID:** `tblwPF7NZ0y6Tjb9U`

| Field | Type | Notes |
|-------|------|-------|
| Number | `formula` | Task + Question combined |
| Task | `multipleRecordLinks` | -> Task |
| Question | `singleLineText` | Question text |
| Extra information | `multilineText` | Hints/context |
| Correct Answer | `singleLineText` | - |

---

### 7. WRITING_TESTS

**Table ID:** `tblyBQSYVCDJTb6Ij`

| Field | Type | Notes |
|-------|------|-------|
| Input | `multilineText` | Student's written response |
| Exercise | `singleLineText` | Exercise identifier |
| lesson_Id | `singleLineText` | - |
| Created By | `createdBy` | - |
| User | `singleLineText` | Legacy field |
| User_ | `multipleRecordLinks` | -> Users |
| Chats | `multipleRecordLinks` | -> Chats |
| AI assist | `aiText` | **AI-powered correction and feedback** |
| Course_enrollment | `lookup` | From User_ |

**AI Assist Prompt:**
> Provides Dutch spelling/writing correction, old vs corrected version, positive feedback, error overview. Considers student level from course name. Replies in English except Dutch texts.

---

### 8. AUDIO_TESTS

**Table ID:** `tblx0byituDy8t15y`

| Field | Type | Notes |
|-------|------|-------|
| Name | `singleLineText` | - |
| Status | `singleSelect` | Todo, In progress, Done |
| T1 | `multipleAttachments` | Teacher audio piece 1 |
| S1 | `multipleAttachments` | Student audio piece 1 |
| A1 | `url` | Audio URL |
| Lesson | `singleLineText` | - |
| lesson_Id | `singleLineText` | - |
| User_ | `singleLineText` | Legacy |
| User | `multipleRecordLinks` | -> Users |
| Chats | `multipleRecordLinks` | -> Chats |

---

### 9. MTP_TESTS

**Table ID:** `tbls2Ha3PO9QFoukW`

| Field | Type | Notes |
|-------|------|-------|
| Name of quiz | `singleLineText` | Quiz identifier |
| User | `singleLineText` | Legacy |
| User_ | `multipleRecordLinks` | -> Users |
| Overall_Score | `number` | Numeric score |
| Analysis | `multilineText` | Performance analysis |
| Created | `createdTime` | - |

---

### 10. Chats

**Table ID:** `tblBfmTN20XWC4sU3`

| Field | Type | Notes |
|-------|------|-------|
| Subject | `singleLineText` | Chat topic |
| Users | `multipleRecordLinks` | -> Users |
| Created Time | `createdTime` | - |
| Attachments | `multipleAttachments` | - |
| Status | `singleSelect` | Submitted, Processing Internally, Responded, Archived |
| Score | `rating` | 1-10 stars |
| Personal Advise | `singleLineText` | - |
| Messages | `multipleRecordLinks` | -> Messages |
| WRITING_TESTS | `multipleRecordLinks` | -> WRITING_TESTS |
| AUDIO_TESTS | `multipleRecordLinks` | -> AUDIO_TESTS |
| Teacher | `lookup` | From Users |

---

### 11. Messages

**Table ID:** `tblzuVXq93AxyJvne`

| Field | Type | Notes |
|-------|------|-------|
| Message | `singleLineText` | Message content |
| Chats | `multipleRecordLinks` | -> Chats |
| Direction | `singleSelect` | Outbound, Inbound |
| Attachment | `multipleAttachments` | - |
| Timestamp | `createdTime` | - |

---

### 12. Course_enrollment

**Table ID:** `tbl8XWGbHeT6JoVIM`

| Field | Type | Notes |
|-------|------|-------|
| Name | `formula` | User + Course combined |
| User | `multipleRecordLinks` | -> Users |
| Startdate | `date` | Enrollment start |
| Closedate | `date` | Enrollment end |
| Course | `multipleRecordLinks` | -> Courses |
| Email (from User) | `lookup` | - |
| Teacher | `singleSelect` | Jamila, Anne E, Annemijn, Anne V, Elsa, Roxane, Ella, Wesley, Catalina, Luis, Kelly |

---

### 13. Events

**Table ID:** `tblhnBw7Q8sR3RRB1`

| Field | Type | Notes |
|-------|------|-------|
| Name | `singleLineText` | Event title |
| Date | `dateTime` | Start date/time |
| Endtime | `dateTime` | End date/time |
| Location | `singleLineText` | - |
| Course | `multipleRecordLinks` | -> Courses |
| Open Lesson | `url` | - |
| Status | `singleSelect` | Online, Offline |
| Email (from Linked Users) | `lookup` | - |
| Online Meeting url | `url` | Video call link |
| Attachment | `multipleAttachments` | - |

---

### 14. User Groups

**Table ID:** `tbliF0jhuw7jXkOi6`

| Field | Type | Notes |
|-------|------|-------|
| Name | `singleLineText` | Group name |
| Teacher | `singleSelect` | Jamila |
| Users | `multipleRecordLinks` | -> Users |
| Activities | `multipleRecordLinks` | -> Activities |

---

### 15. Activities

**Table ID:** `tblBBkQKTtgV7zX8q`

| Field | Type | Notes |
|-------|------|-------|
| Name | `singleLineText` | Activity title |
| Datum en tijd | `dateTime` | Date and time |
| Notes | `multilineText` | - |
| Attachments | `multipleAttachments` | - |
| Location | `singleLineText` | - |
| Group Specific Activity | `multipleRecordLinks` | -> User Groups |
| Users (from Group...) | `lookup` | - |
| More info link | `url` | - |

---

## Entity Relationship Diagram

```
                    +-------------+
                    |   Clients   |
                    +------+------+
                           |
                           v
+--------------+    +-------------+    +------------------+
| User Groups  |<-->|    Users    |<-->| Course_enrollment|
+------+-------+    +------+------+    +--------+---------+
       |                   |                    |
       v                   |                    v
+-------------+            |             +-------------+
| Activities  |            |             |   Courses   |
+-------------+            |             +------+------+
                          |                    |
           +--------------+-------------+     |
           v              v              v     v
    +-----------+  +-----------+  +-----------+
    |   Chats   |  |MTP_TESTS  |  |  Lessons  |
    +-----+-----+  +-----------+  +-----+-----+
          |                             |
    +-----+-----+                      v
    v           v               +-----------+
+--------+ +----------+         |   Tasks   |
|Messages| |AUDIO/    |         +-----+-----+
+--------+ |WRITING   |               |
           |TESTS     |         +-----+-----+
           +----------+         v           v
                         +----------+ +-----------+
                         |Task      | | Questions |
                         |Progress  | +-----------+
                         +----------+
```

---

## Key Features

1. **AI-Powered Writing Feedback:** WRITING_TESTS table has AI assist for automatic Dutch language correction
2. **Multi-modal Assessments:** Separate tables for writing, audio, and multiple choice tests
3. **Progress Tracking:** Granular task-level progress with timestamps
4. **Chat System:** Full messaging system with status workflow
5. **Group Management:** User groups with dedicated activities
6. **Certificate Generation:** Attachments field for completion certificates