# Ürün Link Finder 🔍

Beko, Beko Anabayisi ve Akakce sitelerinde ürün linklerini bulmak için otomatik bir araç.

## Özellikler

✅ Excel dosyasından ürün kodı ve adı okur  
✅ Üç siteyi otomatik olarak tarar  
✅ Bulunamayan ürünler için "Bulunamadı" yazısı ekler  
✅ Sonuçları Excel dosyasına kaydeder  

## Siteler

- 🔗 https://www.beko.com.tr
- 🔗 https://www.bekoanabayisi.com
- 🔗 https://www.akakce.com

## Kurulum

### 1. Python 3.7+ Gerekli

### 2. Gerekli Kütüphaneleri Yükleyin

```bash
pip install -r requirements.txt
```

### 3. Chrome Tarayıcısı (Opsiyonel)

Eğer Selenium kullanacaksanız Chrome'un kurulu olması gerekir.

## Kullanım

### Adım 1: Excel Dosyası Hazırlayın

`input.xlsx` dosyasını aşağıdaki formatta hazırlayın:

| A (Ürün Kodu) | B (Ürün Adı) |
|---|---|
| 7672110277 | Ankastre Bulaşık Makinesi |
| 1234567890 | Çamaşır Makinesi |

### Adım 2: Programı Çalıştırın

```bash
python urun_finder.py
```

### Adım 3: Sonuçları Kontrol Edin

`output.xlsx` dosyasında sonuçlar olacaktır:

| A | B | C (Beko Link) | D (Beko Anabayisi Link) | E (Akakce Link) |
|---|---|---|---|---|
| 7672110277 | Ankastre Bulaşık Makinesi | https://... | Bulunamadı | https://... |

## Örnek Output

```
🔍 Ürün Arama Başladı...

İşleniyor: Kod=7672110277, Adı=Ankastre Bulaşık Makinesi
  Beko: https://www.beko.com.tr/tezgah-alti-bulasik-makinesi/bbc-160-g-ankastre-bulasik-makineleri
  Beko Anabayisi: https://www.bekoanabayisi.com/urun/...
  Akakce: Bulunamadı

✅ Sonuçlar kaydedildi: output.xlsx
✅ İşlem Tamamlandı!
```

## Önemli Notlar

⚠️ **Rate Limiting**: Program siteler arasında 1 saniye bekleme ekler. Bu limiti arttırabilirsiniz.  
⚠️ **Ürün Bulunamama**: Ürün sitenin yapısına bağlı olarak bulunamayabilir.  
⚠️ **Web Scraping**: Lütfen sitelerin Terms of Service'ini kontrol edin.  

## Sorun Giderme

### "input.xlsx Bulunamadı"
```
input.xlsx dosyasını proje klasörüne koyun.
```

### "Modül Bulunamadı" Hatası
```bash
pip install -r requirements.txt
```

### Ürünler Bulunamıyor

1. Ürün kodunu ve adını kontrol edin
2. Sitelerin yapısı değişmiş olabilir (kodu güncellenebilir)
3. Siteler rate limit uyguluyor olabilir

## Geliştirme

Siteler yapılarını değiştirirlerse, `find_in_*` fonksiyonlarındaki HTML selector'ları güncellemeniz gerekir.

## Lisans

MIT License

## İletişim

Sorular için GitHub Issues açın.
