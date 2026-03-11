# Oto Yılan Oyunu

Sayfa açılır açılmaz kendi kendine oynayan, HTML/CSS/JavaScript ile geliştirilmiş otomatik bir yılan oyunu.

## Proje Hakkında

Bu proje, klasik Snake oyununun tamamen otomatik oynayan bir versiyonudur. Oyuncu girişine ihtiyaç duymaz. Oyun açıldığı anda yapay zekâ mantığı devreye girer, yemi toplamak için güvenli yolu hesaplar ve yılan ölürse yeni turu otomatik olarak başlatır.

Demo: https://metinciris.github.io/oto-yilan/

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

## Oyun Mantığı

Oyundaki otomatik sistem şu yaklaşımla çalışır:

* Önce yeme ulaşmak için uygun bir yol arar.
* Bulduğu yolun güvenli olup olmadığını kontrol eder.
* Eğer doğrudan güvenli bir yol yoksa, yılanın sıkışmaması için daha geniş hareket alanı bırakan hamleyi seçer.
* Oyun bittiğinde kısa bir bekleme sonrası kendini yeniden başlatır.

## Geliştirme Fikirleri

* Farklı oyun modları eklemek
* Daha gelişmiş yapay zekâ algoritması yazmak
* Mobil uyumluluğu artırmak
* Ses efektleri ve animasyonlar eklemek
* Manuel mod ile otomatik modu birlikte sunmak
* Skor geçmişini localStorage ile saklamak

Yılan belirgin şekilde  akıllı çünkü artık sadece “yeme git” demiyor, “gidince çıkabilecek miyim?” diye de bakıyor.

## Akıllanmasını sağlayan ana şeyler bunlar:

**1. En kısa yolu arıyor (`bfsPath`)**
Artık rastgele ya da sadece hedefe yaklaşan hamle yapmıyor. Tahtada yeme giden gerçek bir yol arıyor. Bu yüzden koridorları ve engelleri daha iyi okuyor.

**2. Kuyruğu özel ele alıyor (`buildBlockedSet`)**
Çok önemli nokta bu. Yılanın kuyruğu hareket edeceği için bazı durumlarda kuyruk karesi geçici olarak kullanılabilir kabul ediliyor.
Bu sayede “gereksiz yere kapalı sanılan” yolları da kullanabiliyor.

**3. Hamleyi simüle edip sonra karar veriyor (`simulateMove`)**
Önce hamleyi kafasında oynuyor:

* buraya gidersem gövde nasıl olacak?
* büyüyecek miyim?
* çıkış kalacak mı?

Bu, tek adımlık bakıştan daha güçlü.

**4. Güvenlik kontrolü var (`isSafeMove`)**
Asıl fark burada. Yeme giden yol bulsa bile hemen gitmiyor. Önce şunu kontrol ediyor:

* O hamleden sonra yeni kafadan kuyruğa hâlâ bir yol var mı?

Yani sistem şunu düşünüyor:
“Bu hamle kısa vadede güzel ama beni kapana sıkıştırır mı?”

Bu özellik eski sürümlerde yoksa yılan sık sık:

* yemi alıp köşeye kapanır,
* kendi etrafını sarar,
* dar alanda çıkışsız kalırdı.

**5. Yol güvenli değilse alternatif stratejiye geçiyor (`chooseNextMove`)**
Eğer yeme güvenli yol yoksa boş boş intihar etmiyor. Bunun yerine hayatta kalma modu açılıyor.

Bu modda her aday hamle için şunlara bakıyor:

* ne kadar geniş alan bırakıyor (`reachableArea`)
* yeme uzaklık
* duvara fazla yapışıyor mu (`wallPenalty`)

Yani artık sadece “hedef” değil, “manevra alanı” da önemli.

**6. Erişilebilir alan hesabı var (`reachableArea`)**
Bu da çok etkili. Hamleden sonra yılanın başı ne kadar büyük bir açık bölgede kalıyor, onu ölçüyor.
Böylece dar koridordan ziyade geniş ve güvenli bölgelere yöneliyor.

**7. Büyüme durumu hesaba katılıyor (`willGrow`)**
Yemi yiyecekse kuyruk o tur hareket etmeyecek. Kod bunu biliyor.
Bu çok kritik, çünkü büyüme anında güvenli sandığın bir hamle aslında tehlikeli olabilir.

**8. “Yol yoksa en az kötü hamle” mantığı var**
Eskiden sistemler genelde:

* ya direkt yeme gider,
* ya da yol yoksa saçmalar.

Bu sürüm ise yol yoksa bile puanlama yapıp en mantıklı güvenli hamleyi seçiyor. Bu yüzden daha “insansı” görünüyor.

Akıllı görünmesine en çok katkı veren 3 parça bence şunlar:

* `bfsPath`
* `isSafeMove`
* `reachableArea`

Özellikle `isSafeMove` en kritik yükseltme. Çünkü oyunu “hedefe koşan bot”tan çıkarıp “önce hayatta kalmayı bilen bot” yapıyor.

## İlerde daha da akıllandıracak 5 yükseltme de çıkabilir:
Hamiltonian cycle, daha derin simülasyon, trap detection ve lookahead sistemi

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
