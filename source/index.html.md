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
var axios = require("axios");
var qs = require("qs");
var data = qs.stringify({
  grant_type: "password",
  username: "KULLANICIADINIZ",
  password: "SIFRENIZ",
});
var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/Token",
  headers: {
    "Content-Type": "application/x-www-form-urlencoded",
  },
  data: data,
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

Bu uç nokta ile stoklardaki ürünleri toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.
| Parametre | Değer | Tanım |
| --------- | ------- | ------------------------------------------------------------ |
| TipID | 105001 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. |

## Stoktaki Ürünleri Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Stok' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var axios = require("axios");

var config = {
  method: "get",
  url: "https://erp.aaro.com.tr/api/Stok",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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

### HTTP Request

`GET https://erp.aaro.com.tr/api/Stok?`

### URL Parametreleri

| Parameter        | Değer    | Tanım                                                                                                                         | Örnek      |
| ---------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------- | ---------- |
| EsnekAramaKisiti | String   | Stok Kodunda, Stok Adında, Stoğun kodlarında ve etiketlerinde geçen herhangi bir harf veya kelimeye göre arama yapablirsiniz. | alpi meşe  |
| SirketID         | Integer  | Şirket ID'sine göre ürünleri getirmektedir.                                                                                   | 0          |
| SubeID           | Integer  | Şube ID'sine göre ürünleri getirmektedir.                                                                                     | 0          |
| StokID           | Integer  | Belirtilen ID ile ürünü getirmektedir.                                                                                        | 1089       |
| Kalinlik         | Decimal  | Belirtilen kalinliktaki ürünleri getirmektedir.                                                                               | 2.05       |
| En               | Decimal  | Belirtilen endeki ürünleri getirmektedir.                                                                                     | 2.05       |
| Boy              | Decimal  | Belirtilen boydaki ürünleri getirmektedir.                                                                                    | 2.05       |
| Yogunluk         | Decimal  | Belirtilen yoğunluktaki ürünleri getirmektedir.                                                                               | 2.05       |
| Agirlik          | Decimal  | Belirtilen ağırlıktaki ürünleri getirmektedir.                                                                                | 2.05       |
| BayiGozuksunMu   | Boolean  | true ise bayilerde gözüken, false ise bayilerde görünmeyen ürünleri getirmektedir.                                            | true       |
| StokMuhasebeID   | Integer  | Stok Muhasebe ID'sine göre ürünleri getirmektedir.                                                                            | 1234       |
| StokVergiID      | Integer  | Stok Vergi ID'sine göre ürünleri getirmektedir.                                                                               | 1234       |
| Durum            | Boolean  | true ise aktif, false ise pasif ürünleri getirmektedir.                                                                       | true       |
| TipID            | Integer  | Dökümantasyondaki TipID listesini inceleyiniz.                                                                                | 105001     |
| OlsID            | Integer  | Stoğu Oluşturan kişi ID'sine göre ürünleri getirmektedir.                                                                     | 1234       |
| DgsID            | Integer  | Stoğu Değiştiren kişi ID'sine göre ürünleri getirmektedir.                                                                    | 1234       |
| OlsTarBas        | Datetime | Belirtilen tarihten itibaren oluşturulmuş ürünleri getirmektedir.                                                             | 01.01.2021 |
| OlsTarBit        | Datetime | Belirtilen tarihe kadar oluşturulmuş ürünleri getirmektedir.                                                                  | 01.01.2021 |
| DgsTarBas        | Datetime | Belirtilen tarihten itibaren değiştirilmiş ürünleri getirmektedir.                                                            | 01.01.2021 |
| DgsTarBit        | Datetime | Belirtilen tarihe kadar değiştirilmiş ürünleri getirmektedir.                                                                 | 01.01.2021 |
| SablonID         | Integer  | Belirtilen şablon ile oluşturulmuş stokları getirir.                                                                          | 1234       |
| SiralamaKisiti   | String   | Gelen veriyi sıralamak için kullanılır. Durum, StokID gibi kolon adları verilmelidir.                                         | OlsTarBas  |
| Sayfa            | Integer  | Kaç sayfa ürün getirmek istediğiniz                                                                                           | 8          |
| SayfaSatirSayisi | Integer  | Getirilen sayfadaki ürün limiti.                                                                                              | 100        |

## Stok Ekle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1' \
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
        "Kod2ID": null,
        "Etiket1ID": null,
        "SablonID": null
}'

```

```javascript
var axios = require("axios");
var data = JSON.stringify({
  StokID: -1,
  SubeID: 1,
  SirketID: 1,
  StokKodu: "000000000000049",
  StokAdi: "kolonya",
  StokKisaKodu: "000000000000049",
  StokKisaAdi: "kolonya",
  Durum: true,
  TipID: 105001,
  StokMuhasebeID: 201,
  StokVergiID: 1,
  Brm1ID: 1,
  Brm2ID: null,
  Brm3ID: null,
  CevirimBrm2: null,
  CevirimBrm3: null,
  Kalinlik: 10,
  En: 10,
  Boy: 10,
  Yogunluk: 3,
  Agirlik: 5,
  Kod1ID: null,
  Etiket1ID: null,
  SablonID: null,
});

var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1");
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

url = "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1"

payload = "{\n    \t\"StokID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"kolonya\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"kolonya\",\n        \"Durum\": true,\n        \"TipID\": 105001,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}"
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1")
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
    "Kalinlik": 10.0,
    "En": 10.0,
    "Boy": 10.0,
    "Yogunluk": 3.0,
    "Agirlik": 5.0,
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

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre      | Örnek Değer                                  | Tanım                                                                                                                                                                                                                  | ZorunluMu |
| -------------- | -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| StokID         | -1                                           | Eklenilen ürünün stok ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır.                                                                                                                                  | Evet      |
| SubeID         | 1                                            | Stoğun bulunduğu şubenin ID'sidir.                                                                                                                                                                                     | Evet      |
| SirketID       | 1                                            | Stoğun ait olduğu şirketin ID'sidir.                                                                                                                                                                                   | Evet      |
| StokKodu       | "HRD.KPKL.00164"                             | Stoğun detaylı kodudur.                                                                                                                                                                                                | Evet      |
| StokAdi        | "Hırdavat Kapı Kolu Burak Oda Rozetli Saten" | Stoğun gözüken adıdır.                                                                                                                                                                                                 | Evet      |
| StokKisaKodu   | "HRD.KPKL"                                   | Stoğun genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa koda sahip olması önemlidir.                                                                         | Evet      |
| StokKisaAdi    | "Hırdavat Kapı Kolu"                         | Stoğun genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa ada sahip olması önemlidir.                                                                             | Evet      |
| Durum          | true                                         | Stok kartının aktif veya pasif olduğunu belirlemektedir                                                                                                                                                                | Evet      |
| TipID          | 105001                                       | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Gelir-gider hareketleri gibi işlemler de stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. | Evet      |
| StokMuhasebeID | 201                                          | Stokların muhasebesebesi farklı şekilde işlenebilir. Stok muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz                                                                                        | Evet      |
| StokVergiID    | 1                                            | Stoğun satış ve alış faturasında hangi vergilere tabii olduğunu belirtmektedir. 1 girilmesi durumunda standart olarak %18 KDV sınıfına ekler.                                                                          | Evet      |
| Brm1ID         | 1                                            | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse)                                                                                                                                              | Evet      |
| Brm2ID         | 1                                            | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse)                                                                                                                                              | Opsiyonel |
| Brm3ID         | 1                                            | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse)                                                                                                                                              | Opsiyonel |
| CevirimBrm2    | null                                         | Birim 1'in birim 2 cinsine çevrilmesi içindir.                                                                                                                                                                         | Opsiyonel |
| CevirimBrm3    | null                                         | Birim 1'in birim 3 cinsine çevrilmesi içindir.                                                                                                                                                                         | Opsiyonel |
| Kalinlik       | 10.0                                         | Stok kartının fizikel kalınlığıdır.                                                                                                                                                                                    | Opsiyonel |
| En             | 10.0                                         | Stok kartının fizikel enidir.                                                                                                                                                                                          | Opsiyonel |
| Boy            | 10.0                                         | Stok kartının fizikel boyudur.                                                                                                                                                                                         | Opsiyonel |
| Yoğunluk       | 3.0                                          | Stok kartının fizikel yoğunluğudur.                                                                                                                                                                                    | Opsiyonel |
| Agirlik        | 5.0                                          | Stok kartının fizikel ağırlığıdır.                                                                                                                                                                                     | Opsiyonel |
| Kod1ID         | null                                         | Stok kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Elektronik -> Bilgisayar -> HP                                                                                                                        | Opsiyonel |
| Etiket1ID      | null                                         | Ürün etiketleri icindir.                                                                                                                                                                                               | Opsiyonel |
| SablonID       | null                                         | Ürün ekleme şablonu varsa girilmelidir.                                                                                                                                                                                | Opsiyonel |

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
var axios = require("axios");
var data = JSON.stringify({
  StokID: 356,
  SubeID: 1,
  SirketID: 1,
  StokKodu: "000000000000045",
  StokAdi: "kolonyağı",
  StokKisaKodu: "000000000000045",
  StokKisaAdi: "kolonyağı",
  Durum: true,
  TipID: 105001,
  StokMuhasebeID: 201,
  StokVergiID: 1,
  Brm1ID: 1,
  Brm2ID: null,
  Brm3ID: null,
  CevirimBrm2: null,
  CevirimBrm3: null,
  Kalinlik: 16,
  En: 10,
  Boy: 10,
  Yogunluk: 3,
  Agirlik: 5,
  Kod1ID: null,
  Etiket1ID: null,
  SablonID: null,
});

var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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
    "Kalinlik": 10.0,
    "En": 10.0,
    "Boy": 10.0,
    "Yogunluk": 3.0,
    "Agirlik": 5.0,
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

| Parametre | Değer   | Tanım                                                        |
| --------- | ------- | ------------------------------------------------------------ |
| KayitTipi | Integer | 2 seçilerek mevcut ürünün düzenleneceği bilgisi verilmiştir. |

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
}'

```

```javascript
var axios = require("axios");
var data = JSON.stringify({
  StokID: 348,
  SubeID: 1,
  SirketID: 1,
});

var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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
  "{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1}",
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1"

payload = "{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1}"
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
  .body("{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1}")
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
        "StokID": 356,
        "StokKodu": "000000000000044",
        "StokAdi": "kolonya",
        "StokKisaKodu": "000000000000044",
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

| Parametre | Değer   | Tanım                                                      |
| --------- | ------- | ---------------------------------------------------------- |
| KayitTipi | Integer | -1 seçilerek mevcut ürünün silineceği bilgisi verilmiştir. |

<aside class="warning">
Stok silmek ile düzenlemek arasındaki fark KayitTipi=-1 olmasıdır. Stoğu silerken bağlı olduğu bütün fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
</aside>

# Demirbaş

| Parametre | Değer  | Tanım                                                                                                                                                                                     |
| --------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| TipID     | 105003 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Demirbaş da stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. |

## Demirbaşları Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Stok' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var axios = require("axios");

var config = {
  method: "get",
  url: "https://erp.aaro.com.tr/api/Stok",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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

Bu uç nokta ile stoklardaki demirbaşları toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Stok?`

### URL Parametreleri

| Parameter        | Değer    | Tanım                                                                                                                                     | Örnek      |
| ---------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| EsnekAramaKisiti | String   | Demirbaş Kodunda, Demirbaş Adında, Demirbaşın kodlarında ve etiketlerinde geçen herhangi bir harf veya kelimeye göre arama yapablirsiniz. | alpi meşe  |
| SirketID         | Integer  | Şirket ID'sine göre ürünleri getirmektedir.                                                                                               | 0          |
| SubeID           | Integer  | Şube ID'sine göre ürünleri getirmektedir.                                                                                                 | 0          |
| StokID           | Integer  | Belirtilen ID ile ürünü getirmektedir.                                                                                                    | 1089       |
| Kalinlik         | Decimal  | Belirtilen kalinliktaki ürünleri getirmektedir.                                                                                           | 2.05       |
| En               | Decimal  | Belirtilen endeki ürünleri getirmektedir.                                                                                                 | 2.05       |
| Boy              | Decimal  | Belirtilen boydaki ürünleri getirmektedir.                                                                                                | 2.05       |
| Yogunluk         | Decimal  | Belirtilen yoğunluktaki ürünleri getirmektedir.                                                                                           | 2.05       |
| Agirlik          | Decimal  | Belirtilen ağırlıktaki ürünleri getirmektedir.                                                                                            | 2.05       |
| BayiGozuksunMu   | Boolean  | true ise bayilerde gözüken, false ise bayilerde görünmeyen ürünleri getirmektedir.                                                        | true       |
| StokMuhasebeID   | Integer  | Demirbaş Muhasebe ID'sine göre ürünleri getirmektedir.                                                                                    | 1234       |
| StokVergiID      | Integer  | Demirbaş Vergi ID'sine göre ürünleri getirmektedir.                                                                                       | 1234       |
| Durum            | Boolean  | true ise aktif, false ise pasif ürünleri getirmektedir.                                                                                   | true       |
| TipID            | Integer  | Dökümantasyondaki TipID listesini inceleyiniz.                                                                                            | 105001     |
| OlsID            | Integer  | Oluşturan kişi ID'sine göre demirbaşları getirmektedir.                                                                                   | 1234       |
| DgsID            | Integer  | Değiştiren kişi ID'sine göre demirbaşları getirmektedir.                                                                                  | 1234       |
| OlsTarBas        | Datetime | Belirtilen tarihten itibaren oluşturulmuş demirbaşları getirmektedir.                                                                     | 01.01.2021 |
| OlsTarBit        | Datetime | Belirtilen tarihe kadar oluşturulmuş demirbaşları getirmektedir.                                                                          | 01.01.2021 |
| DgsTarBas        | Datetime | Belirtilen tarihten itibaren değiştirilmiş demirbaşları getirmektedir.                                                                    | 01.01.2021 |
| DgsTarBit        | Datetime | Belirtilen tarihe kadar değiştirilmiş demirbaşları getirmektedir.                                                                         | 01.01.2021 |
| SablonID         | Integer  | Belirtilen şablon ile oluşturulmuş demirbaşları getirir.                                                                                  | 1234       |
| SiralamaKisiti   | String   | Gelen veriyi sıralamak için kullanılır. Durum, StokID gibi kolon adları verilmelidir.                                                     | OlsTarBas  |
| Sayfa            | Integer  | Kaç sayfa demirbaş getirmek istediğiniz                                                                                                   | 8          |
| SayfaSatirSayisi | Integer  | Getirilen sayfadaki demirbaş limiti.                                                                                                      | 100        |

## Demirbaş Ekle

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
var axios = require("axios");
var data = JSON.stringify({
  StokID: -1,
  SubeID: 1,
  SirketID: 1,
  StokKodu: "000000000000049",
  StokAdi: "kolonya",
  StokKisaKodu: "000000000000049",
  StokKisaAdi: "kolonya",
  Durum: true,
  TipID: 105001,
  StokMuhasebeID: 201,
  StokVergiID: 1,
  Brm1ID: 1,
  Brm2ID: null,
  Brm3ID: null,
  CevirimBrm2: null,
  CevirimBrm3: null,
  Kalinlik: 10,
  En: 10,
  Boy: 10,
  Yogunluk: 3,
  Agirlik: 5,
  Kod1ID: null,
  Etiket1ID: null,
  SablonID: null,
});

var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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
    "Kalinlik": 10.0,
    "En": 10.0,
    "Boy": 10.0,
    "Yogunluk": 3.0,
    "Agirlik": 5.0,
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

Yeni bir demirbaş kartı eklemek için

### HTTP Request

`GET https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre      | Örnek Değer                                  | Tanım                                                                                                                                                                                     | ZorunluMu |
| -------------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| StokID         | -1                                           | Eklenilen ürünün stok ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır.                                                                                                     | Evet      |
| SubeID         | 1                                            | Demirbaşın bulunduğu şubenin ID'sidir.                                                                                                                                                    | Evet      |
| SirketID       | 1                                            | Demirbaşın ait olduğu şirketin ID'sidir.                                                                                                                                                  | Evet      |
| StokKodu       | "HRD.KPKL.00164"                             | Demirbaşın detaylı kodudur.                                                                                                                                                               | Evet      |
| StokAdi        | "Hırdavat Kapı Kolu Burak Oda Rozetli Saten" | Demirbaşın gözüken adıdır.                                                                                                                                                                | Evet      |
| StokKisaKodu   | "HRD.KPKL"                                   | Demirbaşın genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa koda sahip olması önemlidir.                                        | Evet      |
| StokKisaAdi    | "Hırdavat Kapı Kolu"                         | Demirbaşın genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki ürünlerin aynı kisa ada sahip olması önemlidir.                                            | Evet      |
| Durum          | true                                         | Demirbaş kartının aktif veya pasif olduğunu belirlemektedir                                                                                                                               | Evet      |
| TipID          | 105003                                       | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Demirbaş da stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. | Evet      |
| StokMuhasebeID | 201                                          | Demirbaşların muhasebesebesi farklı şekilde işlenebilir. Stok muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz                                                       | Evet      |
| StokVergiID    | 1                                            | Demirbaşın satış ve alış faturasında hangi vergilere tabii olduğunu belirtmektedir. 1 girilmesi durumunda standart olarak %18 KDV sınıfına ekler.                                         | Evet      |
| Brm1ID         | 1                                            | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse)                                                                                                                 | Evet      |
| Brm2ID         | 1                                            | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse)                                                                                                                 | Opsiyonel |
| Brm3ID         | 1                                            | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse)                                                                                                                 | Opsiyonel |
| CevirimBrm2    | null                                         | Birim 1'in birim 2 cinsine çevrilmesi içindir.                                                                                                                                            | Opsiyonel |
| CevirimBrm3    | null                                         | Birim 1'in birim 3 cinsine çevrilmesi içindir.                                                                                                                                            | Opsiyonel |
| Kalinlik       | 10.0                                         | Demirbaş kartının fizikel kalınlığıdır.                                                                                                                                                   | Opsiyonel |
| En             | 10.0                                         | Demirbaş kartının fizikel enidir.                                                                                                                                                         | Opsiyonel |
| Boy            | 10.0                                         | Demirbaş kartının fizikel boyudur.                                                                                                                                                        | Opsiyonel |
| Yoğunluk       | 3.0                                          | Demirbaş kartının fizikel yoğunluğudur.                                                                                                                                                   | Opsiyonel |
| Agirlik        | 5.0                                          | Demirbaş kartının fizikel ağırlığıdır.                                                                                                                                                    | Opsiyonel |
| Kod1ID         | null                                         | Demirbaş kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Elektronik -> Bilgisayar -> HP                                                                                       | Opsiyonel |
| Etiket1ID      | null                                         | Ürün etiketleri icindir. Örnek                                                                                                                                                            | Opsiyonel |
| SablonID       | null                                         | Ürün ekleme şablonu varsa girilmelidir.                                                                                                                                                   | Opsiyonel |

<aside class="success">
Ürün oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.
</aside>

## Demirbaş Düzenle

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
var axios = require("axios");
var data = JSON.stringify({
  StokID: 356,
  SubeID: 1,
  SirketID: 1,
  StokKodu: "000000000000045",
  StokAdi: "Demirbaş",
  StokKisaKodu: "000000000000045",
  StokKisaAdi: "Demirbaş",
  Durum: true,
  TipID: 105003,
  StokMuhasebeID: 201,
  StokVergiID: 1,
  Brm1ID: 1,
  Brm2ID: null,
  Brm3ID: null,
  CevirimBrm2: null,
  CevirimBrm3: null,
  Kalinlik: 16,
  En: 10,
  Boy: 10,
  Yogunluk: 3,
  Agirlik: 5,
  Kod1ID: null,
  Etiket1ID: null,
  SablonID: null,
});

var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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
  "{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"Demirbaş\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"Demirbaş\",\n        \"Durum\": true,\n        \"TipID\": 105003,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}",
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2"

payload = "{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"Demirbaş\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"Demirbaş\",\n        \"Durum\": true,\n        \"TipID\": 105003,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}"
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
  .body("{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"000000000000044\",\n        \"StokAdi\": \"Demirbaş\",\n        \"StokKisaKodu\": \"000000000000044\",\n        \"StokKisaAdi\": \"Demirbaş\",\n        \"Durum\": true,\n        \"TipID\": 105003,\n        \"StokMuhasebeID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": 1,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kalinlik\": 10.0,\n        \"En\": 10.0,\n        \"Boy\": 10.0,\n        \"Yogunluk\": 3.0,\n        \"Agirlik\": 5.0,\n        \"Kod1ID\": null,\n        \"Etiket1ID\": null,\n        \"SablonID\": null\n        \n}")
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
    "Kalinlik": 10.0,
    "En": 10.0,
    "Boy": 10.0,
    "Yogunluk": 3.0,
    "Agirlik": 5.0,
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
    "TipID": 105003,
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

Stoktaki bir demirbaşı düzenlemek içindir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                        |
| --------- | ------- | ------------------------------------------------------------ |
| KayitTipi | Integer | 2 seçilerek mevcut ürünün düzenleneceği bilgisi verilmiştir. |

<aside class="warning">
Demirbaş eklemek ile düzenlemek arasındaki fark KayitTipi=2 olmasıdır.
</aside>

## Demirbaş Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"StokID": 356,
        "SubeID": 1,
        "SirketID": 1,
}'

```

```javascript
var axios = require("axios");
var data = JSON.stringify({
  StokID: 348,
  SubeID: 1,
  SirketID: 1,
});

var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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
  "{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1}",
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1"

payload = "{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1}"
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
  .body("{\n    \t\"StokID\": 356,\n        \"SubeID\": 1,\n        \"SirketID\": 1}")
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

Stoktaki bir demirbaşı silmek içindir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                      |
| --------- | ------- | ---------------------------------------------------------- |
| KayitTipi | Integer | -1 seçilerek mevcut ürünün silineceği bilgisi verilmiştir. |

<aside class="warning">
Demirbaş silmek ile düzenlemek arasındaki fark KayitTipi=-1 olmasıdır. Demirbaşı silerken bağlı olduğu bütün fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
</aside>

# GelirGider

| Parametre | Değer  | Tanım                                                                                                                                                                                                |
| --------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| TipID     | 105002 | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Gelir-Gider kartlarıda stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. |

## GelirGider Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Stok' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var axios = require("axios");

var config = {
  method: "get",
  url: "https://erp.aaro.com.tr/api/Stok",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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
            "Brm1Kodu": null,
            "Brm2Kodu": null,
            "Brm3Kodu": null,
            "RaporBrmKodu": null,
            "UretimBrmKodu": null,
            "KartPuan": null,
            "SubeKodu": "SRKT.SUBE",
            "SubeAdi": "Şubem",
            "SirketKodu": "SRKT1",
            "SirketAdi": "Şirket 1",
            "EntegrasyonTanimKodu": "G00000000000012",
            "EntegrasyonTanimAdi": "Banka Komisyon Gideri",
            "TipAdi": "GelirGider",
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
            "EsnekAramaKisiti": "G00000000000012 Banka Komisyon Gideri ",
            "StokID": 1086,
            "StokKodu": "G00000000000012",
            "StokAdi": "Banka Komisyon Gideri",
            "StokKisaKodu": "G00000000000012",
            "StokKisaAdi": "Banka Komisyon Gideri",
            "StokMuhasebeID": 209,
            "StokVergiID": 1,
            "Brm1ID": 2,
            "Brm2ID": null,
            "Brm3ID": null,
            "UretimBrmID": null,
            "RaporBrmID": null,
            "CevirimBrm2": 0.000000,
            "CevirimBrm3": 0.000000,
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
            "TipID": 105002,
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

Bu uç nokta ile gelir-gider kartlarını toplu olarak ya da belirli bir kısıt ile getirebilirsiniz.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Stok?`

### URL Parametreleri

| Parameter          | Değer    | Tanım                                                                                                                                         | Örnek      |
| ------------------ | -------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| EsnekAramaKisiti   | String   | GelirGider Kodunda, GelirGider Adında, GelirGider kodlarında ve etiketlerinde geçen herhangi bir harf veya kelimeye göre arama yapablirsiniz. | Gümrük     |
| SirketID           | Integer  | Şirket ID'sine göre kartları getirmektedir.                                                                                                   | 0          |
| SubeID             | Integer  | Şube ID'sine göre kartları getirmektedir.                                                                                                     | 0          |
| StokID             | Integer  | Belirtilen ID ile kartı getirmektedir.                                                                                                        | 1089       |
| EntegrasyonTanimID | Integer  | GelirGider Muhasebe ID'sine göre kartları getirmektedir.                                                                                      | 1234       |
| StokVergiID        | Integer  | GelirGider Vergi ID'sine göre kartları getirmektedir.                                                                                         | 1234       |
| Durum              | Boolean  | true ise aktif, false ise pasif kartları getirmektedir.                                                                                       | true       |
| TipID              | Integer  | Dökümantasyondaki TipID listesini inceleyiniz.                                                                                                | 105002     |
| OlsID              | Integer  | Oluşturan kişi ID'sine göre demirbaşları getirmektedir.                                                                                       | 1234       |
| DgsID              | Integer  | Değiştiren kişi ID'sine göre demirbaşları getirmektedir.                                                                                      | 1234       |
| OlsTarBas          | Datetime | Belirtilen tarihten itibaren oluşturulmuş demirbaşları getirmektedir.                                                                         | 01.01.2021 |
| OlsTarBit          | Datetime | Belirtilen tarihe kadar oluşturulmuş demirbaşları getirmektedir.                                                                              | 01.01.2021 |
| DgsTarBas          | Datetime | Belirtilen tarihten itibaren değiştirilmiş demirbaşları getirmektedir.                                                                        | 01.01.2021 |
| DgsTarBit          | Datetime | Belirtilen tarihe kadar değiştirilmiş demirbaşları getirmektedir.                                                                             | 01.01.2021 |
| SablonID           | Integer  | Belirtilen şablon ile oluşturulmuş demirbaşları getirir.                                                                                      | 1234       |
| SiralamaKisiti     | String   | Gelen veriyi sıralamak için kullanılır. Durum, StokID gibi kolon adları verilmelidir.                                                         | OlsTarBas  |
| Sayfa              | Integer  | Kaç sayfa demirbaş getirmek istediğiniz                                                                                                       | 8          |
| SayfaSatirSayisi   | Integer  | Getirilen sayfadaki demirbaş limiti.                                                                                                          | 100        |

## GelirGider Ekle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"StokID": -1,
        "SubeID": 1,
        "SirketID": 1,
        "StokKodu": "G00000000000019",
        "StokAdi": "Isınma Giderleri",
        "StokKisaKodu": "G00000000000019",
        "StokKisaAdi": "Isınma Giderleri",
        "Durum": true,
        "TipID": 105002,
        "EntegrasyonTanimID": 201,
        "StokVergiID": 1,
        "Brm1ID": null,
        "Brm2ID": null,
        "Brm3ID": null,
        "CevirimBrm2": null,
        "CevirimBrm3": null,
        "ZorunluCari": false,
        "ZorunluDemirbas": false,
        "ZorunluDekont": false,
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
}'

```

```javascript
var axios = require("axios");
var data = JSON.stringify({
  StokID: -1,
  SubeID: 1,
  SirketID: 1,
  StokKodu: "G00000000000019",
  StokAdi: "Isınma Giderleri",
  StokKisaKodu: "G00000000000019",
  StokKisaAdi: "Isınma Giderleri",
  Durum: true,
  TipID: 105002,
  EntegrasyonTanimID: 201,
  StokVergiID: 1,
  Brm1ID: null,
  Brm2ID: null,
  Brm3ID: null,
  CevirimBrm2: null,
  CevirimBrm3: null,
  ZorunluCari: false,
  ZorunluDemirbas: false,
  ZorunluDekont: false,
  Kod1ID: null,
  Kod2ID: null,
  Kod3ID: null,
  Kod4ID: null,
  Kod5ID: null,
  Kod6ID: null,
  Etiket1ID: null,
  Etiket2ID: null,
  Etiket3ID: null,
  Etiket4ID: null,
  Etiket5ID: null,
  SablonID: null,
});

var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddParameter(
  "application/json",
  "{\n    \t\"StokID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"G00000000000019\",\n        \"StokAdi\": \"Isınma Giderleri\",\n        \"StokKisaKodu\": \"G00000000000019\",\n        \"StokKisaAdi\": \"Isınma Giderleri\",\n        \"Durum\": true,\n        \"ZorunluDemirbas\": false,\n        \"ZorunluCari\": false,\n        \"ZorunluDekont\": false,\n        \"TipID\": 105002,\n        \"EntegrasyonTanimID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": null,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}",
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1"

payload = "{\n    \t\"StokID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"G00000000000019\",\n        \"StokAdi\": \"Isınma Giderleri\",\n        \"StokKisaKodu\": \"G00000000000019\",\n        \"StokKisaAdi\": \"Isınma Giderleri\",\n        \"Durum\": true,\n        \"ZorunluDemirbas\": false,\n        \"ZorunluCari\": false,\n        \"ZorunluDekont\": false,\n        \"TipID\": 105002,\n        \"EntegrasyonTanimID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": null,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n      \n}"
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .body("{\n    \t\"StokID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"G00000000000019\",\n        \"StokAdi\": \"Isınma Giderleri\",\n        \"StokKisaKodu\": \"G00000000000019\",\n        \"StokKisaAdi\": \"Isınma Giderleri\",\n        \"Durum\": true,\n        \"ZorunluDemirbas\": false,\n        \"ZorunluCari\": false,\n        \"ZorunluDekont\": false,\n        \"TipID\": 105002,\n        \"EntegrasyonTanimID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": null,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}")
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
    "Brm1Kodu": null,
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
    "TipAdi": "GelirGider",
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
    "EsnekAramaKisiti": "G00000000000019 Isınma Giderleri",
    "StokID": 3707,
    "StokKodu": "G00000000000019",
    "StokAdi": "Isınma Giderleri",
    "StokKisaKodu": "G00000000000019",
    "StokKisaAdi": "Isınma Giderleri",
    "StokMuhasebeID": 201,
    "StokVergiID": 1,
    "Brm1ID": 1,
    "Brm2ID": null,
    "Brm3ID": null,
    "UretimBrmID": null,
    "RaporBrmID": null,
    "CevirimBrm2": null,
    "CevirimBrm3": null,
    "Kalinlik": 0,
    "En": 0,
    "Boy": 0,
    "Yogunluk": 0,
    "Agirlik": 0,
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
    "TipID": 105002,
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

Yeni bir gelir-gider kartı eklemek için

### HTTP Request

`GET https://erp.aaro.com.tr/api/Stok/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre          | Örnek Değer        | Tanım                                                                                                                                                                                     | ZorunluMu |
| ------------------ | ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| StokID             | -1                 | Eklenilen kartın stok ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır.                                                                                                     | Evet      |
| SubeID             | 1                  | Gelir-Giderin bulunduğu şubenin ID'sidir.                                                                                                                                                 | Evet      |
| SirketID           | 1                  | Gelir-Giderin ait olduğu şirketin ID'sidir.                                                                                                                                               | Evet      |
| StokKodu           | "G00000000000019"  | Gelir-Giderin detaylı kodudur.                                                                                                                                                            | Evet      |
| StokAdi            | "Isınma Giderleri" | Gelir-Giderin gözüken adıdır.                                                                                                                                                             | Evet      |
| StokKisaKodu       | "G00000000000019"  | Gelir-Giderin genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki kartların aynı kisa koda sahip olması önemlidir.                                     | Evet      |
| StokKisaAdi        | "Isınma Giderleri" | Gelir-Giderin genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki kartların aynı kisa ada sahip olması önemlidir.                                         | Evet      |
| Durum              | true               | Gelir-Gider kartının aktif veya pasif olduğunu belirlemektedir                                                                                                                            | Evet      |
| TipID              | 105002             | Aaro'da stok yalnızca fiziksel bir malı işaret etmek durumunda değildir. Demirbaş da stok olarak düşünülmektedir dolayısıyla ne tür bir stok olduğunu belirtmek için TipID bulunmaktadır. | Evet      |
| EntegrasyonTanimID | 201                | Gelir-Giderin muhasebesebesi farklı şekilde işlenebilir. EntegrasyonTanimID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz                                                     | Evet      |
| StokVergiID        | 1                  | Demirbaşın satış ve alış faturasında hangi vergilere tabii olduğunu belirtmektedir. 1 girilmesi durumunda standart olarak %18 KDV sınıfına ekler.                                         | Evet      |
| Brm1ID             | null               | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse)                                                                                                                 | Evet      |
| Brm2ID             | nul                | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse)                                                                                                                 | Opsiyonel |
| Brm3ID             | null               | 1 adet, 2 metre, 3 m^2, 4 metre küp (Kullanıcı hangi birimleri eklediyse)                                                                                                                 | Opsiyonel |
| CevirimBrm2        | null               | Birim 1'in birim 2 cinsine çevrilmesi içindir.                                                                                                                                            | Opsiyonel |
| CevirimBrm3        | null               | Birim 1'in birim 3 cinsine çevrilmesi içindir.                                                                                                                                            | Opsiyonel |
| ZorunluDemirbas    | false              | Bu kart için yapılan hareketlerde hareketin hangi demirbaşa ait olduğunun raporlanabilmesi için seçilir. Her harekette istenecektir.                                                      | Opsiyonel |
| ZorunluCari        | false              | Bu kart için yapılan hareketlerde hareketin hangi cariye ait olduğunun raporlanabilmesi için seçilir. Her harekette istenecektir.                                                         | Opsiyonel |
| ZorunluDekont      | false              | Bu kart için yapılan hareketlerde hareketin hangi dekonta ait olduğunun raporlanabilmesi için seçilir. Her harekette istenecektir.                                                        | Opsiyonel |
| Kod1ID             | null               | Gelir-Gider kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Bina -> Oda -> Isınma                                                                                             | Opsiyonel |
| Etiket1ID          | null               | Kart etiketleri icindir. Örnek                                                                                                                                                            | Opsiyonel |
| SablonID           | null               | Kart ekleme şablonu varsa girilmelidir.                                                                                                                                                   | Opsiyonel |

<aside class="success">
Kart oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.
</aside>

## GelirGider Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"StokID": 220,
        "SubeID": 1,
        "SirketID": 1,
        "StokKodu": "G00000000000019",
        "StokAdi": "Isınma Giderleri",
        "StokKisaKodu": "G00000000000019",
        "StokKisaAdi": "Isınma Giderleri",
        "Durum": true,
        "TipID": 105002,
        "EntegrasyonTanimID": 201,
        "StokVergiID": 1,
        "Brm1ID": null,
        "Brm2ID": null,
        "Brm3ID": null,
        "CevirimBrm2": null,
        "CevirimBrm3": null,
        "ZorunluDemirbas": false,
        "ZorunluCari": false,
        "ZorunluDekont": false,
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
}'

