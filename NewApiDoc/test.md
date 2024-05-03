# Project: Aaro Api
Aaro Yazılım web API dökümantasyonuna hoş geldiniz. API aracılığıyla Aaro Erp uç noktalarına erişim sağlayarak stok, cari veya banka gibi çeşitli kalemler için sorgularda bulunabilirsiniz.

API ile Aaro Web arayüzü ile yapılan işlemlerin büyük bir kısmını gerçekleştirebilirsiniz. Üretim modülleri henüz aktif halde değildir.

Dillere göre ayırdığımız siyah alanda kod örnekleri görebilirsiniz. Aynı bölgeden dil değişimini gerçekleştirebilirsiniz.

Talepleriniz için lütfen [Github](https://github.com/AaroYazilim) sayfamızı ziyaret edin.
# 📁 Collection: Authentication 


## End-point: Authentication
### Method: POST
>```
>{{BaseUrl}}/Token
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/x-www-form-urlencoded|


### 🔑 Authentication oauth2

|Param|value|Type|
|---|---|---|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Stok 


## End-point: Stoktaki Ürünleri Getir
Bu uç nokta ile stoklardaki ürünleri toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/Stok
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|EsnekAramaKisiti||
|SirketID|0|
|SubeID|0|
|StokID|3741|
|SablonID||
|StokMuhasebeID||
|StokVergiID||
|BayiGozuksunMu||
|Kalinlik||
|En||
|Boy||
|Agirlik||
|Yogunluk||
|Durum|true|
|OlsID||
|DgsID||
|OlsTarBas||
|OlsTarBit||
|DgsTarBas||
|DgsTarBit||



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stoktaki Ürünleri Getir Min
Bu uç nokta ile stoklardaki ürünleri toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.


### Method: GET
>```
>{{BaseUrl}}/api/Stok/GetKayit
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|EsnekAramaKisiti||
|SubeID|0|
|StokID|3741|
|SablonID||
|StokMuhasebeID||
|StokVergiID||
|BayiGozuksunMu||
|Kalinlik||
|En||
|Boy||
|Agirlik||
|Yogunluk||
|Durum|true|
|OlsID||
|DgsID||
|OlsTarBas||
|OlsTarBit||
|DgsTarBas||
|DgsTarBit||



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stok Ekle
Yeni bir stok kartı eklemek için  
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| StokID | \-1 | Eklenilen ürünün stok ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır. | Evet |
| SubeID | 1 | Stoğun bulunduğu şubenin ID'sidir. | Evet |
| SirketID | 1 | Stoğun ait olduğu şirketin ID'sidir. | Evet |
| StokKodu | "HRD.KPKL.00164" | Stoğun detaylı kodudur. | Evet |
| StokAdi | "Hırdavat Kapı Kolu Burak Oda Rozetli Saten" | Stoğun gözüken adıdır. | Evet |
| StokKisaKodu | "HRD.KPKL" | Stoğun genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa koda sahip olması önemlidir. | Evet |
| StokKisaAdi | "Hırdavat Kapı Kolu" | Stoğun genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa ada sahip olması önemlidir. | Evet |
| Durum | true | Stok kartının aktif veya pasif olduğunu belirlemektedir | Evet |
| TipID | 105001 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Gelir-gider hareketleri gibi işlemler de stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. | Evet |
| StokMuhasebeID | 201 | Stokların muhasebesebesi farklı şekilde işlenebilir. Stok muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz | Evet |
| Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Evet |
| Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel |
| Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel |
| CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel |
| CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel |
| Kalinlik | 10.0 | Stok kartının fizikel kalınlığıdır. | Opsiyonel |
| En | 10.0 | Stok kartının fizikel enidir. | Opsiyonel |
| Boy | 10.0 | Stok kartının fizikel boyudur. | Opsiyonel |
| Yoğunluk | 3.0 | Stok kartının fizikel yoğunluğudur. | Opsiyonel |
| Agirlik | 5.0 | Stok kartının fizikel ağırlığıdır. | Opsiyonel |
| Kod1ID | null | Stok kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Elektronik -> Bilgisayar -> HP | Opsiyonel |
| Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel |
| SablonID | null | Ürün ekleme şablonu varsa girilmelidir. | Opsiyonel |
| TakipYontemi | 0: Normal  <br>1: Lot  <br>2:Seri | Seri, Lot bilgilerinin girilmesi için kullanılır. |  |

> &lt;h5 &gt;Ürün oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.&lt;/h5&gt;
### Method: POST
>```
>{{BaseUrl}}/api/Stok/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "StokID": 237,
            "StokKodu": "DTSK1",
            "StokAdi": "Depo Terminal Stok 1",
            "StokKisaKodu": "DTSK1",
            "StokKisaAdi": "Depo Terminal Stok 1",
            "StokMuhasebeID": null,
            "StokVergiID": null,
            "Brm1ID": 1,
            "Brm2ID": null,
            "Brm3ID": null,
            "UretimBrmID": null,
            "RaporBrmID": null,
            "CevirimBrm2": 0.000000,
            "CevirimBrm3": 0.000000,
            "Kalinlik": 0.000000,
            "En": 0.000000,
            "Boy": 0.000000,
            "Yogunluk": 0.000000,
            "Agirlik": 0.000000,
            "GTIP": null,
            "HizmetMi": false,
            "StandartMi": false,
            "ZorunluDemirbas": false,
            "ZorunluDekont": false,
            "ZorunluCari": false,
            "ZorunluMasrafMerkezi": false,
            "AciklamalarID": null,
            "Aciklama": null,
            "Seviye": 0,
            "FiyatEtiketi": null,
            "BayiGozuksunMu": false,
            "BayiMaksMiktar": 0,
            "HariciDepoMiktar": 0.000000,
            "KargoUcreti": 0.000000,
            "SubeID": 1,
            "SirketID": 1,
            "Durum": true,
            "TipID": 105001,
            "EntegrasyonTanimID": 63,
            "Kod1ID": null,
            "Kod2ID": null,
            "Kod3ID": null,
            "Kod4ID": null,
            "Kod5ID": null,
            "Kod6ID": null,
            "Etiket1ID": null,
            "Etiket2ID": null,
            "Etiket3ID": null,
            "Etiket4ID": null,
            "Etiket5ID": null,
            "YedekD1": 0.000000,
            "YedekD2": 0.000000,
            "YedekD3": 0.000000,
            "YedekS1": null,
            "YedekS2": null,
            "YedekS3": null,
            "SablonID": null,
            "KartPuan": 0.000000,
            "TakipYontemi": 0,
            "TakipYontemiKodOnEki": null,
            "TakipYontemiUretimBireBirIliski": false,
            "RafTakibi": true,
            "PaketTakibi": true
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stok Kod Ağacı Toplu Ekle
Yeni bir kod kartı eklemek için  
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Örnek Değer | Tanım |
| --- | --- | --- |
| SubeID | 1 | Kodun bulunduğu şubenin ID'sidir. |
| SirketID | 1 | Kodun ait olduğu şirketin ID'sidir. |
| Kod1 | "Kod 1 adı" | Kod 1 gözüken adıdır. |
| TipID | 3001 | Stok kartı olduğunu belirtir. |
| Tip2ID | 105001 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Gelir-gider hareketleri gibi işlemler de stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için Tip2ID belirtilmelidir. |

> _**Kartlarda yer alan hiyerarşik sıralamayı sağlayan kod ağacı bölümünde öncelikle kodların oluşturulması gerekmektedir. Kod adını yollayarak oluşturabilirsiniz. Kodlar hiyerarşik olarak oluşturulur. 6 adet kod yapısı oluşturacaksak Kod 1-> Kod 2-> Kod 3 -> Kod 4 -> Kod 5-> Kod 6 şeklinde ad girmeliyiz. Üst kodlar olmadan alt kodları oluşturamazsınız.**_ 
  

| Parametre | TipID | Tip2ID |
| --- | --- | --- |
| Banka | 6002 |  |
| Kasa | 5001 |  |
| Cari | 2001 |  |
| Personel | 1401 |  |
| Reçete | 12010 |  |
| Stok | 3001 | 105001 |
| Demirbaş | 3001 | 105003 |
| Gelir - Gider | 3001 | 105002 |
### Method: POST
>```
>{{BaseUrl}}/api/Kodlar/IDSizTumSeviyeleriBirdenKaydet
>```
### Body (**raw**)

```json
        {
            "TipID": 3001,
            "Tip2ID": 105002,
            "SubeID": 1,
            "SirketID": 1,
            "Kod1": "kırtasiye",
            "Kod2": null,
            "Kod3": null,
            "Kod4": null,
            "Kod5": null,
            "Kod6": null
        }
```

### Response: 200
```json
{
    "Model": {
        "SirketID": 1,
        "SubeID": 1,
        "TipID": 3001,
        "Tip2ID": 105002,
        "Kod1ID": 38,
        "Kod2ID": null,
        "Kod3ID": null,
        "Kod4ID": null,
        "Kod5ID": null,
        "Kod6ID": null,
        "Kod1": "kırtasiye",
        "Kod2": null,
        "Kod3": null,
        "Kod4": null,
        "Kod5": null,
        "Kod6": null
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stok Etiket Ekle
Yeni bir etiket kartı eklemek için  
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Örnek Değer | Tanım |
| --- | --- | --- |
| SubeID | 1 | Etiketin bulunduğu şubenin ID'sidir. |
| SirketID | 1 | Etiketin ait olduğu şirketin ID'sidir. |
| EtiketAdi | "Etiket 1 adı" | Etiket 1 gözüken adıdır. |
| TipID | 3001 | Stok kartı olduğunu belirtir. |
| Tip2ID | 105001 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Gelir-gider hareketleri gibi işlemler de stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için Tip2ID belirtilmelidir. |
| Seviye | 1 | Etiketin seviyesini belirtir. |

> _**Kartlarda yer alan hiyerarşik sıralamayı sağlayan etiket bölümünde öncelikle etiketlerin oluşturulması gerekmektedir. etiket adını yollayarak oluşturabilirsiniz.**_ 
  

| Parametre | TipID | Tip2ID |
| --- | --- | --- |
| Banka | 6002 |  |
| Kasa | 5001 |  |
| Cari | 2001 |  |
| Personel | 1401 |  |
| Reçete | 12010 |  |
| Stok | 3001 | 105001 |
| Demirbaş | 3001 | 105003 |
| Gelir - Gider | 3001 | 105002 |
### Method: POST
>```
>{{BaseUrl}}/api/Etiketler/post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "SirketID": 1,
            "SubeID": 1,
            "TipID": 3001,
            "Tip2ID": 105001,
            "EtiketAdi": "deneme2",
            "Seviye": 1
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "SirketID": 1,
        "SubeID": 1,
        "TipID": 3001,
        "TipKodu": null,
        "Tip2ID": 105001,
        "Tip2Kodu": null,
        "EtiketID": 3,
        "EtiketAdi": "deneme2",
        "Seviye": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stok Kod Ağacı Toplu Listele
Kod ağacını toplu olarak listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/Kodlar/KodlarTumSeviyeler?TipID=3001
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|TipID|3001|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stok Etiket Listele
### Method: GET
>```
>{{BaseUrl}}/api/Etiketler?TipID=3001
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|TipID|3001|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stok Düzenle
Stoktaki bir ürünü düzenlemek içindir.

###### Stok eklemek ile düzenlemek arasındaki fark KayitTipi=2 olmasıdır ve StokID dışındaki parametrelerin zorunlu olmamasıdır.
### Method: POST
>```
>{{BaseUrl}}/api/Stok/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
 {
            "StokID": 237,
            "StokKodu": "DTSK1",
            "StokAdi": "Depo Terminal Stok 1",
            "StokKisaKodu": "DTSK1",
            "StokKisaAdi": "Depo Terminal Stok 1",
            "StokMuhasebeID": null,
            "StokVergiID": null,
            "Brm1ID": 1,
            "Brm2ID": null,
            "Brm3ID": null,
            "UretimBrmID": null,
            "RaporBrmID": null,
            "CevirimBrm2": 0.000000,
            "CevirimBrm3": 0.000000,
            "Kalinlik": 0.000000,
            "En": 0.000000,
            "Boy": 0.000000,
            "Yogunluk": 0.000000,
            "Agirlik": 0.000000,
            "GTIP": null,
            "HizmetMi": false,
            "StandartMi": false,
            "ZorunluDemirbas": false,
            "ZorunluDekont": false,
            "ZorunluCari": false,
            "ZorunluMasrafMerkezi": false,
            "AciklamalarID": null,
            "Aciklama": null,
            "Seviye": 0,
            "FiyatEtiketi": null,
            "BayiGozuksunMu": false,
            "BayiMaksMiktar": 0,
            "HariciDepoMiktar": 0.000000,
            "KargoUcreti": 0.000000,
            "SubeID": 1,
            "SirketID": 1,
            "Durum": true,
            "TipID": 105001,
            "EntegrasyonTanimID": 63,
            "Kod1ID": null,
            "Kod2ID": null,
            "Kod3ID": null,
            "Kod4ID": null,
            "Kod5ID": null,
            "Kod6ID": null,
            "Etiket1ID": null,
            "Etiket2ID": null,
            "Etiket3ID": null,
            "Etiket4ID": null,
            "Etiket5ID": null,
            "YedekD1": 0.000000,
            "YedekD2": 0.000000,
            "YedekD3": 0.000000,
            "YedekS1": null,
            "YedekS2": null,
            "YedekS3": null,
            "SablonID": null,
            "KartPuan": 0.000000,
            "TakipYontemi": 0,
            "TakipYontemiKodOnEki": null,
            "TakipYontemiUretimBireBirIliski": false,
            "RafTakibi": true,
            "PaketTakibi": true
 }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stoktaki Ürünü Sil
Stoktaki bir ürünü silmek içindir.

######  Stok silmek ile düzenlemek arasındaki fark KayitTipi=-1 olmasıdır. Stoğu silerken bağlı olduğu bütün fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
### Method: POST
>```
>{{BaseUrl}}/api/Stok/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
"StokID":"{{stokID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stok Hareketleri Liste
Bu uç nokta ile belirtilen kısıtlara göre stok hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/StokHareketleri
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|EsnekArama|{{esnekAramaSTHar}}|
|SirketID|{{sirketID}}|
|SubeID|{{subeID}}|
|TarihBas|{{birAyOnce}}|
|TarihBit|{{bugun}}|
|StokID||
|TipID||
|SozlesmeID||
|BirimID|{{brm1ID}}|
|CariID||
|DekontID||
|DepoID||
|DovizID||
|HareketID||
|OtomatikKalem||
|PlasiyerID||
|YevmiyeFisHareketID||
|BA|A|
|DevirGetir|true|
|VadeBas||
|VadeBit||
|TutarBas||
|TutarBit||
|TutarDvzBas||
|TutarDvzBit||
|OlsID||
|DgsID||
|OlsTarBas||
|OlsTarBit||
|DgsTarBas||
|DgsTarBit||



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sipariş Hareketleri Liste
Bu uç nokta ile belirtilen kısıtlara göre sipariş hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/SipStokHareketleri
>```
### Query Params

|Param|value|
|---|---|
|EsnekArama|null|
|SirketID|{{sirketID}}|
|SubeID|{{subeID}}|
|StokID|null|
|TarihBas|{{birAyOnce}}|
|TarihBit|{{bugun}}|
|TipID|{{tipIDAlinanSiparis}}|
|SozlesmeID|null|
|BirimID|1|
|CariID|null|
|DekontID|null|
|DepoID|null|
|DovizID|null|
|HareketID|null|
|OtomatikKalem|null|
|PlasiyerID|null|
|YevmiyeFisHareketID|null|
|BA|A|
|DevirGetir|true|
|VadeBas|null|
|VadeBit|null|
|TutarBas|null|
|TutarBit|null|
|TutarDvzBas|null|
|TutarDvzBit|null|
|OlsID|null|
|DgsID|null|
|OlsTarBas|null|
|OlsTarBit|null|
|DgsTarBas|null|
|DgsTarBit|null|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: StokDepo Miktar Min-Max
Bu uç nokta ile belirtilen kısıtlara göre stok depo miktar minimum maksimum hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/StokDepoMiktar
>```
### Query Params

|Param|value|
|---|---|
|StokID|null|
|DepoID|null|
|OlsID|null|
|DgsID|null|
|OlsTarBas|null|
|OlsTarBit|null|
|DgsTarBas|null|
|DgsTarBit|null|


### Response: 200
```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 2,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 2
    },
    "Model": [
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "OnayDurum": 1,
            "OlsTar": "2023-05-17T17:33:40.567",
            "DgsTar": "2023-05-18T09:08:14.57",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "DepoKodu": "DPM",
            "DepoAdi": "Depom",
            "StokKodu": "STOKOTO00000001",
            "StokAdi": "Otomatik Aktarım Stok Kartı",
            "EsnekAramaKisiti": "STOKOTO00000001 Otomatik Aktarım Stok Kartı DPM Depom",
            "StokDepoMiktarID": 1,
            "SubeID": 1,
            "SirketID": 1,
            "DepoID": 2,
            "StokID": 202,
            "Minimum": 5,
            "Maksimum": 25,
            "Durum": true
        },
        {
            "SubeKodu": "S-3-TUM",
            "SubeAdi": "Tüm 3",
            "SirketKodu": "Aaro",
            "SirketAdi": "aaro",
            "OnayDurum": 1,
            "OlsTar": "2023-05-18T09:15:30.25",
            "DgsTar": "2023-05-18T09:15:30.25",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "DepoKodu": "GG",
            "DepoAdi": "GelirGider Depo",
            "StokKodu": "STOKOTO00000001",
            "StokAdi": "Otomatik Aktarım Stok Kartı",
            "EsnekAramaKisiti": "STOKOTO00000001 Otomatik Aktarım Stok Kartı GG GelirGider Depo",
            "StokDepoMiktarID": 3,
            "SubeID": 0,
            "SirketID": 3,
            "DepoID": 1,
            "StokID": 202,
            "Minimum": 5,
            "Maksimum": 5,
            "Durum": true
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: StokDepo Miktar Min-Max Ekle
Yeni bir stok depo miktar min-max kartı eklemek için kullanılır.  
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |
### Method: POST
>```
>{{BaseUrl}}/api/StokDepoMiktar/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "SubeID": 1,
            "SirketID": 1,
            "DepoID": 2,
            "StokID": 202,
            "Minimum": 15.000000,
            "Maksimum": 25.000000,
            "Durum": true
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "StokDepoMiktarID": 4,
        "SubeID": 1,
        "SirketID": 1,
        "DepoID": 2,
        "StokID": 202,
        "Minimum": 15,
        "Maksimum": 25,
        "Durum": true
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: StokDepo Miktar Min-Max Düzenle
Stok Depo Miktar Min-Max'ı düzenlemek içindir.
### Method: POST
>```
>{{BaseUrl}}/api/StokDepoMiktar/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "StokDepoMiktarID": 4,
            "SubeID": 1,
            "SirketID": 1,
            "DepoID": 1,
            "StokID": 202,
            "Minimum": 15.000000,
            "Maksimum": 25.000000,
            "Durum": true
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "StokDepoMiktarID": 4,
        "SubeID": 1,
        "SirketID": 1,
        "DepoID": 1,
        "StokID": 202,
        "Minimum": 15,
        "Maksimum": 25,
        "Durum": true
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: StokDepo Miktar Min-Max Sil
Stok Depo Miktar Min-Max'ı silmek içindir.
### Method: POST
>```
>{{BaseUrl}}/api/StokDepoMiktar/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "StokDepoMiktarID": 4
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "StokDepoMiktarID": 4,
        "SubeID": 0,
        "SirketID": 0,
        "DepoID": 0,
        "StokID": 0,
        "Minimum": 0,
        "Maksimum": 0,
        "Durum": false
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Seri Lot 


## End-point: Seri Lot Getir
Bu uç nokta ile seri lot bilgilerini toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/SeriLot
>```
### Body (**raw**)

```json

```

### Response: 200
```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 10,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 10
    },
    "Model": [
        {
            "StokKodu": "000001",
            "StokAdi": "Deneme 1",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": -1,
            "OnayDurum": 1,
            "OlsTar": "2023-08-21T17:51:51.21",
            "DgsTar": "2023-08-21T17:51:51.21",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SeriLotID": 3,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "000001",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 231,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
        },
        {
            "StokKodu": "000003",
            "StokAdi": "Deneme-3",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": 0,
            "OnayDurum": 1,
            "OlsTar": "2023-08-24T14:00:32.593",
            "DgsTar": "2023-08-24T14:00:32.593",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SeriLotID": 9,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "000002",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 233,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
        },
        {
            "StokKodu": "000003",
            "StokAdi": "Deneme-3",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": 0,
            "OnayDurum": 1,
            "OlsTar": "2023-08-24T14:00:33",
            "DgsTar": "2023-08-24T14:00:33",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SeriLotID": 10,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "000003",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 233,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
        },
        {
            "StokKodu": "000003",
            "StokAdi": "Deneme-3",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": -1,
            "OnayDurum": 1,
            "OlsTar": "2023-08-24T14:00:33.297",
            "DgsTar": "2023-08-24T14:00:33.297",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SeriLotID": 11,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "000004",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 233,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
        },
        {
            "StokKodu": "000003",
            "StokAdi": "Deneme-3",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": 0,
            "OnayDurum": 1,
            "OlsTar": "2023-08-24T14:00:33.597",
            "DgsTar": "2023-08-24T14:00:33.597",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SeriLotID": 12,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "000005",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 233,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
        },
        {
            "StokKodu": "000003",
            "StokAdi": "Deneme-3",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": 0,
            "OnayDurum": 1,
            "OlsTar": "2023-08-24T14:00:33.88",
            "DgsTar": "2023-08-24T14:00:33.88",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SeriLotID": 13,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "000006",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 233,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
        },
        {
            "StokKodu": "STOKOTO00000001",
            "StokAdi": "Otomatik Aktarım Stok Kartı",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": 0,
            "OnayDurum": 1,
            "OlsTar": "2023-09-21T09:12:25.083",
            "DgsTar": "2023-09-21T09:12:25.083",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SeriLotID": 14,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "000007",
            "SeriLotAdi": " ",
            "TipID": 153001,
            "StokID": 202,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
        },
        {
            "StokKodu": "000000000000001",
            "StokAdi": "İlk Stok Kartım",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": 0,
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T10:57:21.433",
            "DgsTar": "2023-09-26T10:57:21.433",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SeriLotID": 45,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "001111",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 201,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
        },
        {
            "StokKodu": "000000000000001",
            "StokAdi": "İlk Stok Kartım",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": 0,
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T10:57:21.727",
            "DgsTar": "2023-09-26T10:57:21.727",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SeriLotID": 46,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "001112",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 201,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
        },
        {
            "StokKodu": "000001",
            "StokAdi": "Deneme 1",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": 0,
            "OnayDurum": 1,
            "OlsTar": "2023-09-27T12:10:56.43",
            "DgsTar": "2023-09-27T12:10:56.43",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SeriLotID": 50,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "500001",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 231,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Seri Lot Ekle
Yeni bir stok kartı eklemek için  
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| SubeID | 1 | Seri Lotun bulunduğu şubenin ID'sidir. | Evet |
| SirketID | 1 | Seri Lotun ait olduğu şirketin ID'sidir. | Evet |
| SeriLotKodu | "000001" | Seri Lotun kodudur. | Evet |
| SeriLotAdi | "" | Seri Lotun adıdır. Boş string yollanmalıdır. | Evet |
| Durum | true | Seri lot kartının aktif veya pasif olduğunu belirlemektedir | Evet |
| TipID | 153001 | Seri : 153001  <br>Lot: 153002 | Evet |
| StokID | 231 | Serinin bağlı olduğu stoğun idsini belirtir | Evet |
| SonKullanmaTarihi | null | Seri / Lotun son kullanma tarihini belirtir | Evet |
| IsEmriID | null | Seri Lotun bağlı olduğu iş emrini belirtir. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/SeriLot/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "500001",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 231,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "SeriLotID": 50,
        "SubeID": 1,
        "SirketID": 1,
        "SeriLotKodu": "500001",
        "SeriLotAdi": "",
        "TipID": 153001,
        "StokID": 231,
        "SonKullanmaTarihi": null,
        "IsEmriID": null,
        "Durum": true
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Seri Lot Düzenle
Seri Lot bilgilerini düzenlemek içindir.
### Method: POST
>```
>{{BaseUrl}}/api/SeriLot/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
 {
            "SeriLotID": 3,
            "StokKodu": "000001",
            "StokAdi": "Deneme 1",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Seri",
            "Brm1Kodu": "AD",
            "Miktar": -1.000000,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotKodu": "000001",
            "SeriLotAdi": "",
            "TipID": 153001,
            "StokID": 231,
            "SonKullanmaTarihi": null,
            "IsEmriID": null,
            "Durum": true
 }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Seri Lot Sil
Stoktaki bir ürünü silmek içindir.

######  Stok silmek ile düzenlemek arasındaki fark KayitTipi=-1 olmasıdır. Stoğu silerken bağlı olduğu bütün fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
### Method: POST
>```
>{{BaseUrl}}/api/SeriLot/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "SeriLotID": 48
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "SeriLotID": 48,
        "SubeID": 0,
        "SirketID": 0,
        "SeriLotKodu": null,
        "SeriLotAdi": null,
        "TipID": 0,
        "StokID": 0,
        "SonKullanmaTarihi": null,
        "IsEmriID": null,
        "Durum": false
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Seri Lot Hareketleri Liste
Bu uç nokta ile belirtilen kısıtlara göre seri lot hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/SeriLotHareketleri?
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
||null|


### Response: 200
```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 6,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 6
    },
    "Model": [
        {
            "SeriLotKodu": "000004",
            "SeriLotAdi": "",
            "StokRafKodu": "02B.03.78",
            "StokRafAdi": null,
            "PaketKodu": "000001",
            "PaketAdi": " ",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "StokID": 202,
            "StokKodu": "STOKOTO00000001",
            "StokAdi": "Otomatik Aktarım Stok Kartı",
            "TipID": 10009,
            "TipKodu": "SIR",
            "TipAdi": "Satış İrsaliyesi",
            "Brm1Kodu": "AD",
            "BakiyeMiktar": -1,
            "OnayDurum": 1,
            "OlsTar": "2023-09-21T09:12:30.643",
            "DgsTar": "2023-09-25T14:52:07.323",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 7,
            "DgsKodu": "d",
            "DgsAdi": "d",
            "SonKullanmaTarihi": null,
            "DepoKodu": "DPM",
            "DepoID": 2,
            "HareketID": 15,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotID": 11,
            "StokRafID": 3,
            "PaketID": 1,
            "Tarih": "2023-08-23T00:00:00",
            "BA": "A",
            "Miktar": 1,
            "StokHareketID": 202,
            "IsEmriID": null,
            "Aciklama": null,
            "Durum": true
        },
        {
            "SeriLotKodu": "000001",
            "SeriLotAdi": "",
            "StokRafKodu": "02B.03.78",
            "StokRafAdi": null,
            "PaketKodu": "000003",
            "PaketAdi": " ",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "StokID": 202,
            "StokKodu": "STOKOTO00000001",
            "StokAdi": "Otomatik Aktarım Stok Kartı",
            "TipID": 10009,
            "TipKodu": "SIR",
            "TipAdi": "Satış İrsaliyesi",
            "Brm1Kodu": "AD",
            "BakiyeMiktar": -2,
            "OnayDurum": 1,
            "OlsTar": "2023-09-25T14:51:51.003",
            "DgsTar": "2023-09-25T14:52:07.403",
            "OlsID": 7,
            "OlsKodu": "d",
            "OlsAdi": "d",
            "DgsID": 7,
            "DgsKodu": "d",
            "DgsAdi": "d",
            "SonKullanmaTarihi": null,
            "DepoKodu": "DPM",
            "DepoID": 2,
            "HareketID": 16,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotID": 3,
            "StokRafID": 3,
            "PaketID": 4,
            "Tarih": "2023-08-23T00:00:00",
            "BA": "A",
            "Miktar": 1,
            "StokHareketID": 202,
            "IsEmriID": null,
            "Aciklama": null,
            "Durum": true
        },
        {
            "SeriLotKodu": "001111",
            "SeriLotAdi": "",
            "StokRafKodu": "02B.03.78",
            "StokRafAdi": null,
            "PaketKodu": "000002",
            "PaketAdi": " ",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "İlk Stok Kartım",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Arası Transfer",
            "Brm1Kodu": "AD",
            "BakiyeMiktar": -3,
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T10:54:50.107",
            "DgsTar": "2023-09-26T10:57:21.573",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SonKullanmaTarihi": null,
            "DepoKodu": "DPM",
            "DepoID": 2,
            "HareketID": 45,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotID": 45,
            "StokRafID": 3,
            "PaketID": 3,
            "Tarih": "2023-09-04T00:00:00",
            "BA": "A",
            "Miktar": 1,
            "StokHareketID": 165,
            "IsEmriID": null,
            "Aciklama": null,
            "Durum": true
        },
        {
            "SeriLotKodu": "001112",
            "SeriLotAdi": "",
            "StokRafKodu": "D-3",
            "StokRafAdi": null,
            "PaketKodu": "000001",
            "PaketAdi": " ",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "İlk Stok Kartım",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Arası Transfer",
            "Brm1Kodu": "AD",
            "BakiyeMiktar": -4,
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T10:54:50.407",
            "DgsTar": "2023-09-26T10:57:21.857",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SonKullanmaTarihi": null,
            "DepoKodu": "DPM",
            "DepoID": 2,
            "HareketID": 46,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotID": 46,
            "StokRafID": 4,
            "PaketID": 1,
            "Tarih": "2023-09-04T00:00:00",
            "BA": "A",
            "Miktar": 1,
            "StokHareketID": 165,
            "IsEmriID": null,
            "Aciklama": null,
            "Durum": true
        },
        {
            "SeriLotKodu": "001111",
            "SeriLotAdi": "",
            "StokRafKodu": "02A.02.01",
            "StokRafAdi": "a",
            "PaketKodu": "000001",
            "PaketAdi": " ",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "İlk Stok Kartım",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Arası Transfer",
            "Brm1Kodu": "AD",
            "BakiyeMiktar": -3,
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T10:57:22.033",
            "DgsTar": "2023-09-26T10:57:22.033",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SonKullanmaTarihi": null,
            "DepoKodu": "GG",
            "DepoID": 1,
            "HareketID": 54,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotID": 45,
            "StokRafID": 2,
            "PaketID": 1,
            "Tarih": "2023-09-04T00:00:00",
            "BA": "B",
            "Miktar": 1,
            "StokHareketID": 166,
            "IsEmriID": null,
            "Aciklama": null,
            "Durum": true
        },
        {
            "SeriLotKodu": "001112",
            "SeriLotAdi": "",
            "StokRafKodu": "02A.02.01",
            "StokRafAdi": "a",
            "PaketKodu": "000001",
            "PaketAdi": " ",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "İlk Stok Kartım",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Arası Transfer",
            "Brm1Kodu": "AD",
            "BakiyeMiktar": -2,
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T10:57:22.207",
            "DgsTar": "2023-09-26T10:57:22.207",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "SonKullanmaTarihi": null,
            "DepoKodu": "GG",
            "DepoID": 1,
            "HareketID": 55,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotID": 46,
            "StokRafID": 2,
            "PaketID": 1,
            "Tarih": "2023-09-04T00:00:00",
            "BA": "B",
            "Miktar": 1,
            "StokHareketID": 166,
            "IsEmriID": null,
            "Aciklama": null,
            "Durum": true
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Seri Lot Hızlı Kayıt
### Sorgu Body JSON açıklaması

**Ön Bilgi**

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| StokHareketID | 202 | Hareketteki stoğun idsini belirtir. | Evet |

**Satırlar**

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| HareketID | \-1 | Seri lot satırının id sini belirtir. Yeni bir kayıtsa yollanmasına gerek yoktur. Düzenleme ya da silme yapılıyorsa hangi satır olduğunun yollanması gerekmektedir. |  |
| StokRafID | 1 | Raf takibi yapılıyorsa seçilen rafın id bilgisini belirtir. |  |
| PaketID | 1 | Paket takibi yapılıyorsa seçilen rafın id bilgisini belirtir. |  |
| YeniKodOlustur | 1 ya da 0 | Yeni bir seri/lot oluşturuluyorsa bu bilgi gönderilir. |  |
| SeriLotID | 5 | Seri lotun id sini belirtir. Yeni bir kayıtsa yollanmasına gerek yoktur. Düzenleme ya da silme yapılıyorsa hangi satır olduğunun yollanması gerekmektedir. |  |
| SeriLotKodu | 500016 | Düzenlenen seri lotun yeni kodunu belirtir. | Yeni seri lot oluşturulacaksa zorunlu. |
| Miktar | 1.0000 | Seri lot satırının miktarını belirtir. |  |
| UrAkisOperasyonAnaMamulSeriLotID | 1 | Üretim hareketinin ana mamulunde tüm hammaddelerin seri lotlarının takibi yapılacaksa kullanılır. |  |
| TransferStokRafID | 1 | Depolar arası transfer de transfer edilen raf id bilgisini belirtir. | Depolar arası transfer için zorunlu |
| TransferPaketID | 1 | Depolar arası transfer de transfer edilen paket id bilgisini belirtir. | Depolar arası transfer için zorunlu |
### Method: POST
>```
>{{BaseUrl}}/api/SeriLot/SeriLotHizliKayit
>```
### Body (**raw**)

```json
{
    "OnBilgi" :{
        "StokHareketID": 653
    },
    "Satirlar": [
            {
                "HareketID": -1, 
                "SeriLotID": 62,    
                "SeriLotKodu": "500011", //Yeni seri lot oluşturulacaksa zorunlu.
                "Miktar": 3.0000,
                "YeniKodOlustur": false,  //Yeni seri lot oluşturulacaksa true olmalı.
                "StokRafID": 8,
                "PaketID": 13
            },
            {
                "HareketID": 409,
                "SeriLotID": 62,
                "SeriLotKodu": "500011",
                "Miktar": 3.0000,
                "YeniKodOlustur": false,
                "StokRafID": 8,
                "PaketID": 13
            }
        ]

    
}
```

### Response: 200
```json
{
    "Mesajlar": {
        "Mesaj": "Seri/Lot tanımlari ve Hareketleri işlendi"
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Seri Lot Hızlı Kayıt Getir
### Sorgu Body JSON açıklaması

**Ön Bilgi**

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| StokHareketID | 202 | Hareketteki stoğun idsini belirtir. | Evet |
### Method: GET
>```
>{{BaseUrl}}/api/SeriLot/SeriLotHizliKayit
>```
### Body (**raw**)

```json
{
        "StokHareketID": 649
}
```

### Response: 200
```json
{
    "Model": {
        "OnBilgi": {
            "UrAkisOperasyonHammaddeID": null,
            "UrAkisOperasyonMamulID": null,
            "IsEmriID": null,
            "StokHareketTipID": 10005,
            "Tarih": "2023-11-15T00:00:00",
            "BA": "A",
            "SirketID": 1,
            "SubeID": 1,
            "ToplamMiktar": 6,
            "SeriLotTipID": 153002,
            "StokID": 201,
            "DepoID": 2,
            "Depo2ID": null,
            "SeriLotTakibi": false,
            "RafTakibi": true,
            "PaketTakibi": true,
            "KarsiStokHareketID": 0,
            "DepoKodu": "DPM",
            "StokKodu": "000000000000001",
            "StokAdi": "İlk Stok Kartım",
            "IsEmriUretimIliskiTakibi": false,
            "TakipYontemiKodOnEki": null,
            "StokHareketID": 649,
            "OtomatikSeriLotKoduHazirla": false
        },
        "Satirlar": [
            {
                "HareketID": 385,
                "StokRafID": 8,
                "StokRafKodu": "Temizlik Rafı",
                "PaketID": 13,
                "PaketKodu": "T1",
                "YeniKodOlustur": false,
                "SeriLotID": 62,
                "EskiSeriLotID": 62,
                "SeriLotKodu": "500011",
                "EskiSeriLotKodu": "500011",
                "Miktar": 3,
                "BA": null,
                "UrAkisOperasyonAnaMamulSeriLotID": null,
                "UrAkisOperasyonAnaMamulSeriLotKodu": null,
                "TransferStokRafID": null,
                "TransferStokRafKodu": null,
                "TransferPaketID": null,
                "TransferPaketKodu": null,
                "TransferHareketID": null
            },
            {
                "HareketID": 409,
                "StokRafID": 8,
                "StokRafKodu": "Temizlik Rafı",
                "PaketID": 13,
                "PaketKodu": "T1",
                "YeniKodOlustur": false,
                "SeriLotID": 62,
                "EskiSeriLotID": 62,
                "SeriLotKodu": "500011",
                "EskiSeriLotKodu": "500011",
                "Miktar": 3,
                "BA": null,
                "UrAkisOperasyonAnaMamulSeriLotID": null,
                "UrAkisOperasyonAnaMamulSeriLotKodu": null,
                "TransferStokRafID": null,
                "TransferStokRafKodu": null,
                "TransferPaketID": null,
                "TransferPaketKodu": null,
                "TransferHareketID": null
            }
        ]
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Seri Lot Hareketleri Ekle
Yeni bir seri lot hareketini eklemek için  
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| SubeID | 1 | Seri Lot hareketlerinin bulunduğu şubenin ID'sidir. | Evet |
| SirketID | 1 | Seri Lot hareketlerinin ait olduğu şirketin ID'sidir. | Evet |
| Durum | true | Seri lot hareketlerinin aktif veya pasif olduğunu belirlemektedir | Evet |
| SeriLotID | 11 | Harekete bağlı olan seri lotun idsidir. | Evet |
| StokID | 231 | Serinin bağlı olduğu stoğun idsini belirtir | Evet |
| Tarih | 2023-08-23 | Seri / Lot hareketlerinin tarihini belirtir. | Evet |
| IsEmriID | null | Seri Lotun bağlı olduğu iş emrini belirtir. | Evet |
| BA | A | Hareketin borç mu alacak mı olduğunu belritir | Evet |
| Miktar | 1.000000 | Hareketin miktarını belirtir. | Evet |
| StokHareketID | 202 | Hareketteki stoğun idsini belirtir. | Evet |
| Aciklama | açıklama | Hareketin açıklamasını belirtir. | Evet |
| UrAkisOperasyonAnaMamulSeriLotID | 1 |  | Hayır |
| UrAkisOperasyonHammaddeID | 1 |  |  |
| UrAkisOperasyonMamulID | 1 |  |  |
### Method: POST
>```
>{{BaseUrl}}/api/SeriLotHareketleri/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotID": 11,
            "StokRafID": null,
            "PaketID": null,
            "Tarih": "2023-08-23",
            "BA": "A",
            "Miktar": 1.000000,
            "StokHareketID": 6,
            "IsEmriID": null,
            "Aciklama": null,
            "Durum": true
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "SeriLotID": 50,
        "SubeID": 1,
        "SirketID": 1,
        "SeriLotKodu": "500001",
        "SeriLotAdi": "",
        "TipID": 153001,
        "StokID": 231,
        "SonKullanmaTarihi": null,
        "IsEmriID": null,
        "Durum": true
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Seri Lot Hareketleri Düzenle
Seri Lot bilgilerini düzenlemek içindir.
### Method: POST
>```
>{{BaseUrl}}/api/SeriLotHareketleri/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
 {
            "SeriLotKodu": "001112",
            "SeriLotAdi": "",
            "StokRafKodu": "D-3",
            "StokRafAdi": null,
            "PaketKodu": "000001",
            "PaketAdi": " ",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "İlk Stok Kartım",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Arası Transfer",
            "Brm1Kodu": "AD",
            "BakiyeMiktar": -4.000000,
            "SonKullanmaTarihi": null,
            "DepoKodu": "DPM",
            "DepoID": 2,
            "HareketID": 46,
            "SubeID": 1,
            "SirketID": 1,
            "SeriLotID": 46,
            "StokRafID": 4,
            "PaketID": 1,
            "Tarih": "2023-09-04T00:00:00",
            "BA": "A",
            "Miktar": 1.000000,
            "StokHareketID": 202,
            "IsEmriID": null,
            "Aciklama": null,
            "Durum": true
 }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Seri Lot Hareketleri Sil
Seri Lot Hareketini silmek içindir.
### Method: POST
>```
>{{BaseUrl}}/api/SeriLotHareketleri/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "HareketID": 56
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "SeriLotID": 48,
        "SubeID": 0,
        "SirketID": 0,
        "SeriLotKodu": null,
        "SeriLotAdi": null,
        "TipID": 0,
        "StokID": 0,
        "SonKullanmaTarihi": null,
        "IsEmriID": null,
        "Durum": false
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Raf Getir
Bu uç nokta ile raf bilgilerini toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/StokRaf
>```
### Body (**raw**)

```json

```

### Response: 200
```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 12,
        "ToplamSayfaSayisi": 2,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": true,
        "SayfaSatirSayisiAktifSayfada": 10
    },
    "Model": [
        {
            "DepoKodu": "GG",
            "DepoAdi": "GelirGider Depo",
            "OnayDurum": 1,
            "OlsTar": "2023-08-16T17:10:57.73",
            "DgsTar": "2023-08-22T15:43:54.13",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StokRafID": 2,
            "StokRafKodu": "02A.02.01",
            "Aciklama": "a",
            "DepoID": 1,
            "KonumX": 1,
            "KonumY": 1,
            "KonumZ": 1,
            "En": 1,
            "Boy": 1,
            "Yukseklik": 1,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 1,
            "Durum": true
        },
        {
            "DepoKodu": "GG",
            "DepoAdi": "GelirGider Depo",
            "OnayDurum": 1,
            "OlsTar": "2023-11-15T17:28:23.137",
            "DgsTar": "2023-11-15T17:28:23.137",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StokRafID": 14,
            "StokRafKodu": "02A.02.02",
            "Aciklama": "a",
            "DepoID": 1,
            "KonumX": 1,
            "KonumY": 1,
            "KonumZ": 1,
            "En": 1,
            "Boy": 1,
            "Yukseklik": 1,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 1,
            "Durum": true
        },
        {
            "DepoKodu": "DPM",
            "DepoAdi": "Depom",
            "OnayDurum": 1,
            "OlsTar": "2023-08-21T16:53:08.797",
            "DgsTar": "2023-09-05T12:11:02.317",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StokRafID": 3,
            "StokRafKodu": "02B.03.78",
            "Aciklama": null,
            "DepoID": 2,
            "KonumX": 1,
            "KonumY": 1,
            "KonumZ": 1,
            "En": 0,
            "Boy": 0,
            "Yukseklik": 0,
            "EtiketKonum": 1,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 0,
            "Durum": true
        },
        {
            "DepoKodu": "DPM",
            "DepoAdi": "Depom",
            "OnayDurum": 1,
            "OlsTar": "2023-08-24T13:52:06.263",
            "DgsTar": "2023-08-24T13:52:06.263",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StokRafID": 4,
            "StokRafKodu": "D-3",
            "Aciklama": null,
            "DepoID": 2,
            "KonumX": 0,
            "KonumY": 0,
            "KonumZ": 0,
            "En": 0,
            "Boy": 0,
            "Yukseklik": 0,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 0,
            "Durum": true
        },
        {
            "DepoKodu": "DPM",
            "DepoAdi": "Depom",
            "OnayDurum": 1,
            "OlsTar": "2023-10-18T10:42:46.083",
            "DgsTar": "2023-10-18T10:42:49.337",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StokRafID": 9,
            "StokRafKodu": "Kırtasiye Rafı",
            "Aciklama": null,
            "DepoID": 2,
            "KonumX": 0,
            "KonumY": 0,
            "KonumZ": 0,
            "En": 0,
            "Boy": 0,
            "Yukseklik": 0,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 0,
            "Durum": true
        },
        {
            "DepoKodu": "DPM",
            "DepoAdi": "Depom",
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T13:13:12.33",
            "DgsTar": "2023-10-05T17:10:19.09",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StokRafID": 5,
            "StokRafKodu": "R.01.1",
            "Aciklama": null,
            "DepoID": 2,
            "KonumX": 0,
            "KonumY": 0,
            "KonumZ": 0,
            "En": 0,
            "Boy": 0,
            "Yukseklik": 0,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 0,
            "Durum": true
        },
        {
            "DepoKodu": "DPM",
            "DepoAdi": "Depom",
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T13:13:28.533",
            "DgsTar": "2023-09-26T13:15:30.267",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StokRafID": 6,
            "StokRafKodu": "R.01.2",
            "Aciklama": null,
            "DepoID": 2,
            "KonumX": 0,
            "KonumY": 0,
            "KonumZ": 0,
            "En": 0,
            "Boy": 0,
            "Yukseklik": 0,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 0,
            "Durum": true
        },
        {
            "DepoKodu": "DPM",
            "DepoAdi": "Depom",
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T13:13:41.833",
            "DgsTar": "2023-09-26T13:15:42.65",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StokRafID": 7,
            "StokRafKodu": "R.01.3",
            "Aciklama": null,
            "DepoID": 2,
            "KonumX": 0,
            "KonumY": 0,
            "KonumZ": 0,
            "En": 0,
            "Boy": 0,
            "Yukseklik": 0,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 0,
            "Durum": true
        },
        {
            "DepoKodu": "DPM",
            "DepoAdi": "Depom",
            "OnayDurum": 1,
            "OlsTar": "2023-10-18T10:43:07.623",
            "DgsTar": "2023-10-18T10:43:07.623",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StokRafID": 10,
            "StokRafKodu": "Teknoloji Rafı",
            "Aciklama": null,
            "DepoID": 2,
            "KonumX": 0,
            "KonumY": 0,
            "KonumZ": 0,
            "En": 0,
            "Boy": 0,
            "Yukseklik": 0,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 0,
            "Durum": true
        },
        {
            "DepoKodu": "DPM",
            "DepoAdi": "Depom",
            "OnayDurum": 1,
            "OlsTar": "2023-10-18T10:42:37.377",
            "DgsTar": "2023-10-18T10:42:37.377",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StokRafID": 8,
            "StokRafKodu": "Temizlik Rafı",
            "Aciklama": null,
            "DepoID": 2,
            "KonumX": 0,
            "KonumY": 0,
            "KonumZ": 0,
            "En": 0,
            "Boy": 0,
            "Yukseklik": 0,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 0,
            "Durum": true
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Raf Ekle
Yeni bir raf kartı eklemek için  
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| StokRafKodu | 02A.02.02 | Rafın kodudur. | Evet |
| Aciklama | aciklama | Raf iiçin açıklamayı ifade eder.Rafın adı girilebilir. | Evet |
| Durum | true | Raf kartının aktif veya pasif olduğunu belirlemektedir | Evet |
| DepoID | 1 | Rafın deposunu belirtir. | Evet |
| KonumX | 1 | Rafın x konumundaki durumunu belirtir. | Evet |
| KonumY | 1 | Rafın y konumundaki durumunu belirtir. | Evet |
| KonumZ | 1 | Rafın z konumundaki durumunu belirtir. | Evet |
| En | 1.000000 | Rafın enini belirtir. | Evet |
| Boy | 1.000000 | Rafın boyunu belirtir. | Evet |
| Yükseklik | 1.000000 | Rafın yüksekliğini belirtir. | Evet |
| EtiketKonum | 0 | Etiketin konumunun alt ya da üst olmasını belirtir.  <br>Üst:0  <br>Alt:1 | Evet |
| EtiketKonumBasilsin | true | Etiketin konumunun raf çıktısına basılıp basılmayacağını belirtir. | Evet |
| AgirlikKapasitesi | 1.000000 | Rafın ağırlık kapasitesini belirtir. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/StokRaf/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "StokRafKodu": "02A.02.02",
            "Aciklama": "a",
            "Durum": true,
            "DepoID": 1,
            "KonumX": 1,
            "KonumY": 1,
            "KonumZ": 1,
            "En": 1.000000,
            "Boy": 1.000000,
            "Yukseklik": 1.000000,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 1.000000
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "StokRafID": 14,
        "StokRafKodu": "02A.02.02",
        "Aciklama": "a",
        "DepoID": 1,
        "KonumX": 1,
        "KonumY": 1,
        "KonumZ": 1,
        "En": 1,
        "Boy": 1,
        "Yukseklik": 1,
        "EtiketKonum": 0,
        "EtiketKonumBasilsin": true,
        "AgirlikKapasitesi": 1,
        "Durum": true
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Raf Düzenle
Raf kartı düzenlemek için  
KayitTipi: 2 Tüm API'de kaydı düzenlemek anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de kaydı düzenlemek anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| StokRafID | 14 | Düzenlenmek istenen rafı belirtir. | Evet |
| StokRafKodu | 02A.02.02 | Rafın kodudur. | Evet |
| Aciklama | aciklama | Raf iiçin açıklamayı ifade eder.Rafın adı girilebilir. | Evet |
| Durum | true | Raf kartının aktif veya pasif olduğunu belirlemektedir | Evet |
| DepoID | 1 | Rafın deposunu belirtir. | Evet |
| KonumX | 1 | Rafın x konumundaki durumunu belirtir. | Evet |
| KonumY | 1 | Rafın y konumundaki durumunu belirtir. | Evet |
| KonumZ | 1 | Rafın z konumundaki durumunu belirtir. | Evet |
| En | 1.000000 | Rafın enini belirtir. | Evet |
| Boy | 1.000000 | Rafın boyunu belirtir. | Evet |
| Yükseklik | 1.000000 | Rafın yüksekliğini belirtir. | Evet |
| EtiketKonum | 0 | Etiketin konumunun alt ya da üst olmasını belirtir.  <br>Üst:0  <br>Alt:1 | Evet |
| EtiketKonumBasilsin | true | Etiketin konumunun raf çıktısına basılıp basılmayacağını belirtir. | Evet |
| AgirlikKapasitesi | 1.000000 | Rafın ağırlık kapasitesini belirtir. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/StokRaf/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
 {
            "StokRafID": 14,
            "StokRafKodu": "02A.02.04",
            "Aciklama": "a",
            "Durum": true,
            "DepoID": 1,
            "KonumX": 1,
            "KonumY": 1,
            "KonumZ": 1,
            "En": 1.000000,
            "Boy": 1.000000,
            "Yukseklik": 1.000000,
            "EtiketKonum": 0,
            "EtiketKonumBasilsin": true,
            "AgirlikKapasitesi": 1.000000
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "StokRafID": 14,
        "StokRafKodu": "02A.02.04",
        "Aciklama": "a",
        "DepoID": 1,
        "KonumX": 1,
        "KonumY": 1,
        "KonumZ": 1,
        "En": 1,
        "Boy": 1,
        "Yukseklik": 1,
        "EtiketKonum": 0,
        "EtiketKonumBasilsin": true,
        "AgirlikKapasitesi": 1,
        "Durum": true
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Raf Sil
Raf kartını silmek içindir.
### Method: POST
>```
>{{BaseUrl}}/api/StokRaf/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "StokRafID": 14
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Paket Getir
Bu uç nokta ile paket bilgilerini toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/Paket
>```
### Body (**raw**)

```json

```

### Response: 200
```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 20,
        "ToplamSayfaSayisi": 2,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": true,
        "SayfaSatirSayisiAktifSayfada": 10
    },
    "Model": [
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Paket",
            "TipKodu": "Paket",
            "PaketKapCinsKodu": "BX",
            "PaketKapCinsAdi": "Kutu",
            "OnayDurum": 1,
            "OlsTar": "2023-08-18T16:35:33.04",
            "DgsTar": "2023-08-18T16:35:33.04",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "PaketID": 1,
            "PaketKodu": "000001",
            "PaketAdi": " ",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Basildi": false,
            "Durum": true
        },
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Paket",
            "TipKodu": "Paket",
            "PaketKapCinsKodu": "BX",
            "PaketKapCinsAdi": "Kutu",
            "OnayDurum": 1,
            "OlsTar": "2023-08-18T17:37:22.037",
            "DgsTar": "2023-08-18T17:37:22.037",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "PaketID": 3,
            "PaketKodu": "000002",
            "PaketAdi": " ",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Basildi": false,
            "Durum": true
        },
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Paket",
            "TipKodu": "Paket",
            "PaketKapCinsKodu": "BX",
            "PaketKapCinsAdi": "Kutu",
            "OnayDurum": 1,
            "OlsTar": "2023-08-18T17:37:32.34",
            "DgsTar": "2023-08-18T17:37:32.34",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "PaketID": 4,
            "PaketKodu": "000003",
            "PaketAdi": " ",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Basildi": false,
            "Durum": true
        },
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Paket",
            "TipKodu": "Paket",
            "PaketKapCinsKodu": "BA",
            "PaketKapCinsAdi": "Varil",
            "OnayDurum": 1,
            "OlsTar": "2023-09-05T10:35:30.727",
            "DgsTar": "2023-09-05T10:35:30.727",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "PaketID": 7,
            "PaketKodu": "6",
            "PaketAdi": "2222",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 1,
            "Sira": 0,
            "Basildi": false,
            "Durum": true
        },
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Paket",
            "TipKodu": "Paket",
            "PaketKapCinsKodu": "BX",
            "PaketKapCinsAdi": "Kutu",
            "OnayDurum": 1,
            "OlsTar": "2023-08-24T13:53:11.313",
            "DgsTar": "2023-08-24T13:53:11.313",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "PaketID": 6,
            "PaketKodu": "D-1-3",
            "PaketAdi": "D-1-3",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Basildi": false,
            "Durum": true
        },
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Paket",
            "TipKodu": "Paket",
            "PaketKapCinsKodu": "BX",
            "PaketKapCinsAdi": "Kutu",
            "OnayDurum": 1,
            "OlsTar": "2023-10-18T10:43:50.107",
            "DgsTar": "2023-10-18T10:43:50.107",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "PaketID": 16,
            "PaketKodu": "K1",
            "PaketAdi": " ",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Basildi": false,
            "Durum": true
        },
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Paket",
            "TipKodu": "Paket",
            "PaketKapCinsKodu": "BX",
            "PaketKapCinsAdi": "Kutu",
            "OnayDurum": 1,
            "OlsTar": "2023-10-18T10:43:53.807",
            "DgsTar": "2023-10-18T10:43:53.807",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "PaketID": 17,
            "PaketKodu": "K2",
            "PaketAdi": " ",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Basildi": false,
            "Durum": true
        },
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Paket",
            "TipKodu": "Paket",
            "PaketKapCinsKodu": "BX",
            "PaketKapCinsAdi": "Kutu",
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T13:16:40.97",
            "DgsTar": "2023-09-26T13:16:40.97",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "PaketID": 10,
            "PaketKodu": "P.01.1",
            "PaketAdi": " ",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Basildi": false,
            "Durum": true
        },
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Paket",
            "TipKodu": "Paket",
            "PaketKapCinsKodu": "BX",
            "PaketKapCinsAdi": "Kutu",
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T13:16:52.037",
            "DgsTar": "2023-09-26T13:16:52.037",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "PaketID": 11,
            "PaketKodu": "P.01.2",
            "PaketAdi": " ",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Basildi": false,
            "Durum": true
        },
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "TipAdi": "Paket",
            "TipKodu": "Paket",
            "PaketKapCinsKodu": "BX",
            "PaketKapCinsAdi": "Kutu",
            "OnayDurum": 1,
            "OlsTar": "2023-09-26T13:17:06.29",
            "DgsTar": "2023-09-26T13:17:06.29",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "PaketID": 12,
            "PaketKodu": "P.01.3",
            "PaketAdi": " ",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Basildi": false,
            "Durum": true
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Paket Ekle
Yeni bir paket kartı eklemek için  
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| PaketKodu | 000001 | Paketin kodudur. | Evet |
| PaketAdi | paket | Paketin adını belirtir. Boş bırakılabilir. | Evet |
| Durum | true | Paket kartının aktif veya pasif olduğunu belirlemektedir | Evet |
| SubeID | 1 | Paketin bulunduğu şubeyi belirtir. | Evet |
| SirketID | 1 | Paketin bulunduğu şirketi belirtir. | Evet |
| TipID | 156001 | Paketin tip idsini belirtir.  <br>Paket : 156001 | Evet |
| PaketKapCinsID | 1 | Paketin cins id sini belritir. Kutu,Koli vb. | Evet |
| Sira | 0 | Paketin sırasını belirtir. | Evet |

### Paket Kap Cins Kodları

| PaketKapCinsID | PaketKapCinsKodu | PaketKapCinsAdi |
| --- | --- | --- |
| 1 | BA | Varil |
| 2 | BE | Bohça |
| 3 | BG | Torba |
| 4 | BH | Demet |
| 5 | BI | Çöp kutusu |
| 6 | BJ | Kova |
| 7 | BK | Sepet |
| 8 | BX | Kutu |
| 9 | CB | Bira kasası |
| 10 | CH | Sandık |
| 11 | CI | Teneke kutu |
| 12 | CK | Fıçı |
| 13 | CN | Konteyner |
| 14 | CR | Kasa |
| 15 | DK | Karton kasa |
| 16 | DR | Bidon |
| 17 | EC | Plastik torba |
| 18 | FC | Meyve kasası |
| 19 | JR | Kavanoz |
| 20 | LV | Liftvan |
| 21 | NE | Ambalajsız |
| 22 | SA | Çuval |
| 23 | SU | Bavul |
| 24 | TN | Teneke |
| 25 | VG | Dökme gaz |
| 26 | VL | Dökme sıvı |
| 27 | VO | Dökme katı |
### Method: POST
>```
>{{BaseUrl}}/api/Paket/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "PaketKodu": "000004",
            "PaketAdi": " ",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Durum": true
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "PaketID": 26,
        "PaketKodu": "000004",
        "PaketAdi": " ",
        "SubeID": 1,
        "SirketID": 1,
        "TipID": 156001,
        "PaketKapCinsID": 8,
        "Sira": 0,
        "Basildi": false,
        "Durum": true
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Paket Düzenle
Paket kartı düzenlemek için  
KayitTipi: 2 Tüm API'de kaydı düzenlemek anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de kaydı düzenlemek anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| PaketID | 26 | Paketin idsidir. | Evet |
| PaketKodu | 000001 | Paketin kodudur. | Evet |
| PaketAdi | paket | Paketin adını belirtir. Boş bırakılabilir. | Evet |
| Durum | true | Paket kartının aktif veya pasif olduğunu belirlemektedir | Evet |
| SubeID | 1 | Paketin bulunduğu şubeyi belirtir. | Evet |
| SirketID | 1 | Paketin bulunduğu şirketi belirtir. | Evet |
| TipID | 156001 | Paketin tip idsini belirtir.  <br>Paket : 156001 | Evet |
| PaketKapCinsID | 1 | Paketin cins id sini belritir. Kutu,Koli vb. | Evet |
| Sira | 0 | Paketin sırasını belirtir. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Paket/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "PaketID": 26,
            "PaketKodu": "000005",
            "PaketAdi": " ",
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 156001,
            "PaketKapCinsID": 8,
            "Sira": 0,
            "Durum": true
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "PaketID": 26,
        "PaketKodu": "000005",
        "PaketAdi": " ",
        "SubeID": 1,
        "SirketID": 1,
        "TipID": 156001,
        "PaketKapCinsID": 8,
        "Sira": 0,
        "Basildi": false,
        "Durum": true
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Paket Sil
Paket kartını silmek içindir.
### Method: POST
>```
>{{BaseUrl}}/api/Paket/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "PaketID": 26
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "PaketID": 26,
        "PaketKodu": null,
        "PaketAdi": null,
        "SubeID": 0,
        "SirketID": 0,
        "TipID": 0,
        "PaketKapCinsID": 0,
        "Sira": 0,
        "Basildi": false,
        "Durum": false
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Gelir Gider 


## End-point: Gelir-Gider Kartlarını Getir
Sistemde kayıtlı olan bütün gelir gider kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/GelirGider/GetKayit
>```
### Query Params

|Param|value|
|---|---|
|EsnekAramaKisiti||
|SiralamaKisiti||
|Sayfa|1|
|SayfaSatirSayisi|2|
|StokID|null|
|Durum|true|
|TipID|{{tipIDGelirGider}}|
|Tip2ID|null|
|SubeID|0|
|SirketID|0|
|StokMuhasebeID|null|
|StokVergiID|null|
|OlsID|null|
|StokKodu||



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Gelir Gider Ekle
Yeni bir gelir gider oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/GelirGider/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "StokKodu": "{{gelirGiderKodu}}",
    "StokAdi": "{{gelirGiderAdi}}",
    "StokKisaKodu": "{{gelirGiderKisaKodu}}",
    "StokKisaAdi": "{{gelirGiderKisaAdi}}",
    "StokMuhasebeID": null,
    "StokVergiID": 1,
    "Brm1ID": "{{brm1ID}}",
    "Brm2ID": null,
    "Brm3ID": null,
    "UretimBrmID": null,
    "RaporBrmID": null,
    "CevirimBrm2": null,
    "CevirimBrm3": null,
    "Kalinlik": 0.000000,
    "En": 0.000000,
    "Boy": 0.000000,
    "Yogunluk": 0.000000,
    "Agirlik": 0.000000,
    "GTIP": null,
    "ZorunluDemirbas": "{{demirbasZorunluMu}}",
    "ZorunluStok": "{{stokZorunluMu}}",
    "ZorunluDekont": "{{dekontZorunluMu}}",
    "ZorunluCari": "{{cariZorunluMu}}",
    "Seviye": 0,
    "FiyatEtiketi": null,
    "BayiGozuksunMu": "{{bayiGozuksunMu}}",
    "SubeID": "{{subeID}}",
    "SirketID": "{{sirketID}}",
    "Durum": true,
    "TipID": "{{tipIDGelirGider}}",
    "EntegrasyonTanimID": null,
    "Kod1ID": null,
    "Kod2ID": null,
    "Kod3ID": null,
    "Kod4ID": null,
    "Kod5ID": null,
    "Kod6ID": null,
    "Etiket1ID": null,
    "Etiket2ID": null,
    "Etiket3ID": null,
    "Etiket4ID": null,
    "Etiket5ID": null,
    "SablonID": null
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Gelir Gider Düzenle
Var olan gelir gideri düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/GelirGider/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
 {
        "StokVergiAdi": "Stok (Kdv18 - Tevkifat 0)",
        "StokVergiAlisKDVOrani": 18,
        "StokVergiSatisKDVOrani": 18,
        "StokVergiKodu": "KDV18",
        "Brm1Kodu": "AD",
        "Brm2Kodu": null,
        "Brm3Kodu": null,
        "RaporBrmKodu": null,
        "UretimBrmKodu": null,
        "Miktar": null,
        "KartPuan": null,
        "SubeKodu": "FBRK",
        "SubeAdi": "Fabrika",
        "SirketKodu": "SRKT1",
        "SirketAdi": "Şirket 1",
        "EntegrasyonTanimKodu": null,
        "EntegrasyonTanimAdi": null,
        "TipAdi": "Stok",
        "TipKodu": null,
        "OnayDurum": 1,
        "OlsTar": "2021-09-20T16:42:31.653",
        "DgsTar": "2021-09-20T16:42:31.653",
        "OlsID": 2,
        "OlsKodu": "yonetici",
        "OlsAdi": "A Kullanicisii",
        "DgsID": 2,
        "DgsKodu": "yonetici",
        "DgsAdi": "A Kullanicisii",
        "Kod1Kodu": null,
        "Kod2Kodu": null,
        "Kod3Kodu": null,
        "Kod4Kodu": null,
        "Kod5Kodu": null,
        "Kod6Kodu": null,
        "Kod1Adi": null,
        "Kod2Adi": null,
        "Kod3Adi": null,
        "Kod4Adi": null,
        "Kod5Adi": null,
        "Kod6Adi": null,
        "Etiket1Adi": null,
        "Etiket2Adi": null,
        "Etiket3Adi": null,
        "Etiket4Adi": null,
        "Etiket5Adi": null,
        "SablonKodu": null,
        "SablonAdi": null,
        "ResimAdresi": null,
        "EsnekAramaKisiti": "Stok Postman Yeni Stok Postman            ",
        "StokID": "{{gelirGiderID}}",
        "StokKodu": "{{gelirGiderKoduDuzelt}}",
        "StokAdi": "{{gelirGiderAdiDuzelt}}",
        "StokKisaKodu": "{{gelirGiderKisaKoduDuzelt}}",
        "StokKisaAdi": "{{gelirGiderKisaAdiDuzelt}}",
        "StokMuhasebeID": null,
        "StokVergiID": 1,
        "Brm1ID": "{{brm1ID}}",
        "Brm2ID": null,
        "Brm3ID": null,
        "UretimBrmID": null,
        "RaporBrmID": null,
        "CevirimBrm2": null,
        "CevirimBrm3": null,
        "Kalinlik": 0.000000,
        "En": 0.000000,
        "Boy": 0.000000,
        "Yogunluk": 0.000000,
        "Agirlik": 0.000000,
        "GTIP": null,
        "ZorunluDemirbas": "{{demirbasZorunluMuDuzelt}}",
        "ZorunluStok": "{{stokZorunluMuDuzelt}}",
        "ZorunluDekont": "{{dekontZorunluMuDuzelt}}",
        "ZorunluCari": "{{cariZorunluMuDuzelt}}",
        "Seviye": 0,
        "FiyatEtiketi": null,
        "BayiGozuksunMu": "{{bayiGozuksunMuDuzelt}}",
        "BayiMaksMiktar": 0,
        "YedekD1": null,
        "YedekD2": null,
        "SubeID": "{{subeID}}",
        "SirketID": "{{sirketID}}",
        "Durum": true,
        "TipID": 105001,
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Kod2ID": null,
        "Kod3ID": null,
        "Kod4ID": null,
        "Kod5ID": null,
        "Kod6ID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "SablonID": null
 }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Gelir Gider Sil
Mevcut gelir gideri silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/GelirGider/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
"StokID":251
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Gelir Gider Hareketleri Liste
Bu uç nokta ile belirtilen kısıtlara göre stok hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/GelirGiderHareketleri
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Demirbas 


## End-point: Demirbas Kartlarını Getir
StartFragment

Sistemde kayıtlı olan bütün demirbaş kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/Demirbas/GetKayit
>```
### Query Params

|Param|value|
|---|---|
|EsnekAramaKisiti||
|SiralamaKisiti||
|Sayfa|1|
|SayfaSatirSayisi|2|
|StokID|null|
|Durum|true|
|TipID|{{tipIDGelirGider}}|
|Tip2ID|null|
|SubeID|0|
|SirketID|0|
|StokMuhasebeID|null|
|StokVergiID|null|
|OlsID|null|
|StokKodu||



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Demirbas Ekle
Yeni bir demirbaş oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Demirbas/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "StokKodu": "{{demirbasKodu}}",
    "StokAdi": "{{demirbasAdi}}",
    "StokKisaKodu": "{{demirbasKisaKodu}}",
    "StokKisaAdi": "{{demirbasKisaAdi}}",
    "StokMuhasebeID": null,
    "StokVergiID": 1,
    "Brm1ID": "{{brm1ID}}",
    "Brm2ID": null,
    "Brm3ID": null,
    "UretimBrmID": null,
    "RaporBrmID": null,
    "CevirimBrm2": null,
    "CevirimBrm3": null,
    "Kalinlik": 0.000000,
    "En": 0.000000,
    "Boy": 0.000000,
    "Yogunluk": 0.000000,
    "Agirlik": 0.000000,
    "GTIP": null,
    "ZorunluDemirbas": false,
    "ZorunluStok": false,
    "ZorunluDekont": false,
    "ZorunluCari": false,
    "Seviye": 0,
    "FiyatEtiketi": null,
    "BayiGozuksunMu": "{{bayiGozuksunMu}}",
    "SubeID": "{{subeID}}",
    "SirketID": "{{sirketID}}",
    "Durum": true,
    "TipID": "{{tipIDDemirbas}}",
    "EntegrasyonTanimID": null,
    "Kod1ID": null,
    "Kod2ID": null,
    "Kod3ID": null,
    "Kod4ID": null,
    "Kod5ID": null,
    "Kod6ID": null,
    "Etiket1ID": null,
    "Etiket2ID": null,
    "Etiket3ID": null,
    "Etiket4ID": null,
    "Etiket5ID": null,
    "SablonID": null
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Demirbas Düzenle
Var olan demirbaşı düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Demirbas/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
 {
        "StokVergiAdi": "Stok (Kdv18 - Tevkifat 0)",
        "StokVergiAlisKDVOrani": 18,
        "StokVergiSatisKDVOrani": 18,
        "StokVergiKodu": "KDV18",
        "Brm1Kodu": "AD",
        "Brm2Kodu": null,
        "Brm3Kodu": null,
        "RaporBrmKodu": null,
        "UretimBrmKodu": null,
        "Miktar": null,
        "KartPuan": null,
        "SubeKodu": "FBRK",
        "SubeAdi": "Fabrika",
        "SirketKodu": "SRKT1",
        "SirketAdi": "Şirket 1",
        "EntegrasyonTanimKodu": null,
        "EntegrasyonTanimAdi": null,
        "TipAdi": "Stok",
        "TipKodu": null,
        "OnayDurum": 1,
        "OlsTar": "2021-09-20T16:42:31.653",
        "DgsTar": "2021-09-20T16:42:31.653",
        "OlsID": 2,
        "OlsKodu": "yonetici",
        "OlsAdi": "A Kullanicisii",
        "DgsID": 2,
        "DgsKodu": "yonetici",
        "DgsAdi": "A Kullanicisii",
        "Kod1Kodu": null,
        "Kod2Kodu": null,
        "Kod3Kodu": null,
        "Kod4Kodu": null,
        "Kod5Kodu": null,
        "Kod6Kodu": null,
        "Kod1Adi": null,
        "Kod2Adi": null,
        "Kod3Adi": null,
        "Kod4Adi": null,
        "Kod5Adi": null,
        "Kod6Adi": null,
        "Etiket1Adi": null,
        "Etiket2Adi": null,
        "Etiket3Adi": null,
        "Etiket4Adi": null,
        "Etiket5Adi": null,
        "SablonKodu": null,
        "SablonAdi": null,
        "ResimAdresi": null,
        "EsnekAramaKisiti": "Stok Postman Yeni Stok Postman            ",
        "StokID": "{{demirbasID}}",
        "StokKodu": "{{demirbasKoduDuzelt}}",
        "StokAdi": "{{demirbasAdiDuzelt}}",
        "StokKisaKodu": "{{demirbasKisaKoduDuzelt}}",
        "StokKisaAdi": "{{demirbasKisaAdiDuzelt}}",
        "StokMuhasebeID": null,
        "StokVergiID": 1,
        "Brm1ID": "{{brm1ID}}",
        "Brm2ID": null,
        "Brm3ID": null,
        "UretimBrmID": null,
        "RaporBrmID": null,
        "CevirimBrm2": null,
        "CevirimBrm3": null,
        "Kalinlik": 0.000000,
        "En": 0.000000,
        "Boy": 0.000000,
        "Yogunluk": 0.000000,
        "Agirlik": 0.000000,
        "GTIP": null,
        "ZorunluDemirbas": false,
        "ZorunluStok": false,
        "ZorunluDekont": false,
        "ZorunluCari": false,
        "Seviye": 0,
        "FiyatEtiketi": null,
        "BayiGozuksunMu": "{{bayiGozuksunMuDuzelt}}",
        "BayiMaksMiktar": 0,
        "YedekD1": null,
        "YedekD2": null,
        "SubeID": "{{subeID}}",
        "SirketID": "{{sirketID}}",
        "Durum": true,
        "TipID": 105001,
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Kod2ID": null,
        "Kod3ID": null,
        "Kod4ID": null,
        "Kod5ID": null,
        "Kod6ID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "SablonID": null
 }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Demirbas Sil
Mevcut demirbaşı silmektedir.
### Method: POST
>```
>https://localhost:44346/api/Demirbas/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
"StokID":"{{demirbasID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Demirbas Hareketleri Liste
Bu uç nokta ile belirtilen kısıtlara göre stok hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/DemirbasHareketleri
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Barkod 


## End-point: Stoktaki Ürünün Bakodunu Getir
Aaro bir ürün için sonsuz sayıda barkodu kabul etmektedir. Dolayısıyla barkod getir değil barkodları getir şekline çalışmaktadır.

###### Birden fazla sonuç gelebilmektedir
### Method: GET
>```
>{{baseUrl}}/api/StokBarkod
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|EsnekAramaKisiti||
|SayfaSatirSayisi||
|Sayfa||
|StokID||
|BarkodID||
|BarkodNo||



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stoktaki Ürüne Barkod Ekle
Yeni bir stok kartı eklemek için
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.
### Method: POST
>```
>{{baseUrl}}/api/StokBarkod/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "StokID": "{{stokID}}",
    "BarkodNo":"{{barkodNoEkle}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stoktaki Ürünün Barkodunu Düzenle
Değiştirmek istediğiniz barkod için aşağıdaki yapıyı kullanınız.

###### Sadece kayıt tipi 2 olarak değişmektedir. BarkodID'si ise 2590 olarak girilerek istenilen barkoda ulaşılmıştır.
### Method: POST
>```
>{{baseUrl}}/api/StokBarkod/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "BarkodID": "{{barkodID}}",
    "StokID": "{{stokID}}",
    "BarkodNo":"{{barkodNoDuzelt}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stoktaki Ürünün Barkodunu Sil
Silmek istediğiniz barkod için aşağıdaki yapıyı kullanınız.

###### Sadece kayıt tipi -1 olarak değişmektedir.
### Method: POST
>```
>{{baseUrl}}/api/StokBarkod/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "BarkodID":"{{barkodID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Depo 


## End-point: Depoları Getir
Sistemde kayıtlı olan bütün depo kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/Depo
>```
### Query Params

|Param|value|
|---|---|
|EsnekAramaKisiti||
|SayfaSatirSayisi||
|Sayfa||
|DepoID||
|CariID||



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Depo Oluştur
Yeni bir depo oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Depo/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "DepoKodu":"{{depoKodu}}",
    "DepoAdi":"{{depoAdi}}",
    "TipID":"{{tipIODepoTipi}}",
    "Durum":"{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Depoyu Düzenle
Mevcut bir deponun düzeltilmesi için kullanılmaktadır.

######  Depo eklemekten farklı olarak ID eklenmesi gerekmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Depo/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "DepoID":"{{depoID}}",
    "DepoKodu":"{{depoKoduDuzelt}}",
    "DepoAdi":"{{depoAdiDuzelt}}",
    "TipID":"{{tipIODepoTipi}}",
    "Durum":"{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Depoyu Sil
Mevcut bir deponun silinmesi için kullanılmaktadır.

######  Depoyu silmeden önce depoya ait bütün hareketlerin ve stoklar silindiğinden/taşındığından emin olunuz. Aksi takdirde silme işlemi gerçekleşmeyecektir.
### Method: POST
>```
>{{baseUrl}}/api/Depo/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "DepoID": "{{depoID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Döviz 


## End-point: Dövizleri Getir
Oluşturulmuş bütün dövizleri getirmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım | Örnek |
| --- | --- | --- | --- |
| EsnekAramaKisiti | String | Dilediğiniz stringe göre listeleme yapabilirsiniz. Doviz kodunda, Doviz adında girilen string'e göre arama yapar. | TL |
| DovizID | Integer | Belirtilen ID'li döviz kartını getirir. | 1 |
| OlsID | Integer | Oluşturan kişi ID'sine göre depo kartlarını getirmektedir. | 1234 |
| DgsID | Integer | Değiştiren kişi ID'sine göre depo kartlarını getirmektedir. | 1234 |
| OlsTarBas | Datetime | Belirtilen tarihten itibaren oluşturulmuş depo kartlarını getirmektedir. | 01.01.2021 |
| OlsTarBit | Datetime | Belirtilen tarihe kadar oluşturulmuş depo kartlarını getirmektedir. | 01.01.2021 |
| DgsTarBas | Datetime | Belirtilen tarihten itibaren değiştirilmiş depo kartlarını getirmektedir. | 01.01.2021 |
| DgsTarBit | Datetime | Belirtilen tarihe kadar değiştirilmiş depo kartlarını getirmektedir. | 01.01.2021 |
| SayfaSatirSayisi | Integer | Limitli sayıda depo getirmek için kullanılmaktadır. | 10 |
### Method: GET
>```
>{{BaseUrl}}/api/Doviz
>```
### Response: 200
```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 9,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 9
    },
    "Model": [
        {
            "OlsTar": "2022-10-20T08:14:07.217",
            "DgsTar": "2022-10-20T08:14:07.217",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "Tümü",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "Tümü",
            "EsnekAramaKisiti": "TRY Türk Lirası TL ",
            "DovizID": 1,
            "DovizKodu": "TRY",
            "DovizAdi": "Türk Lirası TL",
            "DovizSembol": "₺",
            "YaziylaKurus": "Kuruş",
            "Yaziyla": "TL"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.223",
            "DgsTar": "2022-10-20T08:14:07.223",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "Tümü",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "Tümü",
            "EsnekAramaKisiti": "USD Amerikan Doları ",
            "DovizID": 2,
            "DovizKodu": "USD",
            "DovizAdi": "Amerikan Doları",
            "DovizSembol": "$",
            "YaziylaKurus": "Sent",
            "Yaziyla": "Dolar"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.227",
            "DgsTar": "2022-10-20T08:14:07.227",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "Tümü",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "Tümü",
            "EsnekAramaKisiti": "EUR Euro ",
            "DovizID": 3,
            "DovizKodu": "EUR",
            "DovizAdi": "Euro",
            "DovizSembol": "€",
            "YaziylaKurus": "Sent",
            "Yaziyla": "Euro"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.23",
            "DgsTar": "2022-10-20T08:14:07.23",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "Tümü",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "Tümü",
            "EsnekAramaKisiti": "GBP İngiliz Sterlini ",
            "DovizID": 4,
            "DovizKodu": "GBP",
            "DovizAdi": "İngiliz Sterlini",
            "DovizSembol": "£",
            "YaziylaKurus": "Pence",
            "Yaziyla": "Pound"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.23",
            "DgsTar": "2022-10-20T08:14:07.23",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "Tümü",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "Tümü",
            "EsnekAramaKisiti": "RUB Rus Rublesi ",
            "DovizID": 5,
            "DovizKodu": "RUB",
            "DovizAdi": "Rus Rublesi",
            "DovizSembol": "R",
            "YaziylaKurus": "Kapik",
            "Yaziyla": "Ruble"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.233",
            "DgsTar": "2022-10-20T08:14:07.233",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "Tümü",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "Tümü",
            "EsnekAramaKisiti": "CNY Çin Yuanı ",
            "DovizID": 6,
            "DovizKodu": "CNY",
            "DovizAdi": "Çin Yuanı",
            "DovizSembol": "¥",
            "YaziylaKurus": "Jiao",
            "Yaziyla": "Yuan"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.233",
            "DgsTar": "2022-10-20T08:14:07.233",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "Tümü",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "Tümü",
            "EsnekAramaKisiti": "SAR Saudi Riyali ",
            "DovizID": 7,
            "DovizKodu": "SAR",
            "DovizAdi": "Saudi Riyali",
            "DovizSembol": "S",
            "YaziylaKurus": "Halal",
            "Yaziyla": "Riyal"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.233",
            "DgsTar": "2022-10-20T08:14:07.233",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "Tümü",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "Tümü",
            "EsnekAramaKisiti": "XAU Altın ",
            "DovizID": 8,
            "DovizKodu": "XAU",
            "DovizAdi": "Altın",
            "DovizSembol": "A",
            "YaziylaKurus": "Gram Altın",
            "Yaziyla": "Nokta"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.237",
            "DgsTar": "2022-10-20T08:14:07.237",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "Tümü",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "Tümü",
            "EsnekAramaKisiti": "XAG Gümüş ",
            "DovizID": 9,
            "DovizKodu": "XAG",
            "DovizAdi": "Gümüş",
            "DovizSembol": "G",
            "YaziylaKurus": "Gram Gümüş",
            "Yaziyla": "Nokta"
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Döviz Oluştur
Yeni bir döviz eklemek için kullanılmaktadır.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 (KayitTipi=1 bütün API yapısında ürün kaydet demektir) |

### Sorgu Body Parametreleri

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| DovizID | \-1 | Eklenilen kartın döviz ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır. | Evet |
| DovizKodu | "DPM" | Döviz kodudur. | Evet |
| DovizAdi | "Depom" | Döviz adıdır. | Evet |
| DovizSembol | "₺" | Döviz sembolüdür. | Evet |
| YaziylaKurus | "Kuruş" | Döviz cinsinin kuruş için belirttiği addır. Örn: Kuruş, Cent | Evet |
| Yaziyla | "TL" | Döviz cinsinin okunuşunun yazı halidir. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Doviz/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
        "DovizKodu": "DPM",
        "DovizAdi": "Depom",
        "DovizSembol": "₺",
        "YaziylaKurus": "Kurus",
        "Yaziyla": "TL"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "DovizID": 13,
        "DovizKodu": "DPM",
        "DovizAdi": "Depom",
        "DovizSembol": "₺",
        "YaziylaKurus": "Kurus",
        "Yaziyla": "TL"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Döviz Düzenle
Mevcut bir deponun düzeltilmesi için kullanılmaktadır.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 2 (KayitTipi=2 bütün API yapısında PUT işlemine karşılık gelmektedir.) |

### Sorgu Body Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| DovizID | Integer | Düzeltmek istediğiniz dövizin ID'si |
| DovizKodu | String | Dövize vereceğiniz koddur. |
| DovizAdi | String | Dövize vereceğiniz ad. |
| DovizSembol | String | Dövize vereceğiniz sembol. |
| YaziylaKurus | String | Dövize vereceğiniz kuruş okunuşudur. |
| Yaziyla | String | Dövize vereceğiniz okunuştur. |

> **Döviz eklemekten farklı olarak ID eklenmesi gerekmektedir.**
### Method: POST
>```
>{{BaseUrl}}/api/Doviz/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
        "DovizID": 13,
        "DovizKodu": "DPM",
        "DovizAdi": "DepomDepom",
        "DovizSembol": "₺",
        "YaziylaKurus": "Kurus",
        "Yaziyla": "TL"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "DovizID": 13,
        "DovizKodu": "DPM",
        "DovizAdi": "DepomDepom",
        "DovizSembol": "₺",
        "YaziylaKurus": "Kurus",
        "Yaziyla": "TL"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Döviz Sil
Mevcut döviz bilgilerini silmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 (KayitTipi=-1 bütün API yapısında DELETE işlemine karşılık gelmektedir.) |

### Sorgu Body Parametreleri

Yalnızca ID ile de silme işlemini gerçekleştirebilirsiniz.

| Parametre | Değer | Tanım |
| --- | --- | --- |
| DovizID | Integer | Silmek istediğiniz dövizin ID'si |

> **Dövizi silmeden önce dövizin kullanıldığı bütün hareketlerin silindiğinden/taşındığından emin olunuz. Aksi takdirde silme işlemi gerçekleşmeyecektir.**
### Method: POST
>```
>{{BaseUrl}}/api/Doviz/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "DovizID":13
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "DovizID": 13,
        "DovizKodu": null,
        "DovizAdi": null,
        "DovizSembol": null,
        "YaziylaKurus": null,
        "Yaziyla": null
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Döviz Kuru 


## End-point: Döviz Kurlarını Getir
Oluşturulmuş bütün döviz kur kayıtlarını getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/DovizKayitlari
>```
### Response: 200
```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 269,
        "ToplamSayfaSayisi": 27,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": true,
        "SayfaSatirSayisiAktifSayfada": 10
    },
    "Model": [
        {
            "DovizKodu": "USD",
            "DovizAdi": "Amerikan Doları",
            "OnayDurum": 0,
            "OlsTar": "2022-10-20T08:21:47.303",
            "DgsTar": "2022-10-20T08:21:47.303",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StrID": 1,
            "DovizID": 2,
            "Tarih": "2022-10-20T00:00:00",
            "AlisMerkez": 18.5661,
            "SatisMerkez": 18.5996,
            "AlisEfektif": 18.5531,
            "SatisEfektif": 18.6275,
            "AlisSerbest": 18.5661,
            "SatisSerbest": 18.5996
        },
        {
            "DovizKodu": "EUR",
            "DovizAdi": "Euro",
            "OnayDurum": 0,
            "OlsTar": "2022-10-20T08:21:47.51",
            "DgsTar": "2022-10-20T08:21:47.51",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StrID": 2,
            "DovizID": 3,
            "Tarih": "2022-10-20T00:00:00",
            "AlisMerkez": 18.2157,
            "SatisMerkez": 18.2485,
            "AlisEfektif": 18.2029,
            "SatisEfektif": 18.2759,
            "AlisSerbest": 18.2157,
            "SatisSerbest": 18.2485
        },
        {
            "DovizKodu": "GBP",
            "DovizAdi": "İngiliz Sterlini",
            "OnayDurum": 0,
            "OlsTar": "2022-10-20T08:21:47.57",
            "DgsTar": "2022-10-20T08:21:47.57",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StrID": 3,
            "DovizID": 4,
            "Tarih": "2022-10-20T00:00:00",
            "AlisMerkez": 20.8847,
            "SatisMerkez": 20.9936,
            "AlisEfektif": 20.8701,
            "SatisEfektif": 21.0251,
            "AlisSerbest": 20.8847,
            "SatisSerbest": 20.9936
        },
        {
            "DovizKodu": "SAR",
            "DovizAdi": "Saudi Riyali",
            "OnayDurum": 0,
            "OlsTar": "2022-10-20T08:21:47.643",
            "DgsTar": "2022-10-20T08:21:47.643",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StrID": 4,
            "DovizID": 7,
            "Tarih": "2022-10-20T00:00:00",
            "AlisMerkez": 4.9411,
            "SatisMerkez": 4.95,
            "AlisEfektif": 4.904,
            "SatisEfektif": 4.9871,
            "AlisSerbest": 4.9411,
            "SatisSerbest": 4.95
        },
        {
            "DovizKodu": "RUB",
            "DovizAdi": "Rus Rublesi",
            "OnayDurum": 0,
            "OlsTar": "2022-10-20T08:21:47.703",
            "DgsTar": "2022-10-20T08:21:47.703",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StrID": 5,
            "DovizID": 5,
            "Tarih": "2022-10-20T00:00:00",
            "AlisMerkez": 0.29926,
            "SatisMerkez": 0.30318,
            "AlisEfektif": 0,
            "SatisEfektif": 0,
            "AlisSerbest": 0.29926,
            "SatisSerbest": 0.30318
        },
        {
            "DovizKodu": "CNY",
            "DovizAdi": "Çin Yuanı",
            "OnayDurum": 0,
            "OlsTar": "2022-10-20T08:21:47.767",
            "DgsTar": "2022-10-20T08:21:47.767",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StrID": 6,
            "DovizID": 6,
            "Tarih": "2022-10-20T00:00:00",
            "AlisMerkez": 2.5558,
            "SatisMerkez": 2.5892,
            "AlisEfektif": 0,
            "SatisEfektif": 0,
            "AlisSerbest": 2.5558,
            "SatisSerbest": 2.5892
        },
        {
            "DovizKodu": "XAU",
            "DovizAdi": "Altın",
            "OnayDurum": 0,
            "OlsTar": "2022-10-20T08:21:48.003",
            "DgsTar": "2022-10-20T08:21:48.003",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StrID": 7,
            "DovizID": 8,
            "Tarih": "2022-10-20T00:00:00",
            "AlisMerkez": 994.97,
            "SatisMerkez": 1006.07,
            "AlisEfektif": 994.97,
            "SatisEfektif": 1006.07,
            "AlisSerbest": 994.97,
            "SatisSerbest": 1006.07
        },
        {
            "DovizKodu": "XAG",
            "DovizAdi": "Gümüş",
            "OnayDurum": 0,
            "OlsTar": "2022-10-20T08:21:48.213",
            "DgsTar": "2022-10-20T08:21:48.213",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StrID": 8,
            "DovizID": 9,
            "Tarih": "2022-10-20T00:00:00",
            "AlisMerkez": 11.08,
            "SatisMerkez": 12.06,
            "AlisEfektif": 11.08,
            "SatisEfektif": 12.06,
            "AlisSerbest": 11.08,
            "SatisSerbest": 12.06
        },
        {
            "DovizKodu": "USD",
            "DovizAdi": "Amerikan Doları",
            "OnayDurum": 0,
            "OlsTar": "2023-03-06T12:24:37.947",
            "DgsTar": "2023-03-06T12:24:37.947",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StrID": 9,
            "DovizID": 2,
            "Tarih": "2023-03-06T00:00:00",
            "AlisMerkez": 18.8587,
            "SatisMerkez": 18.8927,
            "AlisEfektif": 18.8455,
            "SatisEfektif": 18.921,
            "AlisSerbest": 18.8587,
            "SatisSerbest": 18.8927
        },
        {
            "DovizKodu": "EUR",
            "DovizAdi": "Euro",
            "OnayDurum": 0,
            "OlsTar": "2023-03-06T12:24:38.207",
            "DgsTar": "2023-03-06T12:24:38.207",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "A Kullanicisii",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "A Kullanicisii",
            "StrID": 10,
            "DovizID": 3,
            "Tarih": "2023-03-06T00:00:00",
            "AlisMerkez": 20.0195,
            "SatisMerkez": 20.0555,
            "AlisEfektif": 20.0054,
            "SatisEfektif": 20.0856,
            "AlisSerbest": 20.0195,
            "SatisSerbest": 20.0555
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Döviz Kurunu Oluştur
Yeni bir döviz kuru eklemek için kullanılmaktadır.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 (KayitTipi=1 bütün API yapısında ürün kaydet demektir) |

### Sorgu Body Parametreleri

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| DovizID | 2 | Eklenilen döviz kurunun ID'sidir. | Evet |
| Tarih | 2022-05-18 | Döviz kurunun tarihidir. | Hayır |
| AlisMerkez | 18.566100 |  | Hayır |
| SatisMerkez | 18.599600 |  | Evet |
| AlisEfektif | 18.553100 |  | Hayır |
| SatisEfektif | 18.627500 |  | Hayır |
| AlisSerbest | 18.566100 |  | Hayır |
| SatisSerbest | 18.599600 |  | Hayır |
### Method: POST
>```
>{{BaseUrl}}/api/DovizKayitlari/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
        {
            "DovizID": 2,
            "Tarih": "2022-05-18",
            "AlisMerkez": 18.566100,
            "SatisMerkez": 18.599600,
            "AlisEfektif": 18.553100,
            "SatisEfektif": 18.627500,
            "AlisSerbest": 18.566100,
            "SatisSerbest": 18.599600
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "StrID": 281,
        "DovizID": 2,
        "Tarih": "2022-05-18T00:00:00",
        "AlisMerkez": 18.5661,
        "SatisMerkez": 18.5996,
        "AlisEfektif": 18.5531,
        "SatisEfektif": 18.6275,
        "AlisSerbest": 18.5661,
        "SatisSerbest": 18.5996
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Döviz Kurunu Düzenle
Mevcut bir döviz kurunun düzeltilmesi için kullanılmaktadır.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 2 (KayitTipi=2 bütün API yapısında PUT işlemine karşılık gelmektedir.) |

### Sorgu Body Parametreleri

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| DovizID | 2 | Eklenilen döviz kurunun ID'sidir. | Evet |
| Tarih | 2022-05-18 | Döviz kurunun tarihidir. | Hayır |
| AlisMerkez | 18.566100 |  | Hayır |
| SatisMerkez | 18.599600 |  | Evet |
| AlisEfektif | 18.553100 |  | Hayır |
| SatisEfektif | 18.627500 |  | Hayır |
| AlisSerbest | 18.566100 |  | Hayır |
| SatisSerbest | 18.599600 |  | Hayır |

> **Döviz kuru eklemekten farklı olarak ID eklenmesi gerekmektedir.**
### Method: POST
>```
>{{BaseUrl}}/api/DovizKayitlari/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
        {
            "StrID": 281,
            "DovizID": 1,
            "Tarih": "2022-05-18",
            "AlisMerkez": 18.566100,
            "SatisMerkez": 18.599600,
            "AlisEfektif": 18.553100,
            "SatisEfektif": 18.627500,
            "AlisSerbest": 18.566100,
            "SatisSerbest": 18.599600
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "StrID": 281,
        "DovizID": 1,
        "Tarih": "2022-05-18T00:00:00",
        "AlisMerkez": 18.5661,
        "SatisMerkez": 18.5996,
        "AlisEfektif": 18.5531,
        "SatisEfektif": 18.6275,
        "AlisSerbest": 18.5661,
        "SatisSerbest": 18.5996
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Döviz Kurunu Sil
Mevcut döviz kuru bilgilerini silmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 (KayitTipi=-1 bütün API yapısında DELETE işlemine karşılık gelmektedir.) |

### Sorgu Body Parametreleri

Yalnızca ID ile de silme işlemini gerçekleştirebilirsiniz.

| Parametre | Değer | Tanım |
| --- | --- | --- |
| StrID | Integer | Silmek istediğiniz döviz kurunun ID'si |
### Method: POST
>```
>{{BaseUrl}}/api/DovizKayitlari/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "StrID": 281
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "StrID": 281,
        "DovizID": 0,
        "Tarih": "0001-01-01T00:00:00",
        "AlisMerkez": 0,
        "SatisMerkez": 0,
        "AlisEfektif": 0,
        "SatisEfektif": 0,
        "AlisSerbest": 0,
        "SatisSerbest": 0
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Vergi 


## End-point: Vergi Oranlarını Getir
Bütün vergi oranlarını ya da istenilen kısıttaki vergi kalemleri gelmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/StokVergi
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Vergi Oranı Oluştur
Yeni bir vergi oranı oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/StokVergi/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
"StokVergiKodu":"{{stokVergiKodu}}",
"StokVergiAdi":"{{stokVergiAdi}}",
"AlisKDVOrani":"{{alisKDVOrani}}",
"SatisKDVOrani":"{{satisKDVOrani}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Vergi Oranını Düzenle
Vergi oranı düzenlenmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/StokVergi/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
"StokVergiID":"{{stokVergiID}}",
"StokVergiKodu":"{{stokVergiKoduDuzelt}}",
"StokVergiAdi":"{{stokVergiAdiDuzelt}}",
"AlisKDVOrani":"{{alisKDVOraniDuzelt}}",
"SatisKDVOrani":"{{satisKDVOraniDuzelt}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Vergi Oranını Sil
Vergi oranını silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/StokVergi/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "StokVergiID":"{{stokVergiID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Vergi Daireleri 


## End-point: Vergi Dairelerini Getir
### Method: GET
>```
>{{BaseUrl}}/api/VergiDairesi
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Vergi Dairesi Oluştur
Yeni bir vergi dairesi oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/VergiDairesi/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "VDKodu": "{{vergiDairesiKodu}}",
    "VDAdi": "{{vergiDairesiAdi}}",
    "VM": "{{vergiDairesiVM}}",
    "IlID": "{{vergiDairesiIlID}}",
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Vergi Dairesi Düzenle
Vergi dairesi düzenlenmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/VergiDairesi/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "VDID": "{{vergiDairesiID}}",
    "VDKodu": "{{vergiDairesiKoduDuzelt}}",
    "VDAdi": "{{vergiDairesiAdiDuzelt}}",
    "VM": "{{vergiDairesiVMDuzelt}}",
    "IlID": "{{vergiDairesiIlID}}",
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Vergi Dairesini Sil
Vergi dairesi silinmektedir..

###### Bu işlemin geri dönüşü yoktur. Silmeden önce bu vergi dairesinin hareketlerini silmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/VergiDairesi/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "VDID":"{{vergiDairesiID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Fiyat Listeleri 


## End-point: Fiyat Listelerini Getir
### Method: GET
>```
>{{BaseUrl}}/api/FiyatListesi
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Fiyat Listesi Oluştur
Yeni bir fiyat listesi oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/FiyatListesi/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "Kodu": "{{fiyatListesiKodu}}",
    "Adi": "{{fiyatListesiAdi}}",
    "TipID": "{{fiyatListesiTipID}}",
    "TarihBas": "{{birAyOnce}}",
    "TarihBit": "{{bugun}}",
    "Durum": "{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Fiyat Listesi Düzenle
Var olan Fiyat Listesi'ni düzeltmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/FiyatListesi/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "FiyatListesiID": "{{fiyatListesiID}}",
    "Kodu": "{{fiyatListesiKoduDuzelt}}",
    "Adi": "{{fiyatListesiAdiDuzelt}}",
    "TarihBas": "{{birAyOnce}}",
    "TarihBit": "{{bugun}}",
    "TipID": "{{fiyatListesiTipIDDuzelt}}",
    "Durum": "{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Fiyat Listesini Sil
Mevcut fiyat listesini silmektedir


######  Bu işlemin geri dönüşü yoktur. Silmeden önce bu fiyat listesine bağlı tüm stokların ve hareketlerin liste ile ilişkisini kesmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/FiyatListesi/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "FiyatListesiID":"{{fiyatListesiID}}",
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Fiyat Listesi Satirlar 


## End-point: Fiyat Listesi Satirlar Getir
### Method: GET
>```
>{{BaseUrl}}/api/FiyatListesiSatirlar
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Fiyat Listesi Satir Ekle
Yeni bir fiyat listesi oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/FiyatListesiSatirlar/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "FiyatListesiID": "{{fiyatListesiID}}",
    "StokID": "{{stokID}}",
    "Fiyat": "{{fiyatListesiSatirFiyat}}",
    "DovizID": "{{dovizID}}",
    "TipID": "{{tipIDFiyatListesiSatis}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Fiyat Listesi Satir Düzenle
Yeni bir fiyat listesi oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/FiyatListesiSatirlar/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "StrID": "{{fiyatListesiSatirID}}",
    "FiyatListesiID": "{{fiyatListesiID}}",
    "StokID": "{{stokID}}",
    "DovizID": "{{dovizID}}",
    "Fiyat": "{{fiyatListesiSatirFiyatDuzelt}}",
    "TipID": "{{fiyatListesiTipIDDuzelt}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Fiyat Listesi Satir Sil
Mevcut fiyat listesini silmektedir


######  Bu işlemin geri dönüşü yoktur. Silmeden önce bu fiyat listesine bağlı tüm stokların ve hareketlerin liste ile ilişkisini kesmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/FiyatListesiSatirlar/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "StrID":"{{fiyatListesiSatirID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Cari 


## End-point: Carileri Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Cari/
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|EsnekAramaKisiti||
|CariID|10074|
|CariKodu||
|CariAdi||
|VergiDairesiID||
|VergiDairesiKodu||
|VergiDairesiAdi||
|VergiNo||
|TipAdi||
|TipID||
|OlsID||
|DgsID||
|Durum||
|OnayDurum||
|SirketID||
|SubeID||
|DgsTar|TarihBas eq 2022-05-02|
|||


### 🔑 Authentication bearer

|Param|value|Type|
|---|---|---|
|token|5XFY7Iv3TzsSL18gTiZjTlh6AKcr3O1NpS1As4gQysFpgNZJIaczXEqsqdV1tVR2EBzkY_YzaDzgCQP7MEG6Ew34Es7QDsUHtjTylLdpremuJ94RL0TbdlpoBwSyNTRo3lUSqVhIPoC1yqp7pPX9mRhwV2GlofcaAKfui77_s_kJmb1FRtfIhawJNxSxSaV7_Vc0xznJteGcQpy5-Izmvu0iwjjp-S2dOQ-5CuS37DxCpjwCJMD4QUYNNm7NK8Jd59zmsyyK6R2Gd9e2PXfLIfTJtAHQfku7g6Zwmxjpw9n7J_m1ldgfFIzF0k-Y1jq3Df2VTwkd52ZLxhJYH1jSQpKhbpqfaB81JzNV6_SVQcfmH5J1q1HsRcKGV8GxSg1sf5vGa68vfmAit3pPEdtaos0dVGeKpqD96_L1pivgzOUYaWuOxv2FDhxruG1oGuk-4-7T_N_W7U85QvOkpnyyZIYjwLApE3Q_CBs1kq9QdDaJZg-InhMCBUpzZLAhfxsJ|string|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cari Oluştur
Yeni bir cari oluşturmaktadır.

\-Cariye adres, ilgili, risk, ziyaret vb. eklenmek istenirse cari oluşturulduktan sonra ilgili api kısmından eklenmelidir.

###### Mevcut vergi dairelerini görmek için API dökümanından Vergi Dairesi kısmını inceleyiniz.
### Method: POST
>```
>{{BaseUrl}}/api/Cari/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "CariKodu": "{{cariKodu}}",
            "CariAdi": "{{cariAdi}}",
            "MuhtelifMi": "{{muhtelifMi}}",
            "VergiDairesiID": "{{vergiDairesiID}}",
            "VergiNo": "{{vergiNo}}",
            "SubeID": "{{subeID}}",
            "SirketID": "{{sirketID}}",
            "Durum": "{{durum}}",
            "TipID": "{{tipIDCari_Musteri}}"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cari Düzenle
Mevcut cari düzenlenmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Cari/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "CariID": "{{cariID}}",
            "CariKodu": "{{cariKoduDuzelt}}",
            "CariAdi": "{{cariAdiDuzelt}}",
            "MuhtelifMi": "{{muhtelifMiDuzelt}}",
            "VergiDairesiID": "{{vergiDairesiID}}",
            "VergiNo": "{{vergiNo}}",
            "TipID": "{{tipIDCari_Musteri}}",
            "Durum": "{{durum}}"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cari Sil
Mevcut cariyi silmektedir

###### Bu işlemin geri dönüşü yoktur. Silmeden önce bu carinin hareketler ve bankalarla ile ilişkisini kesmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/Cari/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "CariID":"{{cariID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cari Hareketleri Liste
Bu uç nokta ile belirtilen kısıtlara göre cari hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/CariHareketleri?CariID=1
>```
### Query Params

|Param|value|
|---|---|
||null|
|CariID|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Cari Risk 


## End-point: Cari Riskleri Getir
Sistemde kayıtlı olan bütün cari risk kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/CariRisk/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cari Risk Oluştur
Yeni bir cari risk oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/CariRisk/Post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "CariID": 3,
            "Durum": true,
            "TarihBas": "2023-04-10T00:00:00",
            "TarihBit": "2023-12-31T00:00:00",
            "Aciklama": "Deneme",
            "MusteriCeki": 500.000000,
            "KendiCeki": 500.000000,
            "MusteriSenedi": 500.000000,
            "KendiSenedi": 500.000000,
            "AcikHesap": 500.000000,
            "Teminat": 0.000000,
            "Siparis": 0.000000,
            "SiparisRiskKisimOrn": 0.000000,
            "Toplam": 2500.000000
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cari Risk Düzenle
Var olan cari riski düzenlemeketedir.
### Method: POST
>```
>{{BaseUrl}}/api/CariRisk/Post?KayitTipi=2
>```
### Body (**raw**)

```json
        {
            "RiskID": 10,
            "CariID": 3,
            "Durum": true,
            "TarihBas": "2023-04-10T00:00:00",
            "TarihBit": "2023-12-31T00:00:00",
            "Aciklama": "Deneme",
            "MusteriCeki": 600.000000,
            "KendiCeki": 600.000000,
            "MusteriSenedi": 600.000000,
            "KendiSenedi": 600.000000,
            "AcikHesap": 600.000000,
            "Teminat": 0.000000,
            "Siparis": 0.000000,
            "SiparisRiskKisimOrn": 0.000000,
            "Toplam": 3500.000000
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cari Risk Sil
Mevcut cari riski silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/CariRisk/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "RiskID": 10
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Cari Ziyaret 


## End-point: Cari Ziyaretleri Getir
Sistemde kayıtlı olan bütün cari ziyaret kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/CariZiyaret/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cari Ziyaret Oluştur
Yeni bir cari ziyaret oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/CariZiyaret/Post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "CariID": 1,
            "SirketID": 1,
            "SubeID": 1,
            "Tarih": "2023-04-11T10:13:00",
            "IlgiliID": 2,
            "Konu": "deneme",
            "CariAdresID": 3,
            "ProjeID": null,
            "PlasiyerID": null
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cari Ziyaret Düzenle
Var olan cari ziyareti düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/CariZiyaret/Post?KayitTipi=2
>```
### Body (**raw**)

```json
        {
            "CariZiyaretID": 3,
            "CariID": 1,
            "SirketID": 1,
            "SubeID": 1,
            "Tarih": "2023-04-11T10:13:00",
            "IlgiliID": 2,
            "Konu": "test",
            "CariAdresID": 3,
            "ProjeID": null,
            "PlasiyerID": null
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cari Ziyaret Sil
Mevcut cari ziyareti silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/CariZiyaret/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "CariZiyaretID": 3
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Cari Adresleri 


## End-point: Adresleri Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/CariAdres?CariID=10233
>```
### Query Params

|Param|value|
|---|---|
|CariID|10233|
|IlD|6|
|EsnekAramaKisiti||
|SayfaSatirSayisi||
|AdresID||
|OlsID||
|DgsID||
|Durum||



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: CariAdres Ekle
### Method: POST
>```
>{{BaseUrl}}/api/CariAdres/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
"CariID":"{{cariID}}",
"IlceID":"{{ilceID}}",
"AdresAdi":"{{adresAdi}}",
"SokakAdi":"{{sokakAdi}}",
"BinaAdi":"{{binaAdi}}",
"BinaNo":"{{binaNo}}",
"KapiNo":"{{kapiNo}}",
"Tel":"{{tel}}",
"Email":"{{email}}",
"Web":"{{web}}",
"Durum":"{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: CariAdres Düzenle
### Method: POST
>```
>{{BaseUrl}}/api/CariAdres/post?KayitTipi=2
>```
### Body (**raw**)

```json
{
"AdresID":"{{adresID}}",
"CariID":"{{cariID}}",
"IlceID":"{{ilceID}}",
"AdresAdi":"{{adresAdiDuzelt}}",
"SokakAdi":"{{sokakAdiDuzelt}}",
"BinaAdi":"{{binaAdiDuzelt}}",
"BinaNo":"{{binaNoDuzelt}}",
"KapiNo":"{{kapiNoDuzelt}}",
"Tel":"{{telDuzelt}}",
"Email":"{{emailDuzelt}}",
"Web":"{{webDuzelt}}",
"Durum":"{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: CariAdres Sil
### Method: POST
>```
>{{BaseUrl}}/api/CariAdres/post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "AdresID":"{{adresID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Adres 


## End-point: İlleri Getir
İller listesini getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Iller
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İl Ekle
İl ekleme işlemi için kullanılmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Iller/Post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "IlKodu": "01",  // Plaka kodu
            "IlAdi": "Adana",
            "UlkeID": 1     
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İl Düzenle
İl bilgilerini düzenlemek için kullanılmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Iller/post?KayitTipi=2
>```
### Body (**raw**)

```json
        {
            "IlID": 87,
            "IlKodu": "tk",
            "IlAdi": "tk",
            "UlkeID": 1
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İl Sil
İl bilgisini silmek için kullanılmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Iller/post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "IlID": 87
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İlçeleri Getir
İlçeler listesini getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Ilceler
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İlçe Ekle
İlçe ekleme işlemi için kullanılmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Ilceler/Post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "IlceKodu": "1104",
            "IlceAdi": "Seyhan",
            "IlID": 1,
            "PostaKodu": null,
            "TelAlanKodu": "322"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İlçe Düzenle
İlçe bilgilerini düzenlemek için kullanılmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Ilceler/post?KayitTipi=2
>```
### Body (**raw**)

```json
        {
            "IlceID": 1,
            "IlceKodu": "1104",
            "IlceAdi": "Seyhan",
            "IlID": 1,
            "PostaKodu": null,
            "TelAlanKodu": "322"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İlçe Sil
İlçe bilgisini silmek için kullanılmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Ilceler/post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "IlceID": 1
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Ülkeleri Getir
Ülkeler listesini getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Ulkeler
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Ülke Ekle
Ülke ekleme işlemi için kullanılmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Ulkeler/Post?KayitTipi=1
>```
### Body (**raw**)

```json
 {
            "UlkeKodu": "US",
            "UlkeAdi": "ABD",
            "UlkeAlanKodu": "1"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Ülke Düzenle
Ülke bilgilerini düzenlemek için kullanılmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Ulkeler/post?KayitTipi=2
>```
### Body (**raw**)

```json
        {
            "UlkeID": 2,
            "UlkeKodu": "US",
            "UlkeAdi": "ABD",
            "UlkeAlanKodu": "1"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Ülke Sil
Ülke bilgisini silmek için kullanılmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Ulkeler/post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "UlkeID": 2
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Cari İlgilileri 


## End-point: İlgilileri Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/CariIlgili?CariID=10233
>```
### Query Params

|Param|value|
|---|---|
|CariID|10233|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İlgili Ekle
### Method: POST
>```
>{{BaseUrl}}/api/CariIlgili/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "CariID": "{{cariID}}",
            "IlgiliAdi": "{{ilgiliAdi}}",
            "Tel": "{{ilgiliTel}}",
            "Fax": "{{ilgiliFax}}",
            "Email": "{{ilgiliEmail}}",
            "Not1": "{{ilgiliNot1}}",
            "Not2": "{{ilgiliNot2}}",
            "Unvan": "{{ilgiliUnvan}}",
            "Dogum": "{{ilgiliDogum}}",
            "Durum": "{{durum}}"
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İligli Düzenle
### Method: POST
>```
>{{BaseUrl}}/api/CariIlgili/post?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "IlgiliID": "{{ilgiliID}}",
            "CariID": "{{cariID}}",
            "IlgiliAdi": "{{ilgiliAdiDuzelt}}",
            "Tel": "{{ilgiliTelDuzelt}}",
            "Fax": "{{ilgiliFaxDuzelt}}",
            "Email": "{{ilgiliEmailDuzelt}}",
            "Not1": "{{ilgiliNot1Duzelt}}",
            "Not2": "{{ilgiliNot2Duzelt}}",
            "Unvan": "{{ilgiliUnvanDuzelt}}",
            "Dogum": "{{ilgiliDogumDuzelt}}",
            "Durum": "{{durum}}"
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İlgili Sil
### Method: POST
>```
>{{BaseUrl}}/api/CariIlgili/post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "IlgiliID":"{{ilgiliID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Cari Banka 


## End-point: Bankaları Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/CariBanka?EsnekAramaKisiti&CariID=4920
>```
### Query Params

|Param|value|
|---|---|
|EsnekAramaKisiti|null|
|CariID|4920|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Ekle
### Method: POST
>```
>{{BaseUrl}}/api/CariBanka/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "CariID": "{{cariID}}",
            "BankaSubeID": "{{bankaSubeID}}",
            "IbanNo": "{{cariBankaIbanNo}}",
            "Durum": true
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Düzenle
### Method: POST
>```
>{{BaseUrl}}/api/CariBanka/post?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "CariBankaID": "{{cariBankaID}}",
            "CariID": "{{cariID}}",
            "BankaSubeID": "{{bankaSubeID}}",
            "IbanNo": "{{cariBankaIbanNoDuzelt}}",
            "Durum": true
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Sil
### Method: POST
>```
>{{BaseUrl}}/api/CariBanka/post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "CariBankaID" :"{{cariBankaID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Kasa 


## End-point: Kasaları Getir
Sistemde kayıtlı olan bütün kasa kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/Kasa/GetKayit
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Kasa Oluştur
Yeni bir kasa oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Kasa/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "KasaKodu": "{{kasaKodu}}",
            "KasaAdi": "{{kasaAdi}}",
            "DovizID": "{{kasaDovizID}}",
            "SubeID": "{{subeID}}",
            "SirketID": "{{sirketID}}",
            "Durum": "{{durum}}"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Kasa Düzenle
Var olan kasayı düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Kasa/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "KasaID": "{{kasaID}}",
            "KasaKodu": "{{kasaKoduDuzelt}}",
            "KasaAdi": "{{kasaAdiDuzelt}}",
            "DovizID": "{{kasaDovizIDDuzelt}}",
            "SubeID": "{{subeID}}",
            "SirketID": "{{sirketID}}",
            "Durum": "{{durum}}",
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Kasa Sil
Mevcut kasayı silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Kasa/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "KasaID" : "7"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Kasa Hareketleri Liste
Bu uç nokta ile belirtilen kısıtlara göre kasa hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/KasaHareketleri?CariID=1
>```
### Query Params

|Param|value|
|---|---|
|CariID|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Banka Hesap 


## End-point: Banka Hesapları Getir
Sistemde kayıtlı olan bütün banka hesap kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/BankaHesap/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Hesap Oluştur
StartFragment

Yeni bir banka hesap oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/BankaHesap/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
        "BankaSubeID": 1,
        "HesapKodu": "000000000000100",
        "HesapAdi": "Deneme Banka Kartı",
        "CariBankaHesapID": null,
        "IbanNo": "TR00000",
        "Tel": null,
        "Fax": null,
        "Email": null,
        "Web": null,
        "DovizID": 1,
        "SubeID": 0,
        "SirketID": 0,
        "Durum": true,
        "TipID": 108001,
        "EntegrasyonTanimID": 51,
        "Kod1ID": null,
        "Kod2ID": null,
        "Kod3ID": null,
        "Kod4ID": null,
        "Kod5ID": null,
        "Kod6ID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "YedekD1": null,
        "YedekD2": null,
        "YedekD3": null,
        "YedekS1": null,
        "YedekS2": null,
        "YedekS3": null,
        "SablonID": null,
        "KartPuan": 8.640000
    }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Hesap Düzenle
StartFragment

Var olan banka hesabını düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/BankaHesap/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "BankaHesapID": "{{bankaHesapID}}",
            "BankaSubeID": "{{bankaHesapSubeID}}",
            "HesapKodu": "{{bankaHesapKoduDuzelt}}",
            "HesapAdi": "{{bankaHesapAdiDuzelt}}",
            "IbanNo": "{{bankaHesapIbanNoDuzelt}}",
            "Tel": "{{bankaHesapTel}}",
            "Fax": "{{bankaHesapFax}}",
            "Email": "{{bankaHesapEmail}}",
            "Web": "{{bankaHesapWeb}}",
            "DovizID": "{{bankaHesapDovizID}}",
            "SubeID": "{{subeID}}",
            "SirketID": "{{sirketID}}",
            "Durum": true,
            "TipID": "{{tipIDBankaCari}}"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Hesap Sil
StartFragment

Mevcut banka hesabını silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/BankaHesap/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "BankaHesapID" : "{{bankaHesapID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Hareketleri Liste
Bu uç nokta ile belirtilen kısıtlara göre stok hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/BankaHareketleri
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Banka 


## End-point: Banka Getir
Sistemde kayıtlı olan bütün banka kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/Banka/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Oluştur
Yeni bir banka oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Banka/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "BankaKodu": "100",
            "BankaAdi": "denemebeyzatest",
            "Durum": true
 }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Düzenle
Var olan bankayı düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Banka/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
        "BankaID": 100016,
        "BankaKodu": "100",
        "BankaAdi": "denemebeyzatestson",
        "Durum": true
    }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Sil
Mevcut bankayı silmektedir.

###### Bu işlemin geri dönüşü yoktur. Silmeden önce bu bu bankanın hareketler ve bankalarla ile ilişkisini kesmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/Banka/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
        "BankaID": 100016
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Hareket Türleri Alt 


## End-point: Hareket Türleri Alt Getir
Sistemde kayıtlı olan bütün hareket türleri alt kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/HareketTurleriAlt
>```
### Body (**raw**)

```json

```

### Response: 200
```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 1,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 1
    },
    "Model": [
        {
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "HareketTurleriDtyKodu": "DVR",
            "HareketTurleriDtyAdi": "Devir",
            "HareketTurAltID": 3,
            "HareketKodu": "000001",
            "HareketAdi": "test",
            "SubeID": 1,
            "SirketID": 1,
            "HareketTurDtyID": 1021,
            "Durum": true,
            "IskontoOran": 15,
            "Renk": "#000000"
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Hareket Türleri Alt Oluştur
Yeni bir hareket türleri altı oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/HareketTurleriAlt/Post?KayitTipi=1
>```
### Body (**raw**)

```json
 {
            "HareketKodu": "000002",
            "HareketAdi": "test",
            "SubeID": 1,
            "SirketID": 1,
            "HareketTurDtyID": 1021,
            "Durum": true,
            "IskontoOran": 25.000000,
            "Renk": "#000000"
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "HareketTurAltID": 6,
        "HareketKodu": "000002",
        "HareketAdi": "test",
        "SubeID": 1,
        "SirketID": 1,
        "HareketTurDtyID": 1021,
        "Durum": true,
        "IskontoOran": 25,
        "Renk": "#000000"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Hareket Türleri Alt Düzenle
Var olan hareket türleri altı düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/HareketTurleriAlt/Post?KayitTipi=2
>```
### Body (**raw**)

```json
 {
            "HareketTurAltID": 6,
            "HareketKodu": "000002",
            "HareketAdi": "test",
            "SubeID": 1,
            "SirketID": 1,
            "HareketTurDtyID": 1021,
            "Durum": true,
            "IskontoOran": 35.000000,
            "Renk": "#000000"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "HareketTurAltID": 6,
        "HareketKodu": "000002",
        "HareketAdi": "test",
        "SubeID": 1,
        "SirketID": 1,
        "HareketTurDtyID": 1021,
        "Durum": true,
        "IskontoOran": 35,
        "Renk": "#000000"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Hareket Türleri Alt Sil
Mevcut hareket türleri altı silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/HareketTurleriAlt/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
        "HareketTurAltID": 6
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "HareketTurAltID": 6,
        "HareketKodu": null,
        "HareketAdi": null,
        "SubeID": 0,
        "SirketID": 0,
        "HareketTurDtyID": null,
        "Durum": false,
        "IskontoOran": 0,
        "Renk": null
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Açıklamalar 


## End-point: Aciklamalar Getir
Sistemde kayıtlı olan bütün açıklama kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/Aciklamalar/Get
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Aciklamalar Oluştur
Yeni bir açıklama oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Aciklamalar/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
        "A1": "deneme",
        "A2": null,
        "A3": null,
        "A4": null,
        "A5": null,
        "A6": null,
        "A7": null,
        "A8": null,
        "A9": null,
        "A10": null,
        "A11": null
    }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Aciklamalar Düzenle
Var olan açıklamayı düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Aciklamalar/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
        "AciklamaID": 2,
        "A1": "deneme",
        "A2": "deneme",
        "A3": null,
        "A4": null,
        "A5": null,
        "A6": null,
        "A7": null,
        "A8": null,
        "A9": null,
        "A10": null,
        "A11": null
    }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Aciklamalar Sil
Mevcut açıklamayı silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Aciklamalar/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
        "AciklamaID": 2
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: PerGirisCikis 


## End-point: PerGirisCikis Getir
Sistemde kayıtlı olan bütün personel giriş çıkış kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/PerGirisCikis/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: PerGirisCikis Oluştur
Yeni bir personel giriş çıkış oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/PerGirisCikis/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "PerSirketSicilID": 1,
            "PersonelID": 1,
            "GirisTarihi": "2023-01-01T00:00:00",
            "CikisTarihi": "2023-04-22T00:00:00",
            "CikisNedenSSKID": 1,
            "CikisNedenID": 1,
            "Aciklama": "test",
            "Ihbar": true,
            "Kidem": true,
            "IzinParasi": true,
            "KidemBasTarihi": "2023-01-01T00:00:00",
            "OzlukBasTarihi": "2023-01-01T00:00:00"
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: PerGirisCikis Düzenle
Var olan personel giriş çıkışını düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/PerGirisCikis/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
        "StrID": 6,
        "PerSirketSicilID": 1,
        "PersonelID": 1,
        "GirisTarihi": "2023-01-01T00:00:00",
        "CikisTarihi": "2023-04-26T00:00:00",
        "CikisNedenSSKID": 1,
        "CikisNedenID": 1,
        "Aciklama": "deneme",
        "Ihbar": false,
        "Kidem": false,
        "IzinParasi": false,
        "KidemBasTarihi": "2023-01-01T00:00:00",
        "OzlukBasTarihi": "2023-01-01T00:00:00"
    }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: PerGirisCikis Sil
Mevcut personel giriş çıkışı silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/PerGirisCikis/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
        "StrID": 6
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: TakvimStr 


## End-point: TakvimStr Getir
Sistemde kayıtlı olan bütün takvim satır kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/TakvimStr/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: TakvimStr Oluştur
Yeni bir takvim satırı oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/TakvimStr/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "TakvimID": 1,
            "Tarih": "2024-04-13T00:00:00",
            "BasSaat": 8.000000,
            "BitSaat": 15.500000,
            "Durum": true,
            "GunTip": "NM",
            "GunSure": 450
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: TakvimStr Düzenle
Var olan takvim satırını düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/TakvimStr/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "StrID": 394,
            "TakvimID": 1,
            "Tarih": "2024-05-13T00:00:00",
            "BasSaat": 10.000000,
            "BitSaat": 16.500000,
            "Durum": true,
            "GunTip": "NM",
            "GunSure": 450
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: TakvimStr Sil
Mevcut takvim satırını silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/TakvimStr/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "StrID": 394
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Cek Senet 


## End-point: Cek Senet Getir
Sistemde kayıtlı olan bütün çek senet kartlarının görüntülendiği alandır.
### Method: GET
>```
>https://localhost:44346/api/CekSenet/Get
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cek Senet Oluştur
Yeni bir çek senet oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/CekSenet/Post?KayitTipi=1
>```
### Body (**raw**)

```json

        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cek Senet Düzenle
Var olan çek seneti düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/CekSenet/Post?KayitTipi=2
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Cek Senet Sil
Mevcut çek seneti silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/CekSenet/Post?KayitTipi=-1
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Makine 


## End-point: Makine Getir
Sistemde kayıtlı olan bütün makine kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/urMakine/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Makine Oluştur
Yeni bir makine oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/urMakine/Post?KayitTipi=1
>```
### Body (**raw**)

```json
        {

            "SubeID": 0,
            "SirketID": 0,
            "MakineKodu": "denemetest",
            "MakineAdi": "denemetest",
            "DemirbasID": 233,
            "Durum": true,
            "TipID": 114001,
            "Kod1ID": null,
            "Kod2ID": null,
            "Kod3ID": null,
            "Kod4ID": null,
            "Kod5ID": null,
            "Kod6ID": null,
            "Etiket1ID": null,
            "Etiket2ID": null,
            "Etiket3ID": null,
            "Etiket4ID": null,
            "Etiket5ID": null,
            "Aciklama": "Hızlı Reçeetelerde Kullanılan makine"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Makine Düzenle
Var olan makineyi düzenlemeketedir.
### Method: POST
>```
>{{BaseUrl}}/api/urMakine/Post?KayitTipi=2
>```
### Body (**raw**)

```json
        {
            "MakineID": 3,
            "SubeID": 0,
            "SirketID": 0,
            "MakineKodu": "denemetest",
            "MakineAdi": "denemetest",
            "DemirbasID": 233,
            "Durum": true,
            "TipID": 114001,
            "Kod1ID": null,
            "Kod2ID": null,
            "Kod3ID": null,
            "Kod4ID": null,
            "Kod5ID": null,
            "Kod6ID": null,
            "Etiket1ID": null,
            "Etiket2ID": null,
            "Etiket3ID": null,
            "Etiket4ID": null,
            "Etiket5ID": null,
            "Aciklama": "Hızlı Reçeetelerde Kullanılan makine"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Makine Sil
Mevcut makineyi silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/urMakine/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
        "MakineID": 3
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Makine Arıza 


## End-point: Makine Getir
Sistemde kayıtlı olan bütün makine arıza kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/UrMakineAriza/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Makine Oluştur
Yeni bir makine arızasını oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/urMakineAriza/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "SubeID": 1,
            "SirketID": 1,
            "MakineID": 1,
            "ArizaAciklama": "test",
            "ArizaBaslangic": "2023-04-10T00:00:00",
            "ArizaGiderilmePlanTarihi": "2023-04-10T00:00:00",
            "TamirBaslangic": "2023-04-10T00:00:00",
            "ArizaBitis": "2023-04-10T00:00:00",
            "TamirSuresi": 0,
            "IsciAdedi": 0.000000,
            "IscilikMaliyetiSaat": 0.000000,
            "KullanilanMalzemeMaliyet": 0.000000,
            "YapilanTamirAciklama": "test"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Makine Düzenle
Var olan makine arızasını düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/urMakineAriza/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "MakineArizaID": 3,
            "SubeID": 1,
            "SirketID": 1,
            "MakineID": 1,
            "ArizaAciklama": "deneme",
            "ArizaBaslangic": "2023-04-10T00:00:00",
            "ArizaGiderilmePlanTarihi": "2023-04-10T00:00:00",
            "TamirBaslangic": "2023-04-10T00:00:00",
            "ArizaBitis": "2023-04-10T00:00:00",
            "TamirSuresi": 0,
            "IsciAdedi": 0.000000,
            "IscilikMaliyetiSaat": 0.000000,
            "KullanilanMalzemeMaliyet": 0.000000,
            "YapilanTamirAciklama": "deneme"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Makine Sil
Mevcut makine arızasını silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/urMakineAriza/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "MakineArizaID": 3
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Operasyon 


## End-point: Operasyon Getir
Sistemde kayıtlı olan bütün operasyon kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/urOperasyon/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Operasyon Oluştur
Yeni bir operasyon oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/urOperasyon/Post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "SubeID": 0,
            "SirketID": 0,
            "OperasyonKodu": "deneme",
            "OperasyonAdi": "deneme",
            "Durum": true,
            "TipID": 115001,
            "Kod1ID": null,
            "Kod2ID": null,
            "Kod3ID": null,
            "Kod4ID": null,
            "Kod5ID": null,
            "Kod6ID": null,
            "Etiket1ID": null,
            "Etiket2ID": null,
            "Etiket3ID": null,
            "Etiket4ID": null,
            "Etiket5ID": null,
            "Aciklama": "Hızlı Reçetelerde kullanılan operasyon",
            "HizBirimID": null,
            "KartPuan": 0.000000
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Operasyon Düzenle
Var olan operasyonu düzenlemeketedir.
### Method: POST
>```
>{{BaseUrl}}/api/urOperasyon/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
        "OperasyonID": 12,
        "SubeID": 0,
        "SirketID": 0,
        "OperasyonKodu": "deneme",
        "OperasyonAdi": "testson",
        "Durum": true,
        "TipID": 115001,
        "Kod1ID": null,
        "Kod2ID": null,
        "Kod3ID": null,
        "Kod4ID": null,
        "Kod5ID": null,
        "Kod6ID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "Aciklama": "Hızlı Reçetelerde kullanılan operasyon",
        "HizBirimID": null,
        "KartPuan": 0.000000
    }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Operasyon Sil
Mevcut operasyonu silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/urOperasyon/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
        "OperasyonID": 12
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Yevmiye Fis 


## End-point: YevmiyeFis Getir
Sistemde kayıtlı olan yevmiye fiş kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/YevmiyeFis/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: YevmiyeFis Oluştur
Yeni bir yevmiye fişi oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/YevmiyeFis/Post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "YevmiyeFisID": 0,
            "FisNo": "000000000000001",
            "SirketID": 1,
            "SubeID": 1,
            "TipID": 110002,
            "Tarih": "2023-03-20T00:00:00",
            "Ay": 0,
            "Yil": 0,
            "DekontTipID": 5003,
            "DekontFaturaID": null,
            "Kilitli": false
         }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: YevmiyeFis Düzenle
Var olan yevmiye fişini düzenlemeketedir.
### Method: POST
>```
>{{BaseUrl}}/api/YevmiyeFis/Post?KayitTipi=2
>```
### Body (**raw**)

```json
        {
            "YevmiyeFisID": 23,
            "FisNo": "000000000000001",
            "SirketID": 1,
            "SubeID": 1,
            "TipID": 110002,
            "Tarih": "2023-03-20T00:00:00",
            "Ay": 0,
            "Yil": 0,
            "DekontTipID": 5003,
            "DekontFaturaID": null,
            "Kilitli": false
         }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: YevmiyeFis Sil
Mevcut yevmiye fişini silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/YevmiyeFis/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "YevmiyeFisID": 22
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Yevmiye Fis Hareketleri 


## End-point: YevmiyeFisHareketleri Getir
Sistemde kayıtlı olan bütün yevmiye fiş hareketlerinin görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/YevmiyeFisHareketleri/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: YevmiyeFisHareketleri Oluştur
Yeni bir yevmiye fiş hareketi oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/YevmiyeFisHareketleri/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "HareketID": 0,
            "YevmiyeFisID": 23,
            "SirketID": 1,
            "SubeID": 1,
            "MuhasebeID": 1,
            "TipID": 110002,
            "Tarih": "2023-03-20T00:00:00",
            "Ay": 3,
            "Yil": 2023,
            "BA": "B",
            "Miktar": 5.000000,
            "Tutar": 5.000000,
            "TutarDvz": 0.000000,
            "DovizID": 1,
            "Oran": 0.000000,
            "DekontFaturaID": null,
            "CariHareketTabloID": null,
            "CariHareketID": null,
            "CariKartTabloID": null,
            "CariKartID": null,
            "EntegrasyonTanimID": 3,
            "ProjeID": null,
            "Aciklama1": "",
            "Aciklama2": "",
            "BABSTutar": 0.000000
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: YevmiyeFisHareketleri Düzenle
Var olan yevmiye fiş hareketini düzenlemeketedir.
### Method: POST
>```
>{{BaseUrl}}/api/YevmiyeFisHareketleri/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "HareketID": 32,
            "YevmiyeFisID": 22,
            "SirketID": 1,
            "SubeID": 1,
            "MuhasebeID": 1,
            "TipID": 110002,
            "Tarih": "2023-03-20T00:00:00",
            "Ay": 3,
            "Yil": 2023,
            "BA": "A",
            "Miktar": 5.000000,
            "Tutar": 5.000000,
            "TutarDvz": 0.000000,
            "DovizID": 1,
            "Oran": 0.000000,
            "DekontFaturaID": null,
            "CariHareketTabloID": null,
            "CariHareketID": null,
            "CariKartTabloID": null,
            "CariKartID": null,
            "EntegrasyonTanimID": 3,
            "ProjeID": null,
            "Aciklama1": "",
            "Aciklama2": "",
            "BABSTutar": 0.000000
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: YevmiyeFisHareketleri Sil
Mevcut yevmiye fiş hareketini silmektedir.

###### Bu işlemin geri dönüşü yoktur. Silmeden önce bu bu bankanın hareketler ve bankalarla ile ilişkisini kesmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/YevmiyeFisHareketleri/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "HareketID": 33,
            "YevmiyeFisID": 23
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: OlcuBirimleri 


## End-point: OlcuBirimleri Getir
Sistemde kayıtlı olan bütün ölçü birimlerinin görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/OlcuBirimleri/Get
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: OlcuBirimleri Oluştur
Yeni bir ölçü birimi oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/OlcuBirimleri/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "OlcuBirimleriUBLKodu": "{{olcuBirimleriUBLKodu}}",
            "OlcuBirimleriUBLAdi": "{{olcuBirimleriUBLAdi}}",
            "SubeAdi": "{{subeAdi}}",
            "SirketAdi": "{{sirketAdi}}",
            "TipKodu": "{{tipKodu}}",
            "TipAdi": "{{tipAdi}}",
            "BirimID": {{birimID}},
            "BirimKodu": "{{birimKodu}}",
            "BirimAdi": "{{birimAdi}}",
            "OlcuBirimleriUBLID": {{olcuBirimleriUBLID}},
            "BirimOran": {{birimOran}},
            "TipID": {{tipID}}

            /*"OlcuBirimleriUBLKodu": "C62",
            "OlcuBirimleriUBLAdi": "ADET(UNIT)",
            "SubeAdi": "Tüm Şubeler",
            "SirketAdi": "Tüm Şirketler",
            "TipKodu": "Adet",
            "TipAdi": "Adet",
            "BirimID": 1,
            "BirimKodu": "AD123",
            "BirimAdi": "Adet",
            "OlcuBirimleriUBLID": 7,
            "BirimOran": 0.000000,
            "TipID": 141001*/
        }  
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: OlcuBrimleri Düzenle
Var olan ölçü birimini düzenlemeketedir.
### Method: POST
>```
>{{BaseUrl}}/api/OlcuBirimleri/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
          /* 
            "OlcuBirimleriUBLKodu": "{{olcuBirimleriUBLKodu}}",
            "OlcuBirimleriUBLAdi": "{{olcuBirimleriUBLAdi}}",
            "SubeAdi": "{{subeAdi}}",
            "SirketAdi": "{{sirketAdi}}",
            "TipKodu": "{{tipKodu}}",
            "TipAdi": "{{tipAdi}}",
            "BirimID": {{birimID}},
            "BirimKodu": "{{birimKodu}}",
            "BirimAdi": "{{birimAdi}}",
            "OlcuBirimleriUBLID": {{olcuBirimleriUBLID}},
            "BirimOran": {{birimOran}},
            "TipID": {{tipID}}*/
            "OlcuBirimleriUBLKodu": "GRM",
            "OlcuBirimleriUBLAdi": "GRAM",
            "SubeAdi": "Tüm Şubeler",
            "SirketAdi": "Tüm Şirketler",
            "TipKodu": "Adet",
            "TipAdi": "Adet",
            "BirimID": 15,
            "BirimKodu": "AD123",
            "BirimAdi": "Adet",
            "OlcuBirimleriUBLID": 17,
            "BirimOran": 0.000000,
            "TipID": 141001
        }  
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: OlcuBrimleri Sil
Mevcut ölçü birimini silmektedir.

###### Bu işlemin geri dönüşü yoktur. Silmeden önce bu bu bankanın hareketler ve bankalarla ile ilişkisini kesmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/OlcuBirimleri/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "BirimKodu": "{{birimKodu}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: PerPuantaj 


## End-point: PerPuantaj Getir
Sistemde kayıtlı olan bütün banka kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/PerPuantaj/Get
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: PerPuantaj Oluştur
Yeni bir personel puantaj oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/PerPuantaj/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "PersonelAdiSoyadi": "{{personelAdiSoyadi}}",
            "PerSirketSicilAciklama": "{{perSirketSicilAciklama}}",
            "PersonelID": "{{personelID}}",
            "PerSirketSicilID": "{{perSirketSicilID}}",
            "TipID": "{{tipID}}",
            "Ay": "{{ay}}",
            "Yil": "{{yil}}",
            "BaslikID": "{{baslikID}}",
            "ToplamGun": "{{toplamGun}}",
            "SSKGun": "{{sskGun}}",
            "MazeretIzni": "{{mazeretIzni}}",
            "Rapor": "{{rapor}}",
            "UcretsizIzin": "{{ucretsizIzin}}",
            "YillikIzin": "{{yillikIzin}}",
            "NormalGun": "{{normalGun}}",
            "HaftaTatili": "{{haftaTatili}}",
            "ResmiTatil": "{{resmiTatil}}",
            "EksikGun": "{{eksikGun}}",
            "EksikGunAciklama": "{{eksikGunAciklama}}",
            "FazlaMesai1": "{{fazlaMesai1}}",
            "FazlaMesai2": "{{fazlaMesai2}}",
            "FazlaMesai3": "{{fazlaMesai3}}",
            "NormalSaat":   "{{normalSaat}}",
            "EksikSaat": "{{eksikSaat}}"
            
          /*  "PersonelAdiSoyadi": "test test",
            "PerSirketSicilAciklama": "Sirketim",
            "PersonelID": 4,
            "PerSirketSicilID": 1,
            "TipID": 0,
            "Ay": 3,
            "Yil": 2023,
            "BaslikID": 4,
            "ToplamGun": 0,
            "SSKGun": 0,
            "MazeretIzni": 2,
            "Rapor": 5,
            "UcretsizIzin": 4,
            "YillikIzin": 1,
            "NormalGun": 0,
            "HaftaTatili": 0,
            "ResmiTatil": 0,
            "EksikGun": 5,
            "EksikGunNedenID": null,
            "EksikGunAciklama": null,
            "FazlaMesai1": 0.000000,
            "FazlaMesai2": 0.000000,
            "FazlaMesai3": 0.000000,
            "NormalSaat": 0.000000,
            "EksikSaat": 0.000000,
            "Durum": true*/
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: PerPuantaj Düzenle
Var olan personel puantajını düzenlemeketedir.
### Method: POST
>```
>{{BaseUrl}}/api/PerPuantaj/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
          /*
            "PersonelAdiSoyadi": "{{personelAdiSoyadi}}",
            "PerSirketSicilAciklama": "{{perSirketSicilAciklama}}",
            "PerPuantajID": "{{perPuantajID}}",
            "PersonelID": "{{personelID}}",
            "PerSirketSicilID": "{{perSirketSicilID}}",
            "TipID": "{{tipID}}",
            "Ay": "{{ay}}",
            "Yil": "{{yil}}",
            "BaslikID": "{{baslikID}}",
            "ToplamGun": "{{toplamGun}}",
            "SSKGun": "{{sskGun}}",
            "MazeretIzni": "{{mazeretIzni}}",
            "Rapor": "{{rapor}}",
            "UcretsizIzin": "{{ucretsizIzin}}",
            "YillikIzin": "{{yillikIzin}}",
            "NormalGun": "{{normalGun}}",
            "HaftaTatili": "{{haftaTatili}}",
            "ResmiTatil": "{{resmiTatil}}",
            "EksikGun": "{{eksikGun}}",
            "EksikGunAciklama": "{{eksikGunAciklama}}",
            "FazlaMesai1": "{{fazlaMesai1}}",
            "FazlaMesai2": "{{fazlaMesai2}}",
            "FazlaMesai3": "{{fazlaMesai3}}",
            "NormalSaat":   "{{normalSaat}}",
            "EksikSaat": "{{eksikSaat}}"*/

            
            "PersonelAdiSoyadi": "ENTEGRASYON deneme",
            "PerSirketSicilAciklama": "Sirketim",
            "PerPuantajID": 1,
            "PersonelID": 3,
            "PerSirketSicilID": 1,
            "TipID": 0,
            "Ay": 3,
            "Yil": 2023,
            "BaslikID": 3,
            "ToplamGun": 0,
            "SSKGun": 0,
            "MazeretIzni": 2,
            "Rapor": 5,
            "UcretsizIzin": 4,
            "YillikIzin": 1,
            "NormalGun": 0,
            "HaftaTatili": 0,
            "ResmiTatil": 0,
            "EksikGun": 5,
            "EksikGunNedenID": null,
            "EksikGunAciklama": null,
            "FazlaMesai1": 0.000000,
            "FazlaMesai2": 0.000000,
            "FazlaMesai3": 0.000000,
            "NormalSaat": 0.000000,
            "EksikSaat": 0.000000
            
        }
        
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: PerPuantaj Sil
Mevcut personel puantajını silmektedir.

###### Bu işlemin geri dönüşü yoktur. Silmeden önce bu bu bankanın hareketler ve bankalarla ile ilişkisini kesmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/PerPuantaj/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "PerPuantajID" : "{{perPuantajID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Personel 


## End-point: Personel Getir
Sistemde kayıtlı olan bütün banka kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/Personel/Get
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Personel Oluştur
Yeni bir stok kartı eklemek için
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Personel/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "PersonelAdiSoyadi": "webapi deneme",
            "TC": "11111711111",
            "PersonelKodu": "000011",
            "OzlukBasTar": "2023-03-30T00:00:00",
            "SgkTanimID": 1,
            "Durum":true

}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Personel Düzenle
Mevcut bir deponun düzeltilmesi için kullanılmaktadır.

######  Depo eklemekten farklı olarak ID eklenmesi gerekmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Personel/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "PersonelID": 27,
            "PersonelAdiSoyadi": "denemewebapi denemeWEBAPİ",
            "TC": "11111711111",
            "PersonelKodu": "000010",
            "OzlukBasTar": "2023-03-30T00:00:00",
            "SgkTanimID": 1

}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Personel Sil
Mevcut bir deponun silinmesi için kullanılmaktadır.

######  Depoyu silmeden önce depoya ait bütün hareketlerin ve stoklar silindiğinden/taşındığından emin olunuz. Aksi takdirde silme işlemi gerçekleşmeyecektir.
### Method: POST
>```
>{{BaseUrl}}/api/Personel/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "PersonelID": 27
            
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: İs Emri 


## End-point: İsEmri Getir
Sistemde kayıtlı olan bütün iş emri kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/urIsEmri/Get
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İsEmri Oluştur
StartFragment

Yeni bir iş emri oluşturmaktadır.  
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/urIsEmri/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "SubeID": 1,
            "SirketID": 1,
            "IsEmriNo": "000007",
            "Tarih": "2023-03-21T00:00:00",
            "TeslimTarihi": "2023-03-22T00:00:00",
            "TipID": 113001,
            "Oncelik": 0,
            "ProjeID": null,
            "Kapali": false,
            "AciklamalarID": null,
            "Renk": null,
            "ReceteID": 6,
            "ReceteAdi": "deneme1",
            "Miktar": 5.000000,
            "Aciklama": " \r\nSipariş Açıklama : \r\n \r\n"

}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İsEmri Düzenle
Mevcut bir iş emrinin düzeltilmesi için kullanılmaktadır.

###### İş emri eklemekten farklı olarak ID eklenmesi gerekmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/urIsEmri/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "IsEmriID": 102,
            "Aciklama": "deneme",
            "SubeID": 1,
            "SirketID": 1,
            "ReceteID": 6,
            "ReceteAdi": "deneme1",
            "Miktar": 5.000000,
            "IsEmriNo": "000007",
            "TipID": 113001,
            "Tarih": "2023-03-21T00:00:00",
            "TeslimTarihi": "2023-03-22T00:00:00"


}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: İsEmri Sil
Mevcut bir iş emrinin silinmesi için kullanılmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/urIsEmri/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "IsEmriID": 102
            
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Banka Şube 


## End-point: Banka Şubeleri Getir
StartFragment

Sistemde kayıtlı olan bütün banka şube kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/BankaSube/GetKayit
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Şube Oluştur
StartFragment

Yeni bir banka şube oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/BankaSube/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "BankaID": "{{bankaSubeBankaID}}",
            "IlceID": "{{bankaSubeIlceID}}",
            "BankaSubeKodu": "{{bankaSubeKodu}}",
            "BankaSubeAdi": "{{bankaSubeAdi}}",
            "Tel": "{{bankaSubeTel}}",
            "Fax": "{{bankaSubeFax}}",
            "Email": "{{bankaSubeEmail}}",
            "Adres": "{{bankaSubeAdres}}",
            "Durum": "{{durum}}"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Şube Düzenle
StartFragment

Var olan banka şubesini düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/BankaSube/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "BankaSubeID": "{{bankaSubeID}}",
            "BankaID": "{{bankaSubeBankaID}}",
            "IlceID": "{{bankaSubeIlceIDDuzelt}}",
            "BankaSubeKodu": "{{bankaSubeKoduDuzelt}}",
            "BankaSubeAdi": "{{bankaSubeAdiDuzelt}}",
            "Durum": "{{durum}}"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Banka Şube Sil
StartFragment

Mevcut banka şubeyi silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/BankaSube/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "BankaSubeID": "{{bankaSubeID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Notlar 


## End-point: Notları Getir
### Method: GET
>```
>{{BaseUrl}}/api/Notlar
>```
### Body (**raw**)

```json
{
    "TabloID": 3001
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Not Ekle/Gönder
### Method: POST
>```
>{{BaseUrl}}/api/Notlar/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "Notu": "Son eklenen stok kartı için not",
    "TabloID": 3001,
    "TabloSatirID": "{{stokID}}"
}
```

### Query Params

|Param|value|
|---|---|
|TabloID|6002|
|TabloSatirID|3|
|NotID|6|
|Notu|postman|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Not Sil
### Method: POST
>```
>{{BaseUrl}}/api/Notlar/Post?KayitTipi=2
>```
### Query Params

|Param|value|
|---|---|
|TabloID|6002|
|TabloSatirID|3|
|NotID|6|
|Notu|postman|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Stok Sayım 


## End-point: Sayım Girişleri Getir
Sistemde kayıtlı olan bütün stok sayımlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/StokSayim
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sayım Girişi Yap
Yeni bir stok kartı eklemek için  
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Örnek Değer | Tanım | ZorunluMu |
| --- | --- | --- | --- |
| StokID | \-1 | Eklenilen ürünün stok ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır. | Evet |
| SubeID | 1 | Stoğun bulunduğu şubenin ID'sidir. | Evet |
| SirketID | 1 | Stoğun ait olduğu şirketin ID'sidir. | Evet |
| StokKodu | "HRD.KPKL.00164" | Stoğun detaylı kodudur. | Evet |
| StokAdi | "Hırdavat Kapı Kolu Burak Oda Rozetli Saten" | Stoğun gözüken adıdır. | Evet |
| StokKisaKodu | "HRD.KPKL" | Stoğun genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa koda sahip olması önemlidir. | Evet |
| StokKisaAdi | "Hırdavat Kapı Kolu" | Stoğun genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa ada sahip olması önemlidir. | Evet |
| Durum | true | Stok kartının aktif veya pasif olduğunu belirlemektedir | Evet |
| TipID | 105001 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Gelir-gider hareketleri gibi işlemler de stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. | Evet |
| StokMuhasebeID | 201 | Stokların muhasebesebesi farklı şekilde işlenebilir. Stok muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz | Evet |
| Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Evet |
| Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel |
| Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel |
| CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel |
| CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel |
| Kalinlik | 10.0 | Stok kartının fizikel kalınlığıdır. | Opsiyonel |
| En | 10.0 | Stok kartının fizikel enidir. | Opsiyonel |
| Boy | 10.0 | Stok kartının fizikel boyudur. | Opsiyonel |
| Yoğunluk | 3.0 | Stok kartının fizikel yoğunluğudur. | Opsiyonel |
| Agirlik | 5.0 | Stok kartının fizikel ağırlığıdır. | Opsiyonel |
| Kod1ID | null | Stok kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Elektronik -> Bilgisayar -> HP | Opsiyonel |
| Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel |
| SablonID | null | Ürün ekleme şablonu varsa girilmelidir. | Opsiyonel |

> &lt;h5 &gt;Ürün oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.&lt;/h5&gt;
### Method: POST
>```
>{{BaseUrl}}/api/StokSayim/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "SubeID": "{{subeID}}",
    "SirketID": "{{sirketID}}",
    "Durum": "{{durum}}",
    "Tarih": "{{bugun}}",
    "DepoID": "{{depoID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sayım Girişi Düzelt
Yeni bir stok kartı eklemek için
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.
### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu Body JSON açıklaması

Parametre | Örnek Değer | Tanım | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen ürünün stok ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır.  | Evet
SubeID | 1 | Stoğun bulunduğu şubenin ID'sidir. | Evet
SirketID | 1 | Stoğun ait olduğu şirketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Stoğun detaylı kodudur. | Evet
StokAdi | "Hırdavat Kapı Kolu Burak Oda Rozetli Saten" | Stoğun gözüken adıdır. | Evet
StokKisaKodu |"HRD.KPKL" | Stoğun genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa koda sahip olması önemlidir. | Evet
StokKisaAdi |"Hırdavat Kapı Kolu" | Stoğun genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa ada sahip olması önemlidir. | Evet
Durum | true | Stok kartının aktif veya pasif olduğunu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Gelir-gider hareketleri gibi işlemler de stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. | Evet
StokMuhasebeID | 201 | Stokların muhasebesebesi farklı şekilde işlenebilir. Stok muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel
Kalinlik | 10.0 | Stok kartının fizikel kalınlığıdır. | Opsiyonel
En | 10.0 | Stok kartının fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kartının fizikel boyudur. | Opsiyonel
Yoğunluk | 3.0 | Stok kartının fizikel yoğunluğudur. | Opsiyonel
Agirlik | 5.0 | Stok kartının fizikel ağırlığıdır. | Opsiyonel
Kod1ID | null | Stok kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel
SablonID | null | Ürün ekleme şablonu varsa girilmelidir. | Opsiyonel

>##### Ürün oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.
### Method: POST
>```
>{{BaseUrl}}/api/StokSayim/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
        "SayimID": 4,
        "DepoID": 1,
        "ProjeID": 1,
        "PlasiyerID": 1,
        "SirketID": 0,
        "SubeID": 1,
        "Tarih": "2023-04-11T00:00:00",
        "Durum": true,
        "Aciklama": null
    }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sayım Grişi  Sil
Mevcut cariyi silmektedir

###### Bu işlemin geri dönüşü yoktur. Silmeden önce bu carinin hareketler ve bankalarla ile ilişkisini kesmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/StokSayim/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "SayimID": "{{sayimID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sayım Hareketleri Getir
### Method: GET
>```
>{{BaseUrl}}/api/StokSayimHareketleri/GetKayit
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sayım Hareketi Ekle
Yeni bir stok kartı eklemek için
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.
### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu Body JSON açıklaması

Parametre | Örnek Değer | Tanım | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen ürünün stok ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır.  | Evet
SubeID | 1 | Stoğun bulunduğu şubenin ID'sidir. | Evet
SirketID | 1 | Stoğun ait olduğu şirketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Stoğun detaylı kodudur. | Evet
StokAdi | "Hırdavat Kapı Kolu Burak Oda Rozetli Saten" | Stoğun gözüken adıdır. | Evet
StokKisaKodu |"HRD.KPKL" | Stoğun genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa koda sahip olması önemlidir. | Evet
StokKisaAdi |"Hırdavat Kapı Kolu" | Stoğun genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa ada sahip olması önemlidir. | Evet
Durum | true | Stok kartının aktif veya pasif olduğunu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Gelir-gider hareketleri gibi işlemler de stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. | Evet
StokMuhasebeID | 201 | Stokların muhasebesebesi farklı şekilde işlenebilir. Stok muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel
Kalinlik | 10.0 | Stok kartının fizikel kalınlığıdır. | Opsiyonel
En | 10.0 | Stok kartının fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kartının fizikel boyudur. | Opsiyonel
Yoğunluk | 3.0 | Stok kartının fizikel yoğunluğudur. | Opsiyonel
Agirlik | 5.0 | Stok kartının fizikel ağırlığıdır. | Opsiyonel
Kod1ID | null | Stok kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel
SablonID | null | Ürün ekleme şablonu varsa girilmelidir. | Opsiyonel

>##### Ürün oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.
### Method: POST
>```
>{{BaseUrl}}/api/StokSayimHareketleri/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "SayimID": "{{sayimID}}",
    "StokID": "{{stokID}}",
    "Miktar": "{{stokSayimMiktar}}",
    "Aciklama":"{{stokSayimAciklama}}",
    "SirketID":"{{sirketID}}",
    "SubeID":"{{subeID}}",
    "Durum":"{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sayım Hareketi Düzelt
Yeni bir stok kartı eklemek için
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.
### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu Body JSON açıklaması

Parametre | Örnek Değer | Tanım | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen ürünün stok ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır.  | Evet
SubeID | 1 | Stoğun bulunduğu şubenin ID'sidir. | Evet
SirketID | 1 | Stoğun ait olduğu şirketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Stoğun detaylı kodudur. | Evet
StokAdi | "Hırdavat Kapı Kolu Burak Oda Rozetli Saten" | Stoğun gözüken adıdır. | Evet
StokKisaKodu |"HRD.KPKL" | Stoğun genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa koda sahip olması önemlidir. | Evet
StokKisaAdi |"Hırdavat Kapı Kolu" | Stoğun genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa ada sahip olması önemlidir. | Evet
Durum | true | Stok kartının aktif veya pasif olduğunu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Gelir-gider hareketleri gibi işlemler de stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. | Evet
StokMuhasebeID | 201 | Stokların muhasebesebesi farklı şekilde işlenebilir. Stok muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel
Kalinlik | 10.0 | Stok kartının fizikel kalınlığıdır. | Opsiyonel
En | 10.0 | Stok kartının fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kartının fizikel boyudur. | Opsiyonel
Yoğunluk | 3.0 | Stok kartının fizikel yoğunluğudur. | Opsiyonel
Agirlik | 5.0 | Stok kartının fizikel ağırlığıdır. | Opsiyonel
Kod1ID | null | Stok kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel
SablonID | null | Ürün ekleme şablonu varsa girilmelidir. | Opsiyonel

>##### Ürün oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.
### Method: POST
>```
>{{BaseUrl}}/api/StokSayimHareketleri/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "SayimHareketID": "{{sayimHareketID}}",
    "SayimID": "{{sayimID}}",
    "StokID": "{{stokID}}",
    "Miktar": "{{stokSayimMiktarDuzelt}}",
    "Aciklama":"{{stokSayimAciklamaDuzelt}}",
    "SirketID":"{{sirketID}}",
    "subeID":"{{subeID}}",
    "Durum":"{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sayım Hareketi Sil
Mevcut cariyi silmektedir

###### Bu işlemin geri dönüşü yoktur. Silmeden önce bu carinin hareketler ve bankalarla ile ilişkisini kesmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/StokSayimHareketleri/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "SayimHareketID": "{{sayimHareketID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Dekont 


## End-point: Tamamla
Dekont başlık ve kalem bilgilerini girdikten sonra tamamla çağrılırsa kayıt tamamlanacaktır. Oluşturulan dekont id bilgisi yeterlidir.

> _**Yarım bırakılmış bir kayıt var ve aynı belge numarası ile yeni bir kaydı tamamla metodu ile eklemeye çalışıyorsak bu belge numarası kullanılmıştır hatası alabiliriz.Bu yüzden kayıtlarımızda belge numaraları farklı olmalıdır.**_
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Tamamla
>```
### Body (**raw**)

```json
{
    "DekontID": 261
}
```

### Response: undefined
```json
null
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Dekont Başlık Getir
Bu uç nokta ile kayıtlı olan dekontun DekontID'si gönderilerek başlık bilgisi alınabilir. Aynı bilgiye Başlıkları Getir sekmesinde DekontID kısıtı gönderilerekte ulaşılabilir.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| id | Integer | Belirtilen ID ile Dekont Başlığı getirmektedir. |
### Method: GET
>```
>{{BaseUrl}}/api/Dekont/Baslik?id=286
>```
### Query Params

|Param|value|
|---|---|
|id|286|


### Response: 200
```json
{
    "Model": {
        "DekontID": 277,
        "Tarih": "2023-05-10T00:00:00",
        "BelgeNo": "0000000000001004",
        "RefBelgeNo": "0000000000001004",
        "Vade": "2023-03-22T00:00:00",
        "Tutar": 169.92,
        "Seviye": 255,
        "Durum": false,
        "Aciklama": "Alınan Sipariş İlk Müşterim",
        "OnayDurum": 0,
        "OlsTar": "2023-05-11T17:15:46.59",
        "DgsTar": "2023-05-11T17:17:28.847",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 10013,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": 1,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Dekont Başlıkları Getir
Bu uç nokta ile kayıtlı olan tüm dekontların filtrelenerek listesi alınabilir.
### Method: GET
>```
>{{BaseUrl}}/api/Dekont/Basliklar?BelgeNo=0000000000000111
>```
### Query Params

|Param|value|
|---|---|
|BelgeNo|0000000000000111|


### Response: 200
```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 2,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 2
    },
    "Model": [
        {
            "DekontID": 121,
            "Tarih": "2023-03-22T00:00:00",
            "BelgeNo": "0000000000000111",
            "RefBelgeNo": null,
            "Vade": "2023-03-22T00:00:00",
            "Tutar": 0,
            "Seviye": 0,
            "Durum": true,
            "Aciklama": "Alınan Sipariş İlk Müşterim",
            "OnayDurum": 1,
            "OlsTar": "2023-04-28T09:26:43.673",
            "DgsTar": "2023-04-28T09:26:43.82",
            "YedekN1": null,
            "YedekN2": null,
            "YedekN3": null,
            "YedekC1": null,
            "YedekC2": null,
            "YedekC3": null,
            "YedekI1": null,
            "YedekI2": null,
            "YedekI3": null,
            "RefTeslimTarihi": null,
            "Kapali": false,
            "eFatura": false,
            "eFaturaUUID": null,
            "eFaturaProfilID": null,
            "eFaturaTipID": null,
            "eFaturaDurumID": null,
            "eFaturaTurID": null,
            "eArsivInternetSatisSablon": null,
            "MagazaSiparisID": null,
            "Etiket1ID": null,
            "Etiket2ID": null,
            "Etiket3ID": null,
            "Etiket4ID": null,
            "Etiket5ID": null,
            "KopyaKaynakID": null,
            "SubeID": 0,
            "SirketID": 0,
            "Sube2ID": null,
            "TipID": 10013,
            "TipAltID": null,
            "AciklamalarID": null,
            "OlsID": 2,
            "DgsID": 2,
            "RefSozlesmeID": null,
            "RefDepoID": null,
            "RefKDVDahil": null,
            "RefProjeID": null,
            "RefPlasiyerID": null,
            "RefDepo2ID": null,
            "RefIthalatIhracatID": null,
            "GecerlilikTarihi": null,
            "KartAdi": null,
            "KalemTekDovizID": null,
            "KalemCokDovizID": null,
            "KalemTekDovizKuru": null,
            "KalemCokDovizKuru": null
        },
        {
            "DekontID": 246,
            "Tarih": "2024-06-22T00:00:00",
            "BelgeNo": "0000000000000111",
            "RefBelgeNo": null,
            "Vade": "2023-03-22T00:00:00",
            "Tutar": 0,
            "Seviye": 0,
            "Durum": false,
            "Aciklama": null,
            "OnayDurum": 0,
            "OlsTar": "2023-05-04T11:45:22.107",
            "DgsTar": "2023-05-04T11:45:22.107",
            "YedekN1": null,
            "YedekN2": null,
            "YedekN3": null,
            "YedekC1": null,
            "YedekC2": null,
            "YedekC3": null,
            "YedekI1": null,
            "YedekI2": null,
            "YedekI3": null,
            "RefTeslimTarihi": null,
            "Kapali": false,
            "eFatura": false,
            "eFaturaUUID": null,
            "eFaturaProfilID": null,
            "eFaturaTipID": null,
            "eFaturaDurumID": null,
            "eFaturaTurID": null,
            "eArsivInternetSatisSablon": null,
            "MagazaSiparisID": null,
            "Etiket1ID": null,
            "Etiket2ID": null,
            "Etiket3ID": null,
            "Etiket4ID": null,
            "Etiket5ID": null,
            "KopyaKaynakID": null,
            "SubeID": 0,
            "SirketID": 0,
            "Sube2ID": null,
            "TipID": 1021,
            "TipAltID": null,
            "AciklamalarID": null,
            "OlsID": 2,
            "DgsID": 2,
            "RefSozlesmeID": null,
            "RefDepoID": null,
            "RefKDVDahil": null,
            "RefProjeID": null,
            "RefPlasiyerID": null,
            "RefDepo2ID": null,
            "RefIthalatIhracatID": null,
            "GecerlilikTarihi": null,
            "KartAdi": null,
            "KalemTekDovizID": null,
            "KalemCokDovizID": null,
            "KalemTekDovizKuru": null,
            "KalemCokDovizKuru": null
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Dekont KalemTek  Getir
Bu uç nokta ile kayıtlı olan Dekontun KalemTek bilgisi alınabilir. Nerdeyse tüm dekont tiplerinin vardır. Eğer yoksa boş sonuç döndürür.

### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| DekontID | Integer | Belirtilen ID ile Dekont Başlığı getirmektedir. |
### Method: GET
>```
>{{BaseUrl}}/api/Dekont/KalemTek?DekontID=277
>```
### Query Params

|Param|value|
|---|---|
|DekontID|277|


### Response: 200
```json
{
    "Model": {
        "KalemTipi": 6,
        "Cari": null,
        "Stok": null,
        "Banka": null,
        "Kasa": null,
        "CekSenet": null,
        "SiparisCari": {
            "CariAdresID": null,
            "CariDetayID": null,
            "MuhtelifCariAdi": null,
            "MuhtelifVergiNo": null,
            "MuhtelifVergiDairesi": null,
            "MuhtelifAdres": null,
            "MuhtelifTel": null,
            "CariBankaID": null,
            "BABSTutar": 0,
            "BeklenenTahsilatOdemeID": null
        },
        "SiparisStok": null,
        "HareketID": 128,
        "DekontID": 277,
        "SubeID": 1,
        "SirketID": 1,
        "TipID": 10013,
        "YevmiyeFisHareketID": null,
        "KartID": 4,
        "Tarih": "2023-05-10T00:00:00",
        "Vade": "2023-03-22T00:00:00",
        "BA": "B",
        "Tutar": 169.92,
        "Miktar": 0,
        "DovizID": 1,
        "TutarDvz": 0,
        "SozlesmeID": null,
        "ProjeID": null,
        "PlasiyerID": null,
        "Durum": false,
        "Aciklama": "Sipariş Başlık Modeli Ekleme deneme",
        "AciklamalarID": null,
        "OnayDurum": 0,
        "OlsID": 2,
        "OlsTar": "2023-05-11T17:15:46.747",
        "DgsID": 2,
        "DgsTar": "2023-05-11T17:17:28.72",
        "YedekD1": null,
        "YedekD2": null,
        "YedekD3": null,
        "YedekS1": null,
        "YedekS2": null,
        "YedekS3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "KartAdi": "İlk Müşterim"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Dekont Kalemler Getir
Bu uç nokta ile kayıtlı olan Dekontunkalemleri okunabilir.
### Method: GET
>```
>{{BaseUrl}}/api/Dekont/Kalemler/?DekontID=303
>```
### Query Params

|Param|value|
|---|---|
|DekontID|303|


### Response: 200
```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 5,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 5
    },
    "Model": [
        {
            "KalemTipi": 7,
            "Cari": null,
            "Stok": null,
            "Banka": null,
            "Kasa": null,
            "CekSenet": null,
            "SiparisCari": null,
            "SiparisStok": {
                "BrmFiyatN": 6,
                "BrmFiyatB": 6,
                "BrmFiyatTipi": 0,
                "BrutBirimFiyatManuelAtansin": false,
                "VergiAltID": null,
                "VergiOran": 0,
                "StokDetayID": null,
                "DepoID": 1,
                "CariID": 4,
                "GelirGiderCariID": null,
                "DemirbasID": null,
                "GelirGiderDekontID": null,
                "MasrafMerkeziID": null,
                "OtomatikKalem": null,
                "RafID": null,
                "PromosyonID": null,
                "PaketID": null,
                "KarmaKoliID": null,
                "KarmaKoliAdet": null,
                "IrsaliyeID": null,
                "YuklemeID": null,
                "NakliyeID": null,
                "TeklifHareketID": null,
                "DepoKabulID": null,
                "IskontoTipi": false,
                "IskontoOrani": 0,
                "VadeIskontoOrani": 0,
                "KullaniciIskontoOrani": 0,
                "TeslimTarihi": "2023-03-22T00:00:00",
                "Kapali": false,
                "IsEmriID": null,
                "KarsilamaSekli": null,
                "IthalatIhracatID": null,
                "UstHareketID": null,
                "VergiDetaylari": [
                    {
                        "__TabloID": 3019,
                        "__ProgramID": 3009,
                        "VergiDetayID": 124,
                        "StokHareketID": 233,
                        "VergiID": 1,
                        "VergiAltID": null,
                        "VergiMuafiyetID": null,
                        "Oran": 18,
                        "Tutar": 6.48,
                        "TutarDvz": 0,
                        "Matrah": 36,
                        "MatrahDvz": 0,
                        "BA": "A",
                        "DovizID": 1,
                        "StokHareket": null,
                        "Vergi": null,
                        "VergiAlt": null,
                        "VergiMuafiyet": null,
                        "Doviz": null
                    }
                ]
            },
            "HareketID": 233,
            "DekontID": 277,
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 10013,
            "YevmiyeFisHareketID": null,
            "KartID": 202,
            "Tarih": "2023-05-10T00:00:00",
            "Vade": "2023-03-22T00:00:00",
            "BA": "A",
            "Tutar": 36,
            "Miktar": 6,
            "DovizID": 1,
            "TutarDvz": 0,
            "SozlesmeID": null,
            "ProjeID": null,
            "PlasiyerID": null,
            "Durum": false,
            "Aciklama": "",
            "AciklamalarID": null,
            "OnayDurum": 0,
            "OlsID": 2,
            "OlsTar": "2023-05-11T17:16:22.453",
            "DgsID": 2,
            "DgsTar": "2023-05-11T17:16:22.453",
            "YedekD1": null,
            "YedekD2": null,
            "YedekD3": null,
            "YedekS1": null,
            "YedekS2": null,
            "YedekS3": null,
            "YedekI1": null,
            "YedekI2": null,
            "YedekI3": null,
            "KartAdi": "Otomatik Aktarım Stok Kartı"
        },
        {
            "KalemTipi": 7,
            "Cari": null,
            "Stok": null,
            "Banka": null,
            "Kasa": null,
            "CekSenet": null,
            "SiparisCari": null,
            "SiparisStok": {
                "BrmFiyatN": 6,
                "BrmFiyatB": 6,
                "BrmFiyatTipi": 0,
                "BrutBirimFiyatManuelAtansin": false,
                "VergiAltID": null,
                "VergiOran": 0,
                "StokDetayID": null,
                "DepoID": 1,
                "CariID": 4,
                "GelirGiderCariID": null,
                "DemirbasID": null,
                "GelirGiderDekontID": null,
                "MasrafMerkeziID": null,
                "OtomatikKalem": null,
                "RafID": null,
                "PromosyonID": null,
                "PaketID": null,
                "KarmaKoliID": null,
                "KarmaKoliAdet": null,
                "IrsaliyeID": null,
                "YuklemeID": null,
                "NakliyeID": null,
                "TeklifHareketID": null,
                "DepoKabulID": null,
                "IskontoTipi": false,
                "IskontoOrani": 0,
                "VadeIskontoOrani": 0,
                "KullaniciIskontoOrani": 0,
                "TeslimTarihi": "2023-03-22T00:00:00",
                "Kapali": false,
                "IsEmriID": null,
                "KarsilamaSekli": null,
                "IthalatIhracatID": null,
                "UstHareketID": null,
                "VergiDetaylari": [
                    {
                        "__TabloID": 3019,
                        "__ProgramID": 3009,
                        "VergiDetayID": 125,
                        "StokHareketID": 235,
                        "VergiID": 1,
                        "VergiAltID": null,
                        "VergiMuafiyetID": null,
                        "Oran": 18,
                        "Tutar": 6.48,
                        "TutarDvz": 0,
                        "Matrah": 36,
                        "MatrahDvz": 0,
                        "BA": "A",
                        "DovizID": 1,
                        "StokHareket": null,
                        "Vergi": null,
                        "VergiAlt": null,
                        "VergiMuafiyet": null,
                        "Doviz": null
                    }
                ]
            },
            "HareketID": 235,
            "DekontID": 277,
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 10013,
            "YevmiyeFisHareketID": null,
            "KartID": 202,
            "Tarih": "2023-05-10T00:00:00",
            "Vade": "2023-03-22T00:00:00",
            "BA": "A",
            "Tutar": 36,
            "Miktar": 6,
            "DovizID": 1,
            "TutarDvz": 0,
            "SozlesmeID": null,
            "ProjeID": null,
            "PlasiyerID": null,
            "Durum": false,
            "Aciklama": "",
            "AciklamalarID": null,
            "OnayDurum": 0,
            "OlsID": 2,
            "OlsTar": "2023-05-11T17:16:29.623",
            "DgsID": 2,
            "DgsTar": "2023-05-11T17:16:29.623",
            "YedekD1": null,
            "YedekD2": null,
            "YedekD3": null,
            "YedekS1": null,
            "YedekS2": null,
            "YedekS3": null,
            "YedekI1": null,
            "YedekI2": null,
            "YedekI3": null,
            "KartAdi": "Otomatik Aktarım Stok Kartı"
        },
        {
            "KalemTipi": 7,
            "Cari": null,
            "Stok": null,
            "Banka": null,
            "Kasa": null,
            "CekSenet": null,
            "SiparisCari": null,
            "SiparisStok": {
                "BrmFiyatN": 6,
                "BrmFiyatB": 6,
                "BrmFiyatTipi": 0,
                "BrutBirimFiyatManuelAtansin": false,
                "VergiAltID": null,
                "VergiOran": 0,
                "StokDetayID": null,
                "DepoID": 1,
                "CariID": 4,
                "GelirGiderCariID": null,
                "DemirbasID": null,
                "GelirGiderDekontID": null,
                "MasrafMerkeziID": null,
                "OtomatikKalem": null,
                "RafID": null,
                "PromosyonID": null,
                "PaketID": null,
                "KarmaKoliID": null,
                "KarmaKoliAdet": null,
                "IrsaliyeID": null,
                "YuklemeID": null,
                "NakliyeID": null,
                "TeklifHareketID": null,
                "DepoKabulID": null,
                "IskontoTipi": false,
                "IskontoOrani": 0,
                "VadeIskontoOrani": 0,
                "KullaniciIskontoOrani": 0,
                "TeslimTarihi": "2023-03-22T00:00:00",
                "Kapali": false,
                "IsEmriID": null,
                "KarsilamaSekli": null,
                "IthalatIhracatID": null,
                "UstHareketID": null,
                "VergiDetaylari": [
                    {
                        "__TabloID": 3019,
                        "__ProgramID": 3009,
                        "VergiDetayID": 126,
                        "StokHareketID": 236,
                        "VergiID": 1,
                        "VergiAltID": null,
                        "VergiMuafiyetID": null,
                        "Oran": 18,
                        "Tutar": 6.48,
                        "TutarDvz": 0,
                        "Matrah": 36,
                        "MatrahDvz": 0,
                        "BA": "A",
                        "DovizID": 1,
                        "StokHareket": null,
                        "Vergi": null,
                        "VergiAlt": null,
                        "VergiMuafiyet": null,
                        "Doviz": null
                    }
                ]
            },
            "HareketID": 236,
            "DekontID": 277,
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 10013,
            "YevmiyeFisHareketID": null,
            "KartID": 202,
            "Tarih": "2023-05-10T00:00:00",
            "Vade": "2023-03-22T00:00:00",
            "BA": "A",
            "Tutar": 36,
            "Miktar": 6,
            "DovizID": 1,
            "TutarDvz": 0,
            "SozlesmeID": null,
            "ProjeID": null,
            "PlasiyerID": null,
            "Durum": false,
            "Aciklama": "",
            "AciklamalarID": null,
            "OnayDurum": 0,
            "OlsID": 2,
            "OlsTar": "2023-05-11T17:16:31.623",
            "DgsID": 2,
            "DgsTar": "2023-05-11T17:16:31.623",
            "YedekD1": null,
            "YedekD2": null,
            "YedekD3": null,
            "YedekS1": null,
            "YedekS2": null,
            "YedekS3": null,
            "YedekI1": null,
            "YedekI2": null,
            "YedekI3": null,
            "KartAdi": "Otomatik Aktarım Stok Kartı"
        },
        {
            "KalemTipi": 7,
            "Cari": null,
            "Stok": null,
            "Banka": null,
            "Kasa": null,
            "CekSenet": null,
            "SiparisCari": null,
            "SiparisStok": {
                "BrmFiyatN": 6,
                "BrmFiyatB": 6,
                "BrmFiyatTipi": 0,
                "BrutBirimFiyatManuelAtansin": false,
                "VergiAltID": null,
                "VergiOran": 0,
                "StokDetayID": null,
                "DepoID": 1,
                "CariID": 4,
                "GelirGiderCariID": null,
                "DemirbasID": null,
                "GelirGiderDekontID": null,
                "MasrafMerkeziID": null,
                "OtomatikKalem": null,
                "RafID": null,
                "PromosyonID": null,
                "PaketID": null,
                "KarmaKoliID": null,
                "KarmaKoliAdet": null,
                "IrsaliyeID": null,
                "YuklemeID": null,
                "NakliyeID": null,
                "TeklifHareketID": null,
                "DepoKabulID": null,
                "IskontoTipi": false,
                "IskontoOrani": 0,
                "VadeIskontoOrani": 0,
                "KullaniciIskontoOrani": 0,
                "TeslimTarihi": "2023-03-22T00:00:00",
                "Kapali": false,
                "IsEmriID": null,
                "KarsilamaSekli": null,
                "IthalatIhracatID": null,
                "UstHareketID": null,
                "VergiDetaylari": [
                    {
                        "__TabloID": 3019,
                        "__ProgramID": 3009,
                        "VergiDetayID": 127,
                        "StokHareketID": 237,
                        "VergiID": 1,
                        "VergiAltID": null,
                        "VergiMuafiyetID": null,
                        "Oran": 18,
                        "Tutar": 6.48,
                        "TutarDvz": 0,
                        "Matrah": 36,
                        "MatrahDvz": 0,
                        "BA": "A",
                        "DovizID": 1,
                        "StokHareket": null,
                        "Vergi": null,
                        "VergiAlt": null,
                        "VergiMuafiyet": null,
                        "Doviz": null
                    }
                ]
            },
            "HareketID": 237,
            "DekontID": 277,
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 10013,
            "YevmiyeFisHareketID": null,
            "KartID": 202,
            "Tarih": "2023-05-10T00:00:00",
            "Vade": "2023-03-22T00:00:00",
            "BA": "A",
            "Tutar": 36,
            "Miktar": 6,
            "DovizID": 1,
            "TutarDvz": 0,
            "SozlesmeID": null,
            "ProjeID": null,
            "PlasiyerID": null,
            "Durum": false,
            "Aciklama": "",
            "AciklamalarID": null,
            "OnayDurum": 0,
            "OlsID": 2,
            "OlsTar": "2023-05-11T17:16:32.663",
            "DgsID": 2,
            "DgsTar": "2023-05-11T17:16:32.663",
            "YedekD1": null,
            "YedekD2": null,
            "YedekD3": null,
            "YedekS1": null,
            "YedekS2": null,
            "YedekS3": null,
            "YedekI1": null,
            "YedekI2": null,
            "YedekI3": null,
            "KartAdi": "Otomatik Aktarım Stok Kartı"
        },
        {
            "KalemTipi": 7,
            "Cari": null,
            "Stok": null,
            "Banka": null,
            "Kasa": null,
            "CekSenet": null,
            "SiparisCari": null,
            "SiparisStok": {
                "BrmFiyatN": 6,
                "BrmFiyatB": 6,
                "BrmFiyatTipi": 0,
                "BrutBirimFiyatManuelAtansin": false,
                "VergiAltID": null,
                "VergiOran": 0,
                "StokDetayID": null,
                "DepoID": 1,
                "CariID": 4,
                "GelirGiderCariID": null,
                "DemirbasID": null,
                "GelirGiderDekontID": null,
                "MasrafMerkeziID": null,
                "OtomatikKalem": null,
                "RafID": null,
                "PromosyonID": null,
                "PaketID": null,
                "KarmaKoliID": null,
                "KarmaKoliAdet": null,
                "IrsaliyeID": null,
                "YuklemeID": null,
                "NakliyeID": null,
                "TeklifHareketID": null,
                "DepoKabulID": null,
                "IskontoTipi": false,
                "IskontoOrani": 0,
                "VadeIskontoOrani": 0,
                "KullaniciIskontoOrani": 0,
                "TeslimTarihi": "2023-03-22T00:00:00",
                "Kapali": false,
                "IsEmriID": null,
                "KarsilamaSekli": null,
                "IthalatIhracatID": null,
                "UstHareketID": null,
                "VergiDetaylari": [
                    {
                        "__TabloID": 3019,
                        "__ProgramID": 3009,
                        "VergiDetayID": 128,
                        "StokHareketID": 238,
                        "VergiID": 1,
                        "VergiAltID": null,
                        "VergiMuafiyetID": null,
                        "Oran": 18,
                        "Tutar": 6.48,
                        "TutarDvz": 0,
                        "Matrah": 36,
                        "MatrahDvz": 0,
                        "BA": "A",
                        "DovizID": 1,
                        "StokHareket": null,
                        "Vergi": null,
                        "VergiAlt": null,
                        "VergiMuafiyet": null,
                        "Doviz": null
                    }
                ]
            },
            "HareketID": 238,
            "DekontID": 277,
            "SubeID": 1,
            "SirketID": 1,
            "TipID": 10013,
            "YevmiyeFisHareketID": null,
            "KartID": 202,
            "Tarih": "2023-05-10T00:00:00",
            "Vade": "2023-03-22T00:00:00",
            "BA": "A",
            "Tutar": 36,
            "Miktar": 6,
            "DovizID": 1,
            "TutarDvz": 0,
            "SozlesmeID": null,
            "ProjeID": null,
            "PlasiyerID": null,
            "Durum": false,
            "Aciklama": "",
            "AciklamalarID": null,
            "OnayDurum": 0,
            "OlsID": 2,
            "OlsTar": "2023-05-11T17:42:15.09",
            "DgsID": 2,
            "DgsTar": "2023-05-11T17:42:15.09",
            "YedekD1": null,
            "YedekD2": null,
            "YedekD3": null,
            "YedekS1": null,
            "YedekS2": null,
            "YedekS3": null,
            "YedekI1": null,
            "YedekI2": null,
            "YedekI3": null,
            "KartAdi": "Otomatik Aktarım Stok Kartı"
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Dekont KalemlerOtomatik Getir
### Method: GET
>```
>{{BaseUrl}}/api/Dekont/KalemlerOtomatik?DekontID=93
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|DekontID|93|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Alınan Sipariş Başlık Ekleme
Bu başlık altında Alınan Sipariş hareketinin kaydetme sürecini göreceksiniz. (Tek-Cok) hareketlerinde önce BaslikModel ve KalemTekModel bilgileri ile Başlık kaydedilir. Bu işlem başarılı olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir.

#### BaslikModel

Farklı bir Dekont(Tek-Cok) kaydı oluşturmak istediğinzde örneğin Verilen Sipariş hareketi oluşturmak istediğinizde, BaslikModel'in içinde yer alan TipID parametresini "VerilenSiparis" olarak değiştirmeniz yeterli olacaktır.

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | AlinanSiparis | Dekontun hareket türünü belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi şirkete açılacağını belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi şubeye açılacağını belirler | Evet |
| BelgeNo | String | 2822429117384-AS | Dekontun belge numarasıdır. Uniqe olmak zorundadır. | Evet |
| Tarih | DateTime | 2023-03-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmediği takdirde dekontun tarihi ile aynı değeri alacaktır. | Hayır |
| RefDepoID | Integer | 1 | Alınan siparişe girilen Deponun id'sini belritir. | Hayır |

Yukarıdaki bilgiler Dekont Başlığı oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz BaslikModel'ine bakabilirsiniz.

#### KalemTekModel

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Cari | Alınan Sipariş hareketi Cari üzerinden yapıldığı için KalemTek bilgisinin KalemTipi parametresi Cari olmalıdır. | Evet |
| KartID | Integer | 4920 | Aaro'da tanımlamış olduğunuz cari kartının ID'sidir. | Evet |
| Tutar | Decimal | 100 | Hareketin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. | Hayır |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. | Hayır |
| Aciklama | String | Alınan Sipariş Başlık Modeli Ekleme | Dekont'a ait açıklamadır. | Hayır |

Yukarıdaki bilgiler Dekont KalemTek oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu işlem başarılı olduktan sonra KalemCok bilgisini eklemek için Kalem metodunu kullanacağız.

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "Tarih": "2023-05-10",
        "BelgeNo": "0000000000001005",
        "Vade": "2023-03-22",
        "TipID": 10013, // Alınan sipariş olduğunu belirtir.
        "SirketID": 1,
        "SubeID": 1,
        "RefDepoID":1  //Alınan siparişe girilen Deponun id'sini belirtir.        
    },
    "KalemTek": { //Alınan siparişe girilen cari bilgileri girilmesi için kullanılır.
        "KalemTipi": 6, // Kalem tipine göre belirlenir. Kalem tipi tablosu altında bulabilirsiniz.
        "KartID": 4, //Siparişe girilen cari'nin id'si girilmelidir.
        "DovizID": 1,
        "Aciklama": "Sipariş Başlık Modeli Ekleme deneme"
    }

}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "DekontID": 280,
        "Tarih": "2023-05-10T00:00:00",
        "BelgeNo": "0000000000001005",
        "RefBelgeNo": "0000000000001005",
        "Vade": "2023-03-22T00:00:00",
        "Tutar": 0,
        "Seviye": 255,
        "Durum": false,
        "Aciklama": null,
        "OnayDurum": 0,
        "OlsTar": "2023-05-12T09:13:10.0752629+03:00",
        "DgsTar": "2023-05-12T09:13:10.0752629+03:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 10013,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": 1,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Alınan Sipariş Kalem Ekleme
Başlık kaydetme işlemi başarılı olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanız her kalem için bu metodu çağırmalısınız.

#### KalemCokModel

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | SiparisStok | Alınan Sipariş hareketinde kalemleri ekleyebilmek için KalemTipi parametresi SiparisStok olmalıdır. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydettiğimiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tanımlamış olduğunuz stok kartının ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istediğiniz stoğun kendi birimi cinsinden miktarını belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. | Evet |
| SiparisStok | SiparisStokModel | SiparisStokModel | Dökümanda yer alan SiparisStokModel bilgileriyle oluşturulan model | Evet |

Yukarıdaki bilgiler Dekont KalemCok oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu işlem başarılı olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacağız.

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "KalemTipi": 7,
    "DekontID": 278,
    "KartID": 202,
    "Miktar": 6.000000,
    "Tutar": 36.000000,
    "DovizID": 1,
    "TutarDvz": 0.000000,
    "BA": "A",
    "SiparisStok": {
        "DepoID" : 1,
        "TeslimTarihi" : "2023-03-22",
        "VergiDetaylari": [
            {
                "VergiID": 1,
                "Oran": 18.000000,
                "Tutar": 6.480000,
                "TutarDvz": 0.000000,
                "DovizID": 1,
                "Matrah": 36.000000,
                "MatrahDvz": 0.000000,
                "BA": "A"
            }
        ]
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Alınan Sipariş Başlık Düzeltme
Başlık bilgisinde DekontID'yi set ettikten sorna düzeltme işlemi yapabiliriz

#### BaslikModel

Başlık bilgisini düzeltirken KalemTek bilgisini göndermeniz zorunlu değildir,

#### KalemTekModel

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 Tüm API'de yeni kayıt düzenle anlamına gelmektedir. |

Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Hayır |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=2
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "DekontID":277,
        "Tarih": "2023-06-22",
        "BelgeNo": "00000000001001",
        "Vade": "2023-06-22",
        "TipID": 10013, // Alınan sipariş olduğunu belirtir.
        "SirketID": 1,
        "SubeID": 1,
        "RefDepoID":1  //Alınan siparişe girilen Deponun id'sini belritir.
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "DekontID": 277,
        "Tarih": "2023-06-22T00:00:00",
        "BelgeNo": "00000000001001",
        "RefBelgeNo": "0000000000001004",
        "Vade": "2023-06-22T00:00:00",
        "Tutar": 362.4,
        "Seviye": 255,
        "Durum": true,
        "Aciklama": "Alınan Sipariş İlk Müşterim",
        "OnayDurum": 1,
        "OlsTar": "2023-05-11T17:15:46.59",
        "DgsTar": "2023-05-12T11:24:49.5935228+03:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 10013,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": 1,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Alınan Sipariş Kalem Düzeltme
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra düzeltme işlemi yapabiliriz. Kalem bilgisinin miktarını değiştirip 7 yapalım. Miktar bilgisini güncellediğiniz zaman Tutar bilgisinin de güncellenmesini istiyorsanız, Tutar bigisini de girmeniz gerekmektedir.

> **Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayıt düzenle anlamına gelmektedir. |

> _**Kalem bilgisi düzeltildikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**_
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=2
>```
### Body (**raw**)

```json
{
    "KalemTipi": 7,
    "DekontID": 278,
    "HareketID": 276,
    "KartID": 202,
    "Miktar": 7.000000,
    "Tutar": 42.000000,
    "DovizID": 1,
    "TutarDvz": 0.000000,
    "BA": "A",
    "SiparisStok": {
        "DepoID" : 1,
        "TeslimTarihi" : "2023-03-22",
        "VergiDetaylari": [
            {
                "VergiID": 1,
                "Oran": 18.000000,
                "Tutar": 7.560000,
                "TutarDvz": 0.000000,
                "DovizID": 1,
                "Matrah": 42.000000,
                "MatrahDvz": 0.000000,
                "BA": "A"
            }
        ]
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "KalemTipi": 7,
        "Cari": null,
        "Stok": null,
        "Banka": null,
        "Kasa": null,
        "CekSenet": null,
        "SiparisCari": null,
        "SiparisStok": {
            "BrmFiyatN": 6,
            "BrmFiyatB": 6,
            "BrmFiyatTipi": 0,
            "BrutBirimFiyatManuelAtansin": false,
            "VergiAltID": null,
            "VergiOran": null,
            "StokDetayID": null,
            "DepoID": 1,
            "CariID": 4,
            "GelirGiderCariID": null,
            "DemirbasID": null,
            "GelirGiderDekontID": null,
            "MasrafMerkeziID": null,
            "OtomatikKalem": null,
            "RafID": null,
            "PromosyonID": null,
            "PaketID": null,
            "KarmaKoliID": null,
            "KarmaKoliAdet": null,
            "IrsaliyeID": null,
            "YuklemeID": null,
            "NakliyeID": null,
            "TeklifHareketID": null,
            "DepoKabulID": null,
            "IskontoTipi": false,
            "IskontoOrani": 0,
            "VadeIskontoOrani": 0,
            "KullaniciIskontoOrani": 0,
            "TeslimTarihi": "2023-03-22T00:00:00",
            "Kapali": false,
            "IsEmriID": null,
            "KarsilamaSekli": null,
            "IthalatIhracatID": null,
            "UstHareketID": null,
            "VergiDetaylari": [
                {
                    "__TabloID": 3019,
                    "__ProgramID": 3009,
                    "VergiDetayID": 153,
                    "StokHareketID": 276,
                    "VergiID": 1,
                    "VergiAltID": null,
                    "VergiMuafiyetID": null,
                    "Oran": 18,
                    "Tutar": 7.56,
                    "TutarDvz": 0,
                    "Matrah": 42,
                    "MatrahDvz": 0,
                    "BA": "A",
                    "DovizID": 1,
                    "StokHareket": null,
                    "Vergi": null,
                    "VergiAlt": null,
                    "VergiMuafiyet": null,
                    "Doviz": null
                }
            ]
        },
        "HareketID": 276,
        "DekontID": 278,
        "SubeID": 1,
        "SirketID": 1,
        "TipID": 10013,
        "YevmiyeFisHareketID": null,
        "KartID": 202,
        "Tarih": "2023-05-10T00:00:00",
        "Vade": "2023-03-22T00:00:00",
        "BA": "A",
        "Tutar": 42,
        "Miktar": 7,
        "DovizID": 1,
        "TutarDvz": 0,
        "SozlesmeID": null,
        "ProjeID": null,
        "PlasiyerID": null,
        "Durum": false,
        "Aciklama": null,
        "AciklamalarID": null,
        "OnayDurum": 0,
        "OlsID": 2,
        "OlsTar": "2023-05-12T10:56:51.887",
        "DgsID": 2,
        "DgsTar": "2023-05-12T11:33:17.8180114+03:00",
        "YedekD1": null,
        "YedekD2": null,
        "YedekD3": null,
        "YedekS1": null,
        "YedekS2": null,
        "YedekS3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "KartAdi": "Otomatik Aktarım Stok Kartı"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Alınan Sipariş Başlık Silme
#### BaslikModel

Başlık bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayıt sil anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "DekontID": 278
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "DekontID": 0,
        "Tarih": "0001-01-01T00:00:00",
        "BelgeNo": null,
        "RefBelgeNo": null,
        "Vade": "0001-01-01T00:00:00",
        "Tutar": 0,
        "Seviye": 0,
        "Durum": false,
        "Aciklama": null,
        "OnayDurum": 0,
        "OlsTar": "0001-01-01T00:00:00",
        "DgsTar": "0001-01-01T00:00:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 0,
        "SirketID": 0,
        "Sube2ID": null,
        "TipID": 0,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 0,
        "DgsID": 0,
        "RefSozlesmeID": null,
        "RefDepoID": null,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": null,
        "KalemCokDovizID": null,
        "KalemTekDovizKuru": null,
        "KalemCokDovizKuru": null
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Alınan Sipariş Kalem Silme
Kalem bilgisinin DekontID,KalemTipi ve HareketID'si set edildikten sonra silme işlemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayıt sil anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| KalemCok | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |

> _**Kalem bilgisi silindikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**_
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "HareketID": 286,
    "DekontID": 312,
    "KalemTipi":7
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": null,
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Alınan Sipariş Tevkifatlı  Kalem Ekleme
Başlık kaydetme işlemi başarılı olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanız her kalem için bu metodu çağırmalısınız.

> _**Tevkifatlı kalem bilgisi için vergi alt ID eklenmelidir. Bu Id'nin karşılığı Tevkifat Tip ID'dir. Vergi oranlarını listeyip bu bilgiyi bulabilirsiniz.**_ 
  

#### KalemCokModel

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | SiparisStok | Alınan Sipariş hareketinde kalemleri ekleyebilmek için KalemTipi parametresi SiparisStok olmalıdır. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydettiğimiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tanımlamış olduğunuz stok kartının ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istediğiniz stoğun kendi birimi cinsinden miktarını belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. | Evet |
| SiparisStok | SiparisStokModel | SiparisStokModel | Dökümanda yer alan SiparisStokModel bilgileriyle oluşturulan model | Evet |

Yukarıdaki bilgiler Dekont KalemCok oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu işlem başarılı olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacağız.

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "KalemTipi": 7,
    "DekontID": 277,
    "KartID": 202,
    "Miktar": 6.000000,
    "Tutar": 36.000000,
    "DovizID": 1,
    "TutarDvz": 0.000000,
    "BA": "A",
    "SiparisStok": {
        "DepoID" : 1,
        "TeslimTarihi" : "2023-03-22",
        "VergiDetaylari": [
            {
                "VergiID": 1,
                "Oran": 18.000000,
                "Tutar": 6.480000,
                "TutarDvz": 0.000000,
                "DovizID": 1,
                "Matrah": 36.000000,
                "MatrahDvz": 0.000000,
                "BA": "A"
            },
            {
                "VergiID": 2,
                "VergiAltID": 28, //Tevkifat Tip ID bilgisi girilmelidir. Vergi oranlarını listeyip bu bilgiyi bulabilirsiniz.
                "Oran": 50.000000,
                "Tutar": 3.240000,
                "TutarDvz": 0.000000,
                "Matrah": 6.480000,
                "MatrahDvz": 0.000000,
                "BA": "B"
            }
        ]
    }
}  
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Nakit Tahsilat Ekle
Bu başlık altında Nakit Tahsilat hareketinin kaydetme sürecini göreceksiniz. Bunun için öncelikle BaslikModel, KalemTekModel ve KalemCokModel yapılarımızı oluşturalım.

#### BaslikModel

Farklı bir Dekont(Tek-Tek) kaydı oluşturmak istediğinizde örneğin Nakit Ödeme hareketi oluşturmak istediğinizde, BaslikModel'in içinde yer alan TipID parametresini "NakitOdeme" olarak değiştirmeniz yeterli olacaktır.

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | NakitTahsilat | Dekontun hareket türünü belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi şirkete açılacağını belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi şubeye açılacağını belirler | Evet |
| BelgeNo | String | 2822429117384-NT | Dekontun belge numarasıdır. Uniqe olmak zorundadır. | Evet |
| Tarih | DateTime | 24.09.2021 | Dekont tarihidir. | Evet |
| Vade | DateTime | 24.09.2021 | Deokntun vadesidir. Verilmediği takdirde dekontun tarihi ile aynı değeri alacaktır. | Hayır |
| Aciklama | String | Nakit Tahsilat Başlık Modeli | Dekont'un başlığına ait açıklamadır. | Hayır |

> **Yukarıdaki bilgiler Dekont Başlığı oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz BaslikModel'ine bakabilirsiniz.** 
  

#### KalemTekModel

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Kasa | Nakit Tahsilat hareketi Kasa üzerinden yapıldığı için KalemTek bilgisinin KalemTipi parametresi Kasa olmalıdır. | Evet |
| KartID | Integer | 1 | Aaro'da tanımlamış olduğunuz kasa kartının ID'sidir. | Evet |
| Tutar | Decimal | 1 | Hareketin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. KalemCok bilgisindeki değer ile aynı olmalıdır. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. KalemCok bilgisindeki değer ile aynı olmalıdır. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. KalemCok bilgisindeki değer ile aynı olmalıdır. | Evet |

> **Yukarıdaki bilgiler Dekont KalemTek oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### KalemCokModel

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Cari | Nakit Tahsilat hareketinin diğer tarafı Cari olduğu için KalemTek bilgisinin KalemTipi parametresi Cari olmalıdır. | Evet |
| KartID | Integer | 4920 | Aaro'da tanımlamış olduğunuz cari kartının ID'sidir. | Evet |
| Tutar | Decimal | 100 | Hareketin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. KalemTek bilgisindeki değer ile aynı olmalıdır. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. KalemTek bilgisindeki değer ile aynı olmalıdır. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. KalemTek bilgisindeki değer ile aynı olmalıdır. | Evet |

> **Yukarıdaki bilgiler Dekont KalemCok oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
| KalemCok | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "Tarih":"2023-04-28",
        "BelgeNo":"2822429117384-NT",
        "Vade":"2023-04-28",
        "Aciklama": "Postmandan Nakit Tahsilat",
        "TipID": 5003,
        "SirketID":1,
        "SubeID":1
    },
    // Kasa Bilgileri
    "KalemTek": {
        "KartID":1,
        "KalemTipi" : 4,
        "Tutar" : 12.000000,
        "DovizID":  1,
        "TutarDvz":0.000000
    },
    // Cari Bilgileri
    "KalemCok": {
        "KartID":4,
        "KalemTipi" : 1,
        "Tutar" : 12.000000,
        "DovizID":  1,
        "TutarDvz":0.000000
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "DekontID": 287,
        "Tarih": "2023-04-28T00:00:00",
        "BelgeNo": "2822429117384-NT",
        "RefBelgeNo": "2822429117384-NT",
        "Vade": "2023-04-28T00:00:00",
        "Tutar": 12,
        "Seviye": 255,
        "Durum": true,
        "Aciklama": "Nakit Tahsilat TL Kasa",
        "OnayDurum": 1,
        "OlsTar": "2023-05-15T10:30:50.1149668+03:00",
        "DgsTar": "2023-05-15T10:30:50.6235499+03:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 5003,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": null,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Nakit Tahsilat Düzenle
BaşlıkModel içerisinde DekontID bilgisini set ettikten sonra düzeltme yapabiliriz.

#### BaslikModel

#### KalemTekModel

KalemTek Model deki tutar bilgisini yenileyelim KalemTek icindeki aciklama alanini değiştirelim. Bu alan Dekontun açıklamasıdır.

#### KalemCokModel

KalemCok Model deki tutar bilgisini yenileyelim.

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de kayıt düzenle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
| KalemCok | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?SayfaKayitTipi=2
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "Tarih":"2023-04-28",
        "BelgeNo":"2822429117384-NT",
        "Vade":"2023-04-28",
        "TipID": 5003,
        "SirketID":1,
        "SubeID":1,
        "DekontID":288
    },
    "KalemTek": {
        "KartID":1,
        "KalemTipi" : 4,
        "Tutar" : 18.000000,
        "DovizID":  1,
        "TutarDvz":0.000000,
        "Aciklama": "Postmandan Nakit Tahsilat Düzeltme"
    },
    "KalemCok": {
        "KartID":4,
        "KalemTipi" : 1,
        "Tutar" : 18.000000,
        "DovizID":  1,
        "TutarDvz":0.000000
    }
}
```

### Query Params

|Param|value|
|---|---|
|SayfaKayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "DekontID": 288,
        "Tarih": "2023-04-28T00:00:00",
        "BelgeNo": "2822429117384-NT",
        "RefBelgeNo": "2822429117384-NT",
        "Vade": "2023-04-28T00:00:00",
        "Tutar": 18,
        "Seviye": 255,
        "Durum": true,
        "Aciklama": "Nakit Tahsilat TL Kasa",
        "OnayDurum": 1,
        "OlsTar": "2023-05-15T11:10:11.493",
        "DgsTar": "2023-05-15T11:10:20.1015427+03:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 5003,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": null,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Nakit Tahsilat Sil
BaşlıkModel içerisinde sadece DekontID bilgisini set etmemiz yeterli olacaktır.

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayıt sil anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "DekontID" : 288
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "DekontID": 0,
        "Tarih": "0001-01-01T00:00:00",
        "BelgeNo": null,
        "RefBelgeNo": null,
        "Vade": "0001-01-01T00:00:00",
        "Tutar": 0,
        "Seviye": 0,
        "Durum": false,
        "Aciklama": null,
        "OnayDurum": 0,
        "OlsTar": "0001-01-01T00:00:00",
        "DgsTar": "0001-01-01T00:00:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 0,
        "SirketID": 0,
        "Sube2ID": null,
        "TipID": 0,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 0,
        "DgsID": 0,
        "RefSozlesmeID": null,
        "RefDepoID": null,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": null,
        "KalemCokDovizID": null,
        "KalemTekDovizKuru": null,
        "KalemCokDovizKuru": null
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Satış Faturası Başlık Ekleme
Bu başlık altında Satış faturası hareketinin kaydetme sürecini göreceksiniz. (Tek-Cok) hareketlerinde önce BaslikModel ve KalemTekModel bilgileri ile Başlık kaydedilir. Bu işlem başarılı olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir.

#### BaslikModel

Farklı bir Dekont(Tek-Cok) kaydı oluşturmak istediğinzde örneğin Satış Faturası hareketi oluşturmak istediğinizde, BaslikModel'in içinde yer alan TipID parametresini "Satış Faturası" olarak değiştirmeniz yeterli olacaktır.

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | SatisFaturasi | Dekontun hareket türünü belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi şirkete açılacağını belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi şubeye açılacağını belirler | Evet |
| BelgeNo | String | 2822429117384-AS | Dekontun belge numarasıdır. Uniqe olmak zorundadır. | Evet |
| Tarih | DateTime | 2023-03-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmediği takdirde dekontun tarihi ile aynı değeri alacaktır. | Hayır |
| RefDepoID | Integer | 1 | Satış faturası girilen Deponun id'sini belirtir. | Hayır |

> **Yukarıdaki bilgiler Dekont Başlığı oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz BaslikModel'ine bakabilirsiniz.** 
  

#### KalemTekModel

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Cari | Satış faturası hareketi Cari üzerinden yapıldığı için KalemTek bilgisinin KalemTipi parametresi Cari olmalıdır. | Evet |
| KartID | Integer | 4920 | Aaro'da tanımlamış olduğunuz cari kartının ID'sidir. | Evet |
| Tutar | Decimal | 100 | Hareketin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. | Hayır |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. | Hayır |
| Aciklama | String | Test Satış Faturası | Dekont'a ait açıklamadır. | Hayır |

Yukarıdaki bilgiler Dekont KalemTek oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu işlem başarılı olduktan sonra KalemCok bilgisini eklemek için Kalem metodunu kullanacağız.

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "Tarih": "2023-11-15",
        "BelgeNo": "0000000000001006",
        "Vade": "2023-11-15",
        "TipID": 10005,
        "SirketID": 1,
        "SubeID": 1,
        "RefDepoID":1  //Alınan siparişe girilen Deponun id'sini belirtir.
    },
    "KalemTek": {
        "KalemTipi": 1,
        "KartID": 4,
        "DovizID": 1,
        "Aciklama": "Test Satış Faturası"
    }

}

```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "DekontID": 306,
        "Tarih": "2023-03-22T00:00:00",
        "BelgeNo": "0000000000001005",
        "RefBelgeNo": "0000000000001005",
        "Vade": "2023-03-22T00:00:00",
        "Tutar": 0,
        "Seviye": 255,
        "Durum": false,
        "Aciklama": null,
        "OnayDurum": 0,
        "OlsTar": "2023-05-15T15:17:20.6820968+03:00",
        "DgsTar": "2023-05-15T15:17:20.6820968+03:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 10005,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": 1,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Satış Faturası Kalem Ekleme
Başlık kaydetme işlemi başarılı olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanız her kalem için bu metodu çağırmalısınız.

#### KalemCokModel

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Stok | Satış Faturası hareketinde kalemleri ekleyebilmek için KalemTipi parametresi Stok olmalıdır. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydettiğimiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tanımlamış olduğunuz stok kartının ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istediğiniz stoğun kendi birimi cinsinden miktarını belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. | Evet |
| Stok | StokModel | StokModel | Dökümanda yer alan StokModel bilgileriyle oluşturulan model | Evet |

> **Yukarıdaki bilgiler Dekont KalemCok oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

Bu işlem başarılı olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacağız.

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "KalemTipi": 2,
    "DekontID": 261,
    "KartID": 201,
    "Miktar": 6.000000,
    "Tutar": 36.000000,
    "DovizID": 1,
    "TutarDvz": 0.000000,
    "BA": "A",
    "Stok": {
        "DepoID" : 1,
        "TeslimTarihi" : "2023-03-22",
        "GelirGiderCariID":null,
        "DemirbasID":null,
        "MasrafMerkeziID":null,
        "VergiDetaylari": [
            {
                "VergiID": 1,
                "Oran": 18.000000,
                "Tutar": 6.480000,
                "TutarDvz": 0.000000,
                "DovizID": 1,
                "Matrah": 36.000000,
                "MatrahDvz": 0.000000,
                "BA": "A"
            }
        ]
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "KalemTipi": 2,
        "Cari": null,
        "Stok": {
            "BrmFiyatN": 6,
            "BrmFiyatB": 6,
            "BrmFiyatTipi": 0,
            "BrutBirimFiyatManuelAtansin": false,
            "VergiAltID": null,
            "VergiOran": null,
            "StokDetayID": null,
            "DepoID": 1,
            "CariID": 4,
            "GelirGiderCariID": null,
            "DemirbasID": null,
            "GelirGiderDekontID": null,
            "MasrafMerkeziID": null,
            "OtomatikKalem": null,
            "RafID": null,
            "PromosyonID": null,
            "PaketID": null,
            "KarmaKoliID": null,
            "KarmaKoliAdet": null,
            "IrsaliyeID": null,
            "YuklemeID": null,
            "NakliyeID": null,
            "SiparisHareketID": null,
            "DepoKabulID": null,
            "IskontoTipi": false,
            "IskontoOrani": 0,
            "VadeIskontoOrani": 0,
            "KullaniciIskontoOrani": 0,
            "TransferHareketID": null,
            "IthalatIhracatID": null,
            "UstHareketID": null,
            "GelenEFaturaStokBilgileri": null,
            "VergiDetaylari": [
                {
                    "__TabloID": 3019,
                    "__ProgramID": 3009,
                    "VergiDetayID": 60,
                    "StokHareketID": 110,
                    "VergiID": 1,
                    "VergiAltID": null,
                    "VergiMuafiyetID": null,
                    "Oran": 18,
                    "Tutar": 6.48,
                    "TutarDvz": 0,
                    "Matrah": 36,
                    "MatrahDvz": 0,
                    "BA": "A",
                    "DovizID": 1,
                    "StokHareket": null,
                    "Vergi": null,
                    "VergiAlt": null,
                    "VergiMuafiyet": null,
                    "Doviz": null
                }
            ]
        },
        "Banka": null,
        "Kasa": null,
        "CekSenet": null,
        "SiparisCari": null,
        "SiparisStok": null,
        "HareketID": 110,
        "DekontID": 303,
        "SubeID": 1,
        "SirketID": 1,
        "TipID": 10005,
        "YevmiyeFisHareketID": null,
        "KartID": 202,
        "Tarih": "2023-03-22T00:00:00",
        "Vade": "2023-03-22T00:00:00",
        "BA": "A",
        "Tutar": 36,
        "Miktar": 6,
        "DovizID": 1,
        "TutarDvz": 0,
        "SozlesmeID": null,
        "ProjeID": null,
        "PlasiyerID": null,
        "Durum": false,
        "Aciklama": null,
        "AciklamalarID": null,
        "OnayDurum": 0,
        "OlsID": 2,
        "OlsTar": "2023-05-15T14:48:37.0416135+03:00",
        "DgsID": 2,
        "DgsTar": "2023-05-15T14:48:37.0416135+03:00",
        "YedekD1": null,
        "YedekD2": null,
        "YedekD3": null,
        "YedekS1": null,
        "YedekS2": null,
        "YedekS3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "KartAdi": "Otomatik Aktarım Stok Kartı"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Satış Faturası Başlık Düzeltme
Başlık bilgisinde DekontID'yi set ettikten sorna düzeltme işlemi yapabiliriz

#### BaslikModel

Başlık bilgisini düzeltirken KalemTek bilgisini göndermeniz zorunlu değildir,

#### KalemTekModel

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 Tüm API'de yeni kayıt düzenle anlamına gelmektedir. |

Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Hayır |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=2
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "DekontID":307,
        "Tarih": "2023-03-23",
        "BelgeNo": "0000000000001005",
        "Vade": "2023-03-23",
        "TipID": 10005,
        "SirketID": 1,
        "SubeID": 1,
        "RefDepoID":1  //Alınan siparişe girilen Deponun id'sini belirtir.
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "DekontID": 307,
        "Tarih": "2023-03-23T00:00:00",
        "BelgeNo": "0000000000001005",
        "RefBelgeNo": "0000000000001005",
        "Vade": "2023-03-23T00:00:00",
        "Tutar": 0,
        "Seviye": 255,
        "Durum": true,
        "Aciklama": "Satış Faturası İlk Müşterim",
        "OnayDurum": 1,
        "OlsTar": "2023-05-15T15:19:02.683",
        "DgsTar": "2023-05-15T15:19:11.8718477+03:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 10005,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": 1,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Satış Faturası Kalem Düzeltme
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra düzeltme işlemi yapabiliriz. Kalem bilgisinin miktarını değiştirip 7 yapalım. Miktar bilgisini güncellediğiniz zaman Tutar bilgisinin de güncellenmesini istiyorsanız, Tutar bigisini de girmeniz gerekmektedir.

> **Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayıt düzenle anlamına gelmektedir. |

> _**Kalem bilgisi düzeltildikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**_
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=2
>```
### Body (**raw**)

```json
{
    "KalemTipi": 2,
    "HareketID":116,
    "DekontID": 308,
    "KartID": 202,
    "Miktar": 7.000000,
    "Tutar": 42.000000,
    "DovizID": 1,
    "TutarDvz": 0.000000,
    "BA": "A",
    "Stok": {
        "DepoID" : 1,
        "TeslimTarihi" : "2023-03-22",
        "GelirGiderCariID":null,
        "DemirbasID":null,
        "MasrafMerkeziID":null,
        "VergiDetaylari": [
            {
                "VergiID": 1,
                "Oran": 18.000000,
                "Tutar": 7.560000,
                "TutarDvz": 0.000000,
                "DovizID": 1,
                "Matrah": 42.000000,
                "MatrahDvz": 0.000000,
                "BA": "A"
            }
        ]
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "KalemTipi": 2,
        "Cari": null,
        "Stok": {
            "BrmFiyatN": 6,
            "BrmFiyatB": 6,
            "BrmFiyatTipi": 0,
            "BrutBirimFiyatManuelAtansin": false,
            "VergiAltID": null,
            "VergiOran": null,
            "StokDetayID": null,
            "DepoID": 1,
            "CariID": 4,
            "GelirGiderCariID": null,
            "DemirbasID": null,
            "GelirGiderDekontID": null,
            "MasrafMerkeziID": null,
            "OtomatikKalem": null,
            "RafID": null,
            "PromosyonID": null,
            "PaketID": null,
            "KarmaKoliID": null,
            "KarmaKoliAdet": null,
            "IrsaliyeID": null,
            "YuklemeID": null,
            "NakliyeID": null,
            "SiparisHareketID": null,
            "DepoKabulID": null,
            "IskontoTipi": false,
            "IskontoOrani": 0,
            "VadeIskontoOrani": 0,
            "KullaniciIskontoOrani": 0,
            "TransferHareketID": null,
            "IthalatIhracatID": null,
            "UstHareketID": null,
            "GelenEFaturaStokBilgileri": null,
            "VergiDetaylari": [
                {
                    "__TabloID": 3019,
                    "__ProgramID": 3009,
                    "VergiDetayID": 66,
                    "StokHareketID": 116,
                    "VergiID": 1,
                    "VergiAltID": null,
                    "VergiMuafiyetID": null,
                    "Oran": 18,
                    "Tutar": 7.56,
                    "TutarDvz": 0,
                    "Matrah": 42,
                    "MatrahDvz": 0,
                    "BA": "A",
                    "DovizID": 1,
                    "StokHareket": null,
                    "Vergi": null,
                    "VergiAlt": null,
                    "VergiMuafiyet": null,
                    "Doviz": null
                }
            ]
        },
        "Banka": null,
        "Kasa": null,
        "CekSenet": null,
        "SiparisCari": null,
        "SiparisStok": null,
        "HareketID": 116,
        "DekontID": 308,
        "SubeID": 1,
        "SirketID": 1,
        "TipID": 10005,
        "YevmiyeFisHareketID": 236,
        "KartID": 202,
        "Tarih": "2023-03-22T00:00:00",
        "Vade": "2023-03-22T00:00:00",
        "BA": "A",
        "Tutar": 42,
        "Miktar": 7,
        "DovizID": 1,
        "TutarDvz": 0,
        "SozlesmeID": null,
        "ProjeID": null,
        "PlasiyerID": null,
        "Durum": false,
        "Aciklama": null,
        "AciklamalarID": null,
        "OnayDurum": 0,
        "OlsID": 2,
        "OlsTar": "2023-05-15T15:27:44.953",
        "DgsID": 2,
        "DgsTar": "2023-05-15T15:30:44.1530006+03:00",
        "YedekD1": null,
        "YedekD2": null,
        "YedekD3": null,
        "YedekS1": null,
        "YedekS2": null,
        "YedekS3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "KartAdi": "Otomatik Aktarım Stok Kartı"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Satış Faturası Başlık Silme
#### BaslikModel

Başlık bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayıt sil anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "DekontID": 303
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "DekontID": 0,
        "Tarih": "0001-01-01T00:00:00",
        "BelgeNo": null,
        "RefBelgeNo": null,
        "Vade": "0001-01-01T00:00:00",
        "Tutar": 0,
        "Seviye": 0,
        "Durum": false,
        "Aciklama": null,
        "OnayDurum": 0,
        "OlsTar": "0001-01-01T00:00:00",
        "DgsTar": "0001-01-01T00:00:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 0,
        "SirketID": 0,
        "Sube2ID": null,
        "TipID": 0,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 0,
        "DgsID": 0,
        "RefSozlesmeID": null,
        "RefDepoID": null,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": null,
        "KalemCokDovizID": null,
        "KalemTekDovizKuru": null,
        "KalemCokDovizKuru": null
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Satış Faturası Kalem Silme
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra silme işlemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayıt sil anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| KalemCok | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |

> _**Kalem bilgisi silindikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**_
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "HareketID": 55,
    "DekontID": 87
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": null,
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Karma Transfer Başlık Ekleme
#### BaslikModel

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | KarmaTransfer | Dekontun hareket türünü belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi şirkete açılacağını belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi şubeye açılacağını belirler | Evet |
| BelgeNo | String | 0000000000000011 | Dekontun belge numarasıdır. Uniqe olmak zorundadır. | Evet |
| Tarih | DateTime | 2024-06-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmediği takdirde dekontun tarihi ile aynı değeri alacaktır. | Hayır |
| RefDepoID | Integer | 1 | Karma transfere girilen Deponun id'sini belirtir. | Hayır |

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "Tarih": "2024-06-22",
        "SirketID": 1,
        "SubeID": 1,
        "BelgeNo": "0000000000000011",
        "Vade": "2023-03-22",
        "TipID": 1027,
        "RefDepoID":1  //karma transfere girilen Deponun id'sini belirtir.
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "DekontID": 317,
        "Tarih": "2024-06-22T00:00:00",
        "BelgeNo": "0000000000000011",
        "RefBelgeNo": "0000000000000011",
        "Vade": "2023-03-22T00:00:00",
        "Tutar": 0,
        "Seviye": 255,
        "Durum": false,
        "Aciklama": null,
        "OnayDurum": 0,
        "OlsTar": "2023-05-16T08:47:40.9953191+03:00",
        "DgsTar": "2023-05-16T08:47:40.9953191+03:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 1027,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": 1,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Karma Transfer Kalem Ekle
Başlık kaydetme işlemi başarılı olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanız her kalem için bu metodu çağırmalısınız.

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Stok | Karma transfer hareketinde kalemleri ekleyebilmek için KalemTipi parametresi eklenen tipe göre değişir. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydettiğimiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tanımlamış olduğunuz stok kartının ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istediğiniz stoğun kendi birimi cinsinden miktarını belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. | Evet |
| Stok | StokModel | StokModel | Dökümanda yer alan StokModel bilgileriyle oluşturulan model | Evet |
| Cari | CariModel | CariModel | Dökümanda yer alan CariModelbilgileriyle oluşturulan model |  |
| Banka | BankaModel | BankaModel | Dökümanda yer alan BankaModelbilgileriyle oluşturulan model |  |
| Kasa | KasaModel | KasaModel | Dökümanda yer alan KasaModelbilgileriyle oluşturulan model |  |

> **Yukarıdaki bilgiler Dekont KalemCok oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

Bu işlem başarılı olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacağız.

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "KalemTipi": 2,
            "Stok": {
                "DepoID": 2,
                "GelirGiderCariID":null,
                "DemirbasID":null,
                "MasrafMerkeziID":null,
                "VergiOran":null,
                "VergiDetaylari": []
            },
            "Cari": null,
            "Banka": null,
            "Kasa": null,
            "DekontID": 317,
            "TipID": 1027,
            "KartID": 202,
            "BA": "B",
            "Tutar": 225.000000,
            "Miktar": 5.000000,
            "DovizID": 1,
            "TutarDvz": 0.000000
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "KalemTipi": 2,
        "Cari": null,
        "Stok": {
            "BrmFiyatN": 45,
            "BrmFiyatB": 45,
            "BrmFiyatTipi": 0,
            "BrutBirimFiyatManuelAtansin": false,
            "VergiAltID": null,
            "VergiOran": null,
            "StokDetayID": null,
            "DepoID": 2,
            "CariID": null,
            "GelirGiderCariID": null,
            "DemirbasID": null,
            "GelirGiderDekontID": null,
            "MasrafMerkeziID": null,
            "OtomatikKalem": null,
            "RafID": null,
            "PromosyonID": null,
            "PaketID": null,
            "KarmaKoliID": null,
            "KarmaKoliAdet": null,
            "IrsaliyeID": null,
            "YuklemeID": null,
            "NakliyeID": null,
            "SiparisHareketID": null,
            "DepoKabulID": null,
            "IskontoTipi": false,
            "IskontoOrani": 0,
            "VadeIskontoOrani": 0,
            "KullaniciIskontoOrani": 0,
            "TransferHareketID": null,
            "IthalatIhracatID": null,
            "UstHareketID": null,
            "GelenEFaturaStokBilgileri": null,
            "VergiDetaylari": []
        },
        "Banka": null,
        "Kasa": null,
        "CekSenet": null,
        "SiparisCari": null,
        "SiparisStok": null,
        "HareketID": 151,
        "DekontID": 317,
        "SubeID": 1,
        "SirketID": 1,
        "TipID": 1027,
        "YevmiyeFisHareketID": null,
        "KartID": 202,
        "Tarih": "2024-06-22T00:00:00",
        "Vade": "2023-03-22T00:00:00",
        "BA": "B",
        "Tutar": 225,
        "Miktar": 5,
        "DovizID": 1,
        "TutarDvz": 0,
        "SozlesmeID": null,
        "ProjeID": null,
        "PlasiyerID": null,
        "Durum": false,
        "Aciklama": null,
        "AciklamalarID": null,
        "OnayDurum": 0,
        "OlsID": 2,
        "OlsTar": "2023-05-16T10:53:14.3141911+03:00",
        "DgsID": 2,
        "DgsTar": "2023-05-16T10:53:14.3141911+03:00",
        "YedekD1": null,
        "YedekD2": null,
        "YedekD3": null,
        "YedekS1": null,
        "YedekS2": null,
        "YedekS3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "KartAdi": "Otomatik Aktarım Stok Kartı"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Karma Transfer Başlık Düzeltme
Başlık bilgisinde DekontID'yi set ettikten sorna düzeltme işlemi yapabiliriz

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 Tüm API'de yeni kayıt düzenle anlamına gelmektedir. |

Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=2
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "Tarih": "2024-06-22",
        "SirketID": 1,
        "SubeID": 1,
        "BelgeNo": "0000000000000011",
        "Vade": "2023-03-22",
        "TipID": 1027,
        "RefDepoID":2, //karma transfere girilen Deponun id'sini belirtir.
        "DekontID":317
    }
}

```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "DekontID": 317,
        "Tarih": "2024-06-22T00:00:00",
        "BelgeNo": "0000000000000011",
        "RefBelgeNo": "0000000000000011",
        "Vade": "2023-03-22T00:00:00",
        "Tutar": 480,
        "Seviye": 255,
        "Durum": true,
        "Aciklama": "Karma Transfer Hareketi ",
        "OnayDurum": 1,
        "OlsTar": "2023-05-16T08:47:40.997",
        "DgsTar": "2023-05-16T11:05:23.4942279+03:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 1027,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": 2,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Karma Transfer Kalem Düzenle
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra düzeltme işlemi yapabiliriz.

> **Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayıt düzenle anlamına gelmektedir. |

> _**Kalem bilgisi düzeltildikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**_
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "KalemTipi": 2,
            "Stok": {
                "DepoID": 2,
                "GelirGiderCariID":null,
                "DemirbasID":null,
                "MasrafMerkeziID":null,
                "VergiOran":null,
                "VergiDetaylari": []
            },
            "Cari": null,
            "Banka": null,
            "Kasa": null,            
            "HareketID":143,
            "DekontID": 317,
            "TipID": 1027,
            "KartID": 202,
            "BA": "B",
            "Tutar": 225.000000,
            "Miktar": 5.000000,
            "DovizID": 1,
            "TutarDvz": 0.000000
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "KalemTipi": 2,
        "Cari": null,
        "Stok": {
            "BrmFiyatN": 45,
            "BrmFiyatB": 45,
            "BrmFiyatTipi": 0,
            "BrutBirimFiyatManuelAtansin": false,
            "VergiAltID": null,
            "VergiOran": null,
            "StokDetayID": null,
            "DepoID": 2,
            "CariID": null,
            "GelirGiderCariID": null,
            "DemirbasID": null,
            "GelirGiderDekontID": null,
            "MasrafMerkeziID": null,
            "OtomatikKalem": null,
            "RafID": null,
            "PromosyonID": null,
            "PaketID": null,
            "KarmaKoliID": null,
            "KarmaKoliAdet": null,
            "IrsaliyeID": null,
            "YuklemeID": null,
            "NakliyeID": null,
            "SiparisHareketID": null,
            "DepoKabulID": null,
            "IskontoTipi": false,
            "IskontoOrani": 0,
            "VadeIskontoOrani": 0,
            "KullaniciIskontoOrani": 0,
            "TransferHareketID": null,
            "IthalatIhracatID": null,
            "UstHareketID": null,
            "GelenEFaturaStokBilgileri": null,
            "VergiDetaylari": []
        },
        "Banka": null,
        "Kasa": null,
        "CekSenet": null,
        "SiparisCari": null,
        "SiparisStok": null,
        "HareketID": 143,
        "DekontID": 317,
        "SubeID": 1,
        "SirketID": 1,
        "TipID": 1027,
        "YevmiyeFisHareketID": 247,
        "KartID": 202,
        "Tarih": "2024-06-22T00:00:00",
        "Vade": "2023-03-22T00:00:00",
        "BA": "B",
        "Tutar": 225,
        "Miktar": 5,
        "DovizID": 1,
        "TutarDvz": 0,
        "SozlesmeID": null,
        "ProjeID": null,
        "PlasiyerID": null,
        "Durum": false,
        "Aciklama": null,
        "AciklamalarID": null,
        "OnayDurum": 0,
        "OlsID": 2,
        "OlsTar": "2023-05-16T09:23:30.74",
        "DgsID": 2,
        "DgsTar": "2023-05-16T11:13:52.9089569+03:00",
        "YedekD1": null,
        "YedekD2": null,
        "YedekD3": null,
        "YedekS1": null,
        "YedekS2": null,
        "YedekS3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "KartAdi": "Otomatik Aktarım Stok Kartı"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Karma Transfer  Başlık Silme
#### BaslikModel

Başlık bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayıt sil anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "DekontID": 317
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "DekontID": 0,
        "Tarih": "0001-01-01T00:00:00",
        "BelgeNo": null,
        "RefBelgeNo": null,
        "Vade": "0001-01-01T00:00:00",
        "Tutar": 0,
        "Seviye": 0,
        "Durum": false,
        "Aciklama": null,
        "OnayDurum": 0,
        "OlsTar": "0001-01-01T00:00:00",
        "DgsTar": "0001-01-01T00:00:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 0,
        "SirketID": 0,
        "Sube2ID": null,
        "TipID": 0,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 0,
        "DgsID": 0,
        "RefSozlesmeID": null,
        "RefDepoID": null,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": null,
        "KalemCokDovizID": null,
        "KalemTekDovizKuru": null,
        "KalemCokDovizKuru": null
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Karma Transfer Kalem Sil
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra silme işlemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayıt sil anlamına gelmektedir. |

> _**Kalem bilgisi silindikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**_
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=-1
>```
### Body (**raw**)

```json
{
        "DekontID" : 230,
        "HareketID": 88
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": null,
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Devir Başlık Ekleme
#### BaslikModel

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | Devir | Dekontun hareket türünü belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi şirkete açılacağını belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi şubeye açılacağını belirler | Evet |
| BelgeNo | String | 0000000000000011 | Dekontun belge numarasıdır. Uniqe olmak zorundadır. | Evet |
| Tarih | DateTime | 2024-06-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmediği takdirde dekontun tarihi ile aynı değeri alacaktır. | Hayır |
| RefDepoID | Integer | 1 | Devire girilen Deponun id'sini belirtir. | Hayır |

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "Tarih": "2024-06-22",
        "SirketID": 1,
        "SubeID": 1,
        "BelgeNo": "0000000000000111",
        "Vade": "2023-03-22",
        "TipID": 1021,
        "RefDepoID": 2 //Devire girilen Deponun id'sini belirtir.
    }
}

```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "DekontID": 318,
        "Tarih": "2024-06-22T00:00:00",
        "BelgeNo": "0000000000000111",
        "RefBelgeNo": "0000000000000111",
        "Vade": "2023-03-22T00:00:00",
        "Tutar": 0,
        "Seviye": 255,
        "Durum": false,
        "Aciklama": null,
        "OnayDurum": 0,
        "OlsTar": "2023-05-16T11:30:48.4458039+03:00",
        "DgsTar": "2023-05-16T11:30:48.4458039+03:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 1021,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": 2,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Devir Kalem Ekle
Başlık kaydetme işlemi başarılı olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanız her kalem için bu metodu çağırmalısınız.

| Parametre | Tip | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Stok | Devir hareketinde kalemleri ekleyebilmek için KalemTipi parametresi kalem tipine göre olmalıdır. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydettiğimiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tanımlamış olduğunuz stok kartının ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istediğiniz stoğun kendi birimi cinsinden miktarını belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. | Evet |
| Stok | StokModel | StokModel | Dökümanda yer alan StokModel bilgileriyle oluşturulan model | Evet |
| Cari | CariModel | CariModel | Dökümanda yer alan CariModelbilgileriyle oluşturulan model |  |
| Banka | BankaModel | BankaModel | Dökümanda yer alan BankaModelbilgileriyle oluşturulan model |  |
| Kasa | KasaModel | KasaModel | Dökümanda yer alan KasaModelbilgileriyle oluşturulan model |  |

> **Yukarıdaki bilgiler Dekont KalemCok oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

Bu işlem başarılı olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacağız.

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "KalemTipi": 2,
            "Stok": {
                "DepoID": 2,
                "GelirGiderCariID":null,
                "DemirbasID":null,
                "MasrafMerkeziID":null,
                "VergiOran":null,
                "VergiDetaylari": []
            },
            "Cari": null,
            "Banka": null,
            "Kasa": null,
            "CekSenet": null,
            "DekontID": 322,
            "TipID": 1021,
            "KartID": 202,
            "BA": "B",
            "Tutar": 225.000000,
            "Miktar": 5.000000,
            "DovizID": 1,
            "TutarDvz": 0.000000
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|


### Response: 200
```json
{
    "Model": {
        "KalemTipi": 2,
        "Cari": null,
        "Stok": {
            "BrmFiyatN": 45,
            "BrmFiyatB": 45,
            "BrmFiyatTipi": 0,
            "BrutBirimFiyatManuelAtansin": false,
            "VergiAltID": null,
            "VergiOran": null,
            "StokDetayID": null,
            "DepoID": 2,
            "CariID": null,
            "GelirGiderCariID": null,
            "DemirbasID": null,
            "GelirGiderDekontID": null,
            "MasrafMerkeziID": null,
            "OtomatikKalem": null,
            "RafID": null,
            "PromosyonID": null,
            "PaketID": null,
            "KarmaKoliID": null,
            "KarmaKoliAdet": null,
            "IrsaliyeID": null,
            "YuklemeID": null,
            "NakliyeID": null,
            "SiparisHareketID": null,
            "DepoKabulID": null,
            "IskontoTipi": false,
            "IskontoOrani": 0,
            "VadeIskontoOrani": 0,
            "KullaniciIskontoOrani": 0,
            "TransferHareketID": null,
            "IthalatIhracatID": null,
            "UstHareketID": null,
            "GelenEFaturaStokBilgileri": null,
            "VergiDetaylari": []
        },
        "Banka": null,
        "Kasa": null,
        "CekSenet": null,
        "SiparisCari": null,
        "SiparisStok": null,
        "HareketID": 171,
        "DekontID": 322,
        "SubeID": 1,
        "SirketID": 1,
        "TipID": 1021,
        "YevmiyeFisHareketID": null,
        "KartID": 202,
        "Tarih": "2024-06-22T00:00:00",
        "Vade": "2024-06-22T00:00:00",
        "BA": "B",
        "Tutar": 225,
        "Miktar": 5,
        "DovizID": 1,
        "TutarDvz": 0,
        "SozlesmeID": null,
        "ProjeID": null,
        "PlasiyerID": null,
        "Durum": false,
        "Aciklama": null,
        "AciklamalarID": null,
        "OnayDurum": 0,
        "OlsID": 2,
        "OlsTar": "2023-05-16T13:55:44.3869025+03:00",
        "DgsID": 2,
        "DgsTar": "2023-05-16T13:55:44.3869025+03:00",
        "YedekD1": null,
        "YedekD2": null,
        "YedekD3": null,
        "YedekS1": null,
        "YedekS2": null,
        "YedekS3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "KartAdi": "Otomatik Aktarım Stok Kartı"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Devir Başlık Düzeltme
Başlık bilgisinde DekontID'yi set ettikten sorna düzeltme işlemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Tip | Değer | Tanım |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 Tüm API'de yeni kayıt düzenle anlamına gelmektedir. |

Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=2
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "Tarih": "2024-06-23",
        "SirketID": 1,
        "SubeID": 1,
        "BelgeNo": "0000000000000111",
        "Vade": "2023-03-22",
        "TipID": 1021,
        "RefDepoID": 2 ,//Devire girilen Deponun id'sini belirtir.
        "DekontID":322
    }
}

```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "DekontID": 322,
        "Tarih": "2024-06-23T00:00:00",
        "BelgeNo": "0000000000000111",
        "RefBelgeNo": "0000000000000111",
        "Vade": "2023-03-22T00:00:00",
        "Tutar": 0,
        "Seviye": 255,
        "Durum": true,
        "Aciklama": "Devir ",
        "OnayDurum": 1,
        "OlsTar": "2023-05-16T13:40:59.873",
        "DgsTar": "2023-05-16T14:27:20.3415798+03:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 1,
        "SirketID": 1,
        "Sube2ID": null,
        "TipID": 1021,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 2,
        "DgsID": 2,
        "RefSozlesmeID": null,
        "RefDepoID": 2,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": 1,
        "KalemCokDovizID": 1,
        "KalemTekDovizKuru": 1,
        "KalemCokDovizKuru": 1
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Devir Kalem Düzenle
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra düzeltme işlemi yapabiliriz.

> **Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayıt düzenle anlamına gelmektedir. |

> _**Kalem bilgisi düzeltildikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**_
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "KalemTipi": 2,
            "Stok": {
                "DepoID": 2,
                "GelirGiderCariID":null,
                "DemirbasID":null,
                "MasrafMerkeziID":null,
                "VergiOran":null,
                "VergiDetaylari": []
            },
            "Cari": null,
            "Banka": null,
            "Kasa": null,
            "CekSenet": null,
            "DekontID": 322,
            "TipID": 1021,
            "HareketID":171,
            "KartID": 202,
            "BA": "A",
            "Tutar": 225.000000,
            "Miktar": 5.000000,
            "DovizID": 1,
            "TutarDvz": 0.000000
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|


### Response: 200
```json
{
    "Model": {
        "KalemTipi": 2,
        "Cari": null,
        "Stok": {
            "BrmFiyatN": 45,
            "BrmFiyatB": 45,
            "BrmFiyatTipi": 0,
            "BrutBirimFiyatManuelAtansin": false,
            "VergiAltID": null,
            "VergiOran": null,
            "StokDetayID": null,
            "DepoID": 2,
            "CariID": null,
            "GelirGiderCariID": null,
            "DemirbasID": null,
            "GelirGiderDekontID": null,
            "MasrafMerkeziID": null,
            "OtomatikKalem": null,
            "RafID": null,
            "PromosyonID": null,
            "PaketID": null,
            "KarmaKoliID": null,
            "KarmaKoliAdet": null,
            "IrsaliyeID": null,
            "YuklemeID": null,
            "NakliyeID": null,
            "SiparisHareketID": null,
            "DepoKabulID": null,
            "IskontoTipi": false,
            "IskontoOrani": 0,
            "VadeIskontoOrani": 0,
            "KullaniciIskontoOrani": 0,
            "TransferHareketID": null,
            "IthalatIhracatID": null,
            "UstHareketID": null,
            "GelenEFaturaStokBilgileri": null,
            "VergiDetaylari": []
        },
        "Banka": null,
        "Kasa": null,
        "CekSenet": null,
        "SiparisCari": null,
        "SiparisStok": null,
        "HareketID": 171,
        "DekontID": 322,
        "SubeID": 1,
        "SirketID": 1,
        "TipID": 1021,
        "YevmiyeFisHareketID": 287,
        "KartID": 202,
        "Tarih": "2024-06-23T00:00:00",
        "Vade": "2024-06-22T00:00:00",
        "BA": "A",
        "Tutar": 225,
        "Miktar": 5,
        "DovizID": 1,
        "TutarDvz": 0,
        "SozlesmeID": null,
        "ProjeID": null,
        "PlasiyerID": null,
        "Durum": false,
        "Aciklama": null,
        "AciklamalarID": null,
        "OnayDurum": 1,
        "OlsID": 2,
        "OlsTar": "2023-05-16T13:55:44.387",
        "DgsID": 2,
        "DgsTar": "2023-05-16T14:30:39.4187845+03:00",
        "YedekD1": null,
        "YedekD2": null,
        "YedekD3": null,
        "YedekS1": null,
        "YedekS2": null,
        "YedekS3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "KartAdi": "Otomatik Aktarım Stok Kartı"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Devir Başlık Silme
#### BaslikModel

Başlık bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayıt sil anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer | Tanım | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet |
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Baslik?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "Baslik": {
        "DekontID": 322
    }
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": {
        "DekontID": 0,
        "Tarih": "0001-01-01T00:00:00",
        "BelgeNo": null,
        "RefBelgeNo": null,
        "Vade": "0001-01-01T00:00:00",
        "Tutar": 0,
        "Seviye": 0,
        "Durum": false,
        "Aciklama": null,
        "OnayDurum": 0,
        "OlsTar": "0001-01-01T00:00:00",
        "DgsTar": "0001-01-01T00:00:00",
        "YedekN1": null,
        "YedekN2": null,
        "YedekN3": null,
        "YedekC1": null,
        "YedekC2": null,
        "YedekC3": null,
        "YedekI1": null,
        "YedekI2": null,
        "YedekI3": null,
        "RefTeslimTarihi": null,
        "Kapali": false,
        "eFatura": false,
        "eFaturaUUID": null,
        "eFaturaProfilID": null,
        "eFaturaTipID": null,
        "eFaturaDurumID": null,
        "eFaturaTurID": null,
        "eArsivInternetSatisSablon": null,
        "MagazaSiparisID": null,
        "Etiket1ID": null,
        "Etiket2ID": null,
        "Etiket3ID": null,
        "Etiket4ID": null,
        "Etiket5ID": null,
        "KopyaKaynakID": null,
        "SubeID": 0,
        "SirketID": 0,
        "Sube2ID": null,
        "TipID": 0,
        "TipAltID": null,
        "AciklamalarID": null,
        "OlsID": 0,
        "DgsID": 0,
        "RefSozlesmeID": null,
        "RefDepoID": null,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "GecerlilikTarihi": null,
        "KartAdi": null,
        "KalemTekDovizID": null,
        "KalemCokDovizID": null,
        "KalemTekDovizKuru": null,
        "KalemCokDovizKuru": null
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Devir Kalem Sil
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra silme işlemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Değer | Tanım |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayıt sil anlamına gelmektedir. |

> _**Kalem bilgisi silindikten sonra Tamamla metodu çağrılarak Başlık ve kalem bilgisi kaydedilmiş olur.**_
### Method: POST
>```
>{{BaseUrl}}/api/Dekont/Kalem?KayitTipi=-1
>```
### Body (**raw**)

```json
{
        "HareketID": 13,
        "DekontID": 35

}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|


### Response: 200
```json
{
    "Model": null,
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Başvurulacak Tablolar 

# 📁 Collection: StokOzet 


## End-point: Stok Özet Getir
Bu uç nokta ile stoklardaki ürünleri toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.


### Method: GET
>```
>{{baseUrl}}/api/StokOzet
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Rehber 


## End-point: Rehber Secenekler
Yeni bir stok kartı eklemek için
KayitTipi: 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.
### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu Body JSON açıklaması

Parametre | Örnek Değer | Tanım | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen ürünün stok ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır.  | Evet
SubeID | 1 | Stoğun bulunduğu şubenin ID'sidir. | Evet
SirketID | 1 | Stoğun ait olduğu şirketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Stoğun detaylı kodudur. | Evet
StokAdi | "Hırdavat Kapı Kolu Burak Oda Rozetli Saten" | Stoğun gözüken adıdır. | Evet
StokKisaKodu |"HRD.KPKL" | Stoğun genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa koda sahip olması önemlidir. | Evet
StokKisaAdi |"Hırdavat Kapı Kolu" | Stoğun genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa ada sahip olması önemlidir. | Evet
Durum | true | Stok kartının aktif veya pasif olduğunu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Gelir-gider hareketleri gibi işlemler de stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. | Evet
StokMuhasebeID | 201 | Stokların muhasebesebesi farklı şekilde işlenebilir. Stok muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel
Kalinlik | 10.0 | Stok kartının fizikel kalınlığıdır. | Opsiyonel
En | 10.0 | Stok kartının fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kartının fizikel boyudur. | Opsiyonel
Yoğunluk | 3.0 | Stok kartının fizikel yoğunluğudur. | Opsiyonel
Agirlik | 5.0 | Stok kartının fizikel ağırlığıdır. | Opsiyonel
Kod1ID | null | Stok kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel
SablonID | null | Ürün ekleme şablonu varsa girilmelidir. | Opsiyonel

>##### Ürün oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.
### Method: POST
>```
>{{BaseUrl}}/api/StokSayim/post?KayitTipi=1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
    "SubeID": "{{subeID}}",
    "SirketID": "{{sirketID}}",
    "Durum": "{{durum}}",
    "Tarih": "{{bugun}}",
    "DepoID": "{{depoID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Kullanıcılar 


## End-point: Kullanıcıları Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Kullanicilar?KulID=87
>```
### Query Params

|Param|value|
|---|---|
|KulID|87|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Kullanıcı Gruplar 


## End-point: Kullanıcı Grupları Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/KullaniciGruplar
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Yetkiler 


## End-point: Yetkileri Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Yetkiler
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Yetkiler Alt 


## End-point: Yetkiler Alt Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/YetkilerAlt
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Şubeler 


## End-point: Şubeleri Getir
Bütün şubeleri getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Subeler/GetKayit
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Şubeleri Oluştur
Yeni bir şube oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Subeler/Post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "SubeID": 2,
            "SubeKodu": "000010",
            "SubeAdi": "deneme12344",
            "SubeUzunAdi": "deneme123444",
            "SirketID": 5,
            "Adres": null,
            "IlceID": null
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Şubeleri Düzenle
Var olan şubeyi düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Subeler/Post?KayitTipi=2
>```
### Body (**raw**)

```json
        {
            "SubeID": 2,
            "SubeKodu": "000010",
            "SubeAdi": "deneme123441111",
            "SubeUzunAdi": "deneme12344411111",
            "SirketID": 5,
            "Adres": null,
            "IlceID": null
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Şubeleri Sil
Mevcut şubeyi silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Subeler/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "SirketID": 5,
            "SubeID": 2
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Takvim 


## End-point: Takvim Getir
Bütün takvimleri getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Takvim/GetKayit
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Takvimleri Oluştur
Yeni bir takvim oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Takvim/Post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "TakvimKodu": "10",
            "TakvimAdi": "testdeneme",
            "SubeID": 0,
            "SirketID": 0,
            "TipID": 130001,
            "Durum": true
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Takvimleri Düzenle
Var olan takvimi düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Takvim/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
        "TakvimID": 3,
        "TakvimKodu": "10",
        "TakvimAdi": "testdeneme123",
        "SubeID": 0,
        "SirketID": 0,
        "TipID": 130001,
        "Durum": true
    }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Takvimleri Sil
Mevcut takvimi silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Takvim/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
        "TakvimID": 2
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Şirketler 


## End-point: Şirketleri Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Sirketler/GetKayit
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Şirketi Oluştur
Yeni bir şirket oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/Sirketler/Post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "SirketKodu": "000056",
            "SirketAdi": "test",
            "SirketUzunAdi": "test",
            "VergiDairesiID": null,
            "VergiNo": "0000001",
            "SicilNo": null,
            "MersisNo": null,
            "CariID": null,
            "SokakAdi": "kıopklo",
            "BinaAdi": "asaas",
            "BinaNo": "asasas",
            "KapiNo": "asasasa",
            "PostaKodu": null,
            "IlceID": 1,
            "Tel": null,
            "Tel2": null,
            "Tel3": null,
            "Fax": null,
            "Email": null,
            "Web": null,
            "eFaturaAktif": false,
            "eArsivAktif": false,
            "eIrsaliyeAktif": false,
            "eFaturaEntegrator": 0,
            "eFaturaTCVKNo": null,
            "eFaturaSifre": null,
            "eFaturaKullaniciAdi": null,
            "eFaturaGbEtiketi": null,
            "eFaturaPkEtiketi": null,
            "eIrsaliyeGbEtiketi": null,
            "eIrsaliyePkEtiketi": null,
            "eFaturaTestMi": false,
            "ePosta": null,
            "ePostaSifre": null,
            "ePostaHost": null,
            "ePostaPort": null,
            "ePostaSSL": false,
            "OtomatikKirilimliHesapPlani": false
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Şirketi Düzenle
Var olan şirketi düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Sirketler/Post?KayitTipi=2
>```
### Body (**raw**)

```json
        {
            "SirketID": 5,
            "SirketKodu": "000056",
            "SirketAdi": "testdeneme",
            "SirketUzunAdi": "testdeneme",
            "VergiDairesiID": null,
            "VergiNo": "0000001",
            "SicilNo": null,
            "MersisNo": null,
            "CariID": null,
            "SokakAdi": "kıopklo",
            "BinaAdi": "asaas",
            "BinaNo": "asasas",
            "KapiNo": "asasasa",
            "PostaKodu": null,
            "IlceID": 1,
            "Tel": null,
            "Tel2": null,
            "Tel3": null,
            "Fax": null,
            "Email": null,
            "Web": null,
            "eFaturaAktif": false,
            "eArsivAktif": false,
            "eIrsaliyeAktif": false,
            "eFaturaEntegrator": 0,
            "eFaturaTCVKNo": null,
            "eFaturaSifre": null,
            "eFaturaKullaniciAdi": null,
            "eFaturaGbEtiketi": null,
            "eFaturaPkEtiketi": null,
            "eIrsaliyeGbEtiketi": null,
            "eIrsaliyePkEtiketi": null,
            "eFaturaTestMi": false,
            "ePosta": null,
            "ePostaSifre": null,
            "ePostaHost": null,
            "ePostaPort": null,
            "ePostaSSL": false,
            "OtomatikKirilimliHesapPlani": false
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Şirketi Sil
Mevcut şirketi silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/Sirketler/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
            "SirketID": 5
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Sözleşme 


## End-point: Sözleşmeleri Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Sozlesme
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sözleşme Oluştur
Yeni bir cari oluşturmaktadır.

###### Mevcut vergi dairelerini görmek için API dökümanından Vergi Dairesi kısmını inceleyiniz.
### Method: POST
>```
>{{BaseUrl}}/api/Sozlesme/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "SozlesmeKodu": "{{sozlesmeKodu}}",
            "SozlesmeAdi": "{{sozlesmeAdi}}",
            "CariID": "{{sozlesmeCariID}}",
            "Tarih": "{{sozlesmeTarih}}",
            "BA": "{{sozlesmeBA}}",
            "Tutar": "{{sozlesmeTutar}}",
            "TipID": "{{sozlesmeTipID}}",
            "SubeID": "{{subeID}}",
            "SirketID": "{{sirketID}}",
            "Durum": "{{durum}}"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sözleşme Düzenle
Yeni bir cari oluşturmaktadır.

###### Mevcut vergi dairelerini görmek için API dökümanından Vergi Dairesi kısmını inceleyiniz.
### Method: POST
>```
>{{BaseUrl}}/api/Sozlesme/Post?KayitTipi=2
>```
### Body (**raw**)

```json
{
            "SozlesmeID": "{{sozlesmeID}}",
            "SozlesmeKodu": "{{sozlesmeKoduDuzelt}}",
            "SozlesmeAdi": "{{sozlesmeAdiDuzelt}}",
            "CariID": "{{sozlesmeCariIDDuzelt}}",
            "TipID": "{{sozlesmeTipID}}",
            "Tarih": "{{sozlesmeTarihDuzelt}}",
            "BA": "{{sozlesmeBA}}",
            "Tutar": "{{sozlesmeTutarDuzelt}}",
            "SubeID": "{{subeID}}",
            "SirketID": "{{sirketID}}",
            "Durum": "{{durum}}"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Sözleşme Sil
Mevcut cariyi silmektedir

###### Bu işlemin geri dönüşü yoktur. Silmeden önce bu carinin hareketler ve bankalarla ile ilişkisini kesmelisiniz.
### Method: POST
>```
>{{BaseUrl}}/api/Sozlesme/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "SozlesmeID" : "{{sozlesmeID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: İthalat İhracatlar 


## End-point: İthalat-ihracat Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/IthalatIhracat
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Plasiyer 


## End-point: Plasiyerleri Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Plasiyer
>```
### Query Params

|Param|value|
|---|---|
|CariID|4920|
|IlD|6|
|EsnekAramaKisiti|null|
|SayfaSatirSayisi|null|
|AdresID|null|
|OlsID|null|
|DgsID|null|
|Durum|null|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Plasiyer Ekle
### Method: POST
>```
>{{BaseUrl}}/api/Plasiyer/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
"CariID":"{{cariID}}",
"IlceID":"{{ilceID}}",
"AdresAdi":"{{adresAdi}}",
"SokakAdi":"{{sokakAdi}}",
"BinaAdi":"{{binaAdi}}",
"BinaNo":"{{binaNo}}",
"KapiNo":"{{kapiNo}}",
"Tel":"{{tel}}",
"Email":"{{email}}",
"Web":"{{web}}",
"Durum":"{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Plasiyer Düzenle
### Method: POST
>```
>{{BaseUrl}}/api/Plasiyer/post?KayitTipi=2
>```
### Body (**raw**)

```json
{
"AdresID":"{{adresID}}",
"CariID":"{{cariID}}",
"IlceID":"{{ilceID}}",
"AdresAdi":"{{adresAdiDuzelt}}",
"SokakAdi":"{{sokakAdiDuzelt}}",
"BinaAdi":"{{binaAdiDuzelt}}",
"BinaNo":"{{binaNoDuzelt}}",
"KapiNo":"{{kapiNoDuzelt}}",
"Tel":"{{telDuzelt}}",
"Email":"{{emailDuzelt}}",
"Web":"{{webDuzelt}}",
"Durum":"{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Plasiyer Sil
### Method: POST
>```
>{{BaseUrl}}/api/Plasiyer/post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "AdresID":"{{adresID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Proje 


## End-point: Projeleri Getir
Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Proje
>```
### Query Params

|Param|value|
|---|---|
|CariID|4920|
|IlD|6|
|EsnekAramaKisiti|null|
|SayfaSatirSayisi|null|
|AdresID|null|
|OlsID|null|
|DgsID|null|
|Durum|null|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Proje Ekle
### Method: POST
>```
>{{BaseUrl}}/api/Proje/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
"CariID":"{{cariID}}",
"IlceID":"{{ilceID}}",
"AdresAdi":"{{adresAdi}}",
"SokakAdi":"{{sokakAdi}}",
"BinaAdi":"{{binaAdi}}",
"BinaNo":"{{binaNo}}",
"KapiNo":"{{kapiNo}}",
"Tel":"{{tel}}",
"Email":"{{email}}",
"Web":"{{web}}",
"Durum":"{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Proje Düzenle
### Method: POST
>```
>{{BaseUrl}}/api/Proje/post?KayitTipi=2
>```
### Body (**raw**)

```json
{
"AdresID":"{{adresID}}",
"CariID":"{{cariID}}",
"IlceID":"{{ilceID}}",
"AdresAdi":"{{adresAdiDuzelt}}",
"SokakAdi":"{{sokakAdiDuzelt}}",
"BinaAdi":"{{binaAdiDuzelt}}",
"BinaNo":"{{binaNoDuzelt}}",
"KapiNo":"{{kapiNoDuzelt}}",
"Tel":"{{telDuzelt}}",
"Email":"{{emailDuzelt}}",
"Web":"{{webDuzelt}}",
"Durum":"{{durum}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Proje Sil
### Method: POST
>```
>{{BaseUrl}}/api/Proje/post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
    "AdresID":"{{adresID}}"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Masraf Merkezi 


## End-point: Masraf Merkezi Getir
StartFragment

Sistemde kayıtlı olan bütün masraf merkezi kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/MasrafMerkezi/GetKayit
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Masraf Merkezi Ekle
StartFragment

Yeni bir masraf merkezi oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/MasrafMerkezi/post?KayitTipi=1
>```
### Body (**raw**)

```json
        {
            "MasrafMerkeziKodu": "000003",
            "MasrafMerkeziAdi": "abc",
            "SubeID": 1,
            "SirketID": 1,
            "Durum": true,
            "TipID": 155001
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Masraf Merkezi Düzenle
StartFragment

Var olan masraf merkezi düzenlemektedir.
### Method: POST
>```
>{{BaseUrl}}/api/MasrafMerkezi/post?KayitTipi=2
>```
### Body (**raw**)

```json
{
        "MasrafMerkeziID": 5,
        "MasrafMerkeziKodu": "000003",
        "MasrafMerkeziAdi": "deneme",
        "SubeID": 1,
        "SirketID": 1,
        "Durum": true,
        "TipID": 155001
    }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Masraf Merkezi Sil
StartFragment

Mevcut masraf merkezi silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/MasrafMerkezi/post?KayitTipi=-1
>```
### Body (**raw**)

```json
{
        "MasrafMerkeziID": 5
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Sipariş 


## End-point: SiparisListe
### Method: GET
>```
>{{baseUrl}}/api/SipStokHareketleri?IsEmriID=7869
>```
### Query Params

|Param|value|
|---|---|
|DekontID|209005|
|IsEmriID|7869|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Üretim 


## End-point: Recete
Üretim reçete bilgilerini listeleyebildiğiniz kısımdır.
### Method: GET
>```
>{{BaseUrl}}/api/UrRecete
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Recete Operasyon Hammadde
Üretim reçete operasyon hammadde bilgilerini listeleyebildiğiniz kısımdır.
### Method: GET
>```
>{{BaseUrl}}/api/UrReceteOperasyonHammadde
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Recete Operasyon Mamul
Üretim reçete operasyon mamul bilgilerini listeleyebildiğiniz kısımdır.
### Method: GET
>```
>{{BaseUrl}}/api/UrReceteOperasyonMamul
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Üretim Hareketi 


## End-point: UrAkisOperasyonPersonel
Üretim akış operasyon personel bilgilerini listeleyebildiğiniz kısımdır.
### Method: GET
>```
>{{BaseUrl}}/api/UrAkisOperasyonPersonel
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: UrAkisOperasyonMamul
Üretim akış operasyon mamul bilgilerini listeleyebildiğiniz kısımdır.
### Method: GET
>```
>{{BaseUrl}}/api/UrAkisOperasyonMamul
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: UrAkisOperasyonHammadde
Üretim akış operasyon hammadde bilgilerini listeleyebildiğiniz kısımdır.
### Method: GET
>```
>{{BaseUrl}}/api/UrAkisOperasyonHammadde
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Görevler 


## End-point: Görevler
Görev bilgilerini listeleyebildiğiniz kısımdır.
### Method: GET
>```
>{{BaseUrl}}/api/Gorevler
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Görev Kullanicilari
Görev kullanıcı bilgilerini listeleyebildiğiniz kısımdır.
### Method: GET
>```
>{{BaseUrl}}/api/GorevKullanicilari
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Görev Hareketleri
Görev hareket bilgilerini listeleyebildiğiniz kısımdır.
### Method: GET
>```
>{{BaseUrl}}/api/GorevHareketleri
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Görevler Alt
Alt görev bilgilerini listeleyebildiğiniz kısımdır.

Not: Henüz aktif değildir.
### Method: GET
>```
>{{BaseUrl}}/api/GorevlerAlt
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Stok Vergi 


## End-point: Stok Vergi Getir
Sistemde kayıtlı olan bütün stok vergi kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/StokVergi
>```
### Body (**raw**)

```json

```

### Query Params

|Param|value|
|---|---|
|EsnekAramaKisiti||
|SirketID|0|
|SubeID|0|
|StokID|3741|
|SablonID||
|StokMuhasebeID||
|StokVergiID||
|BayiGozuksunMu||
|Kalinlik||
|En||
|Boy||
|Agirlik||
|Yogunluk||
|Durum|true|
|OlsID||
|DgsID||
|OlsTarBas||
|OlsTarBit||
|DgsTarBas||
|DgsTarBit||



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stok Vergi Ekle
StartFragment

Yeni bir stok vergi kartı oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/StokVergi/post?KayitTipi=1
>```
### Body (**raw**)

```json
{
            "StokVergiKodu": "{{stokVergiKodu}}",
            "StoVergiAdi": "{{stokVergiAdi}}",
            "AlisKDVOrani": 1,
            "SatisKDVOrani": 1,
            "TevkifatVergiAltID": null,
            "TevkifatVergiAltKodu": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi1BirimBasiTutar": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi2BirimBasiTutar": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "AlisVergi3BirimBasiTutar": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi1BirimBasiTutar": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi2BirimBasiTutar": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SatisVergi3BirimBasiTutar": null
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stok Vergi Düzenle
Stoktaki bir ürünü düzenlemek içindir.

###### Stok eklemek ile düzenlemek arasındaki fark KayitTipi=2 olmasıdır ve StokID dışındaki parametrelerin zorunlu olmamasıdır.
### Method: POST
>```
>{{BaseUrl}}/api/StokVergi/post?KayitTipi=2
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
            "StokVergiID":"{{stokVergiID}}",
            "StokVergiKodu": "{{stokVergiKodu}}",
            "StoVergiAdi": "{{stokVergiAdi}}",
            "AlisKDVOrani": 1,
            "SatisKDVOrani": 1,
            "TevkifatVergiAltID": null,
            "TevkifatVergiAltKodu": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi1BirimBasiTutar": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi2BirimBasiTutar": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "AlisVergi3BirimBasiTutar": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi1BirimBasiTutar": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi2BirimBasiTutar": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SatisVergi3BirimBasiTutar": null
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Stok Vergi Sil
Stoktaki bir ürünü silmek içindir.

######  Stok silmek ile düzenlemek arasındaki fark KayitTipi=-1 olmasıdır. Stoğu silerken bağlı olduğu bütün fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
### Method: POST
>```
>https://localhost:44346/api/StokVergi/post?KayitTipi=-1
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/json|


### Body (**raw**)

```json
{
//"StokID":"{{stokVergiID}}"
"StokVergiID":"8"
}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|-1|



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Benzerlik 


## End-point: Benzerlik Getir
Sistemde kayıtlı olan bütün Benzerlik kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/UrBenzerlik/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Benzerlik Oluştur
Yeni bir benzerlik oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/UrBenzerlik/Post?KayitTipi=1
>```
### Body (**raw**)

```json
    {
        "SirketID": 0,
        "SubeID": 0,
        "BenzerlikKodu": "000004",
        "BenzerlikAdi": "api test benzerlik",
        "Durum": true,
        "Acikalama": "aciklama",
        "Renk": "#000000",
        "Sekil": 0
    }
```

### Query Params

|Param|value|Description
|---|---|---|
|KayitTipi|1|1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Benzerlik Düzenle
Var olan benzerliği düzenlemeketedir.
### Method: POST
>```
>{{BaseUrl}}/api/UrBenzerlik/Post?KayitTipi=2
>```
### Body (**raw**)

```json
    {
        "BenzerlikID": 6,
        "SirketID": 0,
        "SubeID": 0,
        "BenzerlikKodu": "000004",
        "BenzerlikAdi": "api test benzerlikk",
        "Durum": true,
        "Acikalama": "aciklama",
        "Renk": "#000000",
        "Sekil": 0
    }
```

### Query Params

|Param|value|Description
|---|---|---|
|KayitTipi|2|2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir.



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Benzerlik Sil
Mevcut benzerliği silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/UrBenzerlik/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
    {
        "BenzerlikID": 7
    }
```

### Query Params

|Param|value|Description
|---|---|---|
|KayitTipi|-1|-1 bütün API'de yeni DELETE(sil) anlamına gelmektedir.


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
# 📁 Collection: Operasyon Makine 

## End-point: Operasyon Makine Getir
Sistemde kayıtlı olan bütün Operasyon Makine kartlarının görüntülendiği alandır.
### Method: GET
>```
>{{BaseUrl}}/api/UrOperasyonMakine/GetKayit
>```
### Body (**raw**)

```json

```


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Operasyon Makine Oluştur
Yeni bir Operasyon Makine oluşturmaktadır.
### Method: POST
>```
>{{BaseUrl}}/api/UrOperasyonMakine/Post?KayitTipi=1
>```
### Body (**raw**)

```json
	{
		"OperasyonID": 9,
		"MakineID": 4,
		"Oncelik": 0
	}
```

### Query Params

|Param|value|Description
|---|---|---|
|KayitTipi|1|1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Operasyon Makine Düzenle
Var olan Operasyon Makine yi düzenlemeketedir.
### Method: POST
>```
>{{BaseUrl}}/api/UrOperasyonMakine/Post?KayitTipi=2
>```
### Body (**raw**)

```json
    {
		"OperasyonMakineID": 15,
		"OperasyonID": 7,
		"MakineID": 8,
		"Oncelik": 0
    }
```

### Query Params

|Param|value|Description
|---|---|---|
|KayitTipi|2|2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir.



⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: Operasyon Makine Sil
Mevcut Operasyon Makine yi silmektedir.
### Method: POST
>```
>{{BaseUrl}}/api/UrOperasyonMakine/Post?KayitTipi=-1
>```
### Body (**raw**)

```json
    {
        "OperasyonMakineID": 14
    }
```

### Query Params

|Param|value|Description
|---|---|---|
|KayitTipi|-1|-1 bütün API'de yeni DELETE(sil) anlamına gelmektedir.


⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃

## End-point: New Request
### Method: GET
>```
>undefined
>```

⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃ ⁃
_________________________________________________
Powered By: [postman-to-markdown](https://github.com/bautistaj/postman-to-markdown/)
