---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: cURL
  - javascript: Node.js
  - csharp: C#
  - python: Python
  - java: Java

toc_footers:
  - <a href='https://www.aaro.com.tr/iletisim/'>Geliştirici Keyi Alın</a>
  - <a href='https://github.com/AaroYazilim'>Github hesabımız</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Giriş

Aaro Yazılım web API dökümantasyonuna hoş geldiniz. API aracılığıyla Aaro Erp uç noktalarına erişim sağlayarak stok, cari veya banka gibi çeşitli kalemler için sorgularda bulunabilirsiniz. 

API ile Aaro Web arayüzü ile yapılan işlemlerin büyük bir kısmını gerçekleştirebilirsiniz. Üretim modülleri henüz aktif halde değildir.

Dillere göre ayırdığımız siyah alanda kod örnekleri görebilirsiniz. Aynı bölgeden dil değişimini gerçekleştirebilirsiniz.

Talepleriniz için lütfen [Github](https://github.com/AaroYazilim) sayfamızı ziyaret edin.


# Authentication

> Örnek authentication kodları:


```shell

curl --location --request POST 'https://erp.aaro.com.tr/Token' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'grant_type=password' \
--data-urlencode 'username=YOURUSERNAME' \
--data-urlencode 'password=YOURPASSWORD'

```

```javascript

var axios = require('axios');
var qs = require('qs');
var data = qs.stringify({
'grant_type': 'password',
'username': 'KULLANICIADINIZ',
'password': 'SIFRENIZ' 
});
var config = {
  method: 'post',
  url: 'https://erp.aaro.com.tr/Token',
  headers: { 
    'Content-Type': 'application/x-www-form-urlencoded', 
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});


```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/Token");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/x-www-form-urlencoded");
request.AddParameter("grant_type", "password");
request.AddParameter("username", "YOURUSERNAME");
request.AddParameter("password", "YOURPASSWORD");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/Token"

payload = 'grant_type=password&username=YOURUSERNAME&password=YOURPASSWORD'
headers = {
  'Content-Type': 'application/x-www-form-urlencoded'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/Token")
  .header("Content-Type", "application/x-www-form-urlencoded")
  .field("grant_type", "password")
  .field("username", "YOURUSERNAME")
  .field("password", "YOURPASSWORD")
  .asString();

```

> Başarılı bir authentication işlemi sonrası aşağıdaki şekilde 12 saat geçerli Token almaktasınız.

```json
{
    "access_token": "token-code",
    "token_type": "bearer",
    "expires_in": 43199,
    "refresh_token": "refresh-token-code",
    "userName": "KULLANICI-ADINIZ",
    ".issued": "Tue, 01 Sep 2020 11:25:25 GMT",
    ".expires": "Tue, 01 Sep 2020 23:25:25 GMT"
}

```

API kimlik doğrulama için oAuth2 kullanmaktadır. Bu protokolü destekleyen istemci kütüphanelerini kullanarak oturum açabilir ve API'yi kullanabilirsiniz.

Gerekli USERNAME, PASSWORD bilgilerini almak için ücretsiz hesap açabilir ya da destek@aaro.com.tr adresine mail atabilirsiniz.

Kimlik doğrulama işleminin başarılı olması durumunda bir adet kimlik jetonu (access_token) gönderilecektir. Kimlik jetonu 12 saat süreyle geçerlidir ve yapacağınız her istekte http başlık(Header) bilgilerinin içerisinde gönderilmelidir.


<aside class="notice">
Şirket hesabınızın yetkili kullanıcısının oturum bilgileri API hesabınız için de kullanılabilmektedir.
</aside>

# Stok

## Stoktaki Ürünleri Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Stok' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://erp.aaro.com.tr/api/Stok',
  headers: {
    'Authorization': 'Bearer YOURTOKEN'
  }
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Stok");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

import requests

url = "https://erp.aaro.com.tr/api/Stok"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/Stok")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 3267,
        "ToplamSayfaSayisi": 327,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": true,
        "SayfaSatirSayisiAktifSayfada": 10
    },
    "Model": [
        {
            "StokVergiAdi": "KDV % 18",
            "StokVergiAlisKDVOrani": 18,
            "StokVergiSatisKDVOrani": 18,
            "StokVergiKodu": "KDV18",
            "Brm1Kodu": "MT",
            "Brm2Kodu": null,
            "Brm3Kodu": null,
            "RaporBrmKodu": null,
            "UretimBrmKodu": null,
            "Miktar": -85.000000,
            "KartPuan": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT1",
            "SirketAdi": "Şirket 1",
            "EntegrasyonTanimKodu": "HM9029",
            "EntegrasyonTanimAdi": "(ST37-2)28 lik TRANSMİSYON MİLİ",
            "TipAdi": "Stok",
            "TipKodu": null,
            "OnayDurum": 1,
            "OlsTar": "2020-10-02T15:43:40.91",
            "DgsTar": "2021-02-10T09:41:58.967",
            "OlsID": 2,
            "OlsKodu": "yonetici",
            "OlsAdi": "yonetici",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "yonetici",
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
            "EsnekAramaKisiti": "HM9029 (ST37-2)28 lik TRANSMİSYON MİLİ            ",
            "StokID": 1086,
            "StokKodu": "HM9029",
            "StokAdi": "(ST37-2)28 lik TRANSMİSYON MİLİ",
            "StokKisaKodu": "HM9029",
            "StokKisaAdi": "(ST37-2)28 lik TRANSMİSYON MİLİ",
            "StokMuhasebeID": 209,
            "StokVergiID": 1,
            "Brm1ID": 2,
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
            "ZorunluDemirbas": false,
            "ZorunluStok": false,
            "ZorunluDekont": false,
            "ZorunluCari": false,
            "Seviye": 0,
            "FiyatEtiketi": null,
            "BayiGozuksunMu": false,
            "BayiMaksMiktar": 0,
            "YedekD1": null,
            "YedekD2": null,
            "SubeID": 1,
            "SirketID": 1,
            "Durum": true,
            "TipID": 105001,
            "EntegrasyonTanimID": 2957,
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
        },
        {
          ...
          },
        {
          ...
          },
    ],
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
```

Bu uç nokta ile stoklardaki ürünleri toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.



### HTTP Request

`GET https://erp.aaro.com.tr/api/Stok?`

### URL Parametreleri

Parameter | Değer | Tanım
--------- | ----------- | ---------
EsnekAramaKisiti | String | Dilediğiniz stringe göre listeleme yapabilirsiniz. Stok kodunda, stok adında, etiket adlarında, kod adlarında girilen string'e göre arama yapar.
SiralamaKisiti | String | Gelen veriyi sıralamak için kullanılır. Durum, StokID gibi kolon adları verilmelidir.
Sayfa | Integer | Kaç sayfa ürün getirmek istediğiniz
SayfaSatirSayisi |Integer | Getirilen sayfadaki ürün limiti.
StokID | Integer | Belirtilen ID ile ürünü getirmektedir.
Durum | Boolean | True ise aktif, false ise pasif ürünleri getirmektedir.
TipID |Integer | Dökümantasyondaki TipID listesini inceleyiniz. Ürün tiplerinin
SubeID | Integer | Şube ID'sine göre ürünleri getirmektedir.
SirketID | Integer | Şirket ID'sine göre ürünleri getirmektedir.
StokMuhasebeID | Integer | Stok Muhasebe ID'sine göre ürünleri getirmektedir.
StokVergiID | Integer | Stok Vergi ID'sine göre ürünleri getirmektedir.
OlsID | Integer | Stoğu Oluşturan kişi ID'sine göre ürünleri getirmektedir.




## Stok Ekle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"StokID": -1,
        "SubeID": 1,
        "SirketID": 1,
        "StokKodu": "000000000000044",
        "StokAdi": "kolonya",
        "StokKisaKodu": "000000000000044",
        "StokKisaAdi": "kolonya",
        "Durum": true,
        "TipID": 105001,
        "StokMuhasebeID": 201,
        "StokVergiID": 1,
        "Brm1ID": 1,
        "Brm2ID": null,
        "Brm3ID": null,
        "CevirimBrm2": null,
        "CevirimBrm3": null,
        "Kalinlik": 10.0,
        "En": 10.0,
        "Boy": 10.0,
        "Yogunluk": 3.0,
        "Agirlik": 5.0,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null
        
}'

```

```javascript

var axios = require('axios');
var data = JSON.stringify({"StokID":-1,"SubeID":1,"SirketID":1,"StokKodu":"000000000000049","StokAdi":"kolonya","StokKisaKodu":"000000000000049","StokKisaAdi":"kolonya","Durum":true,"TipID":105001,"StokMuhasebeID":201,"StokVergiID":1,"Brm1ID":1,"Brm2ID":null,"Brm3ID":null,"CevirimBrm2":null,"CevirimBrm3":null,"Kalinlik":10,"En":10,"Boy":10,"Yogunluk":3,"Agirlik":5,"Kod1ID":null,"Etiket1ID":null,"SablonID":null});

var config = {
  method: 'post',
  url: 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer YOURTOKEN'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddParameter(
  "application/json",
  "{\n    \t\"StokID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"kolonya\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"kolonya\",\n        \"Durum\": true,\n        \"TipID\": 105001,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}",
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1"

payload = "{\n    \t\"StokID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"kolonya\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"kolonya\",\n        \"Durum\": true,\n        \"TipID\": 105001,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}"
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .body("{\n    \t\"StokID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"kolonya\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"kolonya\",\n        \"Durum\": true,\n        \"TipID\": 105001,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "StokVergiAdi": "KDV % 18",
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
        "SubeKodu": "SRKT.SUBE",
        "SubeAdi": "Şubem",
        "SirketKodu": "SRKT1",
        "SirketAdi": "Şirket 1",
        "EntegrasyonTanimKodu": null,
        "EntegrasyonTanimAdi": null,
        "TipAdi": "Stok",
        "TipKodu": null,
        "OnayDurum": 1,
        "OlsTar": "2021-02-22T08:38:01.733",
        "DgsTar": "2021-02-22T08:38:01.733",
        "OlsID": 2,
        "OlsKodu": "yonetici",
        "OlsAdi": "yonetici",
        "DgsID": 2,
        "DgsKodu": "yonetici",
        "DgsAdi": "yonetici",
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
        "EsnekAramaKisiti": "000000000000089 kolonya",
        "StokID": 3707,
        "StokKodu": "000000000000089",
        "StokAdi": "kolonya",
        "StokKisaKodu": "000000000000089",
        "StokKisaAdi": "kolonya",
        "StokMuhasebeID": 201,
        "StokVergiID": 1,
        "Brm1ID": 1,
        "Brm2ID": null,
        "Brm3ID": null,
        "UretimBrmID": null,
        "RaporBrmID": null,
        "CevirimBrm2": null,
        "CevirimBrm3": null,
        "Kalinlik": 10.000000,
        "En": 10.000000,
        "Boy": 10.000000,
        "Yogunluk": 3.000000,
        "Agirlik": 5.000000,
        "GTIP": null,
        "ZorunluDemirbas": false,
        "ZorunluStok": false,
        "ZorunluDekont": false,
        "ZorunluCari": false,
        "Seviye": 0,
        "FiyatEtiketi": null,
        "BayiGozuksunMu": false,
        "BayiMaksMiktar": 0,
        "YedekD1": null,
        "YedekD2": null,
        "SubeID": 1,
        "SirketID": 1,
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
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Yeni bir stok kartı eklemek için

### HTTP Request

`GET https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1`

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
StokVergiID | 1 | Stoğun satış ve alış faturasında hangi vergilere tabii olduğunu belirtmektedir. 1 girilmesi durumunda standart olarak %18 KDV sınıfına ekler. | Evet
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




<aside class="success">
Ürün oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.
</aside>

## Stoğu Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"StokID": 356,
        "SubeID": 1,
        "SirketID": 1,
        "StokKodu": "000000000000044",
        "StokAdi": "kolonya",
        "StokKisaKodu": "000000000000044",
        "StokKisaAdi": "kolonya",
        "Durum": true,
        "TipID": 105001,
        "StokMuhasebeID": 201,
        "StokVergiID": 1,
        "Brm1ID": 1,
        "Brm2ID": null,
        "Brm3ID": null,
        "CevirimBrm2": null,
        "CevirimBrm3": null,
        "Kalinlik": 10.0,
        "En": 10.0,
        "Boy": 10.0,
        "Yogunluk": 3.0,
        "Agirlik": 5.0,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null
        
}'

```

```javascript

var axios = require('axios');
var data = JSON.stringify({"StokID":356,"SubeID":1,"SirketID":1,"StokKodu":"000000000000045","StokAdi":"kolonyağı","StokKisaKodu":"000000000000045","StokKisaAdi":"kolonyağı","Durum":true,"TipID":105001,"StokMuhasebeID":201,"StokVergiID":1,"Brm1ID":1,"Brm2ID":null,"Brm3ID":null,"CevirimBrm2":null,"CevirimBrm3":null,"Kalinlik":16,"En":10,"Boy":10,"Yogunluk":3,"Agirlik":5,"Kod1ID":null,"Etiket1ID":null,"SablonID":null});

var config = {
  method: 'post',
  url: 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer YOURTOKEN'
 
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});


