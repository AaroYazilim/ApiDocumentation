# Project: Aaro Api
Aaro Yazýlým web API dökümantasyonuna hoþ geldiniz. API aracýlýðýyla Aaro Erp uç noktalarýna eriþim saðlayarak stok, cari veya banka gibi çeþitli kalemler için sorgularda bulunabilirsiniz.

API ile Aaro Web arayüzü ile yapýlan iþlemlerin büyük bir kýsmýný gerçekleþtirebilirsiniz. Üretim modülleri henüz aktif halde deðildir.

Dillere göre ayýrdýðýmýz siyah alanda kod örnekleri görebilirsiniz. Ayný bölgeden dil deðiþimini gerçekleþtirebilirsiniz.

Talepleriniz için lütfen [Github](https://github.com/AaroYazilim) sayfamýzý ziyaret edin.
# ?? Collection: Authentication 


## End-point: Authentication
### Method: POST
>```
>{{BaseUrl}}/Token
>```
### Headers

|Content-Type|Value|
|---|---|
|Content-Type|application/x-www-form-urlencoded|


### ?? Authentication oauth2

|Param|value|Type|
|---|---|---|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Stok 


## End-point: Stoktaki Ürünleri Getir
Bu uç nokta ile stoklardaki ürünleri toplu olarak ya da belirli bir kýsýt ile getirebilirsiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stoktaki Ürünleri Getir Min
Bu uç nokta ile stoklardaki ürünleri toplu olarak ya da belirli bir kýsýt ile getirebilirsiniz.


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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stok Ekle
Yeni bir stok kartý eklemek için  
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

### Sorgu Body JSON açýklamasý

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| StokID | \-1 | Eklenilen ürünün stok ID'sidir. -1 girildiði takdirde rasgele olarak ID atanmaktadýr. | Evet |
| SubeID | 1 | Stoðun bulunduðu þubenin ID'sidir. | Evet |
| SirketID | 1 | Stoðun ait olduðu þirketin ID'sidir. | Evet |
| StokKodu | "HRD.KPKL.00164" | Stoðun detaylý kodudur. | Evet |
| StokAdi | "Hýrdavat Kapý Kolu Burak Oda Rozetli Saten" | Stoðun gözüken adýdýr. | Evet |
| StokKisaKodu | "HRD.KPKL" | Stoðun genel kodudur. Genel kod özel kodlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa koda sahip olmasý önemlidir. | Evet |
| StokKisaAdi | "Hýrdavat Kapý Kolu" | Stoðun genel adýdýr. Genel ad özel adlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa ada sahip olmasý önemlidir. | Evet |
| Durum | true | Stok kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet |
| TipID | 105001 | Aaro'da stok yalnýzca fiziksel bir malý iþaret etmek durumunda deðildir. Gelir-gider hareketleri gibi iþlemler de stok olarak düþünülmektedir dolayýsýyla ne tür bir stok olduðunu belirtmek için TipID bulunmaktadýr. | Evet |
| StokMuhasebeID | 201 | Stoklarýn muhasebesebesi farklý þekilde iþlenebilir. Stok muhasebe ID hakkýnda detaylý bilgi için muhasebe bölümünü inceleyiniz | Evet |
| Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Evet |
| Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel |
| Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel |
| CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel |
| CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel |
| Kalinlik | 10.0 | Stok kartýnýn fizikel kalýnlýðýdýr. | Opsiyonel |
| En | 10.0 | Stok kartýnýn fizikel enidir. | Opsiyonel |
| Boy | 10.0 | Stok kartýnýn fizikel boyudur. | Opsiyonel |
| Yoðunluk | 3.0 | Stok kartýnýn fizikel yoðunluðudur. | Opsiyonel |
| Agirlik | 5.0 | Stok kartýnýn fizikel aðýrlýðýdýr. | Opsiyonel |
| Kod1ID | null | Stok kartlarýný hiyerarþik gruplandýrmak için kullanýlýr. Örnek: Elektronik -> Bilgisayar -> HP | Opsiyonel |
| Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel |
| SablonID | null | Ürün ekleme þablonu varsa girilmelidir. | Opsiyonel |
| TakipYontemi | 0: Normal  <br>1: Lot  <br>2:Seri | Seri, Lot bilgilerinin girilmesi için kullanýlýr. |  |

> &lt;h5 &gt;Ürün oluþtururken döküman altýndaki örnek senaryo üzerinden gidebilirsiniz.&lt;/h5&gt;
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stok Kod Aðacý Toplu Ekle
Yeni bir kod kartý eklemek için  
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

### Sorgu Body JSON açýklamasý

| Parametre | Örnek Deðer | Taným |
| --- | --- | --- |
| SubeID | 1 | Kodun bulunduðu þubenin ID'sidir. |
| SirketID | 1 | Kodun ait olduðu þirketin ID'sidir. |
| Kod1 | "Kod 1 adý" | Kod 1 gözüken adýdýr. |
| TipID | 3001 | Stok kartý olduðunu belirtir. |
| Tip2ID | 105001 | Aaro'da stok yalnýzca fiziksel bir malý iþaret etmek durumunda deðildir. Gelir-gider hareketleri gibi iþlemler de stok olarak düþünülmektedir dolayýsýyla ne tür bir stok olduðunu belirtmek için Tip2ID belirtilmelidir. |

> _**Kartlarda yer alan hiyerarþik sýralamayý saðlayan kod aðacý bölümünde öncelikle kodlarýn oluþturulmasý gerekmektedir. Kod adýný yollayarak oluþturabilirsiniz. Kodlar hiyerarþik olarak oluþturulur. 6 adet kod yapýsý oluþturacaksak Kod 1-> Kod 2-> Kod 3 -> Kod 4 -> Kod 5-> Kod 6 þeklinde ad girmeliyiz. Üst kodlar olmadan alt kodlarý oluþturamazsýnýz.**_ 
  

| Parametre | TipID | Tip2ID |
| --- | --- | --- |
| Banka | 6002 |  |
| Kasa | 5001 |  |
| Cari | 2001 |  |
| Personel | 1401 |  |
| Reçete | 12010 |  |
| Stok | 3001 | 105001 |
| Demirbaþ | 3001 | 105003 |
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
            "Kod1": "kýrtasiye",
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
        "Kod1": "kýrtasiye",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stok Etiket Ekle
Yeni bir etiket kartý eklemek için  
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

### Sorgu Body JSON açýklamasý

| Parametre | Örnek Deðer | Taným |
| --- | --- | --- |
| SubeID | 1 | Etiketin bulunduðu þubenin ID'sidir. |
| SirketID | 1 | Etiketin ait olduðu þirketin ID'sidir. |
| EtiketAdi | "Etiket 1 adý" | Etiket 1 gözüken adýdýr. |
| TipID | 3001 | Stok kartý olduðunu belirtir. |
| Tip2ID | 105001 | Aaro'da stok yalnýzca fiziksel bir malý iþaret etmek durumunda deðildir. Gelir-gider hareketleri gibi iþlemler de stok olarak düþünülmektedir dolayýsýyla ne tür bir stok olduðunu belirtmek için Tip2ID belirtilmelidir. |
| Seviye | 1 | Etiketin seviyesini belirtir. |

> _**Kartlarda yer alan hiyerarþik sýralamayý saðlayan etiket bölümünde öncelikle etiketlerin oluþturulmasý gerekmektedir. etiket adýný yollayarak oluþturabilirsiniz.**_ 
  

| Parametre | TipID | Tip2ID |
| --- | --- | --- |
| Banka | 6002 |  |
| Kasa | 5001 |  |
| Cari | 2001 |  |
| Personel | 1401 |  |
| Reçete | 12010 |  |
| Stok | 3001 | 105001 |
| Demirbaþ | 3001 | 105003 |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stok Kod Aðacý Toplu Listele
Kod aðacýný toplu olarak listeleyebilirsiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stok Düzenle
Stoktaki bir ürünü düzenlemek içindir.

###### Stok eklemek ile düzenlemek arasýndaki fark KayitTipi=2 olmasýdýr ve StokID dýþýndaki parametrelerin zorunlu olmamasýdýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stoktaki Ürünü Sil
Stoktaki bir ürünü silmek içindir.

######  Stok silmek ile düzenlemek arasýndaki fark KayitTipi=-1 olmasýdýr. Stoðu silerken baðlý olduðu bütün fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stok Hareketleri Liste
Bu uç nokta ile belirtilen kýsýtlara göre stok hareketlerini listeleyebilirsiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sipariþ Hareketleri Liste
Bu uç nokta ile belirtilen kýsýtlara göre sipariþ hareketlerini listeleyebilirsiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: StokDepo Miktar Min-Max
Bu uç nokta ile belirtilen kýsýtlara göre stok depo miktar minimum maksimum hareketlerini listeleyebilirsiniz.
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "StokAdi": "Otomatik Aktarým Stok Kartý",
            "EsnekAramaKisiti": "STOKOTO00000001 Otomatik Aktarým Stok Kartý DPM Depom",
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
            "StokAdi": "Otomatik Aktarým Stok Kartý",
            "EsnekAramaKisiti": "STOKOTO00000001 Otomatik Aktarým Stok Kartý GG GelirGider Depo",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: StokDepo Miktar Min-Max Ekle
Yeni bir stok depo miktar min-max kartý eklemek için kullanýlýr.  
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: StokDepo Miktar Min-Max Düzenle
Stok Depo Miktar Min-Max'ý düzenlemek içindir.
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: StokDepo Miktar Min-Max Sil
Stok Depo Miktar Min-Max'ý silmek içindir.
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Seri Lot 


## End-point: Seri Lot Getir
Bu uç nokta ile seri lot bilgilerini toplu olarak ya da belirli bir kýsýt ile getirebilirsiniz.
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "StokAdi": "Otomatik Aktarým Stok Kartý",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "StokAdi": "Ýlk Stok Kartým",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "StokAdi": "Ýlk Stok Kartým",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Seri Lot Ekle
Yeni bir stok kartý eklemek için  
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

### Sorgu Body JSON açýklamasý

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| SubeID | 1 | Seri Lotun bulunduðu þubenin ID'sidir. | Evet |
| SirketID | 1 | Seri Lotun ait olduðu þirketin ID'sidir. | Evet |
| SeriLotKodu | "000001" | Seri Lotun kodudur. | Evet |
| SeriLotAdi | "" | Seri Lotun adýdýr. Boþ string yollanmalýdýr. | Evet |
| Durum | true | Seri lot kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet |
| TipID | 153001 | Seri : 153001  <br>Lot: 153002 | Evet |
| StokID | 231 | Serinin baðlý olduðu stoðun idsini belirtir | Evet |
| SonKullanmaTarihi | null | Seri / Lotun son kullanma tarihini belirtir | Evet |
| IsEmriID | null | Seri Lotun baðlý olduðu iþ emrini belirtir. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Seri Lot Sil
Stoktaki bir ürünü silmek içindir.

######  Stok silmek ile düzenlemek arasýndaki fark KayitTipi=-1 olmasýdýr. Stoðu silerken baðlý olduðu bütün fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Seri Lot Hareketleri Liste
Bu uç nokta ile belirtilen kýsýtlara göre seri lot hareketlerini listeleyebilirsiniz.
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
            "StokID": 202,
            "StokKodu": "STOKOTO00000001",
            "StokAdi": "Otomatik Aktarým Stok Kartý",
            "TipID": 10009,
            "TipKodu": "SIR",
            "TipAdi": "Satýþ Ýrsaliyesi",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
            "StokID": 202,
            "StokKodu": "STOKOTO00000001",
            "StokAdi": "Otomatik Aktarým Stok Kartý",
            "TipID": 10009,
            "TipKodu": "SIR",
            "TipAdi": "Satýþ Ýrsaliyesi",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "Ýlk Stok Kartým",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Arasý Transfer",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "Ýlk Stok Kartým",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Arasý Transfer",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "Ýlk Stok Kartým",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Arasý Transfer",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "Ýlk Stok Kartým",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Arasý Transfer",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Seri Lot Hýzlý Kayýt
### Sorgu Body JSON açýklamasý

**Ön Bilgi**

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| StokHareketID | 202 | Hareketteki stoðun idsini belirtir. | Evet |

**Satýrlar**

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| HareketID | \-1 | Seri lot satýrýnýn id sini belirtir. Yeni bir kayýtsa yollanmasýna gerek yoktur. Düzenleme ya da silme yapýlýyorsa hangi satýr olduðunun yollanmasý gerekmektedir. |  |
| StokRafID | 1 | Raf takibi yapýlýyorsa seçilen rafýn id bilgisini belirtir. |  |
| PaketID | 1 | Paket takibi yapýlýyorsa seçilen rafýn id bilgisini belirtir. |  |
| YeniKodOlustur | 1 ya da 0 | Yeni bir seri/lot oluþturuluyorsa bu bilgi gönderilir. |  |
| SeriLotID | 5 | Seri lotun id sini belirtir. Yeni bir kayýtsa yollanmasýna gerek yoktur. Düzenleme ya da silme yapýlýyorsa hangi satýr olduðunun yollanmasý gerekmektedir. |  |
| SeriLotKodu | 500016 | Düzenlenen seri lotun yeni kodunu belirtir. | Yeni seri lot oluþturulacaksa zorunlu. |
| Miktar | 1.0000 | Seri lot satýrýnýn miktarýný belirtir. |  |
| UrAkisOperasyonAnaMamulSeriLotID | 1 | Üretim hareketinin ana mamulunde tüm hammaddelerin seri lotlarýnýn takibi yapýlacaksa kullanýlýr. |  |
| TransferStokRafID | 1 | Depolar arasý transfer de transfer edilen raf id bilgisini belirtir. | Depolar arasý transfer için zorunlu |
| TransferPaketID | 1 | Depolar arasý transfer de transfer edilen paket id bilgisini belirtir. | Depolar arasý transfer için zorunlu |
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
                "SeriLotKodu": "500011", //Yeni seri lot oluþturulacaksa zorunlu.
                "Miktar": 3.0000,
                "YeniKodOlustur": false,  //Yeni seri lot oluþturulacaksa true olmalý.
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
        "Mesaj": "Seri/Lot tanýmlari ve Hareketleri iþlendi"
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Seri Lot Hýzlý Kayýt Getir
### Sorgu Body JSON açýklamasý

**Ön Bilgi**

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| StokHareketID | 202 | Hareketteki stoðun idsini belirtir. | Evet |
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
            "StokAdi": "Ýlk Stok Kartým",
            "IsEmriUretimIliskiTakibi": false,
            "TakipYontemiKodOnEki": null,
            "StokHareketID": 649,
            "OtomatikSeriLotKoduHazirla": false
        },
        "Satirlar": [
            {
                "HareketID": 385,
                "StokRafID": 8,
                "StokRafKodu": "Temizlik Rafý",
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
                "StokRafKodu": "Temizlik Rafý",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Seri Lot Hareketleri Ekle
Yeni bir seri lot hareketini eklemek için  
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

### Sorgu Body JSON açýklamasý

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| SubeID | 1 | Seri Lot hareketlerinin bulunduðu þubenin ID'sidir. | Evet |
| SirketID | 1 | Seri Lot hareketlerinin ait olduðu þirketin ID'sidir. | Evet |
| Durum | true | Seri lot hareketlerinin aktif veya pasif olduðunu belirlemektedir | Evet |
| SeriLotID | 11 | Harekete baðlý olan seri lotun idsidir. | Evet |
| StokID | 231 | Serinin baðlý olduðu stoðun idsini belirtir | Evet |
| Tarih | 2023-08-23 | Seri / Lot hareketlerinin tarihini belirtir. | Evet |
| IsEmriID | null | Seri Lotun baðlý olduðu iþ emrini belirtir. | Evet |
| BA | A | Hareketin borç mu alacak mý olduðunu belritir | Evet |
| Miktar | 1.000000 | Hareketin miktarýný belirtir. | Evet |
| StokHareketID | 202 | Hareketteki stoðun idsini belirtir. | Evet |
| Aciklama | açýklama | Hareketin açýklamasýný belirtir. | Evet |
| UrAkisOperasyonAnaMamulSeriLotID | 1 |  | Hayýr |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "Ýlk Stok Kartým",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Arasý Transfer",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Raf Getir
Bu uç nokta ile raf bilgilerini toplu olarak ya da belirli bir kýsýt ile getirebilirsiniz.
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
            "StokRafKodu": "Kýrtasiye Rafý",
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
            "StokRafKodu": "Teknoloji Rafý",
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
            "StokRafKodu": "Temizlik Rafý",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Raf Ekle
Yeni bir raf kartý eklemek için  
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

### Sorgu Body JSON açýklamasý

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| StokRafKodu | 02A.02.02 | Rafýn kodudur. | Evet |
| Aciklama | aciklama | Raf iiçin açýklamayý ifade eder.Rafýn adý girilebilir. | Evet |
| Durum | true | Raf kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet |
| DepoID | 1 | Rafýn deposunu belirtir. | Evet |
| KonumX | 1 | Rafýn x konumundaki durumunu belirtir. | Evet |
| KonumY | 1 | Rafýn y konumundaki durumunu belirtir. | Evet |
| KonumZ | 1 | Rafýn z konumundaki durumunu belirtir. | Evet |
| En | 1.000000 | Rafýn enini belirtir. | Evet |
| Boy | 1.000000 | Rafýn boyunu belirtir. | Evet |
| Yükseklik | 1.000000 | Rafýn yüksekliðini belirtir. | Evet |
| EtiketKonum | 0 | Etiketin konumunun alt ya da üst olmasýný belirtir.  <br>Üst:0  <br>Alt:1 | Evet |
| EtiketKonumBasilsin | true | Etiketin konumunun raf çýktýsýna basýlýp basýlmayacaðýný belirtir. | Evet |
| AgirlikKapasitesi | 1.000000 | Rafýn aðýrlýk kapasitesini belirtir. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Raf Düzenle
Raf kartý düzenlemek için  
KayitTipi: 2 Tüm API'de kaydý düzenlemek anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de kaydý düzenlemek anlamýna gelmektedir. |

### Sorgu Body JSON açýklamasý

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| StokRafID | 14 | Düzenlenmek istenen rafý belirtir. | Evet |
| StokRafKodu | 02A.02.02 | Rafýn kodudur. | Evet |
| Aciklama | aciklama | Raf iiçin açýklamayý ifade eder.Rafýn adý girilebilir. | Evet |
| Durum | true | Raf kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet |
| DepoID | 1 | Rafýn deposunu belirtir. | Evet |
| KonumX | 1 | Rafýn x konumundaki durumunu belirtir. | Evet |
| KonumY | 1 | Rafýn y konumundaki durumunu belirtir. | Evet |
| KonumZ | 1 | Rafýn z konumundaki durumunu belirtir. | Evet |
| En | 1.000000 | Rafýn enini belirtir. | Evet |
| Boy | 1.000000 | Rafýn boyunu belirtir. | Evet |
| Yükseklik | 1.000000 | Rafýn yüksekliðini belirtir. | Evet |
| EtiketKonum | 0 | Etiketin konumunun alt ya da üst olmasýný belirtir.  <br>Üst:0  <br>Alt:1 | Evet |
| EtiketKonumBasilsin | true | Etiketin konumunun raf çýktýsýna basýlýp basýlmayacaðýný belirtir. | Evet |
| AgirlikKapasitesi | 1.000000 | Rafýn aðýrlýk kapasitesini belirtir. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Raf Sil
Raf kartýný silmek içindir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Paket Getir
Bu uç nokta ile paket bilgilerini toplu olarak ya da belirli bir kýsýt ile getirebilirsiniz.
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Paket Ekle
Yeni bir paket kartý eklemek için  
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

### Sorgu Body JSON açýklamasý

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| PaketKodu | 000001 | Paketin kodudur. | Evet |
| PaketAdi | paket | Paketin adýný belirtir. Boþ býrakýlabilir. | Evet |
| Durum | true | Paket kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet |
| SubeID | 1 | Paketin bulunduðu þubeyi belirtir. | Evet |
| SirketID | 1 | Paketin bulunduðu þirketi belirtir. | Evet |
| TipID | 156001 | Paketin tip idsini belirtir.  <br>Paket : 156001 | Evet |
| PaketKapCinsID | 1 | Paketin cins id sini belritir. Kutu,Koli vb. | Evet |
| Sira | 0 | Paketin sýrasýný belirtir. | Evet |

### Paket Kap Cins Kodlarý

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
| 9 | CB | Bira kasasý |
| 10 | CH | Sandýk |
| 11 | CI | Teneke kutu |
| 12 | CK | Fýçý |
| 13 | CN | Konteyner |
| 14 | CR | Kasa |
| 15 | DK | Karton kasa |
| 16 | DR | Bidon |
| 17 | EC | Plastik torba |
| 18 | FC | Meyve kasasý |
| 19 | JR | Kavanoz |
| 20 | LV | Liftvan |
| 21 | NE | Ambalajsýz |
| 22 | SA | Çuval |
| 23 | SU | Bavul |
| 24 | TN | Teneke |
| 25 | VG | Dökme gaz |
| 26 | VL | Dökme sývý |
| 27 | VO | Dökme katý |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Paket Düzenle
Paket kartý düzenlemek için  
KayitTipi: 2 Tüm API'de kaydý düzenlemek anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de kaydý düzenlemek anlamýna gelmektedir. |

### Sorgu Body JSON açýklamasý

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| PaketID | 26 | Paketin idsidir. | Evet |
| PaketKodu | 000001 | Paketin kodudur. | Evet |
| PaketAdi | paket | Paketin adýný belirtir. Boþ býrakýlabilir. | Evet |
| Durum | true | Paket kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet |
| SubeID | 1 | Paketin bulunduðu þubeyi belirtir. | Evet |
| SirketID | 1 | Paketin bulunduðu þirketi belirtir. | Evet |
| TipID | 156001 | Paketin tip idsini belirtir.  <br>Paket : 156001 | Evet |
| PaketKapCinsID | 1 | Paketin cins id sini belritir. Kutu,Koli vb. | Evet |
| Sira | 0 | Paketin sýrasýný belirtir. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Paket Sil
Paket kartýný silmek içindir.
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Gelir Gider 


## End-point: Gelir-Gider Kartlarýný Getir
Sistemde kayýtlý olan bütün gelir gider kartlarýnýn görüntülendiði alandýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Gelir Gider Ekle
Yeni bir gelir gider oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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
        "SirketAdi": "Þirket 1",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Gelir Gider Hareketleri Liste
Bu uç nokta ile belirtilen kýsýtlara göre stok hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/GelirGiderHareketleri
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Demirbas 


## End-point: Demirbas Kartlarýný Getir
StartFragment

Sistemde kayýtlý olan bütün demirbaþ kartlarýnýn görüntülendiði alandýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Demirbas Ekle
Yeni bir demirbaþ oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Demirbas Düzenle
Var olan demirbaþý düzenlemektedir.
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
        "SirketAdi": "Þirket 1",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Demirbas Sil
Mevcut demirbaþý silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Demirbas Hareketleri Liste
Bu uç nokta ile belirtilen kýsýtlara göre stok hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/DemirbasHareketleri
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Barkod 


## End-point: Stoktaki Ürünün Bakodunu Getir
Aaro bir ürün için sonsuz sayýda barkodu kabul etmektedir. Dolayýsýyla barkod getir deðil barkodlarý getir þekline çalýþmaktadýr.

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stoktaki Ürüne Barkod Ekle
Yeni bir stok kartý eklemek için
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stoktaki Ürünün Barkodunu Düzenle
Deðiþtirmek istediðiniz barkod için aþaðýdaki yapýyý kullanýnýz.

###### Sadece kayýt tipi 2 olarak deðiþmektedir. BarkodID'si ise 2590 olarak girilerek istenilen barkoda ulaþýlmýþtýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stoktaki Ürünün Barkodunu Sil
Silmek istediðiniz barkod için aþaðýdaki yapýyý kullanýnýz.

###### Sadece kayýt tipi -1 olarak deðiþmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Depo 


## End-point: Depolarý Getir
Sistemde kayýtlý olan bütün depo kartlarýnýn görüntülendiði alandýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Depo Oluþtur
Yeni bir depo oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Depoyu Düzenle
Mevcut bir deponun düzeltilmesi için kullanýlmaktadýr.

######  Depo eklemekten farklý olarak ID eklenmesi gerekmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Depoyu Sil
Mevcut bir deponun silinmesi için kullanýlmaktadýr.

######  Depoyu silmeden önce depoya ait bütün hareketlerin ve stoklar silindiðinden/taþýndýðýndan emin olunuz. Aksi takdirde silme iþlemi gerçekleþmeyecektir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Döviz 


## End-point: Dövizleri Getir
Oluþturulmuþ bütün dövizleri getirmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným | Örnek |
| --- | --- | --- | --- |
| EsnekAramaKisiti | String | Dilediðiniz stringe göre listeleme yapabilirsiniz. Doviz kodunda, Doviz adýnda girilen string'e göre arama yapar. | TL |
| DovizID | Integer | Belirtilen ID'li döviz kartýný getirir. | 1 |
| OlsID | Integer | Oluþturan kiþi ID'sine göre depo kartlarýný getirmektedir. | 1234 |
| DgsID | Integer | Deðiþtiren kiþi ID'sine göre depo kartlarýný getirmektedir. | 1234 |
| OlsTarBas | Datetime | Belirtilen tarihten itibaren oluþturulmuþ depo kartlarýný getirmektedir. | 01.01.2021 |
| OlsTarBit | Datetime | Belirtilen tarihe kadar oluþturulmuþ depo kartlarýný getirmektedir. | 01.01.2021 |
| DgsTarBas | Datetime | Belirtilen tarihten itibaren deðiþtirilmiþ depo kartlarýný getirmektedir. | 01.01.2021 |
| DgsTarBit | Datetime | Belirtilen tarihe kadar deðiþtirilmiþ depo kartlarýný getirmektedir. | 01.01.2021 |
| SayfaSatirSayisi | Integer | Limitli sayýda depo getirmek için kullanýlmaktadýr. | 10 |
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
            "EsnekAramaKisiti": "TRY Türk Lirasý TL ",
            "DovizID": 1,
            "DovizKodu": "TRY",
            "DovizAdi": "Türk Lirasý TL",
            "DovizSembol": "?",
            "YaziylaKurus": "Kuruþ",
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
            "EsnekAramaKisiti": "USD Amerikan Dolarý ",
            "DovizID": 2,
            "DovizKodu": "USD",
            "DovizAdi": "Amerikan Dolarý",
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
            "EsnekAramaKisiti": "GBP Ýngiliz Sterlini ",
            "DovizID": 4,
            "DovizKodu": "GBP",
            "DovizAdi": "Ýngiliz Sterlini",
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
            "EsnekAramaKisiti": "CNY Çin Yuaný ",
            "DovizID": 6,
            "DovizKodu": "CNY",
            "DovizAdi": "Çin Yuaný",
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
            "EsnekAramaKisiti": "XAU Altýn ",
            "DovizID": 8,
            "DovizKodu": "XAU",
            "DovizAdi": "Altýn",
            "DovizSembol": "A",
            "YaziylaKurus": "Gram Altýn",
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
            "EsnekAramaKisiti": "XAG Gümüþ ",
            "DovizID": 9,
            "DovizKodu": "XAG",
            "DovizAdi": "Gümüþ",
            "DovizSembol": "G",
            "YaziylaKurus": "Gram Gümüþ",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Döviz Oluþtur
Yeni bir döviz eklemek için kullanýlmaktadýr.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 (KayitTipi=1 bütün API yapýsýnda ürün kaydet demektir) |

### Sorgu Body Parametreleri

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| DovizID | \-1 | Eklenilen kartýn döviz ID'sidir. -1 girildiði takdirde rasgele olarak ID atanmaktadýr. | Evet |
| DovizKodu | "DPM" | Döviz kodudur. | Evet |
| DovizAdi | "Depom" | Döviz adýdýr. | Evet |
| DovizSembol | "?" | Döviz sembolüdür. | Evet |
| YaziylaKurus | "Kuruþ" | Döviz cinsinin kuruþ için belirttiði addýr. Örn: Kuruþ, Cent | Evet |
| Yaziyla | "TL" | Döviz cinsinin okunuþunun yazý halidir. | Evet |
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
        "DovizSembol": "?",
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
        "DovizSembol": "?",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Döviz Düzenle
Mevcut bir deponun düzeltilmesi için kullanýlmaktadýr.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 2 (KayitTipi=2 bütün API yapýsýnda PUT iþlemine karþýlýk gelmektedir.) |

### Sorgu Body Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| DovizID | Integer | Düzeltmek istediðiniz dövizin ID'si |
| DovizKodu | String | Dövize vereceðiniz koddur. |
| DovizAdi | String | Dövize vereceðiniz ad. |
| DovizSembol | String | Dövize vereceðiniz sembol. |
| YaziylaKurus | String | Dövize vereceðiniz kuruþ okunuþudur. |
| Yaziyla | String | Dövize vereceðiniz okunuþtur. |

> **Döviz eklemekten farklý olarak ID eklenmesi gerekmektedir.**
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
        "DovizSembol": "?",
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
        "DovizSembol": "?",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Döviz Sil
Mevcut döviz bilgilerini silmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 (KayitTipi=-1 bütün API yapýsýnda DELETE iþlemine karþýlýk gelmektedir.) |

### Sorgu Body Parametreleri

Yalnýzca ID ile de silme iþlemini gerçekleþtirebilirsiniz.

| Parametre | Deðer | Taným |
| --- | --- | --- |
| DovizID | Integer | Silmek istediðiniz dövizin ID'si |

> **Dövizi silmeden önce dövizin kullanýldýðý bütün hareketlerin silindiðinden/taþýndýðýndan emin olunuz. Aksi takdirde silme iþlemi gerçekleþmeyecektir.**
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Döviz Kuru 


## End-point: Döviz Kurlarýný Getir
Oluþturulmuþ bütün döviz kur kayýtlarýný getirmektedir.
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
            "DovizAdi": "Amerikan Dolarý",
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
            "DovizAdi": "Ýngiliz Sterlini",
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
            "DovizAdi": "Çin Yuaný",
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
            "DovizAdi": "Altýn",
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
            "DovizAdi": "Gümüþ",
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
            "DovizAdi": "Amerikan Dolarý",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Döviz Kurunu Oluþtur
Yeni bir döviz kuru eklemek için kullanýlmaktadýr.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 (KayitTipi=1 bütün API yapýsýnda ürün kaydet demektir) |

### Sorgu Body Parametreleri

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| DovizID | 2 | Eklenilen döviz kurunun ID'sidir. | Evet |
| Tarih | 2022-05-18 | Döviz kurunun tarihidir. | Hayýr |
| AlisMerkez | 18.566100 |  | Hayýr |
| SatisMerkez | 18.599600 |  | Evet |
| AlisEfektif | 18.553100 |  | Hayýr |
| SatisEfektif | 18.627500 |  | Hayýr |
| AlisSerbest | 18.566100 |  | Hayýr |
| SatisSerbest | 18.599600 |  | Hayýr |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Döviz Kurunu Düzenle
Mevcut bir döviz kurunun düzeltilmesi için kullanýlmaktadýr.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 2 (KayitTipi=2 bütün API yapýsýnda PUT iþlemine karþýlýk gelmektedir.) |

### Sorgu Body Parametreleri

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| DovizID | 2 | Eklenilen döviz kurunun ID'sidir. | Evet |
| Tarih | 2022-05-18 | Döviz kurunun tarihidir. | Hayýr |
| AlisMerkez | 18.566100 |  | Hayýr |
| SatisMerkez | 18.599600 |  | Evet |
| AlisEfektif | 18.553100 |  | Hayýr |
| SatisEfektif | 18.627500 |  | Hayýr |
| AlisSerbest | 18.566100 |  | Hayýr |
| SatisSerbest | 18.599600 |  | Hayýr |

> **Döviz kuru eklemekten farklý olarak ID eklenmesi gerekmektedir.**
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Döviz Kurunu Sil
Mevcut döviz kuru bilgilerini silmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 (KayitTipi=-1 bütün API yapýsýnda DELETE iþlemine karþýlýk gelmektedir.) |

### Sorgu Body Parametreleri

Yalnýzca ID ile de silme iþlemini gerçekleþtirebilirsiniz.

| Parametre | Deðer | Taným |
| --- | --- | --- |
| StrID | Integer | Silmek istediðiniz döviz kurunun ID'si |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Vergi 


## End-point: Vergi Oranlarýný Getir
Bütün vergi oranlarýný ya da istenilen kýsýttaki vergi kalemleri gelmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/StokVergi
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Vergi Oraný Oluþtur
Yeni bir vergi oraný oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Vergi Oranýný Düzenle
Vergi oraný düzenlenmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Vergi Oranýný Sil
Vergi oranýný silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Vergi Daireleri 


## End-point: Vergi Dairelerini Getir
### Method: GET
>```
>{{BaseUrl}}/api/VergiDairesi
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Vergi Dairesi Oluþtur
Yeni bir vergi dairesi oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Vergi Dairesini Sil
Vergi dairesi silinmektedir..

###### Bu iþlemin geri dönüþü yoktur. Silmeden önce bu vergi dairesinin hareketlerini silmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Fiyat Listeleri 


## End-point: Fiyat Listelerini Getir
### Method: GET
>```
>{{BaseUrl}}/api/FiyatListesi
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Fiyat Listesi Oluþtur
Yeni bir fiyat listesi oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Fiyat Listesini Sil
Mevcut fiyat listesini silmektedir


######  Bu iþlemin geri dönüþü yoktur. Silmeden önce bu fiyat listesine baðlý tüm stoklarýn ve hareketlerin liste ile iliþkisini kesmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Fiyat Listesi Satirlar 


## End-point: Fiyat Listesi Satirlar Getir
### Method: GET
>```
>{{BaseUrl}}/api/FiyatListesiSatirlar
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Fiyat Listesi Satir Ekle
Yeni bir fiyat listesi oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Fiyat Listesi Satir Düzenle
Yeni bir fiyat listesi oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Fiyat Listesi Satir Sil
Mevcut fiyat listesini silmektedir


######  Bu iþlemin geri dönüþü yoktur. Silmeden önce bu fiyat listesine baðlý tüm stoklarýn ve hareketlerin liste ile iliþkisini kesmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Cari 


## End-point: Carileri Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
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


### ?? Authentication bearer

|Param|value|Type|
|---|---|---|
|token|5XFY7Iv3TzsSL18gTiZjTlh6AKcr3O1NpS1As4gQysFpgNZJIaczXEqsqdV1tVR2EBzkY_YzaDzgCQP7MEG6Ew34Es7QDsUHtjTylLdpremuJ94RL0TbdlpoBwSyNTRo3lUSqVhIPoC1yqp7pPX9mRhwV2GlofcaAKfui77_s_kJmb1FRtfIhawJNxSxSaV7_Vc0xznJteGcQpy5-Izmvu0iwjjp-S2dOQ-5CuS37DxCpjwCJMD4QUYNNm7NK8Jd59zmsyyK6R2Gd9e2PXfLIfTJtAHQfku7g6Zwmxjpw9n7J_m1ldgfFIzF0k-Y1jq3Df2VTwkd52ZLxhJYH1jSQpKhbpqfaB81JzNV6_SVQcfmH5J1q1HsRcKGV8GxSg1sf5vGa68vfmAit3pPEdtaos0dVGeKpqD96_L1pivgzOUYaWuOxv2FDhxruG1oGuk-4-7T_N_W7U85QvOkpnyyZIYjwLApE3Q_CBs1kq9QdDaJZg-InhMCBUpzZLAhfxsJ|string|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Cari Oluþtur
Yeni bir cari oluþturmaktadýr.

\-Cariye adres, ilgili, risk, ziyaret vb. eklenmek istenirse cari oluþturulduktan sonra ilgili api kýsmýndan eklenmelidir.

###### Mevcut vergi dairelerini görmek için API dökümanýndan Vergi Dairesi kýsmýný inceleyiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Cari Sil
Mevcut cariyi silmektedir

###### Bu iþlemin geri dönüþü yoktur. Silmeden önce bu carinin hareketler ve bankalarla ile iliþkisini kesmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Cari Hareketleri Liste
Bu uç nokta ile belirtilen kýsýtlara göre cari hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/CariHareketleri?CariID=1
>```
### Query Params

|Param|value|
|---|---|
||null|
|CariID|1|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Cari Risk 


## End-point: Cari Riskleri Getir
Sistemde kayýtlý olan bütün cari risk kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/CariRisk/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Cari Risk Oluþtur
Yeni bir cari risk oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Cari Ziyaret 


## End-point: Cari Ziyaretleri Getir
Sistemde kayýtlý olan bütün cari ziyaret kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/CariZiyaret/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Cari Ziyaret Oluþtur
Yeni bir cari ziyaret oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Cari Adresleri 


## End-point: Adresleri Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Adres 


## End-point: Ýlleri Getir
Ýller listesini getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Iller
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ýl Ekle
Ýl ekleme iþlemi için kullanýlmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ýl Düzenle
Ýl bilgilerini düzenlemek için kullanýlmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ýl Sil
Ýl bilgisini silmek için kullanýlmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ýlçeleri Getir
Ýlçeler listesini getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Ilceler
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ýlçe Ekle
Ýlçe ekleme iþlemi için kullanýlmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ýlçe Düzenle
Ýlçe bilgilerini düzenlemek için kullanýlmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ýlçe Sil
Ýlçe bilgisini silmek için kullanýlmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ülkeleri Getir
Ülkeler listesini getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Ulkeler
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ülke Ekle
Ülke ekleme iþlemi için kullanýlmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ülke Düzenle
Ülke bilgilerini düzenlemek için kullanýlmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ülke Sil
Ülke bilgisini silmek için kullanýlmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Cari Ýlgilileri 


## End-point: Ýlgilileri Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/CariIlgili?CariID=10233
>```
### Query Params

|Param|value|
|---|---|
|CariID|10233|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ýlgili Ekle
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ýligli Düzenle
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Ýlgili Sil
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Cari Banka 


## End-point: Bankalarý Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/CariBanka?EsnekAramaKisiti&CariID=4920
>```
### Query Params

|Param|value|
|---|---|
|EsnekAramaKisiti|null|
|CariID|4920|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Kasa 


## End-point: Kasalarý Getir
Sistemde kayýtlý olan bütün kasa kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/Kasa/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Kasa Oluþtur
Yeni bir kasa oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Kasa Düzenle
Var olan kasayý düzenlemektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Kasa Sil
Mevcut kasayý silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Kasa Hareketleri Liste
Bu uç nokta ile belirtilen kýsýtlara göre kasa hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/KasaHareketleri?CariID=1
>```
### Query Params

|Param|value|
|---|---|
|CariID|1|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Banka Hesap 


## End-point: Banka Hesaplarý Getir
Sistemde kayýtlý olan bütün banka hesap kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/BankaHesap/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Hesap Oluþtur
StartFragment

Yeni bir banka hesap oluþturmaktadýr.
### Method: POST
>```
>{{BaseUrl}}/api/BankaHesap/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
        "BankaSubeID": 1,
        "HesapKodu": "000000000000100",
        "HesapAdi": "Deneme Banka Kartý",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Hesap Düzenle
StartFragment

Var olan banka hesabýný düzenlemektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Hesap Sil
StartFragment

Mevcut banka hesabýný silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Hareketleri Liste
Bu uç nokta ile belirtilen kýsýtlara göre stok hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/BankaHareketleri
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Banka 


## End-point: Banka Getir
Sistemde kayýtlý olan bütün banka kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/Banka/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Oluþtur
Yeni bir banka oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Düzenle
Var olan bankayý düzenlemektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Sil
Mevcut bankayý silmektedir.

###### Bu iþlemin geri dönüþü yoktur. Silmeden önce bu bu bankanýn hareketler ve bankalarla ile iliþkisini kesmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Hareket Türleri Alt 


## End-point: Hareket Türleri Alt Getir
Sistemde kayýtlý olan bütün hareket türleri alt kartlarýnýn görüntülendiði alandýr.
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
            "SubeAdi": "Þubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "Þirketim",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Hareket Türleri Alt Oluþtur
Yeni bir hareket türleri altý oluþturmaktadýr.
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Hareket Türleri Alt Düzenle
Var olan hareket türleri altý düzenlemektedir.
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Hareket Türleri Alt Sil
Mevcut hareket türleri altý silmektedir.
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Açýklamalar 


## End-point: Aciklamalar Getir
Sistemde kayýtlý olan bütün açýklama kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/Aciklamalar/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Aciklamalar Oluþtur
Yeni bir açýklama oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Aciklamalar Düzenle
Var olan açýklamayý düzenlemektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Aciklamalar Sil
Mevcut açýklamayý silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: PerGirisCikis 


## End-point: PerGirisCikis Getir
Sistemde kayýtlý olan bütün personel giriþ çýkýþ kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/PerGirisCikis/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: PerGirisCikis Oluþtur
Yeni bir personel giriþ çýkýþ oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: PerGirisCikis Düzenle
Var olan personel giriþ çýkýþýný düzenlemektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: PerGirisCikis Sil
Mevcut personel giriþ çýkýþý silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: TakvimStr 


## End-point: TakvimStr Getir
Sistemde kayýtlý olan bütün takvim satýr kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/TakvimStr/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: TakvimStr Oluþtur
Yeni bir takvim satýrý oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: TakvimStr Düzenle
Var olan takvim satýrýný düzenlemektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: TakvimStr Sil
Mevcut takvim satýrýný silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Cek Senet 


## End-point: Cek Senet Getir
Sistemde kayýtlý olan bütün çek senet kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>https://localhost:44346/api/CekSenet/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Cek Senet Oluþtur
Yeni bir çek senet oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Makine 


## End-point: Makine Getir
Sistemde kayýtlý olan bütün makine kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/urMakine/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Makine Oluþtur
Yeni bir makine oluþturmaktadýr.
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
            "Aciklama": "Hýzlý Reçeetelerde Kullanýlan makine"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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
            "Aciklama": "Hýzlý Reçeetelerde Kullanýlan makine"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Makine Arýza 


## End-point: Makine Getir
Sistemde kayýtlý olan bütün makine arýza kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/UrMakineAriza/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Makine Oluþtur
Yeni bir makine arýzasýný oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Makine Düzenle
Var olan makine arýzasýný düzenlemektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Makine Sil
Mevcut makine arýzasýný silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Operasyon 


## End-point: Operasyon Getir
Sistemde kayýtlý olan bütün operasyon kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/urOperasyon/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Operasyon Oluþtur
Yeni bir operasyon oluþturmaktadýr.
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
            "Aciklama": "Hýzlý Reçetelerde kullanýlan operasyon",
            "HizBirimID": null,
            "KartPuan": 0.000000
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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
        "Aciklama": "Hýzlý Reçetelerde kullanýlan operasyon",
        "HizBirimID": null,
        "KartPuan": 0.000000
    }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|2|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Yevmiye Fis 


## End-point: YevmiyeFis Getir
Sistemde kayýtlý olan yevmiye fiþ kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/YevmiyeFis/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: YevmiyeFis Oluþtur
Yeni bir yevmiye fiþi oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: YevmiyeFis Düzenle
Var olan yevmiye fiþini düzenlemeketedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: YevmiyeFis Sil
Mevcut yevmiye fiþini silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Yevmiye Fis Hareketleri 


## End-point: YevmiyeFisHareketleri Getir
Sistemde kayýtlý olan bütün yevmiye fiþ hareketlerinin görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/YevmiyeFisHareketleri/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: YevmiyeFisHareketleri Oluþtur
Yeni bir yevmiye fiþ hareketi oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: YevmiyeFisHareketleri Düzenle
Var olan yevmiye fiþ hareketini düzenlemeketedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: YevmiyeFisHareketleri Sil
Mevcut yevmiye fiþ hareketini silmektedir.

###### Bu iþlemin geri dönüþü yoktur. Silmeden önce bu bu bankanýn hareketler ve bankalarla ile iliþkisini kesmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: OlcuBirimleri 


## End-point: OlcuBirimleri Getir
Sistemde kayýtlý olan bütün ölçü birimlerinin görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/OlcuBirimleri/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: OlcuBirimleri Oluþtur
Yeni bir ölçü birimi oluþturmaktadýr.
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
            "SubeAdi": "Tüm Þubeler",
            "SirketAdi": "Tüm Þirketler",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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
            "SubeAdi": "Tüm Þubeler",
            "SirketAdi": "Tüm Þirketler",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: OlcuBrimleri Sil
Mevcut ölçü birimini silmektedir.

###### Bu iþlemin geri dönüþü yoktur. Silmeden önce bu bu bankanýn hareketler ve bankalarla ile iliþkisini kesmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: PerPuantaj 


## End-point: PerPuantaj Getir
Sistemde kayýtlý olan bütün banka kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/PerPuantaj/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: PerPuantaj Oluþtur
Yeni bir personel puantaj oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: PerPuantaj Düzenle
Var olan personel puantajýný düzenlemeketedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: PerPuantaj Sil
Mevcut personel puantajýný silmektedir.

###### Bu iþlemin geri dönüþü yoktur. Silmeden önce bu bu bankanýn hareketler ve bankalarla ile iliþkisini kesmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Personel 


## End-point: Personel Getir
Sistemde kayýtlý olan bütün banka kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/Personel/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Personel Oluþtur
Yeni bir stok kartý eklemek için
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Personel Düzenle
Mevcut bir deponun düzeltilmesi için kullanýlmaktadýr.

######  Depo eklemekten farklý olarak ID eklenmesi gerekmektedir.
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
            "PersonelAdiSoyadi": "denemewebapi denemeWEBAPÝ",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Personel Sil
Mevcut bir deponun silinmesi için kullanýlmaktadýr.

######  Depoyu silmeden önce depoya ait bütün hareketlerin ve stoklar silindiðinden/taþýndýðýndan emin olunuz. Aksi takdirde silme iþlemi gerçekleþmeyecektir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Ýs Emri 


## End-point: ÝsEmri Getir
Sistemde kayýtlý olan bütün iþ emri kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/urIsEmri/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: ÝsEmri Oluþtur
StartFragment

Yeni bir iþ emri oluþturmaktadýr.  
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.
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
            "Aciklama": " \r\nSipariþ Açýklama : \r\n \r\n"

}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: ÝsEmri Düzenle
Mevcut bir iþ emrinin düzeltilmesi için kullanýlmaktadýr.

