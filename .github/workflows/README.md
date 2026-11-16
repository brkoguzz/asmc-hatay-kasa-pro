# Anatolian Soldiers MC – Hatay Charter Kasası

Aidat, ödeme, dekont ve kulüp kasası takibi için Android uygulaması (Kotlin + Jetpack Compose, Türkçe, koyu tema).

## APK nasıl alınır

### Yol 1 – GitHub ile (bilgisayara bir şey kurmadan)
1. github.com'da ücretsiz hesap açın, **New repository** ile **Private** bir depo oluşturun.
2. Bu klasörün içindekileri (`.github` klasörü dahil) depoya yükleyin (web arayüzünde *Add file → Upload files*; gizli `.github` klasörünün de yüklendiğinden emin olun).
3. Depoda **Actions** sekmesine girin → **APK derle** → derleme yeşil olunca (5-10 dk) en alttaki **Artifacts** bölümünden `anatolian-kasa-apk` dosyasını indirin.
4. İçinden çıkan `app-debug.apk` dosyasını telefona gönderip açın. İstenirse "bilinmeyen kaynaklardan yüklemeye izin ver"i açın.

### Yol 2 – Android Studio ile
1. Android Studio'yu kurun, **File → Open** ile bu klasörü açın, Gradle senkronizasyonunu bekleyin.
2. **Build → Build Bundle(s) / APK(s) → Build APK(s)**. APK `app/build/outputs/apk/debug/` altında oluşur.

## Önemli: veriler nerede tutulur
Uygulama internet/sunucu kullanmaz; tüm kayıtlar **o telefonda** saklanır. Her telefonun verisi ayrıdır.
- Kasa kaydını tutan Treasurer'ın telefonu "ana" kayıttır.
- Diğer üyelerin kendi telefonlarında aynı verileri görmesi için Ayarlar → **Yedek al** ile dosya paylaşılıp, onların telefonunda **Yedekten geri yükle** yapılır (her yedekte yeni durum gönderilir).
- Üyelerin telefonlarından yaptığı ödeme bildirimleri Treasurer'a otomatik ulaşmaz; canlı çok kullanıcılı senkron için bir sunucu (ör. Firebase) eklenmesi gerekir.
- Bildirimler telefonun kendi içinde, günde bir kez (10:00 civarı) kontrol edilerek gösterilir.

## İlk kullanım
Açılışta kulüp/şube bilgisi ve ilk yönetici (Treasurer) PIN'iyle kurulum yapılır. Sonra Üyeler → **Üye ekle** ile herkes eklenir ve her üyeye bir giriş PIN'i verilir.