```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter(
  "application/json",
  "{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"kolonya\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"kolonya\",\n        \"Durum\": true,\n        \"TipID\": 105001,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}",
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2"

payload = "{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"kolonya\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"kolonya\",\n        \"Durum\": true,\n        \"TipID\": 105001,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}"
headers = {
  'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .body("{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"kolonya\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"kolonya\",\n        \"Durum\": true,\n        \"TipID\": 105001,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "StokVergiAdi": "KDV % 18",
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
        "SubeKodu": "SRKT.SUBE",
        "SubeAdi": "Şubem",
        "SirketKodu": "SRKT1",
        "SirketAdi": "Şirket 1",
        "EntegrasyonTanimKodu": null,
        "EntegrasyonTanimAdi": null,
        "TipAdi": "Stok",
        "TipKodu": null,
        "OnayDurum": 1,
        "OlsTar": "2021-02-15T12:03:47.18",
        "DgsTar": "2021-02-22T09:08:15.23",
        "OlsID": 2,
        "OlsKodu": "yonetici",
        "OlsAdi": "yonetici",
        "DgsID": 2,
        "DgsKodu": "yonetici",
        "DgsAdi": "yonetici",
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
        "EsnekAramaKisiti": "000000000000087 kolonya apiden degistirildi            ",
        "StokID": 3705,
        "StokKodu": "000000000000087",
        "StokAdi": "kolonya apiden degistirildi",
        "StokKisaKodu": "000000000000087",
        "StokKisaAdi": "kolonya",
        "StokMuhasebeID": 201,
        "StokVergiID": 1,
        "Brm1ID": 1,
        "Brm2ID": null,
        "Brm3ID": null,
        "UretimBrmID": null,
        "RaporBrmID": null,
        "CevirimBrm2": null,
        "CevirimBrm3": null,
        "Kalinlik": 10.000000,
        "En": 10.000000,
        "Boy": 10.000000,
        "Yogunluk": 3.000000,
        "Agirlik": 5.000000,
        "GTIP": null,
        "ZorunluDemirbas": false,
        "ZorunluStok": false,
        "ZorunluDekont": false,
        "ZorunluCari": false,
        "Seviye": 0,
        "FiyatEtiketi": null,
        "BayiGozuksunMu": false,
        "BayiMaksMiktar": 0,
        "YedekD1": null,
        "YedekD2": null,
        "SubeID": 1,
        "SirketID": 1,
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
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}

```

Stoktaki bir ürünü düzenlemek içindir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 2 seçilerek mevcut ürünün düzenleneceği bilgisi verilmiştir.





<aside class="warning">
Stok eklemek ile düzenlemek arasındaki fark KayitTipi=2 olmasıdır.
</aside>




## Stoktaki Ürünü Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"StokID": 356,
        "SubeID": 1,
        "SirketID": 1,
        "StokKodu": "000000000000044",
        "StokAdi": "kolonya",
        "StokKisaKodu": "000000000000044",
        "StokKisaAdi": "kolonya",
        "Durum": true,
        "TipID": 105001,
        "StokMuhasebeID": 201,
        "StokVergiID": 1,
        "Brm1ID": 1,
        "Brm2ID": null,
        "Brm3ID": null,
        "CevirimBrm2": null,
        "CevirimBrm3": null,
        "Kalinlik": 10.0,
        "En": 10.0,
        "Boy": 10.0,
        "Yogunluk": 3.0,
        "Agirlik": 5.0,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null
        
}'

```

```javascript

var axios = require('axios');
var data = JSON.stringify({"StokID":348,"StokKodu":"111111150","StokAdi":"Masif Ahşap Sehpa","StokKisaKodu":"111111150","StokKisaAdi":"Masif Ahşap Sehpa","Durum":true,"CevirimBrm2":null,"CevirimBrm3":null,"Kalinlik":0,"En":0,"Boy":0,"Yogunluk":0,"Agirlik":0,"OlsTar":"2020-07-03T14:53:53.837","DgsTar":"2020-07-03T14:53:53.837","OnayDurum":1,"TipID":105001,"TipAdi":"Stok","SubeID":1,"SubeKodu":"SRKT.SUBE","SubeAdi":"Şubem","SirketID":1,"SirketKodu":"SRKT","SirketAdi":"Şirketim","StokMuhasebeID":201,"StokMuhasebeKodu":"STOK","StokMuhasebeAdi":"Stok 153, 600, 150, 151, 152, 601, 610, 611","StokVergiID":42,"StokVergiKodu":"KDV57","StokVergiAdi":"Stok(KDV 57)","Brm1ID":1,"Brm1Kodu":"AD","Brm1Adi":"Adet","Brm2ID":null,"Brm2Kodu":null,"Brm2Adi":null,"Brm3ID":null,"Brm3Kodu":null,"Brm3Adi":null,"Kod1ID":null,"Kod1Kodu":null,"Kod1Adi":null,"OlsID":4,"OlsKodu":"MSK","OlsAdi":"Şamil","DgsID":4,"DgsKodu":"MSK","DgsAdi":"Şamil","Etiket1ID":null,"Etiket1Adi":null,"SablonID":null,"SablonKodu":null,"SablonAdi":null});

var config = {
  method: 'post',
  url: 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer YOURTOKEN'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddParameter(
  "application/json",
  "{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"kolonya\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"kolonya\",\n        \"Durum\": true,\n        \"TipID\": 105001,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}",
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1"

payload = "{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"kolonya\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"kolonya\",\n        \"Durum\": true,\n        \"TipID\": 105001,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}"
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .body("{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"kolonya\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"kolonya\",\n        \"Durum\": true,\n        \"TipID\": 105001,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
Başarılı sonuç:

{
    "Model": null,
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}

Hatalı sonuç:
{
    "Model": {
        "StokID": 1255,
        "StokKodu": "SAC 01",
        "StokAdi": null,
        "StokKisaKodu": null,
        "StokKisaAdi": null,
        "StokMuhasebeID": null,
        "StokVergiID": null,
        "Brm1ID": null,
        "Brm2ID": null,
        "Brm3ID": null,
        "UretimBrmID": null,
        "RaporBrmID": null,
        "CevirimBrm2": null,
        "CevirimBrm3": null,
        "Kalinlik": 0.0,
        "En": 0.0,
        "Boy": 0.0,
        "Yogunluk": 0.0,
        "Agirlik": 0.0,
        "GTIP": null,
        "ZorunluDemirbas": false,
        "ZorunluStok": false,
        "ZorunluDekont": false,
        "ZorunluCari": false,
        "Seviye": 0,
        "FiyatEtiketi": null,
        "BayiGozuksunMu": false,
        "BayiMaksMiktar": 0,
        "YedekD1": null,
        "YedekD2": null,
        "SubeID": 0,
        "SirketID": 0,
        "Durum": false,
        "TipID": 0,
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
    },
    "Mesajlar": {
        "Mesaj": "Hareket kayıtları mevcut. Bu kaydı silemezsiniz."
    },
    "Sonuc": false,
    "MesajlarTumu": "Hareket kayıtları mevcut. Bu kaydı silemezsiniz."
}

```

Stoktaki bir ürünü silmek içindir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | -1 seçilerek mevcut ürünün silineceği bilgisi verilmiştir.





<aside class="warning">
Stok silmek ile düzenlemek arasındaki fark KayitTipi=-1 olmasıdır. Stoğu silerken bağlı olduğu bütün fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
</aside>







# Barkod

## Stoktaki Ürünün Barkodunu Getir
```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/StokBarkod' \
--header 'Authorization: Bearer YOURTOKEN' 


```

```javascript

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://erp.aaro.com.tr/api/StokBarkod',
  headers: { 
    'Authorization': 'Bearer YOURTOKEN'
  }
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});


```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/StokBarkod");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokBarkod"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))



```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/StokBarkod")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir(Birden fazla barkod eklenmiştir):

```json
{
    "SayfalandirmaBilgisi": {
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
            "BarkodID": 4,
            "StokID": 201,
            "BarkodNo": "t0712345678911",
            "BarkodTip": "Teknoloji"
        },
        {
            "BarkodID": 3,
            "StokID": 201,
            "BarkodNo": "m0712345678911",
            "BarkodTip": "Masaüstü Bilgisayar"
        },
        {
            "BarkodID": 2,
            "StokID": 201,
            "BarkodNo": "s0712345678911",
            "BarkodTip": "Asus a722"
        }
    ],
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}

```

Aaro bir ürün için sonsuz sayıda barkodu kabul etmektedir. Dolayısıyla barkod getir değil barkodları getir şekline çalışmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
SayfaSatirSayisi | Integer | Getirilen sayfadaki barkod sayısı
Sayfa | Integer | Getirilmesi istenen sayfa numarası
StokID| Integer | Stoktaki barkodu getirilmesi istenen ürün
BarkodID| Integer | Getirilmesi istenenen barkod ID
BarkodNo | String | Barkod Numarasına göre getirilecek barkod
BarkodTip | String | Barkod Tipine göre getirilecek barkodlar


<aside class="info">
Birden fazla sonuç gelebilmektedir
</aside>



## Stoktaki Ürüne Barkod Ekle


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "BarkodID": -1,
    "StokID": 201,
    "BarkodNo": "s0712345678911",
    "BarkodTip": "Bilgisayar Kategorisi"
}'

```

```javascript

var axios = require('axios');
var data = JSON.stringify({"BarkodID":6,"StokID":201,"BarkodNo":"s0712345678911","BarkodTip":"Telefon Kategorisi"});

var config = {
  method: 'post',
  url: 'https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=1',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer YOURTOKEN'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"BarkodID\": -1,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s0712345678911\",\n    \"BarkodTip\": \"Bilgisayar Kategorisi\"\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=1"

payload = "{\n    \"BarkodID\": -1,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s0712345678911\",\n    \"BarkodTip\": \"Bilgisayar Kategorisi\"\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"BarkodID\": -1,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s0712345678911\",\n    \"BarkodTip\": \"Bilgisayar Kategorisi\"\n}")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    
  
    "Model": {
        "BarkodID": 6,
        "StokID": 201,
        "BarkodNo": "s0712345678911",
        "BarkodTip": "Bilgisayar Kategorisi"
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""

}

```

Aaro bir ürün için sonsuz sayıda barkodu kabul etmektedir. Dolayısıyla barkodları haricen eklemelisiniz.

### HTTP Request

`POST https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 (KayitTipi=1 bütün API yapısında ürün kaydet demektir)


### Sorgu Body Parametreleri

Parametre | Değer | Tanım | Örnek Değer
--------- | ----------- | --------- | ---------
BarkodID | Integer | Barkodun sahip olduğu ID'dir. Özel belirtmek istemiyorsanız -1 verebilirsiniz. | -1
StokID | Integer | Hangi stoğa bu barkodu vermek istediğinizi belirtmelisiniz | 201
BarkodNo | String | Barkodun ürün üstünde görünen kısmıdır. | "s0712345678911"
BarkodTip | String | Barkodun ait olduğu stok tipidir. | "Bilgisayar Kategorisi"

<aside class="info">
Barkod eklemek tamamen opsiyoneldir.
</aside>




## Stoktaki Ürünün Barkodunu Düzenle


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "BarkodID": 6,
    "StokID": 201,
    "BarkodNo": "s0712345678911",
    "BarkodTip": "Telefon Kategorisi"
}'

```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=2',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"BarkodID":6,"StokID":201,"BarkodNo":"s0712345678911","BarkodTip":"Telefon Kategorisi"})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"BarkodID\": 6,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s0712345678911\",\n    \"BarkodTip\": \"Telefon Kategorisi\"\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=2"

payload = "{\n    \"BarkodID\": 6,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s0712345678911\",\n    \"BarkodTip\": \"Telefon Kategorisi\"\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"BarkodID\": 6,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s0712345678911\",\n    \"BarkodTip\": \"Telefon Kategorisi\"\n}")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    
  
    "Model": {
        "BarkodID": 6,
        "StokID": 201,
        "BarkodNo": "s0712345678911",
        "BarkodTip": "Telefon Kategorisi"
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""

}

```

Değiştirmek istediğiniz barkod için aşağıdaki yapıyı kullanınız.

### HTTP Request

`POST https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=2`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 2 (KayitTipi=2 bütün API yapısında ürün düzelt demektir)


### Sorgu Body Parametreleri

Parametre | Değer | Tanım | Örnek Değer
--------- | ----------- | --------- | ---------
BarkodID | Integer | Düzeltmek istediğiniz barkod ID'si | 6
StokID | Integer | Hangi stoğa bu barkodu vermek istediğinizi belirtmelisiniz | 201
BarkodNo | String | Barkodun ürün üstünde görünen kısmıdır. | "s0712345678911"
BarkodTip | String | Barkodun ait olduğu stok tipidir. | "Telefon Kategorisi"

<aside class="info">
Sadece kayıt tipi 2 olarak değişmektedir. BarkodID'si ise 6 olarak girilerek istenilen barkoda ulaşılmıştır.
</aside>


## Stoktaki Ürünün Barkodunu Sil


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "BarkodID": 6,
    "StokID": 201,
    "BarkodNo": "s0712345678911",
    "BarkodTip": "Telefon Kategorisi"
}'

```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"BarkodID":6,"StokID":201,"BarkodNo":"s0712345678911","BarkodTip":"Telefon Kategorisi"})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"BarkodID\": 6,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s0712345678911\",\n    \"BarkodTip\": \"Telefon Kategorisi\"\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1"

payload = "{\n    \"BarkodID\": 6,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s0712345678911\",\n    \"BarkodTip\": \"Telefon Kategorisi\"\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"BarkodID\": 6,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s0712345678911\",\n    \"BarkodTip\": \"Telefon Kategorisi\"\n}")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "BarkodID": 0,
        "StokID": 0,
        "BarkodNo": null,
        "BarkodTip": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}

```

Değiştirmek istediğiniz barkod için aşağıdaki yapıyı kullanınız.

### HTTP Request

`POST https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | -1 (KayitTipi=-1 bütün API yapısında ürün sil demektir)


### Sorgu Body Parametreleri

Parametre | Değer | Tanım | Örnek Değer
--------- | ----------- | --------- | ---------
BarkodID | Integer | Düzeltmek istediğiniz barkod ID'si | 6
StokID | Integer | Hangi stoğa bu barkodu vermek istediğinizi belirtmelisiniz | 201
BarkodNo | String | Barkodun ürün üstünde görünen kısmıdır. | "s0712345678911"
BarkodTip | String | Barkodun ait olduğu stok tipidir. | "Telefon Kategorisi"

<aside class="info">
Sadece kayıt tipi -1 olarak değişmektedir.
</aside>




# Depo 

## Depoları Getir


```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Depo?SayfaSatirSayisi=10' \
--header 'Authorization: Bearer YOURTOKEN' \

```

```javascript

var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://erp.aaro.com.tr/api/Depo?SayfaSatirSayisi=10',
  'headers': {
    'Authorization': 'Bearer YOURTOKEN',
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});




