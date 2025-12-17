---
tags:
  - table
  - field-type/singleSelect
  - field-type/date
  - field-type/richText
base: "[[bases/amstel-dutch/index|Amstel Dutch]]"
table_id: tblnUG1lqNMIlLzdJ
---

# Product Launches

> Product launch tracking with status workflow.

## 📋 Table Info

| Property | Value |
|----------|-------|
| Table ID | `tblnUG1lqNMIlLzdJ` |
| Base | [[bases/amstel-dutch/index|Amstel Dutch]] |
| Views | 1 |

## 📊 Fields

| Field | Type | Description |
|-------|------|-------------|
| Product Name | [[reference/field-types#singleLineText\|singleLineText]] | Ürün adı |
| Status | [[reference/field-types#singleSelect\|singleSelect]] | [[#Status Options\|Durum seçenekleri]] |
| Launch date | [[reference/field-types#date\|date]] | Lansman tarihi |
| Owner | [[reference/field-types#singleCollaborator\|singleCollaborator]] | Sorumlu kişi |
| Description | [[reference/field-types#richText\|richText]] | Açıklama |

### Status Options

| Option | Color | Meaning |
|--------|-------|--------|
| Not started | 🔴 Red | Başlanmadı |
| At risk | 🟡 Yellow | Risk altında |
| On track | 🟠 Orange | Yolunda |
| Completed | 🟢 Green | Tamamlandı |

## 👁️ Views

- **Grid view** (`viwfS11RBmKUYXQL3`) - Default view

## 🔗 Relationships

Bu tablo başka tablolarla bağlı değil.

## 📌 Related

- [[bases/amstel-dutch/index|← Back to Amstel Dutch]]
- [[reference/status-workflows|Status Workflows]]