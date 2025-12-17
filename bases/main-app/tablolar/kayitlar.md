# 📝 Kayıtlar Tablosu (Course_enrollment)

## Bu Tablo Ne İçin?

Bu tabloda **hangi öğrencinin hangi kursa ne zaman kayıt olduğu** tutuluyor.

---

## 🤔 Neden Ayrı Bir Tablo?

Bir öğrenci birden fazla kursa kayıt olabilir:
- Ahmet → A1 Part 1 (15 Ocak)
- Ahmet → A1 Part 2 (15 Nisan)

Bu yüzden ayrı bir tablo:
```
Öğrenci + Kurs = Kayıt
```

---

## 📝 Bu Tabloda Neler Var?

| Alan | Açıklama | Örnek |
|------|---------|-------|
| **Startdate** | Başlangıç tarihi | 15 Ocak 2025 |
| **Closedate** | Bitiş tarihi | 15 Nisan 2025 |
| **Teacher** | Atanan öğretmen | Jamila |

### Bağlantılar

| Alan | Ne Gösterir? |
|------|-------------|
| **User** | Hangi öğrenci? |
| **Course** | Hangi kurs? |

---

## 👩‍🏫 Öğretmenler (11 Kişi)

1. Jamila
2. Anne E
3. Annemijn
4. Anne V
5. Elsa
6. Roxane
7. Ella
8. Wesley
9. Catalina
10. Luis
11. Kelly

---

## 📌 İlgili Sayfalar

- [[bases/main-app/ACIKLAMA|← Ana Sistem'e dön]]
- [[bases/main-app/tablolar/ogrenciler|Öğrenciler]]
- [[bases/main-app/tablolar/kurslar|Kurslar]]