```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Depo?SayfaSatirSayisi=10");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Depo?SayfaSatirSayisi=10"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN',
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/Depo?SayfaSatirSayisi=10")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "SayfalandirmaBilgisi": {
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 3,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 3
    },
    "Model": [
               {
            "SubeKodu": "TUM",
            "SubeAdi": "Tüm Şubeler",
            "SirketKodu": "SRKT0",
            "SirketAdi": "Şirket 0",
            "TipAdi": "Depo",
            "TipKodu": null,
            "OnayDurum": 1,
            "OlsTar": "2020-09-30T10:33:58.5",
            "DgsTar": "2020-09-30T10:33:58.5",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "",
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
            "EsnekAramaKisiti": "DPM Depom           ",
            "DepoID": 2,
            "DepoKodu": "DPM",
            "DepoAdi": "Depom",
            "CariID": null,
            "CariKodu": null,
            "MaxHacim": null,
            "MaxAgirlik": 0.000000,
            "SubeID": 0,
            "SirketID": 0,
            "Durum": true,
            "TipID": 107001,
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
        },
        {
          ...
        },
        {
          ...
        }
    ],
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}

```

Mevcut bütün depoları getirmektedir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Depo?`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
EsnekAramaKisiti | String | Dilediğiniz stringe göre listeleme yapabilirsiniz. Depo kodunda, depo adında, etiket adlarında, kod adlarında girilen string'e göre arama yapar.
SayfaSatirSayisi | Integer | Limitli sayıda depo getirmek için kullanılmaktadır.
DepoID | Integer | Sadece belirli bir depoyu getirmek için eklenmektedir.





## Depo Oluştur


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "DepoKodu": "001",
    "DepoAdi": "Online Satış Deposu",
    "TipID": 105001
}'

```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"DepoKodu":"001","DepoAdi":"Online Satış Deposu","TipID":105001})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});





```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"DepoKodu\": \"001\",\n    \"DepoAdi\": \"Online Satış Deposu\",\n    \"TipID\": 105001\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1"

payload = "{\n    \"DepoKodu\": \"001\",\n    \"DepoAdi\": \"Online Satış Deposu\",\n    \"TipID\": 105001\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"DepoKodu\": \"001\",\n    \"DepoAdi\": \"Online Satış Deposu\",\n    \"TipID\": 105001\n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "DepoID": 5,
        "SubeID": 0,
        "SirketID": 0,
        "DepoKodu": "001",
        "DepoAdi": "Online Satış Deposu",
        "CariID": null,
        "Durum": false,
        "TipID": 105001,
        "Kod1ID": null,
        "OnayDurum": 1,
        "OlsID": 4,
        "OlsTar": "2020-07-06T13:37:32.5132058+03:00",
        "DgsID": 4,
        "DgsTar": "2020-07-06T13:37:32.5132058+03:00",
        "Etiket1ID": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}

```

Yeni bir depo eklemek için kullanılmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 (KayitTipi=1 bütün API yapısında ürün kaydet demektir)


### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
DepoKodu | String | Depoya vereceğiniz koddur.
DepoAdi | String | Deponuza vereceğiniz ad. (Örnek: "Ankara/Çankaya Depo")
TipID | Integer | Deponuzun ne tür bir depo olduğunu belirtmeniz gerekmektedir. Bu depoya stok eklerken, stok kartlarında da bu TipID'yi belirtmeniz gerekmektedir.


## Depoyu Düzenle


```shell


curl --location --request POST 'https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "DepoID": 5,
    "DepoKodu": "001",
    "DepoAdi": "Ankara Satış Deposu",
    "TipID": 105001
}'

```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"DepoID":5,"DepoKodu":"001","DepoAdi":"Ankara Satış Deposu","TipID":105001})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});






```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"DepoID\": 5,\n    \"DepoKodu\": \"001\",\n    \"DepoAdi\": \"Ankara Satış Deposu\",\n    \"TipID\": 105001\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2"

payload = "{\n    \"DepoID\": 5,\n    \"DepoKodu\": \"001\",\n    \"DepoAdi\": \"Ankara Satış Deposu\",\n    \"TipID\": 105001\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))



```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"DepoID\": 5,\n    \"DepoKodu\": \"001\",\n    \"DepoAdi\": \"Ankara Satış Deposu\",\n    \"TipID\": 105001\n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json

    {
    "Model": {
        "DepoID": 5,
        "SubeID": 0,
        "SirketID": 0,
        "DepoKodu": "001",
        "DepoAdi": "Ankara Satış Deposu",
        "CariID": null,
        "Durum": false,
        "TipID": 105001,
        "Kod1ID": null,
        "OnayDurum": 1,
        "OlsID": 4,
        "OlsTar": "2020-07-06T13:50:22.2301736+03:00",
        "DgsID": 4,
        "DgsTar": "2020-07-06T13:50:22.2301736+03:00",
        "Etiket1ID": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}


```

Mevcut bir deponun düzeltilmesi için kullanılmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 2 (KayitTipi=2 bütün API yapısında PUT işlemine karşılık gelmektedir.)


### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
DepoID | Integer | Düzeltmek istediğiniz deponun ID'si
DepoKodu | String | Depoya vereceğiniz koddur.
DepoAdi | String | Deponuza vereceğiniz ad. (Örnek: "Ankara/Çankaya Depo")
TipID | Integer | Deponuzun ne tür bir depo olduğunu belirtmeniz gerekmektedir. Bu depoya stok eklerken, stok kartlarında da bu TipID'yi belirtmeniz gerekmektedir.

<aside class="warning">
Depo eklemekten farklı olarak ID eklenmesi gerekmektedir.
</aside>


## Depoyu Sil


```shell


curl --location --request POST 'https://erp.aaro.com.tr/api/Depo/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "DepoID": 5,
    "DepoKodu": "001",
    "DepoAdi": "Ankara Satış Deposu",
    "TipID": 105001
}'

```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/Depo/post?KayitTipi=-1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"DepoID":5,"DepoKodu":"001","DepoAdi":"Ankara Satış Deposu","TipID":105001})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});






```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Depo/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"DepoID\": 5,\n    \"DepoKodu\": \"001\",\n    \"DepoAdi\": \"Ankara Satış Deposu\",\n    \"TipID\": 105001\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=-1"

payload = "{\n    \"DepoID\": 5,\n    \"DepoKodu\": \"001\",\n    \"DepoAdi\": \"Ankara Satış Deposu\",\n    \"TipID\": 105001\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))



```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Depo/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"DepoID\": 5,\n    \"DepoKodu\": \"001\",\n    \"DepoAdi\": \"Ankara Satış Deposu\",\n    \"TipID\": 105001\n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "DepoID": 0,
        "SubeID": 0,
        "SirketID": 0,
        "DepoKodu": null,
        "DepoAdi": null,
        "CariID": null,
        "Durum": false,
        "TipID": 0,
        "Kod1ID": null,
        "OnayDurum": 0,
        "OlsID": 0,
        "OlsTar": "0001-01-01T00:00:00",
        "DgsID": 0,
        "DgsTar": "0001-01-01T00:00:00",
        "Etiket1ID": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}

```

Mevcut bir deponun düzeltilmesi için kullanılmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Depo/post?KayitTipi=-1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | -1 (KayitTipi=-1 bütün API yapısında DELETE işlemine karşılık gelmektedir.)


### Sorgu Body Parametreleri

Yalnızca ID ile de silme işlemini gerçekleştirebilirsiniz.

Parametre | Değer | Tanım
--------- | ----------- | ---------
DepoID | Integer | Silmek istediğiniz deponun ID'si
DepoKodu | String | Depo kodunuz.
DepoAdi | String | Depo adınız.
TipID | Integer | Deponuzun ne tür bir depo olduğunu belirtmeniz gerekmektedir. Bu depoya stok eklerken, stok kartlarında da bu TipID'yi belirtmeniz gerekmektedir.

<aside class="warning">
Depoyu silmeden önce depoya ait bütün hareketlerin ve stoklar silindiğinden/taşındığından emin olunuz. Aksi takdirde silme işlemi gerçekleşmeyecektir.
</aside>

# Vergi / Vergi Daireleri

## Vergi Oranlarını Getir


```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/StokVergi' \
--header 'Authorization: Bearer YOURTOKEN' 


```

```javascript

var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://erp.aaro.com.tr/api/StokVergi?',
  'headers': {
    'Authorization': 'Bearer YOURTOKEN'
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});




```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/StokVergi?");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokVergi?"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/StokVergi")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "SayfalandirmaBilgisi": {
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 85,
        "ToplamSayfaSayisi": 9,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": true,
        "SayfaSatirSayisiAktifSayfada": 10
    },
    "Model": [
        {
            "StokVergiID": 3,
            "SubeID": 0,
            "SirketID": 0,
            "StokVergiKodu": "KDV01",
            "StokVergiAdi": "KDV % 1 ",
            "AlisKDVOrani": 1,
            "SatisKDVOrani": 1,
            "TevkifatVergiAltID": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SablonID": null
        },
        {
            "StokVergiID": 1,
            "SubeID": 0,
            "SirketID": 0,
            "StokVergiKodu": "KDV18",
            "StokVergiAdi": "KDV % 18",
            "AlisKDVOrani": 18,
            "SatisKDVOrani": 18,
            "TevkifatVergiAltID": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SablonID": null
        },
        {
            "StokVergiID": 2,
            "SubeID": 0,
            "SirketID": 0,
            "StokVergiKodu": "KDV08",
            "StokVergiAdi": "KDV % 8 ",
            "AlisKDVOrani": 8,
            "SatisKDVOrani": 8,
            "TevkifatVergiAltID": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SablonID": null
        },
        {
            "StokVergiID": 85,
            "SubeID": 1,
            "SirketID": 1,
            "StokVergiKodu": "KDV100",
            "StokVergiAdi": "Stok(KDV 100)",
            "AlisKDVOrani": 100,
            "SatisKDVOrani": 100,
            "TevkifatVergiAltID": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SablonID": null
        },
        {
            "StokVergiID": 4,
            "SubeID": 1,
            "SirketID": 1,
            "StokVergiKodu": "KDV19",
            "StokVergiAdi": "Stok(KDV 19)",
            "AlisKDVOrani": 19,
            "SatisKDVOrani": 19,
            "TevkifatVergiAltID": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SablonID": null
        },
        {
            "StokVergiID": 5,
            "SubeID": 1,
            "SirketID": 1,
            "StokVergiKodu": "KDV20",
            "StokVergiAdi": "Stok(KDV 20)",
            "AlisKDVOrani": 20,
            "SatisKDVOrani": 20,
            "TevkifatVergiAltID": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SablonID": null
        },
        {
            "StokVergiID": 6,
            "SubeID": 1,
            "SirketID": 1,
            "StokVergiKodu": "KDV21",
            "StokVergiAdi": "Stok(KDV 21)",
            "AlisKDVOrani": 21,
            "SatisKDVOrani": 21,
            "TevkifatVergiAltID": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SablonID": null
        },
        {
            "StokVergiID": 7,
            "SubeID": 1,
            "SirketID": 1,
            "StokVergiKodu": "KDV22",
            "StokVergiAdi": "Stok(KDV 22)",
            "AlisKDVOrani": 22,
            "SatisKDVOrani": 22,
            "TevkifatVergiAltID": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SablonID": null
        },
        {
            "StokVergiID": 8,
            "SubeID": 1,
            "SirketID": 1,
            "StokVergiKodu": "KDV23",
            "StokVergiAdi": "Stok(KDV 23)",
            "AlisKDVOrani": 23,
            "SatisKDVOrani": 23,
            "TevkifatVergiAltID": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SablonID": null
        },
        {
            "StokVergiID": 9,
            "SubeID": 1,
            "SirketID": 1,
            "StokVergiKodu": "KDV24",
            "StokVergiAdi": "Stok(KDV 24)",
            "AlisKDVOrani": 24,
            "SatisKDVOrani": 24,
            "TevkifatVergiAltID": null,
            "AlisVergi1ID": null,
            "AlisVergi1AltID": null,
            "AlisVergi1Oran": null,
            "AlisVergi2ID": null,
            "AlisVergi2AltID": null,
            "AlisVergi2Oran": null,
            "AlisVergi3ID": null,
            "AlisVergi3AltID": null,
            "AlisVergi3Oran": null,
            "SatisVergi1ID": null,
            "SatisVergi1AltID": null,
            "SatisVergi1Oran": null,
            "SatisVergi2ID": null,
            "SatisVergi2AltID": null,
            "SatisVergi2Oran": null,
            "SatisVergi3ID": null,
            "SatisVergi3AltID": null,
            "SatisVergi3Oran": null,
            "SablonID": null
        }
    ],
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Bütün vergi oranlarını ya da istenilen kısıttaki vergi kalemleri gelmektedir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/StokVergi?`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
SayfaSatirSayisi | Integer | Limitli sayıda vergi kalemi getirmek için kullanılmaktadır.
StokVergiID | Integer | Sadece belirli bir vergiyi getirmek için eklenmektedir.




## Yeni Vergi Oranı Oluştur


```shell


curl --location --request POST 'https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "StokVergiID": -1,
    "StokVergiKodu": 105576,
    "StokVergiAdi": "Mobilya Vergisi",
    "AlisKDVOrani": 8,
    "SatisKDVOrani": 8
}'

```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"StokVergiID":-1,"StokVergiKodu":105576,"StokVergiAdi":"Mobilya Vergisi","AlisKDVOrani":8,"SatisKDVOrani":8})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});




```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"StokVergiID\": -1,\n    \"StokVergiKodu\": 105576,\n    \"StokVergiAdi\": \"Mobilya Vergisi\",\n    \"AlisKDVOrani\": 8,\n    \"SatisKDVOrani\": 8\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=1"