```

```javascript
var axios = require("axios");
var data = JSON.stringify({
  StokID: 220,
  SubeID: 1,
  SirketID: 1,
  StokKodu: "G00000000000019",
  StokAdi: "Isınma Giderleri",
  StokKisaKodu: "G00000000000019",
  StokKisaAdi: "Isınma Giderleri",
  Durum: true,
  TipID: 105002,
  EntegrasyonTanimID: 201,
  StokVergiID: 1,
  Brm1ID: null,
  Brm2ID: null,
  Brm3ID: null,
  CevirimBrm2: null,
  CevirimBrm3: null,
  ZorunluDemirbas: false,
  ZorunluCari: false,
  ZorunluDekont: false,
  Kod1ID: null,
  Kod2ID: null,
  Kod3ID: null,
  Kod4ID: null,
  Kod5ID: null,
  Kod6ID: null,
  Etiket1ID: null,
  Etiket2ID: null,
  Etiket3ID: null,
  Etiket4ID: null,
  Etiket5ID: null,
  SablonID: null,
});

var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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
  "{\n    \t\"StokID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"G00000000000019\",\n        \"StokAdi\": \"Isınma Giderleri\",\n        \"StokKisaKodu\": \"G00000000000019\",\n        \"StokKisaAdi\": \"Isınma Giderleri\",\n        \"Durum\": true,\n        \"ZorunluDemirbas\": false,\n        \"ZorunluCari\": false,\n        \"ZorunluDekont\": false,\n        \"TipID\": 105002,\n        \"EntegrasyonTanimID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": null,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}",
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2"

payload = "{\n    \t\"StokID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"G00000000000019\",\n        \"StokAdi\": \"Isınma Giderleri\",\n        \"StokKisaKodu\": \"G00000000000019\",\n        \"StokKisaAdi\": \"Isınma Giderleri\",\n        \"Durum\": true,\n        \"ZorunluDemirbas\": false,\n        \"ZorunluCari\": false,\n        \"ZorunluDekont\": false,\n        \"TipID\": 105002,\n        \"EntegrasyonTanimID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": null,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}"
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
  .body("{\n    \t\"StokID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"StokKodu\": \"G00000000000019\",\n        \"StokAdi\": \"Isınma Giderleri\",\n        \"StokKisaKodu\": \"G00000000000019\",\n        \"StokKisaAdi\": \"Isınma Giderleri\",\n        \"Durum\": true,\n        \"ZorunluDemirbas\": false,\n        \"ZorunluCari\": false,\n        \"ZorunluDekont\": false,\n        \"TipID\": 105002,\n        \"EntegrasyonTanimID\": 201,\n        \"StokVergiID\": 1,\n        \"Brm1ID\": null,\n        \"Brm2ID\": null,\n        \"Brm3ID\": null,\n        \"CevirimBrm2\": null,\n        \"CevirimBrm3\": null,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}")
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
    "Brm1Kodu": null,
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
    "EntegrasyonTanimKodu": "G00000000000019",
    "EntegrasyonTanimAdi": "Isınma Giderleri",
    "TipAdi": "GelirGider",
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
    "EsnekAramaKisiti": "G00000000000019 Isınma Giderleri            ",
    "StokID": 3705,
    "StokKodu": "G00000000000019",
    "StokAdi": "Isınma Giderleri",
    "StokKisaKodu": "G00000000000019",
    "StokKisaAdi": "Isınma Giderleri",
    "EntegrasyonTanimID": 201,
    "StokVergiID": 1,
    "Brm1ID": 1,
    "Brm2ID": null,
    "Brm3ID": null,
    "UretimBrmID": null,
    "RaporBrmID": null,
    "CevirimBrm2": null,
    "CevirimBrm3": null,
    "Kalinlik": 0,
    "En": 0,
    "Boy": 0,
    "Yogunluk": 0,
    "Agirlik": 0,
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
    "TipID": 105002,
    "EntegrasyonTanimID": 201,
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

Gelir-Gider kartını düzenlemek içindir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Stok/post?KayitTipi=2`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                        |
| --------- | ------- | ------------------------------------------------------------ |
| KayitTipi | Integer | 2 seçilerek mevcut ürünün düzenleneceği bilgisi verilmiştir. |

<aside class="warning">
GelirGider eklemek ile düzenlemek arasındaki fark KayitTipi=2 olmasıdır.
</aside>

## GelirGider Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"StokID": 220,
        "SubeID": 1,
        "SirketID": 1,
}'

```

```javascript
var axios = require("axios");
var data = JSON.stringify({
  StokID: 220,
  SubeID: 1,
  SirketID: 1,
});

var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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
  "{\n    \t\"StokID\": 220,\n        \"SubeID\": 1,\n        \"SirketID\": 1}",
  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1"

payload = "{\n    \t\"StokID\": 220,\n        \"SubeID\": 1,\n        \"SirketID\": 1}"
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
  .body("{\n    \t\"StokID\": 220,\n        \"SubeID\": 1,\n        \"SirketID\": 1}")
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
        "StokID": 220,
        "StokKodu": "G00000000000019",
        "StokAdi": "null",
        "StokKisaKodu": "G00000000000019",
        "StokKisaAdi": "null",
        "EntegrasyonTanimID": null,
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
        "TipID": 105002,
        "EntegrasyonTanimID": 201,
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

GelirGider kartını silmek içindir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Stok/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                      |
| --------- | ------- | ---------------------------------------------------------- |
| KayitTipi | Integer | -1 seçilerek mevcut ürünün silineceği bilgisi verilmiştir. |

<aside class="warning">
GelirGider silmek ile düzenlemek arasındaki fark KayitTipi=-1 olmasıdır. GelirGideri silerken bağlı olduğu bütün fiyat listeleri ve hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
</aside>

# Barkod

## Stoktaki Ürünün Barkodunu Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/StokBarkod' \
--header 'Authorization: Bearer YOURTOKEN'


```

```javascript
var axios = require("axios");

var config = {
  method: "get",
  url: "https://erp.aaro.com.tr/api/StokBarkod",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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

Aaro bir ürün için sonsuz sayıda barkodu kabul etmektedir. Dolayısıyla barkod getir değil barkodları getir şeklinde çalışmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre        | Değer   | Tanım                                     | Örnek          |
| ---------------- | ------- | ----------------------------------------- | -------------- |
| BarkodID         | Integer | Getirilmesi istenenen barkod ID           | 23654          |
| StokID           | Integer | Stoktaki barkodu getirilmesi istenen ürün | 10236          |
| BarkodNo         | String  | Barkod Numarasına göre getirilecek barkod | s0712345678911 |
| BarkodTip        | String  | Barkod Tipine göre getirilecek barkodlar  | null           |
| SayfaSatirSayisi | Integer | Getirilen sayfadaki barkod sayısı         | 40             |
| Sayfa            | Integer | Getirilmesi istenen sayfa numarası        | 3              |

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
var axios = require("axios");
var data = JSON.stringify({
  BarkodID: 6,
  StokID: 201,
  BarkodNo: "s0712345678911",
  BarkodTip: "Telefon Kategorisi",
});

var config = {
  method: "post",
  url: "https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

| Parametre | Değer   | Tanım                                                    |
| --------- | ------- | -------------------------------------------------------- |
| KayitTipi | Integer | 1 (KayitTipi=1 bütün API yapısında ürün kaydet demektir) |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                                                                          | Örnek Değer             | Zorunlu Mu |
| --------- | ------- | ------------------------------------------------------------------------------ | ----------------------- | ---------- |
| BarkodID  | Integer | Barkodun sahip olduğu ID'dir. Özel belirtmek istemiyorsanız -1 verebilirsiniz. | -1                      | Evet       |
| StokID    | Integer | Hangi stoğa bu barkodu vermek istediğinizi belirtmelisiniz                     | 201                     | Evet       |
| BarkodNo  | String  | Barkodun ürün üstünde görünen kısmıdır.                                        | "s0712345678911"        | Evet       |
| BarkodTip | String  | Barkodun ait olduğu stok tipidir.                                              | "Bilgisayar Kategorisi" | Opsiyonel  |

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
    "BarkodNo": "s11987654321070",
    "BarkodTip": "Telefon Kategorisi"
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    BarkodID: 6,
    StokID: 201,
    BarkodNo: "s11987654321070",
    BarkodTip: "Telefon Kategorisi",
  }),
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
request.AddParameter("application/json", "{\n    \"BarkodID\": 6,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s11987654321070\",\n    \"BarkodTip\": \"Telefon Kategorisi\"\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=2"

payload = "{\n    \"BarkodID\": 6,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s11987654321070\",\n    \"BarkodTip\": \"Telefon Kategorisi\"\n}"
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
  .body("{\n    \"BarkodID\": 6,\n    \"StokID\": 201,\n    \"BarkodNo\": \"s11987654321070\",\n    \"BarkodTip\": \"Telefon Kategorisi\"\n}")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "BarkodID": 6,
    "StokID": 201,
    "BarkodNo": "s11987654321070",
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

| Parametre | Değer   | Tanım                                                    |
| --------- | ------- | -------------------------------------------------------- |
| KayitTipi | Integer | 2 (KayitTipi=2 bütün API yapısında ürün düzelt demektir) |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                                                      | Örnek Değer          |
| --------- | ------- | ---------------------------------------------------------- | -------------------- |
| BarkodID  | Integer | Düzeltmek istediğiniz barkod ID'si                         | 6                    |
| StokID    | Integer | Hangi stoğa bu barkodu vermek istediğinizi belirtmelisiniz | 201                  |
| BarkodNo  | String  | Barkodun ürün üstünde görünen kısmıdır.                    | "s11987654321070"    |
| BarkodTip | String  | Barkodun ait olduğu stok tipidir.                          | "Telefon Kategorisi" |

<aside class="info">
Sadece kayıt tipi 2 olarak değişmektedir. BarkodID'si ise 6 olarak girilerek istenilen barkoda ulaşılmıştır.
</aside>

## Stoktaki Ürünün Barkodunu Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "BarkodID": 6
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    BarkodID: 6,
  }),
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
request.AddParameter("application/json", "{\n    \"BarkodID\": 6}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1"

payload = "{\n    \"BarkodID\": 6}"
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
  .body("{\n    \"BarkodID\": 6}")
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

Silmek istediğiniz barkod için aşağıdaki yapıyı kullanınız.

### HTTP Request

`POST https://erp.aaro.com.tr/api/StokBarkod/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                   |
| --------- | ------- | ------------------------------------------------------- |
| KayitTipi | Integer | -1 (KayitTipi=-1 bütün API yapısında ürün sil demektir) |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                           | Örnek Değer |
| --------- | ------- | ------------------------------- | ----------- |
| BarkodID  | Integer | Silmek istediğiniz barkod ID'si | 6           |

<aside class="info">
Barkod silmek ile düzenlemek arasındaki fark KayitTipi=-1 olmasıdır.
</aside>

# Depo

| Parametre | Değer  | Tanım                             |
| --------- | ------ | --------------------------------- |
| TipID     | 107001 | Depo tipi olduğunu belirtir       |
| TipID     | 107002 | Ambar tipi olduğunu belirtir      |
| TipID     | 107003 | Belge Depo tipi olduğunu belirtir |

## Depoları Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Depo?SayfaSatirSayisi=10' \
--header 'Authorization: Bearer YOURTOKEN' \

```

```javascript
var request = require("request");
var options = {
  method: "GET",
  url: "https://erp.aaro.com.tr/api/Depo?SayfaSatirSayisi=10",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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

| Parametre        | Değer    | Tanım                                                                                                                                            | Örnek      |
| ---------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- |
| EsnekAramaKisiti | String   | Dilediğiniz stringe göre listeleme yapabilirsiniz. Depo kodunda, depo adında, etiket adlarında, kod adlarında girilen string'e göre arama yapar. | Depo       |
| DepoID           | Integer  | Belirtilen ID'li depo kartını getirir.                                                                                                           | 1          |
| TipID            | Integer  | Belirtilen tipteki depo kartlarını getirir.                                                                                                      | 17001      |
| CariID           | Integer  | Belirtilen ID'deki carinin atanmış olduğu depo kartlarını getirir.                                                                               | 655        |
| Durum            | Boolean  | true ise aktif, false ise pasif kartları getirmektedir.                                                                                          | true       |
| OlsID            | Integer  | Oluşturan kişi ID'sine göre depo kartlarını getirmektedir.                                                                                       | 1234       |
| DgsID            | Integer  | Değiştiren kişi ID'sine göre depo kartlarını getirmektedir.                                                                                      | 1234       |
| OlsTarBas        | Datetime | Belirtilen tarihten itibaren oluşturulmuş depo kartlarını getirmektedir.                                                                         | 01.01.2021 |
| OlsTarBit        | Datetime | Belirtilen tarihe kadar oluşturulmuş depo kartlarını getirmektedir.                                                                              | 01.01.2021 |
| DgsTarBas        | Datetime | Belirtilen tarihten itibaren değiştirilmiş depo kartlarını getirmektedir.                                                                        | 01.01.2021 |
| DgsTarBit        | Datetime | Belirtilen tarihe kadar değiştirilmiş depo kartlarını getirmektedir.                                                                             | 01.01.2021 |
| SablonID         | Integer  | Belirtilen şablon ile oluşturulmuş depo kartlarını getirir.                                                                                      | 1234       |
| SayfaSatirSayisi | Integer  | Limitli sayıda depo getirmek için kullanılmaktadır.                                                                                              | 10         |

## Depo Oluştur

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    DepoID": -1,
        "SubeID": 1,
        "SirketID": 1,
        "DepoKodu": "DPM",
        "DepoAdi": "Depom",
        "Durum": true,
        "TipID": 107001,
        "EntegrasyonTanimID": null,
        "MaxHacim": 0.00,
        "MaxAgirlik": 0.00,
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
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    DepoID: -1,
    SubeID: 1,
    SirketID: 1,
    DepoKodu: "DPM",
    DepoAdi: "Depom",
    Durum: true,
    TipID: 107001,
    EntegrasyonTanimID: null,
    MaxHacim: 0.0,
    MaxAgirlik: 0.0,
    Kod1ID: null,
    Kod2ID: null,
    Kod3ID: null,
    Kod4ID: null,
    Kod5ID: null,
    Kod6ID: null,
    Etiket1ID: null,
    Etiket2ID: null,
    Etiket3ID: null,
    Etiket4ID: null,
    Etiket5ID: null,
    SablonID: null,
  }),
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
request.AddParameter("application/json", "{\n    \t\"DepoID\": 2,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"DepoKodu\": \"DPM\",\n        \"DepoAdi\": \"DPM Depom\",\n        \"Durum\": true,\n        \"CariID\": null,\n        \"TipID\": 107001,\n        \"EntegrasyonTanimID\": null,\n        \"MaxHacim\": 0.00,\n        \"MaxAgirlik\": 0.00,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1"

payload = "{\n    \t\"DepoID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"DepoKodu\": \"DPM\",\n        \"DepoAdi\": \"Depom\",\n        \"Durum\": true,\n        \"CariID\": null,\n        \"TipID\": 107001,\n        \"EntegrasyonTanimID\": null,\n        \"MaxHacim\": 0.00,\n        \"MaxAgirlik\": 0.00,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}"
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
  .body("{\n    \t\"DepoID\": -1,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"DepoKodu\": \"DPM\",\n        \"DepoAdi\": \"Depom\",\n        \"Durum\": true,\n        \"CariID\": null,\n        \"TipID\": 107001,\n        \"EntegrasyonTanimID\": null,\n        \"MaxHacim\": 0.00,\n        \"MaxAgirlik\": 0.00,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "SubeKodu": "TUM",
    "SubeAdi": "Tüm Şubeler",
    "SirketKodu": "SRKT0",
    "SirketAdi": "Şirket 0",
    "TipAdi": "Depo",
    "TipKodu": null,
    "OnayDurum": 1,
    "OlsTar": "2021-04-06T11:39:37.473",
    "DgsTar": "2021-04-06T11:39:37.473",
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
    "EsnekAramaKisiti": "Depom DPM             ",
    "DepoID": 9,
    "DepoKodu": "DPM",
    "DepoAdi": "Depom",
    "CariID": null,
    "CariKodu": null,
    "MaxHacim": null,
    "MaxAgirlik": 0,
    "SubeID": 0,
    "SirketID": 0,
    "Durum": false,
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
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Yeni bir depo eklemek için kullanılmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                    |
| --------- | ------- | -------------------------------------------------------- |
| KayitTipi | Integer | 1 (KayitTipi=1 bütün API yapısında ürün kaydet demektir) |

### Sorgu Body Parametreleri

| Parametre          | Örnek Değer | Tanım                                                                                                                           | ZorunluMu  |
| ------------------ | ----------- | ------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| DepoID             | -1          | Eklenilen kartın depo ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır.                                           | Evet       |
| SubeID             | 1           | Deponun bulunduğu şubenin ID'sidir.                                                                                             | Evet       |
| SirketID           | 1           | Deponun ait olduğu şirketin ID'sidir.                                                                                           | Evet       |
| DepoKodu           | "DPM"       | Deponun detaylı kodudur.                                                                                                        | Evet       |
| DepoAdi            | "Depom"     | Deponun gözüken adıdır.                                                                                                         | Evet       |
| Durum              | true        | Depo kartının aktif veya pasif olduğunu belirlemektedir                                                                         | Evet       |
| TipID              | 107001      | Aaro'da birden çok depo çeşidi bulunur. Depo 107001, Ambar 107002, Belge Depo 107003.                                           | Evet       |
| MaxHacim           | 0           | Deponun maximum hacmini belirtir                                                                                                | OpsiFyonel |
| MaxAgirlik         | 0           | Deponun maximum ağırlığını belirtir                                                                                             | OpsiFyonel |
| CariID             | 1           | Depodan sorumlu olan cari ID'sini belirtir                                                                                      | OpsiFyonel |
| EntegrasyonTanimID | null        | Deponun muhasebesebesi farklı şekilde işlenebilir. EntegrasyonTanimID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz | Opsiyonel  |
| Kod1ID             | null        | Depo kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Ankara -> Çankaya -> depo                                      | Opsiyonel  |
| Etiket1ID          | null        | Kart etiketleri icindir. Örnek                                                                                                  | Opsiyonel  |
| SablonID           | null        | Kart ekleme şablonu varsa girilmelidir.                                                                                         |

## Depoyu Düzenle

```shell


curl --location --request POST 'https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
        "DepoID": 2,
        "SubeID": 1,
        "SirketID": 1,
        "DepoKodu": "DPM",
        "DepoAdi": "Depom",
        "Durum": true,
        "TipID": 107001,
        "EntegrasyonTanimID": null,
        "MaxHacim": 0,
        "MaxAgirlik": 0,
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
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    DepoID: 2,
    SubeID: 1,
    SirketID: 1,
    DepoKodu: "DPM",
    DepoAdi: "Depom",
    Durum: true,
    TipID: 107001,
    EntegrasyonTanimID: null,
    MaxHacim: 0,
    MaxAgirlik: 0,
    Kod1ID: null,
    Kod2ID: null,
    Kod3ID: null,
    Kod4ID: null,
    Kod5ID: null,
    Kod6ID: null,
    Etiket1ID: null,
    Etiket2ID: null,
    Etiket3ID: null,
    Etiket4ID: null,
    Etiket5ID: null,
    SablonID: null,
  }),
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
request.AddParameter("application/json", "{\n    \t\"DepoID\": 2,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"DepoKodu\": \"DPM\",\n        \"DepoAdi\": \"Depom\",\n        \"Durum\": true,\n        \"CariID\": null,\n        \"TipID\": 107001,\n        \"EntegrasyonTanimID\": null,\n        \"MaxHacim\": 0,\n        \"MaxAgirlik\": 0,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2"

payload = "{\n    \t\"DepoID\": 2,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"DepoKodu\": \"DPM\",\n        \"DepoAdi\": \"Depom\",\n        \"Durum\": true,\n        \"CariID\": null,\n        \"TipID\": 107001,\n        \"EntegrasyonTanimID\": null,\n        \"MaxHacim\": 0,\n        \"MaxAgirlik\": 0,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}"
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
  .body("{\n    \t\"DepoID\": 2,\n        \"SubeID\": 1,\n        \"SirketID\": 1,\n        \"DepoKodu\": \"DPM\",\n        \"DepoAdi\": \"Depom\",\n        \"Durum\": true,\n        \"CariID\": null,\n        \"TipID\": 107001,\n        \"EntegrasyonTanimID\": null,\n        \"MaxHacim\": 0,\n        \"MaxAgirlik\": 0,\n        \"Kod1ID\": null,\n        \"Kod2ID\": null,\n        \"Kod3ID\": null,\n        \"Kod4ID\": null,\n        \"Kod5ID\": null,\n        \"Kod6ID\": null,\n        \"Etiket1ID\": null,\n        \"Etiket2ID\": null,\n        \"Etiket3ID\": null,\n        \"Etiket4ID\": null,\n        \"Etiket5ID\": null,\n        \"SablonID\": null\n        \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "SubeKodu": "TUM",
    "SubeAdi": "Tüm Şubeler",
    "SirketKodu": "SRKT0",
    "SirketAdi": "Şirket 0",
    "TipAdi": "Depo",
    "TipKodu": null,
    "OnayDurum": 1,
    "OlsTar": "2021-04-06T11:39:37.473",
    "DgsTar": "2021-04-06T11:39:37.473",
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
    "EsnekAramaKisiti": "Depom DPM             ",
    "DepoID": 9,
    "DepoKodu": "DPM",
    "DepoAdi": "Depom",
    "CariID": null,
    "CariKodu": null,
    "MaxHacim": null,
    "MaxAgirlik": 0,
    "SubeID": 0,
    "SirketID": 0,
    "Durum": false,
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
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut bir deponun düzeltilmesi için kullanılmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                                  |
| --------- | ------- | ---------------------------------------------------------------------- |
| KayitTipi | Integer | 2 (KayitTipi=2 bütün API yapısında PUT işlemine karşılık gelmektedir.) |

### Sorgu Body Parametreleri

| Parametre          | Değer   | Tanım                                                                                                                           |
| ------------------ | ------- | ------------------------------------------------------------------------------------------------------------------------------- |
| DepoID             | Integer | Düzeltmek istediğiniz deponun ID'si                                                                                             |
| DepoKodu           | String  | Depoya vereceğiniz koddur.                                                                                                      |
| DepoAdi            | String  | Deponuza vereceğiniz ad.                                                                                                        |
| Durum              | Booelan | Depo kartının aktif veya pasif olduğunu belirlemektedir                                                                         |
| TipID              | Integer | Aaro'da birden çok depo çeşidi bulunur. Depo 107001, Ambar 107002, Belge Depo 107003.                                           |
| MaxHacim           | Decimal | Deponun maximum hacmini belirtir                                                                                                |
| MaxAgirlik         | Decimal | Deponun maximum ağırlığını belirtir                                                                                             |
| CariID             | Integer | Depodan sorumlu olan cari ID'sini belirtir                                                                                      |
| EntegrasyonTanimID | Integer | Deponun muhasebesebesi farklı şekilde işlenebilir. EntegrasyonTanimID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz |
| Kod1ID             | Integer | Depo kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Ankara -> Çankaya -> depo                                      |
| Etiket1ID          | Integer | Kart etiketleri icindir.                                                                                                        |
| SablonID           | Integer | Kartın şablonu değiştirilebilir                                                                                                 |

<aside class="warning">
Depo eklemekten farklı olarak ID eklenmesi gerekmektedir.
</aside>

## Depoyu Sil

```shell


curl --location --request POST 'https://erp.aaro.com.tr/api/Depo/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "DepoID": 9,
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    DepoID: 9,
  }),
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
request.AddParameter("application/json", "{\n    \t\"DepoID\": 2   \n}",  ParameterType.RequestBody);
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

| Parametre | Değer   | Tanım                                                                       |
| --------- | ------- | --------------------------------------------------------------------------- |
| KayitTipi | Integer | -1 (KayitTipi=-1 bütün API yapısında DELETE işlemine karşılık gelmektedir.) |

### Sorgu Body Parametreleri

Yalnızca ID ile de silme işlemini gerçekleştirebilirsiniz.

| Parametre | Değer   | Tanım                                                                                                                                             |
| --------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| DepoID    | Integer | Silmek istediğiniz deponun ID'si                                                                                                                  |
| DepoKodu  | String  | Depo kodunuz.                                                                                                                                     |
| DepoAdi   | String  | Depo adınız.                                                                                                                                      |
| TipID     | Integer | Deponuzun ne tür bir depo olduğunu belirtmeniz gerekmektedir. Bu depoya stok eklerken, stok kartlarında da bu TipID'yi belirtmeniz gerekmektedir. |

<aside class="warning">
Depoyu silmeden önce depoya ait bütün hareketlerin ve stoklar silindiğinden/taşındığından emin olunuz. Aksi takdirde silme işlemi gerçekleşmeyecektir.
</aside>

# Döviz

| Parametre | Değer | Tanım           |
| --------- | ----- | --------------- |
| DovizID   | 1     | Türk Lirası TL  |
| DovizID   | 2     | Amerikan Doları |
| DovizID   | 3     | Euro            |

## Dövizleri Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Doviz?SayfaSatirSayisi=10' \
--header 'Authorization: Bearer YOURTOKEN' \

```

```javascript
var request = require("request");
var options = {
  method: "GET",
  url: "https://erp.aaro.com.tr/api/Doviz?SayfaSatirSayisi=10",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Doviz?SayfaSatirSayisi=10");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Doviz?SayfaSatirSayisi=10"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN',
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/Doviz?SayfaSatirSayisi=10")
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
            "OlsTar": "2018-11-09T12:02:49.217",
            "DgsTar": "2018-11-09T12:02:49.217",
            "OlsID": 4,
            "OlsKodu": "yonetici",
            "OlsAdi": "Personel 376",
            "DgsID": 4,
            "DgsKodu": "yonetici",
            "DgsAdi": "Personel 376",
            "EsnekAramaKisiti": "TRY Türk Lirası TL ",
            "DovizID": 1,
            "DovizKodu": "TRY",
            "DovizAdi": "Türk Lirası TL",
            "DovizSembol": null,
            "YaziylaKurus": "Kuruş",
            "Yaziyla": "TL"
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

Oluşturulmuş bütün dövizleri getirmektedir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Doviz?`

### Sorgu URL Parametreleri

| Parametre        | Değer    | Tanım                                                                                                             | Örnek      |
| ---------------- | -------- | ----------------------------------------------------------------------------------------------------------------- | ---------- |
| EsnekAramaKisiti | String   | Dilediğiniz stringe göre listeleme yapabilirsiniz. Doviz kodunda, Doviz adında girilen string'e göre arama yapar. | TL         |
| DovizID          | Integer  | Belirtilen ID'li döviz kartını getirir.                                                                           | 1          |
| OlsID            | Integer  | Oluşturan kişi ID'sine göre depo kartlarını getirmektedir.                                                        | 1234       |
| DgsID            | Integer  | Değiştiren kişi ID'sine göre depo kartlarını getirmektedir.                                                       | 1234       |
| OlsTarBas        | Datetime | Belirtilen tarihten itibaren oluşturulmuş depo kartlarını getirmektedir.                                          | 01.01.2021 |
| OlsTarBit        | Datetime | Belirtilen tarihe kadar oluşturulmuş depo kartlarını getirmektedir.                                               | 01.01.2021 |
| DgsTarBas        | Datetime | Belirtilen tarihten itibaren değiştirilmiş depo kartlarını getirmektedir.                                         | 01.01.2021 |
| DgsTarBit        | Datetime | Belirtilen tarihe kadar değiştirilmiş depo kartlarını getirmektedir.                                              | 01.01.2021 |
| SayfaSatirSayisi | Integer  | Limitli sayıda depo getirmek için kullanılmaktadır.                                                               | 10         |

## Döviz Oluştur

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "DovizID": -1,
        "DovizKodu": "TRY",
        "DovizAdi": "Türk Lirası TL",
        "DovizSembol": "₺",
        "Yaziyla": "TL",
        "YaziylaKurus": "Kuruş",
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    DovizID: -1,
    DovizKodu: "TRY",
    DovizAdi: "Türk Lirası TL",
    DovizSembol: "₺",
    Yaziyla: "TL",
    YaziylaKurus: "Kuruş",
  }),
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Doviz/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \t\"DovizID\": -1,\n        \"DovizKodu\": \"TRY\",\n        \"DovizAdi\": \"Türk Lirası TL\"   \n,\n        \"DovizSembol\": \"₺\",\n        \"Yaziyla\": \"TL\",\n        \"YaziylaKurus\": \"Kuruş\"}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1"

payload = "{\n    \t\"DovizID\": -1,\n        \"DovizKodu\": \"TRY\",\n        \"DovizAdi\": \"Türk Lirası TL\"   \n,\n        \"DovizSembol\": \"₺\",\n        \"Yaziyla\": \"TL\",\n        \"YaziylaKurus\": \"Kuruş\"}"
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
  .body("{\n    \t\"DovizID\": -1,\n        \"DovizKodu\": \"TRY\",\n        \"DovizAdi\": \"Türk Lirası TL\"   \n,\n        \"DovizSembol\": \"₺\",\n        \"Yaziyla\": \"TL\",\n        \"YaziylaKurus\": \"Kuruş\"}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "OlsTar": "2021-04-06T15:07:18.37",
    "DgsTar": "2021-04-06T15:07:18.37",
    "OlsID": 2,
    "OlsKodu": "yonetici",
    "OlsAdi": "yonetici",
    "DgsID": 2,
    "DgsKodu": "yonetici",
    "DgsAdi": "yonetici",
    "EsnekAramaKisiti": "TRY Türk Lirası TL ",
    "DovizID": 10,
    "DovizKodu": "TRY",
    "DovizAdi": "Türk Lirası TL",
    "DovizSembol": "₺",
    "YaziylaKurus": "Kuruş",
    "Yaziyla": "TL"
  },
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Yeni bir döviz eklemek için kullanılmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Depo/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                    |
| --------- | ------- | -------------------------------------------------------- |
| KayitTipi | Integer | 1 (KayitTipi=1 bütün API yapısında ürün kaydet demektir) |

### Sorgu Body Parametreleri

| Parametre    | Örnek Değer | Tanım                                                                                  | ZorunluMu |
| ------------ | ----------- | -------------------------------------------------------------------------------------- | --------- |
| DovizID      | -1          | Eklenilen kartın döviz ID'sidir. -1 girildiği takdirde rasgele olarak ID atanmaktadır. | Evet      |
| DovizKodu    | "DPM"       | Döviz kodudur.                                                                         | Evet      |
| DovizAdi     | "Depom"     | Döviz adıdır.                                                                          | Evet      |
| DovizAdi     | "₺"         | Döviz sembolüdür.                                                                      | Evet      |
| YaziylaKurus | "Kuruş"     | Döviz cinsinin kuruş için belirttiği addır. Örn: Kuruş, Cent                           | Evet      |
| Yaziyla      | "TL"        | Döviz cinsinin okunuşunun yazı halidir.                                                | Evet      |

## Dövizi Düzenle

```shell


curl --location --request POST 'https://erp.aaro.com.tr/api/Doviz/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
        "DovizID": 1,
    "DovizKodu": "TRY",
    "DovizAdi": "Türk Lirası TL",
    "DovizSembol": "₺",
    "Yaziyla": "TL",
    "YaziylaKurus": "Kuruş",
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Doviz/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    DovizID: 1,
    DovizKodu: "TRY",
    DovizAdi: "Türk Lirası TL",
    DovizSembol: "₺",
    Yaziyla: "TL",
    YaziylaKurus: "Kuruş",
  }),
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Doviz/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \t\"DovizID\": -1,\n        \"DovizKodu\": \"TRY\",\n        \"DovizAdi\": \"Türk Lirası TL\"   \n,\n        \"DovizSembol\": \"₺\",\n        \"Yaziyla\": \"TL\",\n        \"YaziylaKurus\": \"Kuruş\}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Depo/post?KayitTipi=2"

