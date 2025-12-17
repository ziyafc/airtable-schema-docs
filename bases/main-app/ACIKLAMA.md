# Ana Uygulama - Detaylı Açıklama

> Hollandaca öğrenme platformunun ana veritabanı.

## 🎯 Bu Veritabanı Ne Yapıyor?

Bu, **Hollandaca dil kursu** yönetim sistemi. İçinde:

- 👥 **Öğrenciler** - Kim katılıyor?
- 📖 **Kurslar** - Hangi seviyeler var? (A1, A2, B1...)
- 📚 **Dersler** - Her kursta neler öğretiliyor?
- ✅ **Ödevler** - Öğrenciler ne yapmalı?
- 📝 **Testler** - Yazma, konuşma, çoktan seçmeli
- 💬 **Sohbetler** - Öğretmen-öğrenci iletişimi

---

## 🗺️ Genel Yapı

Sistemi bir **ağaç** gibi düşün:

```
🏢 MÜŞTERİLER (Kurumlar)
    │
    └── 👥 ÖĞRENCİLER
            │
            ├── 📖 KURSLAR (A1, A2, B1...)
            │       │
            │       └── 📚 DERSLER (Hafta 1, Hafta 2...)
            │               │
            │               └── ✅ ÖDEVLER (Görevler)
            │                       │
            │                       └── ❓ SORULAR
            │
            ├── 📊 İLERLEME (Hangi ödevleri yaptı?)
            │
            ├── 📝 TESTLER (Yazma, Ses, Çoktan Seçmeli)
            │
            └── 💬 SOHBETLER (Öğretmenle iletişim)
```

---

## 📊 Tüm Tablolar

Her tablonun detaylı açıklaması için tıkla:

### 👥 İnsan Tabloları

| Tablo | Ne Tutuyor? | Detay |
|-------|-------------|-------|
| Öğrenciler | Tüm öğrenci bilgileri | [[bases/main-app/tablolar/ogrenciler|→ Detay]] |
| Müşteriler | Kurumsal müşteriler (şirketler) | [[bases/main-app/tablolar/musteriler|→ Detay]] |
| Gruplar | Öğrenci grupları | [[bases/main-app/tablolar/gruplar|→ Detay]] |

---

### 📚 İçerik Tabloları

| Tablo | Ne Tutuyor? | Detay |
|-------|-------------|-------|
| Kurslar | A1, A2, B1 seviyeleri | [[bases/main-app/tablolar/kurslar|→ Detay]] |
| Dersler | Her kurstaki haftalık dersler | [[bases/main-app/tablolar/dersler|→ Detay]] |
| Ödevler | Her dersteki görevler | [[bases/main-app/tablolar/odevler|→ Detay]] |
| Sorular | Quiz soruları | [[bases/main-app/tablolar/sorular|→ Detay]] |

---

### 📝 Test Tabloları

| Tablo | Test Türü | Detay |
|-------|----------|-------|
| Yazı Testleri | ✉️ Yazma + **AI düzeltme** | [[bases/main-app/tablolar/yazi-testleri|→ Detay]] |
| Ses Testleri | 🎙️ Konuşma kaydı | [[bases/main-app/tablolar/ses-testleri|→ Detay]] |
| Çoktan Seçmeli | ✅ Quiz | [[bases/main-app/tablolar/coktan-secmeli|→ Detay]] |

---

### 💬 İletişim Tabloları

| Tablo | Ne Tutuyor? | Detay |
|-------|-------------|-------|
| Sohbetler | Öğretmen-öğrenci konuşmaları | [[bases/main-app/tablolar/sohbetler|→ Detay]] |
| Mesajlar | Sohbet içindeki mesajlar | [[bases/main-app/tablolar/mesajlar|→ Detay]] |

---

### 📊 Takip Tabloları

| Tablo | Ne Tutuyor? | Detay |
|-------|-------------|-------|
| İlerleme | Kim hangi ödevi yaptı? | [[bases/main-app/tablolar/ilerleme|→ Detay]] |
| Kayıtlar | Kim hangi kursa kayıtlı? | [[bases/main-app/tablolar/kayitlar|→ Detay]] |
| Etkinlikler | Canlı dersler ne zaman? | [[bases/main-app/tablolar/etkinlikler|→ Detay]] |
| Aktiviteler | Grup aktiviteleri | [[bases/main-app/tablolar/aktiviteler|→ Detay]] |

---

## 🤖 AI Özelliği

Bu sistemin en güçlü özelliği **Yazı Testleri**'ndeki yapay zeka:

1. Öğrenci Hollandaca bir şey yazıyor
2. AI otomatik analiz ediyor
3. Hataları buluyor
4. Doğru versiyonunu gösteriyor
5. Açıklama yapıyor

**[[bases/main-app/tablolar/yazi-testleri|→ Detaylı açıklama]]**

---

## 🔄 Tipik Bir Akış

Bir öğrencinin sistemi nasıl kullandığını görelim:

```
1️⃣ Ahmet sisteme kayıt oluyor
   → Öğrenciler tablosuna ekleniyor
   → Kayıtlar ile A1 kursuna bağlanıyor

2️⃣ Ahmet derslerini görüyor
   → Kursu üzerinden Derslere erişiyor
   → Her dersin Ödevlerini görüyor

3️⃣ Ahmet bir yazı ödevi yapıyor
   → Yazı Testlerine kaydediliyor
   → AI otomatik geri bildirim veriyor
   → Öğretmen kontrol edip puan veriyor

4️⃣ Ahmet'in sorusu var
   → Sohbetlerde yeni sohbet açıyor
   → Mesajlara mesajı yazıyor
   → Öğretmen yanıtlıyor

5️⃣ Öğretmen ilerlemeyi takip ediyor
   → İlerleme tablosundan kimin ne yaptığını görüyor
```

---

## 👩‍🏫 Öğretmenler

Sistemde 11 öğretmen tanımlı:
- Jamila, Anne E, Annemijn, Anne V, Elsa
- Roxane, Ella, Wesley, Catalina, Luis, Kelly

Her öğrenci bir öğretmene atanabiliyor.

---

## 📌 İlgili Sayfalar

- [[GIRIS|← Giriş sayfasına dön]]
- [[bases/main-app/index|Teknik detaylar (geliştiriciler için)]]