payload = "{\n    \"StokVergiID\": -1,\n    \"StokVergiKodu\": 105576,\n    \"StokVergiAdi\": \"Mobilya Vergisi\",\n    \"AlisKDVOrani\": 8,\n    \"SatisKDVOrani\": 8\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"StokVergiID\": -1,\n    \"StokVergiKodu\": 105576,\n    \"StokVergiAdi\": \"Mobilya Vergisi\",\n    \"AlisKDVOrani\": 8,\n    \"SatisKDVOrani\": 8\n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "StokVergiID": 89,
        "SubeID": 0,
        "SirketID": 0,
        "StokVergiKodu": "105576",
        "StokVergiAdi": "Mobilya Vergisi",
        "AlisKDVOrani": 8,
        "SatisKDVOrani": 8,
        "TevkifatVergiAltID": null,
        "AlisVergi1ID": null,
        "AlisVergi1AltID": null,
        "AlisVergi1Oran": null,
        "AlisVergi2ID": null,
        "AlisVergi2AltID": null,
        "AlisVergi2Oran": null,
        "AlisVergi3ID": null,
        "AlisVergi3AltID": null,
        "AlisVergi3Oran": null,
        "SatisVergi1ID": null,
        "SatisVergi1AltID": null,
        "SatisVergi1Oran": null,
        "SatisVergi2ID": null,
        "SatisVergi2AltID": null,
        "SatisVergi2Oran": null,
        "SatisVergi3ID": null,
        "SatisVergi3AltID": null,
        "SatisVergi3Oran": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Yeni bir vergi oranı oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
StokVergiID | Integer | -1 ile rasgele atama yapılmaktadır.
StokVergiKodu | Integer | Vergi kodu unique olmalıdır.
StokVergiAdi | String | Vergi adı girilmelidir ( Örnek: Mobilya vergisi)
AlisKDVOrani | Integer | Bu senaryoda 8 girilmiştir. Yeni düzenlemede bir süreliğine mobilyadan %8 kdv alınmaktadır.
SatisKDVOrani | Integer | Bu senaryoda 8 girilmiştir. Yeni düzenlemede bir süreliğine mobilyadan %8 kdv alınmaktadır.





## Vergi Oranını Düzenle


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "StokVergiID": 89,
    "StokVergiKodu": 105576,
    "StokVergiAdi": "Teknoloji Vergisi ",
    "AlisKDVOrani": 18,
    "SatisKDVOrani": 18
}'

```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=2',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"StokVergiID":89,"StokVergiKodu":105576,"StokVergiAdi":"Teknoloji Vergisi ","AlisKDVOrani":18,"SatisKDVOrani":18})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});




```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"StokVergiID\": 89,\n    \"StokVergiKodu\": 105576,\n    \"StokVergiAdi\": \"Teknoloji Vergisi \",\n    \"AlisKDVOrani\": 18,\n    \"SatisKDVOrani\": 18\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=2"

payload = "{\n    \"StokVergiID\": 89,\n    \"StokVergiKodu\": 105576,\n    \"StokVergiAdi\": \"Teknoloji Vergisi \",\n    \"AlisKDVOrani\": 18,\n    \"SatisKDVOrani\": 18\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))



```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"StokVergiID\": 89,\n    \"StokVergiKodu\": 105576,\n    \"StokVergiAdi\": \"Teknoloji Vergisi \",\n    \"AlisKDVOrani\": 18,\n    \"SatisKDVOrani\": 18\n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "StokVergiID": 89,
        "SubeID": 0,
        "SirketID": 0,
        "StokVergiKodu": "105576",
        "StokVergiAdi": "Teknoloji Vergisi ",
        "AlisKDVOrani": 18,
        "SatisKDVOrani": 18,
        "TevkifatVergiAltID": null,
        "AlisVergi1ID": null,
        "AlisVergi1AltID": null,
        "AlisVergi1Oran": null,
        "AlisVergi2ID": null,
        "AlisVergi2AltID": null,
        "AlisVergi2Oran": null,
        "AlisVergi3ID": null,
        "AlisVergi3AltID": null,
        "AlisVergi3Oran": null,
        "SatisVergi1ID": null,
        "SatisVergi1AltID": null,
        "SatisVergi1Oran": null,
        "SatisVergi2ID": null,
        "SatisVergi2AltID": null,
        "SatisVergi2Oran": null,
        "SatisVergi3ID": null,
        "SatisVergi3AltID": null,
        "SatisVergi3Oran": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Vergi oranı düzenlenmektedir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=2`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 2 KayitTipi=2 bütün API'de PUT anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
StokVergiID | Integer | Düzenlenmek istenen vergi ID'si.
StokVergiKodu | Integer | Vergi kodu unique olmalıdır.
StokVergiAdi | String | Vergi adı.
AlisKDVOrani | Integer | Bu senaryoda 18 girilmiştir. %8 oran %18 olarak değiştirilmiştir.
SatisKDVOrani | Integer | Bu senaryoda 18 girilmiştir. %8 oran %18 olarak değiştirilmiştir.

## Vergi Oranını Sil


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "StokVergiID": 89
  
}'
```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=-1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"StokVergiID":89})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});





```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"StokVergiID\": 89\n  \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=-1"

payload = "{\n    \"StokVergiID\": 89\n  \n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))




```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"StokVergiID\": 89\n  \n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "StokVergiID": 89,
        "SubeID": 0,
        "SirketID": 0,
        "StokVergiKodu": "105576",
        "StokVergiAdi": "Teknoloji Vergisi ",
        "AlisKDVOrani": 18,
        "SatisKDVOrani": 18,
        "TevkifatVergiAltID": null,
        "AlisVergi1ID": null,
        "AlisVergi1AltID": null,
        "AlisVergi1Oran": null,
        "AlisVergi2ID": null,
        "AlisVergi2AltID": null,
        "AlisVergi2Oran": null,
        "AlisVergi3ID": null,
        "AlisVergi3AltID": null,
        "AlisVergi3Oran": null,
        "SatisVergi1ID": null,
        "SatisVergi1AltID": null,
        "SatisVergi1Oran": null,
        "SatisVergi2ID": null,
        "SatisVergi2AltID": null,
        "SatisVergi2Oran": null,
        "SatisVergi3ID": null,
        "SatisVergi3AltID": null,
        "SatisVergi3Oran": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Vergi oranını silmektedir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=-1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de DELETE anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
StokVergiID | Integer | Silinmek istenen vergi ID'si.






## Vergi Dairelerini Getir


```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/VergiDairesi' \
--header 'Authorization: Bearer YOURTOKEN' 


```

```javascript

var request = require('request');
var options = {
  'method': 'GET',
    'url': 'https://erp.aaro.com.tr/api/VergiDairesi?',
  'headers': {
    'Authorization': 'Bearer YOURTOKEN'
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});




```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/VergiDairesi?");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/VergiDairesi?"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/VergiDairesi")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "SayfalandirmaBilgisi": {
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 1037,
        "ToplamSayfaSayisi": 104,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": true,
        "SayfaSatirSayisiAktifSayfada": 10
    },
    "Model": [
        {
            "VDID": 435,
            "VDKodu": "55110",
            "VDAdi": "19 Mayıs ",
            "VM": "M",
            "IlID": 55
        },
        {
            "VDID": 970,
            "VDKodu": "55251",
            "VDAdi": "19 MAYIS ",
            "VM": "V",
            "IlID": 55
        },
        {
            "VDID": 735,
            "VDKodu": "26253",
            "VDAdi": "2 EYLÜL",
            "VM": "V",
            "IlID": 26
        },
        {
            "VDID": 749,
            "VDKodu": "31201",
            "VDAdi": "23 TEMMUZ ",
            "VM": "V",
            "IlID": 31
        },
        {
            "VDID": 911,
            "VDKodu": "43201",
            "VDAdi": "30 AĞUSTOS ",
            "VM": "V",
            "IlID": 43
        },
        {
            "VDID": 856,
            "VDKodu": "35251",
            "VDAdi": "9 EYLÜL ",
            "VM": "V",
            "IlID": 35
        },
        {
            "VDID": 292,
            "VDKodu": "37112",
            "VDAdi": "Abana ",
            "VM": "M",
            "IlID": 37
        },
        {
            "VDID": 395,
            "VDKodu": "50107",
            "VDAdi": "Acıgöl ",
            "VM": "M",
            "IlID": 50
        },
        {
            "VDID": 712,
            "VDKodu": "20261",
            "VDAdi": "ACIPAYAM ",
            "VM": "V",
            "IlID": 20
        },
        {
            "VDID": 898,
            "VDKodu": "41290",
            "VDAdi": "ACISU  ",
            "VM": "V",
            "IlID": 41
        }
    ],
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Bütün vergi dairelerini ya da istenilen kısıttaki vergi dairelerini getirmektedir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/VergiDairesi?`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
SayfaSatirSayisi | Integer | Limitli sayıda vergi kalemi getirmek için kullanılmaktadır.
Sayfa | Integer | Birden fazla sayfada sonuç geldiğinde, belirli bir sayfaya gitmek için kullanılır.
VDID | Integer | Sadece belirli bir vergi dairesini getirmek için eklenmektedir.
VDKodu  | String |Sadece belirli bir koda sahip vergi dairesini getirmek için eklenmektedir.
VDAdi  | String | Vergi dairesi adına göre sorgulamak için mevcuttur.
VM | String | ***
IlID | Integer | İl koduna göre sonuç dönmektedir.  
## Vergi Dairesi Oluştur


```shell


curl --location --request POST 'https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "VDKodu": "454360",
    "VDAdi" : "Yahya Galip Vergi Dairesi",
       "IlID": 6
}'

```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"VDKodu":"454360","VDAdi":"Yahya Galip Vergi Dairesi","IlID":6})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});




```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"VDKodu\": \"454360\",\n    \"VDAdi\" : \"Yahya Galip Vergi Dairesi\",\n       \"IlID\": 6\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=1"

payload = "{\n    \"VDKodu\": \"454360\",\n    \"VDAdi\" : \"Yahya Galip Vergi Dairesi\",\n       \"IlID\": 6\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"VDKodu\": \"454360\",\n    \"VDAdi\" : \"Yahya Galip Vergi Dairesi\",\n       \"IlID\": 6\n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "VDID": 1042,
        "VDKodu": "454360",
        "VDAdi": "Yahya Galip Vergi Dairesi",
        "VM": null,
        "IlID": 6
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Yeni bir vergi dairesi oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım | Zorunlu Mu?
--------- | ----------- | ---------
VDID | Integer | -1 ile rasgele atama yapılmaktadır. | Opsiyonel
VDKodu | Integer | Vergi dairesi kodu unique olmalıdır. | Evet
VDAdi | String | Vergi dairesi adı girilmelidir | Evet
IlID | Integer | Vergi dairesinin bulunduğu il girilmelidir. | Evet
VM | String | *** | Opsiyonel





## Vergi Dairesi Düzenle


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "VDID": 1042,
    "VDAdi": "Murat Akan Vergi Dairesi"
}'

```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=2',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"VDID":1042,"VDAdi":"Murat Akan Vergi Dairesi"})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});




```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"VDID\": 1042,\n    \"VDAdi\": \"Murat Akan Vergi Dairesi\"\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=2"


payload = "{\n    \"VDID\": 1042,\n    \"VDAdi\": \"Murat Akan Vergi Dairesi\"\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))



```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"VDID\": 1042,\n    \"VDAdi\": \"Murat Akan Vergi Dairesi\"\n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "VDID": 1042,
        "VDKodu": "454360",
        "VDAdi": "Murat Akan Vergi Dairesi",
        "VM": null,
        "IlID": 6
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Vergi dairesi düzenlenmektedir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=2`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 2 KayitTipi=2 bütün API'de PUT anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım | Zorunlu Mu?
--------- | ----------- | ---------
VDID | Integer | Düzenlenmek istenen Vergi Dairesi ID'si | Evet
VDKodu | Integer | Vergi dairesi kodu unique olmalıdır. | Opsiyonel
VDAdi | String | Vergi dairesi adı girilmelidir | Opsiyonel
IlID | Integer | Vergi dairesinin bulunduğu il girilmelidir. | Opsiyonel
VM | String | *** | Opsiyonel


## Vergi Dairesini Sil


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "VDID": 1042
}'

```

```javascript

var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=-1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
    body: JSON.stringify({"VDID":1042})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});




```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"VDID\": 1042\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=-1"

payload = "{\n    \"VDID\": 1042\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))



```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"VDID\": 1042\n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "VDID": 1042,
        "VDKodu": "454360",
        "VDAdi": "Murat Akan Vergi Dairesi",
        "VM": null,
        "IlID": 6
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Vergi dairesi silinmektedir..

### HTTP Request

`POST https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=-1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de DELETE anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım | Zorunlu Mu?
--------- | ----------- | ---------
VDID | Integer | Silinmek istenen Vergi Dairesi ID'si | Evet


<aside class="warning">
Bu işlemin geri dönüşü yoktur. Silmeden önce bu vergi dairesinin hareketlerini silmelisiniz.
</aside>


# Fiyat Listeleri 

## Fiyat Listelerini Getir


```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/FiyatListesi' \
--header 'Authorization: Bearer YOURTOKEN' 

```

```javascript

var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://erp.aaro.com.tr/api/FiyatListesi',
  'headers': {
    'Authorization': 'Bearer YOURTOKEN'
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});




```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/FiyatListesi?");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesi?"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/FiyatListesi")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json