payload = "{\n    \t\"DovizID\": -1,\n        \"DovizKodu\": \"TRY\",\n        \"DovizAdi\": \"Türk Lirası TL\"   \n,\n        \"DovizSembol\": \"₺\",\n        \"Yaziyla\": \"TL\",\n        \"YaziylaKurus\": \"Kuruş\}"
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
  .body("{\n    \t\"DovizID\": -1,\n        \"DovizKodu\": \"TRY\",\n        \"DovizAdi\": \"Türk Lirası TL\"   \n,\n        \"DovizSembol\": \"₺\",\n        \"Yaziyla\": \"TL\",\n        \"YaziylaKurus\": \"Kuruş\}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "OlsTar": "2021-04-06T15:07:18.37",
    "DgsTar": "2021-04-06T15:07:18.37",
    "OlsID": 2,
    "OlsKodu": "yonetici",
    "OlsAdi": "yonetici",
    "DgsID": 2,
    "DgsKodu": "yonetici",
    "DgsAdi": "yonetici",
    "EsnekAramaKisiti": "TRY Türk Lirası TL ",
    "DovizID": 10,
    "DovizKodu": "TRY",
    "DovizAdi": "Türk Lirası TL",
    "DovizSembol": "₺",
    "YaziylaKurus": "Kuruş",
    "Yaziyla": "TL"
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

| Parametre | Değer   | Tanım                                                                  |
| --------- | ------- | ---------------------------------------------------------------------- |
| KayitTipi | Integer | 2 (KayitTipi=2 bütün API yapısında PUT işlemine karşılık gelmektedir.) |

### Sorgu Body Parametreleri

| Parametre    | Değer   | Tanım                                |
| ------------ | ------- | ------------------------------------ |
| DovizID      | Integer | Düzeltmek istediğiniz dövizin ID'si  |
| DovizKodu    | String  | Dövize vereceğiniz koddur.           |
| DovizAdi     | String  | Dövize vereceğiniz ad.               |
| DovizSembol  | String  | Dövize vereceğiniz sembol.           |
| YaziylaKurus | String  | Dövize vereceğiniz kuruş okunuşudur. |
| Yaziyla      | String  | Dövize vereceğiniz okunuştur.        |

<aside class="warning">
Döviz eklemekten farklı olarak ID eklenmesi gerekmektedir.
</aside>

## Dövizi Sil

```shell


curl --location --request POST 'https://erp.aaro.com.tr/api/Doviz/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "DovizID": 10,
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Doviz/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    DovizID: 10,
  }),
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/Doviz/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \t\"DovizID\": 10   \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Doviz/post?KayitTipi=-1"

payload = "{\n    \"DovizID\": 10}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))



```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Doviz/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"DovizID\": 10}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": null,
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut bir deponun düzeltilmesi için kullanılmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Doviz/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                                       |
| --------- | ------- | --------------------------------------------------------------------------- |
| KayitTipi | Integer | -1 (KayitTipi=-1 bütün API yapısında DELETE işlemine karşılık gelmektedir.) |

### Sorgu Body Parametreleri

Yalnızca ID ile de silme işlemini gerçekleştirebilirsiniz.

| Parametre | Değer   | Tanım                            |
| --------- | ------- | -------------------------------- |
| DovizID   | Integer | Silmek istediğiniz dövizin ID'si |

<aside class="warning">
Dövizi silmeden önce dövizin kullanıldığı bütün hareketlerin silindiğinden/taşındığından emin olunuz. Aksi takdirde silme işlemi gerçekleşmeyecektir.
</aside>

# Vergi / Vergi Daireleri

## Vergi Oranlarını Getir

```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/StokVergi' \
--header 'Authorization: Bearer YOURTOKEN'


```

```javascript
var request = require("request");
var options = {
  method: "GET",
  url: "https://erp.aaro.com.tr/api/StokVergi?",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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
      "SubeKodu": "TUM",
      "SubeAdi": "Tüm Şubeler",
      "SirketKodu": "SRKT0",
      "SirketAdi": "Şirket 0",
      "TipAdi": null,
      "TipKodu": null,
      "OnayDurum": 0,
      "OlsTar": "0001-01-01T00:00:00",
      "DgsTar": "0001-01-01T00:00:00",
      "OlsID": 0,
      "OlsKodu": null,
      "OlsAdi": null,
      "DgsID": 0,
      "DgsKodu": null,
      "DgsAdi": null,
      "SablonKodu": null,
      "SablonAdi": null,
      "EsnekAramaKisiti": "KDV18 Stok (Kdv18 - Tevkifat 0)",
      "StokVergiID": 1,
      "StokVergiKodu": "KDV18",
      "StokVergiAdi": "Stok (Kdv18 - Tevkifat 0)",
      "AlisKDVOrani": 18,
      "SatisKDVOrani": 18,
      "TevkifatVergiAltID": null,
      "TevkifatVergiAltKodu": null,
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
      "SubeID": 0,
      "SirketID": 0,
      "SablonID": null
    },
    {},
    {}
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

| Parametre        | Değer   | Tanım                                                                                    | Örnek Değer |
| ---------------- | ------- | ---------------------------------------------------------------------------------------- | ----------- |
| EsnekAramaKisiti | String  | Vergi kodunda ve adında geçen herhangi bir harf veya kelimeye göre arama yapabilirsiniz. | KDV         |
| SirketID         | Integer | Şirket ID'sine göre ürünleri getirmektedir.                                              | 0           |
| SubeID           | Integer | Şube ID'sine göre ürünleri getirmektedir.                                                | 0           |
| StokVergiID      | Integer | Sadece belirli bir vergiyi getirmek için eklenmektedir.                                  | 2           |
| SayfaSatirSayisi | Integer | Limitli sayıda vergi kalemi getirmek için kullanılmaktadır.                              | 100         |

## Yeni Vergi Oranı Oluştur

```shell


curl --location --request POST 'https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "StokVergiID": -1,
    "SirketID": 1,
    "SubeID": 1,
    "StokVergiKodu": "KDV18",
    "StokVergiAdi": "Stok (Kdv18 - Tevkifat 0)",
    "AlisKDVOrani": 18,
    "SatisKDVOrani": 18,
    "TevkifatVergiAltID": null,
    "AlisVergi1ID": null,
    "AlisVergi2ID": null,
    "AlisVergi3ID": null,
    "AlisVergi1Oran": null,
    "AlisVergi2Oran": null,
    "AlisVergi3Oran": null,
    "SatisVergi1ID": null,
    "SatisVergi2ID": null,
    "SatisVergi3ID": null,
    "SatisVergi1Oran": null,
    "SatisVergi2Oran": null,
    "SatisVergi3Oran": null,
    "SablonID": null
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    StokVergiID: -1,
    SirketID: 1,
    SubeID: 1,
    StokVergiKodu: "KDV18",
    StokVergiAdi: "Stok (Kdv18 - Tevkifat 0)",
    AlisKDVOrani: 18,
    SatisKDVOrani: 18,
    TevkifatVergiAltID: null,
    AlisVergi1ID: null,
    AlisVergi2ID: null,
    AlisVergi3ID: null,
    AlisVergi1Oran: null,
    AlisVergi2Oran: null,
    AlisVergi3Oran: null,
    SatisVergi1ID: null,
    SatisVergi2ID: null,
    SatisVergi3ID: null,
    SatisVergi1Oran: null,
    SatisVergi2Oran: null,
    SatisVergi3Oran: null,
    SablonID: null,
  }),
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
request.AddParameter("application/json", "{\n    \"StokVergiID\": -1,\n    \"SirketID\": 1,\n    \"SubeID\": 1,\n    \"StokVergiKodu\": \"KDV18\",\n    \"StokVergiAdi\": \"Stok (Kdv18 - Tevkifat 0)\",\n    \"AlisKDVOrani\": 18,\n    \"SatisKDVOrani\": 18,\n    \"TevkifatVergiAltID\": null,\n    \"AlisVergi1ID\": null,\n    \"AlisVergi2ID\": null,\n    \"AlisVergi3ID\": null,\n    \"AlisVergi1Oran\": null,\n    \"AlisVergi2Oran\": null,\n    \"AlisVergi3Oran\": null,\n    \"SatisVergi1ID\": null,\n    \"SatisVergi2ID\": null,\n    \"SatisVergi3ID\": null,\n    \"SatisVergi1Oran\": null,\n    \"SatisVergi2Oran\": null,\n    \"SatisVergi3Oran\": null,n    \"SablonID\": null}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=1"

payload = "{\n    \"StokVergiID\": -1,\n    \"SirketID\": 1,\n    \"SubeID\": 1,\n    \"StokVergiKodu\": \"KDV18\",\n    \"StokVergiAdi\": \"Stok (Kdv18 - Tevkifat 0)\",\n    \"AlisKDVOrani\": 18,\n    \"SatisKDVOrani\": 18,\n    \"TevkifatVergiAltID\": null,\n    \"AlisVergi1ID\": null,\n    \"AlisVergi2ID\": null,\n    \"AlisVergi3ID\": null,\n    \"AlisVergi1Oran\": null,\n    \"AlisVergi2Oran\": null,\n    \"AlisVergi3Oran\": null,\n    \"SatisVergi1ID\": null,\n    \"SatisVergi2ID\": null,\n    \"SatisVergi3ID\": null,\n    \"SatisVergi1Oran\": null,\n    \"SatisVergi2Oran\": null,\n    \"SatisVergi3Oran\": null,n    \"SablonID\": null}"
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
  .body("{\n    \"StokVergiID\": -1,\n    \"SirketID\": 1,\n    \"SubeID\": 1,\n    \"StokVergiKodu\": \"KDV18\",\n    \"StokVergiAdi\": \"Stok (Kdv18 - Tevkifat 0)\",\n    \"AlisKDVOrani\": 18,\n    \"SatisKDVOrani\": 18,\n    \"TevkifatVergiAltID\": null,\n    \"AlisVergi1ID\": null,\n    \"AlisVergi2ID\": null,\n    \"AlisVergi3ID\": null,\n    \"AlisVergi1Oran\": null,\n    \"AlisVergi2Oran\": null,\n    \"AlisVergi3Oran\": null,\n    \"SatisVergi1ID\": null,\n    \"SatisVergi2ID\": null,\n    \"SatisVergi3ID\": null,\n    \"SatisVergi1Oran\": null,\n    \"SatisVergi2Oran\": null,\n    \"SatisVergi3Oran\": null,n    \"SablonID\": null}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "StokVergiID": 10,
    "SirketID": 1,
    "SubeID": 1,
    "StokVergiKodu": "KDV18",
    "StokVergiAdi": "Stok (Kdv18 - Tevkifat 0)",
    "AlisKDVOrani": 18,
    "SatisKDVOrani": 18,
    "TevkifatVergiAltID": null,
    "AlisVergi1ID": null,
    "AlisVergi2ID": null,
    "AlisVergi3ID": null,
    "AlisVergi1Oran": null,
    "AlisVergi2Oran": null,
    "AlisVergi3Oran": null,
    "SatisVergi1ID": null,
    "SatisVergi2ID": null,
    "SatisVergi3ID": null,
    "SatisVergi1Oran": null,
    "SatisVergi2Oran": null,
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

| Parametre | Değer   | Tanım                                                       |
| --------- | ------- | ----------------------------------------------------------- |
| KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre          | Değer   | Tanım                                                                                                               | Zorunlu Mu |
| ------------------ | ------- | ------------------------------------------------------------------------------------------------------------------- | ---------- |
| SirketID           | Integer |                                                                                                                     | Evet       |
| SubeID             | Integer |                                                                                                                     | Evet       |
| StokVergiKodu      | String  | Vergi kodu unique olmalıdır.                                                                                        | Evet       |
| StokVergiAdi       | String  | Vergi adı girilmelidir ( Örnek: Mobilya vergisi)                                                                    | Evet       |
| AlisKDVOrani       | Integer | Bu senaryoda 18 girilmiştir. Yeni düzenlemede bir süreliğine mobilyadan %18 kdv alınmaktadır. Default değeri 0'dır. | Opsiyonel  |
| SatisKDVOrani      | Integer | Bu senaryoda 18 girilmiştir. Yeni düzenlemede bir süreliğine mobilyadan %18 kdv alınmaktadır. Default değeri 0'dır. | Opsiyonel  |
| TevkifatVergiAltID | Integer |                                                                                                                     | Opsiyonel  |
| AlisVergi1ID       | Integer |                                                                                                                     | Opsiyonel  |
| AlisVergi2ID       | Integer |                                                                                                                     | Opsiyonel  |
| AlisVergi3ID       | Integer |                                                                                                                     | Opsiyonel  |
| AlisVergi1Oran     | Integer |                                                                                                                     | Opsiyonel  |
| AlisVergi2Oran     | Integer |                                                                                                                     | Opsiyonel  |
| AlisVergi3Oran     | Integer |                                                                                                                     | Opsiyonel  |
| SatisVergi1ID      | Integer |                                                                                                                     | Opsiyonel  |
| SatisVergi2ID      | Integer |                                                                                                                     | Opsiyonel  |
| SatisVergi3ID      | Integer |                                                                                                                     | Opsiyonel  |
| SatisVergi1Oran    | Integer |                                                                                                                     | Opsiyonel  |
| SatisVergi2Oran    | Integer |                                                                                                                     | Opsiyonel  |
| SatisVergi3Oran    | Integer |                                                                                                                     | Opsiyonel  |
| SablonID           | Integer |                                                                                                                     | Opsiyonel  |

## Vergi Oranını Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "StokVergiID": 10,
    "SirketID": 1,
    "SubeID": 1,
    "StokVergiKodu": "KDV18",
    "StokVergiAdi": "Stok (Kdv18 - Tevkifat 0)",
    "AlisKDVOrani": 18,
    "SatisKDVOrani": 18,
    "TevkifatVergiAltID": null,
    "AlisVergi1ID": null,
    "AlisVergi2ID": null,
    "AlisVergi3ID": null,
    "AlisVergi1Oran": null,
    "AlisVergi2Oran": null,
    "AlisVergi3Oran": null,
    "SatisVergi1ID": null,
    "SatisVergi2ID": null,
    "SatisVergi3ID": null,
    "SatisVergi1Oran": null,
    "SatisVergi2Oran": null,
    "SatisVergi3Oran": null,
    "SablonID": null
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    StokVergiID: 10,
    SirketID: 1,
    SubeID: 1,
    StokVergiKodu: "KDV18",
    StokVergiAdi: "Stok (Kdv18 - Tevkifat 0)",
    AlisKDVOrani: 18,
    SatisKDVOrani: 18,
    TevkifatVergiAltID: null,
    AlisVergi1ID: null,
    AlisVergi2ID: null,
    AlisVergi3ID: null,
    AlisVergi1Oran: null,
    AlisVergi2Oran: null,
    AlisVergi3Oran: null,
    SatisVergi1ID: null,
    SatisVergi2ID: null,
    SatisVergi3ID: null,
    SatisVergi1Oran: null,
    SatisVergi2Oran: null,
    SatisVergi3Oran: null,
    SablonID: null,
  }),
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
request.AddParameter("application/json", "{\n    \"StokVergiID\": 10,\n    \"SirketID\": 1,\n    \"SubeID\": 1,\n    \"StokVergiKodu\": \"KDV18\",\n    \"StokVergiAdi\": \"Stok (Kdv18 - Tevkifat 0)\",\n    \"AlisKDVOrani\": 18,\n    \"SatisKDVOrani\": 18,\n    \"TevkifatVergiAltID\": null,\n    \"AlisVergi1ID\": null,\n    \"AlisVergi2ID\": null,\n    \"AlisVergi3ID\": null,\n    \"AlisVergi1Oran\": null,\n    \"AlisVergi2Oran\": null,\n    \"AlisVergi3Oran\": null,\n    \"SatisVergi1ID\": null,\n    \"SatisVergi2ID\": null,\n    \"SatisVergi3ID\": null,\n    \"SatisVergi1Oran\": null,\n    \"SatisVergi2Oran\": null,\n    \"SatisVergi3Oran\": null,n    \"SablonID\": null}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=2"

payload = "{\n    \"StokVergiID\": 10,\n    \"SirketID\": 1,\n    \"SubeID\": 1,\n    \"StokVergiKodu\": \"KDV18\",\n    \"StokVergiAdi\": \"Stok (Kdv18 - Tevkifat 0)\",\n    \"AlisKDVOrani\": 18,\n    \"SatisKDVOrani\": 18,\n    \"TevkifatVergiAltID\": null,\n    \"AlisVergi1ID\": null,\n    \"AlisVergi2ID\": null,\n    \"AlisVergi3ID\": null,\n    \"AlisVergi1Oran\": null,\n    \"AlisVergi2Oran\": null,\n    \"AlisVergi3Oran\": null,\n    \"SatisVergi1ID\": null,\n    \"SatisVergi2ID\": null,\n    \"SatisVergi3ID\": null,\n    \"SatisVergi1Oran\": null,\n    \"SatisVergi2Oran\": null,\n    \"SatisVergi3Oran\": null,n    \"SablonID\": null}"
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
  .body("{\n    \"StokVergiID\": 10,\n    \"SirketID\": 1,\n    \"SubeID\": 1,\n    \"StokVergiKodu\": \"KDV18\",\n    \"StokVergiAdi\": \"Stok (Kdv18 - Tevkifat 0)\",\n    \"AlisKDVOrani\": 18,\n    \"SatisKDVOrani\": 18,\n    \"TevkifatVergiAltID\": null,\n    \"AlisVergi1ID\": null,\n    \"AlisVergi2ID\": null,\n    \"AlisVergi3ID\": null,\n    \"AlisVergi1Oran\": null,\n    \"AlisVergi2Oran\": null,\n    \"AlisVergi3Oran\": null,\n    \"SatisVergi1ID\": null,\n    \"SatisVergi2ID\": null,\n    \"SatisVergi3ID\": null,\n    \"SatisVergi1Oran\": null,\n    \"SatisVergi2Oran\": null,\n    \"SatisVergi3Oran\": null,n    \"SablonID\": null}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "StokVergiID": 10,
    "SirketID": 1,
    "SubeID": 1,
    "StokVergiKodu": "KDV18",
    "StokVergiAdi": "Stok (Kdv18 - Tevkifat 0)",
    "AlisKDVOrani": 18,
    "SatisKDVOrani": 18,
    "TevkifatVergiAltID": null,
    "AlisVergi1ID": null,
    "AlisVergi2ID": null,
    "AlisVergi3ID": null,
    "AlisVergi1Oran": null,
    "AlisVergi2Oran": null,
    "AlisVergi3Oran": null,
    "SatisVergi1ID": null,
    "SatisVergi2ID": null,
    "SatisVergi3ID": null,
    "SatisVergi1Oran": null,
    "SatisVergi2Oran": null,
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

| Parametre | Değer   | Tanım                                                |
| --------- | ------- | ---------------------------------------------------- |
| KayitTipi | Integer | 2 KayitTipi=2 bütün API'de PUT anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre   | Değer   | Tanım                                                                                                              |
| ----------- | ------- | ------------------------------------------------------------------------------------------------------------------ |
| StokVergiID | Integer | Düzenlenmek istenen vergi ID'si. Zorunludur. Düzenlemek ile eklemek arasındaki tek fark kayıt tipinin 2 olmasıdır. |

## Vergi Oranını Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "StokVergiID": 10

}'
```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({ StokVergiID: 10 }),
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
request.AddParameter("application/json", "{\n    \"StokVergiID\": 10\n  \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=-1"

payload = "{\n    \"StokVergiID\": 10\n  \n}"
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
  .body("{\n    \"StokVergiID\": 10\n  \n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": null,
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Vergi oranını silmektedir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/StokVergi/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                     |
| --------- | ------- | --------------------------------------------------------- |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de DELETE anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre   | Değer   | Tanım                         |
| ----------- | ------- | ----------------------------- |
| StokVergiID | Integer | Silinmek istenen vergi ID'si. |

## Vergi Dairelerini Getir

```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/VergiDairesi' \
--header 'Authorization: Bearer YOURTOKEN'


```

```javascript
var request = require("request");
var options = {
  method: "GET",
  url: "https://erp.aaro.com.tr/api/VergiDairesi?",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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
      "EsnekAramaKisiti": "55110 19 mayıs ",
      "VDID": 435,
      "VDKodu": "55110",
      "VDAdi": "19 mayıs ",
      "VM": "M",
      "IlID": 55,
      "IlAdi": "Samsun"
    },
    {},
    {}
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

| Parametre        | Değer   | Tanım                                                                              |
| ---------------- | ------- | ---------------------------------------------------------------------------------- |
| EsnekAramaKisiti | String  | Vergi Dairesinin adında veya kodunda girilen string'e göre arama yapar             |
| VDID             | Integer | Sadece belirli bir vergi dairesini getirmek için eklenmektedir.                    |
| VDKodu           | String  | Sadece belirli bir koda sahip vergi dairesini getirmek için eklenmektedir.         |
| VDAdi            | String  | Vergi dairesi adına göre sorgulamak için mevcuttur.                                |
| VM               | String  | Mal Müdürlüğü (M) veya Vergi Dairesi (V) olduğunu gösteren alan                    |
| IlID             | Integer | İl koduna göre sonuç dönmektedir.                                                  |
| SayfaSatirSayisi | Integer | Limitli sayıda vergi kalemi getirmek için kullanılmaktadır.                        |
| Sayfa            | Integer | Birden fazla sayfada sonuç geldiğinde, belirli bir sayfaya gitmek için kullanılır. |

## Vergi Dairesi Oluştur

```shell


curl --location --request POST 'https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "VDKodu": "454360",
    "VDAdi": "Yahya Galip Vergi Dairesi",
    "IlID": 6,
    "VM": "V"
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    VDKodu: "454360",
    VDAdi: "Yahya Galip Vergi Dairesi",
    IlID: 6,
    VM: "V",
  }),
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
request.AddParameter("application/json", "{\n    \"VDKodu\": \"454360\",\n    \"VDAdi\" : \"Yahya Galip Vergi Dairesi\",\n  \"IlID\": 6,\n    \"VM\": \"V\" \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=1"

payload = "{\n    \"VDKodu\": \"454360\",\n    \"VDAdi\" : \"Yahya Galip Vergi Dairesi\",\n  \"IlID\": 6,\n    \"VM\": \"V\" \n}"
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
  .body("{\n    \"VDKodu\": \"454360\",\n    \"VDAdi\" : \"Yahya Galip Vergi Dairesi\",\n  \"IlID\": 6,\n    \"VM\": \"V\" \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "VDID": 1042,
    "VDKodu": "454360",
    "VDAdi": "Yahya Galip Vergi Dairesi",
    "VM": "V",
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

| Parametre | Değer   | Tanım                                                       |
| --------- | ------- | ----------------------------------------------------------- |
| KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                                                           | Zorunlu Mu? |
| --------- | ------- | --------------------------------------------------------------- | ----------- |
| VDKodu    | Integer | Vergi dairesi kodu unique olmalıdır.                            | Evet        |
| VDAdi     | String  | Vergi dairesi adı girilmelidir                                  | Evet        |
| IlID      | Integer | Vergi dairesinin bulunduğu il girilmelidir.                     | Evet        |
| VM        | String  | Mal Müdürlüğü (M) veya Vergi Dairesi (V) olduğunu gösteren alan | Opsiyonel   |

## Vergi Dairesi Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "VDID": 1042,
"VDKodu": "454360",
    "VDAdi": "Murat Akan Vergi Dairesi",
"VM": "V",
    "IlID": 6
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    VDID: 1042,
    VDKodu: "454360",
    VDAdi: "Murat Akan Vergi Dairesi",
    VM: "V",
    IlID: 6,
  }),
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
request.AddParameter("application/json", "{\n    \"VDID\": 1042,\n    \"VDKodu\": \"454360\",\n    \"VDAdi\": \"Murat Akan Vergi Dairesi\",\n  \"IlID\": 6,\n    \"VM\": \"V\" \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=2"


payload = "{\n    \"VDID\": 1042,\n    \"VDKodu\": \"454360\",\n    \"VDAdi\": \"Murat Akan Vergi Dairesi\",\n  \"IlID\": 6,\n    \"VM\": \"V\" \n}"
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
  .body("{\n    \"VDID\": 1042,\n    \"VDKodu\": \"454360\",\n    \"VDAdi\": \"Murat Akan Vergi Dairesi\",\n  \"IlID\": 6,\n    \"VM\": \"V\" \n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "VDID": 1042,
    "VDKodu": "454360",
    "VDAdi": "Murat Akan Vergi Dairesi",
    "VM": "V",
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

| Parametre | Değer   | Tanım                                                |
| --------- | ------- | ---------------------------------------------------- |
| KayitTipi | Integer | 2 KayitTipi=2 bütün API'de PUT anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                                                           | Zorunlu Mu? |
| --------- | ------- | --------------------------------------------------------------- | ----------- |
| VDID      | Integer | Düzenlenmek istenen Vergi Dairesi ID'si                         | Evet        |
| VDKodu    | Integer | Vergi dairesi kodu unique olmalıdır.                            | Opsiyonel   |
| VDAdi     | String  | Vergi dairesi adı girilmelidir                                  | Opsiyonel   |
| IlID      | Integer | Vergi dairesinin bulunduğu il girilmelidir.                     | Opsiyonel   |
| VM        | String  | Mal Müdürlüğü (M) veya Vergi Dairesi (V) olduğunu gösteren alan | Opsiyonel   |

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
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({ VDID: 1042 }),
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
  "Model": null,
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Vergi dairesi silinmektedir..

### HTTP Request

`POST https://erp.aaro.com.tr/api/VergiDairesi/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                     |
| --------- | ------- | --------------------------------------------------------- |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de DELETE anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                                | Zorunlu Mu? |
| --------- | ------- | ------------------------------------ | ----------- |
| VDID      | Integer | Silinmek istenen Vergi Dairesi ID'si | Evet        |

<aside class="warning">
Bu işlemin geri dönüşü yoktur. Silmeden önce bu vergi dairesinin hareketlerini silmelisiniz.
</aside>

# Fiyat Listeleri

| Parametre | Değer  | Tanım               |
| --------- | ------ | ------------------- |
| TipID     | 136001 | Satış Fiyat Listesi |
| TipID     | 136002 | Alış Fiyat Listesi  |

## Fiyat Listelerini Getir

```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/FiyatListesi' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var request = require("request");
var options = {
  method: "GET",
  url: "https://erp.aaro.com.tr/api/FiyatListesi",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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
      "SubeKodu": "TUM",
      "SubeAdi": "Tüm Şubeler",
      "SirketKodu": "SRKT0",
      "SirketAdi": "Şirket 0",
      "TipAdi": "Satis",
      "TipKodu": null,
      "OnayDurum": 1,
      "OlsTar": "2018-05-11T11:03:04.807",
      "DgsTar": "2018-11-13T16:36:31.483",
      "OlsID": 3,
      "OlsKodu": "yonetici",
      "OlsAdi": "Personel 90",
      "DgsID": 3,
      "DgsKodu": "yonetici",
      "DgsAdi": "Personel 376",
      "Etiket1Adi": null,
      "Etiket2Adi": null,
      "Etiket3Adi": null,
      "Etiket4Adi": null,
      "Etiket5Adi": null,
      "SablonKodu": null,
      "SablonAdi": null,
      "EsnekAramaKisiti": "HZKP.2018-2.S HazırKapı (2018-2) Satış     ",
      "FiyatListesiID": 184,
      "Kodu": "HZKP.2018-2.S",
      "Adi": "HazırKapı (2018-2) Satış",
      "Vade": 120,
      "TarihBas": "2018-06-01T00:00:00",
      "TarihBit": "2018-11-13T00:00:00",
      "SubeID": 0,
      "SirketID": 0,
      "Durum": true,
      "TipID": 136001,
      "Etiket1ID": null,
      "Etiket2ID": null,
      "Etiket3ID": null,
      "Etiket4ID": null,
      "Etiket5ID": null
    },
    {},
    {}
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

| Parametre        | Değer    | Tanım                                                                                                                                                   |
| ---------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| EsnekAramaKisiti | String   | Dilediğiniz stringe göre listeleme yapabilirsiniz. Fiyat listerinin kodunda, adında, etiket adlarında, kod adlarında girilen string'e göre arama yapar. |
| SayfaSatirSayisi | Integer  | Limitli sayıda fiyat listesi getirmek için kullanılmaktadır.                                                                                            |
| FiyatListesiID   | Integer  | Sadece belirli bir fiyat listesini getirmek için eklenmektedir.                                                                                         |
| TipID            | Integer  | Fiyat listelerinin tipine göre çağırım için mevcuttur. (alım fiyat listesi, satış fiyat listesi gibi)                                                   |
| Vade             | Integer  | Listelerin vadesi                                                                                                                                       |
| VadeBas          | DateTime | Listelerin geçerli olduğu Vade başlangıcı                                                                                                               |
| VadeBit          | DateTime | Listelerin geçerli olduğu son Vade                                                                                                                      |
| TarihBasBas      | DateTime | Listelerin geçerli olduğu tarih başlangıcı alt sınırı                                                                                                   |
| TarihBasBit      | DateTime | Listelerin geçerli olduğu tarih başlangıcı üst sınırı                                                                                                   |
| TarihBitBas      | DateTime | Listelerin geçerli olduğu bitiş tarihinin alt sınırı                                                                                                    |
| TarihBitBit      | DateTime | Listelerin geçerli olduğu bitiş tarihinin üst sınırı                                                                                                    |
| TarihBas         | DateTime | Listelerin geçerli olduğu tarih başlangıcı                                                                                                              |
| TarihBit         | DateTime | Listelerin geçerli olduğu son tarih                                                                                                                     |
| OlsID            | Integer  | Oluşturan kişi ID'si                                                                                                                                    |
| DgsID            | Integer  | Değiştiren kişi ID'si                                                                                                                                   |
| Durum            | Boolean  | Aktif veya Pasif listeler için mevcuttur.                                                                                                               |
| OnayDurum        | Integer  | Listenin onayı var mı?                                                                                                                                  |
| OlsTarBas        | DateTime | Listelerin oluşturulma tarihlerinin başlangıcı                                                                                                          |
| OlsTarBit        | DateTime | Listelerin oluşturulma tarihlerinin bitisi                                                                                                              |
| DgsTarBas        | DateTime | Listelerin değiştirilme tarihlerinin başlangıcı                                                                                                         |
| DgsTarBit        | DateTime | Listelerin değiştirilme tarihlerinin bitisi                                                                                                             |
| SirketID         | Integer  | Belirli bir şirkete ait fiyat listeleri için girilmektedir.                                                                                             |
| SubeID           | Integer  | Belirli bir şubenin listelerini getirmek için kullanılmaktadır.                                                                                         |

<aside class="info">
Genelde şirket ve şube belirtilerek fiyat listeleri getirilir. Örnek: https://erp.aaro.com.tr/api/FiyatListesi?SubeID=1&SirketID=1 
</aside>

## Fiyat Listesi Oluştur

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "SirketID": 0,
    "SubeID": 0,
    "Kodu": "0123-Ss",
    "Adi": "Satis Fiyat Listesi",
    "TarihBas": "2019-07-03",
    "TarihBit": "2020-07-03",
    "Vade": 150,
    "TipID": 136001,
    "Durum": true
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    SirketID: 0,
    SubeID: 0,
    Kodu: "0123-Ss",
    Adi: "Satis Fiyat Listesi",
    TarihBas: "2019-07-03",
    TarihBit: "2020-07-03",
    Vade: 150,
    TipID: 136001,
    Durum: true,
  }),
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
request.AddParameter("application/json", "{\n    \"SirketID\": 0,\n    \"SubeID\": 0,\n    \"Kodu\": \"0123-Ss\",\n    \"Adi\": \"Satis Fiyat Listesi\",\n    \"TarihBas\": \"2019-07-03\",\n    \"TarihBit\": \"2020-07-03\",\n    \"Vade\": 150,\n    \"TipID\": 136001,\n    \"Durum\": true\n    \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1"

payload = "{\n    \"SirketID\": 0,\n    \"SubeID\": 0,\n    \"Kodu\": \"0123-Ss\",\n    \"Adi\": \"Satis Fiyat Listesi\",\n    \"TarihBas\": \"2019-07-03\",\n    \"TarihBit\": \"2020-07-03\",\n    \"Vade\": 150,\n    \"TipID\": 136001,\n    \"Durum\": true\n    \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"SirketID\": 0,\n    \"SubeID\": 0,\n    \"Kodu\": \"0123-Ss\",\n    \"Adi\": \"Satis Fiyat Listesi\",\n    \"TarihBas\": \"2019-07-03\",\n    \"TarihBit\": \"2020-07-03\",\n    \"Vade\": 150,\n    \"TipID\": 136001,\n    \"Durum\": true\n    \n}")
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
    "Adi": "Satis Fiyat Listesi",
    "TipID": 136001,
    "TarihBas": "2019-07-03T00:00:00",
    "TarihBit": "2020-07-03T00:00:00",
    "Vade": 150,
    "Durum": true,
    "OnayDurum": 1,
    "OlsID": 4,
    "OlsTar": "2019-07-07T12:37:55.4333781+03:00",
    "DgsID": 4,
    "DgsTar": "2019-07-07T12:37:55.4333781+03:00"
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

| Parametre | Değer   | Tanım                                                       |
| --------- | ------- | ----------------------------------------------------------- |
| KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                                      |
| --------- | ------- | ------------------------------------------ |
| SirketID  | Integer | Fiyat Listesinin açıldığı şirket           |
| SubeID    | Integer | Fiyat Listesinin açıldığı şube             |
| Kodu      | String  | Fiyat listesine vereceğiniz kod            |
| Adi       | String  | Fiyat listesine vereceğiniz ad             |
| TarihBas  | String  | Listelerin geçerli olduğu tarih başlangıcı |
| TarihBit  | String  | Listelerin geçerli olduğu son tarih        |
| TipID     | Integer | TipID tablosundan bakınız                  |
| Vade      | Integer | Fiyat listesinin vadesi                    |
| Durum     | Boolean | Aktif ya da pasif olması için önemlidir    |

## Fiyat Listesini Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "FiyatListesiID": 10,
    "SirketID": 0,
    "SubeID": 0,
    "Kodu": "0123-Ss",
    "Adi": "Satis Fiyat Listesi",
    "TarihBas": "2019-07-03",
    "TarihBit": "2020-07-03",
    "Vade": 150,
    "TipID": 136001,
    "Durum": true

}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    FiyatListesiID: 10,
    SirketID: 0,
    SubeID: 0,
    Kodu: "0123-Ss",
    Adi: "Satis Fiyat Listesi",
    TarihBas: "2019-07-03",
    TarihBit: "2020-07-03",
    Vade: 150,
    TipID: 136001,
    Durum: true,
  }),
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
request.AddParameter("application/json", "{\n    \"FiyatListesiID\":10,\n    \"Kodu\": \"0123-Ss\",\n    \"Adi\": \"Satis Fiyat Listesi\",\n        \"TarihBas\": \"2019-07-03T14:53:47.5\",\n        \"TarihBit\": \"2020-07-03T14:53:47.5\",\n            \"TipID\": 136001,\n            \"Vade\": 150,\n            \"Durum\": true\n    \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=1"

payload = "{\n    \"FiyatListesiID\":10,\n    \"Kodu\": \"0123-Ss\",\n    \"Adi\": \"Satis Fiyat Listesi\",\n        \"TarihBas\": \"2019-07-03T14:53:47.5\",\n        \"TarihBit\": \"2020-07-03T14:53:47.5\",\n            \"TipID\": 136001,\n            \"Vade\": 150,\n            \"Durum\": true\n    \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"FiyatListesiID\":10,\n    \"Kodu\": \"0123-Ss\",\n    \"Adi\": \"Satis Fiyat Listesi\",\n        \"TarihBas\": \"2019-07-03T14:53:47.5\",\n        \"TarihBit\": \"2020-07-03T14:53:47.5\",\n            \"TipID\": 136001,\n            \"Vade\": 150,\n            \"Durum\": true\n    \n}")
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
    "Adi": "Satis Fiyat Listesi",
    "TipID": 136001,
    "TarihBas": "2019-07-03T14:53:47.5",
    "TarihBit": "2020-07-03T14:53:47.5",
    "Vade": 150,
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

| Parametre | Değer   | Tanım                                                              |
| --------- | ------- | ------------------------------------------------------------------ |
| KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre      | Değer   | Tanım                                      |
| -------------- | ------- | ------------------------------------------ |
| FiyatListesiID | Integer | Fiyat listesinin ID'si                     |
| SirketID       | Integer | Fiyat listesinin ait olduğu şirket ID'si   |
| SubeID         | Integer | Fiyat listesinin ait olduğu şube ID'si     |
| Kodu           | String  | Fiyat listesine vereceğiniz kod            |
| Adi            | String  | Fiyat listesine vereceğiniz ad             |
| TarihBas       | String  | Listelerin geçerli olduğu tarih başlangıcı |
| TarihBit       | String  | Listelerin geçerli olduğu son tarih        |
| Vade           | Integer | Fiyat Listesinin vadesi                    |
| TipID          | Integer | TipID tablosundan bakınız                  |
| Durum          | Boolean | Aktif ya da pasif olması için önemlidir    |

## Fiyat Listesini Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "FiyatListesiID":10,
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({ FiyatListesiID: 10 }),
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
request.AddParameter("application/json", "{\n    \"FiyatListesiID\":10,\n       \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1"

payload = "{\n    \"FiyatListesiID\":10,\n     \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"FiyatListesiID\":10,\n      \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": null,
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut fiyat listesini silmektedir

### HTTP Request

`POST https://erp.aaro.com.tr/api/FiyatListesi/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                               |
| --------- | ------- | ------------------------------------------------------------------- |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de yeni DELETE(sil) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre      | Değer   | Tanım                                  |
| -------------- | ------- | -------------------------------------- |
| FiyatListesiID | Integer | Silmek istediğiniz fiyat listesi ID'si |

<aside class="warning">
Bu işlemin geri dönüşü yoktur. Silmeden önce bu fiyat listesine bağlı tüm stokların ve hareketlerin liste ile ilişkisini kesmelisiniz.
</aside>

# Fiyat Listesi Satirlar

## Fiyat Listesi Satirlar Getir

```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/FiyatListesiSatirlar' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var request = require("request");
var options = {
  method: "GET",
  url: "https://erp.aaro.com.tr/api/FiyatListesiSatirlar",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/FiyatListesiSatirlar?");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesiSatirlar?"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/FiyatListesiSatirlar")
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
      "SirketKodu": "SRKT0",
      "SubeKodu": "TUM",
      "TarihBas": "2017-02-01T00:00:00",
      "TarihBit": "2017-08-30T00:00:00",
      "TipKodu": "Satis",
      "TipAdi": "Satis",
      "DovizAdi": "Türk Lirası TL",
      "BirimAdi": "Adet",
      "OnayDurum": 1,
      "OlsTar": "2017-01-30T16:48:52.283",
      "DgsTar": "2017-02-08T17:00:39.327",
      "OlsID": 0,
      "OlsKodu": "yonetici",
      "OlsAdi": "",
      "DgsID": 3,
      "DgsKodu": "yonetici",
      "DgsAdi": "Personel 90",
      "EsnekAramaKisiti": "ZAI (2017--109  Ahşap (2017-1) Ahşap Arızalı Ürün 0.400000 Türk Lirası TL ",
      "StrID": 8225,
      "FiyatListesiID": 109,
      "FiyatListesiKodu": "ZAI (2017--109 ",
      "FiyatListesiAdi": "Ahşap (2017-1)",
      "StokID": 3927,
      "StokKodu": "ZAI.ARZL.00001",
      "StokAdi": "Ahşap Arızalı Ürün",
      "Durum": true,
      "TipID": 136001,
      "Nakliye": 0.0,
      "Diger": 0.0,
      "Fiyat": 0.4,
      "DovizID": 1,
      "DovizKodu": "TRY",
      "BirimID": 1,
      "BirimKodu": "AD"
    },
    {},
    {}
  ],
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Bütün fiyat listelerini ya da istenilen kısıttaki fiyat listelerini getirmektedir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/FiyatListesiSatirlar?`

### Sorgu URL Parametreleri

| Parametre        | Değer    | Tanım                                                                                                                                                                                                       |
| ---------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| EsnekAramaKisiti | String   | Dilediğiniz stringe göre listeleme yapabilirsiniz. Satırın ait olduğu fiyat listesinin kodunda, adında ve satira ait stoğun kodunda ve adinda, fiyatında ve döviz adında girilen string'e göre arama yapar. |
| StrID            | Integer  | Sadece belirli bir fiyat liste satırını getirmek için eklenmektedir.                                                                                                                                        |
| FiyatListesiID   | Integer  | Sadece belirli bir fiyat listesine ait satırları getirmek için eklenmektedir.                                                                                                                               |
| StokID           | Integer  | Bu ID'ye sahip stoğun fiat satırları getirilir.                                                                                                                                                             |
| Fiyat            | Integer  | Fiyat liste satırlanın fiyatına göre arama yapmak için. Girilen fiyata sahip olan satırlar gelir.                                                                                                           |
| DovizID          | Integer  | Fiyat liste satırlanın fiyatının döviz cinsini belirtir                                                                                                                                                     |
| TipID            | Integer  | Fiyat listelerinin tipine göre çağırım için mevcuttur. (alım fiyat listesi, satış fiyat listesi gibi)                                                                                                       |
| TarihBas         | DateTime | Satırın ait olduğu Fiyat Listesinin tarih başlangıcı                                                                                                                                                        |
| TarihBit         | DateTime | Satırın ait olduğu Fiyat Listesinin son tarihi                                                                                                                                                              |
| OlsID            | Integer  | Oluşturan kişi ID'si                                                                                                                                                                                        |
| DgsID            | Integer  | Değiştiren kişi ID'si                                                                                                                                                                                       |
| Durum            | Boolean  | Aktif veya Pasif listeler için mevcuttur.                                                                                                                                                                   |
| OnayDurum        | Integer  | Listenin onayı var mı?                                                                                                                                                                                      |
| OlsTarBas        | DateTime | Listelerin oluşturulma tarihlerinin başlangıcı                                                                                                                                                              |
| OlsTarBit        | DateTime | Listelerin oluşturulma tarihlerinin bitisi                                                                                                                                                                  |
| DgsTarBas        | DateTime | Listelerin değiştirilme tarihlerinin başlangıcı                                                                                                                                                             |
| DgsTarBit        | DateTime | Listelerin değiştirilme tarihlerinin bitisi                                                                                                                                                                 |
| SirketID         | Integer  | Belirli bir şirkete ait fiyat listelerinin satırlarını çekmek için girilmektedir.                                                                                                                           |
| SubeID           | Integer  | Belirli bir şubenin fiyat listelerinin satırlarını çekmek için kullanılmaktadır.                                                                                                                            |
| SayfaSatirSayisi | Integer  | Limitli sayıda fiyat listesi getirmek için kullanılmaktadır.                                                                                                                                                |

<aside class="info">
Genelde şirket ve şube belirtilerek fiyat listeleri getirilir. Örnek: https://erp.aaro.com.tr/api/FiyatListesi?SubeID=1&SirketID=1 
</aside>

## Fiyat Listesi Satir Ekle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "FiyatListesiID": 306,
    "StokID": 8147,
    "Fiyat": 45.75,
    "DovizID":1 ,
    "TipID": 136001
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    FiyatListesiID: 306,
    StokID: 8147,
    Fiyat: 45.75,
    DovizID: 1,
    TipID: 136001,
  }),
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"FiyatListesiID\": 306,\n    \"StokID\": 8147,\n    \"Fiyat\": 45.75,\n    \"DovizID\": 1,\n    \"TipID\": 136001  \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=1"

