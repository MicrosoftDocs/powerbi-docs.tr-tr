---
title: Power BI mobil uygulamalarında belirli bir konumun bağlantısını oluşturma
description: Tekdüzen kaynak tanımlayıcısı (URI) kullanarak Power BI mobil uygulamasındaki belirli bir panonun, kutucuğun veya raporun ayrıntılı bağlantısını oluşturmayı öğrenin.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: mshenhav
ms.openlocfilehash: 4e09b10e38b018f8e5572343b343a243ace3bf81
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2019
ms.locfileid: "64906523"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında belirli bir konumun bağlantısını oluşturma
Power BI’da bulunan belirli öğelere doğrudan ulaşmak için bağlantıları kullanabilirsiniz: Rapor, Pano ve Kutucuk.

Power BI Mobil’de bağlantıları kullanmak için iki temel senaryo bulunur: 

* Power BI’ı **uygulamanın dışından** açmak ve belirli içeriklere (raporlar/panolar/uygulamalar) erişmek için. Bu, genellikle Power BI Mobil’i farklı bir uygulamadan açmayı hedeflediğiniz bir tümleştirme senaryosudur. 
* Power BI’da **gezinmek** için. Bu, genellikle Power BI’da özel bir gezinti oluşturmayı hedeflediğiniz durumlar içindir.


## <a name="use-links-from-outside-of-power-bi"></a>Bağlantıları Power BI’ın dışından kullanma
Bağlantıyı Power BI uygulamasının dışından bir kullandığınızda uygulamanın bunu açabildiğinden emin olmanız gerekir. Uygulama cihazda yüklü değilse kullanıcıya yüklemesini önerin. Tam olarak bunu desteklemesi için özel bir bağlantı biçimi oluşturduk. Bu bağlantı biçimi, cihazın bağlantıyı açmak için uygulamayı kullandığından emin olur ve uygulama cihazda yüklü değilse, kullanıcıya mağazaya gidip bunu edinmesini önerir.

Bağlantı şununla başlamalıdır:  
```html
https://app.powerbi.com/Redirect?[**QUERYPARAMS**]
```

> [!IMPORTANT]
> İçeriğiniz Kamu, Çin vb. özel bir veri merkezinde barındırılıyorsa Bağlantı, `app.powerbigov.us` veya `app.powerbi.cn` gibi doğru Power BI adresiyle başlamalıdır.   
>


**SORGU PARAMETRELERİ** şunlardır:
* **action** (zorunlu) = OpenApp / OpenDashboard / OpenTile / OpenReport
* **appId** = bir uygulamanın parçası olan raporu veya panoyu açmak istiyorsanız 
* **groupObjectId** = çalışma alanının (“çalışma alanım” dışında) parçası olan bir raporu veya panoyu açmak istiyorsanız
* **dashboardObjectId** = pano nesnesi kimliği (eylem OpenDashboard veya OpenTile olduğunda)
* **reportObjectId** = rapor nesnesi kimliği (eylem OpenReport olduğunda)
* **tileObjectId** = kutucuk nesnesi kimliği (eylem OpenTile olduğunda)
* **reportPage** = belirli bir rapor bölümünü açmak isterseniz (eylem OpenReport olduğunda)
* **ctid** = öğenin kuruluş kimliği (B2B senaryosuna yöneliktir. Öğe, kullanıcının kuruluşuna aitse bu atlanabilir).

**Örnekler:**

* Uygulama bağlantısını açma 
  ```html
  https://app.powerbi.com/Redirect?action=OpenApp&appId=appidguid&ctid=organizationid
  ```

* Bir uygulamanın parçası olan panoyu açma 
  ```html
  https://app.powerbi.com/Redirect?action=OpenDashboard&appId=**appidguid**&dashboardObjectId=**dashboardidguid**&ctid=**organizationid**
  ```