###### Ýþ emri eklemekten farklý olarak ID eklenmesi gerekmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: ÝsEmri Sil
Mevcut bir iþ emrinin silinmesi için kullanýlmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Banka Þube 


## End-point: Banka Þubeleri Getir
StartFragment

Sistemde kayýtlý olan bütün banka þube kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/BankaSube/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Þube Oluþtur
StartFragment

Yeni bir banka þube oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Þube Düzenle
StartFragment

Var olan banka þubesini düzenlemektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Þube Sil
StartFragment

Mevcut banka þubeyi silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Notlar 


## End-point: Notlarý Getir
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Not Ekle/Gönder
### Method: POST
>```
>{{BaseUrl}}/api/Notlar/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "Notu": "Son eklenen stok kartý için not",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Stok Sayým 


## End-point: Sayým Giriþleri Getir
Sistemde kayýtlý olan bütün stok sayýmlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/StokSayim
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sayým Giriþi Yap
Yeni bir stok kartý eklemek için  
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

### Sorgu Body JSON açýklamasý

| Parametre | Örnek Deðer | Taným | ZorunluMu |
| --- | --- | --- | --- |
| StokID | \-1 | Eklenilen ürünün stok ID'sidir. -1 girildiði takdirde rasgele olarak ID atanmaktadýr. | Evet |
| SubeID | 1 | Stoðun bulunduðu þubenin ID'sidir. | Evet |
| SirketID | 1 | Stoðun ait olduðu þirketin ID'sidir. | Evet |
| StokKodu | "HRD.KPKL.00164" | Stoðun detaylý kodudur. | Evet |
| StokAdi | "Hýrdavat Kapý Kolu Burak Oda Rozetli Saten" | Stoðun gözüken adýdýr. | Evet |
| StokKisaKodu | "HRD.KPKL" | Stoðun genel kodudur. Genel kod özel kodlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa koda sahip olmasý önemlidir. | Evet |
| StokKisaAdi | "Hýrdavat Kapý Kolu" | Stoðun genel adýdýr. Genel ad özel adlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa ada sahip olmasý önemlidir. | Evet |
| Durum | true | Stok kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet |
| TipID | 105001 | Aaro'da stok yalnýzca fiziksel bir malý iþaret etmek durumunda deðildir. Gelir-gider hareketleri gibi iþlemler de stok olarak düþünülmektedir dolayýsýyla ne tür bir stok olduðunu belirtmek için TipID bulunmaktadýr. | Evet |
| StokMuhasebeID | 201 | Stoklarýn muhasebesebesi farklý þekilde iþlenebilir. Stok muhasebe ID hakkýnda detaylý bilgi için muhasebe bölümünü inceleyiniz | Evet |
| Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Evet |
| Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel |
| Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel |
| CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel |
| CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel |
| Kalinlik | 10.0 | Stok kartýnýn fizikel kalýnlýðýdýr. | Opsiyonel |
| En | 10.0 | Stok kartýnýn fizikel enidir. | Opsiyonel |
| Boy | 10.0 | Stok kartýnýn fizikel boyudur. | Opsiyonel |
| Yoðunluk | 3.0 | Stok kartýnýn fizikel yoðunluðudur. | Opsiyonel |
| Agirlik | 5.0 | Stok kartýnýn fizikel aðýrlýðýdýr. | Opsiyonel |
| Kod1ID | null | Stok kartlarýný hiyerarþik gruplandýrmak için kullanýlýr. Örnek: Elektronik -> Bilgisayar -> HP | Opsiyonel |
| Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel |
| SablonID | null | Ürün ekleme þablonu varsa girilmelidir. | Opsiyonel |

> &lt;h5 &gt;Ürün oluþtururken döküman altýndaki örnek senaryo üzerinden gidebilirsiniz.&lt;/h5&gt;
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sayým Giriþi Düzelt
Yeni bir stok kartý eklemek için
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.
### Sorgu URL Parametreleri

Parametre | Deðer | Taným
--------- | ----------- | ---------
KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu Body JSON açýklamasý

Parametre | Örnek Deðer | Taným | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen ürünün stok ID'sidir. -1 girildiði takdirde rasgele olarak ID atanmaktadýr.  | Evet
SubeID | 1 | Stoðun bulunduðu þubenin ID'sidir. | Evet
SirketID | 1 | Stoðun ait olduðu þirketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Stoðun detaylý kodudur. | Evet
StokAdi | "Hýrdavat Kapý Kolu Burak Oda Rozetli Saten" | Stoðun gözüken adýdýr. | Evet
StokKisaKodu |"HRD.KPKL" | Stoðun genel kodudur. Genel kod özel kodlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa koda sahip olmasý önemlidir. | Evet
StokKisaAdi |"Hýrdavat Kapý Kolu" | Stoðun genel adýdýr. Genel ad özel adlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa ada sahip olmasý önemlidir. | Evet
Durum | true | Stok kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yalnýzca fiziksel bir malý iþaret etmek durumunda deðildir. Gelir-gider hareketleri gibi iþlemler de stok olarak düþünülmektedir dolayýsýyla ne tür bir stok olduðunu belirtmek için TipID bulunmaktadýr. | Evet
StokMuhasebeID | 201 | Stoklarýn muhasebesebesi farklý þekilde iþlenebilir. Stok muhasebe ID hakkýnda detaylý bilgi için muhasebe bölümünü inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel
Kalinlik | 10.0 | Stok kartýnýn fizikel kalýnlýðýdýr. | Opsiyonel
En | 10.0 | Stok kartýnýn fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kartýnýn fizikel boyudur. | Opsiyonel
Yoðunluk | 3.0 | Stok kartýnýn fizikel yoðunluðudur. | Opsiyonel
Agirlik | 5.0 | Stok kartýnýn fizikel aðýrlýðýdýr. | Opsiyonel
Kod1ID | null | Stok kartlarýný hiyerarþik gruplandýrmak için kullanýlýr. Örnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel
SablonID | null | Ürün ekleme þablonu varsa girilmelidir. | Opsiyonel

>##### Ürün oluþtururken döküman altýndaki örnek senaryo üzerinden gidebilirsiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sayým Griþi  Sil
Mevcut cariyi silmektedir

###### Bu iþlemin geri dönüþü yoktur. Silmeden önce bu carinin hareketler ve bankalarla ile iliþkisini kesmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sayým Hareketleri Getir
### Method: GET
>```
>{{BaseUrl}}/api/StokSayimHareketleri/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sayým Hareketi Ekle
Yeni bir stok kartý eklemek için
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.
### Sorgu URL Parametreleri

