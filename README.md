# TR
# Öğrenci Otomasyonu
localStorage tabanlı, tarayıcıda çalışan sade bir öğrenci yönetim uygulaması. Öğrenci ekleme, silme, güncelleme ve ada göre arama işlemlerini destekler; sayfa yenilendiğinde veriler kaybolmaz.

## Canlı Önizleme

[Projenin deploy edildikten sonra önizlemesi.](https://dursunkokturk.github.io/JavaScript-Project-Student-Automation/)


## Özellikler

- Öğrenci Listeleme — 20 başlangıç öğrencisi localStorage'a yazılır ve kart formatında listelenir
- Öğrenci Ekleme — prompt() ile ad, soyad, yaş, cinsiyet ve fotoğraf URL alınarak listeye eklenir
- Öğrenci Silme — Onay kutusuyla birlikte seçilen öğrenciyi listeden ve localStorage'dan kaldırır
- Öğrenci Güncelleme — Seçilen öğrencinin tüm bilgilerini prompt() üzerinden günceller
- Ada Göre Arama — Form gönderimi ile büyük/küçük harf duyarsız, anlık filtreleme yapar
- Sıfırlama — Arama kutusunu temizler ve tam listeyi yeniden gösterir
- localStorage Kalıcılığı — Sayfa yenilendiğinde veriler korunur; ilk açılışta başlangıç verisi otomatik yazılır
- Duyarlı Kart Tasarımı — Mobilsde tek sütun, tablette iki sütun, masaüstünde üç sütun


## Duyarlı Düzenler

| Ekran    | Genişlik         | Düzen                                       |
| -------- |------------------| --------------------------------------------|
| Mobil    | 375px Varsayılan | Tek sütun kart listesi, dikey buton grubu   |
| Tablet   | > 767px          | İki sütunlu kart ızgarası                   |
| Masaüstü | > 1024px         | Üç sütunlu kart ızgarası, yatay buton grubu |


## Teknolojiler
 

| Teknoloji  | Açıklama                                        |
| ---------- |-------------------------------------------------|
| HTML5      | Semantik sayfa yapısı                           |
| CSS3       | Flexbox, @media sorguları, kart tasarımı        |
| JavaScript | DOM manipülasyonu, localStorage, dizi işlemleri |


### Proje Yapısı
student-automation/ <br>
├── index.html <br>
└── assets/ <br>
    ├── css/ <br>
    │   └── style.css <br>
    └── js/ <br>
        └── students.js <br>

### Uygulama Akışı
Sayfa Açılır <br>
    │ <br>
    ▼ <br>
localStorage'da veri var mı? <br>
    │ <br>
    ├── Hayır → initialStudents yazılır <br>
    │ <br>
    └── Evet  → localStorage'dan okunur <br>
                       │ <br>
                       ▼ <br>
                 studentsList() çağrılır → Kartlar DOM'a basılır <br>

## Kurulum
Proje herhangi bir bağımlılık gerektirmez. Klonladıktan sonra doğrudan tarayıcıda açabilirsiniz.
bash# Repoyu klonlayın
git clone https://github.com/kullanici-adi/student-automation.git

### Proje klasörüne girin
cd student-automation

### index.html dosyasını tarayıcıda açın
open index.html

#### Not: students.js dosyası defer ile yüklenir; bu nedenle script, HTML tamamen parse edildikten sonra çalışır.


## Tasarım Detayları

- Renk Paleti:

  - rgb(52, 73, 94) — Koyu mavi-gri (buton arka planı)
  - #FF0000 — Kırmızı (silme butonu)
  - lightblue — Açık mavi (düzenleme butonu)


- Font: system-ui, Arial, Helvetica (sistem fontu)
- Kart Efekti: hover durumunda translateY(-5px) ile yukarı kalkma animasyonu
