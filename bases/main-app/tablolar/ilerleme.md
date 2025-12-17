# 📊 İlerleme Tablosu (Task Progress)

## Bu Tablo Ne İçin?

Bu tabloda **hangi öğrencinin hangi ödevi yaptığı** tutuluyor. Yani öğrenci takibi.

---

## 📝 Bu Tabloda Neler Var?

| Alan | Açıklama | Örnek |
|------|---------|-------|
| **Notes** | Ekstra notlar | "Öğretmen kontrolü bekleniyor" |
| **Finished** | Tamamlandı mı? | ✅ Evet / ❌ Hayır |
| **Finished time** | Ne zaman tamamlandı? | 16 Ocak 2025, 10:30 |

### Bağlantılar

| Alan | Ne Gösterir? |
|------|-------------|
| **Users** | Hangi öğrenci? |
| **Task** | Hangi ödev? |

---

## 🔄 Nasıl Çalışıyor?

```
Öğrenci + Ödev = İlerleme Kaydı
```

Örnek:
- Ahmet + "Ödev 1" = 1 satır
- Ahmet + "Ödev 2" = 1 satır
- Ayşe + "Ödev 1" = 1 satır

---

## 💡 Örnek Tablo

| Öğrenci | Ödev | Tamamlandı? | Zaman |
|---------|------|------------|-------|
| Ahmet | Kendinizi tanıtın | ✅ | 15 Ocak, 10:00 |
| Ahmet | Sayılar quiz'i | ✅ | 15 Ocak, 11:30 |
| Ahmet | Diyalog | ❌ | - |
| Ayşe | Kendinizi tanıtın | ✅ | 14 Ocak, 09:00 |

Bu tablodan:
- Ahmet 3 ödevden 2'sini yaptı
- Ayşe 2 ödevden 1'ini yaptı

---

## 📌 İlgili Sayfalar

- [[bases/main-app/ACIKLAMA|← Ana Sistem'e dön]]
- [[bases/main-app/tablolar/ogrenciler|Öğrenciler]]
- [[bases/main-app/tablolar/odevler|Ödevler]]