Parametre | Deðer | Taným
--------- | ----------- | ---------
KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu Body JSON açýklamasý

Parametre | Örnek Deðer | Taným | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen ürünün stok ID'sidir. -1 girildiði takdirde rasgele olarak ID atanmaktadýr.  | Evet
SubeID | 1 | Stoðun bulunduðu þubenin ID'sidir. | Evet
SirketID | 1 | Stoðun ait olduðu þirketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Stoðun detaylý kodudur. | Evet
StokAdi | "Hýrdavat Kapý Kolu Burak Oda Rozetli Saten" | Stoðun gözüken adýdýr. | Evet
StokKisaKodu |"HRD.KPKL" | Stoðun genel kodudur. Genel kod özel kodlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa koda sahip olmasý önemlidir. | Evet
StokKisaAdi |"Hýrdavat Kapý Kolu" | Stoðun genel adýdýr. Genel ad özel adlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa ada sahip olmasý önemlidir. | Evet
Durum | true | Stok kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yalnýzca fiziksel bir malý iþaret etmek durumunda deðildir. Gelir-gider hareketleri gibi iþlemler de stok olarak düþünülmektedir dolayýsýyla ne tür bir stok olduðunu belirtmek için TipID bulunmaktadýr. | Evet
StokMuhasebeID | 201 | Stoklarýn muhasebesebesi farklý þekilde iþlenebilir. Stok muhasebe ID hakkýnda detaylý bilgi için muhasebe bölümünü inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel
Kalinlik | 10.0 | Stok kartýnýn fizikel kalýnlýðýdýr. | Opsiyonel
En | 10.0 | Stok kartýnýn fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kartýnýn fizikel boyudur. | Opsiyonel
Yoðunluk | 3.0 | Stok kartýnýn fizikel yoðunluðudur. | Opsiyonel
Agirlik | 5.0 | Stok kartýnýn fizikel aðýrlýðýdýr. | Opsiyonel
Kod1ID | null | Stok kartlarýný hiyerarþik gruplandýrmak için kullanýlýr. Örnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel
SablonID | null | Ürün ekleme þablonu varsa girilmelidir. | Opsiyonel