{
    "SayfalandirmaBilgisi": {
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 8,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 8
    },
    "Model": [
        {
            "FiyatListesiID": 6,
            "SubeID": 1,
            "SirketID": 1,
            "Kodu": "FLAktarim11",
            "Adi": "2020-FiyatListesi",
            "TipID": 136001,
            "TarihBas": "2020-07-03T00:00:00",
            "TarihBit": "2025-07-03T00:00:00",
            "Vade": 0,
            "Durum": true,
            "OnayDurum": 1,
            "OlsID": 4,
            "OlsTar": "2020-07-03T14:53:47.5",
            "DgsID": 4,
            "DgsTar": "2020-07-03T14:53:47.5"
        },
        {
            "FiyatListesiID": 2,
            "SubeID": 1,
            "SirketID": 1,
            "Kodu": "KOPYA0000000001",
            "Adi": "abc fiyat listesi",
            "TipID": 136001,
            "TarihBas": "2020-05-22T00:00:00",
            "TarihBit": "2020-12-31T00:00:00",
            "Vade": 0,
            "Durum": true,
            "OnayDurum": 1,
            "OlsID": 3,
            "OlsTar": "2020-05-22T12:00:35.267",
            "DgsID": 4,
            "DgsTar": "2020-07-01T21:30:46.547"
        },
        {
            "FiyatListesiID": 1,
            "SubeID": 1,
            "SirketID": 1,
            "Kodu": "1",
            "Adi": "abc fiyat listesi",
            "TipID": 136002,
            "TarihBas": "2020-05-22T00:00:00",
            "TarihBit": "2020-12-31T00:00:00",
            "Vade": 0,
            "Durum": true,
            "OnayDurum": 1,
            "OlsID": 3,
            "OlsTar": "2020-05-22T11:35:57.967",
            "DgsID": 3,
            "DgsTar": "2020-05-22T11:37:24.58"
        },
        {
            "FiyatListesiID": 9,
            "SubeID": 0,
            "SirketID": 0,
            "Kodu": "0123-S",
            "Adi": "Api Fiyat Listesi",
            "TipID": 136001,
            "TarihBas": "2020-07-03T14:53:47.5",
            "TarihBit": "2020-07-03T14:53:47.5",
            "Vade": 0,
            "Durum": true,
            "OnayDurum": 1,
            "OlsID": 4,
            "OlsTar": "2020-07-07T12:28:49.703",
            "DgsID": 4,
            "DgsTar": "2020-07-07T12:30:45.51"
        },
        {
            "FiyatListesiID": 10,
            "SubeID": 0,
            "SirketID": 0,
            "Kodu": "0123-Ss",
            "Adi": "Api Fiyat Listesii",
            "TipID": 136001,
            "TarihBas": "2020-07-03T00:00:00",
            "TarihBit": "2020-07-03T00:00:00",
            "Vade": 0,
            "Durum": true,
            "OnayDurum": 1,
            "OlsID": 4,
            "OlsTar": "2020-07-07T12:37:55.433",
            "DgsID": 4,
            "DgsTar": "2020-07-07T12:37:55.433"
        },
        {
            "FiyatListesiID": 3,
            "SubeID": 1,
            "SirketID": 1,
            "Kodu": "kfl",
            "Adi": "kereste fiyat listesi",
            "TipID": 136001,
            "TarihBas": "2020-07-02T00:00:00",
            "TarihBit": "2020-12-31T00:00:00",
            "Vade": 0,
            "Durum": true,
            "OnayDurum": 1,
            "OlsID": 4,
            "OlsTar": "2020-07-02T12:45:04.077",
            "DgsID": 4,
            "DgsTar": "2020-07-02T12:45:43.253"
        },
        {
            "FiyatListesiID": 4,
            "SubeID": 1,
            "SirketID": 1,
            "Kodu": "kesme-tahtalari",
            "Adi": "Kesme  Tahtaları",
            "TipID": 136001,
            "TarihBas": "2020-07-03T00:00:00",
            "TarihBit": "2020-12-31T00:00:00",
            "Vade": 0,
            "Durum": true,
            "OnayDurum": 1,
            "OlsID": 4,
            "OlsTar": "2020-07-03T08:08:35.007",
            "DgsID": 4,
            "DgsTar": "2020-07-03T08:10:45.22"
        },
        {
            "FiyatListesiID": 5,
            "SubeID": 1,
            "SirketID": 1,
            "Kodu": "kesmetahta-alis",
            "Adi": "Kesme Tahtası Alış",
            "TipID": 136002,
            "TarihBas": "2020-07-03T00:00:00",
            "TarihBit": "2020-12-31T00:00:00",
            "Vade": 0,
            "Durum": true,
            "OnayDurum": 1,
            "OlsID": 4,
            "OlsTar": "2020-07-03T08:12:55.167",
            "DgsID": 4,
            "DgsTar": "2020-07-03T08:12:55.167"
        }
    ],
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}

```

Bütün fiyat listelerini ya da istenilen kısıttaki fiyat listelerini getirmektedir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/FiyatListesi?`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
EsnekAramaKisiti | String | Dilediğiniz stringe göre listeleme yapabilirsiniz. Fiyat listerinin kodunda, Fiyat listerinin adında, etiket adlarında, kod adlarında girilen string'e göre arama yapar.
SayfaSatirSayisi | Integer | Limitli sayıda fiyat listesi getirmek için kullanılmaktadır.
FiyatListesiID | Integer | Sadece belirli bir fiyat listesini getirmek için eklenmektedir.
TipID | Integer | Fiyat listelerinin tipine göre çağırım için mevcuttur. (alım fiyat listesi, satış fiyat listesi gibi)
OlsID | Integer | Oluşturan kişi ID'si
DgsID | Integer | Değiştiren kişi ID'si
Durum | Boolean | Aktif veya Pasif listeler için mevcuttur. 
TarihBas | String | Listelerin geçerli olduğu tarih başlangıcı
TarihBit | String | Listelerin geçerli olduğu son tarih
Vade | Integer | Listelerin vadesi
OnayDurum| Integer | Listenin onayı var mı?
SirketID | Integer | Belirli bir şirkete ait fiyat listeleri için girilmektedir.
SubeID | Integer | Belirli bir şubenin listelerini getirmek için kullanılmaktadır.

<aside class="info">
Genelde şirket ve şube belirtilerek fiyat listeleri getirilir. Örnek: https://erp.aaro.com.tr/api/FiyatListesi?SubeID=1&SirketID=1 
</aside>

## Fiyat Listesi Oluştur


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{

    "Kodu": "0123-Ss",
    "Adi": "Api Fiyat Listesii",
    "TarihBas": "2020-07-03",
    "TarihBit": "2020-07-03",
    "TipID": 136001,
    "Durum": true
    
}'

```

```javascript


var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"Kodu":"0123-Ss","Adi":"Api Fiyat Listesii","TarihBas":"2020-07-03","TarihBit":"2020-07-03","TipID":136001,"Durum":true})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n\n    \"Kodu\": \"0123-Ss\",\n    \"Adi\": \"Api Fiyat Listesii\",\n    \"TarihBas\": \"2020-07-03\",\n    \"TarihBit\": \"2020-07-03\",\n    \"TipID\": 136001,\n    \"Durum\": true\n    \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1"

payload = "{\n\n    \"Kodu\": \"0123-Ss\",\n    \"Adi\": \"Api Fiyat Listesii\",\n    \"TarihBas\": \"2020-07-03\",\n    \"TarihBit\": \"2020-07-03\",\n    \"TipID\": 136001,\n    \"Durum\": true\n    \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n\n    \"Kodu\": \"0123-Ss\",\n    \"Adi\": \"Api Fiyat Listesii\",\n    \"TarihBas\": \"2020-07-03\",\n    \"TarihBit\": \"2020-07-03\",\n    \"TipID\": 136001,\n    \"Durum\": true\n    \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "FiyatListesiID": 10,
        "SubeID": 0,
        "SirketID": 0,
        "Kodu": "0123-Ss",
        "Adi": "Api Fiyat Listesii",
        "TipID": 136001,
        "TarihBas": "2020-07-03T00:00:00",
        "TarihBit": "2020-07-03T00:00:00",
        "Vade": 0,
        "Durum": true,
        "OnayDurum": 1,
        "OlsID": 4,
        "OlsTar": "2020-07-07T12:37:55.4333781+03:00",
        "DgsID": 4,
        "DgsTar": "2020-07-07T12:37:55.4333781+03:00"
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Yeni bir fiyat listesi oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
Kodu | String | Fiyat listesine vereceğiniz kod
Adi | String | Fiyat listesine vereceğiniz ad
TarihBas | String | Listelerin geçerli olduğu tarih başlangıcı
TarihBit | String | Listelerin geçerli olduğu son tarih
TipID | Integer | TipID tablosundan bakınız
Durum | Boolean | Aktif ya da pasif olması için önemlidir




## Fiyat Listesini Düzenle


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "FiyatListesiID":9,
    "Kodu": "0123-S",
    "Adi": "Honda Fiyat Listesi",
        "TarihBas": "2020-07-03T14:53:47.5",
        "TarihBit": "2020-07-03T14:53:47.5",
            "TipID": 136001,
            "Durum": true
    
}'

```

```javascript


var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=2',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"FiyatListesiID":9,"Kodu":"0123-S","Adi":"Honda Fiyat Listesi","TarihBas":"2020-07-03T14:53:47.5","TarihBit":"2020-07-03T14:53:47.5","TipID":136001,"Durum":true})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"FiyatListesiID\":9,\n    \"Kodu\": \"0123-S\",\n    \"Adi\": \"Honda Fiyat Listesi\",\n        \"TarihBas\": \"2020-07-03T14:53:47.5\",\n        \"TarihBit\": \"2020-07-03T14:53:47.5\",\n            \"TipID\": 136001,\n            \"Durum\": true\n    \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1"

payload = "{\n    \"FiyatListesiID\":9,\n    \"Kodu\": \"0123-S\",\n    \"Adi\": \"Honda Fiyat Listesi\",\n        \"TarihBas\": \"2020-07-03T14:53:47.5\",\n        \"TarihBit\": \"2020-07-03T14:53:47.5\",\n            \"TipID\": 136001,\n            \"Durum\": true\n    \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"FiyatListesiID\":9,\n    \"Kodu\": \"0123-S\",\n    \"Adi\": \"Honda Fiyat Listesi\",\n        \"TarihBas\": \"2020-07-03T14:53:47.5\",\n        \"TarihBit\": \"2020-07-03T14:53:47.5\",\n            \"TipID\": 136001,\n            \"Durum\": true\n    \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "FiyatListesiID": 9,
        "SubeID": 0,
        "SirketID": 0,
        "Kodu": "0123-S",
        "Adi": "Honda Fiyat Listesi",
        "TipID": 136001,
        "TarihBas": "2020-07-03T14:53:47.5",
        "TarihBit": "2020-07-03T14:53:47.5",
        "Vade": 0,
        "Durum": true,
        "OnayDurum": 1,
        "OlsID": 4,
        "OlsTar": "2020-07-07T13:18:34.5553512+03:00",
        "DgsID": 4,
        "DgsTar": "2020-07-07T13:18:34.5553512+03:00"
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Yeni bir fiyat listesi oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=2`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
FiyatListesiID | Integer | Fiyat listesinin ID'si
Kodu | String | Fiyat listesine vereceğiniz kod
Adi | String | Fiyat listesine vereceğiniz ad
TarihBas | String | Listelerin geçerli olduğu tarih başlangıcı
TarihBit | String | Listelerin geçerli olduğu son tarih
TipID | Integer | TipID tablosundan bakınız
Durum | Boolean | Aktif ya da pasif olması için önemlidir



## Fiyat Listesini Sil


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "FiyatListesiID":9,
  
    
}'

```

```javascript


var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"FiyatListesiID":9})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"FiyatListesiID\":9,\n       \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1"

payload = "{\n    \"FiyatListesiID\":9,\n     \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"FiyatListesiID\":9,\n      \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "FiyatListesiID": 0,
        "SubeID": 0,
        "SirketID": 0,
        "Kodu": null,
        "Adi": null,
        "TipID": 0,
        "TarihBas": "0001-01-01T00:00:00",
        "TarihBit": "0001-01-01T00:00:00",
        "Vade": 0,
        "Durum": false,
        "OnayDurum": 0,
        "OlsID": 0,
        "OlsTar": "0001-01-01T00:00:00",
        "DgsID": 0,
        "DgsTar": "0001-01-01T00:00:00"
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Mevcut fiyat listesini silmektedir

### HTTP Request

`POST https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de yeni DELETE(sil) anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
FiyatListesiID | Integer | Silmek istediğiniz fiyat listesi ID'si


<aside class="warning">
Bu işlemin geri dönüşü yoktur. Silmeden önce bu fiyat listesine bağlı tüm stokların ve hareketlerin liste ile ilişkisini kesmelisiniz.
</aside>

# Müşteri(Cari) / Tedarikçi

## Carileri Getir


```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/Cari' \
--header 'Authorization: Bearer YOURTOKEN' 

```

```javascript

var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://erp.aaro.com.tr/api/Cari?',
  'headers': {
    'Authorization': 'Bearer YOURTOKEN'
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});




```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Cari?");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari?"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/Cari")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json

{
    "SayfalandirmaBilgisi": {
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
            "CariID": 5,
            "CariKodu": "000000000000001",
            "CariAdi": "AARO YAZILIM VE MAKİNA A.Ş",
            "Durum": true,
            "VergiNo": "0011030472",
            "DovizCalisabilir": false,
            "MuhtelifMi": false,
            "Vade": 0,
            "Iskonto": 0,
            "OnayDurum": 1,
            "OlsTar": "2020-05-13T13:34:51.677",
            "DgsTar": "2020-05-13T13:50:56.56",
            "TipID": 102001,
            "TipAdi": "Musteri",
            "SubeID": 1,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketID": 1,
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "MuhasebeBorcID": 11,
            "MuhasebeBorcKodu": "120",
            "MuhasebeBorcAdi": "Alıcılar",
            "MuhasebeAlacakID": 11,
            "MuhasebeAlacakKodu": "120",
            "MuhasebeAlacakAdi": "Alıcılar",
            "VergiDairesiID": 633,
            "VergiDairesiKodu": "06270",
            "VergiDairesiAdi": "M.KARAGÜZEL ",
            "FiyatListesiCariGrupID": null,
            "FiyatListesiCariGrupKodu": null,
            "FiyatListesiCariGrupAdi": null,
            "Kod1ID": null,
            "Kod1Kodu": null,
            "Kod1Adi": null,
            "OlsID": 3,
            "OlsKodu": "EY",
            "OlsAdi": "Emine Yiğit",
            "DgsID": 3,
            "DgsKodu": "EY",
            "DgsAdi": "Emine Yiğit",
            "Etiket1ID": null,
            "Etiket1Adi": null,
            "SablonID": null,
            "SablonKodu": null,
            "SablonAdi": null,
            "Bakiye": -2678.520000,
            "BakiyeDvz2": null,
            "BakiyeDvz3": null
        },  {
            "CariID": 13,
            "CariKodu": "000000000000006",
            "CariAdi": "KALE İNŞAAT LTD.ŞTİ.",
            "Durum": true,
            "VergiNo": "0011452365",
            "DovizCalisabilir": false,
            "MuhtelifMi": false,
            "Vade": 95,
            "Iskonto": 0,
            "OnayDurum": 1,
            "OlsTar": "2020-05-18T23:14:35.383",
            "DgsTar": "2020-05-18T23:14:35.383",
            "TipID": 102001,
            "TipAdi": "Musteri",
            "SubeID": 1,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketID": 1,
            "SirketKodu": "SRKT",
            "SirketAdi": "Şirketim",
            "MuhasebeBorcID": 11,
            "MuhasebeBorcKodu": "120",
            "MuhasebeBorcAdi": "Alıcılar",
            "MuhasebeAlacakID": 11,
            "MuhasebeAlacakKodu": "120",
            "MuhasebeAlacakAdi": "Alıcılar",
            "VergiDairesiID": 633,
            "VergiDairesiKodu": "06270",
            "VergiDairesiAdi": "M.KARAGÜZEL ",
            "FiyatListesiCariGrupID": null,
            "FiyatListesiCariGrupKodu": null,
            "FiyatListesiCariGrupAdi": null,
            "Kod1ID": null,
            "Kod1Kodu": null,
            "Kod1Adi": null,
            "OlsID": 3,
            "OlsKodu": "EY",
            "OlsAdi": "Emine Yiğit",
            "DgsID": 3,
            "DgsKodu": "EY",
            "DgsAdi": "Emine Yiğit",
            "Etiket1ID": null,
            "Etiket1Adi": null,
            "SablonID": null,
            "SablonKodu": null,
            "SablonAdi": null,
            "Bakiye": 5000.010000,
            "BakiyeDvz2": null,
            "BakiyeDvz3": null
        }
    ],
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}