payload = "{\n    \"FiyatListesiID\": 306,\n    \"StokID\": 8147,\n    \"Fiyat\": 45.75,\n    \"DovizID\": 1,\n    \"TipID\": 136001  \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n    \"FiyatListesiID\": 306,\n    \"StokID\": 8147,\n    \"Fiyat\": 45.75,\n    \"DovizID\": 1,\n    \"TipID\": 136001  \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "SirketKodu": "SRKT0",
    "SubeKodu": "TUM",
    "TarihBas": "2021-08-08T00:00:00",
    "TarihBit": "2021-09-30T00:00:00",
    "TipKodu": "Satis",
    "TipAdi": "Satis",
    "DovizAdi": "Türk Lirası TL",
    "BirimAdi": "Adet",
    "OnayDurum": 1,
    "OlsTar": "2021-08-17T10:55:10.87",
    "DgsTar": "2021-08-17T10:55:10.87",
    "OlsID": 2,
    "OlsKodu": "yonetici",
    "OlsAdi": "A Kullanicisii",
    "DgsID": 2,
    "DgsKodu": "yonetici",
    "DgsAdi": "A Kullanicisii",
    "EsnekAramaKisiti": "KOPYA0000000010 HazırKapı (20210808) S HazırKapı BaşlıkKasaPervaz     4.1X15X134cm 45.750000 Türk Lirası TL ",
    "StrID": 24645,
    "FiyatListesiID": 306,
    "FiyatListesiKodu": "KOPYA0000000010",
    "FiyatListesiAdi": "HazırKapı (20210808) S",
    "StokID": 8147,
    "StokKodu": "HZRKP.BSLKS.064",
    "StokAdi": "HazırKapı BaşlıkKasaPervaz     4.1X15X134cm",
    "Durum": true,
    "TipID": 136001,
    "Nakliye": 0.0,
    "Diger": 0.0,
    "Fiyat": 45.75,
    "DovizID": 1,
    "DovizKodu": "TRY",
    "BirimID": 1,
    "BirimKodu": "AD"
  },
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Yeni bir fiyat listesi oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                       |
| --------- | ------- | ----------------------------------------------------------- |
| KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre      | Değer   | Tanım                                                                                                      |
| -------------- | ------- | ---------------------------------------------------------------------------------------------------------- |
| FiyatListesiID | Integer | Fiyat eklemek istediğiniz fiyat listesinin ID'sidir.                                                       |
| StokID         | Integer | Fiyat eklemek istediğiniz stooğun ID'sidir.                                                                |
| Fiyat          | Integer | Eklemek istediğiniz stoğa ait fiyattır.                                                                    |
| DovizID        | Integer | Eklediğiniz fiyatın döviz cinsini belirtir.                                                                |
| TipID          | Integer | Fiyat eklemek istediğiniz fiyat listesinin tipini belirtir. (alım fiyat listesi, satış fiyat listesi gibi) |

<aside class="warning">
Bir fiyat listesine aynı stok için birden fazla fiyat ekleyemezsiniz.
</aside>

## Fiyat Listesi Satir Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "StrID": 24645,
    "FiyatListesiID": 306,
    "StokID": 8147,
    "Fiyat": 45.75,
    "DovizID":1 ,
    "TipID": 136001
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    StrID: 24645,
    FiyatListesiID: 306,
    StokID: 8147,
    Fiyat: 45.75,
    DovizID: 1,
    TipID: 136001,
  }),
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"StrID\": 24645, \n    \"FiyatListesiID\": 306,\n    \"StokID\": 8147,\n    \"Fiyat\": 45.75,\n    \"DovizID\": 1,\n    \"TipID\": 136001  \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=1"

payload = "{\n    \"StrID\": 24645, \n    \"FiyatListesiID\": 306,\n    \"StokID\": 8147,\n    \"Fiyat\": 45.75,\n    \"DovizID\": 1,\n    \"TipID\": 136001  \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"StrID\": 24645, \n    \"FiyatListesiID\": 306,\n    \"StokID\": 8147,\n    \"Fiyat\": 45.75,\n    \"DovizID\": 1,\n    \"TipID\": 136001  \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "SirketKodu": "SRKT0",
    "SubeKodu": "TUM",
    "TarihBas": "2021-08-08T00:00:00",
    "TarihBit": "2021-09-30T00:00:00",
    "TipKodu": "Satis",
    "TipAdi": "Satis",
    "DovizAdi": "Türk Lirası TL",
    "BirimAdi": "Adet",
    "OnayDurum": 1,
    "OlsTar": "2021-08-17T10:55:10.87",
    "DgsTar": "2021-08-17T10:55:10.87",
    "OlsID": 2,
    "OlsKodu": "yonetici",
    "OlsAdi": "A Kullanicisii",
    "DgsID": 2,
    "DgsKodu": "yonetici",
    "DgsAdi": "A Kullanicisii",
    "EsnekAramaKisiti": "KOPYA0000000010 HazırKapı (20210808) S HazırKapı BaşlıkKasaPervaz     4.1X15X134cm 45.750000 Türk Lirası TL ",
    "StrID": 24645,
    "FiyatListesiID": 306,
    "FiyatListesiKodu": "KOPYA0000000010",
    "FiyatListesiAdi": "HazırKapı (20210808) S",
    "StokID": 8147,
    "StokKodu": "HZRKP.BSLKS.064",
    "StokAdi": "HazırKapı BaşlıkKasaPervaz     4.1X15X134cm",
    "Durum": true,
    "TipID": 136001,
    "Nakliye": 0.0,
    "Diger": 0.0,
    "Fiyat": 45.75,
    "DovizID": 1,
    "DovizKodu": "TRY",
    "BirimID": 1,
    "BirimKodu": "AD"
  },
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Yeni bir fiyat listesi oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=2`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                              |
| --------- | ------- | ------------------------------------------------------------------ |
| KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre      | Değer   | Tanım                                                    |
| -------------- | ------- | -------------------------------------------------------- |
| StrID          | Integer | Düzeltmek istediğiniz satırın ID'sidir.                  |
| FiyatListesiID | Integer | Düzeltmek istediğiniz satırın fiyat listesinin ID'sidir. |
| StokID         | Integer | Düzeltmek istediğiniz stoğun ID2sidir.                   |
| Fiyat          | Integer | Düzeltmek istediğiniz fiyattır.                          |
| DovizID        | Integer | Düzeltmek istediğiniz döviz ID'sidir.                    |

## Fiyat Listesi Satir Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "StrID":24645,
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({ StrID: 24645 }),
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"StrID\":24645,\n       \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=-1"

payload = "{\n    \"StrID\":24645,\n     \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"StrID\":24645,\n      \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": null,
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut fiyat listesini silmektedir

### HTTP Request

`POST https://erp.aaro.com.tr/api/FiyatListesiSatirlar/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                               |
| --------- | ------- | ------------------------------------------------------------------- |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de yeni DELETE(sil) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                            |
| --------- | ------- | -------------------------------- |
| StrID     | Integer | Silmek istediğiniz satırın ID'si |

# Müşteri(Cari) / Tedarikçi

| Parametre | Değer  | Tanım                             |
| --------- | ------ | --------------------------------- |
| TipID     | 102001 | Musteri tipi olduğunu belirtir    |
| TipID     | 102002 | Satici tipi olduğunu belirtir     |
| TipID     | 102003 | Karaliste tipi olduğunu belirtir  |
| TipID     | 102004 | Potansiyel tipi olduğunu belirtir |
| TipID     | 102005 | Personel tipi olduğunu belirtir   |
| TipID     | 102006 | Kamu tipi olduğunu belirtir       |
| TipID     | 102007 | Ortak tipi olduğunu belirtir      |

## Carileri Getir

```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/Cari' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var request = require("request");
var options = {
  method: "GET",
  url: "https://erp.aaro.com.tr/api/Cari?",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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
      "VergiDairesiAdi": "M.karagüzel ",
      "VergiDairesiKodu": "06270",
      "FiyatListesiCariGrupKodu": "Tml",
      "FiyatListesiCariGrupAdi": "Temel",
      "IlceAdi": "Altındağ",
      "IlAdi": "Ankara",
      "UlkeAdi": "Türkiye",
      "IlceID": 58,
      "IlID": 6,
      "UlkeID": 1,
      "Tel": "0539485339",
      "EMail": "",
      "Bakiye": 900.0,
      "BakiyeDvz": 0.0,
      "DovizID": 1,
      "DovizKodu": "TRY",
      "SubeKodu": "TUM",
      "SubeAdi": "Tüm Şubeler",
      "SirketKodu": "SRKT0",
      "SirketAdi": "Şirket 0",
      "EntegrasyonTanimKodu": "4920",
      "EntegrasyonTanimAdi": "GÜLANTİK MOBİLYA",
      "TipAdi": "Musteri",
      "TipKodu": null,
      "OnayDurum": 1,
      "OlsTar": "2016-10-10T08:52:18.873",
      "DgsTar": "2016-10-10T08:52:18.873",
      "OlsID": 10,
      "OlsKodu": "umak",
      "OlsAdi": "Personel 377",
      "DgsID": 10,
      "DgsKodu": "umak",
      "DgsAdi": "Personel 377",
      "Kod1Kodu": "CR",
      "Kod2Kodu": null,
      "Kod3Kodu": null,
      "Kod4Kodu": null,
      "Kod5Kodu": null,
      "Kod6Kodu": null,
      "Kod1Adi": "Cari",
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
      "EsnekAramaKisiti": "M07976 Aaro Yazılım ve Makina AŞ 4540499300 Cari          ",
      "CariID": 4920,
      "CariKodu": "M07976",
      "CariAdi": "Aaro Yazılım ve Makina AŞ",
      "VergiDairesiID": 633,
      "VergiNo": "4540499300",
      "DovizCalisabilir": false,
      "MuhtelifMi": false,
      "Vade": 0,
      "Iskonto": 0,
      "FiyatListesiCariGrupID": 1,
      "Seviye": 0,
      "PlasiyerID": null,
      "KartPuan": 0.754775,
      "SubeID": 0,
      "SirketID": 0,
      "Durum": true,
      "TipID": 102001,
      "EntegrasyonTanimID": 5030,
      "Kod1ID": 699,
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
    {},
    {}
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

| Parametre              | Değer    | Tanım                                                                                                                                            |
| ---------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| EsnekAramaKisiti       | String   | Dilediğiniz stringe göre listeleme yapabilirsiniz. Cari kodunda, cari adında, etiket adlarında, kod adlarında girilen string'e göre arama yapar. |
| SayfaSatirSayisi       | Integer  | Limitli sayıda cari getirmek için kullanılmaktadır.                                                                                              |
| SirketID               | Integer  | Belirli bir şirkete ait cari/cariler için girilmektedir.                                                                                         |
| SubeID                 | Integer  | Belirli bir şubeye ait cari/cariler için kullanılmaktadır.                                                                                       |
| TipID                  | Integer  | Carinin tipine göre çağırım için mevcuttur. (Tip ID listesinden bakınız)                                                                         |
| CariID                 | Integer  | Sadece belirli bir cariyi getirmek için eklenmektedir.                                                                                           |
| DovizID                | Integer  |                                                                                                                                                  |
| IlceID                 | Integer  |                                                                                                                                                  |
| IlID                   | Integer  |                                                                                                                                                  |
| UlkeID                 | Integer  |                                                                                                                                                  |
| PlasiyerID             | Integer  |                                                                                                                                                  |
| SablonID               | Integer  |                                                                                                                                                  |
| FiyatListesiCariGrupID | Integer  |                                                                                                                                                  |
| EntegrasyonTanimID     | Integer  |                                                                                                                                                  |
| VadeBas                | DateTime |                                                                                                                                                  |
| VadeBit                | DateTime |                                                                                                                                                  |
| Kod1ID                 | Integer  |                                                                                                                                                  |
| Kod2ID                 | Integer  |                                                                                                                                                  |
| Kod3ID                 | Integer  |                                                                                                                                                  |
| Kod4ID                 | Integer  |                                                                                                                                                  |
| Kod5ID                 | Integer  |                                                                                                                                                  |
| Kod6ID                 | Integer  |                                                                                                                                                  |
| Etiket1ID              | Integer  |                                                                                                                                                  |
| Etiket2ID              | Integer  |                                                                                                                                                  |
| Etiket3ID              | Integer  |                                                                                                                                                  |
| Etiket4ID              | Integer  |                                                                                                                                                  |
| Etiket5ID              | Integer  |                                                                                                                                                  |
| OlsID                  | Integer  | Oluşturan kişi ID'si                                                                                                                             |
| DgsID                  | Integer  | Değiştiren kişi ID'si                                                                                                                            |
| Durum                  | Boolean  | Aktif veya Pasif listeler için mevcuttur.                                                                                                        |
| OnayDurum              | Integer  | Carinin onayı var mı?                                                                                                                            |
| OlsTarBas              | DateTime |                                                                                                                                                  |
| OlsTarBit              | DateTime |                                                                                                                                                  |
| DgsTarBas              | DateTime |                                                                                                                                                  |
| DgsTarBit              | DateTime |                                                                                                                                                  |

<aside class="info">
</aside>

## Cari Oluştur

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "CariAdi": "Aaro Yazılım ve Makina AŞ",
    "CariKodu": "M07976",
    "TipID": 102001,
    "VergiDairesiID":633,
    "VergiNo": "4540499300",
    "Kod1ID": 699,
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
    "EtegrasyonTanimID": 152100,
    "EtegrasyonKodu": "4920",
    "EtegrasyonAdi": "GÜLANTİK MOBİLYA",
    "CariAlisDetayID": 6039,
    "CariAlisMuhasebeID": 11,
    "CariSatisDetayID": 6039,
    "CariSatisMuhasebeID": 11,
    "SirketID": 0,
    "SubeID": 0,
    "Durum": true,
    "Vade": 0,
    "gccVade": 0,
    "FiyatListesiCariGrupID": 1,
    "MuhtelifMi": false,
    "Notu": null,
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
    body: JSON.stringify({
    CariAdi: "Aaro Yazılım ve Makina AŞ",
    CariKodu: "M07976",
    TipID: 102001,
    VergiDairesiID:633,
    VergiNo: "4540499300",
    Kod1ID: 699,
    Kod2ID: null,
    Kod3ID: null,
    Kod4ID: null,
    Kod5ID: null,
    Kod6ID: null,
    Etiket1ID: null,
    Etiket2ID: null,
    Etiket3ID: null,
    Etiket4ID: null,
    Etiket5ID: null,
    EtegrasyonTanimID: 152100,
    EtegrasyonKodu: "4920",
    EtegrasyonAdi: "GÜLANTİK MOBİLYA",
    CariAlisDetayID: 6039,
    CariAlisMuhasebeID: 11,
    CariSatisDetayID: 6039,
    CariSatisMuhasebeID: 11,
    SirketID: 0,
    SubeID: 0,
    Durum: true,
    Vade: 0,
    gccVade: 0,
    FiyatListesiCariGrupID: 1,
    MuhtelifMi: false,
    Notu: null,
})

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
request.AddParameter("application/json", "{\n    \"CariAdi\": \"Aaro Yazılım ve Makina AŞ\", \n   \"CariKodu\": \"M07976\", \n   \"TipID\": 102001,\n    \"VergiDairesiID\":633,\n    \"VergiNo\": \"4540499300\",\n    \"Kod1ID\": 699,\n    \"Kod2ID\": null,\n    \"Kod3ID\": null,\n    \"Kod4ID\": null,\n    \"Kod5ID\": null,\n    \"Kod6ID\": null,\n    \"Etiket1ID\": null,\n    \"Etiket2ID\": null,\n    \"Etiket3ID\": null,\n    \"Etiket4ID\": null,\n    \"Etiket5ID\": null,\n    \"EtegrasyonTanimID\": 152100,\n    \"EtegrasyonKodu\": \"4920\", \n   \"EtegrasyonAdi\": \"GÜLANTİK MOBİLYA\", \n   \"CariAlisDetayID\": 6039,\n    \"CariAlisMuhasebeID\": 11,\n    \"CariSatisDetayID\": 6039,\n    \"CariSatisMuhasebeID\": 11,\n    \"SirketID\": 0,\n    \"SubeID\": 0,\n    \"Durum\": true,\n    \"Vade\": 0,\n    \"gccVade\": 0,\n    \"FiyatListesiCariGrupID\": 1,\n    \"MuhtelifMi\": false,\n    \"Notu\": null \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1"

payload = "{\n    \"CariAdi\": \"Aaro Yazılım ve Makina AŞ\", \n   \"CariKodu\": \"M07976\", \n   \"TipID\": 102001,\n    \"VergiDairesiID\":633,\n    \"VergiNo\": \"4540499300\",\n    \"Kod1ID\": 699,\n    \"Kod2ID\": null,\n    \"Kod3ID\": null,\n    \"Kod4ID\": null,\n    \"Kod5ID\": null,\n    \"Kod6ID\": null,\n    \"Etiket1ID\": null,\n    \"Etiket2ID\": null,\n    \"Etiket3ID\": null,\n    \"Etiket4ID\": null,\n    \"Etiket5ID\": null,\n    \"EtegrasyonTanimID\": 152100,\n    \"EtegrasyonKodu\": \"4920\", \n   \"EtegrasyonAdi\": \"GÜLANTİK MOBİLYA\", \n   \"CariAlisDetayID\": 6039,\n    \"CariAlisMuhasebeID\": 11,\n    \"CariSatisDetayID\": 6039,\n    \"CariSatisMuhasebeID\": 11,\n    \"SirketID\": 0,\n    \"SubeID\": 0,\n    \"Durum\": true,\n    \"Vade\": 0,\n    \"gccVade\": 0,\n    \"FiyatListesiCariGrupID\": 1,\n    \"MuhtelifMi\": false,\n    \"Notu\": null \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
.body("{\n    \"CariAdi\": \"Aaro Yazılım ve Makina AŞ\", \n   \"CariKodu\": \"M07976\", \n   \"TipID\": 102001,\n    \"VergiDairesiID\":633,\n    \"VergiNo\": \"4540499300\",\n    \"Kod1ID\": 699,\n    \"Kod2ID\": null,\n    \"Kod3ID\": null,\n    \"Kod4ID\": null,\n    \"Kod5ID\": null,\n    \"Kod6ID\": null,\n    \"Etiket1ID\": null,\n    \"Etiket2ID\": null,\n    \"Etiket3ID\": null,\n    \"Etiket4ID\": null,\n    \"Etiket5ID\": null,\n    \"EtegrasyonTanimID\": 152100,\n    \"EtegrasyonKodu\": \"4920\", \n   \"EtegrasyonAdi\": \"GÜLANTİK MOBİLYA\", \n   \"CariAlisDetayID\": 6039,\n    \"CariAlisMuhasebeID\": 11,\n    \"CariSatisDetayID\": 6039,\n    \"CariSatisMuhasebeID\": 11,\n    \"SirketID\": 0,\n    \"SubeID\": 0,\n    \"Durum\": true,\n    \"Vade\": 0,\n    \"gccVade\": 0,\n    \"FiyatListesiCariGrupID\": 1,\n    \"MuhtelifMi\": false,\n    \"Notu\": null \n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "VergiDairesiAdi": "M.karagüzel ",
    "VergiDairesiKodu": "06270",
    "FiyatListesiCariGrupKodu": null,
    "FiyatListesiCariGrupAdi": null,
    "IlceAdi": null,
    "IlAdi": null,
    "UlkeAdi": null,
    "IlceID": null,
    "IlID": null,
    "UlkeID": null,
    "Tel": null,
    "EMail": null,
    "Bakiye": 0.0,
    "BakiyeDvz": null,
    "DovizID": null,
    "DovizKodu": null,
    "SubeKodu": "TUM",
    "SubeAdi": "Tüm Şubeler",
    "SirketKodu": "SRKT0",
    "SirketAdi": "Şirket 0",
    "EntegrasyonTanimKodu": null,
    "EntegrasyonTanimAdi": null,
    "TipAdi": "Musteri",
    "TipKodu": null,
    "OnayDurum": 1,
    "OlsTar": "2021-08-17T13:12:41.977",
    "DgsTar": "2021-08-17T13:12:41.977",
    "OlsID": 2,
    "OlsKodu": "yonetici",
    "OlsAdi": "A Kullanicisii",
    "DgsID": 2,
    "DgsKodu": "yonetici",
    "DgsAdi": "A Kullanicisii",
    "Kod1Kodu": "CR",
    "Kod2Kodu": null,
    "Kod3Kodu": null,
    "Kod4Kodu": null,
    "Kod5Kodu": null,
    "Kod6Kodu": null,
    "Kod1Adi": "Cari",
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
    "EsnekAramaKisiti": "M07976 Aaro Yazılım ve Makina AŞ 4540499300 Cari          ",
    "CariID": 10058,
    "CariKodu": "M07976",
    "CariAdi": "Aaro Yazılım ve Makina AŞ",
    "VergiDairesiID": 633,
    "VergiNo": "4540499300",
    "DovizCalisabilir": false,
    "MuhtelifMi": false,
    "Vade": 0,
    "Iskonto": 0,
    "FiyatListesiCariGrupID": null,
    "Seviye": 0,
    "PlasiyerID": null,
    "KartPuan": 0.0,
    "SubeID": 0,
    "SirketID": 0,
    "Durum": false,
    "TipID": 102001,
    "EntegrasyonTanimID": null,
    "Kod1ID": 699,
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

Yeni bir cari oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                       |
| --------- | ------- | ----------------------------------------------------------- |
| KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre              | Değer   | Tanım                                                                                                                                                                           | Zorunlu Mu? | Örnek                       |
| ---------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | --------------------------- |
| CariAdi                | String  | Cariye vereceğiniz ad                                                                                                                                                           | Evet        | "Aaro Yazılım ve Makina AŞ" |
| CariKodu               | String  | Cariye vereceğiniz kod                                                                                                                                                          | Evet        | "M07976"                    |
| TipID                  | Integer | TipID tablosundan bakınız                                                                                                                                                       | Evet        | 102001                      |
| VergiDairesiID         | Integer | Oluşturduğunuz vergi dairesi ID'sidir                                                                                                                                           | Evet        | 633                         |
| VergiNo                | String  | Cariniin kayıtlı olduğu vergi numarası                                                                                                                                          | Evet        | "4540499300"                |
| Kod1ID                 | Integer | Carilerinizi kod ağacı yapısı oluşturarak raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan kodların ID'sini giriniz.                           | Opsiyonel   | 699                         |
| Kod2ID                 | Integer | Carilerinizi kod ağacı yapısı oluşturarak raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan kodların ID'sini giriniz. Kod1'i girmek zorunludur. | Opsiyonel   | null                        |
| Kod3ID                 | Integer | Carilerinizi kod ağacı yapısı oluşturarak raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan kodların ID'sini giriniz. Kod2'i girmek zorunludur. | Opsiyonel   | null                        |
| Kod4ID                 | Integer | Carilerinizi kod ağacı yapısı oluşturarak raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan kodların ID'sini giriniz. Kod3'i girmek zorunludur. | Opsiyonel   | null                        |
| Kod5ID                 | Integer | Carilerinizi kod ağacı yapısı oluşturarak raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan kodların ID'sini giriniz. Kod4'i girmek zorunludur. | Opsiyonel   | null                        |
| Kod6ID                 | Integer | Carilerinizi kod ağacı yapısı oluşturarak raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan kodların ID'sini giriniz. Kod5'i girmek zorunludur. | Opsiyonel   | null                        |
| Etiket1ID              | Integer | Carilerinizi eiketleyerek raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan etiketlerin ID'sini giriniz.                                        | Opsiyonel   | null                        |
| Etiket2ID              | Integer | Carilerinizi eiketleyerek raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan etiketlerin ID'sini giriniz.                                        | Opsiyonel   | null                        |
| Etiket3ID              | Integer | Carilerinizi eiketleyerek raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan etiketlerin ID'sini giriniz.                                        | Opsiyonel   | null                        |
| Etiket4ID              | Integer | Carilerinizi eiketleyerek raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan etiketlerin ID'sini giriniz.                                        | Opsiyonel   | null                        |
| Etiket5ID              | Integer | Carilerinizi eiketleyerek raporlarda ve liste aramalarında işinizi kolaylaştırabilirsiniz. Sistemde varolan etiketlerin ID'sini giriniz.                                        | Opsiyonel   | null                        |
| EntegrasyonTanimID     | Integer |                                                                                                                                                                                 | Opsiyonel   | null                        |
| EntegrasyonAdi         | String  | Cariniin kayıtlı olduğu vergi numarası                                                                                                                                          | Opsiyonel   | null                        |
| EntegrasyonKodu        | String  | Cariniin kayıtlı olduğu vergi numarası                                                                                                                                          | Opsiyonel   | null                        |
| CariAlisDetayID        | Integer |                                                                                                                                                                                 | Opsiyonel   | null                        |
| CariAlisMuhasebeID     | Integer |                                                                                                                                                                                 | Opsiyonel   | null                        |
| CariSatisDetayID       | Integer |                                                                                                                                                                                 | Opsiyonel   | null                        |
| CariSatisMuhasebeID    | Integer |                                                                                                                                                                                 | Opsiyonel   | null                        |
| SirketID               | Integer |                                                                                                                                                                                 | Opsiyonel   | 0                           |
| SubeID                 | Integer |                                                                                                                                                                                 | Opsiyonel   | 0                           |
| Durum                  | Boolean | Aktif ya da pasif olması için önemlidir                                                                                                                                         | Opsiyonel   | true                        |
| Vade                   | Integer |                                                                                                                                                                                 | Opsiyonel   | true                        |
| gccVade                | Integer |                                                                                                                                                                                 | Opsiyonel   | null                        |
| FiyatListesiCariGrupID | Integer |                                                                                                                                                                                 | Opsiyonel   | null                        |
| MuhtelifMi             | Boolean |                                                                                                                                                                                 | Opsiyonel   | false                       |
| Notu                   | String  |                                                                                                                                                                                 | Opsiyonel   | null                        |

<aside class="success">
Mevcut vergi dairelerini görmek için API dökümanından Vergi Dairesi kısmını inceleyiniz.
</aside>

<aside class="info">
Cari için adres bilgisi girmek isterseniz API dökümanından Müşteri/Satıcı(Cari) Adres kısmını inceleyiniz.
</aside>

<aside class="info">
Cari için ilgili bilgisi girmek isterseniz API dökümanından Müşteri/Satıcı(Cari) İlgili kısmını inceleyiniz.
</aside>

<aside class="info">
Cari için banka hesap bilgisi girmek isterseniz API dökümanından Müşteri/Satıcı(Cari) Banka Hesap kısmını inceleyiniz.
</aside>

## Cari Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "CariID": 10058,
    "CariAdi": "Aaro Yazılım ve Makina AŞ",
    "CariKodu": "M07976",
    "TipID": 102001,
    "VergiDairesiID":633,
    "VergiNo": "4540499300",
    "Kod1ID": 699,
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
    "EtegrasyonTanimID": 152100,
    "EtegrasyonKodu": "4920",
    "EtegrasyonAdi": "GÜLANTİK MOBİLYA",
    "CariAlisDetayID": 6039,
    "CariAlisMuhasebeID": 11,
    "CariSatisDetayID": 6039,
    "CariSatisMuhasebeID": 11,
    "SirketID": 0,
    "SubeID": 0,
    "Durum": true,
    "Vade": 0,
    "gccVade": 0,
    "FiyatListesiCariGrupID": 1,
    "MuhtelifMi": false,
    "Notu": null,
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    CariID: 10058,
    CariAdi: "Aaro Yazılım ve Makina AŞ",
    CariKodu: "M07976",
    TipID: 102001,
    VergiDairesiID: 633,
    VergiNo: "4540499300",
    Kod1ID: 699,
    Kod2ID: null,
    Kod3ID: null,
    Kod4ID: null,
    Kod5ID: null,
    Kod6ID: null,
    Etiket1ID: null,
    Etiket2ID: null,
    Etiket3ID: null,
    Etiket4ID: null,
    Etiket5ID: null,
    EtegrasyonTanimID: 152100,
    EtegrasyonKodu: "4920",
    EtegrasyonAdi: "GÜLANTİK MOBİLYA",
    CariAlisDetayID: 6039,
    CariAlisMuhasebeID: 11,
    CariSatisDetayID: 6039,
    CariSatisMuhasebeID: 11,
    SirketID: 0,
    SubeID: 0,
    Durum: true,
    Vade: 0,
    gccVade: 0,
    FiyatListesiCariGrupID: 1,
    MuhtelifMi: false,
    Notu: null,
  }),
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
request.AddParameter("application/json", "{\n    \"CariID\": 10058,\n    \"CariAdi\": \"Aaro Yazılım ve Makina AŞ\", \n   \"CariKodu\": \"M07976\", \n   \"TipID\": 102001,\n    \"VergiDairesiID\":633,\n    \"VergiNo\": \"4540499300\",\n    \"Kod1ID\": 699,\n    \"Kod2ID\": null,\n    \"Kod3ID\": null,\n    \"Kod4ID\": null,\n    \"Kod5ID\": null,\n    \"Kod6ID\": null,\n    \"Etiket1ID\": null,\n    \"Etiket2ID\": null,\n    \"Etiket3ID\": null,\n    \"Etiket4ID\": null,\n    \"Etiket5ID\": null,\n    \"EtegrasyonTanimID\": 152100,\n    \"EtegrasyonKodu\": \"4920\", \n   \"EtegrasyonAdi\": \"GÜLANTİK MOBİLYA\", \n   \"CariAlisDetayID\": 6039,\n    \"CariAlisMuhasebeID\": 11,\n    \"CariSatisDetayID\": 6039,\n    \"CariSatisMuhasebeID\": 11,\n    \"SirketID\": 0,\n    \"SubeID\": 0,\n    \"Durum\": true,\n    \"Vade\": 0,\n    \"gccVade\": 0,\n    \"FiyatListesiCariGrupID\": 1,\n    \"MuhtelifMi\": false,\n    \"Notu\": null \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2"

payload = "{\n    \"CariID\": 20,\n    \"CariID\": 10058,\n    \"CariAdi\": \"Aaro Yazılım ve Makina AŞ\", \n   \"CariKodu\": \"M07976\", \n   \"TipID\": 102001,\n    \"VergiDairesiID\":633,\n    \"VergiNo\": \"4540499300\",\n    \"Kod1ID\": 699,\n    \"Kod2ID\": null,\n    \"Kod3ID\": null,\n    \"Kod4ID\": null,\n    \"Kod5ID\": null,\n    \"Kod6ID\": null,\n    \"Etiket1ID\": null,\n    \"Etiket2ID\": null,\n    \"Etiket3ID\": null,\n    \"Etiket4ID\": null,\n    \"Etiket5ID\": null,\n    \"EtegrasyonTanimID\": 152100,\n    \"EtegrasyonKodu\": \"4920\", \n   \"EtegrasyonAdi\": \"GÜLANTİK MOBİLYA\", \n   \"CariAlisDetayID\": 6039,\n    \"CariAlisMuhasebeID\": 11,\n    \"CariSatisDetayID\": 6039,\n    \"CariSatisMuhasebeID\": 11,\n    \"SirketID\": 0,\n    \"SubeID\": 0,\n    \"Durum\": true,\n    \"Vade\": 0,\n    \"gccVade\": 0,\n    \"FiyatListesiCariGrupID\": 1,\n    \"MuhtelifMi\": false,\n    \"Notu\": null \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"CariID\": 20,\n    \"CariID\": 10058,\n    \"CariAdi\": \"Aaro Yazılım ve Makina AŞ\", \n   \"CariKodu\": \"M07976\", \n   \"TipID\": 102001,\n    \"VergiDairesiID\":633,\n    \"VergiNo\": \"4540499300\",\n    \"Kod1ID\": 699,\n    \"Kod2ID\": null,\n    \"Kod3ID\": null,\n    \"Kod4ID\": null,\n    \"Kod5ID\": null,\n    \"Kod6ID\": null,\n    \"Etiket1ID\": null,\n    \"Etiket2ID\": null,\n    \"Etiket3ID\": null,\n    \"Etiket4ID\": null,\n    \"Etiket5ID\": null,\n    \"EtegrasyonTanimID\": 152100,\n    \"EtegrasyonKodu\": \"4920\", \n   \"EtegrasyonAdi\": \"GÜLANTİK MOBİLYA\", \n   \"CariAlisDetayID\": 6039,\n    \"CariAlisMuhasebeID\": 11,\n    \"CariSatisDetayID\": 6039,\n    \"CariSatisMuhasebeID\": 11,\n    \"SirketID\": 0,\n    \"SubeID\": 0,\n    \"Durum\": true,\n    \"Vade\": 0,\n    \"gccVade\": 0,\n    \"FiyatListesiCariGrupID\": 1,\n    \"MuhtelifMi\": false,\n    \"Notu\": null \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "CariID": 10058,
    "CariAdi": "Aaro Yazılım ve Makina AŞ",
    "CariKodu": "M07976",
    "TipID": 102001,
    "VergiDairesiID": 633,
    "VergiNo": "4540499300",
    "Kod1ID": 699,
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
    "EtegrasyonTanimID": 152100,
    "EtegrasyonKodu": "4920",
    "EtegrasyonAdi": "GÜLANTİK MOBİLYA",
    "CariAlisDetayID": 6039,
    "CariAlisMuhasebeID": 11,
    "CariSatisDetayID": 6039,
    "CariSatisMuhasebeID": 11,
    "SirketID": 0,
    "SubeID": 0,
    "Durum": true,
    "Vade": 0,
    "gccVade": 0,
    "FiyatListesiCariGrupID": 1,
    "MuhtelifMi": false,
    "Notu": null
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

| Parametre | Değer   | Tanım                                                              |
| --------- | ------- | ------------------------------------------------------------------ |
| KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                            |
| --------- | ------- | -------------------------------- |
| CariID    | Integer | Cari ID'si girilmesi zorunludur. |

## Cari Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "CariID":10058,
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({ CariID: 10058 }),
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
request.AddParameter("application/json", "{\n    \"CariID\":10058,\n       \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1"

payload = "{\n    \"CariID\":10058,\n     \n}"
headers = {
response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"CariID\":10058,\n      \n}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": null,
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut cariyi silmektedir

### HTTP Request

`POST https://erp.aaro.com.tr/api/Cari/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                               |
| --------- | ------- | ------------------------------------------------------------------- |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de yeni DELETE(sil) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                         |
| --------- | ------- | ----------------------------- |
| CariID    | Integer | Silmek istediğiniz cari ID'si |