* Bir çalışma alanının parçası olan raporu açma
  ```html
  https://app.powerbi.com/Redirect?Action=OpenReport&reportObjectId=**reportidguid**&groupObjectId=**groupidguid**&reportPage=**ReportSectionName**
  ```

### <a name="how-to-get-the-right-link-format"></a>Doğru bağlantı biçimini alma

#### <a name="links-of-apps-and-items-in-app"></a>Uygulamadaki uygulama ve öğelerin bağlantıları

**Bir uygulamanın parçası olan uygulama, rapor ve panolar** için bağlantıyı almanın en kolay yolu, uygulama çalışma alanına gidip “Uygulamayı güncelleştir” seçeneğini belirlemektir. Bu, “Uygulamayı yayımlama” deneyimini açar. Erişim sekmesinde, **Bağlantılar** bölümü bulunur. Bu bölümü genişlettiğinizde, öğelere doğrudan erişmek için kullanılabilen uygulama ve tüm içerik bağlantılarının listesini görebilirsiniz.

![Power BI uygulama yayımlama bağlantıları ](./media/mobile-apps-links/mobile-link-copy-app-links.png)

#### <a name="links-of-items-not-in-app"></a>Uygulamada bulunmayan öğelerin bağlantıları 

Bir uygulamanın parçası olmayan rapor ve panolar için, öğe URL’sinden kimlikleri ayıklamanız gerekir.

Örneğin, 36 karakterden oluşan **pano** nesnesi kimliğini bulmak için Power BI hizmetinde söz konusu panoya gidin 

```html
https://app.powerbi.com/groups/me/dashboards/**dashboard guid comes here**?ctid=**organization id comes here**`
```

36 karakterden oluşan **rapor** nesnesi kimliğini bulmak için Power BI hizmetindeki söz konusu rapora gidin.
Bu, “Çalışma Alanım” bölümündeki raporun bir örneğidir

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**`
```
Yukarıdaki URL, **“ReportSection3”** adlı özel rapor sayfasını da içerir.

Bu, çalışma alanında (Çalışma Alanım değildir) bulunan bir raporun örneğidir

```html
https://app.powerbi.com/groups/**groupid comes here**/reports/**reportid comes here**/ReportSection1?ctid=**organizationid comes here**
```

## <a name="use-links-inside-power-bi"></a>Bağlantıları Power BI’ın içinden kullanma

Power BI içindeki bağlantılar, mobil uygulamalarda Power Hizmeti’nde çalıştıkları gibi çalışır.

Raporunuza, farklı bir Power BI öğesine işaret eden bağlantı eklemek istiyorsanız, tarayıcı adres çubuğundan bu öğe URL’sini kopyalayabilirsiniz. [Bir rapordaki metin kutusuna köprü ekleme](https://docs.microsoft.com/power-bi/service-add-hyperlink-to-text-box) hakkında daha fazla bilgi edinin.

## <a name="use-report-url-with-filter"></a>Filtre ile rapor URL’si kullanma
Power BI hizmetinde olduğu gibi, Power BI Mobil uygulamaları da filtre sorgu parametresi içeren rapor URL’lerini destekler. Raporu Power BI Mobil uygulamasında açabilir ve belirli bir durum için filtreleyebilirsiniz. Örneğin, bu URL, Satış raporunu açıp Bölgeye göre filtreler

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**&filter=Store/Territory eq 'NC'
```

[Raporları filtrelemek için sorgu parametreleri oluşturma](https://docs.microsoft.com/power-bi/service-url-filters) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
Geri bildiriminiz gelecekte neler yapacağımıza karar verme konusunda bize yardımcı olur, bu nedenle Power BI mobil uygulamalarında görmek istediğiniz diğer özellikleri oylamayı unutmayın. 

* [Mobil cihazlar için Power BI uygulamaları](mobile-apps-for-mobile-devices.md)
* Bizi Twitter'da takip edin: @MSPowerBI
* [Power BI Topluluğu](http://community.powerbi.com/)'nda sohbete katılın
* [Power BI nedir?](../../power-bi-overview.md)