>##### Ürün oluþtururken döküman altýndaki örnek senaryo üzerinden gidebilirsiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sayým Hareketi Düzelt
Yeni bir stok kartý eklemek için
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.
### Sorgu URL Parametreleri

Parametre | Deðer | Taným
--------- | ----------- | ---------
KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu Body JSON açýklamasý

Parametre | Örnek Deðer | Taným | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen ürünün stok ID'sidir. -1 girildiði takdirde rasgele olarak ID atanmaktadýr.  | Evet
SubeID | 1 | Stoðun bulunduðu þubenin ID'sidir. | Evet
SirketID | 1 | Stoðun ait olduðu þirketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Stoðun detaylý kodudur. | Evet
StokAdi | "Hýrdavat Kapý Kolu Burak Oda Rozetli Saten" | Stoðun gözüken adýdýr. | Evet
StokKisaKodu |"HRD.KPKL" | Stoðun genel kodudur. Genel kod özel kodlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa koda sahip olmasý önemlidir. | Evet
StokKisaAdi |"Hýrdavat Kapý Kolu" | Stoðun genel adýdýr. Genel ad özel adlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa ada sahip olmasý önemlidir. | Evet
Durum | true | Stok kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yalnýzca fiziksel bir malý iþaret etmek durumunda deðildir. Gelir-gider hareketleri gibi iþlemler de stok olarak düþünülmektedir dolayýsýyla ne tür bir stok olduðunu belirtmek için TipID bulunmaktadýr. | Evet
StokMuhasebeID | 201 | Stoklarýn muhasebesebesi farklý þekilde iþlenebilir. Stok muhasebe ID hakkýnda detaylý bilgi için muhasebe bölümünü inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel
Kalinlik | 10.0 | Stok kartýnýn fizikel kalýnlýðýdýr. | Opsiyonel
En | 10.0 | Stok kartýnýn fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kartýnýn fizikel boyudur. | Opsiyonel
Yoðunluk | 3.0 | Stok kartýnýn fizikel yoðunluðudur. | Opsiyonel
Agirlik | 5.0 | Stok kartýnýn fizikel aðýrlýðýdýr. | Opsiyonel
Kod1ID | null | Stok kartlarýný hiyerarþik gruplandýrmak için kullanýlýr. Örnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel
SablonID | null | Ürün ekleme þablonu varsa girilmelidir. | Opsiyonel