<aside class="warning">
Bu işlemin geri dönüşü yoktur. Silmeden önce bu carinin hareketler ve bankalarla ile ilişkisini kesmelisiniz.
</aside>

# Müşteri/Satıcı(Cari) Adres

## Cari Adresleri Getir

```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/CariBanka' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var request = require("request");
var options = {
  method: "GET",
  url: "https://erp.aaro.com.tr/api/CariBanka?",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/CariBanka?");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/CariBanka?"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/CariBanka")
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
      "CariAdi": "Aaro Yazılım ve Makina AŞ",
      "IlceAdi": "Altındağ",
      "IlAdi": "Ankara",
      "UlkeAdi": "Türkiye",
      "OnayDurum": 1,
      "OlsTar": "2016-10-10T08:53:22.537",
      "DgsTar": "2021-08-17T12:29:04.07",
      "OlsID": 10,
      "OlsKodu": "umak",
      "OlsAdi": "Personel 377",
      "DgsID": 2,
      "DgsKodu": "yonetici",
      "DgsAdi": "A Kullanicisii",
      "EsnekAramaKisiti": "ANKARA Deneme sok. Deneme Mah. No:5124     Altındağ Ankara Türkiye",
      "AdresID": 5124,
      "CariID": 4920,
      "CariKodu": "M07976",
      "AdresAdi": "ANKARA",
      "SokakAdi": "Deneme sok. Deneme Mah. No:5124",
      "BinaAdi": null,
      "BinaNo": null,
      "KapiNo": null,
      "PostaKodu": null,
      "Durum": true,
      "IlceID": 58,
      "Tel": "0539485339",
      "Tel2": null,
      "Tel3": null,
      "Fax": null,
      "Email": null,
      "Web": null,
      "Enlem": 0.0,
      "Boylam": 0.0,
      "Oncelik": true
    },
    {},
    {}
  ],
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Bütün cari listelerini ya da istenilen kısıttaki cariyi getirmektedir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/CariBanka?`

### Sorgu URL Parametreleri

| Parametre        | Değer    | Tanım                                                                                                                                                                               |
| ---------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| EsnekAramaKisiti | String   | Dilediğiniz stringe göre listeleme yapabilirsiniz. Adres adı, sokak adı, bina adı, bina no, kapı no, posta kodu, ilçe adı, il adı ve ülke adında girilen string'e göre arama yapar. |
| AdresID          | Integer  | Sadece belirli bir adresi getirir                                                                                                                                                   |
| CariID           | Integer  | Sadece belirli bir carinin adresini                                                                                                                                                 |
| IlceID           | Integer  |                                                                                                                                                                                     |
| OlsID            | Integer  | Oluşturan kişi ID'si                                                                                                                                                                |
| DgsID            | Integer  | Değiştiren kişi ID'si                                                                                                                                                               |
| Durum            | Boolean  | Aktif veya Pasif listeler için mevcuttur.                                                                                                                                           |
| OnayDurum        | Integer  | Carinin onayı var mı?                                                                                                                                                               |
| OlsTarBas        | DateTime |                                                                                                                                                                                     |
| OlsTarBit        | DateTime |                                                                                                                                                                                     |
| DgsTarBas        | DateTime |                                                                                                                                                                                     |
| DgsTarBit        | DateTime |                                                                                                                                                                                     |

## Cari Adres Oluştur

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "CariID": 4920,
    "AdresAdi": "ANKARA",
    "IlceID": 58,
    "SokakAdi":"Deneme sok. Deneme Mah. No:5124",
    "BinaAdi": null,
    "BinaNo": null,
    "KapiNo": null,
    "Tel": "05000000000",
    "Tel2": null,
    "Tel3": null,
    "Fax": null,
    "Email": null,
    "Web": null,
    "Durum": true,
    "Oncelik": false
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
    body: JSON.stringify({
    CariID: 4920,
    AdresAdi: "ANKARA",
    IlceID: 58,
    SokakAdi:"Deneme sok. Deneme Mah. No:5124",
    BinaAdi: null,
    BinaNo: null,
    KapiNo: null,
    Tel: "05000000000",
    Tel2: null,
    Tel3: null,
    Fax: null,
    Email: null,
    Web: null,
    Durum: true,
    Oncelik: false
})

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
request.AddParameter("application/json", "{\n  \"CariID\": 4920, \n   \"AdresAdi\": \"ANKARA\", \n  \"IlceID\": 58,\n   \"SokakAdi\":\"Deneme sok. Deneme Mah. No:5124\", \n  \"BinaAdi\": null,\n    \"BinaNo\": null,\n    \"KapiNo\": null,\n    \"Tel\": \"05000000000\", \n  \"Tel2\": null,\n    \"Tel3\": null,\n    \"Fax\": null,\n    \"Email\": null,\n    \"Web\": null,\n    \"Durum\": true,\n   \"Oncelik\": false   \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1"

payload = "{\n  \"CariID\": 4920,\n   \"AdresAdi\": \"ANKARA\", \n  \"IlceID\": 58,\n   \"SokakAdi\":\"Deneme sok. Deneme Mah. No:5124\", \n  \"BinaAdi\": null,\n    \"BinaNo\": null,\n    \"KapiNo\": null,\n    \"Tel\": \"05000000000\", \n  \"Tel2\": null,\n    \"Tel3\": null,\n    \"Fax\": null,\n    \"Email\": null,\n    \"Web\": null,\n    \"Durum\": true,\n   \"Oncelik\": false   \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
.body("{\n  \"CariID\": 4920,\n   \"AdresAdi\": \"ANKARA\", \n  \"IlceID\": 58,\n   \"SokakAdi\":\"Deneme sok. Deneme Mah. No:5124\", \n  \"BinaAdi\": null,\n    \"BinaNo\": null,\n    \"KapiNo\": null,\n    \"Tel\": \"05000000000\", \n  \"Tel2\": null,\n    \"Tel3\": null,\n    \"Fax\": null,\n    \"Email\": null,\n    \"Web\": null,\n    \"Durum\": true,\n   \"Oncelik\": false   \n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "CariAdi": "Aaro Yazılım ve Makina AŞ",
    "IlceAdi": "Altındağ",
    "IlAdi": "Ankara",
    "UlkeAdi": "Türkiye",
    "OnayDurum": 1,
    "OlsTar": "2021-08-17T14:35:02.84",
    "DgsTar": "2021-08-17T14:35:02.84",
    "OlsID": 2,
    "OlsKodu": "yonetici",
    "OlsAdi": "A Kullanicisii",
    "DgsID": 2,
    "DgsKodu": "yonetici",
    "DgsAdi": "A Kullanicisii",
    "EsnekAramaKisiti": "ANKARA Deneme sok. Deneme Mah. No:5124        Altındağ Ankara Türkiye",
    "AdresID": 8823,
    "CariID": 4920,
    "CariKodu": "M07976",
    "AdresAdi": "ANKARA",
    "SokakAdi": "Deneme sok. Deneme Mah. No:5124",
    "BinaAdi": "null",
    "BinaNo": "null",
    "KapiNo": "null",
    "PostaKodu": null,
    "Durum": true,
    "IlceID": 58,
    "Tel": "05000000000",
    "Tel2": "null",
    "Tel3": "null",
    "Fax": "null",
    "Email": "null",
    "Web": "null",
    "Enlem": 0.0,
    "Boylam": 0.0,
    "Oncelik": false
  },
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Yeni bir cari oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                       |
| --------- | ------- | ----------------------------------------------------------- |
| KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                                                                       | Zorunlu Mu? | Örnek                           |
| --------- | ------- | --------------------------------------------------------------------------- | ----------- | ------------------------------- |
| CariID    | Integer | Adres bilgisini yüklemek istediğiniz carinin ID'si.                         | Evet        | 4920                            |
| AdresAdi  | String  | Adrese vereceğiniz ad                                                       | Evet        | ANKARA                          |
| SokakAdi  | String  | Sokağa vereceğiniz ad                                                       | Evet        | Deneme sok. Deneme Mah. No:5124 |
| IlceID    | Integer | Adresin buunduğu ilçe                                                       | Evet        | 58                              |
| Tel       | String  | Adrese ait telefon.                                                         | Evet        | 05000000000                     |
| BinaAdi   | String  | Binaya vereceğiniz ad                                                       | Opsiyonel   | null                            |
| BinaNo    | String  | Binaya vereceğiniz no                                                       | Opsiyonel   | null                            |
| KapiNo    | String  | Kapıya vereceğiniz no                                                       | Opsiyonel   | null                            |
| Tel2      | String  | Adrese ait ikinici telefon.                                                 | Opsiyonel   | null                            |
| Tel3      | String  | Adrese ait üçüncü telefon.                                                  | Opsiyonel   | null                            |
| Fax       | String  | Adrese ait fax.                                                             | Opsiyonel   | null                            |
| Email     | String  | Adrese ait e-mail.                                                          | Opsiyonel   | null                            |
| Web       | String  | Adrese ait web.                                                             | Opsiyonel   | null                            |
| Durum     | Boolean | Aktiflik ve pasiflik durumunu belirler. true ise aktif, false ise pasiftir. | Opsiyonel   | true                            |

<aside class="success">
Aynı Cari için birden çok adres bilgisi girebilirsiniz.
</aside>

## Cari Adres Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "AdresID": 8823,
    "CariID": 4920,
    "AdresAdi": "ANKARA",
    "IlceID": 58,
    "SokakAdi":"Deneme sok. Deneme Mah. No:5124",
    "BinaAdi": null,
    "BinaNo": null,
    "KapiNo": null,
    "Tel": "05000000000",
    "Tel2": null,
    "Tel3": null,
    "Fax": null,
    "Email": null,
    "Web": null,
    "Durum": true,
    "Oncelik": false
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    AdresID: 8823,
    CariID: 4920,
    AdresAdi: "ANKARA",
    IlceID: 58,
    SokakAdi: "Deneme sok. Deneme Mah. No:5124",
    BinaAdi: null,
    BinaNo: null,
    KapiNo: null,
    Tel: "05000000000",
    Tel2: null,
    Tel3: null,
    Fax: null,
    Email: null,
    Web: null,
    Durum: true,
    Oncelik: false,
  }),
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
request.AddParameter("application/json", "{\n  \"AdresID\": 8823,\n  \"CariID\": 4920,\n   \"AdresAdi\": \"ANKARA\", \n  \"IlceID\": 58,\n   \"SokakAdi\":\"Deneme sok. Deneme Mah. No:5124\", \n  \"BinaAdi\": null,\n    \"BinaNo\": null,\n    \"KapiNo\": null,\n    \"Tel\": \"05000000000\", \n  \"Tel2\": null,\n    \"Tel3\": null,\n    \"Fax\": null,\n    \"Email\": null,\n    \"Web\": null,\n    \"Durum\": true,\n   \"Oncelik\": false   \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2"

payload = "{\n  \"AdresID\": 8823,\n  \"CariID\": 4920,\n   \"AdresAdi\": \"ANKARA\", \n  \"IlceID\": 58,\n   \"SokakAdi\":\"Deneme sok. Deneme Mah. No:5124\", \n  \"BinaAdi\": null,\n    \"BinaNo\": null,\n    \"KapiNo\": null,\n    \"Tel\": \"05000000000\", \n  \"Tel2\": null,\n    \"Tel3\": null,\n    \"Fax\": null,\n    \"Email\": null,\n    \"Web\": null,\n    \"Durum\": true,\n   \"Oncelik\": false   \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n  \"AdresID\": 8823,\n  \"CariID\": 4920,\n   \"AdresAdi\": \"ANKARA\", \n  \"IlceID\": 58,\n   \"SokakAdi\":\"Deneme sok. Deneme Mah. No:5124\", \n  \"BinaAdi\": null,\n    \"BinaNo\": null,\n    \"KapiNo\": null,\n    \"Tel\": \"05000000000\", \n  \"Tel2\": null,\n    \"Tel3\": null,\n    \"Fax\": null,\n    \"Email\": null,\n    \"Web\": null,\n    \"Durum\": true,\n   \"Oncelik\": false   \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "CariAdi": "Aaro Yazılım ve Makina AŞ",
    "IlceAdi": "Altındağ",
    "IlAdi": "Ankara",
    "UlkeAdi": "Türkiye",
    "OnayDurum": 1,
    "OlsTar": "2021-08-17T14:35:02.84",
    "DgsTar": "2021-08-17T14:35:02.84",
    "OlsID": 2,
    "OlsKodu": "yonetici",
    "OlsAdi": "A Kullanicisii",
    "DgsID": 2,
    "DgsKodu": "yonetici",
    "DgsAdi": "A Kullanicisii",
    "EsnekAramaKisiti": "ANKARA Deneme sok. Deneme Mah. No:5124        Altındağ Ankara Türkiye",
    "AdresID": 8823,
    "CariID": 4920,
    "CariKodu": "M07976",
    "AdresAdi": "ANKARA",
    "SokakAdi": "Deneme sok. Deneme Mah. No:5124",
    "BinaAdi": "null",
    "BinaNo": "null",
    "KapiNo": "null",
    "PostaKodu": null,
    "Durum": true,
    "IlceID": 58,
    "Tel": "05000000000",
    "Tel2": "null",
    "Tel3": "null",
    "Fax": "null",
    "Email": "null",
    "Web": "null",
    "Enlem": 0.0,
    "Boylam": 0.0,
    "Oncelik": false
  },
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut cari düzenlenmektedir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=2`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                              |
| --------- | ------- | ------------------------------------------------------------------ |
| KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                             |
| --------- | ------- | --------------------------------- |
| AdresID   | Integer | Adres ID'si girilmesi zorunludur. |

## Cari Adres Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "AdresID":10058,
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({ AdresID: 10058 }),
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"AdresID\":10058,\n       \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1"

payload = "{\n    \"AdresID\":10058,\n     \n}"
headers = {
response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"AdresID\":10058,\n      \n}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": null,
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut adresi silmektedir

### HTTP Request

`POST https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                               |
| --------- | ------- | ------------------------------------------------------------------- |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de yeni DELETE(sil) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                          |
| --------- | ------- | ------------------------------ |
| AdresID   | Integer | Silmek istediğiniz adres ID'si |

# Müşteri/Satıcı(Cari) İlgili

## Cari İlgilileri Getir

```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/CariBanka' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var request = require("request");
var options = {
  method: "GET",
  url: "https://erp.aaro.com.tr/api/CariBanka?",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/CariBanka?");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/CariBanka?"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/CariBanka")
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
      "CariKodu": "M07976",
      "CariAdi": "Aaro Yazılım ve Makina AŞ",
      "OnayDurum": 1,
      "OlsTar": "2021-08-17T12:19:55.323",
      "DgsTar": "2021-08-17T12:29:04.127",
      "OlsID": 2,
      "OlsKodu": "yonetici",
      "OlsAdi": "A Kullanicisii",
      "DgsID": 2,
      "DgsKodu": "yonetici",
      "DgsAdi": "A Kullanicisii",
      "EsnekAramaKisiti": "Yeni İlgili Aug 17 2021 12:00AM 0   True Onaylanmis True",
      "IlgiliID": 1552,
      "IlgiliAdi": "Yeni İlgili",
      "CariID": 4920,
      "Durum": true,
      "Tel": "0",
      "Fax": null,
      "Email": null,
      "Not1": null,
      "Not2": null,
      "Unvan": null,
      "Dogum": "2021-08-17T00:00:00",
      "Oncelik": true
    },
    {},
    {}
  ],
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Bütün iligli listelerini ya da istenilen kısıttaki ilgiliyi getirmektedir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/CariBanka?`

### Sorgu URL Parametreleri

| Parametre        | Değer   | Tanım                                                                                                                                        |
| ---------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| EsnekAramaKisiti | String  | Dilediğiniz stringe göre listeleme yapabilirsiniz. İlgili adı, doğum, telefon, ünvan, e-mail bilgilerinde girilen string'e göre arama yapar. |
| IlgiliID         | Integer | Sadece belirli bir iligliyi getirir                                                                                                          |
| CariID           | Integer | Sadece belirli bir carinin adresini                                                                                                          |
| Durum            | Boolean | Aktif veya Pasif listeler için mevcuttur.                                                                                                    |

## Cari İlgili Oluştur

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "CariID": 4920,
    "IlgiliAdi": "Yeni İlgili",
    "Tel": "05000000000",
    "Fax": null,
    "Email": null,
    "Not1": null,
    "Not2": null,
    "Unvan": null,
    "Dogum": null,
    "Durum": true,
    "Oncelik": false
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
    body: JSON.stringify({
    CariID: 4920,
    IlgiliAdi: "Yeni İlgili",
    Tel: "05000000000",
    Fax: null,
    Email: null,
    Not1: null,
    Not2: null,
    Unvan: null,
    Dogum: null,
    Durum: true,
    Oncelik: false
})

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
request.AddParameter("application/json", "{\n  \"CariID\": 4920,\n    \"IlgiliAdi\": \"Yeni İlgili\", \n   \"Tel\": \"05000000000\", \n   \"Fax\": null,\n    \"Email\": null,\n    \"Not1\": null,\n    \"Not2\": null,\n    \"Unvan\": null,\n    \"Dogum\": null,\n    \"Durum\": true, \n   \"Oncelik\": false   \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1"

payload = "{\n  \"CariID\": 4920,\n    \"IlgiliAdi\": \"Yeni İlgili\", \n   \"Tel\": \"05000000000\", \n   \"Fax\": null,\n    \"Email\": null,\n    \"Not1\": null,\n    \"Not2\": null,\n    \"Unvan\": null,\n    \"Dogum\": null,\n    \"Durum\": true, \n   \"Oncelik\": false   \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
.body("{\n  \"CariID\": 4920,\n    \"IlgiliAdi\": \"Yeni İlgili\", \n   \"Tel\": \"05000000000\", \n   \"Fax\": null,\n    \"Email\": null,\n    \"Not1\": null,\n    \"Not2\": null,\n    \"Unvan\": null,\n    \"Dogum\": null,\n    \"Durum\": true, \n   \"Oncelik\": false   \n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "CariKodu": "M07976",
    "CariAdi": "Aaro Yazılım ve Makina AŞ",
    "OnayDurum": 1,
    "OlsTar": "2021-08-17T15:10:10.857",
    "DgsTar": "2021-08-17T15:10:10.857",
    "OlsID": 2,
    "OlsKodu": "yonetici",
    "OlsAdi": "A Kullanicisii",
    "DgsID": 2,
    "DgsKodu": "yonetici",
    "DgsAdi": "A Kullanicisii",
    "EsnekAramaKisiti": "Yeni İlgili Jan  1 1990 12:00AM 05000000000   False Onaylanmis True",
    "IlgiliID": 1557,
    "IlgiliAdi": "Yeni İlgili",
    "CariID": 4920,
    "Durum": true,
    "Tel": "05000000000",
    "Fax": null,
    "Email": null,
    "Not1": null,
    "Not2": null,
    "Unvan": null,
    "Dogum": "1990-01-01T00:00:00",
    "Oncelik": false
  },
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Yeni bir cari oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                       |
| --------- | ------- | ----------------------------------------------------------- |
| KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer    | Tanım                                                                       | Zorunlu Mu? | Örnek       |
| --------- | -------- | --------------------------------------------------------------------------- | ----------- | ----------- |
| CariID    | Integer  | İlgili bilgisini yüklemek istediğiniz carinin ID'si.                        | Evet        | 4920        |
| IlgiliAdi | String   | İlgilinin adı                                                               | Evet        | Yni İlgili  |
| Dogum     | DateTime | İlgilinin doğm yılı                                                         | Evet        | 1990-01-01  |
| Tel       | String   | İlgiliye ait telefon.                                                       | Opsiyonel   | 05000000000 |
| Email     | String   | İlgiliye ait e-mail.                                                        | Opsiyonel   | null        |
| Fax       | String   | İlgiliye ait fax.                                                           | Opsiyonel   | null        |
| Not1      | String   | Binaya vereceğiniz ad                                                       | Opsiyonel   | null        |
| Not2      | String   | Binaya vereceğiniz no                                                       | Opsiyonel   | null        |
| KapiNo    | String   | Kapıya vereceğiniz no                                                       | Opsiyonel   | null        |
| Durum     | Boolean  | Aktiflik ve pasiflik durumunu belirler. true ise aktif, false ise pasiftir. | Opsiyonel   | true        |

<aside class="success">
Aynı Cari için birden çok ilgili bilgisi girebilirsiniz.
</aside>

## Cari İlgili Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "IlgiliID": 1557,
    "CariID": 4920,
    "IlgiliAdi": "Yeni İlgili",
    "Tel": "05000000000",
    "Fax": null,
    "Email": null,
    "Not1": null,
    "Not2": null,
    "Unvan": null,
    "Dogum": null,
    "Durum": true,
    "Oncelik": false
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    IlgiliID: 1557,
    CariID: 4920,
    IlgiliAdi: "Yeni İlgili",
    Tel: "05000000000",
    Fax: null,
    Email: null,
    Not1: null,
    Not2: null,
    Unvan: null,
    Dogum: null,
    Durum: true,
    Oncelik: false,
  }),
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
request.AddParameter("application/json", "{\n \"IlgiliID\": 1557,\n    \"CariID\": 4920,\n    \"IlgiliAdi\": \"Yeni İlgili\", \n   \"Tel\": \"05000000000\", \n   \"Fax\": null,\n    \"Email\": null,\n    \"Not1\": null,\n    \"Not2\": null,\n    \"Unvan\": null,\n    \"Dogum\": null,\n    \"Durum\": true,\n   \"Oncelik\": false \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2"

payload = "{\n \"IlgiliID\": 1557,\n    \"CariID\": 4920,\n    \"IlgiliAdi\": \"Yeni İlgili\", \n   \"Tel\": \"05000000000\", \n   \"Fax\": null,\n    \"Email\": null,\n    \"Not1\": null,\n    \"Not2\": null,\n    \"Unvan\": null,\n    \"Dogum\": null,\n    \"Durum\": true,\n   \"Oncelik\": false \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n \"IlgiliID\": 1557,\n    \"CariID\": 4920,\n    \"IlgiliAdi\": \"Yeni İlgili\", \n   \"Tel\": \"05000000000\", \n   \"Fax\": null,\n    \"Email\": null,\n    \"Not1\": null,\n    \"Not2\": null,\n    \"Unvan\": null,\n    \"Dogum\": null,\n    \"Durum\": true,\n   \"Oncelik\": false \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "CariKodu": "M07976",
    "CariAdi": "Aaro Yazılım ve Makina AŞ",
    "OnayDurum": 1,
    "OlsTar": "2021-08-17T15:10:10.857",
    "DgsTar": "2021-08-17T15:10:10.857",
    "OlsID": 2,
    "OlsKodu": "yonetici",
    "OlsAdi": "A Kullanicisii",
    "DgsID": 2,
    "DgsKodu": "yonetici",
    "DgsAdi": "A Kullanicisii",
    "EsnekAramaKisiti": "Yeni İlgili Jan  1 1990 12:00AM 05000000000   False Onaylanmis True",
    "IlgiliID": 1557,
    "IlgiliAdi": "Yeni İlgili",
    "CariID": 4920,
    "Durum": true,
    "Tel": "05000000000",
    "Fax": null,
    "Email": null,
    "Not1": null,
    "Not2": null,
    "Unvan": null,
    "Dogum": "1990-01-01T00:00:00",
    "Oncelik": false
  },
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut cari düzenlenmektedir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=2`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                              |
| --------- | ------- | ------------------------------------------------------------------ |
| KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                              |
| --------- | ------- | ---------------------------------- |
| IlgiliID  | Integer | İlgili ID'si girilmesi zorunludur. |

## Cari İlgili Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "IlgiliID":10058,
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({ IlgiliID: 10058 }),
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"IlgiliID\":10058,\n       \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1"

payload = "{\n    \"IlgiliID\":10058,\n     \n}"
headers = {
response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"IlgiliID\":10058,\n      \n}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": null,
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut ilgiliyi silmektedir

### HTTP Request

`POST https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                               |
| --------- | ------- | ------------------------------------------------------------------- |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de yeni DELETE(sil) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                           |
| --------- | ------- | ------------------------------- |
| IlgiliID  | Integer | Silmek istediğiniz Ilgili ID'si |

# Müşteri/Satıcı(Cari) Banka

## Cari Bankaları Getir

```shell


curl --location --request GET 'https://erp.aaro.com.tr/api/CariBanka' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var request = require("request");
var options = {
  method: "GET",
  url: "https://erp.aaro.com.tr/api/CariBanka?",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/CariBanka?");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/CariBanka?"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/CariBanka")
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
      "BankaSubeAdi": "Siteler/ankara                     ",
      "CariKodu": "M01254",
      "CariAdi": "ERKUR MOBİLYA LTD. ŞTİ.",
      "DovizKodu": null,
      "OnayDurum": 1,
      "OlsTar": "2016-01-01T14:49:46.363",
      "DgsTar": "2016-01-01T14:49:46.363",
      "OlsID": 0,
      "OlsKodu": null,
      "OlsAdi": null,
      "DgsID": 0,
      "DgsKodu": null,
      "DgsAdi": null,
      "EsnekAramaKisiti": null,
      "CariBankaID": 11,
      "CariID": 585,
      "BankaSubeID": 5737,
      "IbanNo": " 000000",
      "Durum": true,
      "Oncelik": false,
      "DovizID": null
    },
    {},
    {}
  ],
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Bütün iligli listelerini ya da istenilen kısıttaki ilgiliyi getirmektedir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/CariBanka?`

### Sorgu URL Parametreleri

| Parametre        | Değer   | Tanım                                                                                                                                                    |
| ---------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| EsnekAramaKisiti | String  | Dilediğiniz stringe göre listeleme yapabilirsiniz. Banka adı ve kodunda, doğum, iban numarısında, cari adı ve kodunda girilen string'e göre arama yapar. |
| BankaSubeID      | Integer | Sadece belirli bir bankayı getirir                                                                                                                       |
| CariID           | Integer | Sadece belirli bir carinin banka bilgilerini getirir                                                                                                     |
| IbanNo           | String  | Girilen iban numarasına sahip bankayı getirir                                                                                                            |
| Durum            | Boolean | Aktif veya Pasif listeler için mevcuttur.                                                                                                                |

## Cari Banka Oluştur

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
            "CariID": 4920,
            "IbanNo": "0",
            "BankaSubeID": 13000,
            "Durum": true,
            "Oncelik": true,
            "DovizID": null
}'

```

```javascript


var request = require('request');
var options = {
  'method': 'POST',
 'url': 'https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=1',
  'headers': {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer YOURTOKEN'
  },
    body: JSON.stringify({
    CariID: 4920,
            IbanNo: "0",
            BankaSubeID: 13000,
            Durum: true,
            Oncelik: true,
            DovizID: null
})
};

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});



```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n  \"CariID\": 4920,\n \"IbanNo\": \"0\",\n \"BankaSubeID\": 13000,\n \"Durum\": true,\n \"Oncelik\": true,\n \"DovizID\": null   \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=1"
payload = "{\n  \"CariID\": 4920,\n \"IbanNo\": \"0\",\n \"BankaSubeID\": 13000,\n \"Durum\": true,\n \"Oncelik\": true,\n \"DovizID\": null   \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
  .body("{\n  \"CariID\": 4920,\n \"IbanNo\": \"0\",\n \"BankaSubeID\": 13000,\n \"Durum\": true,\n \"Oncelik\": true,\n \"DovizID\": null   \n}")
  .asString();




```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "BankaSubeAdi": "Avcılar Şubesi",
    "CariKodu": "M07976",
    "CariAdi": "Aaro Yazılım ve Makina AŞ",
    "DovizKodu": null,
    "OnayDurum": 1,
    "OlsTar": "2021-08-17T15:58:54.647",
    "DgsTar": "2021-08-17T15:58:54.647",
    "OlsID": 2,
    "OlsKodu": null,
    "OlsAdi": null,
    "DgsID": 2,
    "DgsKodu": null,
    "DgsAdi": null,
    "EsnekAramaKisiti": null,
    "CariBankaID": 2512,
    "CariID": 4920,
    "BankaSubeID": 13000,
    "IbanNo": "0",
    "Durum": true,
    "Oncelik": true,
    "DovizID": null
  },
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Yeni bir cari banka oluşturmaktadır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                       |
| --------- | ------- | ----------------------------------------------------------- |
| KayitTipi | Integer | 1 KayitTipi=1 bütün API'de yeni kayıt anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre   | Değer   | Tanım                                                                       | Zorunlu Mu? | Örnek |
| ----------- | ------- | --------------------------------------------------------------------------- | ----------- | ----- |
| CariID      | Integer | Banka bilgisini yüklemek istediğiniz carinin ID'si.                         | Evet        | 4920  |
| IbanNo      | String  | İban numarası                                                               | Evet        | 0     |
| BankaSubeID | Integer | Sistem kayıtlı banka ID'si                                                  | Evet        | 13000 |
| DovizID     | Integer | Sistem kayıtlı banka ID'si                                                  | Opsiyonel   | null  |
| Durum       | Boolean | Aktiflik ve pasiflik durumunu belirler. true ise aktif, false ise pasiftir. | Opsiyonel   | true  |
| Oncelik     | Boolean | Aktiflik ve pasiflik durumunu belirler. true ise aktif, false ise pasiftir. | Opsiyonel   | true  |

<aside class="success">
Aynı Cari için birden çok banka bilgisi girebilirsiniz.
</aside>

## Cari Banka Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
  "CariBankaID":2512,
"CariID": 4920,
            "IbanNo": "0",
            "BankaSubeID": 13000,
            "Durum": true,
            "Oncelik": true,
            "DovizID": null
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({
    CariBankaID: 2512,
    CariID: 4920,
    IbanNo: "0",
    BankaSubeID: 13000,
    Durum: true,
    Oncelik: true,
    DovizID: null,
  }),
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
request.AddParameter("application/json", "{\n \"CariBankaID\":2512,\n   \"CariID\": 4920, \n   \"IbanNo\": \"0\", \n   \"BankaSubeID\": 13000, \n  \"Durum\": true, \n   \"Oncelik\": true, \n  \"DovizID\": null}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2"

payload = "{\n \"CariBankaID\":2512,\n   \"CariID\": 4920, \n   \"IbanNo\": \"0\", \n   \"BankaSubeID\": 13000, \n  \"Durum\": true, \n   \"Oncelik\": true, \n  \"DovizID\": null \n}"
headers = {


response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/Cari/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n \"CariBankaID\":2512,\n   \"CariID\": 4920, \n   \"IbanNo\": \"0\", \n   \"BankaSubeID\": 13000, \n  \"Durum\": true, \n   \"Oncelik\": true, \n  \"DovizID\": null \n}")
  .asString();



```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "BankaSubeAdi": "Avcılar Şubesi",
    "CariKodu": "M07976",
    "CariAdi": "Aaro Yazılım ve Makina AŞ",
    "DovizKodu": null,
    "OnayDurum": 1,
    "OlsTar": "2021-08-17T15:58:54.647",
    "DgsTar": "2021-08-17T15:58:54.647",
    "OlsID": 2,
    "OlsKodu": null,
    "OlsAdi": null,
    "DgsID": 2,
    "DgsKodu": null,
    "DgsAdi": null,
    "EsnekAramaKisiti": null,
    "CariBankaID": 2512,
    "CariID": 4920,
    "BankaSubeID": 13000,
    "IbanNo": "0",
    "Durum": true,
    "Oncelik": true,
    "DovizID": null
  },
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut cari düzenlenmektedir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=2`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                              |
| --------- | ------- | ------------------------------------------------------------------ |
| KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre   | Değer   | Tanım                              |
| ----------- | ------- | ---------------------------------- |
| CariBankaID | Integer | İlgili ID'si girilmesi zorunludur. |

## Cari Banka Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOURTOKEN' \
--data-raw '{
    "CariBankaID":10058,
}'