```

Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Cari?`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
EsnekAramaKisiti | String | Dilediğiniz stringe göre listeleme yapabilirsiniz. Cari kodunda, cari adında, etiket adlarında, kod adlarında girilen string'e göre arama yapar.SayfaSatirSayisi | Integer | Limitli sayıda cari getirmek için kullanılmaktadır.
CariID | Integer | Sadece belirli bir cariyi getirmek için eklenmektedir.
CariKodu | String | Cari koduna göre cari veya carileri döndürmektedir.
CariAdi | String | Carinin kayıtlı adına göre getirmektedir.
VergiDairesiID | Integer | Belirli bir vergi dairesi ID'sine bağlı carileri getirmektedir.
VergiDairesiKodu | String | Belirli bir vergi dairesi koduna bağlı carileri getirmektedir.
VergiDairesiAdi | String | Belirli bir vergi dairesi adına bağlı carileri getirmektedir.
VergiNo | String | Vergi numarasına göre kayıt dönülmektedir.
TipAdi | Integer | Carinin tipine göre çağırım için mevcuttur. (Musteri, bayi gibi)
TipID | Integer | Carinin tipine göre çağırım için mevcuttur. (Tip ID listesinden bakınız)
OlsID | Integer | Oluşturan kişi ID'si
DgsID | Integer | Değiştiren kişi ID'si
Durum | Boolean | Aktif veya Pasif listeler için mevcuttur. 
OnayDurum| Integer | Carinin onayı var mı?
SirketID | Integer | Belirli bir şirkete ait cari/cariler için girilmektedir.
SubeID | Integer | Belirli bir şubeye ait cari/cariler için kullanılmaktadır.

<aside class="info">
Genelde şirket ve şube belirtilerek fiyat listeleri getirilir. Örnek: https://erp.aaro.com.tr/api/FiyatListesi?SubeID=1&SirketID=1 
</aside> 

## Cari Oluştur



```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "CariKodu": "000123S",
    "CariAdi": "Aaro Yazilim",
    "VergiNo": "14110155",
    "TipID": 102001,
    "Durum": true,
    "MuhasebeAlacakID":11,
    "MuhasebeBorcID":11,
    "VergiDairesiID":633
}'

```

```javascript


var request = require('request');
var options = {
  'method': 'POST',
 'url': 'https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
    body: JSON.stringify({"CariKodu":"000123S","CariAdi":"Aaro Yazilim","VergiNo":"14110155","TipID":102001,"Durum":true,"MuhasebeAlacakID":11,"MuhasebeBorcID":11,"VergiDairesiID":633})

};

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"CariKodu\": \"000123S\",\n    \"CariAdi\": \"Aaro Yazilim\",\n    \"VergiNo\": \"14110155\",\n    \"TipID\": 102001,\n    \"Durum\": true,\n   \"MuhasebeAlacakID\":11,\n    \"MuhasebeBorcID\":11,\n    \"VergiDairesiID\":633\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1"

payload = "{\n    \"CariKodu\": \"000123S\",\n    \"CariAdi\": \"Aaro Yazilim\",\n    \"VergiNo\": \"14110155\",\n    \"TipID\": 102001,\n    \"Durum\": true,\n    \"MuhasebeAlacakID\":11,\n    \"MuhasebeBorcID\":11,\n    \"VergiDairesiID\":633\n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
.body("{\n    \"CariKodu\": \"000123S\",\n    \"CariAdi\": \"Aaro Yazilim\",\n    \"VergiNo\": \"14110155\",\n    \"TipID\": 102001,\n    \"Durum\": true,\n    \"MuhasebeAlacakID\":11,\n    \"MuhasebeBorcID\":11,\n    \"VergiDairesiID\":633\n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "CariID": 20,
        "SubeID": 0,
        "SirketID": 0,
        "CariKodu": "000123S",
        "CariAdi": "Aaro Yazilim",
        "Durum": true,
        "TipID": 102001,
        "VergiDairesiID": 633,
        "VergiNo": "14110155",
        "MuhasebeBorcID": 11,
        "MuhasebeAlacakID": 11,
        "DovizCalisabilir": false,
        "MuhtelifMi": false,
        "Kod1ID": null,
        "Vade": 0,
        "Iskonto": 0,
        "FiyatListesiCariGrupID": null,
        "Etiket1ID": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Yeni bir cari oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım | Zorunlu Mu?
--------- | ----------- | --------- | -----------
CariKodu | String | Cariye vereceğiniz kod | Evet
CariAdi | String | Cariye vereceğiniz ad | Evet
VergiNo | String | Cariniin kayıtlı olduğu vergi numarası | Evet
TipID | Integer | TipID tablosundan bakınız | Evet
MuhasebeAlacakID | Integer | Muhasebe Tablosundan Bakınız | Evet
MuhasebeBorcID  | Integer | Muhasebe Tablosundan Bakınız | Evet
VergiDairesiID | Integer | Oluşturduğunuz vergi dairesi ID'sidir | Evet
Durum | Boolean | Aktif ya da pasif olması için önemlidir | Opsiyonel
Iskonto | Integer | Müşteriye ait iskonto oranı | Opsiyonel
CariID | Integer | Müşterinin ID'si | Opsiyonel
SirketID | Integer | Bağlı olduğu şirket ID'si | Opsiyonel
SubeID | Integer | Bağlı olduğu şube ID'si | Opsiyonel

<aside class="success">
Mevcut vergi dairelerini görmek için API dökümanından Vergi Dairesi kısmını inceleyiniz.
</aside>


## Cari Düzenle


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "CariID": 20,
    "Iskonto": 4    
}'

```

```javascript


var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
    body: JSON.stringify({"CariID":20,"Iskonto":4})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"CariID\": 20,\n    \"Iskonto\": 4\n}\n\n",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2"

payload = "{\n    \"CariID\": 20,\n    \"Iskonto\": 4\n}\n\n"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"CariID\": 20,\n    \"Iskonto\": 4\n}\n\n")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "CariID": 20,
        "SubeID": 0,
        "SirketID": 0,
        "CariKodu": "000123S",
        "CariAdi": "Aaro Yazilim Ltd. Şti",
        "Durum": false,
        "TipID": 102001,
        "VergiDairesiID": 633,
        "VergiNo": "14110155",
        "MuhasebeBorcID": 11,
        "MuhasebeAlacakID": 11,
        "DovizCalisabilir": false,
        "MuhtelifMi": false,
        "Kod1ID": null,
        "Vade": 0,
        "Iskonto": 4,
        "FiyatListesiCariGrupID": null,
        "Etiket1ID": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Mevcut cari düzenlenmektedir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
CariID | Integer | Cari ID'si girilmesi zorunludur.



## Cari Sil


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "CariID":20,
  
    
}'

```

```javascript


var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
  body: JSON.stringify({"CariID":20})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"CariID\":20,\n       \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1"

payload = "{\n    \"CariID\":20,\n     \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"CariID\":20,\n      \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "CariID": 0,
        "SubeID": 0,
        "SirketID": 0,
        "CariKodu": null,
        "CariAdi": null,
        "Durum": false,
        "TipID": 0,
        "VergiDairesiID": 0,
        "VergiNo": null,
        "MuhasebeBorcID": 0,
        "MuhasebeAlacakID": 0,
        "DovizCalisabilir": false,
        "MuhtelifMi": false,
        "Kod1ID": null,
        "Vade": 0,
        "Iskonto": 0,
        "FiyatListesiCariGrupID": null,
        "Etiket1ID": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Mevcut cariyi silmektedir

### HTTP Request

`POST https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de yeni DELETE(sil) anlamına gelmektedir.


### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
CariID | Integer | Silmek istediğiniz cari ID'si


<aside class="warning">
Bu işlemin geri dönüşü yoktur. Silmeden önce bu carinin hareketler ve bankalarla ile ilişkisini kesmelisiniz.
</aside>



# Kasa

## Kasaları Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Kasa' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://erp.aaro.com.tr/api/Kasa',
  headers: {
    'Authorization': 'Bearer YOURTOKEN'
  }
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Kasa");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Kasa"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/Kasa")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 4,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 4
    },
    "Model": [
        {
            "Bakiye": 0.000000,
            "BakiyeDvz": null,
            "DevirTutar": null,
            "DevirTutarDvz": null,
            "DovizKodu": "EUR",
            "SubeKodu": "TUM",
            "SubeAdi": "Tüm Şubeler",
            "SirketKodu": "SRKT0",
            "SirketAdi": "Şirket 0",
            "EntegrasyonTanimKodu": "100.10.002",
            "EntegrasyonTanimAdi": "EURO KASASI",
            "TipAdi": "Kasa",
            "TipKodu": null,
            "OnayDurum": 1,
            "OlsTar": "2020-09-30T10:34:13.08",
            "DgsTar": "2020-10-02T16:46:14.613",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "",
            "DgsID": 2,
            "DgsKodu": "yonetici",
            "DgsAdi": "yonetici",
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
            "EsnekAramaKisiti": "100.10.002 EURO KASASI           ",
            "KasaID": 2,
            "KasaKodu": "100.10.002",
            "KasaAdi": "EURO KASASI",
            "DovizID": 3,
            "Seviye": 0,
            "SubeID": 0,
            "SirketID": 0,
            "Durum": true,
            "TipID": 103001,
            "EntegrasyonTanimID": 2925,
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
        },
        {
          ...
        },
         {
          ...
        },
    ],
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Bu uç nokta ile kasalarınızı toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.



### HTTP Request

`GET https://erp.aaro.com.tr/api/Kasa?`

### URL Parametreleri

Parameter | Değer | Tanım
--------- | ----------- | ---------
EsnekAramaKisiti | String | Dilediğiniz stringe göre listeleme yapabilirsiniz. Kasa kodunda, kasa adında, etiket adlarında, kod adlarında girilen string'e göre arama yapar.
SiralamaKisiti | String | Gelen veriyi sıralamak için kullanılır. Durum, KasaID gibi kolon adları verilmelidir.
Sayfa | Integer | Kaç sayfa kasa getirmek istediğinizi belirtir.
SayfaSatirSayisi |Integer | Getirilen sayfadaki kasa limitini belirtir.
KasaID | Integer | Belirtilen ID ile kasa getirmektedir.
Durum | Boolean | True ise aktif, false ise pasif ürünleri getirmektedir.
TipID |Integer | Kasanın tipine göre çağırım için mevcuttur. (Tip ID listesinden bakınız)
SubeID | Integer | Şube ID'sine göre ürünleri getirmektedir.
SirketID | Integer | Şirket ID'sine göre ürünleri getirmektedir.
StokMuhasebeID | Integer | Stok Muhasebe ID'sine göre ürünleri getirmektedir.
StokVergiID | Integer | Stok Vergi ID'sine göre ürünleri getirmektedir.
OlsID | Integer | Stoğu Oluşturan kişi ID'sine göre ürünleri getirmektedir.




## Kasa Ekle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Kasa/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"KasaID": -1,
        "SubeID": 1,
        "SirketID": 1,
        "KasaKodu": "00000000000002",
        "KasaAdi": "TL Kasa",
        "KasaKisaKodu": "00000000000002",
        "KasaKisaAdi": "TL Kasa",
        "Durum": true,
        "TipID": 103001,
        "KasaMuhasebeID": 201,
        "DovizID": 1,
        "Seviye": 1,
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null
}'

```

```javascript

var axios = require('axios');
var data = JSON.stringify({"KasaID":-1,"SubeID":1,"SirketID":1,"KasaKodu":"00000000000002","KasaAdi":"TL Kasa","KasaKisaKodu":"00000000000002","KasaKisaAdi":"TL Kasa","Durum":true,"TipID":103001,"KasaMuhasebeID":201,"DovizID":1,"Seviye":1,"EntegrasyonTanimID":null,"Kod1ID":null,"Etiket1ID":null,"SablonID":null});