>##### Ürün oluþtururken döküman altýndaki örnek senaryo üzerinden gidebilirsiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sayým Hareketi Sil
Mevcut cariyi silmektedir

###### Bu iþlemin geri dönüþü yoktur. Silmeden önce bu carinin hareketler ve bankalarla ile iliþkisini kesmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Dekont 


## End-point: Tamamla
Dekont baþlýk ve kalem bilgilerini girdikten sonra tamamla çaðrýlýrsa kayýt tamamlanacaktýr. Oluþturulan dekont id bilgisi yeterlidir.

> _**Yarým býrakýlmýþ bir kayýt var ve ayný belge numarasý ile yeni bir kaydý tamamla metodu ile eklemeye çalýþýyorsak bu belge numarasý kullanýlmýþtýr hatasý alabiliriz.Bu yüzden kayýtlarýmýzda belge numaralarý farklý olmalýdýr.**_
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Dekont Baþlýk Getir
Bu uç nokta ile kayýtlý olan dekontun DekontID'si gönderilerek baþlýk bilgisi alýnabilir. Ayný bilgiye Baþlýklarý Getir sekmesinde DekontID kýsýtý gönderilerekte ulaþýlabilir.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| id | Integer | Belirtilen ID ile Dekont Baþlýðý getirmektedir. |
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
        "Aciklama": "Alýnan Sipariþ Ýlk Müþterim",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Dekont Baþlýklarý Getir