```

```javascript
var request = require("request");
var options = {
  method: "POST",
  url: "https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  body: JSON.stringify({ CariBankaID: 10058 }),
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```

```csharp

var client = new RestClient("https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer YOURTOKEN");
request.AddParameter("application/json", "{\n    \"CariBankaID\":10058,\n       \n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1"

payload = "{\n    \"CariBankaID\":10058,\n     \n}"
headers = {
response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .header("Authorization", "Bearer YOURTOKEN")
   .body("{\n    \"CariBankaID\":10058,\n      \n}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": null,
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

Mevcut cari bankayı silmektedir

### HTTP Request

`POST https://erp.aaro.com.tr/api/CariBanka/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                               |
| --------- | ------- | ------------------------------------------------------------------- |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de yeni DELETE(sil) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre   | Değer   | Tanım                          |
| ----------- | ------- | ------------------------------ |
| CariBankaID | Integer | Silmek istediğiniz banka ID'si |

# Kasa

## Kasaları Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Kasa' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var axios = require("axios");

var config = {
  method: "get",
  url: "https://erp.aaro.com.tr/api/Kasa",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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

| Parameter        | Değer   | Tanım                                                                                                                                            |
| ---------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| EsnekAramaKisiti | String  | Dilediğiniz stringe göre listeleme yapabilirsiniz. Kasa kodunda, kasa adında, etiket adlarında, kod adlarında girilen string'e göre arama yapar. |
| SiralamaKisiti   | String  | Gelen veriyi sıralamak için kullanılır. Durum, KasaID gibi kolon adları verilmelidir.                                                            |
| Sayfa            | Integer | Kaç sayfa kasa getirmek istediğinizi belirtir.                                                                                                   |
| SayfaSatirSayisi | Integer | Getirilen sayfadaki kasa limitini belirtir.                                                                                                      |
| KasaID           | Integer | Belirtilen ID ile kasa getirmektedir.                                                                                                            |
| Durum            | Boolean | True ise aktif, false ise pasif ürünleri getirmektedir.                                                                                          |
| TipID            | Integer | Kasanın tipine göre çağırım için mevcuttur. (Tip ID listesinden bakınız)                                                                         |
| SubeID           | Integer | Şube ID'sine göre ürünleri getirmektedir.                                                                                                        |
| SirketID         | Integer | Şirket ID'sine göre ürünleri getirmektedir.                                                                                                      |
| StokMuhasebeID   | Integer | Stok Muhasebe ID'sine göre ürünleri getirmektedir.                                                                                               |
| StokVergiID      | Integer | Stok Vergi ID'sine göre ürünleri getirmektedir.                                                                                                  |
| OlsID            | Integer | Stoğu Oluşturan kişi ID'sine göre ürünleri getirmektedir.                                                                                        |

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
var axios = require("axios");
var data = JSON.stringify({
  KasaID: -1,
  SubeID: 1,
  SirketID: 1,
  KasaKodu: "00000000000002",
  KasaAdi: "TL Kasa",
  KasaKisaKodu: "00000000000002",
  KasaKisaAdi: "TL Kasa",
  Durum: true,
  TipID: 103001,
  KasaMuhasebeID: 201,
  DovizID: 1,
  Seviye: 1,
  EntegrasyonTanimID: null,
  Kod1ID: null,
  Etiket1ID: null,
  SablonID: null,
});

var config = {
  method: "post",
  url: "https://localhost:44346/api/Kasa/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre      | Örnek Değer       | Tanım                                                                                                                                           | ZorunluMu |
| -------------- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| KasaID         | -1                | Eklenilen ürünün Kasa ID'sidir. -1 girildiği takdirde rastgele olarak ID atanmaktadır.                                                          | Evet      |
| SubeID         | 1                 | Kasanın bulunduğu şubenin ID'sidir.                                                                                                             | Evet      |
| SirketID       | 1                 | Kasanın ait olduğu şirketin ID'sidir.                                                                                                           | Evet      |
| KasaKodu       | "000000000000001" | Kasanın detaylı kodudur.                                                                                                                        | Evet      |
| KasaAdi        | "MERKEZ KASA"     | Kasanın gözüken adıdır.                                                                                                                         | Evet      |
| KasaKisaKodu   | "MerKas"          | Kasanın genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki kasaların aynı kisa koda sahip olması önemlidir. | Evet      |
| KasaKisaAdi    | "Merkez Kasa"     | Kasanın genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki kasaların aynı kisa ada sahip olması önemlidir.     | Evet      |
| Durum          | true              | Kasa kartının aktif veya pasif olduğunu belirlemektedir                                                                                         | Evet      |
| TipID          | 105001            | Aaro'da Kasa'yı işaret eder                                                                                                                     | Evet      |
| KasaMuhasebeID | 201               | Kasaların muhasebesebesi farklı şekilde işlenebilir. Kasa muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz                 | Evet      |
| DovizID        | 1                 | Kasanın döviz tipini belirtmeliniz. Örn TL olması için 1 olmalıdır.                                                                             | Evet      |
| Kod1ID         | null              | Kasa kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Merkez -> TL                                                                   | Opsiyonel |
| Etiket1ID      | null              | Kasa etiketleri icindir. Örnek: Merkez                                                                                                          | Opsiyonel |
| SablonID       | null              | Kasa ekleme şablonu varsa girilmelidir.                                                                                                         | Opsiyonel |

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
var axios = require("axios");
var data = JSON.stringify({
  KasaID: -1,
  SubeID: 1,
  SirketID: 1,
  KasaKodu: "00000000000002",
  KasaAdi: "TL Kasa",
  KasaKisaKodu: "00000000000002",
  KasaKisaAdi: "TL Kasa",
  Durum: true,
  TipID: 103001,
  KasaMuhasebeID: 201,
  DovizID: 1,
  Seviye: 1,
  EntegrasyonTanimID: null,
  Kod1ID: null,
  Etiket1ID: null,
  SablonID: null,
});

var config = {
  method: "post",
  url: "https://localhost:44346/api/Kasa/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

| Parametre | Değer   | Tanım                                                              |
| --------- | ------- | ------------------------------------------------------------------ |
| KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer   | Tanım                            |
| --------- | ------- | -------------------------------- |
| KasaID    | Integer | Kasa ID'si girilmesi zorunludur. |

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
var axios = require("axios");
var data = JSON.stringify({
  KasaID: -1,
  SubeID: 1,
  SirketID: 1,
  KasaKodu: "00000000000002",
  KasaAdi: "TL Kasa",
  KasaKisaKodu: "00000000000002",
  KasaKisaAdi: "TL Kasa",
  Durum: true,
  TipID: 103001,
  KasaMuhasebeID: 201,
  DovizID: 1,
  Seviye: 1,
  EntegrasyonTanimID: null,
  Kod1ID: null,
  Etiket1ID: null,
  SablonID: null,
});

var config = {
  method: "post",
  url: "https://localhost:44346/api/Kasa/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

| Parametre | Değer   | Tanım                                                       |
| --------- | ------- | ----------------------------------------------------------- |
| KayitTipi | Integer | -1 seçilerek mevcut kasanın silineceği bilgisi verilmiştir. |

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
var axios = require("axios");

var config = {
  method: "get",
  url: "https://erp.aaro.com.tr/api/BankaHesap",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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

| Parameter            | Değer   | Tanım                                                                                                                                              |
| -------------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| EsnekAramaKisiti     | String  | Dilediğiniz stringe göre listeleme yapabilirsiniz. Hesap kodunda, Hesap adında ,etiket adlarında, kod adlarında girilen string'e göre arama yapar. |
| SiralamaKisiti       | String  | Gelen veriyi sıralamak için kullanılır. Durum, BankaHesapID gibi kolon adları verilmelidir.                                                        |
| Sayfa                | Integer | Kaç sayfa BankaHesap getirmek istediğiniz                                                                                                          |
| SayfaSatirSayisi     | Integer | Getirilen sayfadaki BankaHesap limiti.                                                                                                             |
| BankaHesapID         | Integer | Belirtilen ID ile BankaHesap getirmektedir.                                                                                                        |
| Durum                | Boolean | True ise aktif, false ise pasif hesapları getirmektedir.                                                                                           |
| TipID                | Integer | BankaHesabın tipine göre çağırım için mevcuttur. (Tip ID listesinden bakınız)                                                                      |
| SubeID               | Integer | Şube ID'sine göre hesapları getirmektedir.                                                                                                         |
| SirketID             | Integer | Şirket ID'sine göre hesapları getirmektedir.                                                                                                       |
| BankaHesapMuhasebeID | Integer | BankaHesap Muhasebe ID'sine göre hesapları getirmektedir.                                                                                          |
| OlsID                | Integer | BankaHesab'ı Oluşturan kişi ID'sine göre hesapları getirmektedir.                                                                                  |

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
var axios = require("axios");
var data =
  '{"BankaHesapID": -1,"SubeID": 1,"SirketID": 1,"HesapKodu": "00000000005552","HesapAdi": "TL Hesap","HesapKisaKodu": "00000000000002","HesapKisaAdi": "TL Hesap","Durum": true,"TipID": 108001,"BankaHesapMuhasebeID": 201, "DovizID": 1,"BankaSubeID": 1,"CariBankaHesapID": 1,"IbanNo": "TR00000000000000000000000","Tel": "00000000000","Fax": "00000","Email": "demo@aaro.com.tr","Web": "www.aaro.com.tr","EntegrasyonTanimID": null,"Kod1ID": null,"Etiket1ID": null,"SablonID": null}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/BankaHesap/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

url = "https://localhost:44346/api/BankaHesap/post?KayitTipi=1"

payload="{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/BankaHesap/post?KayitTipi=1")
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
    "SablonID": null
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

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre            | Örnek Değer         | Tanım                                                                                                                                                 | ZorunluMu     |
| -------------------- | ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| BankaHesapID         | -1                  | Eklenilen ürünün BankaHesap ID'sidir. -1 girildiği takdirde rastgele olarak ID atanmaktadır.                                                          | Evet          |
| SubeID               | 1                   | BankaHesapnın bulunduğu şubenin ID'sidir.                                                                                                             | Evet          |
| SirketID             | 1                   | BankaHesapnın ait olduğu şirketin ID'sidir.                                                                                                           | Evet          |
| HesapKodu            | "000000000000001"   | BankaHesapnın detaylı kodudur.                                                                                                                        | Evet          |
| HesapAdi             | "MERKEZ Bankası"    | BankaHesapnın gözüken adıdır.                                                                                                                         | Evet          |
| HesapKisaKodu        | "MerBank"           | BankaHesapnın genel kodudur. Genel kod özel kodların parentı olarak düşünülebilir. Aynı kategorideki kasaların aynı kisa koda sahip olması önemlidir. | Evet          |
| HesapKisaAdi         | "Merkez BankaHesap" | BankaHesapnın genel adıdır. Genel ad özel adların parentı olarak düşünülebilir. Aynı kategorideki kasaların aynı kisa ada sahip olması önemlidir.     | Evet          |
| Durum                | true                | BankaHesap kartının aktif veya pasif olduğunu belirlemektedir                                                                                         | Evet          |
| TipID                | 108001              | BankaHesab'ınızın tipinin Pos veya Cari olduğunu belirler. Cari:108001, Pos:108004                                                                    | Evet          |
| BankaHesapMuhasebeID | 201                 | BankaHesapların muhasebesebesi farklı şekilde işlenebilir. BankaHesap muhasebe ID hakkında detaylı bilgi için muhasebe bölümünü inceleyiniz           | Evet          |
| DovizID              | 1                   | BankaHesabının döviz tipini belirtmelisiniz. Örn TL olması için 1 olmalıdır.                                                                          | Evet          |
| BankaSubeID          | 1                   | BankaHesap kartınızın hangi bankanın hangi şubesi olduğunu belirtir. Örn: YESILBAG - TÜRKİYE GARANTİ                                                  | Evet          |
| CariBankaHesapID     | 1                   | Eğer bu kartın tipi 'CARİDEN' farklı ise bu alt hesabın bağlı olduğu cari hesap girilmelidir.Ana hesabı belirtir. Örn:VAKIFB No:5 (300.5)             | Evet(Koşullu) |
| IbanNo               | null                | Bu banka hesabın iban numarasını belirtir.                                                                                                            | Opsiyonel     |
| Tel                  | null                | Bu banka hesaba ait telefon numarasını belirtir.                                                                                                      | Opsiyonel     |
| Email                | null                | Bu banka hesaba ait email adresini belirtir.                                                                                                          | Opsiyonel     |
| Fax                  | null                | Bu banka hesaba ait fax numarasını belirtir.                                                                                                          | Opsiyonel     |
| Web                  | null                | Bu banka hesaba ait internet adresini belirtir.                                                                                                       | Opsiyonel     |
| Kod1ID               | null                | BankaHesap kartlarını hiyerarşik gruplandırmak için kullanılır. Örnek: Ankara -> Ziraat                                                               | Opsiyonel     |
| Etiket1ID            | null                | BankaHesap etiketleri icindir. Örnek: Merkez                                                                                                          | Opsiyonel     |
| SablonID             | null                | BankaHesap ekleme şablonu varsa girilmelidir.                                                                                                         | Opsiyonel     |

<aside class="success">
BankaHesap oluştururken döküman altındaki örnek senaryo üzerinden gidebilirsiniz.
</aside>

## BankaHesap Düzenle

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/BankaHesap/post?KayitTipi=2' \
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
var axios = require("axios");
var data =
  '{"BankaHesapID": -1,"SubeID": 1,"SirketID": 1,"HesapKodu": "00000000005552","HesapAdi": "TL Hesap","HesapKisaKodu": "00000000000002","HesapKisaAdi": "TL Hesap","Durum": true,"TipID": 108001,"BankaHesapMuhasebeID": 201, "DovizID": 1,"BankaSubeID": 1,"CariBankaHesapID": 1,"IbanNo": "TR00000000000000000000000","Tel": "00000000000","Fax": "00000","Email": "demo@aaro.com.tr","Web": "www.aaro.com.tr","EntegrasyonTanimID": null,"Kod1ID": null,"Etiket1ID": null,"SablonID": null}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/BankaHesap/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/BankaHesap/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/BankaHesap/post?KayitTipi=2"

payload="{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/BankaHesap/post?KayitTipi=2")
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
    "SablonID": null
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

| Parametre | Değer   | Tanım                                                              |
| --------- | ------- | ------------------------------------------------------------------ |
| KayitTipi | Integer | 2 KayitTipi=2 bütün API'de yeni PUT(düzenle) anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre    | Değer   | Tanım                                  |
| ------------ | ------- | -------------------------------------- |
| BankaHesapID | Integer | BankaHesap ID'si girilmesi zorunludur. |

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
var axios = require("axios");
var data =
  '{"BankaHesapID": -1,"SubeID": 1,"SirketID": 1,"HesapKodu": "00000000005552","HesapAdi": "TL Hesap","HesapKisaKodu": "00000000000002","HesapKisaAdi": "TL Hesap","Durum": true,"TipID": 108001,"BankaHesapMuhasebeID": 201, "DovizID": 1,"BankaSubeID": 1,"CariBankaHesapID": 1,"IbanNo": "TR00000000000000000000000","Tel": "00000000000","Fax": "00000","Email": "demo@aaro.com.tr","Web": "www.aaro.com.tr","EntegrasyonTanimID": null,"Kod1ID": null,"Etiket1ID": null,"SablonID": null}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/BankaHesap/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

url = "https://localhost:44346/api/BankaHesap/post?KayitTipi=-1"

payload="{\r\n    \"BankaHesapID\": -1,\r\n    \"SubeID\": 1,\r\n    \"SirketID\": 1,\r\n    \"HesapKodu\": \"00000000005552\",\r\n    \"HesapAdi\": \"TL Hesap\",\r\n    \"HesapKisaKodu\": \"00000000000002\",\r\n    \"HesapKisaAdi\": \"TL Hesap\",\r\n    \"Durum\": true,\r\n    \"TipID\": 108001,\r\n    \"BankaHesapMuhasebeID\": 201,\r\n    \"DovizID\": 1,\r\n    \"BankaSubeID\": 1,\r\n    \"CariBankaHesapID\": 1,\r\n    \"IbanNo\": \"TR00000000000000000000000\",\r\n    \"Tel\": \"00000000000\",\r\n    \"Fax\": \"00000\",\r\n    \"Email\": \"demo@aaro.com.tr\",\r\n    \"Web\": \"www.aaro.com.tr\",\r\n    \"EntegrasyonTanimID\": null,\r\n    \"Kod1ID\": null,\r\n    \"Etiket1ID\": null,\r\n    \"SablonID\": null,\r\n}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/BankaHesap/post?KayitTipi=-1")
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
    "SablonID": null
  },
  "Mesajlar": {},
  "Sonuc": true,
  "MesajlarTumu": ""
}
```

BankaHesap kartı silmek içindir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/BankaHesap/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                  |
| --------- | ------- | ------------------------------------------------------ |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de sil anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre    | Değer   | Tanım                                  |
| ------------ | ------- | -------------------------------------- |
| BankaHesapID | Integer | BankaHesap ID'si girilmesi zorunludur. |

<aside class="warning">
BankaHesap düzenlemek ile silmek arasındaki fark KayitTipi=-1 olmasıdır. BankaHesap kartını silerken bağlı olduğu bütün hareketlerden de silmeniz gerekmektedir. Aksi takdirde hata dönecektir.
</aside>

# Dekont

## Başlık Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Dekont/Baslik?id=1' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var axios = require("axios");

var config = {
  method: "get",
  url: "https://erp.aaro.com.tr/api/Dekont/Baslik?id=1",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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

var client = new RestClient("https://erp.aaro.com.tr/api/Dekont/Baslik?id=1");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Dekont/Baslik?id=1"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/Dekont/Baslik?id=1")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 1,
    "Tarih": "2015-08-04T00:00:00",
    "BelgeNo": "A0000000001",
    "RefBelgeNo": "A0000000001",
    "Vade": "2015-08-04T00:00:00",
    "Tutar": 0.0,
    "YedekT": 0.0,
    "Seviye": 0,
    "Durum": true,
    "Aciklama": "",
    "OnayDurum": 1,
    "OlsTar": "2016-01-01T14:52:49.183",
    "DgsTar": "2016-01-01T14:52:49.183",
    "YedekN1": null,
    "YedekN2": null,
    "YedekN3": null,
    "YedekC1": null,
    "YedekC2": null,
    "YedekC3": null,
    "YedekI1": 1,
    "YedekI2": null,
    "YedekI3": null,
    "RefTeslimTarihi": "2015-09-06T00:00:00",
    "Kapali": true,
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
    "SubeID": 2,
    "SirketID": 1,
    "Sube2ID": null,
    "TipID": 10013,
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
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Bu uç nokta ile kayıtlı olan dekontun DekontID'si gönderilerek başlık bilgisi alınabilir. Aynı bilgiye Başlıkları Getir sekmesinde DekontID kısıtı gönderilerekte ulaşılabilir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Dekont/Baslik?id=1`

### URL Parametreleri

| Parameter | Değer   | Tanım                                           |
| --------- | ------- | ----------------------------------------------- |
| id        | Integer | Belirtilen ID ile Dekont Başlığı getirmektedir. |

## Başlıkları Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Dekont/Basliklar' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var axios = require("axios");

var config = {
  method: "get",
  url: "https://erp.aaro.com.tr/api/Dekont/Basliklar",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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

var client = new RestClient("https://erp.aaro.com.tr/api/Dekont/Basliklar");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Dekont/Basliklar"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/Dekont/Basliklar")
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
        "ToplamSatirSayisi": 131020,
        "ToplamSayfaSayisi": 13102,
        "OncekiSayfaVarMi": false,
        "SonrakiSayfaVarMi": true,
        "SayfaSatirSayisiAktifSayfada": 10
    },
    "Model": [
        {
            "DekontID": 1,
            "Tarih": "2015-08-04T00:00:00",
            "BelgeNo": "A0000000001",
            "RefBelgeNo": null,
            "Vade": "2015-08-04T00:00:00",
            "Tutar": 0.000000,
            "YedekT": 0.0,
            "Seviye": 0,
            "Durum": false,
            "Aciklama": "",
            "OnayDurum": 0,
            "OlsTar": "2016-01-01T14:52:49.183",
            "DgsTar": "2016-01-01T14:52:49.183",
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
            "OlsID": 0,
            "DgsID": 0,
            "RefSozlesmeID": null,
            "RefDepoID": null,
            "RefKDVDahil": null,
            "RefProjeID": null,
            "RefPlasiyerID": null,
            "RefDepo2ID": null,
            "RefIthalatIhracatID": null,
            "KartAdi": null
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

Bu uç nokta ile kayıtlı olan tüm dekontların filtrelenerek listesi alınabilir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Dekont/Basliklar?`

### URL Parametreleri

| Parameter        | Değer    | Tanım                                                                                                                                              |
| ---------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| EsnekAramaKisiti | String   | Dilediğiniz stringe göre listeleme yapabilirsiniz. Hesap kodunda, Hesap adında ,etiket adlarında, kod adlarında girilen string'e göre arama yapar. |
| SiralamaKisiti   | String   | Gelen veriyi sıralamak için kullanılır. Durum, BankaHesapID gibi kolon adları verilmelidir.                                                        |
| Sayfa            | Integer  | Kaç sayfa BankaHesap getirmek istediğiniz                                                                                                          |
| SayfaSatirSayisi | Integer  | Getirilen sayfadaki BankaHesap limiti.                                                                                                             |
| DekontID         | Integer  | Belirtilen ID ile Dekont Başlığı getirmektedir.                                                                                                    |
| TarihBas         | DateTime | Bu tarihten itibaren oluşturulmuş başlıkları getirir.                                                                                              |
| TarihBit         | DateTime | Bu tarihe kadar oluşturulmuş başlıkları getirir.                                                                                                   |
| Durum            | Boolean  | True ise aktif, false ise pasif hesapları getirmektedir.                                                                                           |
| TipID            | Integer  | Dekontun tipine göre başlıkları getirmenizi sağlar.Satış Faturası içi 10005. (Tip ID listesinden bakınız)                                          |
| SubeID           | Integer  | Şube ID'sine göre hesapları getirmektedir.                                                                                                         |
| SirketID         | Integer  | Şirket ID'sine göre hesapları getirmektedir.                                                                                                       |
| OlsID            | Integer  | BankaHesab'ı Oluşturan kişi ID'sine göre hesapları getirmektedir.                                                                                  |

## KalemTek Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Dekont/KalemTek?DekontID=1' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var axios = require("axios");

var config = {
  method: "get",
  url: "https://erp.aaro.com.tr/api/Dekont/KalemTek?DekontID=1",
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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

var client = new RestClient("https://erp.aaro.com.tr/api/Dekont/KalemTek?DekontID=1");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Dekont/KalemTek?DekontID=1"

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/Dekont/KalemTek?DekontID=1")
  .header("Authorization", "Bearer YOURTOKEN")
  .asString();


```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

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
      "BABSTutar": 0.0,
      "BeklenenTahsilatOdemeID": null
    },
    "SiparisStok": null,
    "HareketID": 1,
    "DekontID": 1,
    "SubeID": 2,
    "SirketID": 1,
    "TipID": 10013,
    "YevmiyeFisHareketID": null,
    "KartID": 3963,
    "Tarih": "2015-08-04T00:00:00",
    "Vade": "2015-08-04T00:00:00",
    "BA": "B",
    "Tutar": 61000.049976,
    "Miktar": 0.0,
    "DovizID": 1,
    "TutarDvz": 0.0,
    "SozlesmeID": null,
    "ProjeID": null,
    "PlasiyerID": null,
    "Durum": true,
    "Aciklama": null,
    "AciklamalarID": null,
    "OnayDurum": 1,
    "OlsID": 0,
    "OlsTar": "2016-01-01T14:52:53.35",
    "DgsID": 0,
    "DgsTar": "2016-01-01T14:52:53.35",
    "YedekD1": null,
    "YedekD2": null,
    "YedekD3": null,
    "YedekS1": null,
    "YedekS2": null,
    "YedekS3": null,
    "YedekI1": null,
    "YedekI2": null,
    "YedekI3": null,
    "KartAdi": "HÜRRİYET AYANA (ÖZYÖN MAKİNA)"
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Bu uç nokta ile kayıtlı olan Dekontun KalemTek bilgisi alınabilir. Nerdeyse tüm dekont tiplerinin vardır. Eğer yoksa boş sonuç döndürür.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Dekont/KalemTek?DekontID=1`

### URL Parametreleri

| Parameter | Değer   | Tanım                                           |
| --------- | ------- | ----------------------------------------------- |
| DekontID  | Integer | Belirtilen ID ile Dekont Başlığı getirmektedir. |

## Kalemler Getir

```shell

curl --location --request GET 'https://erp.aaro.com.tr/api/Dekont/Kalemler?DekontID=190322&HareketID=null&SiralamaKisiti="OlsTar"' \
--header 'Authorization: Bearer YOURTOKEN'

```

```javascript
var axios = require("axios");

var config = {
  method: "get",
  url: 'https://erp.aaro.com.tr/api/Dekont/Kalemler?DekontID=190322&HareketID=null&SiralamaKisiti="OlsTar"',
  headers: {
    Authorization: "Bearer YOURTOKEN",
  },
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

var client = new RestClient("https://erp.aaro.com.tr/api/Dekont/Kalemler?DekontID=190322&HareketID=null&SiralamaKisiti=\"OlsTar\"");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "Bearer YOURTOKEN");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);

```

```python

import requests

url = "https://erp.aaro.com.tr/api/Dekont/Kalemler?DekontID=190322&HareketID=null&SiralamaKisiti=\"OlsTar\""

payload = {}
headers = {
  'Authorization': 'Bearer YOURTOKEN'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.get("https://erp.aaro.com.tr/api/Dekont/Kalemler?DekontID=190322&HareketID=null&SiralamaKisiti=\"OlsTar\"")
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
    "ToplamSatirSayisi": 2,
    "ToplamSayfaSayisi": 1,
    "OncekiSayfaVarMi": false,
    "SonrakiSayfaVarMi": false,
    "SayfaSatirSayisiAktifSayfada": 2
  },
  "Model": [
    {
      "KalemTipi": 2,
      "Cari": null,
      "Stok": {
        "BrmFiyatN": 50.0,
        "BrmFiyatB": 10.4,
        "BrmFiyatTipi": 1,
        "VergiAltID": null,
        "VergiOran": null,
        "StokDetayID": null,
        "DepoID": 1,
        "CariID": 4920,
        "GelirGiderCariID": null,
        "DemirbasID": null,
        "GelirGiderDekontID": null,
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
        "IskontoTipi": true,
        "IskontoOrani": 0.0,
        "VadeIskontoOrani": 9.426919,
        "KullaniciIskontoOrani": 16.0,
        "TransferHareketID": null,
        "IthalatIhracatID": null,
        "UstHareketID": null,
        "GelenEFaturaStokBilgileri": null,
        "VergiDetaylari": [
          {
            "__TabloID": 3019,
            "__ProgramID": 3009,
            "VergiDetayID": 253175,
            "StokHareketID": 804203,
            "VergiID": 1,
            "VergiAltID": null,
            "VergiMuafiyetID": null,
            "Oran": 18.0,
            "Tutar": 9.0,
            "TutarDvz": 0.0,
            "Matrah": 50.0,
            "MatrahDvz": 0.0,
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
      "HareketID": 804203,
      "DekontID": 190322,
      "SubeID": 1,
      "SirketID": 1,
      "TipID": 10005,
      "YevmiyeFisHareketID": 730501,
      "KartID": 3658,
      "Tarih": "2021-09-22T00:00:00",
      "Vade": "2021-09-22T00:00:00",
      "BA": "A",
      "Tutar": 50.0,
      "Miktar": 1.0,
      "DovizID": 1,
      "TutarDvz": 0.0,
      "SozlesmeID": null,
      "ProjeID": null,
      "PlasiyerID": null,
      "Durum": true,
      "Aciklama": null,
      "AciklamalarID": null,
      "OnayDurum": 1,
      "OlsID": 2,
      "OlsTar": "2021-09-22T16:29:48.223",
      "DgsID": 2,
      "DgsTar": "2021-09-23T08:38:51.907",
      "YedekD1": null,
      "YedekD2": null,
      "YedekD3": null,
      "YedekS1": null,
      "YedekS2": null,
      "YedekS3": null,
      "YedekI1": null,
      "YedekI2": null,
      "YedekI3": null,
      "KartAdi": "Profil Seren Ahşap Ladin   3.0X4.3X300cm"
    },
    {
      "KalemTipi": 2,
      "Cari": null,
      "Stok": {
        "BrmFiyatN": 5.1,
        "BrmFiyatB": 5.1,
        "BrmFiyatTipi": 0,
        "VergiAltID": null,
        "VergiOran": null,
        "StokDetayID": null,
        "DepoID": 1,
        "CariID": 4920,
        "GelirGiderCariID": null,
        "DemirbasID": null,
        "GelirGiderDekontID": null,
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
        "IskontoOrani": 0.0,
        "VadeIskontoOrani": 0.0,
        "KullaniciIskontoOrani": 0.0,
        "TransferHareketID": null,
        "IthalatIhracatID": null,
        "UstHareketID": null,
        "GelenEFaturaStokBilgileri": null,
        "VergiDetaylari": [
          {
            "__TabloID": 3019,
            "__ProgramID": 3009,
            "VergiDetayID": 253176,
            "StokHareketID": 804206,
            "VergiID": 1,
            "VergiAltID": null,
            "VergiMuafiyetID": null,
            "Oran": 18.0,
            "Tutar": 0.918,
            "TutarDvz": 0.0,
            "Matrah": 5.1,
            "MatrahDvz": 0.0,
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
      "HareketID": 804206,
      "DekontID": 190322,
      "SubeID": 1,
      "SirketID": 1,
      "TipID": 10005,
      "YevmiyeFisHareketID": 730506,
      "KartID": 3919,
      "Tarih": "2021-09-22T00:00:00",
      "Vade": "2021-09-22T00:00:00",
      "BA": "A",
      "Tutar": 5.1,
      "Miktar": 1.0,
      "DovizID": 1,
      "TutarDvz": 0.0,
      "SozlesmeID": null,
      "ProjeID": null,
      "PlasiyerID": null,
      "Durum": true,
      "Aciklama": "",
      "AciklamalarID": null,
      "OnayDurum": 1,
      "OlsID": 2,
      "OlsTar": "2021-09-23T08:38:44.003",
      "DgsID": 2,
      "DgsTar": "2021-09-23T08:38:52.073",
      "YedekD1": null,
      "YedekD2": null,
      "YedekD3": null,
      "YedekS1": null,
      "YedekS2": null,
      "YedekS3": null,
      "YedekI1": null,
      "YedekI2": null,
      "YedekI3": null,
      "KartAdi": "Tutkal KG Üreformaldehid  1kg"
    }
  ],
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Bu uç nokta ile kayıtlı olan Dekontunkalemleri okunabilir.

### HTTP Request

`GET https://erp.aaro.com.tr/api/Dekont/Kalemler?DekontID=190322&HareketID=null&SiralamaKisiti="OlsTar"`

### URL Parametreleri

| Parameter      | Değer   | Tanım                                                                    | Zorunlu |
| -------------- | ------- | ------------------------------------------------------------------------ | ------- |
| DekontID       | Integer | Belirtilen ID ile Dekont Başlığı getirmektedir.                          | Evet    |
| HareketID      | Integer | Belirtilen ID ile dekonta ait kalem bilgisi getirilmektedir.             | Hayır   |
| SiralamaKisiti | string  | Belirtilen kısıta göre göre artan şekilde sıralayarak kalemleri getirir. | Hayır   |

## Dekont Baslik Yapisi (BaslikModel)

| Parameter                 | Değer                     | Tanım                                                      | Zorunlu |
| ------------------------- | ------------------------- | ---------------------------------------------------------- | ------- |
| DekontID                  | Integer                   | Belirtilen ID ile Dekont Başlığı getirmektedir.            | Evet    |
| TipID                     | HareketTurleriEnum        | Dekontun tipini ifade eder.                                | Evet    |
| Tarih                     | DateTime                  | Dekontun tarihini ifade eder.                              | Evet    |
| BelgeNo                   | String                    | Dekontun belge numarasıdır.                                | Evet    |
| Vade                      | DateTime                  | Dekontun tarihini ifade eder.                              | Evet    |
| Seviye                    | Byte                      |                                                            | Hayır   |
| Durum                     | Bool                      | Dekontun aktif pasif olamasını sağlar. Default değeri true | Hayır   |
| Kapali                    | Bool                      | Sipariş ve tekliflerde belgenin kapatılabilmesi için.      | Hayır   |
| Tutar                     | Decimal                   | Dekontun tutarıdır. bilgi amaçlıdır                        | Hayır   |
| KartAdi                   | String                    | Dekontun tutarıdır. bilgi amaçlıdır                        | Hayır   |
| eFatura                   | Bool                      |                                                            | Hayır   |
| eFaturaUUID               | String                    |                                                            | Hayır   |
| eFaturaProfilID           | Nullable eBelgeProfilleri |                                                            | Hayır   |
| eFaturaTipID              | Nullable eBelgeTipleri    |                                                            | Hayır   |
| eFaturaDurumID            | Nullable eFaturaDurumlari |                                                            | Hayır   |
| eFaturaTurID              | Nullable eBelgeTurleri    |                                                            | Hayır   |
| eArsivInternetSatisSablon | String                    |                                                            | Hayır   |
| MagazaSiparisID           | Nullable Integer          |                                                            | Hayır   |
| Etiket1ID                 | Nullable Integer          |                                                            | Hayır   |
| Etiket2ID                 | Nullable Integer          |                                                            | Hayır   |
| Etiket3ID                 | Nullable Integer          |                                                            | Hayır   |
| Etiket4ID                 | Nullable Integer          |                                                            | Hayır   |
| Etiket5ID                 | Nullable Integer          |                                                            | Hayır   |
| KopyaKaynakID             | Nullable Integer          |                                                            | Hayır   |
| RefSozlesmeID             | Nullable Integer          |                                                            | Hayır   |
| RefDepoID                 | Nullable Integer          |                                                            | Hayır   |
| RefProjeID                | Nullable Integer          |                                                            | Hayır   |
| RefPlasiyerID             | Nullable Integer          |                                                            | Hayır   |
| RefDepo2ID                | Nullable Integer          |                                                            | Hayır   |
| RefPlasiyerID             | Nullable Integer          |                                                            | Hayır   |
| RefIthalatIhracatID       | Nullable Integer          |                                                            | Hayır   |
| RefKDVDahil               | Nullable Bool             |                                                            | Hayır   |

```Json
{
    "DekontID": 0,
    "TipID": "SatisFaturasi",
    "SirketID": 0,
    "SubeID": 0,
    "BelgeNo": "000000000000001",
    "Tarih": "23.09.2021",
    "Vade": "23.09.2021",
    "Aciklama": "SatisFaturasi",
}
```

## Dekont Kalem Yapısı (KalemModel)

KalemModel genel olarak şu şekilde özetlenebilir.

Kalem Tipi,
Kalem Genel Bilgisi.
Kalem Tip Özel Bilgisi,

### Kalem Tipi

Kalem Tipi bilgisi dekont oluşturulurken eklenecek kalemlerin tipini belirtir. Zorunludur. Alabileceği değerler aşağıdaki tabloda belirtilmiştir.

| KalemTipi   | Değer            | Tanım                                                                                                                                        |
| ----------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Cari        | 1, "Cari"        | Nakit Tahsilat, Nakit Ödeme, Satış Faturası, Alış Faturası hareketlerinde KalemTek olarak gönderilir.                                        |
| Stok        | 2, "Stok"        | Alış Faturası, Satış Faturası gibi hareketlerde KalemCok bilgisi olarak gönderilir                                                           |
| Banka       | 3, "Banka"       | Havale/Eft Alma, Havale/Eft Gönderme, Pos Tahsilat gibi hareketlerde KalemCok bilgisi olarak gönderilir.                                     |
| Kasa        | 4, "Kasa"        | Nakit Tahsilat, Nakit Ödeme, Kasa Hesaplar Arası Transfer gibi hareketlerde KalemCok bilgisi olarak gönderilir.                              |
| CekSenet    | 5, "CekSenet"    | Çek/Senet Ciro Edildi/Verildi, Çek Bankaya Tahsile Verildi, Çek Bankadan Tahsil Edildi gibi hareketlerde KalemCok bilgisi olarak gönderilir. |
| SiparisCari | 6, "SiparisCari" | Alınan Sipariş, Verilen Sipariş gib hareketlerde KalemTek olarak gönderilir.                                                                 |
| SiparisStok | 7, "SiparisStok" | Alınan Sipariş, Verilen Sipariş gib hareketlerde KalemCok olarak gönderilir.                                                                 |

### Kalem Genel Bilgisi

KalemModel içindeki bu alanlar tüm kalem tiplerinde ortaktır. Hepsinde kullanılırlar.

| Parametre | Değer    | Tanım                                                                                                                                 | Zorunlu |
| --------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| KalemTipi | Integer  | Hareketi oluşturulacak Kalemin Tipini belirtir.                                                                                       | Evet    |
| DekontID  | Integer  | Dekontun ID'sidir.                                                                                                                    | Evet    |
| HareketID | Integer  | Dekonta eklenen kalemin HareketID'sidir. Dekonta kalem eklemek aynı zamanda Dekont'a ait hareket eklemek anlamına da gelir            | Evet    |
| SubeID    | Integer  | Hareketin ait olduğu şubenin ID'sidir.                                                                                                | Evet    |
| SirketID  | Integer  | Hareketin ait olduğu şirketin ID'sidir.                                                                                               | Evet    |
| KartID    | Integer  | Harekette kullanılan Stok, GelirGider, Kasa, Banka, Cari, CekSenet gibi kartların ID'sidir.                                           | Evet    |
| Miktar    | Decimal  | Eklenen kalemin miktarını belirtir. Kalemin birimi cinsinden belirtilmelidir. Kaç kilo, adet yada km gibi.                            | Evet    |
| Tutar     | Decimal  | Eklenen hareketin tutar bilgisidir.                                                                                                   | Evet    |
| DovizID   | Integer  | Harekete ait tutarın döviz cinsini belirtir. TL ise 1 girilmelidir. TL'den farklı bir döviz cinsi kullanılacaksa TutarDvz zorunludur. | Evet    |
| TutarDvz  | Decimal  | Eklenen hareketin belirtilen döviz cinsinden tutar bilgisidir                                                                         | Hayır   |
| Tarih     | DateTime | Harekete ait tarih bilgisidir.                                                                                                        | Hayır   |
| Vade      | DateTime | Harekete ait tarih bilgisidir.                                                                                                        | Hayır   |
| BA        | String   | Eklenen kalemin borc mu alacak mı olduğunu belirtir.                                                                                  | Hayır   |
| Aciklama  | String   | Kalem için eklenmek istenen açıklama bilgisidir. KalemTek içinde gönderilirse dekontun açıklaması olur                                | Hayır   |
| KartAdi   | String   | Bilgi amaçlıdır. Kalemde kullanılan kartın ID'sidir.                                                                                  | Hayır   |

```Json
{
    "KalemTipi": "SiparisStok",
    "DekontID": 190324,
    "KartID": "3658",
    "Miktar": 1,
    "Tutar": 50,
    "DovizID": 1,
    "TutarDvz": 0,
}
```

### Kalem Tip Özel Bilgisi

KalemModel içerisinde eklenen kalem tipi için ayrıca gerekecek alanların tanımlandığı modellerdir.

#### CariKalem

| Parametre               | Değer            | Tanım                                                                                       |
| ----------------------- | ---------------- | ------------------------------------------------------------------------------------------- |
| CariAdresID             | Nullable Integer | Cari'ye ait adres blgisini tutan Adres kartının ID'sidir.Sevk adresindeki bilgiler içindir. |
| CariDetayID             | Nullable Integer | Alt carilere bağlamak için.                                                                 |
| CariBankaID             | Nullable Integer | Havale vs gibi işlemler için.                                                               |
| BeklenenTahsilatOdemeID | Nullable Integer |                                                                                             |
| MuhtelifCariAdi         | string           |                                                                                             |
| MuhtelifVergiNo         | string           |                                                                                             |
| MuhtelifVergiDairesi    | string           |                                                                                             |
| MuhtelifAdres           | string           |                                                                                             |
| MuhtelifTel             | string           |                                                                                             |
| BABSTutar               | Decimal          |                                                                                             |

```Json
{
    "KalemTipi": "Cari",
    "DekontID": 190324,
    "KartID": "4920",
    "Miktar": 1,
    "Tutar": 50,
    "DovizID": 1,
    "TutarDvz": 0,
    "Cari" : {
     "CariAdresID": 1,
     "CariDetayID": null,
     "CariBankaID":null,
     "BeklenenTahsilatOdemeID":null,
     "MuhtelifCariAdi":"",
     "MuhtelifVergiNo":"",
     "MuhtelifVergiDairesi":"",
     "MuhtelifAdres":"",
     "MuhtelifTel":"",
     "BABSTutar:0
    }
}
```

#### StokKalem

| Parametre                 | Değer                                 | Tanım |
| ------------------------- | ------------------------------------- | ----- |
| BrmFiyatN                 | Decimal                               |       |
| BrmFiyatB                 | Decimal                               |       |
| BrmFiyatTipi              | BirimFiyatTipleri                     |       |
| DepoID                    | Integer                               |       |
| IskontoTipi               | Bool                                  |       |
| IskontoOrani              | Decimal                               |       |
| VadeIskontoOrani          | Decimal                               |       |
| KullaniciIskontoOrani     | Decimal                               |       |
| GelenEFaturaStokBilgileri | String                                |       |
| VergiDetaylari            | List of StokHareketleriVergiDetaylari |       |
| KullaniciIskontoOrani     | Decimal                               |       |
| OtomatikKalem             | Nullable Bool                         |       |
| KarmaKoliAdet             | Nullable Decimal                      |       |
| VergiOran                 | Nullable Decimal                      |       |
| VergiAltID                | Nullable Integer                      |       |
| StokDetayID               | Nullable Integer                      |       |
| CariID                    | Nullable Integer                      |       |
| GelirGiderCariID          | Nullable Integer                      |       |
| DemirbasID                | Nullable Integer                      |       |
| GelirGiderDekontID        | Nullable Integer                      |       |
| RafID                     | Nullable Integer                      |       |
| PromosyonID               | Nullable Integer                      |       |
| PaketID                   | Nullable Integer                      |       |
| KarmaKoliID               | Nullable Integer                      |       |
| IrsaliyeID                | Nullable Integer                      |       |
| YuklemeID                 | Nullable Integer                      |       |
| NakliyeID                 | Nullable Integer                      |       |
| SiparisHareketID          | Nullable Integer                      |       |
| DepoKabulID               | Nullable Integer                      |       |
| IthalatIhracatID          | Nullable Integer                      |       |
| TransferHareketID         | Nullable Integer                      |       |
| KarmaKoliID               | Nullable Integer                      |       |
| UstHareketID              | Nullable Integer                      |       |
| KarmaKoliID               | Nullable Integer                      |       |
| UstHareketID              | Nullable Integer                      |       |

```Json
{
    "KalemTipi": "Stok",
    "DekontID": 190324,
    "KartID": "3658",
    "Miktar": 1,
    "Tutar": 50,
    "DovizID": 1,
    "TutarDvz": 0,
    "Stok" : {
     "BrmFiyatN": 1,
     "BrmFiyatB": 21.12,
     "BrmFiyatTipi":12.21,
     "DepoID":1,
     "IskontoOrani":0,
     "VadeIskontoOrani":0,
     "KullaniciIskontoOrani":0,
     "GelenEFaturaStokBilgileri":0,
     "VergiDetaylari":[
                        {
                        ...
                        },
                        {
                        ...
                        }
                    ],
    }
}
```

#### BankaKalem

| Parametre       | Değer            | Tanım |
| --------------- | ---------------- | ----- |
| CekSenetID      | Nullable Integer |       |
| KrediPosKosulID | Nullable Integer |       |

```Json
{
    "KalemTipi": "Banka",
    "DekontID": 190324,
    "KartID": "4920",
    "Miktar": 1,
    "Tutar": 50,
    "DovizID": 1,
    "TutarDvz": 0,
    "Banka" : {
     "CekSenetID": null,
     "KrediPosKosulID":null,
    }
}
```

#### KasaKalem

| Parametre | Değer | Tanım |
| --------- | ----- | ----- |

```Json
{
    "KalemTipi": "Kasa",
    "DekontID": 190324,
    "KartID": "4920",
    "Miktar": 1,
    "Tutar": 50,
    "DovizID": 1,
    "TutarDvz": 0,
    "Kasa" : {
    }
}
```

#### CekSenetKalem

| Parametre         | Değer                         | Tanım |
| ----------------- | ----------------------------- | ----- |
| CekSenetID        | Integer                       |       |
| SubeID            | Integer                       |       |
| SirketID          | Integer                       |       |
| TipID             | TabloTipleri                  |       |
| Tutar             | Decimal                       |       |
| DovizID           | Integer                       |       |
| TutarDvz          | Decimal                       |       |
| Tarih             | DateTime                      |       |
| Vade              | DateTime                      |       |
| YedekT            | Decimal                       |       |
| YedekTD           | Decimal                       |       |
| AsilMi            | Bool                          |       |
| AsilVergiNumarasi | String                        |       |
| AsilAdi           | String                        |       |
| SeriNo            | String                        |       |
| KesideIlID        | Integer                       |       |
| SonDurumID        | CekSenetSonDurumlari          |       |
| MuhasebeBorcID    | Integer                       |       |
| MuhasebeAlacakID  | Integer                       |       |
| Aciklama          | String                        |       |
| DevirSonDurumID   | Nullable CekSenetSonDurumlari |       |
| CariID            | Nullable Integer              |       |
| BankaSubeID       | Nullable Integer              |       |
| ProjeID           | Nullable Integer              |       |
| PlasiyerID        | Nullable Integer              |       |
| SozlesmeID        | Nullable Integer              |       |
| PlasiyerID        | Nullable Integer              |       |
| YeriCariID        | Nullable Integer              |       |
| YeriBankaHesapID  | Nullable Integer              |       |

```Json
{
    "KalemTipi": "CekSenet",
    "DekontID": 190324,
    "KartID": "3658",
    "Miktar": 1,
    "Tutar": 50,
    "DovizID": 1,
    "TutarDvz": 0,
    "CekSenet" : {
     "CekSenetID": 1,
     "SubeID": 1,
     "SirketID": 1,
     "TipID": 1,
     "Tutar": 100,
     "DovizID": 1,
     "TutarDvz": 0,
     "Tarih": "2021.09.23",
     "Vade": "2021.09.23",
     "YedekT": 1,
     "YedekD": 1,
     "AsilMi": false,
     "AsilVergiNumarasi": "",
     "AsilAdi": "",
     "SeriNo": "",
     "KesideIlID": 1,
     "SonDurumID": 1,
     "MuhasebeBorcID": 1,
     "MuhasebeAlacakID": 1,
     "Aciklama": "",
    }
}
```

#### SiparisCariKalem

| Parametre               | Değer            | Tanım                                                                                       |
| ----------------------- | ---------------- | ------------------------------------------------------------------------------------------- |
| CariAdresID             | Nullable Integer | Cari'ye ait adres blgisini tutan Adres kartının ID'sidir.Sevk adresindeki bilgiler içindir. |
| CariDetayID             | Nullable Integer | Alt carilere bağlamak için.                                                                 |
| CariBankaID             | Nullable Integer | Havale vs gibi işlemler için.                                                               |
| BeklenenTahsilatOdemeID | Nullable Integer |                                                                                             |
| MuhtelifCariAdi         | string           |                                                                                             |
| MuhtelifVergiNo         | string           |                                                                                             |
| MuhtelifVergiDairesi    | string           |                                                                                             |
| MuhtelifAdres           | string           |                                                                                             |
| MuhtelifTel             | string           |                                                                                             |
| BABSTutar               | Decimal          |                                                                                             |

```Json
{
    "KalemTipi": "SiparisCari",
    "DekontID": 190324,
    "KartID": "4920",
    "Miktar": 1,
    "Tutar": 50,
    "DovizID": 1,
    "TutarDvz": 0,
    "SiparisCari" : {
     "CariAdresID": 1,
     "CariDetayID": null,
     "CariBankaID":null,
     "BeklenenTahsilatOdemeID":null,
     "MuhtelifCariAdi":"",
     "MuhtelifVergiNo":"",
     "MuhtelifVergiDairesi":"",
     "MuhtelifAdres":"",
     "MuhtelifTel":"",
     "BABSTutar:0
    }
}
```

#### SiparisStokKalem

| Parametre                 | Değer                                 | Tanım |
| ------------------------- | ------------------------------------- | ----- |
| BrmFiyatN                 | Decimal                               |       |
| BrmFiyatB                 | Decimal                               |       |
| BrmFiyatTipi              | BirimFiyatTipleri                     |       |
| DepoID                    | Integer                               |       |
| IskontoTipi               | Bool                                  |       |
| IskontoOrani              | Decimal                               |       |
| VadeIskontoOrani          | Decimal                               |       |
| KullaniciIskontoOrani     | Decimal                               |       |
| TeslimTarihi              | DateTime                              |       |
| Kapali                    | Bool                                  |       |
| GelenEFaturaStokBilgileri | String                                |       |
| VergiDetaylari            | List of StokHareketleriVergiDetaylari |       |
| KullaniciIskontoOrani     | Decimal                               |       |
| OtomatikKalem             | Nullable Bool                         |       |
| KarmaKoliAdet             | Nullable Decimal                      |       |
| VergiOran                 | Nullable Decimal                      |       |
| VergiAltID                | Nullable Integer                      |       |
| StokDetayID               | Nullable Integer                      |       |
| CariID                    | Nullable Integer                      |       |
| GelirGiderCariID          | Nullable Integer                      |       |
| DemirbasID                | Nullable Integer                      |       |
| GelirGiderDekontID        | Nullable Integer                      |       |
| RafID                     | Nullable Integer                      |       |
| PromosyonID               | Nullable Integer                      |       |
| PaketID                   | Nullable Integer                      |       |
| KarmaKoliID               | Nullable Integer                      |       |
| IrsaliyeID                | Nullable Integer                      |       |
| YuklemeID                 | Nullable Integer                      |       |
| NakliyeID                 | Nullable Integer                      |       |
| TeklifHareketID           | Nullable Integer                      |       |
| DepoKabulID               | Nullable Integer                      |       |
| IsEmriID                  | Nullable Integer                      |       |
| DepoKabulID               | Nullable Integer                      |       |
| KarsilamaSekli            | Nullable Integer                      |       |
| IthalatIhracatID          | Nullable Integer                      |       |
| UstHareketID              | Nullable Integer                      |       |

```Json
{
    "KalemTipi": "SiparisStok",
    "DekontID": 190324,
    "KartID": "3658",
    "Miktar": 1,
    "Tutar": 50,
    "DovizID": 1,
    "TutarDvz": 0,
    "SiparisStok" : {
     "BrmFiyatN": 1,
     "BrmFiyatB": 21.12,
     "BrmFiyatTipi":12.21,
     "DepoID":1,
     "IskontoOrani":0,
     "VadeIskontoOrani":0,
     "KullaniciIskontoOrani":0,
     "GelenEFaturaStokBilgileri":0,
     "TeslimTarihi": "2021.09.23",
     "Kapali": false,
     "VergiDetaylari":[
                        {
                        ...
                        },
                        {
                        ...
                        }
                    ],
    }
}
```

#### StokHareketleriVergiDetaylari

| Parametre       | Değer            | Tanım   |
| --------------- | ---------------- | ------- |
| VergiDetayID    | Integer          |         |
| StokHareketID   | Integer          |         |
| VergiID         | Integer          |         |
| VergiAltID      | Nullable Integer |         |
| VergiMuafiyetID | Nullable Integer |         |
| Oran            | Decimal          |         |
| Tutar           | Decimal          |         |
| DovizID         | Integer          |         |
| TutarDvz        | Decimal          |         |
| Matrah          | Decimal          |         |
| MatrahDvz       | Decimal          |         |
| BA              | String           | Zorunlu |

```Json
{
    "VergiDetayID": 1,
    "StokHareketID": 1,
    "VergiID": 1,
    "VergiAltID": null,
    "VergiMuafiyetID": null,
    "Oran": 18,
    "Tutar": 50,
    "DovizID": 1,
    "TutarDvz": 0,
    "Matrah": 0,
    "MatrahDvz": 0,
    "BA": "B",
}
```

## Dekont Kaydetme Süreci (Tek-Tek)

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"Baslik": BaslikModel,
        "KalemTek": KalemModel,
        "KalemCok": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel,
        "KalemCok": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Baslik/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
        "KalemCok": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Baslik/post?KayitTipi=1"

payload="{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
        "KalemCok": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .body("{
        \"Baslik\": \"BaslikModel\",
        \"KalemTek\": \"KalemModel\",
        \"KalemCok\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 190327,
    "Tarih": "2021-09-23T05:10:23.75Z",
    "BelgeNo": "1129529508609-DK",
    "RefBelgeNo": "1129529508609-DK",
    "Vade": "2021-09-23T05:10:23.75Z",
    "Tutar": 100.0,
    "YedekT": 0.0,
    "Seviye": 255,
    "Durum": true,
    "Aciklama": "Nakit Tahsilat TL Kasa",
    "OnayDurum": 1,
    "OlsTar": "2021-09-23T14:18:21.9577521+03:00",
    "DgsTar": "2021-09-23T14:18:22.5217204+03:00",
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
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Dekont eklendikten sonra oluşan Dekontun ID sini Baslik Modelin'de set ettikten sonra düzenle metodunu çağırınız. Böylelikle ilk eklemeden sonra Durumu false olan kalemlerin Durumu true olarak kaydedilir. Aksi takdirde dekont tamamlanmamış olur.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Değer       | Tanım                                                  | Zorunlu |
| --------- | ----------- | ------------------------------------------------------ | ------- |
| Baslik    | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |
| KalemTek  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |
| KalemCok  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |

<aside class="success">
Dekont(Tek-Tek) oluştururken Nakit Tahsilat örnek senaryo üzerinden gidebilirsiniz.
</aside>

## Dekont Kaydetme Süreci (Tek-Cok)

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"Baslik": BaslikModel,
        "KalemTek": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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
request.AddParameter("application/json", "{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kasa/post?KayitTipi=1"

payload="{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .body("{
        \"Baslik\": \"BaslikModel\",
        \"KalemTek\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 190328,
    "Tarih": "2021-09-23T05:10:23.75Z",
    "BelgeNo": "1129529508609-DK",
    "RefBelgeNo": "1129529508609-DK",
    "Vade": "2021-09-23T05:10:23.75Z",
    "Tutar": 0.0,
    "YedekT": 0.0,
    "Seviye": 255,
    "Durum": false,
    "Aciklama": null,
    "OnayDurum": 0,
    "OlsTar": "2021-09-23T14:34:36.0746084+03:00",
    "DgsTar": "2021-09-23T14:34:36.0746084+03:00",
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
    "RefDepoID": null,
    "RefKDVDahil": null,
    "RefProjeID": null,
    "RefPlasiyerID": null,
    "RefDepo2ID": null,
    "RefIthalatIhracatID": null,
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Yeni bir dekont(tek-cok) eklemek KayitTipi "Ekle" parametresi ile çağrılır. RequestBody içerisinde Başlık Bilgisi ve KalemTek Bilgisi gönderilir. Bu method başarılı olduktan sonra KalemCok bilgisi Kalem Methodu ile gönderilir. çağrılır.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Değer       | Tanım                                                  | Zorunlu |
| --------- | ----------- | ------------------------------------------------------ | ------- |
| Baslik    | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |
| KalemTek  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |

<aside class="info">
Dekont eklendikten sonra oluşan Dekontun ID sini Baslik Modelin'de set ettikten sonra KayitTipi URL parametresini "Duzenle" yaparak aynı metodu tekrar çağırınız. Böylelikle ilk eklemeden sonra Durumu false olan kalemlerin Durumu true olarak kaydedilir. Aksi takdirde dekont tamamlanmamış olur.
</aside>
<aside class="success">
Dekont (Tek-Cok) eklerken Alınan Sipariş örneği üzerinden gidebilirsiniz.
</aside>

## Dekont Kaydetme Süreci Kalem Metodu

Var olan Dekont'a kalem eklemek için bu metod çağrılır. RequestBody içerisinde KalemModel'i gönderirken "KalemCok" ismi yerine "Kalem" ismini kullanınız.

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--data-raw '{
        "Kalem": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Kalem": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Kalem/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Kalem/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Kalem": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kalem/post?KayitTipi=1"

payload="{
        "Kalem": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kalem/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .body("{
        \"Kalem\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "KalemTipi": 2,
    "Cari": null,
    "Stok": {
      "BrmFiyatN": 50.0,
      "BrmFiyatB": 10.4,
      "BrmFiyatTipi": 1,
      "VergiAltID": null,
      "VergiOran": null,
      "StokDetayID": null,
      "DepoID": 1,
      "CariID": 4920,
      "GelirGiderCariID": null,
      "DemirbasID": null,
      "GelirGiderDekontID": null,
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
      "IskontoTipi": true,
      "IskontoOrani": 0.0,
      "VadeIskontoOrani": 9.426919,
      "KullaniciIskontoOrani": 16.0,
      "TransferHareketID": null,
      "IthalatIhracatID": null,
      "UstHareketID": null,
      "GelenEFaturaStokBilgileri": null,
      "VergiDetaylari": [
        {
          "__TabloID": 3019,
          "__ProgramID": 3009,
          "VergiDetayID": 253179,
          "StokHareketID": 804211,
          "VergiID": 1,
          "VergiAltID": null,
          "VergiMuafiyetID": null,
          "Oran": 18.0,
          "Tutar": 9.0,
          "TutarDvz": 0.0,
          "Matrah": 50.0,
          "MatrahDvz": 0.0,
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
    "HareketID": 804211,
    "DekontID": 190328,
    "SubeID": 1,
    "SirketID": 1,
    "TipID": 10005,
    "YevmiyeFisHareketID": null,
    "KartID": 3658,
    "Tarih": "2021-09-23T05:10:23.75",
    "Vade": "2021-09-23T05:10:23.75",
    "BA": "A",
    "Tutar": 50.0,
    "Miktar": 1.0,
    "DovizID": 1,
    "TutarDvz": 0.0,
    "SozlesmeID": null,
    "ProjeID": null,
    "PlasiyerID": null,
    "Durum": false,
    "Aciklama": null,
    "AciklamalarID": null,
    "OnayDurum": 0,
    "OlsID": 2,
    "OlsTar": "2021-09-23T14:38:42.7905702+03:00",
    "DgsID": 2,
    "DgsTar": "2021-09-23T14:38:42.7905702+03:00",
    "YedekD1": null,
    "YedekD2": null,
    "YedekD3": null,
    "YedekS1": null,
    "YedekS2": null,
    "YedekS3": null,
    "YedekI1": null,
    "YedekI2": null,
    "YedekI3": null,
    "KartAdi": "Profil Seren Ahşap Ladin   3.0X4.3X300cm"
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Yeni bir dekont(tek-cok) eklemek KayitTipi "Ekle" parametresi ile çağrılır. RequestBody içerisinde Başlık Bilgisi ve KalemTek Bilgisi gönderilir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Değer      | Tanım                                                    | Zorunlu |
| --------- | ---------- | -------------------------------------------------------- | ------- |
| Kalem     | KalemModel | KalemCokModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |

<aside class="success">
Dekont eklendikten sonra oluşan Dekontun ID sini Baslik Modelin'de set ettikten sonra KayitTipi URL parametresini "Duzenle" yaparak aynı metodu tekrar çağırınız. Böylelikle ilk eklemeden sonra Durumu false olan kalemlerin Durumu true olarak kaydedilir. Aksi takdirde dekont tamamlanmamış olur.
</aside>

## Dekont Düzenle (Tek-Tek)

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"Baslik": BaslikModel,
        "KalemTek": KalemModel,
        "KalemCok": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel,
        "KalemCok": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Baslik/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
        "KalemCok": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Baslik/post?KayitTipi=2"

payload="{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
        "KalemCok": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .body("{
        \"Baslik\": \"BaslikModel\",
        \"KalemTek\": \"KalemModel\",
        \"KalemCok\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 190327,
    "Tarih": "2021-09-23T05:10:23.75Z",
    "BelgeNo": "1129529508609-DK",
    "RefBelgeNo": "1129529508609-DK",
    "Vade": "2021-09-23T05:10:23.75Z",
    "Tutar": 100.0,
    "YedekT": 0.0,
    "Seviye": 255,
    "Durum": true,
    "Aciklama": "Nakit Tahsilat TL Kasa",
    "OnayDurum": 1,
    "OlsTar": "2021-09-23T14:18:21.9577521+03:00",
    "DgsTar": "2021-09-23T14:18:22.5217204+03:00",
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
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Dekont eklendikten sonra oluşan Dekontun ID sini Baslik Modelin'de set ettikten sonra düzenle metodunu çağırınız. Böylelikle ilk eklemeden sonra Durumu false olan kalemlerin Durumu true olarak kaydedilir. Aksi takdirde dekont tamamlanmamış olur.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=2`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                      |
| --------- | ------- | ------------------------------------------ |
| KayitTipi | Integer | 2 Tüm API'de düzenle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Değer       | Tanım                                                  | Zorunlu |
| --------- | ----------- | ------------------------------------------------------ | ------- |
| Baslik    | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |
| KalemTek  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |
| KalemCok  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |

<aside class="success">
Dekont(Tek-Tek) düzenlerken örnek senaryo üzerinden gidebilirsiniz.
</aside>

## Dekont Düzenle (Tek-Cok)

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"Baslik": BaslikModel,
        "KalemTek": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/BankaHesap/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kasa/post?KayitTipi=2"

payload="{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .body("{
        \"Baslik\": \"BaslikModel\",
        \"KalemTek\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 190328,
    "Tarih": "2021-09-23T05:10:23.75Z",
    "BelgeNo": "1129529508609-DK",
    "RefBelgeNo": "1129529508609-DK",
    "Vade": "2021-09-23T05:10:23.75Z",
    "Tutar": 0.0,
    "YedekT": 0.0,
    "Seviye": 255,
    "Durum": false,
    "Aciklama": null,
    "OnayDurum": 0,
    "OlsTar": "2021-09-23T14:34:36.0746084+03:00",
    "DgsTar": "2021-09-23T14:34:36.0746084+03:00",
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
    "RefDepoID": null,
    "RefKDVDahil": null,
    "RefProjeID": null,
    "RefPlasiyerID": null,
    "RefDepo2ID": null,
    "RefIthalatIhracatID": null,
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Yeni bir dekont(tek-cok) eklemek için KayitTipi "Ekle" parametresi ile çağrılır. RequestBody içerisinde Başlık Bilgisi ve KalemTek Bilgisi gönderilir. Bu method başarılı olduktan sonra KalemCok bilgisi Kalem Methodu ile gönderilir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=2`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Değer       | Tanım                                                  | Zorunlu |
| --------- | ----------- | ------------------------------------------------------ | ------- |
| Baslik    | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |
| KalemTek  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |

<aside class="success">
Dekont (Tek-Cok) düzenlerken Alınan Sipariş örneği üzerinden gidebilirsiniz.
</aside>

## Dekont Düzenle Kalem Metodu

Var olan Dekont'a kalem eklemek için bu metod çağrılır. RequestBody içerisinde KalemModel'i gönderirken "KalemCok" ismi yerine "Kalem" ismini kullanınız.

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--data-raw '{
        "Kalem": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Kalem": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Kalem/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Kalem/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Kalem": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kalem/post?KayitTipi=2"

payload="{
        "Kalem": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kalem/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .body("{
        \"Kalem\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "KalemTipi": 2,
    "Cari": null,
    "Stok": {
      "BrmFiyatN": 50.0,
      "BrmFiyatB": 10.4,
      "BrmFiyatTipi": 1,
      "VergiAltID": null,
      "VergiOran": null,
      "StokDetayID": null,
      "DepoID": 1,
      "CariID": 4920,
      "GelirGiderCariID": null,
      "DemirbasID": null,
      "GelirGiderDekontID": null,
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
      "IskontoTipi": true,
      "IskontoOrani": 0.0,
      "VadeIskontoOrani": 9.426919,
      "KullaniciIskontoOrani": 16.0,
      "TransferHareketID": null,
      "IthalatIhracatID": null,
      "UstHareketID": null,
      "GelenEFaturaStokBilgileri": null,
      "VergiDetaylari": [
        {
          "__TabloID": 3019,
          "__ProgramID": 3009,
          "VergiDetayID": 253179,
          "StokHareketID": 804211,
          "VergiID": 1,
          "VergiAltID": null,
          "VergiMuafiyetID": null,
          "Oran": 18.0,
          "Tutar": 9.0,
          "TutarDvz": 0.0,
          "Matrah": 50.0,
          "MatrahDvz": 0.0,
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
    "HareketID": 804211,
    "DekontID": 190328,
    "SubeID": 1,
    "SirketID": 1,
    "TipID": 10005,
    "YevmiyeFisHareketID": null,
    "KartID": 3658,
    "Tarih": "2021-09-23T05:10:23.75",
    "Vade": "2021-09-23T05:10:23.75",
    "BA": "A",
    "Tutar": 50.0,
    "Miktar": 1.0,
    "DovizID": 1,
    "TutarDvz": 0.0,
    "SozlesmeID": null,
    "ProjeID": null,
    "PlasiyerID": null,
    "Durum": false,
    "Aciklama": null,
    "AciklamalarID": null,
    "OnayDurum": 0,
    "OlsID": 2,
    "OlsTar": "2021-09-23T14:38:42.7905702+03:00",
    "DgsID": 2,
    "DgsTar": "2021-09-23T14:38:42.7905702+03:00",
    "YedekD1": null,
    "YedekD2": null,
    "YedekD3": null,
    "YedekS1": null,
    "YedekS2": null,
    "YedekS3": null,
    "YedekI1": null,
    "YedekI2": null,
    "YedekI3": null,
    "KartAdi": "Profil Seren Ahşap Ladin   3.0X4.3X300cm"
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Yeni bir dekont(tek-cok) eklemek KayitTipi "Ekle" parametresi ile çağrılır. RequestBody içerisinde Başlık Bilgisi ve KalemTek Bilgisi gönderilir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=2`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

### Sorgu Body JSON açıklaması

| Parametre | Değer      | Tanım                                                    | Zorunlu |
| --------- | ---------- | -------------------------------------------------------- | ------- |
| Kalem     | KalemModel | KalemCokModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |

## Dekont Baslik Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"Baslik": {
        "DekontID" : 190329
    }
}'

```

```javascript
var axios = require("axios");
var data =
  '{
    "Baslik": {
        "DekontID" : 190329
    }
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Baslik/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
"Baslik": {
        "DekontID" : 190329
    }
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Baslik/post?KayitTipi=-1"

payload="{
"Baslik": {
        "DekontID" : 190329
    }
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .body("{
"Baslik": {
        "DekontID" : 190329
    }
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 0,
    "Tarih": "0001-01-01T00:00:00",
    "BelgeNo": null,
    "RefBelgeNo": null,
    "Vade": "0001-01-01T00:00:00",
    "Tutar": 0.0,
    "YedekT": 0.0,
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
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Dekont silmek içindir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                  |
| --------- | ------- | ------------------------------------------------------ |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de sil anlamına gelmektedir. |

### Sorgu Body Parametreleri

| Parametre | Değer       | Tanım                                                       |
| --------- | ----------- | ----------------------------------------------------------- |
| Baslik    | BaslikModel | BaslikModel içinde sadece DekontID'yi göndermek yeterlidir. |

## Dekont Kalem Sil

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--data-raw '{
    	"Kalem": {
        "KalemTipi": "Stok",
        "DekontID": "{{dekontID}}",
        "HareketID": 804227
    }
}'

```

```javascript
var axios = require("axios");
var data =
  '{
    "Baslik": {
        "DekontID" : 190329
    }
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Kalem/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Kalem/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
"Baslik": {
        "DekontID" : 190329
    }
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kalem/post?KayitTipi=-1"

payload="{
"Baslik": {
        "DekontID" : 190329
    }
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kalem/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .body("{
"Baslik": {
        "DekontID" : 190329
    }
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 0,
    "Tarih": "0001-01-01T00:00:00",
    "BelgeNo": null,
    "RefBelgeNo": null,
    "Vade": "0001-01-01T00:00:00",
    "Tutar": 0.0,
    "YedekT": 0.0,
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
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Dekont silmek içindir.

### HTTP Request

`POST https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=-1`

### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                  |
| --------- | ------- | ------------------------------------------------------ |
| KayitTipi | Integer | -1 KayitTipi=-1 bütün API'de sil anlamına gelmektedir. |

### Sorgu Body Parametreleri

## Nakit Tahsilat Oluşturma-Düzenleme-Silme (Tek-Tek)

Bu başık altında Nakit Tahsilat hareketinin kaydetme, düzeltme ve silme süreçlerini göreceksiniz. Bunun için öncelikle BaslikModel, KalemTekModel ve KalemCokModel yapılarımızı oluşturalım.

### Nakit Tahsilat Kaydetme

Bu başık altında Nakit Tahsilat hareketinin kaydetme sürecini göreceksiniz. Bunun için öncelikle BaslikModel, KalemTekModel ve KalemCokModel yapılarımızı oluşturalım.

#### BaslikModel

Farklı bir Dekont(Tek-Tek) kaydı oluşturmak istediğinzde örneğin Nakit Ödeme hareketi oluşturmak istediğinizde, BaslikModel'in içinde yer alan TipID parametresini "NakitOdeme" olarak değiştirmeniz yeterli olacaktır.

| Parametre | Tip                | Değer                        | Tanım                                                                               | Zorunlu |
| --------- | ------------------ | ---------------------------- | ----------------------------------------------------------------------------------- | ------- |
| TipID     | HareketTurleriEnum | NakitTahsilat                | Dekontun hareket türünü belirler.                                                   | Evet    |
| SirketID  | Integer            | 1                            | Hareketin hangi şirkete açılacağını belirler                                        | Evet    |
| SubeID    | Integer            | 1                            | Hareketin hangi şubeye açılacağını belirler                                         | Evet    |
| BelgeNo   | String             | 2822429117384-NT             | Dekontun belge numarasıdır. Uniqe olmak zorundadır.                                 | Evet    |
| Tarih     | DateTime           | 24.09.2021                   | Dekont tarihidir.                                                                   | Evet    |
| Vade      | DateTime           | 24.09.2021                   | Deokntun vadesidir. Verilmediği takdirde dekontun tarihi ile aynı değeri alacaktır. | Hayır   |
| Aciklama  | String             | Nakit Tahsilat Başlık Modeli | Dekont'un başlığına ait açıklamadır.                                                | Hayır   |

```Json
"Baslik": {
    "TipID": "NakitTahsilat",
    "SirketID": 1,
    "SubeID": 1,
    "BelgeNo": "2822429117384-NT",
    "Tarih": "24.09.2021",
    "Vade": "24.09.2021",
    "Aciklama": "Nakit Tahsilat Başlık Modeli",
}
```

<aside class="info">
Yukarıdaki bilgiler Dekont Başlığı oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz BaslikModel'ine bakabilirsiniz.
</aside>

#### KalemTekModel

| Parametre | Tip          | Değer | Tanım                                                                                                                                                      | Zorunlu |
| --------- | ------------ | ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| KalemTipi | KalemTipleri | Kasa  | Nakit Tahsilat hareketi Kasa üzerinden yapıldığı için KalemTek bilgisinin KalemTipi parametresi Kasa olmalıdır.                                            | Evet    |
| KartID    | Integer      | 1     | Aaro'da tanımlamış olduğunuz kasa kartının ID'sidir.                                                                                                       | Evet    |
| Tutar     | Decimal      | 1     | Hareketin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. KalemCok bilgisindeki değer ile aynı olmalıdır.                                         | Evet    |
| DovizID   | Integer      | 1     | DovizID hareketin döviz cinsini belirler. KalemCok bilgisindeki değer ile aynı olmalıdır.                                                                  | Evet    |
| TutarDvz  | Decimal      | 0     | Hareketin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. KalemCok bilgisindeki değer ile aynı olmalıdır. | Evet    |

```Json
"KalemTek": {
        "KalemTipi" : "Kasa",
        "KartID" : 1,
        "Tutar" : 100,
        "DovizID":  1,
        "TutarDvz":0
}
```

<aside class="info">
Yukarıdaki bilgiler Dekont KalemTek oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.
</aside>

#### KalemCokModel

| Parametre | Tip          | Değer | Tanım                                                                                                                                                      | Zorunlu |
| --------- | ------------ | ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| KalemTipi | KalemTipleri | Cari  | Nakit Tahsilat hareketinin diğer tarafı Cari olduğu için KalemTek bilgisinin KalemTipi parametresi Cari olmalıdır.                                         | Evet    |
| KartID    | Integer      | 4920  | Aaro'da tanımlamış olduğunuz cari kartının ID'sidir.                                                                                                       | Evet    |
| Tutar     | Decimal      | 100   | Hareketin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez. KalemTek bilgisindeki değer ile aynı olmalıdır.                                         | Evet    |
| DovizID   | Integer      | 1     | DovizID hareketin döviz cinsini belirler. KalemTek bilgisindeki değer ile aynı olmalıdır.                                                                  | Evet    |
| TutarDvz  | Decimal      | 0     | Hareketin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. KalemTek bilgisindeki değer ile aynı olmalıdır. | Evet    |

```Json
"KalemTek": {
        "KalemTipi" : "Cari",
        "KartID" : 4920,
        "Tutar" : 100,
        "DovizID":  1,
        "TutarDvz":0
}
```

<aside class="info">
Yukarıdaki bilgiler Dekont KalemCok oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.
</aside>

#### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=1`

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--data-raw '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel,
        "KalemCok": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel,
        "KalemCok": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Baslik/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
        "KalemCok": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Baslik/post?KayitTipi=1"

payload="{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
        "KalemCok": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .body("{
        \"Baslik\": \"BaslikModel\",
        \"KalemTek\": \"KalemModel\",
        \"KalemCok\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 190338,
    "Tarih": "2021-09-24T05:34:24.462Z",
    "BelgeNo": "2822429117384-NT",
    "RefBelgeNo": "2822429117384-NT",
    "Vade": "2021-09-24T05:34:24.462Z",
    "Tutar": 100.0,
    "YedekT": 0.0,
    "Seviye": 255,
    "Durum": true,
    "Aciklama": "Nakit Tahsilat TL Kasa",
    "OnayDurum": 1,
    "OlsTar": "2021-09-24T09:01:45.1996952+03:00",
    "DgsTar": "2021-09-24T09:01:45.4761338+03:00",
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
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Dekont eklendikten sonra oluşan Dekontun ID sini Baslik Modelin'de set ettikten sonra düzenle metodunu çağırınız. Böylelikle ilk eklemeden sonra Durumu false olan kalemlerin Durumu true olarak kaydedilir. Aksi takdirde dekont tamamlanmamış olur.

#### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer       | Tanım                                                  | Zorunlu |
| --------- | ----------- | ------------------------------------------------------ | ------- |
| Baslik    | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |
| KalemTek  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |
| KalemCok  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |

<aside class="success">
Dekont(Tek-Tek) oluştururken Nakit Tahsilat örnek senaryo üzerinden gidebilirsiniz.
</aside>

### Nakit Tahsilat Düzenleme

BaşlıkModel içerisinde DekontID bilgisini set ettikten sonra düzeltme yapabiliriz.

#### BaslikModel

```Json
"Baslik": {
    "DekontID": 190338,
    "TipID": "NakitTahsilat",
    "SirketID": 1,
    "SubeID": 1,
    "BelgeNo": "2822429117384-NT",
    "Tarih": "24.09.2021",
    "Vade": "24.09.2021",
}
```

#### KalemTekModel

KalemTek Model deki tutar bilgisini yenileyelim
KalemTek icindeki aciklama alanini değiştirelim. Bu alan Dekontun açıklamasıdır.

```Json
"KalemTek": {
        "KalemTipi" : "Kasa",
        "KartID" : 1,
        "Tutar" : 200,
        "DovizID":  1,
        "TutarDvz":0,
        "Aciklama": "Nakit Tahsilat Başlık Modeli Düzenleme",
}
```

#### KalemCokModel

KalemCok Model deki tutar bilgisini yenileyelim

```Json
"KalemTek": {
        "KalemTipi" : "Cari",
        "KartID" : 4920,
        "Tutar" : 200,
        "DovizID":  1,
        "TutarDvz":0
}
```

#### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=2`

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--data-raw '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel,
        "KalemCok": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel,
        "KalemCok": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Baslik/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
        "KalemCok": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Baslik/post?KayitTipi=2"

payload="{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
        "KalemCok": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .body("{
        \"Baslik\": \"BaslikModel\",
        \"KalemTek\": \"KalemModel\",
        \"KalemCok\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 190338,
    "Tarih": "2021-09-24T05:34:24.462Z",
    "BelgeNo": "2822429117384-NT",
    "RefBelgeNo": "2822429117384-NT",
    "Vade": "2021-09-24T05:34:24.462Z",
    "Tutar": 100.0,
    "YedekT": 0.0,
    "Seviye": 255,
    "Durum": true,
    "Aciklama": "Nakit Tahsilat Başlık Modeli Düzenleme",
    "OnayDurum": 1,
    "OlsTar": "2021-09-24T09:01:45.1996952+03:00",
    "DgsTar": "2021-09-24T09:01:45.4761338+03:00",
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
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Dekont eklendikten sonra oluşan Dekontun ID sini Baslik Modelin'de set ettikten sonra düzenle metodunu çağırınız. Böylelikle ilk eklemeden sonra Durumu false olan kalemlerin Durumu true olarak kaydedilir. Aksi takdirde dekont tamamlanmamış olur.

#### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                            |
| --------- | ------- | ------------------------------------------------ |
| KayitTipi | Integer | 2 Tüm API'de kayıt düzenle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer       | Tanım                                                  | Zorunlu |
| --------- | ----------- | ------------------------------------------------------ | ------- |
| Baslik    | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |
| KalemTek  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |
| KalemCok  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |

### Nakit Tahsilat Silme

BaşlıkModel içerisinde sadece DekontID bilgisini set etmemiz yeterli olacaktır.

#### BaslikModel

```Json
"Baslik": {
    "DekontID": 190338
}
```

#### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=-1`

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--data-raw '{
        "Baslik": BaslikModel,
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Baslik": BaslikModel,
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Baslik/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Baslik": "BaslikModel",
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Baslik/post?KayitTipi=-1"

payload="{
        "Baslik": "BaslikModel",
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .body("{
        \"Baslik\": \"BaslikModel\",
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 0,
    "Tarih": "0001-01-01T00:00:00",
    "BelgeNo": null,
    "RefBelgeNo": null,
    "Vade": "0001-01-01T00:00:00",
    "Tutar": 0.0,
    "YedekT": 0.0,
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
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

#### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                         |
| --------- | ------- | --------------------------------------------- |
| KayitTipi | Integer | -1 Tüm API'de kayıt sil anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer       | Tanım                                                  | Zorunlu |
| --------- | ----------- | ------------------------------------------------------ | ------- |
| Baslik    | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |

## Alınan Sipariş Oluşturma-Düzenleme-Silme (Tek-Cok)

### Alınan Sipariş Başlık Kaydetme

Bu başık altında Alınan Sipariş hareketinin kaydetme sürecini göreceksiniz. (Tek-Cok) hareketlerinde önce BaslikModel ve KalemTekModel bilgileri ile Başlık kaydedilir. Bu işlem başarılı olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir.

#### BaslikModel

Farklı bir Dekont(Tek-Cok) kaydı oluşturmak istediğinzde örneğin Verilen Sipariş hareketi oluşturmak istediğinizde, BaslikModel'in içinde yer alan TipID parametresini "VerilenSiparis" olarak değiştirmeniz yeterli olacaktır.

| Parametre | Tip                | Değer                               | Tanım                                                                               | Zorunlu |
| --------- | ------------------ | ----------------------------------- | ----------------------------------------------------------------------------------- | ------- |
| TipID     | HareketTurleriEnum | AlinanSiparis                       | Dekontun hareket türünü belirler.                                                   | Evet    |
| SirketID  | Integer            | 1                                   | Hareketin hangi şirkete açılacağını belirler                                        | Evet    |
| SubeID    | Integer            | 1                                   | Hareketin hangi şubeye açılacağını belirler                                         | Evet    |
| BelgeNo   | String             | 2822429117384-AS                    | Dekontun belge numarasıdır. Uniqe olmak zorundadır.                                 | Evet    |
| Tarih     | DateTime           | 24.09.2021                          | Dekont tarihidir.                                                                   | Evet    |
| Vade      | DateTime           | 24.09.2021                          | Deokntun vadesidir. Verilmediği takdirde dekontun tarihi ile aynı değeri alacaktır. | Hayır   |
| Aciklama  | String             | Alınan Sipariş Başlık Modeli Ekleme | Dekont'un başlığına ait açıklamadır.                                                | Hayır   |

```Json
"Baslik": {
    "TipID": "AlinanSiparis",
    "SirketID": 1,
    "SubeID": 1,
    "BelgeNo": "4655889712369-AS",
    "Tarih": "24.09.2021",
    "Vade": "24.09.2021",
    "Aciklama": "Alınan Sipariş Başlık Modeli Ekleme",
}
```

<aside class="info">
Yukarıdaki bilgiler Dekont Başlığı oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz BaslikModel'ine bakabilirsiniz.
</aside>

#### KalemTekModel

| Parametre | Tip          | Değer | Tanım                                                                                                           | Zorunlu |
| --------- | ------------ | ----- | --------------------------------------------------------------------------------------------------------------- | ------- |
| KalemTipi | KalemTipleri | Cari  | Alınan Sipariş hareketi Cari üzerinden yapıldığı için KalemTek bilgisinin KalemTipi parametresi Cari olmalıdır. | Evet    |
| KartID    | Integer      | 4920  | Aaro'da tanımlamış olduğunuz cari kartının ID'sidir.                                                            | Evet    |
| Tutar     | Decimal      | 100   | Hareketin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez.                                              | Evet    |
| DovizID   | Integer      | 1     | DovizID hareketin döviz cinsini belirler.                                                                       | Evet    |
| TutarDvz  | Decimal      | 0     | Hareketin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez.      | Evet    |

```Json
"KalemTek": {
        "KalemTipi" : "Cari",
        "KartID" : 4920,
        "Tutar" : 100,
        "DovizID":  1,
        "TutarDvz":0
}
```

<aside class="info">
Yukarıdaki bilgiler Dekont KalemTek oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.
</aside>

#### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=1`

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--data-raw '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel,
        "KalemCok": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel,
        "KalemCok": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Baslik/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
        "KalemCok": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Baslik/post?KayitTipi=1"

payload="{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
        "KalemCok": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .body("{
        \"Baslik\": \"BaslikModel\",
        \"KalemTek\": \"KalemModel\",
        \"KalemCok\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "Model": {
        "DekontID": 190339,
        "Tarih": "2021-09-24T07:57:24.035Z",
        "BelgeNo": "4655889712369-AS",
        "RefBelgeNo": "4655889712369-AS",
        "Vade": "2021-09-24T07:57:24.035Z",
        "Tutar": 0.0,
        "YedekT": 0.0,
        "Seviye": 255,
        "Durum": false,
        "Aciklama": null,
        "OnayDurum": 0,
        "OlsTar": "2021-09-24T11:01:53.0072954+03:00",
        "DgsTar": "2021-09-24T11:01:53.0072954+03:00",
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
        "RefDepoID": null,
        "RefKDVDahil": null,
        "RefProjeID": null,
        "RefPlasiyerID": null,
        "RefDepo2ID": null,
        "RefIthalatIhracatID": null,
        "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Bu işlem başarılı olduktan sonra KalemCok bilgisini eklemek için Kalem metodunu kullanacaz

#### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer       | Tanım                                                  | Zorunlu |
| --------- | ----------- | ------------------------------------------------------ | ------- |
| Baslik    | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |
| KalemTek  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Evet    |

### Alınan Sipariş Kalem Kaydetme

Başlık kaydetme işlemi başarılı olduktan sonra KalemCok bilgisi "Kalem" metoduyla beraber kaydedilir. Birden çok kalem kaydetmek istiyorsanız her kalem için bu metodu çağırmalısınız

#### KalemCokModel

| Parametre   | Tip              | Değer            | Tanım                                                                                                    | Zorunlu |
| ----------- | ---------------- | ---------------- | -------------------------------------------------------------------------------------------------------- | ------- |
| KalemTipi   | KalemTipleri     | SiparisStok      | Alınan Sipariş hareketinde kalemleri ekleyebilmek için KalemTipi parametresi SiparisStok olmalıdır.      | Evet    |
| DekontID    | Integer          | 190339           | Baslik metodunu kullanarak kaydettiğimiz dekontun ID'sidir.                                              | Evet    |
| KartID      | Integer          | 3658             | Aaro'da tanımlamış olduğunuz stok kartının ID'sidir.                                                     | Evet    |
| Miktar      | Decimal          | 1                | Eklemek istediğiniz stoğun kendi birimi cinsinden miktarını belirtir.                                    | Evet    |
| Tutar       | Decimal          | 150              | Kalemin toplam tutarının TL cinsinden karşılığıdır. 0 girilemez.                                         | Evet    |
| DovizID     | Integer          | 1                | DovizID hareketin döviz cinsini belirler.                                                                | Evet    |
| TutarDvz    | Decimal          | 0                | Kalemin tutarının belirtilen döviz cinsinden karşılığıdır. Döviz cinsi TL(1)'den farklı ise 0 girilemez. | Evet    |
| SiparisStok | SiparisStokModel | SiparisStokModel | Dökümanda yer alan SiparisStokModel bilgileriyle oluşturulan model                                       | Evet    |

```Json
"KalemCok": {
    "KalemTipi": "SiparisStok",
    "DekontID": 190339,
    "KartID": "3658",
    "Miktar": 1,
    "Tutar": 150,
    "DovizID": 1,
    "TutarDvz": 0,
    "SiparisStok": {
        "DepoID" : 1,
        "TeslimTarihi" : "24.09.2021",
        "VergiDetaylari": [
            {
                "VergiID": 1,
                "Oran": 18,
                "Tutar": 9,
                "TutarDvz": 0,
                "DovizID": 1,
                "Matrah": 50,
                "MatrahDvz": 0,
                "BA": "B"
            }
        ]
    }
}
```

<aside class="info">
Yukarıdaki bilgiler Dekont KalemCok oluşturmak için gereken asgari bilgilerdir. Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.
</aside>

#### HTTP Request

`POST https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=1`

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=1' \
--header 'Content-Type: application/json' \
--data-raw '{
        "KalemCok": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "KalemCok": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Kalem/post?KayitTipi=1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Kalem/post?KayitTipi=1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "KalemCok": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kalem/post?KayitTipi=1"

payload="{
        "KalemCok": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kalem/post?KayitTipi=1")
  .header("Content-Type", "application/json")
  .body("{
        \"KalemCok\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

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
      "BrmFiyatN": 150.0,
      "BrmFiyatB": 10.4,
      "BrmFiyatTipi": 1,
      "VergiAltID": null,
      "VergiOran": null,
      "StokDetayID": null,
      "DepoID": 1,
      "CariID": 4920,
      "GelirGiderCariID": null,
      "DemirbasID": null,
      "GelirGiderDekontID": null,
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
      "IskontoTipi": true,
      "IskontoOrani": 0.0,
      "VadeIskontoOrani": 9.426919,
      "KullaniciIskontoOrani": 16.0,
      "TeslimTarihi": "2021-09-24T07:57:24.035Z",
      "Kapali": false,
      "IsEmriID": null,
      "KarsilamaSekli": null,
      "IthalatIhracatID": null,
      "UstHareketID": null,
      "VergiDetaylari": [
        {
          "__TabloID": 3019,
          "__ProgramID": 3009,
          "VergiDetayID": 33260,
          "StokHareketID": 28075,
          "VergiID": 1,
          "VergiAltID": null,
          "VergiMuafiyetID": null,
          "Oran": 18.0,
          "Tutar": 27.0,
          "TutarDvz": 0.0,
          "Matrah": 150.0,
          "MatrahDvz": 0.0,
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
    "HareketID": 28075,
    "DekontID": 190339,
    "SubeID": 1,
    "SirketID": 1,
    "TipID": 10013,
    "YevmiyeFisHareketID": null,
    "KartID": 3658,
    "Tarih": "2021-09-24T07:57:24.037",
    "Vade": "2021-09-24T07:57:24.037",
    "BA": "A",
    "Tutar": 150.0,
    "Miktar": 1.0,
    "DovizID": 1,
    "TutarDvz": 0.0,
    "SozlesmeID": null,
    "ProjeID": null,
    "PlasiyerID": null,
    "Durum": false,
    "Aciklama": null,
    "AciklamalarID": null,
    "OnayDurum": 0,
    "OlsID": 2,
    "OlsTar": "2021-09-24T11:24:29.3273835+03:00",
    "DgsID": 2,
    "DgsTar": "2021-09-24T11:24:29.3273835+03:00",
    "YedekD1": null,
    "YedekD2": null,
    "YedekD3": null,
    "YedekS1": null,
    "YedekS2": null,
    "YedekS3": null,
    "YedekI1": null,
    "YedekI2": null,
    "YedekI3": null,
    "KartAdi": "Profil Seren Ahşap Ladin   3.0X4.3X300cm"
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Bu işlem başarılı olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacaz

#### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                              |
| --------- | ------- | -------------------------------------------------- |
| KayitTipi | Integer | 1 Tüm API'de yeni kayıt ekle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer      | Tanım                                                 | Zorunlu |
| --------- | ---------- | ----------------------------------------------------- | ------- |
| KalemCok  | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |

<aside class="success">
KalemCok bilgisi eklendikten sonra Baslik düzenle metodu çağrılarak Başlık bilgisi yenilenmiş olur. Kalemleri ekleme işlemi tamamlandıktan sonra Baslik metodunu KayitTipi "Düzelt" yaparak çağrılmalıdır.
</aside>

### Alınan Sipariş Başlık Düzeltme

Başlık bilgisinde DekontID'yi set ettikten sorna düzeltme işlemi yapabiliriz

#### BaslikModel

Başlık bilgisini düzeltirken KalemTek bilgisini göndermeniz zorunlu değildir.

```Json
"Baslik": {
    "DekontID": 190339,
    "TipID": "AlinanSiparis",
    "SirketID": 1,
    "SubeID": 1,
    "BelgeNo": "4655889712369-AS",
    "Tarih": "24.09.2021",
    "Vade": "24.09.2021",
    "Aciklama": "Alınan Sipariş Başlık Modeli Ekleme",
}
```

#### KalemTekModel

```Json
"KalemTek": {
        "KalemTipi" : "Cari",
        "KartID" : 4920,
        "Tutar" : 100,
        "DovizID":  1,
        "TutarDvz":0
}
```

#### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=2`

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--data-raw '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel,
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Baslik": BaslikModel,
        "KalemTek": KalemModel,
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Baslik/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Baslik/post?KayitTipi=2"

payload="{
        "Baslik": "BaslikModel",
        "KalemTek": "KalemModel",
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .body("{
        \"Baslik\": \"BaslikModel\",
        \"KalemTek\": \"KalemModel\",
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 190339,
    "Tarih": "2021-09-24T07:57:24.035Z",
    "BelgeNo": "4655889712369-AS",
    "RefBelgeNo": "4655889712369-AS",
    "Vade": "2021-09-24T07:57:24.035Z",
    "Tutar": 177.0,
    "YedekT": 0.0,
    "Seviye": 255,
    "Durum": true,
    "Aciklama": "Alınan Sipariş Aaro Yazılım ve Makina AŞ",
    "OnayDurum": 1,
    "OlsTar": "2021-09-24T11:01:53.007",
    "DgsTar": "2021-09-24T11:39:21.52",
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
    "RefDepoID": null,
    "RefKDVDahil": null,
    "RefProjeID": null,
    "RefPlasiyerID": null,
    "RefDepo2ID": null,
    "RefIthalatIhracatID": null,
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

#### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                 |
| --------- | ------- | ----------------------------------------------------- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayıt düzenle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer       | Tanım                                                  | Zorunlu |
| --------- | ----------- | ------------------------------------------------------ | ------- |
| Baslik    | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |
| KalemTek  | KalemModel  | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz.  | Hayır   |

### Alınan Sipariş Kalem Düzeltme

Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra düzeltme işlemi yapabiliriz.
Kalem bilgisinin miktarını değiştirip 3 yapalım. Miktar bilgisini güncellediğiniz zaman Tutar bilgisinin de güncellenmesini istiyorsanız, Tutar bigisini de girmeniz gerekmektedir.

```Json
"KalemCok": {
    "KalemTipi": "SiparisStok",
    "DekontID": 190339,
    "HareketID": 28075,
    "KartID": "3658",
    "Miktar": 3,
    "Tutar": 150,
    "DovizID": 1,
    "TutarDvz": 0,
    "SiparisStok": {
        "DepoID" : 1,
        "TeslimTarihi" : "24.09.2021",
        "VergiDetaylari": [
            {
                "VergiID": 1,
                "Oran": 18,
                "Tutar": 9,
                "TutarDvz": 0,
                "DovizID": 1,
                "Matrah": 50,
                "MatrahDvz": 0,
                "BA": "B"
            }
        ]
    }
}
```

<aside class="info">
Daha fazla parametre göndermek isterseniz KalemModel'ine bakabilirsiniz.
</aside>

#### HTTP Request

`POST https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=2`

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=2' \
--header 'Content-Type: application/json' \
--data-raw '{
        "KalemCok": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "KalemCok": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Kalem/post?KayitTipi=2",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Kalem/post?KayitTipi=2");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "KalemCok": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kalem/post?KayitTipi=2"

payload="{
        "KalemCok": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kalem/post?KayitTipi=2")
  .header("Content-Type", "application/json")
  .body("{
        \"KalemCok\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

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
      "BrmFiyatN": 50.0,
      "BrmFiyatB": 10.4,
      "BrmFiyatTipi": 1,
      "VergiAltID": null,
      "VergiOran": null,
      "StokDetayID": null,
      "DepoID": 1,
      "CariID": 4920,
      "GelirGiderCariID": null,
      "DemirbasID": null,
      "GelirGiderDekontID": null,
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
      "IskontoTipi": true,
      "IskontoOrani": 0.0,
      "VadeIskontoOrani": 9.426919,
      "KullaniciIskontoOrani": 16.0,
      "TeslimTarihi": "2021-09-24T07:57:24.035Z",
      "Kapali": false,
      "IsEmriID": null,
      "KarsilamaSekli": null,
      "IthalatIhracatID": null,
      "UstHareketID": null,
      "VergiDetaylari": [
        {
          "__TabloID": 3019,
          "__ProgramID": 3009,
          "VergiDetayID": 33261,
          "StokHareketID": 28075,
          "VergiID": 1,
          "VergiAltID": null,
          "VergiMuafiyetID": null,
          "Oran": 18.0,
          "Tutar": 27.0,
          "TutarDvz": 0.0,
          "Matrah": 150.0,
          "MatrahDvz": 0.0,
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
    "HareketID": 28075,
    "DekontID": 190339,
    "SubeID": 1,
    "SirketID": 1,
    "TipID": 10013,
    "YevmiyeFisHareketID": null,
    "KartID": 3658,
    "Tarih": "2021-09-24T07:57:24.037",
    "Vade": "2021-09-24T07:57:24.037",
    "BA": "A",
    "Tutar": 150.0,
    "Miktar": 3.0,
    "DovizID": 1,
    "TutarDvz": 0.0,
    "SozlesmeID": null,
    "ProjeID": null,
    "PlasiyerID": null,
    "Durum": false,
    "Aciklama": null,
    "AciklamalarID": null,
    "OnayDurum": 1,
    "OlsID": 2,
    "OlsTar": "2021-09-24T11:24:29.327",
    "DgsID": 2,
    "DgsTar": "2021-09-24T11:47:07.9325796+03:00",
    "YedekD1": null,
    "YedekD2": null,
    "YedekD3": null,
    "YedekS1": null,
    "YedekS2": null,
    "YedekS3": null,
    "YedekI1": null,
    "YedekI2": null,
    "YedekI3": null,
    "KartAdi": "Profil Seren Ahşap Ladin   3.0X4.3X300cm"
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

Bu işlem başarılı olduktan sonra KalemCok bilgisini eklemek için Kalemler metodunu kullanacaz

#### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                                 |
| --------- | ------- | ----------------------------------------------------- |
| KayitTipi | Integer | 2 Tüm API'de yeni kayıt düzenle anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer      | Tanım                                                 | Zorunlu |
| --------- | ---------- | ----------------------------------------------------- | ------- |
| KalemCok  | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |

<aside class="success">
KalemCok bilgisi eklendikten sonra Baslik düzenle metodu çağrılarak Başlık bilgisi yenilenmiş olur. Kalemleri düzenleme işlemi tamamlandıktan sonra Baslik metodunu KayitTipi "Düzelt" yaparak çağrılmalıdır.
</aside>

### Alınan Sipariş Kalem Silme

Kalem bilgisinin DekontID ve HareketID'si set edildikten sonra silme işlemi yapabiliriz.

```Json
"KalemCok": {
    "KalemTipi": "SiparisStok",
    "DekontID": 190339,
    "HareketID": 28075,
}
```

#### HTTP Request

`POST https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=-1`

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Kalem/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--data-raw '{
        "KalemCok": KalemModel
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "KalemCok": KalemModel
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Kalem/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Kalem/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "KalemCok": "KalemModel"
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Kalem/post?KayitTipi=-1"

payload="{
        "KalemCok": "KalemModel"
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Kalem/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .body("{
        \"KalemCok\": \"KalemModel\"
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "KalemTipi": 0,
    "Cari": null,
    "Stok": null,
    "Banka": null,
    "Kasa": null,
    "CekSenet": null,
    "SiparisCari": null,
    "SiparisStok": null,
    "HareketID": 0,
    "DekontID": 0,
    "SubeID": 0,
    "SirketID": 0,
    "TipID": 0,
    "YevmiyeFisHareketID": null,
    "KartID": 0,
    "Tarih": "0001-01-01T00:00:00",
    "Vade": "0001-01-01T00:00:00",
    "BA": null,
    "Tutar": 0.0,
    "Miktar": 0.0,
    "DovizID": 0,
    "TutarDvz": 0.0,
    "SozlesmeID": null,
    "ProjeID": null,
    "PlasiyerID": null,
    "Durum": false,
    "Aciklama": null,
    "AciklamalarID": null,
    "OnayDurum": 0,
    "OlsID": 0,
    "OlsTar": "0001-01-01T00:00:00",
    "DgsID": 0,
    "DgsTar": "0001-01-01T00:00:00",
    "YedekD1": null,
    "YedekD2": null,
    "YedekD3": null,
    "YedekS1": null,
    "YedekS2": null,
    "YedekS3": null,
    "YedekI1": null,
    "YedekI2": null,
    "YedekI3": null,
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

#### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                         |
| --------- | ------- | --------------------------------------------- |
| KayitTipi | Integer | -1 Tüm API'de kayıt sil anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer      | Tanım                                                 | Zorunlu |
| --------- | ---------- | ----------------------------------------------------- | ------- |
| KalemCok  | KalemModel | KalemModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |

<aside class="success">
KalemCok bilgisi silindikten sonra Baslik düzenle metodu çağrılarak Başlık bilgisi yenilenmiş olur. Kalemleri düzenleme işlemi tamamlandıktan sonra Baslik metodunu KayitTipi "Düzelt" yaparak çağrılmalıdır.
</aside>

### Alınan Sipariş Başlık Silme

#### BaslikModel

Başlık bilgisi silinirken sadece DekontID'yi set etmek yeterli olacak.

```Json
"Baslik": {
    "DekontID": 190339
}
```

#### HTTP Request

`POST https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=-1`

```shell

curl --location --request POST 'https://erp.aaro.com.tr/api/Baslik/post?KayitTipi=-1' \
--header 'Content-Type: application/json' \
--data-raw '{
        "Baslik": BaslikModel,
        }'

```

```javascript
var axios = require("axios");
var data =
  '{
        "Baslik": BaslikModel,
}';

var config = {
  method: "post",
  url: "https://localhost:44346/api/Baslik/post?KayitTipi=-1",
  headers: {
    "Content-Type": "application/json",
    Authorization: "Bearer YOURTOKEN",
  },
  data: data,
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

var client = new RestClient("https://localhost:44346/api/Baslik/post?KayitTipi=-1");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddParameter("application/json", "{
        "Baslik": "BaslikModel",
}",  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```python

import requests

url = "https://localhost:44346/api/Baslik/post?KayitTipi=-1"

payload="{
        "Baslik": "BaslikModel",
}"

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))


```

```java

Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://localhost:44346/api/Baslik/post?KayitTipi=-1")
  .header("Content-Type", "application/json")
  .body("{
        \"Baslik\": \"BaslikModel\",
}")
  .asString();

```

> Yukarıdaki kodlar aşağıdaki gibi bir JSON cevabı döndürmektedir:

```json
{
  "Model": {
    "DekontID": 0,
    "Tarih": "0001-01-01T00:00:00",
    "BelgeNo": null,
    "RefBelgeNo": null,
    "Vade": "0001-01-01T00:00:00",
    "Tutar": 0.0,
    "YedekT": 0.0,
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
    "KartAdi": null
  },
  "Mesajlar": {
    "Mesaj": ""
  },
  "Sonuc": true,
  "Detay": ""
}
```

#### Sorgu URL Parametreleri

| Parametre | Değer   | Tanım                                         |
| --------- | ------- | --------------------------------------------- |
| KayitTipi | Integer | -1 Tüm API'de kayıt sil anlamına gelmektedir. |

#### Sorgu Body JSON açıklaması

| Parametre | Değer       | Tanım                                                  | Zorunlu |
| --------- | ----------- | ------------------------------------------------------ | ------- |
| Baslik    | BaslikModel | BaslikModel'in açıklamasına bakıp bilgi alabilirsiniz. | Evet    |

# Başvurulacak Tablolar

Bu bölümde parametreler arasında Aaro'nun kendi kodlarında tanımladığı enum tablolarına ulaşabilirsiniz.

## KayitTipiEnum

| Parametre | Değer | Açıklama |
| --------- | ----- | -------- |
| Tanimsiz  | -2    | Tanımsız |
| Sil       | -1    | Sil      |
| Oku       | 0     | Oku      |
| Ekle      | 1     | Ekle     |
| Duzelt    | 2     | Duzelt   |

## HareketTurleriEnum

| Parametre            | Değer | Açıklama               | Hareket Tipi |
| -------------------- | ----- | ---------------------- | ------------ |
| NakitTahsilat        | 5003  | Nakit Tahsilat         | (Tek-Tek)    |
| NakitOdeme           | 5004  | Nakit Ödeme            | (Tek-Tek)    |
| BankayaParaYatirma   | 5008  | Bankaya Para Yatırma   | (Tek-Tek)    |
| BankadanParaCekme    | 5009  | Bankadan Para Çekme    | (Tek-Tek)    |
| SatisFaturasi        | 10005 | Satış Faturası         | (Tek-Cok)    |
| AlisFaturasi         | 10006 | Alış Faturası          | (Tek-Cok)    |
| SatisIadeFaturasi    | 10007 | Satış İade Faturası    | (Tek-Cok)    |
| AlisIadeFaturasi     | 10008 | Alış İade Faturası     | (Tek-Cok)    |
| SatisIrsaliyesi      | 10009 | Satış İrsaliyesi       | (Tek-Cok)    |
| AlisIrsaliyesi       | 10010 | Alış İrsaliyesi        | (Tek-Cok)    |
| SatisIadeIrsaliyesi  | 10011 | Satış İade İrsaliyesi  | (Tek-Cok)    |
| AlisIadeIrsaliyesi   | 10012 | Alış İade İrsaliyesi   | (Tek-Cok)    |
| AlinanSiparis        | 10013 | Alınan Sipariş         | (Tek-Cok)    |
| VerilenSiparis       | 10014 | Verilen Sipariş        | (Tek-Cok)    |
| AlinanTeklif         | 10015 | Alinan Teklif          | (Tek-Cok)    |
| VerilenTeklif        | 10016 | Verilen Teklif         | (Tek-Cok)    |
| DepolarArasiTransfer | 10019 | Depolar Arası Transfer | (Tek-Cok)    |

### Yevmiye Fis

