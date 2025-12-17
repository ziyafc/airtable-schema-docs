# Airtable Schema Documentation

Bu vault, Airtable workspace'inin tam dokümantasyonunu içerir.

## 🗺️ Navigation

### Bases
- [[bases/amstel-dutch/index|Amstel Dutch]] - Product launch tracking
- [[bases/expat-student/index|Expat Student Course Management]] - Öğrenci ve kurs yönetimi
- [[bases/main-app/index|Main App (!!Base for App!!)]] - Ana uygulama veritabanı
- [[bases/dev-staging/index|Dev/Staging (Untitled Base)]] - Geliştirme ortamı

### Quick Reference
- [[reference/field-types|Field Types]] - Airtable field type'ları
- [[reference/status-workflows|Status Workflows]] - Durum akışları
- [[reference/api-ids|API IDs]] - Tüm Base ve Table ID'leri
- [[reference/patterns|Common Patterns]] - Tekrar eden yapılar

### Diagrams
- [[diagrams/overview|Architecture Overview]] - Genel mimari
- [[diagrams/relationships|Cross-Base Relationships]] - Base'ler arası ilişkiler

---

## 📊 Base Summary

| Base | Tables | AI Fields | Chat | Tests |
|------|--------|-----------|------|-------|
| [[bases/amstel-dutch/index\|Amstel Dutch]] | 1 | ❌ | ❌ | ❌ |
| [[bases/expat-student/index\|Expat Student]] | 6 | ✅ | ❌ | ✅ |
| [[bases/main-app/index\|Main App]] | 20 | ✅ | ✅ | ✅ |
| [[bases/dev-staging/index\|Dev/Staging]] | 5 | ❌ | ❌ | ❌ |

---

## 🏷️ Tags

- `#base` - Base dökümanları
- `#table` - Tablo dökümanları  
- `#field-type/*` - Field type'lara göre
- `#has-ai` - AI field içeren tablolar
- `#has-formula` - Formula içeren tablolar
- `#junction-table` - Many-to-many ilişki tabloları

---

*Son güncelleme: 2025-12-17*