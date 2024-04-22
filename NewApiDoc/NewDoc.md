# Project: Aaro Api
Aaro Yaz�l�m web API d�k�mantasyonuna ho� geldiniz. API arac�l���yla Aaro Erp u� noktalar�na eri�im sa�layarak stok, cari veya banka gibi �e�itli kalemler i�in sorgularda bulunabilirsiniz.

API ile Aaro Web aray�z� ile yap�lan i�lemlerin b�y�k bir k�sm�n� ger�ekle�tirebilirsiniz. �retim mod�lleri hen�z aktif halde de�ildir.

Dillere g�re ay�rd���m�z siyah alanda kod �rnekleri g�rebilirsiniz. Ayn� b�lgeden dil de�i�imini ger�ekle�tirebilirsiniz.

Talepleriniz i�in l�tfen [Github](https://github.com/AaroYazilim) sayfam�z� ziyaret edin.
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


## End-point: Stoktaki �r�nleri Getir
Bu u� nokta ile stoklardaki �r�nleri toplu olarak ya da belirli bir k�s�t ile getirebilirsiniz.
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

## End-point: Stoktaki �r�nleri Getir Min
Bu u� nokta ile stoklardaki �r�nleri toplu olarak ya da belirli bir k�s�t ile getirebilirsiniz.


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
Yeni bir stok kart� eklemek i�in  
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

### Sorgu Body JSON a��klamas�

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| StokID | \-1 | Eklenilen �r�n�n stok ID'sidir. -1 girildi�i takdirde rasgele olarak ID atanmaktad�r. | Evet |
| SubeID | 1 | Sto�un bulundu�u �ubenin ID'sidir. | Evet |
| SirketID | 1 | Sto�un ait oldu�u �irketin ID'sidir. | Evet |
| StokKodu | "HRD.KPKL.00164" | Sto�un detayl� kodudur. | Evet |
| StokAdi | "H�rdavat Kap� Kolu Burak Oda Rozetli Saten" | Sto�un g�z�ken ad�d�r. | Evet |
| StokKisaKodu | "HRD.KPKL" | Sto�un genel kodudur. Genel kod �zel kodlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa koda sahip olmas� �nemlidir. | Evet |
| StokKisaAdi | "H�rdavat Kap� Kolu" | Sto�un genel ad�d�r. Genel ad �zel adlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa ada sahip olmas� �nemlidir. | Evet |
| Durum | true | Stok kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet |
| TipID | 105001 | Aaro'da stok yaln�zca fiziksel bir mal� i�aret etmek durumunda de�ildir. Gelir-gider hareketleri gibi i�lemler de stok olarak d���n�lmektedir dolay�s�yla ne t�r bir stok oldu�unu belirtmek i�in TipID bulunmaktad�r. | Evet |
| StokMuhasebeID | 201 | Stoklar�n muhasebesebesi farkl� �ekilde i�lenebilir. Stok muhasebe ID hakk�nda detayl� bilgi i�in muhasebe b�l�m�n� inceleyiniz | Evet |
| Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Evet |
| Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel |
| Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel |
| CevirimBrm2 | null | Birim 1'in birim 2 cinsine �evrilmesi i�indir. | Opsiyonel |
| CevirimBrm3 | null | Birim 1'in birim 3 cinsine �evrilmesi i�indir. | Opsiyonel |
| Kalinlik | 10.0 | Stok kart�n�n fizikel kal�nl���d�r. | Opsiyonel |
| En | 10.0 | Stok kart�n�n fizikel enidir. | Opsiyonel |
| Boy | 10.0 | Stok kart�n�n fizikel boyudur. | Opsiyonel |
| Yo�unluk | 3.0 | Stok kart�n�n fizikel yo�unlu�udur. | Opsiyonel |
| Agirlik | 5.0 | Stok kart�n�n fizikel a��rl���d�r. | Opsiyonel |
| Kod1ID | null | Stok kartlar�n� hiyerar�ik grupland�rmak i�in kullan�l�r. �rnek: Elektronik -> Bilgisayar -> HP | Opsiyonel |
| Etiket1ID | null | �r�n etiketleri icindir. �rnek | Opsiyonel |
| SablonID | null | �r�n ekleme �ablonu varsa girilmelidir. | Opsiyonel |
| TakipYontemi | 0: Normal  <br>1: Lot  <br>2:Seri | Seri, Lot bilgilerinin girilmesi i�in kullan�l�r. |  |

> &lt;h5 &gt;�r�n olu�tururken d�k�man alt�ndaki �rnek senaryo �zerinden gidebilirsiniz.&lt;/h5&gt;
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

## End-point: Stok Kod A�ac� Toplu Ekle
Yeni bir kod kart� eklemek i�in  
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

### Sorgu Body JSON a��klamas�

| Parametre | �rnek De�er | Tan�m |
| --- | --- | --- |
| SubeID | 1 | Kodun bulundu�u �ubenin ID'sidir. |
| SirketID | 1 | Kodun ait oldu�u �irketin ID'sidir. |
| Kod1 | "Kod 1 ad�" | Kod 1 g�z�ken ad�d�r. |
| TipID | 3001 | Stok kart� oldu�unu belirtir. |
| Tip2ID | 105001 | Aaro'da stok yaln�zca fiziksel bir mal� i�aret etmek durumunda de�ildir. Gelir-gider hareketleri gibi i�lemler de stok olarak d���n�lmektedir dolay�s�yla ne t�r bir stok oldu�unu belirtmek i�in Tip2ID belirtilmelidir. |

> _**Kartlarda yer alan hiyerar�ik s�ralamay� sa�layan kod a�ac� b�l�m�nde �ncelikle kodlar�n olu�turulmas� gerekmektedir. Kod ad�n� yollayarak olu�turabilirsiniz. Kodlar hiyerar�ik olarak olu�turulur. 6 adet kod yap�s� olu�turacaksak Kod 1-> Kod 2-> Kod 3 -> Kod 4 -> Kod 5-> Kod 6 �eklinde ad girmeliyiz. �st kodlar olmadan alt kodlar� olu�turamazs�n�z.**_ 
  

| Parametre | TipID | Tip2ID |
| --- | --- | --- |
| Banka | 6002 |  |
| Kasa | 5001 |  |
| Cari | 2001 |  |
| Personel | 1401 |  |
| Re�ete | 12010 |  |
| Stok | 3001 | 105001 |
| Demirba� | 3001 | 105003 |
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
            "Kod1": "k�rtasiye",
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
        "Kod1": "k�rtasiye",
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
Yeni bir etiket kart� eklemek i�in  
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

### Sorgu Body JSON a��klamas�

| Parametre | �rnek De�er | Tan�m |
| --- | --- | --- |
| SubeID | 1 | Etiketin bulundu�u �ubenin ID'sidir. |
| SirketID | 1 | Etiketin ait oldu�u �irketin ID'sidir. |
| EtiketAdi | "Etiket 1 ad�" | Etiket 1 g�z�ken ad�d�r. |
| TipID | 3001 | Stok kart� oldu�unu belirtir. |
| Tip2ID | 105001 | Aaro'da stok yaln�zca fiziksel bir mal� i�aret etmek durumunda de�ildir. Gelir-gider hareketleri gibi i�lemler de stok olarak d���n�lmektedir dolay�s�yla ne t�r bir stok oldu�unu belirtmek i�in Tip2ID belirtilmelidir. |
| Seviye | 1 | Etiketin seviyesini belirtir. |

> _**Kartlarda yer alan hiyerar�ik s�ralamay� sa�layan etiket b�l�m�nde �ncelikle etiketlerin olu�turulmas� gerekmektedir. etiket ad�n� yollayarak olu�turabilirsiniz.**_ 
  

| Parametre | TipID | Tip2ID |
| --- | --- | --- |
| Banka | 6002 |  |
| Kasa | 5001 |  |
| Cari | 2001 |  |
| Personel | 1401 |  |
| Re�ete | 12010 |  |
| Stok | 3001 | 105001 |
| Demirba� | 3001 | 105003 |
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

## End-point: Stok Kod A�ac� Toplu Listele
Kod a�ac�n� toplu olarak listeleyebilirsiniz.
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

## End-point: Stok D�zenle
Stoktaki bir �r�n� d�zenlemek i�indir.

###### Stok eklemek ile d�zenlemek aras�ndaki fark KayitTipi=2 olmas�d�r ve StokID d���ndaki parametrelerin zorunlu olmamas�d�r.
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

## End-point: Stoktaki �r�n� Sil
Stoktaki bir �r�n� silmek i�indir.

######  Stok silmek ile d�zenlemek aras�ndaki fark KayitTipi=-1 olmas�d�r. Sto�u silerken ba�l� oldu�u b�t�n fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata d�necektir.
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
Bu u� nokta ile belirtilen k�s�tlara g�re stok hareketlerini listeleyebilirsiniz.
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

## End-point: Sipari� Hareketleri Liste
Bu u� nokta ile belirtilen k�s�tlara g�re sipari� hareketlerini listeleyebilirsiniz.
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
Bu u� nokta ile belirtilen k�s�tlara g�re stok depo miktar minimum maksimum hareketlerini listeleyebilirsiniz.
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "StokAdi": "Otomatik Aktar�m Stok Kart�",
            "EsnekAramaKisiti": "STOKOTO00000001 Otomatik Aktar�m Stok Kart� DPM Depom",
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
            "SubeAdi": "T�m 3",
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
            "StokAdi": "Otomatik Aktar�m Stok Kart�",
            "EsnekAramaKisiti": "STOKOTO00000001 Otomatik Aktar�m Stok Kart� GG GelirGider Depo",
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
Yeni bir stok depo miktar min-max kart� eklemek i�in kullan�l�r.  
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |
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

## End-point: StokDepo Miktar Min-Max D�zenle
Stok Depo Miktar Min-Max'� d�zenlemek i�indir.
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
Stok Depo Miktar Min-Max'� silmek i�indir.
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
Bu u� nokta ile seri lot bilgilerini toplu olarak ya da belirli bir k�s�t ile getirebilirsiniz.
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "StokAdi": "Otomatik Aktar�m Stok Kart�",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "StokAdi": "�lk Stok Kart�m",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "StokAdi": "�lk Stok Kart�m",
            "IsEmriNo": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
Yeni bir stok kart� eklemek i�in  
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

### Sorgu Body JSON a��klamas�

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| SubeID | 1 | Seri Lotun bulundu�u �ubenin ID'sidir. | Evet |
| SirketID | 1 | Seri Lotun ait oldu�u �irketin ID'sidir. | Evet |
| SeriLotKodu | "000001" | Seri Lotun kodudur. | Evet |
| SeriLotAdi | "" | Seri Lotun ad�d�r. Bo� string yollanmal�d�r. | Evet |
| Durum | true | Seri lot kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet |
| TipID | 153001 | Seri : 153001  <br>Lot: 153002 | Evet |
| StokID | 231 | Serinin ba�l� oldu�u sto�un idsini belirtir | Evet |
| SonKullanmaTarihi | null | Seri / Lotun son kullanma tarihini belirtir | Evet |
| IsEmriID | null | Seri Lotun ba�l� oldu�u i� emrini belirtir. | Evet |
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

## End-point: Seri Lot D�zenle
Seri Lot bilgilerini d�zenlemek i�indir.
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
Stoktaki bir �r�n� silmek i�indir.

######  Stok silmek ile d�zenlemek aras�ndaki fark KayitTipi=-1 olmas�d�r. Sto�u silerken ba�l� oldu�u b�t�n fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata d�necektir.
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
Bu u� nokta ile belirtilen k�s�tlara g�re seri lot hareketlerini listeleyebilirsiniz.
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
            "StokID": 202,
            "StokKodu": "STOKOTO00000001",
            "StokAdi": "Otomatik Aktar�m Stok Kart�",
            "TipID": 10009,
            "TipKodu": "SIR",
            "TipAdi": "Sat�� �rsaliyesi",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
            "StokID": 202,
            "StokKodu": "STOKOTO00000001",
            "StokAdi": "Otomatik Aktar�m Stok Kart�",
            "TipID": 10009,
            "TipKodu": "SIR",
            "TipAdi": "Sat�� �rsaliyesi",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "�lk Stok Kart�m",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Aras� Transfer",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "�lk Stok Kart�m",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Aras� Transfer",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "�lk Stok Kart�m",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Aras� Transfer",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "�lk Stok Kart�m",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Aras� Transfer",
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

## End-point: Seri Lot H�zl� Kay�t
### Sorgu Body JSON a��klamas�

**�n Bilgi**

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| StokHareketID | 202 | Hareketteki sto�un idsini belirtir. | Evet |

**Sat�rlar**

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| HareketID | \-1 | Seri lot sat�r�n�n id sini belirtir. Yeni bir kay�tsa yollanmas�na gerek yoktur. D�zenleme ya da silme yap�l�yorsa hangi sat�r oldu�unun yollanmas� gerekmektedir. |  |
| StokRafID | 1 | Raf takibi yap�l�yorsa se�ilen raf�n id bilgisini belirtir. |  |
| PaketID | 1 | Paket takibi yap�l�yorsa se�ilen raf�n id bilgisini belirtir. |  |
| YeniKodOlustur | 1 ya da 0 | Yeni bir seri/lot olu�turuluyorsa bu bilgi g�nderilir. |  |
| SeriLotID | 5 | Seri lotun id sini belirtir. Yeni bir kay�tsa yollanmas�na gerek yoktur. D�zenleme ya da silme yap�l�yorsa hangi sat�r oldu�unun yollanmas� gerekmektedir. |  |
| SeriLotKodu | 500016 | D�zenlenen seri lotun yeni kodunu belirtir. | Yeni seri lot olu�turulacaksa zorunlu. |
| Miktar | 1.0000 | Seri lot sat�r�n�n miktar�n� belirtir. |  |
| UrAkisOperasyonAnaMamulSeriLotID | 1 | �retim hareketinin ana mamulunde t�m hammaddelerin seri lotlar�n�n takibi yap�lacaksa kullan�l�r. |  |
| TransferStokRafID | 1 | Depolar aras� transfer de transfer edilen raf id bilgisini belirtir. | Depolar aras� transfer i�in zorunlu |
| TransferPaketID | 1 | Depolar aras� transfer de transfer edilen paket id bilgisini belirtir. | Depolar aras� transfer i�in zorunlu |
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
                "SeriLotKodu": "500011", //Yeni seri lot olu�turulacaksa zorunlu.
                "Miktar": 3.0000,
                "YeniKodOlustur": false,  //Yeni seri lot olu�turulacaksa true olmal�.
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
        "Mesaj": "Seri/Lot tan�mlari ve Hareketleri i�lendi"
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Seri Lot H�zl� Kay�t Getir
### Sorgu Body JSON a��klamas�

**�n Bilgi**

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| StokHareketID | 202 | Hareketteki sto�un idsini belirtir. | Evet |
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
            "StokAdi": "�lk Stok Kart�m",
            "IsEmriUretimIliskiTakibi": false,
            "TakipYontemiKodOnEki": null,
            "StokHareketID": 649,
            "OtomatikSeriLotKoduHazirla": false
        },
        "Satirlar": [
            {
                "HareketID": 385,
                "StokRafID": 8,
                "StokRafKodu": "Temizlik Raf�",
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
                "StokRafKodu": "Temizlik Raf�",
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
Yeni bir seri lot hareketini eklemek i�in  
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

### Sorgu Body JSON a��klamas�

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| SubeID | 1 | Seri Lot hareketlerinin bulundu�u �ubenin ID'sidir. | Evet |
| SirketID | 1 | Seri Lot hareketlerinin ait oldu�u �irketin ID'sidir. | Evet |
| Durum | true | Seri lot hareketlerinin aktif veya pasif oldu�unu belirlemektedir | Evet |
| SeriLotID | 11 | Harekete ba�l� olan seri lotun idsidir. | Evet |
| StokID | 231 | Serinin ba�l� oldu�u sto�un idsini belirtir | Evet |
| Tarih | 2023-08-23 | Seri / Lot hareketlerinin tarihini belirtir. | Evet |
| IsEmriID | null | Seri Lotun ba�l� oldu�u i� emrini belirtir. | Evet |
| BA | A | Hareketin bor� mu alacak m� oldu�unu belritir | Evet |
| Miktar | 1.000000 | Hareketin miktar�n� belirtir. | Evet |
| StokHareketID | 202 | Hareketteki sto�un idsini belirtir. | Evet |
| Aciklama | a��klama | Hareketin a��klamas�n� belirtir. | Evet |
| UrAkisOperasyonAnaMamulSeriLotID | 1 |  | Hay�r |
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

## End-point: Seri Lot Hareketleri D�zenle
Seri Lot bilgilerini d�zenlemek i�indir.
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
            "StokID": 201,
            "StokKodu": "000000000000001",
            "StokAdi": "�lk Stok Kart�m",
            "TipID": 10019,
            "TipKodu": "DAT",
            "TipAdi": "Depolar Aras� Transfer",
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
Seri Lot Hareketini silmek i�indir.
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
Bu u� nokta ile raf bilgilerini toplu olarak ya da belirli bir k�s�t ile getirebilirsiniz.
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
            "StokRafKodu": "K�rtasiye Raf�",
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
            "StokRafKodu": "Teknoloji Raf�",
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
            "StokRafKodu": "Temizlik Raf�",
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
Yeni bir raf kart� eklemek i�in  
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

### Sorgu Body JSON a��klamas�

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| StokRafKodu | 02A.02.02 | Raf�n kodudur. | Evet |
| Aciklama | aciklama | Raf ii�in a��klamay� ifade eder.Raf�n ad� girilebilir. | Evet |
| Durum | true | Raf kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet |
| DepoID | 1 | Raf�n deposunu belirtir. | Evet |
| KonumX | 1 | Raf�n x konumundaki durumunu belirtir. | Evet |
| KonumY | 1 | Raf�n y konumundaki durumunu belirtir. | Evet |
| KonumZ | 1 | Raf�n z konumundaki durumunu belirtir. | Evet |
| En | 1.000000 | Raf�n enini belirtir. | Evet |
| Boy | 1.000000 | Raf�n boyunu belirtir. | Evet |
| Y�kseklik | 1.000000 | Raf�n y�ksekli�ini belirtir. | Evet |
| EtiketKonum | 0 | Etiketin konumunun alt ya da �st olmas�n� belirtir.  <br>�st:0  <br>Alt:1 | Evet |
| EtiketKonumBasilsin | true | Etiketin konumunun raf ��kt�s�na bas�l�p bas�lmayaca��n� belirtir. | Evet |
| AgirlikKapasitesi | 1.000000 | Raf�n a��rl�k kapasitesini belirtir. | Evet |
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

## End-point: Raf D�zenle
Raf kart� d�zenlemek i�in  
KayitTipi: 2 T�m API'de kayd� d�zenlemek anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 2 T�m API'de kayd� d�zenlemek anlam�na gelmektedir. |

### Sorgu Body JSON a��klamas�

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| StokRafID | 14 | D�zenlenmek istenen raf� belirtir. | Evet |
| StokRafKodu | 02A.02.02 | Raf�n kodudur. | Evet |
| Aciklama | aciklama | Raf ii�in a��klamay� ifade eder.Raf�n ad� girilebilir. | Evet |
| Durum | true | Raf kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet |
| DepoID | 1 | Raf�n deposunu belirtir. | Evet |
| KonumX | 1 | Raf�n x konumundaki durumunu belirtir. | Evet |
| KonumY | 1 | Raf�n y konumundaki durumunu belirtir. | Evet |
| KonumZ | 1 | Raf�n z konumundaki durumunu belirtir. | Evet |
| En | 1.000000 | Raf�n enini belirtir. | Evet |
| Boy | 1.000000 | Raf�n boyunu belirtir. | Evet |
| Y�kseklik | 1.000000 | Raf�n y�ksekli�ini belirtir. | Evet |
| EtiketKonum | 0 | Etiketin konumunun alt ya da �st olmas�n� belirtir.  <br>�st:0  <br>Alt:1 | Evet |
| EtiketKonumBasilsin | true | Etiketin konumunun raf ��kt�s�na bas�l�p bas�lmayaca��n� belirtir. | Evet |
| AgirlikKapasitesi | 1.000000 | Raf�n a��rl�k kapasitesini belirtir. | Evet |
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
Raf kart�n� silmek i�indir.
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
Bu u� nokta ile paket bilgilerini toplu olarak ya da belirli bir k�s�t ile getirebilirsiniz.
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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
Yeni bir paket kart� eklemek i�in  
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

### Sorgu Body JSON a��klamas�

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| PaketKodu | 000001 | Paketin kodudur. | Evet |
| PaketAdi | paket | Paketin ad�n� belirtir. Bo� b�rak�labilir. | Evet |
| Durum | true | Paket kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet |
| SubeID | 1 | Paketin bulundu�u �ubeyi belirtir. | Evet |
| SirketID | 1 | Paketin bulundu�u �irketi belirtir. | Evet |
| TipID | 156001 | Paketin tip idsini belirtir.  <br>Paket : 156001 | Evet |
| PaketKapCinsID | 1 | Paketin cins id sini belritir. Kutu,Koli vb. | Evet |
| Sira | 0 | Paketin s�ras�n� belirtir. | Evet |

### Paket Kap Cins Kodlar�

| PaketKapCinsID | PaketKapCinsKodu | PaketKapCinsAdi |
| --- | --- | --- |
| 1 | BA | Varil |
| 2 | BE | Boh�a |
| 3 | BG | Torba |
| 4 | BH | Demet |
| 5 | BI | ��p kutusu |
| 6 | BJ | Kova |
| 7 | BK | Sepet |
| 8 | BX | Kutu |
| 9 | CB | Bira kasas� |
| 10 | CH | Sand�k |
| 11 | CI | Teneke kutu |
| 12 | CK | F��� |
| 13 | CN | Konteyner |
| 14 | CR | Kasa |
| 15 | DK | Karton kasa |
| 16 | DR | Bidon |
| 17 | EC | Plastik torba |
| 18 | FC | Meyve kasas� |
| 19 | JR | Kavanoz |
| 20 | LV | Liftvan |
| 21 | NE | Ambalajs�z |
| 22 | SA | �uval |
| 23 | SU | Bavul |
| 24 | TN | Teneke |
| 25 | VG | D�kme gaz |
| 26 | VL | D�kme s�v� |
| 27 | VO | D�kme kat� |
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

## End-point: Paket D�zenle
Paket kart� d�zenlemek i�in  
KayitTipi: 2 T�m API'de kayd� d�zenlemek anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 2 T�m API'de kayd� d�zenlemek anlam�na gelmektedir. |

### Sorgu Body JSON a��klamas�

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| PaketID | 26 | Paketin idsidir. | Evet |
| PaketKodu | 000001 | Paketin kodudur. | Evet |
| PaketAdi | paket | Paketin ad�n� belirtir. Bo� b�rak�labilir. | Evet |
| Durum | true | Paket kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet |
| SubeID | 1 | Paketin bulundu�u �ubeyi belirtir. | Evet |
| SirketID | 1 | Paketin bulundu�u �irketi belirtir. | Evet |
| TipID | 156001 | Paketin tip idsini belirtir.  <br>Paket : 156001 | Evet |
| PaketKapCinsID | 1 | Paketin cins id sini belritir. Kutu,Koli vb. | Evet |
| Sira | 0 | Paketin s�ras�n� belirtir. | Evet |
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
Paket kart�n� silmek i�indir.
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


## End-point: Gelir-Gider Kartlar�n� Getir
Sistemde kay�tl� olan b�t�n gelir gider kartlar�n�n g�r�nt�lendi�i aland�r.
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
Yeni bir gelir gider olu�turmaktad�r.
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

## End-point: Gelir Gider D�zenle
Var olan gelir gideri d�zenlemektedir.
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
        "SirketAdi": "�irket 1",
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
Bu u� nokta ile belirtilen k�s�tlara g�re stok hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/GelirGiderHareketleri
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Demirbas 


## End-point: Demirbas Kartlar�n� Getir
StartFragment

Sistemde kay�tl� olan b�t�n demirba� kartlar�n�n g�r�nt�lendi�i aland�r.
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
Yeni bir demirba� olu�turmaktad�r.
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

## End-point: Demirbas D�zenle
Var olan demirba�� d�zenlemektedir.
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
        "SirketAdi": "�irket 1",
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
Mevcut demirba�� silmektedir.
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
Bu u� nokta ile belirtilen k�s�tlara g�re stok hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/DemirbasHareketleri
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Barkod 


## End-point: Stoktaki �r�n�n Bakodunu Getir
Aaro bir �r�n i�in sonsuz say�da barkodu kabul etmektedir. Dolay�s�yla barkod getir de�il barkodlar� getir �ekline �al��maktad�r.

###### Birden fazla sonu� gelebilmektedir
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

## End-point: Stoktaki �r�ne Barkod Ekle
Yeni bir stok kart� eklemek i�in
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.
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

## End-point: Stoktaki �r�n�n Barkodunu D�zenle
De�i�tirmek istedi�iniz barkod i�in a�a��daki yap�y� kullan�n�z.

###### Sadece kay�t tipi 2 olarak de�i�mektedir. BarkodID'si ise 2590 olarak girilerek istenilen barkoda ula��lm��t�r.
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

## End-point: Stoktaki �r�n�n Barkodunu Sil
Silmek istedi�iniz barkod i�in a�a��daki yap�y� kullan�n�z.

###### Sadece kay�t tipi -1 olarak de�i�mektedir.
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


## End-point: Depolar� Getir
Sistemde kay�tl� olan b�t�n depo kartlar�n�n g�r�nt�lendi�i aland�r.
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

## End-point: Depo Olu�tur
Yeni bir depo olu�turmaktad�r.
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

## End-point: Depoyu D�zenle
Mevcut bir deponun d�zeltilmesi i�in kullan�lmaktad�r.

######  Depo eklemekten farkl� olarak ID eklenmesi gerekmektedir.
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
Mevcut bir deponun silinmesi i�in kullan�lmaktad�r.

######  Depoyu silmeden �nce depoya ait b�t�n hareketlerin ve stoklar silindi�inden/ta��nd���ndan emin olunuz. Aksi takdirde silme i�lemi ger�ekle�meyecektir.
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
# ?? Collection: D�viz 


## End-point: D�vizleri Getir
Olu�turulmu� b�t�n d�vizleri getirmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m | �rnek |
| --- | --- | --- | --- |
| EsnekAramaKisiti | String | Diledi�iniz stringe g�re listeleme yapabilirsiniz. Doviz kodunda, Doviz ad�nda girilen string'e g�re arama yapar. | TL |
| DovizID | Integer | Belirtilen ID'li d�viz kart�n� getirir. | 1 |
| OlsID | Integer | Olu�turan ki�i ID'sine g�re depo kartlar�n� getirmektedir. | 1234 |
| DgsID | Integer | De�i�tiren ki�i ID'sine g�re depo kartlar�n� getirmektedir. | 1234 |
| OlsTarBas | Datetime | Belirtilen tarihten itibaren olu�turulmu� depo kartlar�n� getirmektedir. | 01.01.2021 |
| OlsTarBit | Datetime | Belirtilen tarihe kadar olu�turulmu� depo kartlar�n� getirmektedir. | 01.01.2021 |
| DgsTarBas | Datetime | Belirtilen tarihten itibaren de�i�tirilmi� depo kartlar�n� getirmektedir. | 01.01.2021 |
| DgsTarBit | Datetime | Belirtilen tarihe kadar de�i�tirilmi� depo kartlar�n� getirmektedir. | 01.01.2021 |
| SayfaSatirSayisi | Integer | Limitli say�da depo getirmek i�in kullan�lmaktad�r. | 10 |
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
            "OlsAdi": "T�m�",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "T�m�",
            "EsnekAramaKisiti": "TRY T�rk Liras� TL ",
            "DovizID": 1,
            "DovizKodu": "TRY",
            "DovizAdi": "T�rk Liras� TL",
            "DovizSembol": "?",
            "YaziylaKurus": "Kuru�",
            "Yaziyla": "TL"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.223",
            "DgsTar": "2022-10-20T08:14:07.223",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "T�m�",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "T�m�",
            "EsnekAramaKisiti": "USD Amerikan Dolar� ",
            "DovizID": 2,
            "DovizKodu": "USD",
            "DovizAdi": "Amerikan Dolar�",
            "DovizSembol": "$",
            "YaziylaKurus": "Sent",
            "Yaziyla": "Dolar"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.227",
            "DgsTar": "2022-10-20T08:14:07.227",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "T�m�",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "T�m�",
            "EsnekAramaKisiti": "EUR Euro ",
            "DovizID": 3,
            "DovizKodu": "EUR",
            "DovizAdi": "Euro",
            "DovizSembol": "�",
            "YaziylaKurus": "Sent",
            "Yaziyla": "Euro"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.23",
            "DgsTar": "2022-10-20T08:14:07.23",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "T�m�",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "T�m�",
            "EsnekAramaKisiti": "GBP �ngiliz Sterlini ",
            "DovizID": 4,
            "DovizKodu": "GBP",
            "DovizAdi": "�ngiliz Sterlini",
            "DovizSembol": "�",
            "YaziylaKurus": "Pence",
            "Yaziyla": "Pound"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.23",
            "DgsTar": "2022-10-20T08:14:07.23",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "T�m�",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "T�m�",
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
            "OlsAdi": "T�m�",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "T�m�",
            "EsnekAramaKisiti": "CNY �in Yuan� ",
            "DovizID": 6,
            "DovizKodu": "CNY",
            "DovizAdi": "�in Yuan�",
            "DovizSembol": "�",
            "YaziylaKurus": "Jiao",
            "Yaziyla": "Yuan"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.233",
            "DgsTar": "2022-10-20T08:14:07.233",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "T�m�",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "T�m�",
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
            "OlsAdi": "T�m�",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "T�m�",
            "EsnekAramaKisiti": "XAU Alt�n ",
            "DovizID": 8,
            "DovizKodu": "XAU",
            "DovizAdi": "Alt�n",
            "DovizSembol": "A",
            "YaziylaKurus": "Gram Alt�n",
            "Yaziyla": "Nokta"
        },
        {
            "OlsTar": "2022-10-20T08:14:07.237",
            "DgsTar": "2022-10-20T08:14:07.237",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "T�m�",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "T�m�",
            "EsnekAramaKisiti": "XAG G�m�� ",
            "DovizID": 9,
            "DovizKodu": "XAG",
            "DovizAdi": "G�m��",
            "DovizSembol": "G",
            "YaziylaKurus": "Gram G�m��",
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

## End-point: D�viz Olu�tur
Yeni bir d�viz eklemek i�in kullan�lmaktad�r.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 (KayitTipi=1 b�t�n API yap�s�nda �r�n kaydet demektir) |

### Sorgu Body Parametreleri

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| DovizID | \-1 | Eklenilen kart�n d�viz ID'sidir. -1 girildi�i takdirde rasgele olarak ID atanmaktad�r. | Evet |
| DovizKodu | "DPM" | D�viz kodudur. | Evet |
| DovizAdi | "Depom" | D�viz ad�d�r. | Evet |
| DovizSembol | "?" | D�viz sembol�d�r. | Evet |
| YaziylaKurus | "Kuru�" | D�viz cinsinin kuru� i�in belirtti�i add�r. �rn: Kuru�, Cent | Evet |
| Yaziyla | "TL" | D�viz cinsinin okunu�unun yaz� halidir. | Evet |
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

## End-point: D�viz D�zenle
Mevcut bir deponun d�zeltilmesi i�in kullan�lmaktad�r.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 2 (KayitTipi=2 b�t�n API yap�s�nda PUT i�lemine kar��l�k gelmektedir.) |

### Sorgu Body Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| DovizID | Integer | D�zeltmek istedi�iniz d�vizin ID'si |
| DovizKodu | String | D�vize verece�iniz koddur. |
| DovizAdi | String | D�vize verece�iniz ad. |
| DovizSembol | String | D�vize verece�iniz sembol. |
| YaziylaKurus | String | D�vize verece�iniz kuru� okunu�udur. |
| Yaziyla | String | D�vize verece�iniz okunu�tur. |

> **D�viz eklemekten farkl� olarak ID eklenmesi gerekmektedir.**
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

## End-point: D�viz Sil
Mevcut d�viz bilgilerini silmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 (KayitTipi=-1 b�t�n API yap�s�nda DELETE i�lemine kar��l�k gelmektedir.) |

### Sorgu Body Parametreleri

Yaln�zca ID ile de silme i�lemini ger�ekle�tirebilirsiniz.

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| DovizID | Integer | Silmek istedi�iniz d�vizin ID'si |

> **D�vizi silmeden �nce d�vizin kullan�ld��� b�t�n hareketlerin silindi�inden/ta��nd���ndan emin olunuz. Aksi takdirde silme i�lemi ger�ekle�meyecektir.**
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
# ?? Collection: D�viz Kuru 


## End-point: D�viz Kurlar�n� Getir
Olu�turulmu� b�t�n d�viz kur kay�tlar�n� getirmektedir.
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
            "DovizAdi": "Amerikan Dolar�",
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
            "DovizAdi": "�ngiliz Sterlini",
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
            "DovizAdi": "�in Yuan�",
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
            "DovizAdi": "Alt�n",
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
            "DovizAdi": "G�m��",
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
            "DovizAdi": "Amerikan Dolar�",
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

## End-point: D�viz Kurunu Olu�tur
Yeni bir d�viz kuru eklemek i�in kullan�lmaktad�r.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 (KayitTipi=1 b�t�n API yap�s�nda �r�n kaydet demektir) |

### Sorgu Body Parametreleri

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| DovizID | 2 | Eklenilen d�viz kurunun ID'sidir. | Evet |
| Tarih | 2022-05-18 | D�viz kurunun tarihidir. | Hay�r |
| AlisMerkez | 18.566100 |  | Hay�r |
| SatisMerkez | 18.599600 |  | Evet |
| AlisEfektif | 18.553100 |  | Hay�r |
| SatisEfektif | 18.627500 |  | Hay�r |
| AlisSerbest | 18.566100 |  | Hay�r |
| SatisSerbest | 18.599600 |  | Hay�r |
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

## End-point: D�viz Kurunu D�zenle
Mevcut bir d�viz kurunun d�zeltilmesi i�in kullan�lmaktad�r.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 2 (KayitTipi=2 b�t�n API yap�s�nda PUT i�lemine kar��l�k gelmektedir.) |

### Sorgu Body Parametreleri

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| DovizID | 2 | Eklenilen d�viz kurunun ID'sidir. | Evet |
| Tarih | 2022-05-18 | D�viz kurunun tarihidir. | Hay�r |
| AlisMerkez | 18.566100 |  | Hay�r |
| SatisMerkez | 18.599600 |  | Evet |
| AlisEfektif | 18.553100 |  | Hay�r |
| SatisEfektif | 18.627500 |  | Hay�r |
| AlisSerbest | 18.566100 |  | Hay�r |
| SatisSerbest | 18.599600 |  | Hay�r |

> **D�viz kuru eklemekten farkl� olarak ID eklenmesi gerekmektedir.**
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

## End-point: D�viz Kurunu Sil
Mevcut d�viz kuru bilgilerini silmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 (KayitTipi=-1 b�t�n API yap�s�nda DELETE i�lemine kar��l�k gelmektedir.) |

### Sorgu Body Parametreleri

Yaln�zca ID ile de silme i�lemini ger�ekle�tirebilirsiniz.

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| StrID | Integer | Silmek istedi�iniz d�viz kurunun ID'si |
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


## End-point: Vergi Oranlar�n� Getir
B�t�n vergi oranlar�n� ya da istenilen k�s�ttaki vergi kalemleri gelmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/StokVergi
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Vergi Oran� Olu�tur
Yeni bir vergi oran� olu�turmaktad�r.
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

## End-point: Vergi Oran�n� D�zenle
Vergi oran� d�zenlenmektedir.
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

## End-point: Vergi Oran�n� Sil
Vergi oran�n� silmektedir.
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

## End-point: Vergi Dairesi Olu�tur
Yeni bir vergi dairesi olu�turmaktad�r.
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

## End-point: Vergi Dairesi D�zenle
Vergi dairesi d�zenlenmektedir.
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

###### Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu vergi dairesinin hareketlerini silmelisiniz.
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

## End-point: Fiyat Listesi Olu�tur
Yeni bir fiyat listesi olu�turmaktad�r.
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

## End-point: Fiyat Listesi D�zenle
Var olan Fiyat Listesi'ni d�zeltmektedir.
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


######  Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu fiyat listesine ba�l� t�m stoklar�n ve hareketlerin liste ile ili�kisini kesmelisiniz.
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
Yeni bir fiyat listesi olu�turmaktad�r.
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

## End-point: Fiyat Listesi Satir D�zenle
Yeni bir fiyat listesi olu�turmaktad�r.
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


######  Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu fiyat listesine ba�l� t�m stoklar�n ve hareketlerin liste ile ili�kisini kesmelisiniz.
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
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
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

## End-point: Cari Olu�tur
Yeni bir cari olu�turmaktad�r.

\-Cariye adres, ilgili, risk, ziyaret vb. eklenmek istenirse cari olu�turulduktan sonra ilgili api k�sm�ndan eklenmelidir.

###### Mevcut vergi dairelerini g�rmek i�in API d�k�man�ndan Vergi Dairesi k�sm�n� inceleyiniz.
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

## End-point: Cari D�zenle
Mevcut cari d�zenlenmektedir.
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

###### Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu carinin hareketler ve bankalarla ile ili�kisini kesmelisiniz.
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
Bu u� nokta ile belirtilen k�s�tlara g�re cari hareketlerini listeleyebilirsiniz.
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
Sistemde kay�tl� olan b�t�n cari risk kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/CariRisk/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Cari Risk Olu�tur
Yeni bir cari risk olu�turmaktad�r.
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

## End-point: Cari Risk D�zenle
Var olan cari riski d�zenlemeketedir.
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
Sistemde kay�tl� olan b�t�n cari ziyaret kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/CariZiyaret/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Cari Ziyaret Olu�tur
Yeni bir cari ziyaret olu�turmaktad�r.
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

## End-point: Cari Ziyaret D�zenle
Var olan cari ziyareti d�zenlemektedir.
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
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
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

## End-point: CariAdres D�zenle
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


## End-point: �lleri Getir
�ller listesini getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Iller
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: �l Ekle
�l ekleme i�lemi i�in kullan�lmaktad�r.
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

## End-point: �l D�zenle
�l bilgilerini d�zenlemek i�in kullan�lmaktad�r.
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

## End-point: �l Sil
�l bilgisini silmek i�in kullan�lmaktad�r.
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

## End-point: �l�eleri Getir
�l�eler listesini getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Ilceler
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: �l�e Ekle
�l�e ekleme i�lemi i�in kullan�lmaktad�r.
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

## End-point: �l�e D�zenle
�l�e bilgilerini d�zenlemek i�in kullan�lmaktad�r.
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

## End-point: �l�e Sil
�l�e bilgisini silmek i�in kullan�lmaktad�r.
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

## End-point: �lkeleri Getir
�lkeler listesini getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Ulkeler
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: �lke Ekle
�lke ekleme i�lemi i�in kullan�lmaktad�r.
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

## End-point: �lke D�zenle
�lke bilgilerini d�zenlemek i�in kullan�lmaktad�r.
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

## End-point: �lke Sil
�lke bilgisini silmek i�in kullan�lmaktad�r.
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
# ?? Collection: Cari �lgilileri 


## End-point: �lgilileri Getir
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/CariIlgili?CariID=10233
>```
### Query Params

|Param|value|
|---|---|
|CariID|10233|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: �lgili Ekle
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

## End-point: �ligli D�zenle
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

## End-point: �lgili Sil
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


## End-point: Bankalar� Getir
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
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

## End-point: Banka D�zenle
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


## End-point: Kasalar� Getir
Sistemde kay�tl� olan b�t�n kasa kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/Kasa/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Kasa Olu�tur
Yeni bir kasa olu�turmaktad�r.
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

## End-point: Kasa D�zenle
Var olan kasay� d�zenlemektedir.
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
Mevcut kasay� silmektedir.
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
Bu u� nokta ile belirtilen k�s�tlara g�re kasa hareketlerini listeleyebilirsiniz.
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


## End-point: Banka Hesaplar� Getir
Sistemde kay�tl� olan b�t�n banka hesap kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/BankaHesap/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Hesap Olu�tur
StartFragment

Yeni bir banka hesap olu�turmaktad�r.
### Method: POST
>```
>{{BaseUrl}}/api/BankaHesap/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
        "BankaSubeID": 1,
        "HesapKodu": "000000000000100",
        "HesapAdi": "Deneme Banka Kart�",
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

## End-point: Banka Hesap D�zenle
StartFragment

Var olan banka hesab�n� d�zenlemektedir.
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

Mevcut banka hesab�n� silmektedir.
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
Bu u� nokta ile belirtilen k�s�tlara g�re stok hareketlerini listeleyebilirsiniz.
### Method: GET
>```
>{{BaseUrl}}/api/BankaHareketleri
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Banka 


## End-point: Banka Getir
Sistemde kay�tl� olan b�t�n banka kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/Banka/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka Olu�tur
Yeni bir banka olu�turmaktad�r.
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

## End-point: Banka D�zenle
Var olan bankay� d�zenlemektedir.
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
Mevcut bankay� silmektedir.

###### Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu bu bankan�n hareketler ve bankalarla ile ili�kisini kesmelisiniz.
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
# ?? Collection: Hareket T�rleri Alt 


## End-point: Hareket T�rleri Alt Getir
Sistemde kay�tl� olan b�t�n hareket t�rleri alt kartlar�n�n g�r�nt�lendi�i aland�r.
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
            "SubeAdi": "�ubem",
            "SirketKodu": "SRKT",
            "SirketAdi": "�irketim",
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

## End-point: Hareket T�rleri Alt Olu�tur
Yeni bir hareket t�rleri alt� olu�turmaktad�r.
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

## End-point: Hareket T�rleri Alt D�zenle
Var olan hareket t�rleri alt� d�zenlemektedir.
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

## End-point: Hareket T�rleri Alt Sil
Mevcut hareket t�rleri alt� silmektedir.
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
# ?? Collection: A��klamalar 


## End-point: Aciklamalar Getir
Sistemde kay�tl� olan b�t�n a��klama kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/Aciklamalar/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Aciklamalar Olu�tur
Yeni bir a��klama olu�turmaktad�r.
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

## End-point: Aciklamalar D�zenle
Var olan a��klamay� d�zenlemektedir.
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
Mevcut a��klamay� silmektedir.
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
Sistemde kay�tl� olan b�t�n personel giri� ��k�� kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/PerGirisCikis/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: PerGirisCikis Olu�tur
Yeni bir personel giri� ��k�� olu�turmaktad�r.
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

## End-point: PerGirisCikis D�zenle
Var olan personel giri� ��k���n� d�zenlemektedir.
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
Mevcut personel giri� ��k��� silmektedir.
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
Sistemde kay�tl� olan b�t�n takvim sat�r kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/TakvimStr/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: TakvimStr Olu�tur
Yeni bir takvim sat�r� olu�turmaktad�r.
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

## End-point: TakvimStr D�zenle
Var olan takvim sat�r�n� d�zenlemektedir.
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
Mevcut takvim sat�r�n� silmektedir.
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
Sistemde kay�tl� olan b�t�n �ek senet kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>https://localhost:44346/api/CekSenet/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Cek Senet Olu�tur
Yeni bir �ek senet olu�turmaktad�r.
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

## End-point: Cek Senet D�zenle
Var olan �ek seneti d�zenlemektedir.
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
Mevcut �ek seneti silmektedir.
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
Sistemde kay�tl� olan b�t�n makine kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/urMakine/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Makine Olu�tur
Yeni bir makine olu�turmaktad�r.
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
            "Aciklama": "H�zl� Re�eetelerde Kullan�lan makine"
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Makine D�zenle
Var olan makineyi d�zenlemeketedir.
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
            "Aciklama": "H�zl� Re�eetelerde Kullan�lan makine"
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
# ?? Collection: Makine Ar�za 


## End-point: Makine Getir
Sistemde kay�tl� olan b�t�n makine ar�za kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/UrMakineAriza/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Makine Olu�tur
Yeni bir makine ar�zas�n� olu�turmaktad�r.
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

## End-point: Makine D�zenle
Var olan makine ar�zas�n� d�zenlemektedir.
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
Mevcut makine ar�zas�n� silmektedir.
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
Sistemde kay�tl� olan b�t�n operasyon kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/urOperasyon/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Operasyon Olu�tur
Yeni bir operasyon olu�turmaktad�r.
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
            "Aciklama": "H�zl� Re�etelerde kullan�lan operasyon",
            "HizBirimID": null,
            "KartPuan": 0.000000
        }
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Operasyon D�zenle
Var olan operasyonu d�zenlemeketedir.
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
        "Aciklama": "H�zl� Re�etelerde kullan�lan operasyon",
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
Sistemde kay�tl� olan yevmiye fi� kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/YevmiyeFis/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: YevmiyeFis Olu�tur
Yeni bir yevmiye fi�i olu�turmaktad�r.
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

## End-point: YevmiyeFis D�zenle
Var olan yevmiye fi�ini d�zenlemeketedir.
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
Mevcut yevmiye fi�ini silmektedir.
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
Sistemde kay�tl� olan b�t�n yevmiye fi� hareketlerinin g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/YevmiyeFisHareketleri/GetKayit
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: YevmiyeFisHareketleri Olu�tur
Yeni bir yevmiye fi� hareketi olu�turmaktad�r.
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

## End-point: YevmiyeFisHareketleri D�zenle
Var olan yevmiye fi� hareketini d�zenlemeketedir.
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
Mevcut yevmiye fi� hareketini silmektedir.

###### Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu bu bankan�n hareketler ve bankalarla ile ili�kisini kesmelisiniz.
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
Sistemde kay�tl� olan b�t�n �l�� birimlerinin g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/OlcuBirimleri/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: OlcuBirimleri Olu�tur
Yeni bir �l�� birimi olu�turmaktad�r.
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
            "SubeAdi": "T�m �ubeler",
            "SirketAdi": "T�m �irketler",
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

## End-point: OlcuBrimleri D�zenle
Var olan �l�� birimini d�zenlemeketedir.
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
            "SubeAdi": "T�m �ubeler",
            "SirketAdi": "T�m �irketler",
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
Mevcut �l�� birimini silmektedir.

###### Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu bu bankan�n hareketler ve bankalarla ile ili�kisini kesmelisiniz.
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
Sistemde kay�tl� olan b�t�n banka kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/PerPuantaj/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: PerPuantaj Olu�tur
Yeni bir personel puantaj olu�turmaktad�r.
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

## End-point: PerPuantaj D�zenle
Var olan personel puantaj�n� d�zenlemeketedir.
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
Mevcut personel puantaj�n� silmektedir.

###### Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu bu bankan�n hareketler ve bankalarla ile ili�kisini kesmelisiniz.
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
Sistemde kay�tl� olan b�t�n banka kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/Personel/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Personel Olu�tur
Yeni bir stok kart� eklemek i�in
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.
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

## End-point: Personel D�zenle
Mevcut bir deponun d�zeltilmesi i�in kullan�lmaktad�r.

######  Depo eklemekten farkl� olarak ID eklenmesi gerekmektedir.
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
            "PersonelAdiSoyadi": "denemewebapi denemeWEBAP�",
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
Mevcut bir deponun silinmesi i�in kullan�lmaktad�r.

######  Depoyu silmeden �nce depoya ait b�t�n hareketlerin ve stoklar silindi�inden/ta��nd���ndan emin olunuz. Aksi takdirde silme i�lemi ger�ekle�meyecektir.
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
# ?? Collection: �s Emri 


## End-point: �sEmri Getir
Sistemde kay�tl� olan b�t�n i� emri kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/urIsEmri/Get
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: �sEmri Olu�tur
StartFragment

Yeni bir i� emri olu�turmaktad�r.  
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.
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
            "Aciklama": " \r\nSipari� A��klama : \r\n \r\n"

}
```

### Query Params

|Param|value|
|---|---|
|KayitTipi|1|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: �sEmri D�zenle
Mevcut bir i� emrinin d�zeltilmesi i�in kullan�lmaktad�r.

###### �� emri eklemekten farkl� olarak ID eklenmesi gerekmektedir.
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

## End-point: �sEmri Sil
Mevcut bir i� emrinin silinmesi i�in kullan�lmaktad�r.
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
# ?? Collection: Banka �ube 


## End-point: Banka �ubeleri Getir
StartFragment

Sistemde kay�tl� olan b�t�n banka �ube kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/BankaSube/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Banka �ube Olu�tur
StartFragment

Yeni bir banka �ube olu�turmaktad�r.
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

## End-point: Banka �ube D�zenle
StartFragment

Var olan banka �ubesini d�zenlemektedir.
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

## End-point: Banka �ube Sil
StartFragment

Mevcut banka �ubeyi silmektedir.
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


## End-point: Notlar� Getir
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

## End-point: Not Ekle/G�nder
### Method: POST
>```
>{{BaseUrl}}/api/Notlar/Post?KayitTipi=1
>```
### Body (**raw**)

```json
{
    "Notu": "Son eklenen stok kart� i�in not",
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
# ?? Collection: Stok Say�m 


## End-point: Say�m Giri�leri Getir
Sistemde kay�tl� olan b�t�n stok say�mlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/StokSayim
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Say�m Giri�i Yap
Yeni bir stok kart� eklemek i�in  
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

### Sorgu Body JSON a��klamas�

| Parametre | �rnek De�er | Tan�m | ZorunluMu |
| --- | --- | --- | --- |
| StokID | \-1 | Eklenilen �r�n�n stok ID'sidir. -1 girildi�i takdirde rasgele olarak ID atanmaktad�r. | Evet |
| SubeID | 1 | Sto�un bulundu�u �ubenin ID'sidir. | Evet |
| SirketID | 1 | Sto�un ait oldu�u �irketin ID'sidir. | Evet |
| StokKodu | "HRD.KPKL.00164" | Sto�un detayl� kodudur. | Evet |
| StokAdi | "H�rdavat Kap� Kolu Burak Oda Rozetli Saten" | Sto�un g�z�ken ad�d�r. | Evet |
| StokKisaKodu | "HRD.KPKL" | Sto�un genel kodudur. Genel kod �zel kodlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa koda sahip olmas� �nemlidir. | Evet |
| StokKisaAdi | "H�rdavat Kap� Kolu" | Sto�un genel ad�d�r. Genel ad �zel adlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa ada sahip olmas� �nemlidir. | Evet |
| Durum | true | Stok kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet |
| TipID | 105001 | Aaro'da stok yaln�zca fiziksel bir mal� i�aret etmek durumunda de�ildir. Gelir-gider hareketleri gibi i�lemler de stok olarak d���n�lmektedir dolay�s�yla ne t�r bir stok oldu�unu belirtmek i�in TipID bulunmaktad�r. | Evet |
| StokMuhasebeID | 201 | Stoklar�n muhasebesebesi farkl� �ekilde i�lenebilir. Stok muhasebe ID hakk�nda detayl� bilgi i�in muhasebe b�l�m�n� inceleyiniz | Evet |
| Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Evet |
| Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel |
| Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel |
| CevirimBrm2 | null | Birim 1'in birim 2 cinsine �evrilmesi i�indir. | Opsiyonel |
| CevirimBrm3 | null | Birim 1'in birim 3 cinsine �evrilmesi i�indir. | Opsiyonel |
| Kalinlik | 10.0 | Stok kart�n�n fizikel kal�nl���d�r. | Opsiyonel |
| En | 10.0 | Stok kart�n�n fizikel enidir. | Opsiyonel |
| Boy | 10.0 | Stok kart�n�n fizikel boyudur. | Opsiyonel |
| Yo�unluk | 3.0 | Stok kart�n�n fizikel yo�unlu�udur. | Opsiyonel |
| Agirlik | 5.0 | Stok kart�n�n fizikel a��rl���d�r. | Opsiyonel |
| Kod1ID | null | Stok kartlar�n� hiyerar�ik grupland�rmak i�in kullan�l�r. �rnek: Elektronik -> Bilgisayar -> HP | Opsiyonel |
| Etiket1ID | null | �r�n etiketleri icindir. �rnek | Opsiyonel |
| SablonID | null | �r�n ekleme �ablonu varsa girilmelidir. | Opsiyonel |

> &lt;h5 &gt;�r�n olu�tururken d�k�man alt�ndaki �rnek senaryo �zerinden gidebilirsiniz.&lt;/h5&gt;
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

## End-point: Say�m Giri�i D�zelt
Yeni bir stok kart� eklemek i�in
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.
### Sorgu URL Parametreleri

Parametre | De�er | Tan�m
--------- | ----------- | ---------
KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu Body JSON a��klamas�

Parametre | �rnek De�er | Tan�m | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen �r�n�n stok ID'sidir. -1 girildi�i takdirde rasgele olarak ID atanmaktad�r.  | Evet
SubeID | 1 | Sto�un bulundu�u �ubenin ID'sidir. | Evet
SirketID | 1 | Sto�un ait oldu�u �irketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Sto�un detayl� kodudur. | Evet
StokAdi | "H�rdavat Kap� Kolu Burak Oda Rozetli Saten" | Sto�un g�z�ken ad�d�r. | Evet
StokKisaKodu |"HRD.KPKL" | Sto�un genel kodudur. Genel kod �zel kodlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa koda sahip olmas� �nemlidir. | Evet
StokKisaAdi |"H�rdavat Kap� Kolu" | Sto�un genel ad�d�r. Genel ad �zel adlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa ada sahip olmas� �nemlidir. | Evet
Durum | true | Stok kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yaln�zca fiziksel bir mal� i�aret etmek durumunda de�ildir. Gelir-gider hareketleri gibi i�lemler de stok olarak d���n�lmektedir dolay�s�yla ne t�r bir stok oldu�unu belirtmek i�in TipID bulunmaktad�r. | Evet
StokMuhasebeID | 201 | Stoklar�n muhasebesebesi farkl� �ekilde i�lenebilir. Stok muhasebe ID hakk�nda detayl� bilgi i�in muhasebe b�l�m�n� inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine �evrilmesi i�indir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine �evrilmesi i�indir. | Opsiyonel
Kalinlik | 10.0 | Stok kart�n�n fizikel kal�nl���d�r. | Opsiyonel
En | 10.0 | Stok kart�n�n fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kart�n�n fizikel boyudur. | Opsiyonel
Yo�unluk | 3.0 | Stok kart�n�n fizikel yo�unlu�udur. | Opsiyonel
Agirlik | 5.0 | Stok kart�n�n fizikel a��rl���d�r. | Opsiyonel
Kod1ID | null | Stok kartlar�n� hiyerar�ik grupland�rmak i�in kullan�l�r. �rnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | �r�n etiketleri icindir. �rnek | Opsiyonel
SablonID | null | �r�n ekleme �ablonu varsa girilmelidir. | Opsiyonel

>##### �r�n olu�tururken d�k�man alt�ndaki �rnek senaryo �zerinden gidebilirsiniz.
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

## End-point: Say�m Gri�i  Sil
Mevcut cariyi silmektedir

###### Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu carinin hareketler ve bankalarla ile ili�kisini kesmelisiniz.
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

## End-point: Say�m Hareketleri Getir
### Method: GET
>```
>{{BaseUrl}}/api/StokSayimHareketleri/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Say�m Hareketi Ekle
Yeni bir stok kart� eklemek i�in
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.
### Sorgu URL Parametreleri

Parametre | De�er | Tan�m
--------- | ----------- | ---------
KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu Body JSON a��klamas�

Parametre | �rnek De�er | Tan�m | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen �r�n�n stok ID'sidir. -1 girildi�i takdirde rasgele olarak ID atanmaktad�r.  | Evet
SubeID | 1 | Sto�un bulundu�u �ubenin ID'sidir. | Evet
SirketID | 1 | Sto�un ait oldu�u �irketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Sto�un detayl� kodudur. | Evet
StokAdi | "H�rdavat Kap� Kolu Burak Oda Rozetli Saten" | Sto�un g�z�ken ad�d�r. | Evet
StokKisaKodu |"HRD.KPKL" | Sto�un genel kodudur. Genel kod �zel kodlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa koda sahip olmas� �nemlidir. | Evet
StokKisaAdi |"H�rdavat Kap� Kolu" | Sto�un genel ad�d�r. Genel ad �zel adlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa ada sahip olmas� �nemlidir. | Evet
Durum | true | Stok kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yaln�zca fiziksel bir mal� i�aret etmek durumunda de�ildir. Gelir-gider hareketleri gibi i�lemler de stok olarak d���n�lmektedir dolay�s�yla ne t�r bir stok oldu�unu belirtmek i�in TipID bulunmaktad�r. | Evet
StokMuhasebeID | 201 | Stoklar�n muhasebesebesi farkl� �ekilde i�lenebilir. Stok muhasebe ID hakk�nda detayl� bilgi i�in muhasebe b�l�m�n� inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine �evrilmesi i�indir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine �evrilmesi i�indir. | Opsiyonel
Kalinlik | 10.0 | Stok kart�n�n fizikel kal�nl���d�r. | Opsiyonel
En | 10.0 | Stok kart�n�n fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kart�n�n fizikel boyudur. | Opsiyonel
Yo�unluk | 3.0 | Stok kart�n�n fizikel yo�unlu�udur. | Opsiyonel
Agirlik | 5.0 | Stok kart�n�n fizikel a��rl���d�r. | Opsiyonel
Kod1ID | null | Stok kartlar�n� hiyerar�ik grupland�rmak i�in kullan�l�r. �rnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | �r�n etiketleri icindir. �rnek | Opsiyonel
SablonID | null | �r�n ekleme �ablonu varsa girilmelidir. | Opsiyonel

>##### �r�n olu�tururken d�k�man alt�ndaki �rnek senaryo �zerinden gidebilirsiniz.
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

## End-point: Say�m Hareketi D�zelt
Yeni bir stok kart� eklemek i�in
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.
### Sorgu URL Parametreleri

Parametre | De�er | Tan�m
--------- | ----------- | ---------
KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu Body JSON a��klamas�

Parametre | �rnek De�er | Tan�m | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen �r�n�n stok ID'sidir. -1 girildi�i takdirde rasgele olarak ID atanmaktad�r.  | Evet
SubeID | 1 | Sto�un bulundu�u �ubenin ID'sidir. | Evet
SirketID | 1 | Sto�un ait oldu�u �irketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Sto�un detayl� kodudur. | Evet
StokAdi | "H�rdavat Kap� Kolu Burak Oda Rozetli Saten" | Sto�un g�z�ken ad�d�r. | Evet
StokKisaKodu |"HRD.KPKL" | Sto�un genel kodudur. Genel kod �zel kodlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa koda sahip olmas� �nemlidir. | Evet
StokKisaAdi |"H�rdavat Kap� Kolu" | Sto�un genel ad�d�r. Genel ad �zel adlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa ada sahip olmas� �nemlidir. | Evet
Durum | true | Stok kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yaln�zca fiziksel bir mal� i�aret etmek durumunda de�ildir. Gelir-gider hareketleri gibi i�lemler de stok olarak d���n�lmektedir dolay�s�yla ne t�r bir stok oldu�unu belirtmek i�in TipID bulunmaktad�r. | Evet
StokMuhasebeID | 201 | Stoklar�n muhasebesebesi farkl� �ekilde i�lenebilir. Stok muhasebe ID hakk�nda detayl� bilgi i�in muhasebe b�l�m�n� inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine �evrilmesi i�indir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine �evrilmesi i�indir. | Opsiyonel
Kalinlik | 10.0 | Stok kart�n�n fizikel kal�nl���d�r. | Opsiyonel
En | 10.0 | Stok kart�n�n fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kart�n�n fizikel boyudur. | Opsiyonel
Yo�unluk | 3.0 | Stok kart�n�n fizikel yo�unlu�udur. | Opsiyonel
Agirlik | 5.0 | Stok kart�n�n fizikel a��rl���d�r. | Opsiyonel
Kod1ID | null | Stok kartlar�n� hiyerar�ik grupland�rmak i�in kullan�l�r. �rnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | �r�n etiketleri icindir. �rnek | Opsiyonel
SablonID | null | �r�n ekleme �ablonu varsa girilmelidir. | Opsiyonel

>##### �r�n olu�tururken d�k�man alt�ndaki �rnek senaryo �zerinden gidebilirsiniz.
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

## End-point: Say�m Hareketi Sil
Mevcut cariyi silmektedir

###### Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu carinin hareketler ve bankalarla ile ili�kisini kesmelisiniz.
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
Dekont ba�l�k ve kalem bilgilerini girdikten sonra tamamla �a�r�l�rsa kay�t tamamlanacakt�r. Olu�turulan dekont id bilgisi yeterlidir.

> _**Yar�m b�rak�lm�� bir kay�t var ve ayn� belge numaras� ile yeni bir kayd� tamamla metodu ile eklemeye �al���yorsak bu belge numaras� kullan�lm��t�r hatas� alabiliriz.Bu y�zden kay�tlar�m�zda belge numaralar� farkl� olmal�d�r.**_
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

## End-point: Dekont Ba�l�k Getir
Bu u� nokta ile kay�tl� olan dekontun DekontID'si g�nderilerek ba�l�k bilgisi al�nabilir. Ayn� bilgiye Ba�l�klar� Getir sekmesinde DekontID k�s�t� g�nderilerekte ula��labilir.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| id | Integer | Belirtilen ID ile Dekont Ba�l��� getirmektedir. |
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
        "Aciklama": "Al�nan Sipari� �lk M��terim",
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

## End-point: Dekont Ba�l�klar� Getir
Bu u� nokta ile kay�tl� olan t�m dekontlar�n filtrelenerek listesi al�nabilir.
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
            "Aciklama": "Al�nan Sipari� �lk M��terim",
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
Bu u� nokta ile kay�tl� olan Dekontun KalemTek bilgisi al�nabilir. Nerdeyse t�m dekont tiplerinin vard�r. E�er yoksa bo� sonu� d�nd�r�r.

### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| DekontID | Integer | Belirtilen ID ile Dekont Ba�l��� getirmektedir. |
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
        "Aciklama": "Sipari� Ba�l�k Modeli Ekleme deneme",
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
        "KartAdi": "�lk M��terim"
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
Bu u� nokta ile kay�tl� olan Dekontunkalemleri okunabilir.
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
            "KartAdi": "Otomatik Aktar�m Stok Kart�"
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
            "KartAdi": "Otomatik Aktar�m Stok Kart�"
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
            "KartAdi": "Otomatik Aktar�m Stok Kart�"
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
            "KartAdi": "Otomatik Aktar�m Stok Kart�"
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
            "KartAdi": "Otomatik Aktar�m Stok Kart�"
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

## End-point: Al�nan Sipari� Ba�l�k Ekleme
Bu ba�l�k alt�nda Al�nan Sipari� hareketinin kaydetme s�recini g�receksiniz. (Tek-Cok) hareketlerinde �nce BaslikModel ve KalemTekModel bilgileri ile Ba�l�k kaydedilir. Bu i�lem ba�ar�l� olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir.

#### BaslikModel

Farkl� bir Dekont(Tek-Cok) kayd� olu�turmak istedi�inzde �rne�in Verilen Sipari� hareketi olu�turmak istedi�inizde, BaslikModel'in i�inde yer alan TipID parametresini "VerilenSiparis" olarak de�i�tirmeniz yeterli olacakt�r.

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | AlinanSiparis | Dekontun hareket t�r�n� belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi �irkete a��laca��n� belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi �ubeye a��laca��n� belirler | Evet |
| BelgeNo | String | 2822429117384-AS | Dekontun belge numaras�d�r. Uniqe olmak zorundad�r. | Evet |
| Tarih | DateTime | 2023-03-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmedi�i takdirde dekontun tarihi ile ayn� de�eri alacakt�r. | Hay�r |
| RefDepoID | Integer | 1 | Al�nan sipari�e girilen Deponun id'sini belritir. | Hay�r |

Yukar�daki bilgiler Dekont Ba�l��� olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz BaslikModel'ine bakabilirsiniz.

#### KalemTekModel

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Cari | Al�nan Sipari� hareketi Cari �zerinden yap�ld��� i�in KalemTek bilgisinin KalemTipi parametresi Cari olmal�d�r. | Evet |
| KartID | Integer | 4920 | Aaro'da tan�mlam�� oldu�unuz cari kart�n�n ID'sidir. | Evet |
| Tutar | Decimal | 100 | Hareketin toplam tutar�n�n TL cinsinden kar��l���d�r. 0 girilemez. | Hay�r |
| DovizID | Integer | 1 | DovizID hareketin d�viz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutar�n�n belirtilen d�viz cinsinden kar��l���d�r. D�viz cinsi TL(1)'den farkl� ise 0 girilemez. | Hay�r |
| Aciklama | String | Al�nan Sipari� Ba�l�k Modeli Ekleme | Dekont'a ait a��klamad�r. | Hay�r |

Yukar�daki bilgiler Dekont KalemTek olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu i�lem ba�ar�l� olduktan sonra KalemCok bilgisini eklemek i�in Kalem metodunu kullanaca��z.

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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
        "TipID": 10013, // Al�nan sipari� oldu�unu belirtir.
        "SirketID": 1,
        "SubeID": 1,
        "RefDepoID":1  //Al�nan sipari�e girilen Deponun id'sini belirtir.        
    },
    "KalemTek": { //Al�nan sipari�e girilen cari bilgileri girilmesi i�in kullan�l�r.
        "KalemTipi": 6, // Kalem tipine g�re belirlenir. Kalem tipi tablosu alt�nda bulabilirsiniz.
        "KartID": 4, //Sipari�e girilen cari'nin id'si girilmelidir.
        "DovizID": 1,
        "Aciklama": "Sipari� Ba�l�k Modeli Ekleme deneme"
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

## End-point: Al�nan Sipari� Kalem Ekleme
Ba�l�k kaydetme i�lemi ba�ar�l� olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden �ok kalem kaydetmek istiyorsan�z her kalem i�in bu metodu �a��rmal�s�n�z.

#### KalemCokModel

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | SiparisStok | Al�nan Sipari� hareketinde kalemleri ekleyebilmek i�in KalemTipi parametresi SiparisStok olmal�d�r. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydetti�imiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tan�mlam�� oldu�unuz stok kart�n�n ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istedi�iniz sto�un kendi birimi cinsinden miktar�n� belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutar�n�n TL cinsinden kar��l���d�r. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin d�viz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutar�n�n belirtilen d�viz cinsinden kar��l���d�r. D�viz cinsi TL(1)'den farkl� ise 0 girilemez. | Evet |
| SiparisStok | SiparisStokModel | SiparisStokModel | D�k�manda yer alan SiparisStokModel bilgileriyle olu�turulan model | Evet |

Yukar�daki bilgiler Dekont KalemCok olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu i�lem ba�ar�l� olduktan sonra KalemCok bilgisini eklemek i�in Kalemler metodunu kullanaca��z.

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**
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

## End-point: Al�nan Sipari� Ba�l�k D�zeltme
Ba�l�k bilgisinde DekontID'yi set ettikten sorna d�zeltme i�lemi yapabiliriz

#### BaslikModel

Ba�l�k bilgisini d�zeltirken KalemTek bilgisini g�ndermeniz zorunlu de�ildir,

#### KalemTekModel

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 T�m API'de yeni kay�t d�zenle anlam�na gelmektedir. |

Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Hay�r |
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
        "TipID": 10013, // Al�nan sipari� oldu�unu belirtir.
        "SirketID": 1,
        "SubeID": 1,
        "RefDepoID":1  //Al�nan sipari�e girilen Deponun id'sini belritir.
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
        "Aciklama": "Al�nan Sipari� �lk M��terim",
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

## End-point: Al�nan Sipari� Kalem D�zeltme
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra d�zeltme i�lemi yapabiliriz. Kalem bilgisinin miktar�n� de�i�tirip 7 yapal�m. Miktar bilgisini g�ncelledi�iniz zaman Tutar bilgisinin de g�ncellenmesini istiyorsan�z, Tutar bigisini de girmeniz gerekmektedir.

> **Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 2 T�m API'de yeni kay�t d�zenle anlam�na gelmektedir. |

> _**Kalem bilgisi d�zeltildikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**_
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
        "KartAdi": "Otomatik Aktar�m Stok Kart�"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Al�nan Sipari� Ba�l�k Silme
#### BaslikModel

Ba�l�k bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 T�m API'de kay�t sil anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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

## End-point: Al�nan Sipari� Kalem Silme
Kalem bilgisinin DekontID,KalemTipi ve HareketID'si set edildikten sonra silme i�lemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 T�m API'de kay�t sil anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| KalemCok | KalemModel | KalemModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |

> _**Kalem bilgisi silindikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**_
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

## End-point: Al�nan Sipari� Tevkifatl�  Kalem Ekleme
Ba�l�k kaydetme i�lemi ba�ar�l� olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden �ok kalem kaydetmek istiyorsan�z her kalem i�in bu metodu �a��rmal�s�n�z.

> _**Tevkifatl� kalem bilgisi i�in vergi alt ID eklenmelidir. Bu Id'nin kar��l��� Tevkifat Tip ID'dir. Vergi oranlar�n� listeyip bu bilgiyi bulabilirsiniz.**_ 
  

#### KalemCokModel

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | SiparisStok | Al�nan Sipari� hareketinde kalemleri ekleyebilmek i�in KalemTipi parametresi SiparisStok olmal�d�r. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydetti�imiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tan�mlam�� oldu�unuz stok kart�n�n ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istedi�iniz sto�un kendi birimi cinsinden miktar�n� belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutar�n�n TL cinsinden kar��l���d�r. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin d�viz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutar�n�n belirtilen d�viz cinsinden kar��l���d�r. D�viz cinsi TL(1)'den farkl� ise 0 girilemez. | Evet |
| SiparisStok | SiparisStokModel | SiparisStokModel | D�k�manda yer alan SiparisStokModel bilgileriyle olu�turulan model | Evet |

Yukar�daki bilgiler Dekont KalemCok olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu i�lem ba�ar�l� olduktan sonra KalemCok bilgisini eklemek i�in Kalemler metodunu kullanaca��z.

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**
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
                "VergiAltID": 28, //Tevkifat Tip ID bilgisi girilmelidir. Vergi oranlar�n� listeyip bu bilgiyi bulabilirsiniz.
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
Bu ba�l�k alt�nda Nakit Tahsilat hareketinin kaydetme s�recini g�receksiniz. Bunun i�in �ncelikle BaslikModel, KalemTekModel ve KalemCokModel yap�lar�m�z� olu�tural�m.

#### BaslikModel

Farkl� bir Dekont(Tek-Tek) kayd� olu�turmak istedi�inizde �rne�in Nakit �deme hareketi olu�turmak istedi�inizde, BaslikModel'in i�inde yer alan TipID parametresini "NakitOdeme" olarak de�i�tirmeniz yeterli olacakt�r.

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | NakitTahsilat | Dekontun hareket t�r�n� belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi �irkete a��laca��n� belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi �ubeye a��laca��n� belirler | Evet |
| BelgeNo | String | 2822429117384-NT | Dekontun belge numaras�d�r. Uniqe olmak zorundad�r. | Evet |
| Tarih | DateTime | 24.09.2021 | Dekont tarihidir. | Evet |
| Vade | DateTime | 24.09.2021 | Deokntun vadesidir. Verilmedi�i takdirde dekontun tarihi ile ayn� de�eri alacakt�r. | Hay�r |
| Aciklama | String | Nakit Tahsilat Ba�l�k Modeli | Dekont'un ba�l���na ait a��klamad�r. | Hay�r |

> **Yukar�daki bilgiler Dekont Ba�l��� olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz BaslikModel'ine bakabilirsiniz.** 
  

#### KalemTekModel

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Kasa | Nakit Tahsilat hareketi Kasa �zerinden yap�ld��� i�in KalemTek bilgisinin KalemTipi parametresi Kasa olmal�d�r. | Evet |
| KartID | Integer | 1 | Aaro'da tan�mlam�� oldu�unuz kasa kart�n�n ID'sidir. | Evet |
| Tutar | Decimal | 1 | Hareketin toplam tutar�n�n TL cinsinden kar��l���d�r. 0 girilemez. KalemCok bilgisindeki de�er ile ayn� olmal�d�r. | Evet |
| DovizID | Integer | 1 | DovizID hareketin d�viz cinsini belirler. KalemCok bilgisindeki de�er ile ayn� olmal�d�r. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutar�n�n belirtilen d�viz cinsinden kar��l���d�r. D�viz cinsi TL(1)'den farkl� ise 0 girilemez. KalemCok bilgisindeki de�er ile ayn� olmal�d�r. | Evet |

> **Yukar�daki bilgiler Dekont KalemTek olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### KalemCokModel

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Cari | Nakit Tahsilat hareketinin di�er taraf� Cari oldu�u i�in KalemTek bilgisinin KalemTipi parametresi Cari olmal�d�r. | Evet |
| KartID | Integer | 4920 | Aaro'da tan�mlam�� oldu�unuz cari kart�n�n ID'sidir. | Evet |
| Tutar | Decimal | 100 | Hareketin toplam tutar�n�n TL cinsinden kar��l���d�r. 0 girilemez. KalemTek bilgisindeki de�er ile ayn� olmal�d�r. | Evet |
| DovizID | Integer | 1 | DovizID hareketin d�viz cinsini belirler. KalemTek bilgisindeki de�er ile ayn� olmal�d�r. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutar�n�n belirtilen d�viz cinsinden kar��l���d�r. D�viz cinsi TL(1)'den farkl� ise 0 girilemez. KalemTek bilgisindeki de�er ile ayn� olmal�d�r. | Evet |

> **Yukar�daki bilgiler Dekont KalemCok olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
| KalemCok | KalemModel | KalemModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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

## End-point: Nakit Tahsilat D�zenle
Ba�l�kModel i�erisinde DekontID bilgisini set ettikten sonra d�zeltme yapabiliriz.

#### BaslikModel

#### KalemTekModel

KalemTek Model deki tutar bilgisini yenileyelim KalemTek icindeki aciklama alanini de�i�tirelim. Bu alan Dekontun a��klamas�d�r.

#### KalemCokModel

KalemCok Model deki tutar bilgisini yenileyelim.

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 2 T�m API'de kay�t d�zenle anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
| KalemCok | KalemModel | KalemModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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
        "Aciklama": "Postmandan Nakit Tahsilat D�zeltme"
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
Ba�l�kModel i�erisinde sadece DekontID bilgisini set etmemiz yeterli olacakt�r.

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 T�m API'de kay�t sil anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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

## End-point: Sat�� Faturas� Ba�l�k Ekleme
Bu ba�l�k alt�nda Sat�� faturas� hareketinin kaydetme s�recini g�receksiniz. (Tek-Cok) hareketlerinde �nce BaslikModel ve KalemTekModel bilgileri ile Ba�l�k kaydedilir. Bu i�lem ba�ar�l� olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir.

#### BaslikModel

Farkl� bir Dekont(Tek-Cok) kayd� olu�turmak istedi�inzde �rne�in Sat�� Faturas� hareketi olu�turmak istedi�inizde, BaslikModel'in i�inde yer alan TipID parametresini "Sat�� Faturas�" olarak de�i�tirmeniz yeterli olacakt�r.

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | SatisFaturasi | Dekontun hareket t�r�n� belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi �irkete a��laca��n� belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi �ubeye a��laca��n� belirler | Evet |
| BelgeNo | String | 2822429117384-AS | Dekontun belge numaras�d�r. Uniqe olmak zorundad�r. | Evet |
| Tarih | DateTime | 2023-03-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmedi�i takdirde dekontun tarihi ile ayn� de�eri alacakt�r. | Hay�r |
| RefDepoID | Integer | 1 | Sat�� faturas� girilen Deponun id'sini belirtir. | Hay�r |

> **Yukar�daki bilgiler Dekont Ba�l��� olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz BaslikModel'ine bakabilirsiniz.** 
  

#### KalemTekModel

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Cari | Sat�� faturas� hareketi Cari �zerinden yap�ld��� i�in KalemTek bilgisinin KalemTipi parametresi Cari olmal�d�r. | Evet |
| KartID | Integer | 4920 | Aaro'da tan�mlam�� oldu�unuz cari kart�n�n ID'sidir. | Evet |
| Tutar | Decimal | 100 | Hareketin toplam tutar�n�n TL cinsinden kar��l���d�r. 0 girilemez. | Hay�r |
| DovizID | Integer | 1 | DovizID hareketin d�viz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Hareketin tutar�n�n belirtilen d�viz cinsinden kar��l���d�r. D�viz cinsi TL(1)'den farkl� ise 0 girilemez. | Hay�r |
| Aciklama | String | Test Sat�� Faturas� | Dekont'a ait a��klamad�r. | Hay�r |

Yukar�daki bilgiler Dekont KalemTek olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.

Bu i�lem ba�ar�l� olduktan sonra KalemCok bilgisini eklemek i�in Kalem metodunu kullanaca��z.

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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
        "RefDepoID":1  //Al�nan sipari�e girilen Deponun id'sini belirtir.
    },
    "KalemTek": {
        "KalemTipi": 1,
        "KartID": 4,
        "DovizID": 1,
        "Aciklama": "Test Sat�� Faturas�"
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

## End-point: Sat�� Faturas� Kalem Ekleme
Ba�l�k kaydetme i�lemi ba�ar�l� olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden �ok kalem kaydetmek istiyorsan�z her kalem i�in bu metodu �a��rmal�s�n�z.

#### KalemCokModel

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Stok | Sat�� Faturas� hareketinde kalemleri ekleyebilmek i�in KalemTipi parametresi Stok olmal�d�r. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydetti�imiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tan�mlam�� oldu�unuz stok kart�n�n ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istedi�iniz sto�un kendi birimi cinsinden miktar�n� belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutar�n�n TL cinsinden kar��l���d�r. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin d�viz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutar�n�n belirtilen d�viz cinsinden kar��l���d�r. D�viz cinsi TL(1)'den farkl� ise 0 girilemez. | Evet |
| Stok | StokModel | StokModel | D�k�manda yer alan StokModel bilgileriyle olu�turulan model | Evet |

> **Yukar�daki bilgiler Dekont KalemCok olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

Bu i�lem ba�ar�l� olduktan sonra KalemCok bilgisini eklemek i�in Kalemler metodunu kullanaca��z.

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**
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
        "KartAdi": "Otomatik Aktar�m Stok Kart�"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sat�� Faturas� Ba�l�k D�zeltme
Ba�l�k bilgisinde DekontID'yi set ettikten sorna d�zeltme i�lemi yapabiliriz

#### BaslikModel

Ba�l�k bilgisini d�zeltirken KalemTek bilgisini g�ndermeniz zorunlu de�ildir,

#### KalemTekModel

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 T�m API'de yeni kay�t d�zenle anlam�na gelmektedir. |

Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
| KalemTek | KalemModel | KalemModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Hay�r |
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
        "RefDepoID":1  //Al�nan sipari�e girilen Deponun id'sini belirtir.
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
        "Aciklama": "Sat�� Faturas� �lk M��terim",
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

## End-point: Sat�� Faturas� Kalem D�zeltme
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra d�zeltme i�lemi yapabiliriz. Kalem bilgisinin miktar�n� de�i�tirip 7 yapal�m. Miktar bilgisini g�ncelledi�iniz zaman Tutar bilgisinin de g�ncellenmesini istiyorsan�z, Tutar bigisini de girmeniz gerekmektedir.

> **Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 2 T�m API'de yeni kay�t d�zenle anlam�na gelmektedir. |

> _**Kalem bilgisi d�zeltildikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**_
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
        "KartAdi": "Otomatik Aktar�m Stok Kart�"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Sat�� Faturas� Ba�l�k Silme
#### BaslikModel

Ba�l�k bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 T�m API'de kay�t sil anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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

## End-point: Sat�� Faturas� Kalem Silme
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra silme i�lemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 T�m API'de kay�t sil anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| KalemCok | KalemModel | KalemModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |

> _**Kalem bilgisi silindikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**_
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

## End-point: Karma Transfer Ba�l�k Ekleme
#### BaslikModel

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | KarmaTransfer | Dekontun hareket t�r�n� belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi �irkete a��laca��n� belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi �ubeye a��laca��n� belirler | Evet |
| BelgeNo | String | 0000000000000011 | Dekontun belge numaras�d�r. Uniqe olmak zorundad�r. | Evet |
| Tarih | DateTime | 2024-06-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmedi�i takdirde dekontun tarihi ile ayn� de�eri alacakt�r. | Hay�r |
| RefDepoID | Integer | 1 | Karma transfere girilen Deponun id'sini belirtir. | Hay�r |

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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
Ba�l�k kaydetme i�lemi ba�ar�l� olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden �ok kalem kaydetmek istiyorsan�z her kalem i�in bu metodu �a��rmal�s�n�z.

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Stok | Karma transfer hareketinde kalemleri ekleyebilmek i�in KalemTipi parametresi eklenen tipe g�re de�i�ir. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydetti�imiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tan�mlam�� oldu�unuz stok kart�n�n ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istedi�iniz sto�un kendi birimi cinsinden miktar�n� belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutar�n�n TL cinsinden kar��l���d�r. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin d�viz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutar�n�n belirtilen d�viz cinsinden kar��l���d�r. D�viz cinsi TL(1)'den farkl� ise 0 girilemez. | Evet |
| Stok | StokModel | StokModel | D�k�manda yer alan StokModel bilgileriyle olu�turulan model | Evet |
| Cari | CariModel | CariModel | D�k�manda yer alan CariModelbilgileriyle olu�turulan model |  |
| Banka | BankaModel | BankaModel | D�k�manda yer alan BankaModelbilgileriyle olu�turulan model |  |
| Kasa | KasaModel | KasaModel | D�k�manda yer alan KasaModelbilgileriyle olu�turulan model |  |

> **Yukar�daki bilgiler Dekont KalemCok olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

Bu i�lem ba�ar�l� olduktan sonra KalemCok bilgisini eklemek i�in Kalemler metodunu kullanaca��z.

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**
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
        "KartAdi": "Otomatik Aktar�m Stok Kart�"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Karma Transfer Ba�l�k D�zeltme
Ba�l�k bilgisinde DekontID'yi set ettikten sorna d�zeltme i�lemi yapabiliriz

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 T�m API'de yeni kay�t d�zenle anlam�na gelmektedir. |

Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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

## End-point: Karma Transfer Kalem D�zenle
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra d�zeltme i�lemi yapabiliriz.

> **Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 2 T�m API'de yeni kay�t d�zenle anlam�na gelmektedir. |

> _**Kalem bilgisi d�zeltildikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**_
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
        "KartAdi": "Otomatik Aktar�m Stok Kart�"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Karma Transfer  Ba�l�k Silme
#### BaslikModel

Ba�l�k bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 T�m API'de kay�t sil anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra silme i�lemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 T�m API'de kay�t sil anlam�na gelmektedir. |

> _**Kalem bilgisi silindikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**_
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

## End-point: Devir Ba�l�k Ekleme
#### BaslikModel

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| TipID | HareketTurleriEnum | Devir | Dekontun hareket t�r�n� belirler. | Evet |
| SirketID | Integer | 1 | Hareketin hangi �irkete a��laca��n� belirler | Evet |
| SubeID | Integer | 1 | Hareketin hangi �ubeye a��laca��n� belirler | Evet |
| BelgeNo | String | 0000000000000011 | Dekontun belge numaras�d�r. Uniqe olmak zorundad�r. | Evet |
| Tarih | DateTime | 2024-06-22 | Dekont tarihidir. | Evet |
| Vade | DateTime | 2023-03-22 | Dekontun vadesidir. Verilmedi�i takdirde dekontun tarihi ile ayn� de�eri alacakt�r. | Hay�r |
| RefDepoID | Integer | 1 | Devire girilen Deponun id'sini belirtir. | Hay�r |

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | **Zorunlu** |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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
Ba�l�k kaydetme i�lemi ba�ar�l� olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden �ok kalem kaydetmek istiyorsan�z her kalem i�in bu metodu �a��rmal�s�n�z.

| Parametre | Tip | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- | --- |
| KalemTipi | KalemTipleri | Stok | Devir hareketinde kalemleri ekleyebilmek i�in KalemTipi parametresi kalem tipine g�re olmal�d�r. | Evet |
| KartID | Integer | 190339 | Baslik metodunu kullanarak kaydetti�imiz dekontun ID'sidir. | Evet |
| DekontID | Integer | 3658 | Aaro'da tan�mlam�� oldu�unuz stok kart�n�n ID'sidir. | Evet |
| Miktar | Decimal | 1 | Eklemek istedi�iniz sto�un kendi birimi cinsinden miktar�n� belirtir. | Evet |
| Tutar | Decimal | 150 | Kalemin toplam tutar�n�n TL cinsinden kar��l���d�r. 0 girilemez. | Evet |
| DovizID | Integer | 1 | DovizID hareketin d�viz cinsini belirler. | Evet |
| TutarDvz | Decimal | 0 | Kalemin tutar�n�n belirtilen d�viz cinsinden kar��l���d�r. D�viz cinsi TL(1)'den farkl� ise 0 girilemez. | Evet |
| Stok | StokModel | StokModel | D�k�manda yer alan StokModel bilgileriyle olu�turulan model | Evet |
| Cari | CariModel | CariModel | D�k�manda yer alan CariModelbilgileriyle olu�turulan model |  |
| Banka | BankaModel | BankaModel | D�k�manda yer alan BankaModelbilgileriyle olu�turulan model |  |
| Kasa | KasaModel | KasaModel | D�k�manda yer alan KasaModelbilgileriyle olu�turulan model |  |

> **Yukar�daki bilgiler Dekont KalemCok olu�turmak i�in gereken asgari bilgilerdir. Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

Bu i�lem ba�ar�l� olduktan sonra KalemCok bilgisini eklemek i�in Kalemler metodunu kullanaca��z.

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir. |

> **Kalem bilgisi eklendikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**
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
        "KartAdi": "Otomatik Aktar�m Stok Kart�"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Devir Ba�l�k D�zeltme
Ba�l�k bilgisinde DekontID'yi set ettikten sorna d�zeltme i�lemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | Tip | De�er | Tan�m |
| --- | --- | --- | --- |
| KayitTipi | KayitTipi | Integer | 2 T�m API'de yeni kay�t d�zenle anlam�na gelmektedir. |

Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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

## End-point: Devir Kalem D�zenle
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra d�zeltme i�lemi yapabiliriz.

> **Daha fazla parametre g�ndermek isterseniz KalemModel'ine bakabilirsiniz.** 
  

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | 2 T�m API'de yeni kay�t d�zenle anlam�na gelmektedir. |

> _**Kalem bilgisi d�zeltildikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**_
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
        "KartAdi": "Otomatik Aktar�m Stok Kart�"
    },
    "Mesajlar": {
        "Mesaj": ""
    },
    "Sonuc": true,
    "Detay": ""
}
```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Devir Ba�l�k Silme
#### BaslikModel

Ba�l�k bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 T�m API'de kay�t sil anlam�na gelmektedir. |

#### Sorgu Body JSON a��klamas�

| Parametre | De�er | Tan�m | Zorunlu |
| --- | --- | --- | --- |
| Baslik | BaslikModel | BaslikModel'in a��klamas�na bak�p bilgi alabilirsiniz. | Evet |
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
Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra silme i�lemi yapabiliriz.

#### Sorgu URL Parametreleri

| Parametre | De�er | Tan�m |
| --- | --- | --- |
| KayitTipi | Integer | \-1 T�m API'de kay�t sil anlam�na gelmektedir. |

> _**Kalem bilgisi silindikten sonra Tamamla metodu �a�r�larak Ba�l�k ve kalem bilgisi kaydedilmi� olur.**_
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
# ?? Collection: Ba�vurulacak Tablolar 

# ?? Collection: StokOzet 


## End-point: Stok �zet Getir
Bu u� nokta ile stoklardaki �r�nleri toplu olarak ya da belirli bir k�s�t ile getirebilirsiniz.


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
Yeni bir stok kart� eklemek i�in
KayitTipi: 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.
### Sorgu URL Parametreleri

Parametre | De�er | Tan�m
--------- | ----------- | ---------
KayitTipi | Integer | 1 T�m API'de yeni kay�t ekle anlam�na gelmektedir.

### Sorgu Body JSON a��klamas�

Parametre | �rnek De�er | Tan�m | ZorunluMu
--------- | ------- | ----------- | -----------
StokID | -1 | Eklenilen �r�n�n stok ID'sidir. -1 girildi�i takdirde rasgele olarak ID atanmaktad�r.  | Evet
SubeID | 1 | Sto�un bulundu�u �ubenin ID'sidir. | Evet
SirketID | 1 | Sto�un ait oldu�u �irketin ID'sidir. | Evet
StokKodu | "HRD.KPKL.00164" | Sto�un detayl� kodudur. | Evet
StokAdi | "H�rdavat Kap� Kolu Burak Oda Rozetli Saten" | Sto�un g�z�ken ad�d�r. | Evet
StokKisaKodu |"HRD.KPKL" | Sto�un genel kodudur. Genel kod �zel kodlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa koda sahip olmas� �nemlidir. | Evet
StokKisaAdi |"H�rdavat Kap� Kolu" | Sto�un genel ad�d�r. Genel ad �zel adlar�n parent� olarak d���n�lebilir. Ayn� kategorideki �r�nlerin ayn� kisa ada sahip olmas� �nemlidir. | Evet
Durum | true | Stok kart�n�n aktif veya pasif oldu�unu belirlemektedir | Evet
TipID | 105001 | Aaro'da stok yaln�zca fiziksel bir mal� i�aret etmek durumunda de�ildir. Gelir-gider hareketleri gibi i�lemler de stok olarak d���n�lmektedir dolay�s�yla ne t�r bir stok oldu�unu belirtmek i�in TipID bulunmaktad�r. | Evet
StokMuhasebeID | 201 | Stoklar�n muhasebesebesi farkl� �ekilde i�lenebilir. Stok muhasebe ID hakk�nda detayl� bilgi i�in muhasebe b�l�m�n� inceleyiniz | Evet
Brm1ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Evet
Brm2ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel
Brm3ID | 1 | 1 adet, 2 metre, 3 m^2, 4 metre k�p (Kullan�c� hangi birimleri eklediyse) | Opsiyonel
CevirimBrm2 | null | Birim 1'in birim 2 cinsine �evrilmesi i�indir. | Opsiyonel
CevirimBrm3 | null | Birim 1'in birim 3 cinsine �evrilmesi i�indir. | Opsiyonel
Kalinlik | 10.0 | Stok kart�n�n fizikel kal�nl���d�r. | Opsiyonel
En | 10.0 | Stok kart�n�n fizikel enidir. | Opsiyonel
Boy | 10.0 | Stok kart�n�n fizikel boyudur. | Opsiyonel
Yo�unluk | 3.0 | Stok kart�n�n fizikel yo�unlu�udur. | Opsiyonel
Agirlik | 5.0 | Stok kart�n�n fizikel a��rl���d�r. | Opsiyonel
Kod1ID | null | Stok kartlar�n� hiyerar�ik grupland�rmak i�in kullan�l�r. �rnek: Elektronik -> Bilgisayar -> HP| Opsiyonel
Etiket1ID | null | �r�n etiketleri icindir. �rnek | Opsiyonel
SablonID | null | �r�n ekleme �ablonu varsa girilmelidir. | Opsiyonel

>##### �r�n olu�tururken d�k�man alt�ndaki �rnek senaryo �zerinden gidebilirsiniz.
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
# ?? Collection: Kullan�c�lar 


## End-point: Kullan�c�lar� Getir
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Kullanicilar?KulID=87
>```
### Query Params