var config = {
  method: 'post',
  url: 'https://localhost:44346/api/Kasa/post?KayitTipi=1',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer YOURTOKEN'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

```csharp

var client = new RestClient("https://localhost:44346/api/Kasa/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{\r\n    \"KasaID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"KasaKodu\": \"00000000000002\",\r\n    \"KasaAdi\": \"TL Kasa\",\r\n    \"KasaKisaKodu\": \"00000000000002\",\r\n    \"KasaKisaAdi\": \"TL Kasa\",\r\n    \"Durum\": true,\r\n    \"TipID\": 103001,\r\n    \"KasaMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"Seviye\": 1,\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null\r\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kasa/post?KayitTipi=1"

payload="{\r\n    \"KasaID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"KasaKodu\": \"00000000000002\",\r\n    \"KasaAdi\": \"TL Kasa\",\r\n    \"KasaKisaKodu\": \"00000000000002\",\r\n    \"KasaKisaAdi\": \"TL Kasa\",\r\n    \"Durum\": true,\r\n    \"TipID\": 103001,\r\n    \"KasaMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"Seviye\": 1,\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null\r\n}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kasa/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .body("{\r\n    \"KasaID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"KasaKodu\": \"00000000000002\",\r\n    \"KasaAdi\": \"TL Kasa\",\r\n    \"KasaKisaKodu\": \"00000000000002\",\r\n    \"KasaKisaAdi\": \"TL Kasa\",\r\n    \"Durum\": true,\r\n    \"TipID\": 103001,\r\n    \"KasaMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"Seviye\": 1,\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null\r\n}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "Bakiye": null,
        "BakiyeDvz": null,
        "DevirTutar": null,
        "DevirTutarDvz": null,
        "DovizKodu": "TRY",
        "SubeKodu": "SRKT.SUBE",
        "SubeAdi": "Şubem",
        "SirketKodu": "SRKT1",
        "SirketAdi": "Şirket 1",
        "EntegrasyonTanimKodu": null,
        "EntegrasyonTanimAdi": null,
        "TipAdi": "Kasa",
        "TipKodu": null,
        "OnayDurum": 1,
        "OlsTar": "2021-02-19T12:37:38.53",
        "DgsTar": "2021-02-19T12:37:38.53",
        "OlsID": 2,
        "OlsKodu": "yonetici",
        "OlsAdi": "yonetici",
        "DgsID": 2,
        "DgsKodu": "yonetici",
        "DgsAdi": "yonetici",
        "Kod1Kodu": null,
        "Kod1Adi": null,
        "Etiket1Adi": null,
        "SablonKodu": null,
        "SablonAdi": null,
        "ResimAdresi": null,
        "EsnekAramaKisiti": "00000000000002 TL Kasa           ",
        "KasaID": 6,
        "KasaKodu": "00000000000002",
        "KasaAdi": "TL Kasa",
        "DovizID": 1,
        "Seviye": 0,
        "SubeID": 1,
        "SirketID": 1,
        "Durum": true,
        "TipID": 103001,
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Yeni bir kasa kartı eklemek için

### HTTP Request

`POST https://erp.aaro.com.tr/api/Kasa/post?KayitTipi=1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu Body JSON açıklaması

Parametre | Örnek Değer | Tanım | ZorunluMu
--------- | ------- | ----------- | -----------
KasaID | -1 | Eklenilen ürünün Kasa ID'sidir. -1 girildiği takdirde rastgele olarak ID atanmaktadır.  | Evet
SubeID | 1 | Kasanın bulunduğu şubenin ID'sidir. | Evet
SirketID | 1 | Kasanın ait olduğu şirketin ID'sidir. | Evet
KasaKodu | "000000000000001" | Kasanın detaylı kodudur. | Evet
KasaAdi | "MERKEZ KASA" | Kasanın gözüken adıdır. | Evet
KasaKisaKodu |"MerKas" | Kasanın genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki kasaların aynı kisa koda sahip olması önemlidir. | Evet
KasaKisaAdi |"Merkez Kasa" | Kasanın genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki kasaların aynı kisa ada sahip olması önemlidir. | Evet
Durum | true | Kasa kartının aktif veya pasif olduğunu belirlemektedir | Evet
TipID | 105001 | Aaro'da Kasa'yı işaret eder | Evet
KasaMuhasebeID | 201 | Kasaların muhasebesebesi farklı şekilde işlenebilir. Kasa muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz | Evet
DovizID | 1 | Kasanın döviz tipini belirtmeliniz. Örn TL olması için 1 olmalıdır.  | Evet
Kod1ID | null | Kasa kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Merkez -> TL| Opsiyonel
Etiket1ID | null | Kasa etiketleri icindir. Örnek: Merkez | Opsiyonel
SablonID | null | Kasa ekleme şablonu varsa girilmelidir. | Opsiyonel




<aside class="success">
Kasa oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.
</aside>


## Kasa Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Kasa/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"KasaID": -1,
        "SubeID": 1,
        "SirketID": 1,
        "KasaKodu": "00000000000002",
        "KasaAdi": "TL Kasa",
        "KasaKisaKodu": "00000000000002",
        "KasaKisaAdi": "TL Kasa",
        "Durum": true,
        "TipID": 103001,
        "KasaMuhasebeID": 201,
        "DovizID": 1,
        "Seviye": 1,
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null
}'

```

```javascript

var axios = require('axios');
var data = JSON.stringify({"KasaID":-1,"SubeID":1,"SirketID":1,"KasaKodu":"00000000000002","KasaAdi":"TL Kasa","KasaKisaKodu":"00000000000002","KasaKisaAdi":"TL Kasa","Durum":true,"TipID":103001,"KasaMuhasebeID":201,"DovizID":1,"Seviye":1,"EntegrasyonTanimID":null,"Kod1ID":null,"Etiket1ID":null,"SablonID":null});

var config = {
  method: 'post',
  url: 'https://localhost:44346/api/Kasa/post?KayitTipi=2',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer YOURTOKEN'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

```csharp

var client = new RestClient("https://localhost:44346/api/Kasa/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{\r\n    \"KasaID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"KasaKodu\": \"00000000000002\",\r\n    \"KasaAdi\": \"TL Kasa\",\r\n    \"KasaKisaKodu\": \"00000000000002\",\r\n    \"KasaKisaAdi\": \"TL Kasa\",\r\n    \"Durum\": true,\r\n    \"TipID\": 103001,\r\n    \"KasaMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"Seviye\": 1,\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null\r\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kasa/post?KayitTipi=2"

payload="{\r\n    \"KasaID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"KasaKodu\": \"00000000000002\",\r\n    \"KasaAdi\": \"TL Kasa\",\r\n    \"KasaKisaKodu\": \"00000000000002\",\r\n    \"KasaKisaAdi\": \"TL Kasa\",\r\n    \"Durum\": true,\r\n    \"TipID\": 103001,\r\n    \"KasaMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"Seviye\": 1,\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null\r\n}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kasa/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .body("{\r\n    \"KasaID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"KasaKodu\": \"00000000000002\",\r\n    \"KasaAdi\": \"TL Kasa\",\r\n    \"KasaKisaKodu\": \"00000000000002\",\r\n    \"KasaKisaAdi\": \"TL Kasa\",\r\n    \"Durum\": true,\r\n    \"TipID\": 103001,\r\n    \"KasaMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"Seviye\": 1,\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null\r\n}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "Bakiye": null,
        "BakiyeDvz": null,
        "DevirTutar": null,
        "DevirTutarDvz": null,
        "DovizKodu": "TRY",
        "SubeKodu": "SRKT.SUBE",
        "SubeAdi": "Şubem",
        "SirketKodu": "SRKT1",
        "SirketAdi": "Şirket 1",
        "EntegrasyonTanimKodu": null,
        "EntegrasyonTanimAdi": null,
        "TipAdi": "Kasa",
        "TipKodu": null,
        "OnayDurum": 1,
        "OlsTar": "2021-02-19T12:37:38.53",
        "DgsTar": "2021-02-19T12:37:38.53",
        "OlsID": 2,
        "OlsKodu": "yonetici",
        "OlsAdi": "yonetici",
        "DgsID": 2,
        "DgsKodu": "yonetici",
        "DgsAdi": "yonetici",
        "Kod1Kodu": null,
        "Kod1Adi": null,
        "Etiket1Adi": null,
        "SablonKodu": null,
        "SablonAdi": null,
        "ResimAdresi": null,
        "EsnekAramaKisiti": "00000000000002 TL Kasa           ",
        "KasaID": 6,
        "KasaKodu": "00000000000002",
        "KasaAdi": "TL Kasa",
        "DovizID": 1,
        "Seviye": 0,
        "SubeID": 1,
        "SirketID": 1,
        "Durum": true,
        "TipID": 103001,
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Kasa kartı düzeltmek içindir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Kasa/post?KayitTipi=2`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir.

### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KasaID | Integer | Kasa ID'si girilmesi zorunludur.

## Kasa Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Kasa/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"KasaID": -1,
        "SubeID": 1,
        "SirketID": 1,
        "KasaKodu": "00000000000002",
        "KasaAdi": "TL Kasa",
        "KasaKisaKodu": "00000000000002",
        "KasaKisaAdi": "TL Kasa",
        "Durum": true,
        "TipID": 103001,
        "KasaMuhasebeID": 201,
        "DovizID": 1,
        "Seviye": 1,
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null
}'

```

```javascript

var axios = require('axios');
var data = JSON.stringify({"KasaID":-1,"SubeID":1,"SirketID":1,"KasaKodu":"00000000000002","KasaAdi":"TL Kasa","KasaKisaKodu":"00000000000002","KasaKisaAdi":"TL Kasa","Durum":true,"TipID":103001,"KasaMuhasebeID":201,"DovizID":1,"Seviye":1,"EntegrasyonTanimID":null,"Kod1ID":null,"Etiket1ID":null,"SablonID":null});

var config = {
  method: 'post',
  url: 'https://localhost:44346/api/Kasa/post?KayitTipi=-1',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer YOURTOKEN'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

```csharp

var client = new RestClient("https://localhost:44346/api/Kasa/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{\r\n    \"KasaID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"KasaKodu\": \"00000000000002\",\r\n    \"KasaAdi\": \"TL Kasa\",\r\n    \"KasaKisaKodu\": \"00000000000002\",\r\n    \"KasaKisaAdi\": \"TL Kasa\",\r\n    \"Durum\": true,\r\n    \"TipID\": 103001,\r\n    \"KasaMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"Seviye\": 1,\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null\r\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kasa/post?KayitTipi=-1"

payload="{\r\n    \"KasaID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"KasaKodu\": \"00000000000002\",\r\n    \"KasaAdi\": \"TL Kasa\",\r\n    \"KasaKisaKodu\": \"00000000000002\",\r\n    \"KasaKisaAdi\": \"TL Kasa\",\r\n    \"Durum\": true,\r\n    \"TipID\": 103001,\r\n    \"KasaMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"Seviye\": 1,\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null\r\n}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kasa/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .body("{\r\n    \"KasaID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"KasaKodu\": \"00000000000002\",\r\n    \"KasaAdi\": \"TL Kasa\",\r\n    \"KasaKisaKodu\": \"00000000000002\",\r\n    \"KasaKisaAdi\": \"TL Kasa\",\r\n    \"Durum\": true,\r\n    \"TipID\": 103001,\r\n    \"KasaMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"Seviye\": 1,\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null\r\n}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
        "Bakiye": null,
        "BakiyeDvz": null,
        "DevirTutar": null,
        "DevirTutarDvz": null,
        "DovizKodu": "TRY",
        "SubeKodu": "SRKT.SUBE",
        "SubeAdi": "Şubem",
        "SirketKodu": "SRKT1",
        "SirketAdi": "Şirket 1",
        "EntegrasyonTanimKodu": null,
        "EntegrasyonTanimAdi": null,
        "TipAdi": "Kasa",
        "TipKodu": null,
        "OnayDurum": 1,
        "OlsTar": "2021-02-19T12:37:38.53",
        "DgsTar": "2021-02-19T12:37:38.53",
        "OlsID": 2,
        "OlsKodu": "yonetici",
        "OlsAdi": "yonetici",
        "DgsID": 2,
        "DgsKodu": "yonetici",
        "DgsAdi": "yonetici",
        "Kod1Kodu": null,
        "Kod1Adi": null,
        "Etiket1Adi": null,
        "SablonKodu": null,
        "SablonAdi": null,
        "ResimAdresi": null,
        "EsnekAramaKisiti": "00000000000002 TL Kasa           ",
        "KasaID": 6,
        "KasaKodu": "00000000000002",
        "KasaAdi": "TL Kasa",
        "DovizID": 1,
        "Seviye": 0,
        "SubeID": 1,
        "SirketID": 1,
        "Durum": true,
        "TipID": 103001,
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Kasa kartı silmek için

### HTTP Request

`POST https://erp.aaro.com.tr/api/Kasa/post?KayitTipi=-1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | -1 seçilerek mevcut kasanın silineceği bilgisi verilmiştir.





<aside class="warning">
Kasa düzenlemek ile silmek arasındaki fark KayitTipi=-1 olmasıdır. Kasayı silerken bağlı olduğu bütün fhareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
</aside>






# BankaHesap

## BankaHesapları Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/BankaHesap' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://erp.aaro.com.tr/api/BankaHesap',
  headers: {
    'Authorization': 'Bearer YOURTOKEN'
  }
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/BankaHesap");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/BankaHesap"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/BankaHesap")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "SayfalandirmaBilgisi": {
        "maxSayfaSatirSayisi": 100,
        "Sayfa": 1,
        "SayfaSatirSayisi": 10,
        "ToplamSatirSayisi": 4,
        "ToplamSayfaSayisi": 1,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": false,
        "SayfaSatirSayisiAktifSayfada": 4
    },
