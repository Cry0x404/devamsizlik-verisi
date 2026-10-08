# Devamsızlık verisi

Uygulama `devamsizlik.json` dosyasını açılışta ve yeniden öne geldiğinde okur. Dosyayı düzenlemek için GitHub'da dosyaya girin, kalem düğmesine basın ve değişikliği **Commit changes** ile kaydedin. Uygulamayı yeniden açın veya devamsızlık sayfasında **Yenile** düğmesine basın.

## Kayıt ekleme veya değiştirme

Her tarih yalnızca bir kez bulunmalıdır. Tarih biçimi `YYYY-AA-GG` şeklindedir. `gun` alanı tam gün için `1`, yarım gün için `0.5` olmalıdır.

```json
{ "tarih": "2026-10-09", "tur": "ozursuz", "gun": 0.5 }
```

`tur` seçenekleri:

| Değer | Uygulamadaki görünüm | Toplam |
| --- | --- | --- |
| `ozursuz` | Tam Gün / Yarım Gün | Özürsüz |
| `ozurlu` | Özürlü / Özürlü · Yarım Gün | Özürlü |
| `izinli` | İzinli / İzinli · Yarım Gün | Özürlü |
| `raporlu` | Raporlu / Raporlu · Yarım Gün | Özürlü |

Kaydı silerseniz liste ve takvimdeki mavi daire de kaldırılır. Toplamlar kayıtlardan hesaplanır. Takvimdeki günler elle seçilemez.

## Önceki toplamın korunması

Başlangıçtaki ekranda özürlü toplamı 4 gün, görünen özürlü kayıtlar ise 2 gündür. `listede_olmayan_ozurlu_gun: 2` bu eski farkı korur. Bu alan takvimde herhangi bir gün işaretlemez. Tüm günleri tek tek yazdığınızda alanı `0` yapın. Uygulama özürlü toplamını bu alan + özürlü kayıtların gün miktarı olarak hesaplar. Özürsüz toplamı yalnızca kayıtlardan hesaplanır.

Başlangıç dosyasında 8 Ekim kaydı bulunmaz. Kimlik, öğrenci adı, fotoğraf veya giriş bilgisi bu depoya yüklenmez.

## Hatalar

İnternet yokken uygulama eski veriyi göstermez; toplamlar, kayıtlar ve mavi daireler temizlenir. Dosya hatalıysa veya indirilemiyorsa veri gösterilmez ve açıklayıcı hata çıkar. JSON'da yorum satırı, son elemandan sonra virgül, geçersiz tarih veya yinelenen tarih kullanmayın. Boş kayıt listesi geçerlidir.
