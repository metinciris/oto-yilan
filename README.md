# Oto Yılan Oyunu

Sayfa açılır açılmaz kendi kendine oynayan, HTML/CSS/JavaScript ile geliştirilmiş otomatik bir yılan oyunu.

## Proje Hakkında

Bu proje, klasik Snake oyununun tamamen otomatik oynayan bir versiyonudur. Oyuncu girişine ihtiyaç duymaz. Oyun açıldığı anda yapay zekâ mantığı devreye girer, yemi toplamak için güvenli yolu hesaplar ve yılan ölürse yeni turu otomatik olarak başlatır.

## Öne Çıkan Özellikler

* Tam otomatik oynanış
* Sayfa açılır açılmaz oyunun başlaması
* Güvenli yol bulmaya çalışan basit oyun zekâsı
* Ölüm sonrası otomatik yeniden başlatma
* Skor, en iyi skor, tur ve hız göstergeleri
* Modern ve şık tek sayfa arayüz
* Sadece tek bir HTML dosyası ile çalışır

## Kullanılan Teknolojiler

* HTML5
* CSS3
* Vanilla JavaScript
* Canvas API

## Nasıl Çalıştırılır

1. Projeyi indir veya klonla.
2. HTML dosyasını tarayıcıda aç.
3. Oyun otomatik olarak çalışmaya başlar.

## Önerilen Proje Yapısı

```text
oto-yilan-oyunu/
├── index.html
└── README.md
```

> Mevcut oyun dosyanı `index.html` olarak adlandırırsan GitHub Pages üzerinde yayınlamak daha kolay olur.

## Oyun Mantığı

Oyundaki otomatik sistem şu yaklaşımla çalışır:

* Önce yeme ulaşmak için uygun bir yol arar.
* Bulduğu yolun güvenli olup olmadığını kontrol eder.
* Eğer doğrudan güvenli bir yol yoksa, yılanın sıkışmaması için daha geniş hareket alanı bırakan hamleyi seçer.
* Oyun bittiğinde kısa bir bekleme sonrası kendini yeniden başlatır.

## GitHub Pages ile Yayınlama

Bu proje statik olduğu için GitHub Pages ile kolayca yayınlanabilir.

### Adımlar

1. GitHub’da yeni bir repo oluştur.
2. `index.html` ve `README.md` dosyalarını yükle.
3. Repo ayarlarından **Pages** bölümünü aç.
4. Branch olarak `main` ve klasör olarak `/root` seç.
5. Kaydet ve birkaç saniye sonra oluşan linkten projeyi aç.

## Geliştirme Fikirleri

* Farklı oyun modları eklemek
* Daha gelişmiş yapay zekâ algoritması yazmak
* Mobil uyumluluğu artırmak
* Ses efektleri ve animasyonlar eklemek
* Manuel mod ile otomatik modu birlikte sunmak
* Skor geçmişini localStorage ile saklamak

## Ekran Görünümü

Bu proje modern kart yapısına sahip bir arayüz içerir:

* Sol bölümde oyun alanı
* Sağ bölümde skor ve durum paneli
* Otomatik oynanışı açıklayan bilgi kartları

## Katkı

Katkı sunmak istersen fork alabilir, geliştirme yapabilir ve pull request gönderebilirsin.

## Lisans

Bu proje kişisel ve eğitim amaçlı kullanım için uygundur.

---

## Kısa Tanıtım Metni

**Oto Yılan Oyunu**, tarayıcıda çalışan ve hiçbir kullanıcı girdisi olmadan kendi kendine oynayan modern bir Snake oyunudur. Basit ama etkili bir yol bulma mantığı kullanır ve saf HTML, CSS ve JavaScript ile geliştirilmiştir.