Bu uç nokta ile kayýtlý olan tüm dekontlarýn filtrelenerek listesi alýnabilir.
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
            "Aciklama": "Alýnan Sipariþ Ýlk Müþterim",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Dekont KalemTek  Getir
Bu uç nokta ile kayýtlý olan Dekontun KalemTek bilgisi alýnabilir. Nerdeyse tüm dekont tiplerinin vardýr. Eðer yoksa boþ sonuç döndürür.

### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| DekontID | Integer | Belirtilen ID ile Dekont Baþlýðý getirmektedir. |
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
        "Aciklama": "Sipariþ Baþlýk Modeli Ekleme deneme",
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
        "KartAdi": "Ýlk Müþterim"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Dekont Kalemler Getir
Bu uç nokta ile kayýtlý olan Dekontunkalemleri okunabilir.
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
            "KartAdi": "Otomatik Aktarým Stok Kartý"
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
            "KartAdi": "Otomatik Aktarým Stok Kartý"
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
            "KartAdi": "Otomatik Aktarým Stok Kartý"
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
            "KartAdi": "Otomatik Aktarým Stok Kartý"
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
            "KartAdi": "Otomatik Aktarým Stok Kartý"
        }
    ],
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Alýnan Sipariþ Baþlýk Ekleme
Bu baþlýk altýnda Alýnan Sipariþ hareketinin kaydetme sürecini göreceksiniz. (Tek-Cok) hareketlerinde önce BaslikModel ve KalemTekModel bilgileri ile Baþlýk kaydedilir. Bu iþlem baþarýlý olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir.

#### BaslikModel

Farklý bir Dekont(Tek-Cok) kaydý oluþturmak istediðinzde örneðin Verilen Sipariþ hareketi oluþturmak istediðinizde, BaslikModel'in içinde yer alan TipID parametresini "VerilenSiparis" olarak deðiþtirmeniz yeterli olacaktýr.

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | AlinanSiparis | Dekontun hareket türünü belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi þirkete açýlacaðýný belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi þubeye açýlacaðýný belirler | Evet |
| BelgeNo | String | 2822429117384-AS | Dekontun belge numarasýdýr. Uniqe olmak zorundadýr. | Evet |
| Tarih | DateTime | 2023-03-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmediði takdirde dekontun tarihi ile ayný deðeri alacaktýr. | Hayýr |
| RefDepoID | Integer | 1 | Alýnan sipariþe girilen Deponun id'sini belritir. | Hayýr |

Yukarýdaki bilgiler Dekont Baþlýðý oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz BaslikModel'ine bakabilirsiniz.

#### KalemTekModel

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Cari | Alýnan Sipariþ hareketi Cari üzerinden yapýldýðý için KalemTek bilgisinin KalemTipi parametresi Cari olmalýdýr. | Evet |
| KartID | Integer | 4920 | Aaro'da tanýmlamýþ olduðunuz cari kartýnýn ID'sidir. | Evet |
| Tutar | Decimal | 100 | Hareketin toplam tutarýnýn TL cinsinden karþýlýðýdýr. 0 girilemez. | Hayýr |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutarýnýn belirtilen döviz cinsinden karþýlýðýdýr. Döviz cinsi TL(1)'den farklý ise 0 girilemez. | Hayýr |
| Aciklama | String | Alýnan Sipariþ Baþlýk Modeli Ekleme | Dekont'a ait açýklamadýr. | Hayýr |

