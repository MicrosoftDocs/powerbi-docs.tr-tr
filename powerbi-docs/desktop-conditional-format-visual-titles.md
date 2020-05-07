---
title: Power BI Desktop’ta ifade tabanlı başlıklar
description: Koşullu programlı biçimlendirmeyi kullanarak, programlama ifadelerine göre değişen Power BI Desktop dinamik başlıkları oluşturun
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: reference
ms.date: 04/10/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f3c1f047e3be7520005458294381877d1198ee21
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "73878626"
---
# <a name="expression-based-titles-in-power-bi-desktop"></a>Power BI Desktop’ta ifade tabanlı başlıklar

Power BI görselleriniz için dinamik ve özelleştirilmiş başlıklar oluşturabilirsiniz. Alanlar, değişkenler veya diğer programlama öğelerine göre Veri Çözümleme İfadeleri (DAX) oluşturarak görsellerinizin başlıklarını gerektiği şekilde otomatik olarak ayarlayabilirsiniz. Bu değişiklikler filtreler, seçimler veya diğer kullanıcı etkileşimlerine ve yapılandırmalarına göre yapılır.

![Power BI Desktop koşullu biçimlendirme seçeneğinin ekran görüntüsü](media/desktop-conditional-formatting-visual-titles/expression-based-title-01.png)

*İfade tabanlı başlıklar* olarak da adlandırılan dinamik başlıklar oluşturmak basittir. 

## <a name="create-a-field-for-your-title"></a>Başlığınız için bir alan oluşturma

İfade tabanlı bir başlık oluşturmanın ilk adımı, modelinizde başlık için kullanılacak bir alan oluşturmaktır. 

Görselinizin başlığının söylemesini veya ifade etmesini istediklerinizi yansıtmasını sağlamanın çeşitli yaratıcı yolları vardır. Birkaç örneğe göz atalım.

Ürünün marka adı için görselin aldığı filtre bağlamına göre değişen bir ifade oluşturabilirsiniz. Aşağıdaki görüntüde böyle bir alanın DAX formülü gösterilmektedir.

![DAX formülünün ekran görüntüsü](media/desktop-conditional-formatting-visual-titles/expression-based-title-02.png)

Diğer bir örnek, kullanıcının diline veya kültürüne göre değişen dinamik bir başlık kullanmaktır. `USERCULTURE()` işlevini kullanarak, DAX ölçüsünde dile özgü başlıklar oluşturabilirsiniz. Bu işlev, kullanıcının işletim sistemine veya tarayıcı ayarlarına bağlı olarak kültür kodunu döndürür. Doğru çevrilmiş değeri seçmek için aşağıdaki DAX anahtar ifadesini kullanabilirsiniz. 

```
SWITCH (
  USERCULTURE(),
  "de-DE", “Umsatz nach Produkt”,
  "fr-FR", “Ventes par produit”,
  “Sales by product”
)
```

Ya da dizeyi, tüm çevirileri içeren bir arama tablosundan alabilirsiniz. Bu tabloyu modelinize yerleştirebilirsiniz. 

Bunlar, Power BI Desktop görselleriniz için dinamik, ifade tabanlı başlıklar oluşturmak üzere kullanabileceğiniz yalnızca birkaç örnektir. Başlıklarınız ile yapabilecekleriniz yalnızca hayal gücünüz ve modeliniz ile sınırlıdır.


## <a name="select-your-field-for-your-title"></a>Başlığınız için bir alan seçme

Modelinizde oluşturduğunuz alan için DAX ifadesini oluşturduktan sonra, bunu görselin başlığına uygulamanız gerekir.

Alanı seçmek ve uygulamak için **Görselleştirmeler** bölmesine gidin. **Biçim** alanında, görsel için başlık seçeneklerini göstermek için **Başlık**’ı seçin. 

**Başlık metni**’ne sağ tıkladığınızda, **<em>fx</em>Koşullu biçimlendirme** seçeneğini belirlemenize olanak sağlayan bir bağlam menüsü görüntülenir. Bu menü öğesini seçtiğinizde bir **Başlık metni** iletişim kutusu görüntülenir. 

![Başlık metni iletişim kutusunun ekran görüntüsü](media/desktop-conditional-formatting-visual-titles/expression-based-title-02b.png)

Bu pencereden, başlığınız için kullanmak üzere oluşturduğunuz alanı seçebilirsiniz.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

Görsellere yönelik ifade tabanlı başlıkların geçerli uygulamasına yönelik bazı sınırlamalar vardır:

* İfade tabanlı biçimlendirme şu anda Python görselleri, R görselleri veya Anahtar Etkileyenler görsellerinde desteklenmez.
* Başlık için oluşturduğunuz alan bir dize veri türü olmalıdır. Sayı veya tarih/saat (veya başka bir veri türü) döndüren ölçüler şu anda desteklenmiyor.
* Bir görseli panoya sabitlediğinizde ifade tabanlı başlıklar uygulanmaz.

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, görsellerinizin başlıklarını, kullanıcılar raporlarınızla etkileşime geçtikçe değişebilen dinamik alanlara dönüştürmek için DAX ifadeleri oluşturma açıklanmıştır. Aşağıdaki makaleleri de yararlı bulabilirsiniz.

* [Tablolarda koşullu biçimlendirme](desktop-conditional-table-formatting.md)
* [Power BI Desktop'ta çapraz rapor detaylandırma özelliğini kullanma](desktop-cross-report-drill-through.md)
* [Power BI Desktop'ta detaylandırma özelliğini kullanma](desktop-drillthrough.md)