|Param|value|
|---|---|
|KulID|87|



? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Kullan�c� Gruplar 


## End-point: Kullan�c� Gruplar� Getir
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/KullaniciGruplar
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Yetkiler 


## End-point: Yetkileri Getir
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Yetkiler
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Yetkiler Alt 


## End-point: Yetkiler Alt Getir
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/YetkilerAlt
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: �ubeler 


## End-point: �ubeleri Getir
B�t�n �ubeleri getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Subeler/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: �ubeleri Olu�tur
Yeni bir �ube olu�turmaktad�r.
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

## End-point: �ubeleri D�zenle
Var olan �ubeyi d�zenlemektedir.
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

## End-point: �ubeleri Sil
Mevcut �ubeyi silmektedir.
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
B�t�n takvimleri getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Takvim/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Takvimleri Olu�tur
Yeni bir takvim olu�turmaktad�r.
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

## End-point: Takvimleri D�zenle
Var olan takvimi d�zenlemektedir.
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
# ?? Collection: �irketler 


## End-point: �irketleri Getir
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Sirketler/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: �irketi Olu�tur
Yeni bir �irket olu�turmaktad�r.
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
            "SokakAdi": "k�opklo",
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

## End-point: �irketi D�zenle
Var olan �irketi d�zenlemektedir.
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
            "SokakAdi": "k�opklo",
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