Yukarýdaki bilgiler Dekont KalemTek oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu iþlem baþarýlý olduktan sonra KalemCok bilgisini eklemek için Kalem metodunu kullanacaðýz.

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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
        "TipID": 10013, // Alýnan sipariþ olduðunu belirtir.
        "SirketID": 1,
        "SubeID": 1,
        "RefDepoID":1  //Alýnan sipariþe girilen Deponun id'sini belirtir.        
    },
    "KalemTek": { //Alýnan sipariþe girilen cari bilgileri girilmesi için kullanýlýr.
        "KalemTipi": 6, // Kalem tipine göre belirlenir. Kalem tipi tablosu altýnda bulabilirsiniz.
        "KartID": 4, //Sipariþe girilen cari'nin id'si girilmelidir.
        "DovizID": 1,
        "Aciklama": "Sipariþ Baþlýk Modeli Ekleme deneme"
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Alýnan Sipariþ Kalem Ekleme
Baþlýk kaydetme iþlemi baþarýlý olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanýz her kalem için bu metodu çaðýrmalýsýnýz.

#### KalemCokModel

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | SiparisStok | Alýnan Sipariþ hareketinde kalemleri ekleyebilmek için KalemTipi parametresi SiparisStok olmalýdýr. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydettiðimiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tanýmlamýþ olduðunuz stok kartýnýn ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istediðiniz stoðun kendi birimi cinsinden miktarýný belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutarýnýn TL cinsinden karþýlýðýdýr. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutarýnýn belirtilen döviz cinsinden karþýlýðýdýr. Döviz cinsi TL(1)'den farklý ise 0 girilemez. | Evet |
| SiparisStok | SiparisStokModel | SiparisStokModel | Dökümanda yer alan SiparisStokModel bilgileriyle oluþturulan model | Evet |

Yukarýdaki bilgiler Dekont KalemCok oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu iþlem baþarýlý olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacaðýz.

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Alýnan Sipariþ Baþlýk Düzeltme
Baþlýk bilgisinde DekontID'yi set ettikten sorna düzeltme iþlemi yapabiliriz

#### BaslikModel

Baþlýk bilgisini düzeltirken KalemTek bilgisini göndermeniz zorunlu deðildir,

#### KalemTekModel

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 Tüm API'de yeni kayýt düzenle anlamýna gelmektedir. |

Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Hayýr |
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
        "TipID": 10013, // Alýnan sipariþ olduðunu belirtir.
        "SirketID": 1,
        "SubeID": 1,
        "RefDepoID":1  //Alýnan sipariþe girilen Deponun id'sini belritir.
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
        "Aciklama": "Alýnan Sipariþ Ýlk Müþterim",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Alýnan Sipariþ Kalem Düzeltme
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra düzeltme iþlemi yapabiliriz. Kalem bilgisinin miktarýný deðiþtirip 7 yapalým. Miktar bilgisini güncellediðiniz zaman Tutar bilgisinin de güncellenmesini istiyorsanýz, Tutar bigisini de girmeniz gerekmektedir.

> **Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayýt düzenle anlamýna gelmektedir. |

> _**Kalem bilgisi düzeltildikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**_
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
        "KartAdi": "Otomatik Aktarým Stok Kartý"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Alýnan Sipariþ Baþlýk Silme
#### BaslikModel

Baþlýk bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayýt sil anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Alýnan Sipariþ Kalem Silme
Kalem bilgisinin DekontID,KalemTipi ve HareketID'si set edildikten sonra silme iþlemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayýt sil anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| KalemCok | KalemModel | KalemModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |

> _**Kalem bilgisi silindikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**_
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Alýnan Sipariþ Tevkifatlý  Kalem Ekleme
Baþlýk kaydetme iþlemi baþarýlý olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanýz her kalem için bu metodu çaðýrmalýsýnýz.

> _**Tevkifatlý kalem bilgisi için vergi alt ID eklenmelidir. Bu Id'nin karþýlýðý Tevkifat Tip ID'dir. Vergi oranlarýný listeyip bu bilgiyi bulabilirsiniz.**_ 
  

#### KalemCokModel

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | SiparisStok | Alýnan Sipariþ hareketinde kalemleri ekleyebilmek için KalemTipi parametresi SiparisStok olmalýdýr. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydettiðimiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tanýmlamýþ olduðunuz stok kartýnýn ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istediðiniz stoðun kendi birimi cinsinden miktarýný belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutarýnýn TL cinsinden karþýlýðýdýr. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutarýnýn belirtilen döviz cinsinden karþýlýðýdýr. Döviz cinsi TL(1)'den farklý ise 0 girilemez. | Evet |
| SiparisStok | SiparisStokModel | SiparisStokModel | Dökümanda yer alan SiparisStokModel bilgileriyle oluþturulan model | Evet |

Yukarýdaki bilgiler Dekont KalemCok oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu iþlem baþarýlý olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacaðýz.

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**
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
                "VergiAltID": 28, //Tevkifat Tip ID bilgisi girilmelidir. Vergi oranlarýný listeyip bu bilgiyi bulabilirsiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Nakit Tahsilat Ekle
Bu baþlýk altýnda Nakit Tahsilat hareketinin kaydetme sürecini göreceksiniz. Bunun için öncelikle BaslikModel, KalemTekModel ve KalemCokModel yapýlarýmýzý oluþturalým.

#### BaslikModel

Farklý bir Dekont(Tek-Tek) kaydý oluþturmak istediðinizde örneðin Nakit Ödeme hareketi oluþturmak istediðinizde, BaslikModel'in içinde yer alan TipID parametresini "NakitOdeme" olarak deðiþtirmeniz yeterli olacaktýr.

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | NakitTahsilat | Dekontun hareket türünü belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi þirkete açýlacaðýný belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi þubeye açýlacaðýný belirler | Evet |
| BelgeNo | String | 2822429117384-NT | Dekontun belge numarasýdýr. Uniqe olmak zorundadýr. | Evet |
| Tarih | DateTime | 24.09.2021 | Dekont tarihidir. | Evet |
| Vade | DateTime | 24.09.2021 | Deokntun vadesidir. Verilmediði takdirde dekontun tarihi ile ayný deðeri alacaktýr. | Hayýr |
| Aciklama | String | Nakit Tahsilat Baþlýk Modeli | Dekont'un baþlýðýna ait açýklamadýr. | Hayýr |

> **Yukarýdaki bilgiler Dekont Baþlýðý oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz BaslikModel'ine bakabilirsiniz.** 
  

#### KalemTekModel

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Kasa | Nakit Tahsilat hareketi Kasa üzerinden yapýldýðý için KalemTek bilgisinin KalemTipi parametresi Kasa olmalýdýr. | Evet |
| KartID | Integer | 1 | Aaro'da tanýmlamýþ olduðunuz kasa kartýnýn ID'sidir. | Evet |
| Tutar | Decimal | 1 | Hareketin toplam tutarýnýn TL cinsinden karþýlýðýdýr. 0 girilemez. KalemCok bilgisindeki deðer ile ayný olmalýdýr. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. KalemCok bilgisindeki deðer ile ayný olmalýdýr. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutarýnýn belirtilen döviz cinsinden karþýlýðýdýr. Döviz cinsi TL(1)'den farklý ise 0 girilemez. KalemCok bilgisindeki deðer ile ayný olmalýdýr. | Evet |

> **Yukarýdaki bilgiler Dekont KalemTek oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### KalemCokModel

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Cari | Nakit Tahsilat hareketinin diðer tarafý Cari olduðu için KalemTek bilgisinin KalemTipi parametresi Cari olmalýdýr. | Evet |
| KartID | Integer | 4920 | Aaro'da tanýmlamýþ olduðunuz cari kartýnýn ID'sidir. | Evet |
| Tutar | Decimal | 100 | Hareketin toplam tutarýnýn TL cinsinden karþýlýðýdýr. 0 girilemez. KalemTek bilgisindeki deðer ile ayný olmalýdýr. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. KalemTek bilgisindeki deðer ile ayný olmalýdýr. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutarýnýn belirtilen döviz cinsinden karþýlýðýdýr. Döviz cinsi TL(1)'den farklý ise 0 girilemez. KalemTek bilgisindeki deðer ile ayný olmalýdýr. | Evet |

> **Yukarýdaki bilgiler Dekont KalemCok oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
| KalemCok | KalemModel | KalemModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Nakit Tahsilat Düzenle
BaþlýkModel içerisinde DekontID bilgisini set ettikten sonra düzeltme yapabiliriz.

#### BaslikModel

#### KalemTekModel

KalemTek Model deki tutar bilgisini yenileyelim KalemTek icindeki aciklama alanini deðiþtirelim. Bu alan Dekontun açýklamasýdýr.

#### KalemCokModel

KalemCok Model deki tutar bilgisini yenileyelim.

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de kayýt düzenle anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
| KalemCok | KalemModel | KalemModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Nakit Tahsilat Sil
BaþlýkModel içerisinde sadece DekontID bilgisini set etmemiz yeterli olacaktýr.

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayýt sil anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Satýþ Faturasý Baþlýk Ekleme
Bu baþlýk altýnda Satýþ faturasý hareketinin kaydetme sürecini göreceksiniz. (Tek-Cok) hareketlerinde önce BaslikModel ve KalemTekModel bilgileri ile Baþlýk kaydedilir. Bu iþlem baþarýlý olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir.

#### BaslikModel

Farklý bir Dekont(Tek-Cok) kaydý oluþturmak istediðinzde örneðin Satýþ Faturasý hareketi oluþturmak istediðinizde, BaslikModel'in içinde yer alan TipID parametresini "Satýþ Faturasý" olarak deðiþtirmeniz yeterli olacaktýr.

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | SatisFaturasi | Dekontun hareket türünü belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi þirkete açýlacaðýný belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi þubeye açýlacaðýný belirler | Evet |
| BelgeNo | String | 2822429117384-AS | Dekontun belge numarasýdýr. Uniqe olmak zorundadýr. | Evet |
| Tarih | DateTime | 2023-03-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmediði takdirde dekontun tarihi ile ayný deðeri alacaktýr. | Hayýr |
| RefDepoID | Integer | 1 | Satýþ faturasý girilen Deponun id'sini belirtir. | Hayýr |

> **Yukarýdaki bilgiler Dekont Baþlýðý oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz BaslikModel'ine bakabilirsiniz.** 
  

#### KalemTekModel

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Cari | Satýþ faturasý hareketi Cari üzerinden yapýldýðý için KalemTek bilgisinin KalemTipi parametresi Cari olmalýdýr. | Evet |
| KartID | Integer | 4920 | Aaro'da tanýmlamýþ olduðunuz cari kartýnýn ID'sidir. | Evet |
| Tutar | Decimal | 100 | Hareketin toplam tutarýnýn TL cinsinden karþýlýðýdýr. 0 girilemez. | Hayýr |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutarýnýn belirtilen döviz cinsinden karþýlýðýdýr. Döviz cinsi TL(1)'den farklý ise 0 girilemez. | Hayýr |
| Aciklama | String | Test Satýþ Faturasý | Dekont'a ait açýklamadýr. | Hayýr |

Yukarýdaki bilgiler Dekont KalemTek oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu iþlem baþarýlý olduktan sonra KalemCok bilgisini eklemek için Kalem metodunu kullanacaðýz.

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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
        "RefDepoID":1  //Alýnan sipariþe girilen Deponun id'sini belirtir.
    },
    "KalemTek": {
        "KalemTipi": 1,
        "KartID": 4,
        "DovizID": 1,
        "Aciklama": "Test Satýþ Faturasý"
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Satýþ Faturasý Kalem Ekleme
Baþlýk kaydetme iþlemi baþarýlý olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanýz her kalem için bu metodu çaðýrmalýsýnýz.

#### KalemCokModel

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Stok | Satýþ Faturasý hareketinde kalemleri ekleyebilmek için KalemTipi parametresi Stok olmalýdýr. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydettiðimiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tanýmlamýþ olduðunuz stok kartýnýn ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istediðiniz stoðun kendi birimi cinsinden miktarýný belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutarýnýn TL cinsinden karþýlýðýdýr. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutarýnýn belirtilen döviz cinsinden karþýlýðýdýr. Döviz cinsi TL(1)'den farklý ise 0 girilemez. | Evet |
| Stok | StokModel | StokModel | Dökümanda yer alan StokModel bilgileriyle oluþturulan model | Evet |

> **Yukarýdaki bilgiler Dekont KalemCok oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

Bu iþlem baþarýlý olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacaðýz.

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**
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
        "KartAdi": "Otomatik Aktarým Stok Kartý"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Satýþ Faturasý Baþlýk Düzeltme
Baþlýk bilgisinde DekontID'yi set ettikten sorna düzeltme iþlemi yapabiliriz

#### BaslikModel

Baþlýk bilgisini düzeltirken KalemTek bilgisini göndermeniz zorunlu deðildir,

#### KalemTekModel

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 Tüm API'de yeni kayýt düzenle anlamýna gelmektedir. |

Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Hayýr |
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
        "RefDepoID":1  //Alýnan sipariþe girilen Deponun id'sini belirtir.
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
        "Aciklama": "Satýþ Faturasý Ýlk Müþterim",
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Satýþ Faturasý Kalem Düzeltme
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra düzeltme iþlemi yapabiliriz. Kalem bilgisinin miktarýný deðiþtirip 7 yapalým. Miktar bilgisini güncellediðiniz zaman Tutar bilgisinin de güncellenmesini istiyorsanýz, Tutar bigisini de girmeniz gerekmektedir.

> **Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayýt düzenle anlamýna gelmektedir. |

> _**Kalem bilgisi düzeltildikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**_
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
        "KartAdi": "Otomatik Aktarým Stok Kartý"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Satýþ Faturasý Baþlýk Silme
#### BaslikModel

Baþlýk bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayýt sil anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Satýþ Faturasý Kalem Silme
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra silme iþlemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayýt sil anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| KalemCok | KalemModel | KalemModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |

> _**Kalem bilgisi silindikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**_
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Karma Transfer Baþlýk Ekleme
#### BaslikModel

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | KarmaTransfer | Dekontun hareket türünü belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi þirkete açýlacaðýný belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi þubeye açýlacaðýný belirler | Evet |
| BelgeNo | String | 0000000000000011 | Dekontun belge numarasýdýr. Uniqe olmak zorundadýr. | Evet |
| Tarih | DateTime | 2024-06-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmediði takdirde dekontun tarihi ile ayný deðeri alacaktýr. | Hayýr |
| RefDepoID | Integer | 1 | Karma transfere girilen Deponun id'sini belirtir. | Hayýr |

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Karma Transfer Kalem Ekle
Baþlýk kaydetme iþlemi baþarýlý olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanýz her kalem için bu metodu çaðýrmalýsýnýz.

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Stok | Karma transfer hareketinde kalemleri ekleyebilmek için KalemTipi parametresi eklenen tipe göre deðiþir. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydettiðimiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tanýmlamýþ olduðunuz stok kartýnýn ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istediðiniz stoðun kendi birimi cinsinden miktarýný belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutarýnýn TL cinsinden karþýlýðýdýr. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutarýnýn belirtilen döviz cinsinden karþýlýðýdýr. Döviz cinsi TL(1)'den farklý ise 0 girilemez. | Evet |
| Stok | StokModel | StokModel | Dökümanda yer alan StokModel bilgileriyle oluþturulan model | Evet |
| Cari | CariModel | CariModel | Dökümanda yer alan CariModelbilgileriyle oluþturulan model |  |
| Banka | BankaModel | BankaModel | Dökümanda yer alan BankaModelbilgileriyle oluþturulan model |  |
| Kasa | KasaModel | KasaModel | Dökümanda yer alan KasaModelbilgileriyle oluþturulan model |  |

> **Yukarýdaki bilgiler Dekont KalemCok oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

Bu iþlem baþarýlý olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacaðýz.

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**
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
        "KartAdi": "Otomatik Aktarým Stok Kartý"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Karma Transfer Baþlýk Düzeltme
Baþlýk bilgisinde DekontID'yi set ettikten sorna düzeltme iþlemi yapabiliriz

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 Tüm API'de yeni kayýt düzenle anlamýna gelmektedir. |

Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Karma Transfer Kalem Düzenle
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra düzeltme iþlemi yapabiliriz.

> **Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayýt düzenle anlamýna gelmektedir. |

> _**Kalem bilgisi düzeltildikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**_
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
        "KartAdi": "Otomatik Aktarým Stok Kartý"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Karma Transfer  Baþlýk Silme
#### BaslikModel

Baþlýk bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayýt sil anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Karma Transfer Kalem Sil
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra silme iþlemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayýt sil anlamýna gelmektedir. |

> _**Kalem bilgisi silindikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**_
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Devir Baþlýk Ekleme
#### BaslikModel

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | Devir | Dekontun hareket türünü belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi þirkete açýlacaðýný belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi þubeye açýlacaðýný belirler | Evet |
| BelgeNo | String | 0000000000000011 | Dekontun belge numarasýdýr. Uniqe olmak zorundadýr. | Evet |
| Tarih | DateTime | 2024-06-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmediði takdirde dekontun tarihi ile ayný deðeri alacaktýr. | Hayýr |
| RefDepoID | Integer | 1 | Devire girilen Deponun id'sini belirtir. | Hayýr |

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Devir Kalem Ekle
Baþlýk kaydetme iþlemi baþarýlý olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanýz her kalem için bu metodu çaðýrmalýsýnýz.

| Parametre | Tip | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Stok | Devir hareketinde kalemleri ekleyebilmek için KalemTipi parametresi kalem tipine göre olmalýdýr. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydettiðimiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tanýmlamýþ olduðunuz stok kartýnýn ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istediðiniz stoðun kendi birimi cinsinden miktarýný belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutarýnýn TL cinsinden karþýlýðýdýr. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin döviz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutarýnýn belirtilen döviz cinsinden karþýlýðýdýr. Döviz cinsi TL(1)'den farklý ise 0 girilemez. | Evet |
| Stok | StokModel | StokModel | Dökümanda yer alan StokModel bilgileriyle oluþturulan model | Evet |
| Cari | CariModel | CariModel | Dökümanda yer alan CariModelbilgileriyle oluþturulan model |  |
| Banka | BankaModel | BankaModel | Dökümanda yer alan BankaModelbilgileriyle oluþturulan model |  |
| Kasa | KasaModel | KasaModel | Dökümanda yer alan KasaModelbilgileriyle oluþturulan model |  |

> **Yukarýdaki bilgiler Dekont KalemCok oluþturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

Bu iþlem baþarýlý olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacaðýz.

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**
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
        "KartAdi": "Otomatik Aktarým Stok Kartý"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Devir Baþlýk Düzeltme
Baþlýk bilgisinde DekontID'yi set ettikten sorna düzeltme iþlemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Tip | Deðer | Taným |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 Tüm API'de yeni kayýt düzenle anlamýna gelmektedir. |

Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Devir Kalem Düzenle
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra düzeltme iþlemi yapabiliriz.

> **Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayýt düzenle anlamýna gelmektedir. |

> _**Kalem bilgisi düzeltildikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**_
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
        "KartAdi": "Otomatik Aktarým Stok Kartý"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Devir Baþlýk Silme
#### BaslikModel

Baþlýk bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayýt sil anlamýna gelmektedir. |

#### Sorgu Body JSON açýklamasý

| Parametre | Deðer | Taným | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in açýklamasýna bakýp bilgi alabilirsiniz. | Evet |
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Devir Kalem Sil
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra silme iþlemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Deðer | Taným |
| --- | --- | --- |
| KayitTipi | Integer | \-1 Tüm API'de kayýt sil anlamýna gelmektedir. |

> _**Kalem bilgisi silindikten sonra Tamamla metodu çaðrýlarak Baþlýk ve kalem bilgisi kaydedilmiþ olur.**_
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


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Baþvurulacak Tablolar 

# ?? Collection: StokOzet 


## End-point: Stok Özet Getir
Bu uç nokta ile stoklardaki ürünleri toplu olarak ya da belirli bir kýsýt ile getirebilirsiniz.


### Method: GET
>```
>{{baseUrl}}/api/StokOzet
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Rehber 


## End-point: Rehber Secenekler
Yeni bir stok kartý eklemek için
KayitTipi: 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.
### Sorgu URL Parametreleri

Parametre | Deðer | Taným
--------- | ----------- | ---------
KayitTipi | Integer | 1 Tüm API'de yeni kayýt ekle anlamýna gelmektedir.

### Sorgu Body JSON açýklamasý

Parametre | Örnek Deðer | Taným | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen ürünün stok ID'sidir. -1 girildiði takdirde rasgele olarak ID atanmaktadýr.  | Evet
SubeID | 1 | Stoðun bulunduðu þubenin ID'sidir. | Evet
SirketID | 1 | Stoðun ait olduðu þirketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Stoðun detaylý kodudur. | Evet
StokAdi | "Hýrdavat Kapý Kolu Burak Oda Rozetli Saten" | Stoðun gözüken adýdýr. | Evet
StokKisaKodu |"HRD.KPKL" | Stoðun genel kodudur. Genel kod özel kodlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa koda sahip olmasý önemlidir. | Evet
StokKisaAdi |"Hýrdavat Kapý Kolu" | Stoðun genel adýdýr. Genel ad özel adlarýn parentý olarak düþünülebilir. Ayný kategorideki ürünlerin ayný kisa ada sahip olmasý önemlidir. | Evet
Durum | true | Stok kartýnýn aktif veya pasif olduðunu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yalnýzca fiziksel bir malý iþaret etmek durumunda deðildir. Gelir-gider hareketleri gibi iþlemler de stok olarak düþünülmektedir dolayýsýyla ne tür bir stok olduðunu belirtmek için TipID bulunmaktadýr. | Evet
StokMuhasebeID | 201 | Stoklarýn muhasebesebesi farklý þekilde iþlenebilir. Stok muhasebe ID hakkýnda detaylý bilgi için muhasebe bölümünü inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanýcý hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine çevrilmesi içindir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine çevrilmesi içindir. | Opsiyonel
Kalinlik | 10.0 | Stok kartýnýn fizikel kalýnlýðýdýr. | Opsiyonel
En | 10.0 | Stok kartýnýn fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kartýnýn fizikel boyudur. | Opsiyonel
Yoðunluk | 3.0 | Stok kartýnýn fizikel yoðunluðudur. | Opsiyonel
Agirlik | 5.0 | Stok kartýnýn fizikel aðýrlýðýdýr. | Opsiyonel
Kod1ID | null | Stok kartlarýný hiyerarþik gruplandýrmak için kullanýlýr. Örnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | Ürün etiketleri icindir. Örnek | Opsiyonel
SablonID | null | Ürün ekleme þablonu varsa girilmelidir. | Opsiyonel

>##### Ürün oluþtururken döküman altýndaki örnek senaryo üzerinden gidebilirsiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Kullanýcýlar 


## End-point: Kullanýcýlarý Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Kullanicilar?KulID=87
>```
### Query Params

|Param|value|
|---|---|
|KulID|87|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Kullanýcý Gruplar 


## End-point: Kullanýcý Gruplarý Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/KullaniciGruplar
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Yetkiler 


## End-point: Yetkileri Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Yetkiler
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Yetkiler Alt 


## End-point: Yetkiler Alt Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/YetkilerAlt
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Þubeler 


## End-point: Þubeleri Getir
Bütün þubeleri getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Subeler/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Þubeleri Oluþtur
Yeni bir þube oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Þubeleri Düzenle
Var olan þubeyi düzenlemektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Þubeleri Sil
Mevcut þubeyi silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Takvim 


## End-point: Takvim Getir
Bütün takvimleri getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Takvim/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Takvimleri Oluþtur
Yeni bir takvim oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Þirketler 


## End-point: Þirketleri Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Sirketler/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Þirketi Oluþtur
Yeni bir þirket oluþturmaktadýr.
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
            "SokakAdi": "kýopklo",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Þirketi Düzenle
Var olan þirketi düzenlemektedir.
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
            "SokakAdi": "kýopklo",
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Þirketi Sil
Mevcut þirketi silmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Sözleþme 


## End-point: Sözleþmeleri Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Sozlesme
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sözleþme Oluþtur
Yeni bir cari oluþturmaktadýr.

###### Mevcut vergi dairelerini görmek için API dökümanýndan Vergi Dairesi kýsmýný inceleyiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sözleþme Düzenle
Yeni bir cari oluþturmaktadýr.

###### Mevcut vergi dairelerini görmek için API dökümanýndan Vergi Dairesi kýsmýný inceleyiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sözleþme Sil
Mevcut cariyi silmektedir

###### Bu iþlemin geri dönüþü yoktur. Silmeden önce bu carinin hareketler ve bankalarla ile iliþkisini kesmelisiniz.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Ýthalat Ýhracatlar 


## End-point: Ýthalat-ihracat Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/IthalatIhracat
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Plasiyer 


## End-point: Plasiyerleri Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Proje 


## End-point: Projeleri Getir
Bütün cari listelerini ya da istenilen kýsýttaki cariyi getirmektedir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Masraf Merkezi 


## End-point: Masraf Merkezi Getir
StartFragment

Sistemde kayýtlý olan bütün masraf merkezi kartlarýnýn görüntülendiði alandýr.
### Method: GET
>```
>{{BaseUrl}}/api/MasrafMerkezi/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Masraf Merkezi Ekle
StartFragment

Yeni bir masraf merkezi oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Sipariþ 


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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Üretim 


## End-point: Recete
Üretim reçete bilgilerini listeleyebildiðiniz kýsýmdýr.
### Method: GET
>```
>{{BaseUrl}}/api/UrRecete
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Recete Operasyon Hammadde
Üretim reçete operasyon hammadde bilgilerini listeleyebildiðiniz kýsýmdýr.
### Method: GET
>```
>{{BaseUrl}}/api/UrReceteOperasyonHammadde
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Recete Operasyon Mamul
Üretim reçete operasyon mamul bilgilerini listeleyebildiðiniz kýsýmdýr.
### Method: GET
>```
>{{BaseUrl}}/api/UrReceteOperasyonMamul
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Üretim Hareketi 


## End-point: UrAkisOperasyonPersonel
Üretim akýþ operasyon personel bilgilerini listeleyebildiðiniz kýsýmdýr.
### Method: GET
>```
>{{BaseUrl}}/api/UrAkisOperasyonPersonel
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: UrAkisOperasyonMamul
Üretim akýþ operasyon mamul bilgilerini listeleyebildiðiniz kýsýmdýr.
### Method: GET
>```
>{{BaseUrl}}/api/UrAkisOperasyonMamul
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: UrAkisOperasyonHammadde
Üretim akýþ operasyon hammadde bilgilerini listeleyebildiðiniz kýsýmdýr.
### Method: GET
>```
>{{BaseUrl}}/api/UrAkisOperasyonHammadde
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Görevler 


## End-point: Görevler
Görev bilgilerini listeleyebildiðiniz kýsýmdýr.
### Method: GET
>```
>{{BaseUrl}}/api/Gorevler
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Görev Kullanicilari
Görev kullanýcý bilgilerini listeleyebildiðiniz kýsýmdýr.
### Method: GET
>```
>{{BaseUrl}}/api/GorevKullanicilari
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Görev Hareketleri
Görev hareket bilgilerini listeleyebildiðiniz kýsýmdýr.
### Method: GET
>```
>{{BaseUrl}}/api/GorevHareketleri
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Görevler Alt
Alt görev bilgilerini listeleyebildiðiniz kýsýmdýr.

Not: Henüz aktif deðildir.
### Method: GET
>```
>{{BaseUrl}}/api/GorevlerAlt
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Stok Vergi 


## End-point: Stok Vergi Getir
Sistemde kayýtlý olan bütün stok vergi kartlarýnýn görüntülendiði alandýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stok Vergi Ekle
StartFragment

Yeni bir stok vergi kartý oluþturmaktadýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stok Vergi Düzenle
Stoktaki bir ürünü düzenlemek içindir.

###### Stok eklemek ile düzenlemek arasýndaki fark KayitTipi=2 olmasýdýr ve StokID dýþýndaki parametrelerin zorunlu olmamasýdýr.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Stok Vergi Sil
Stoktaki bir ürünü silmek içindir.

######  Stok silmek ile düzenlemek arasýndaki fark KayitTipi=-1 olmasýdýr. Stoðu silerken baðlý olduðu bütün fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
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



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: New Request
### Method: GET
>```
>undefined
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
_________________________________________________
Powered By: [postman-to-markdown](https://github.com/bautistaj/postman-to-markdown/)