"Model": [
        {
            "DovizKodu": "TRY",
            "DovizAdi": null,
            "Bakiye": null,
            "BakiyeDvz": null,
            "CariBankaHesapKodu": null,
            "BankaSubeKodu": null,
            "BankaSubeAdi": "YESILBAG",
            "SubeKodu": "TUM",
            "SubeAdi": "Tüm Şubeler",
            "SirketKodu": "SRKT0",
            "SirketAdi": "Şirket 0",
            "EntegrasyonTanimKodu": "000000000000001",
            "EntegrasyonTanimAdi": "İlk Cari Banka Hesabım",
            "TipAdi": "Cari",
            "TipKodu": null,
            "OnayDurum": 1,
            "OlsTar": "2020-09-30T10:34:13.237",
            "DgsTar": "2020-09-30T10:34:13.237",
            "OlsID": 0,
            "OlsKodu": "TUM",
            "OlsAdi": "",
            "DgsID": 0,
            "DgsKodu": "TUM",
            "DgsAdi": "",
            "Kod1Kodu": null,
            "Kod1Adi": null,
            "Etiket1Adi": null,
            "SablonKodu": null,
            "SablonAdi": null,
            "ResimAdresi": null,
            "EsnekAramaKisiti": "00001 İlk Ca No:1            ",
            "BankaHesapID": 1,
            "BankaSubeID": 1,
            "HesapKodu": "00001",
            "HesapAdi": "İlk Ca No:1",
            "CariBankaHesapID": null,
            "IbanNo": "TR000001",
            "Tel": null,
            "Fax": null,
            "Email": null,
            "Web": null,
            "DovizID": 1,
            "SubeID": 0,
            "SirketID": 0,
            "Durum": true,
            "TipID": 108001,
            "EntegrasyonTanimID": 2928,
            "Kod1ID": null,
            "Etiket1ID": null,
            "SablonID": null
        },
        {
          ...
        },
         {
          ...
        },
    ],
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Bu uç nokta ile banka hesaplarınız toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.



### HTTP Request

`GET https://erp.aaro.com.tr/api/BankaHesap?`

### URL Parametreleri

Parameter | Değer | Tanım
--------- | ----------- | ---------
EsnekAramaKisiti | String | Dilediğiniz stringe göre listeleme yapabilirsiniz. Hesap kodunda, Hesap adında ,etiket adlarında, kod adlarında girilen string'e göre arama yapar.
SiralamaKisiti | String | Gelen veriyi sıralamak için kullanılır. Durum, BankaHesapID gibi kolon adları verilmelidir.
Sayfa | Integer | Kaç sayfa BankaHesap getirmek istediğiniz
SayfaSatirSayisi |Integer | Getirilen sayfadaki BankaHesap limiti.
BankaHesapID | Integer | Belirtilen ID ile BankaHesap getirmektedir.
Durum | Boolean | True ise aktif, false ise pasif hesapları getirmektedir.
TipID |Integer |BankaHesabın tipine göre çağırım için mevcuttur. (Tip ID listesinden bakınız)
SubeID | Integer | Şube ID'sine göre hesapları getirmektedir.
SirketID | Integer | Şirket ID'sine göre hesapları getirmektedir.
BankaHesapMuhasebeID | Integer | BankaHesap Muhasebe ID'sine göre hesapları getirmektedir.
OlsID | Integer | BankaHesab'ı Oluşturan kişi ID'sine göre hesapları getirmektedir.




## BankaHesap Ekle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/BankaHesap/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"BankaHesapID": -1,
        "SubeID": 1,
        "SirketID": 1,
        "HesapKodu": "00000000000002",
        "HesapAdi": "TL Hesap",
        "HesapKisaKodu": "00000000000002",
        "HesapKisaAdi": "TL Hesap",
        "Durum": true,
        "TipID": 108001,
        "BankaHesapMuhasebeID": 201, 
        "DovizID": 1,
        "BankaSubeID": 1,
        "CariBankaHesapID": null,
        "IbanNo": "TR00000000000000000000000",
        "Tel": "00000000000",
        "Fax": "00000",
        "Email": "demo@aaro.com.tr",
        "Web": "www.aaro.com.tr",
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null,
}'

```

```javascript

var axios = require('axios');
var data = '{"BankaHesapID": -1,"SubeID": 1,"SirketID": 1,"HesapKodu": "00000000005552","HesapAdi": "TL Hesap","HesapKisaKodu": "00000000000002","HesapKisaAdi": "TL Hesap","Durum": true,"TipID": 108001,"BankaHesapMuhasebeID": 201, "DovizID": 1,"BankaSubeID": 1,"CariBankaHesapID": 1,"IbanNo": "TR00000000000000000000000","Tel": "00000000000","Fax": "00000","Email": "demo@aaro.com.tr","Web": "www.aaro.com.tr","EntegrasyonTanimID": null,"Kod1ID": null,"Etiket1ID": null,"SablonID": null}';

var config = {
  method: 'post',
  url: 'https://localhost:44346/api/BankaHesap/post?KayitTipi=1',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer YOURTOKEN'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

```csharp

var client = new RestClient("https://localhost:44346/api/BankaHesap/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kasa/post?KayitTipi=1"

payload="{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kasa/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .body("{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
    "BankaHesapID": -1,
    "SubeID": 1,
    "SirketID": 1,
    "HesapKodu": "00000000005552",
    "HesapAdi": "TL Hesap",
    "HesapKisaKodu": "00000000000002",
    "HesapKisaAdi": "TL Hesap",
    "Durum": true,
    "TipID": 108001,
    "BankaHesapMuhasebeID": 201,
    "DovizID": 1,
    "BankaSubeID": 1,
    "CariBankaHesapID": 1,
    "IbanNo": "TR00000000000000000000000",
    "Tel": "00000000000",
    "Fax": "00000",
    "Email": "demo@aaro.com.tr",
    "Web": "www.aaro.com.tr",
    "EntegrasyonTanimID": null,
    "Kod1ID": null,
    "Etiket1ID": null,
    "SablonID": null,
    },
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

Yeni bir banka hesap kartı eklemek için

### HTTP Request

`POST https://erp.aaro.com.tr/api/BankaHesap/post?KayitTipi=1`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir.

### Sorgu Body JSON açıklaması

Parametre | Örnek Değer | Tanım | ZorunluMu
--------- | ------- | ----------- | -----------
BankaHesapID | -1 | Eklenilen ürünün BankaHesap ID'sidir. -1 girildiği takdirde rastgele olarak ID atanmaktadır.  | Evet
SubeID | 1 | BankaHesapnın bulunduğu şubenin ID'sidir. | Evet
SirketID | 1 | BankaHesapnın ait olduğu şirketin ID'sidir. | Evet
HesapKodu | "000000000000001" | BankaHesapnın detaylı kodudur. | Evet
HesapAdi | "MERKEZ Bankası" | BankaHesapnın gözüken adıdır. | Evet
HesapKisaKodu |"MerBank" | BankaHesapnın genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki kasaların aynı kisa koda sahip olması önemlidir. | Evet
HesapKisaAdi |"Merkez BankaHesap" | BankaHesapnın genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki kasaların aynı kisa ada sahip olması önemlidir. | Evet
Durum | true | BankaHesap kartının aktif veya pasif olduğunu belirlemektedir | Evet
TipID | 108001 | BankaHesab'ınızın tipinin Pos veya Cari olduğunu belirler. Cari:108001, Pos:108004 | Evet
BankaHesapMuhasebeID | 201 | BankaHesapların muhasebesebesi farklı şekilde işlenebilir. BankaHesap muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz | Evet
DovizID | 1 | BankaHesabının döviz tipini belirtmelisiniz. Örn TL olması için 1 olmalıdır.  | Evet
BankaSubeID | 1 | BankaHesap kartınızın hangi bankanın hangi şubesi olduğunu belirtir. Örn: YESILBAG - TÜRKİYE GARANTİ  | Evet
CariBankaHesapID | 1 | Eğer bu kartın tipi 'CARİDEN' farklı ise bu alt hesabın bağlı olduğu cari hesap girilmelidir.Ana hesabı belirtir. Örn:VAKIFB No:5 (300.5)  | Evet(Koşullu)
IbanNo | null | Bu banka hesabın iban numarasını belirtir. | Opsiyonel
Tel | null | Bu banka hesaba ait telefon numarasını belirtir. | Opsiyonel
Email | null | Bu banka hesaba ait email adresini belirtir. | Opsiyonel
Fax | null | Bu banka hesaba ait fax numarasını belirtir. | Opsiyonel
Web | null | Bu banka hesaba ait internet adresini belirtir. | Opsiyonel
Kod1ID | null | BankaHesap kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Ankara -> Ziraat| Opsiyonel
Etiket1ID | null | BankaHesap etiketleri icindir. Örnek: Merkez | Opsiyonel
SablonID | null | BankaHesap ekleme şablonu varsa girilmelidir. | Opsiyonel




<aside class="success">
BankaHesap oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.
</aside>

## BankaHesap Düzenle


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/BankaHesap/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"BankaHesapID": -1,
        "SubeID": 1,
        "SirketID": 1,
        "HesapKodu": "00000000000002",
        "HesapAdi": "TL Hesap",
        "HesapKisaKodu": "00000000000002",
        "HesapKisaAdi": "TL Hesap",
        "Durum": true,
        "TipID": 108001,
        "BankaHesapMuhasebeID": 201, 
        "DovizID": 1,
        "BankaSubeID": 1,
        "CariBankaHesapID": null,
        "IbanNo": "TR00000000000000000000000",
        "Tel": "00000000000",
        "Fax": "00000",
        "Email": "demo@aaro.com.tr",
        "Web": "www.aaro.com.tr",
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null,
}'

```

```javascript

var axios = require('axios');
var data = '{"BankaHesapID": -1,"SubeID": 1,"SirketID": 1,"HesapKodu": "00000000005552","HesapAdi": "TL Hesap","HesapKisaKodu": "00000000000002","HesapKisaAdi": "TL Hesap","Durum": true,"TipID": 108001,"BankaHesapMuhasebeID": 201, "DovizID": 1,"BankaSubeID": 1,"CariBankaHesapID": 1,"IbanNo": "TR00000000000000000000000","Tel": "00000000000","Fax": "00000","Email": "demo@aaro.com.tr","Web": "www.aaro.com.tr","EntegrasyonTanimID": null,"Kod1ID": null,"Etiket1ID": null,"SablonID": null}';

var config = {
  method: 'post',
  url: 'https://localhost:44346/api/BankaHesap/post?KayitTipi=1',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer YOURTOKEN'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

```csharp

var client = new RestClient("https://localhost:44346/api/BankaHesap/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kasa/post?KayitTipi=1"

payload="{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kasa/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .body("{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
    "BankaHesapID": -1,
    "SubeID": 1,
    "SirketID": 1,
    "HesapKodu": "00000000005552",
    "HesapAdi": "TL Hesap",
    "HesapKisaKodu": "00000000000002",
    "HesapKisaAdi": "TL Hesap",
    "Durum": true,
    "TipID": 108001,
    "BankaHesapMuhasebeID": 201,
    "DovizID": 1,
    "BankaSubeID": 1,
    "CariBankaHesapID": 1,
    "IbanNo": "TR00000000000000000000000",
    "Tel": "00000000000",
    "Fax": "00000",
    "Email": "demo@aaro.com.tr",
    "Web": "www.aaro.com.tr",
    "EntegrasyonTanimID": null,
    "Kod1ID": null,
    "Etiket1ID": null,
    "SablonID": null,
},
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

BankaHesap kartı düzeltmek içindir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/BankaHesap/post?KayitTipi=2`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir.

### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
BankaHesapID | Integer | BankaHesap ID'si girilmesi zorunludur.

## BankaHesap Sil


```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/BankaHesap/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"BankaHesapID": -1,
        "SubeID": 1,
        "SirketID": 1,
        "HesapKodu": "00000000000002",
        "HesapAdi": "TL Hesap",
        "HesapKisaKodu": "00000000000002",
        "HesapKisaAdi": "TL Hesap",
        "Durum": true,
        "TipID": 108001,
        "BankaHesapMuhasebeID": 201, 
        "DovizID": 1,
        "BankaSubeID": 1,
        "CariBankaHesapID": null,
        "IbanNo": "TR00000000000000000000000",
        "Tel": "00000000000",
        "Fax": "00000",
        "Email": "demo@aaro.com.tr",
        "Web": "www.aaro.com.tr",
        "EntegrasyonTanimID": null,
        "Kod1ID": null,
        "Etiket1ID": null,
        "SablonID": null,
}'

```

```javascript

var axios = require('axios');
var data = '{"BankaHesapID": -1,"SubeID": 1,"SirketID": 1,"HesapKodu": "00000000005552","HesapAdi": "TL Hesap","HesapKisaKodu": "00000000000002","HesapKisaAdi": "TL Hesap","Durum": true,"TipID": 108001,"BankaHesapMuhasebeID": 201, "DovizID": 1,"BankaSubeID": 1,"CariBankaHesapID": 1,"IbanNo": "TR00000000000000000000000","Tel": "00000000000","Fax": "00000","Email": "demo@aaro.com.tr","Web": "www.aaro.com.tr","EntegrasyonTanimID": null,"Kod1ID": null,"Etiket1ID": null,"SablonID": null}';

var config = {
  method: 'post',
  url: 'https://localhost:44346/api/BankaHesap/post?KayitTipi=-1',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer YOURTOKEN'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

```csharp

var client = new RestClient("https://localhost:44346/api/BankaHesap/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kasa/post?KayitTipi=-1"

payload="{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kasa/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .body("{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
    "Model": {
    "BankaHesapID": -1,
    "SubeID": 1,
    "SirketID": 1,
    "HesapKodu": "00000000005552",
    "HesapAdi": "TL Hesap",
    "HesapKisaKodu": "00000000000002",
    "HesapKisaAdi": "TL Hesap",
    "Durum": true,
    "TipID": 108001,
    "BankaHesapMuhasebeID": 201,
    "DovizID": 1,
    "BankaSubeID": 1,
    "CariBankaHesapID": 1,
    "IbanNo": "TR00000000000000000000000",
    "Tel": "00000000000",
    "Fax": "00000",
    "Email": "demo@aaro.com.tr",
    "Web": "www.aaro.com.tr",
    "EntegrasyonTanimID": null,
    "Kod1ID": null,
    "Etiket1ID": null,
    "SablonID": null,
},
    "Mesajlar": {},
    "Sonuc": true,
    "MesajlarTumu": ""
}
```

BankaHesap kartı silmek içindir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/BankaHesap/post?KayitTipi=2`

### Sorgu URL Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir.

### Sorgu Body Parametreleri

Parametre | Değer | Tanım
--------- | ----------- | ---------
BankaHesapID | Integer | BankaHesap ID'si girilmesi zorunludur.


<aside class="warning">
BankaHesap düzenlemek ile silmek arasındaki fark KayitTipi=-1 olmasıdır. BankaHesap kartını silerken bağlı olduğu bütün hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
</aside>