## End-point: �irketi Sil
Mevcut �irketi silmektedir.
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
# ?? Collection: S�zle�me 


## End-point: S�zle�meleri Getir
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/Sozlesme
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: S�zle�me Olu�tur
Yeni bir cari olu�turmaktad�r.

###### Mevcut vergi dairelerini g�rmek i�in API d�k�man�ndan Vergi Dairesi k�sm�n� inceleyiniz.
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

## End-point: S�zle�me D�zenle
Yeni bir cari olu�turmaktad�r.

###### Mevcut vergi dairelerini g�rmek i�in API d�k�man�ndan Vergi Dairesi k�sm�n� inceleyiniz.
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

## End-point: S�zle�me Sil
Mevcut cariyi silmektedir

###### Bu i�lemin geri d�n��� yoktur. Silmeden �nce bu carinin hareketler ve bankalarla ile ili�kisini kesmelisiniz.
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
# ?? Collection: �thalat �hracatlar 


## End-point: �thalat-ihracat Getir
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
### Method: GET
>```
>{{BaseUrl}}/api/IthalatIhracat
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Plasiyer 


## End-point: Plasiyerleri Getir
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
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

## End-point: Plasiyer D�zenle
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
B�t�n cari listelerini ya da istenilen k�s�ttaki cariyi getirmektedir.
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

## End-point: Proje D�zenle
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

Sistemde kay�tl� olan b�t�n masraf merkezi kartlar�n�n g�r�nt�lendi�i aland�r.
### Method: GET
>```
>{{BaseUrl}}/api/MasrafMerkezi/GetKayit
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Masraf Merkezi Ekle
StartFragment

Yeni bir masraf merkezi olu�turmaktad�r.
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

## End-point: Masraf Merkezi D�zenle
StartFragment

Var olan masraf merkezi d�zenlemektedir.
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
# ?? Collection: Sipari� 


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
# ?? Collection: �retim 


## End-point: Recete
�retim re�ete bilgilerini listeleyebildi�iniz k�s�md�r.
### Method: GET
>```
>{{BaseUrl}}/api/UrRecete
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Recete Operasyon Hammadde
�retim re�ete operasyon hammadde bilgilerini listeleyebildi�iniz k�s�md�r.
### Method: GET
>```
>{{BaseUrl}}/api/UrReceteOperasyonHammadde
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: Recete Operasyon Mamul
�retim re�ete operasyon mamul bilgilerini listeleyebildi�iniz k�s�md�r.
### Method: GET
>```
>{{BaseUrl}}/api/UrReceteOperasyonMamul
>```
### Body (**raw**)

```json

```


? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: �retim Hareketi 


## End-point: UrAkisOperasyonPersonel
�retim ak�� operasyon personel bilgilerini listeleyebildi�iniz k�s�md�r.
### Method: GET
>```
>{{BaseUrl}}/api/UrAkisOperasyonPersonel
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: UrAkisOperasyonMamul
�retim ak�� operasyon mamul bilgilerini listeleyebildi�iniz k�s�md�r.
### Method: GET
>```
>{{BaseUrl}}/api/UrAkisOperasyonMamul
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: UrAkisOperasyonHammadde
�retim ak�� operasyon hammadde bilgilerini listeleyebildi�iniz k�s�md�r.
### Method: GET
>```
>{{BaseUrl}}/api/UrAkisOperasyonHammadde
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: G�revler 


## End-point: G�revler
G�rev bilgilerini listeleyebildi�iniz k�s�md�r.
### Method: GET
>```
>{{BaseUrl}}/api/Gorevler
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: G�rev Kullanicilari
G�rev kullan�c� bilgilerini listeleyebildi�iniz k�s�md�r.
### Method: GET
>```
>{{BaseUrl}}/api/GorevKullanicilari
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: G�rev Hareketleri
G�rev hareket bilgilerini listeleyebildi�iniz k�s�md�r.
### Method: GET
>```
>{{BaseUrl}}/api/GorevHareketleri
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?

## End-point: G�revler Alt
Alt g�rev bilgilerini listeleyebildi�iniz k�s�md�r.

Not: Hen�z aktif de�ildir.
### Method: GET
>```
>{{BaseUrl}}/api/GorevlerAlt
>```

? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ? ?
# ?? Collection: Stok Vergi 


## End-point: Stok Vergi Getir
Sistemde kay�tl� olan b�t�n stok vergi kartlar�n�n g�r�nt�lendi�i aland�r.
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

Yeni bir stok vergi kart� olu�turmaktad�r.
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

## End-point: Stok Vergi D�zenle
Stoktaki bir �r�n� d�zenlemek i�indir.

###### Stok eklemek ile d�zenlemek aras�ndaki fark KayitTipi=2 olmas�d�r ve StokID d���ndaki parametrelerin zorunlu olmamas�d�r.
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
Stoktaki bir �r�n� silmek i�indir.

######  Stok silmek ile d�zenlemek aras�ndaki fark KayitTipi=-1 olmas�d�r. Sto�u silerken ba�l� oldu�u b�t�n fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata d�necektir.
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
