---
title: Power BI Desktop'ta ifade tabanlı başlıklar
description: Power BI değiştiren programlı ifadelerini temel alarak koşullu biçimlendirme programlı kullanarak Desktop'ta dinamik başlık oluşturma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: reference
ms.date: 04/10/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b90ef66d2c118a70f1b18ed4fe302ce1db23e45c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64769748"
---
# <a name="expression-based-titles-in-power-bi-desktop"></a>Power BI Desktop'ta ifade tabanlı başlıklar

Dinamik oluşturabilirsiniz başlıklar, Power BI görselleri için özelleştirilebilir. Alanlar, değişkenleri veya diğer programlama öğeleri göre veri çözümleme ifadeleri (DAX) oluşturarak, gerektiği şekilde otomatik olarak, görsellerin başlıkları ayarlayabilirsiniz. Bu değişiklikler, filtreleri, seçimleri veya diğer kullanıcı etkileşimlerine ve yapılandırmaları temel alır.

![Koşullu biçimlendirme seçeneği Power BI Desktop'ın ekran görüntüsü](media/desktop-conditional-formatting-visual-titles/expression-based-title-01.png)

Dinamik başlık oluşturma olarak da adlandırılır *ifade tabanlı başlıkları*, oldukça basittir. 

## <a name="create-a-field-for-your-title"></a>Bir alan, bir başlık oluşturun

İfade tabanlı bir başlık oluşturmanın ilk adımı, modelinizdeki başlığı için kullanılacak bir alan oluşturmaktır. 

Her tür visual başlığınızı ne söylemek istediğiniz veya ifade etmek istediğiniz yansıtmak için yaratıcı yöntemler vardır. Birkaç örnek bir göz atalım.

Görsel ürünün marka adı için alan filtre bağlamı değişiklikleri dayalı bir ifade oluşturabilirsiniz. Aşağıdaki görüntüde bu türden bir alan için DAX formülü gösterilmektedir.

![Ekran görüntüsü, DAX formülü](media/desktop-conditional-formatting-visual-titles/expression-based-title-02.png)

Başka bir örnek, kullanıcının dil veya kültür değişikliklere göre dinamik bir başlık kullanıyor. DAX ölçüsü kullanarak dile özgü başlıkları oluşturabilirsiniz `USERCULTURE()` işlevi. Bu işlev, işletim sistemi veya tarayıcı ayarları dayanarak bu kullanıcı için kültür kodu döndürür. Aşağıdaki DAX switch ifadesi, doğru çevrilmiş değer seçmek için kullanabilirsiniz. 

```
SWITCH (
  USERCULTURE(),
  "de-DE", “Umsatz nach Produkt”,
  "fr-FR", “Ventes par produit”,
  “Sales by product”
)
```

Veya tüm çevirileri içeren bir arama tablosundan dize alabilir. Modelinizde Bu tablo yerleştirdiğiniz. 

Bu, yalnızca Power BI Desktop'ta dinamik, ifade tabanlı başlıkları için görsellerinizi oluşturmak için kullanabileceğiniz örnekler birkaç vardır. Başlıkları ile neler yapabileceğinizi sınırlıdır yalnızca hayal gücünüzü ve model tarafından.


## <a name="select-your-field-for-your-title"></a>Alan, başlık seçin

Alanın modelinizi oluşturmak için DAX ifadesini oluşturduktan sonra görselinizin başlık uygulamanız gerekir.

Alan seçin ve uygulamak için Git **görselleştirmeler** bölmesi. İçinde **biçimi** alanında **başlık** görsel başlığı seçeneklerini göstermek için. 

Sağ tıkladığınızda **başlık metni**, seçmenize olanak sağlayan bir bağlam menüsü görüntülenir ***fx * koşullu biçimlendirme**. Bu menü öğesini seçtiğinizde bir **başlık metni** iletişim kutusu görüntülenir. 

![Ekran görüntüsü, başlık metin iletişim kutusu](media/desktop-conditional-formatting-visual-titles/expression-based-title-02b.png)

Bu penceresinden kullanmak için başlık oluşturulan alanın seçebilirsiniz.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

İfade tabanlı başlıklarının görseller için geçerli uygulamaya ilişkin birkaç sınırlama vardır:

* İfade tabanlı biçimlendirme Python görseller, R görselleri veya anahtar öğrenilenler görsel şu anda desteklenmemektedir.
* Başlığını oluşturduğunuz alan bir dize veri türünde olmalıdır. Sayı veya tarih/saat (veya başka bir veri türü) döndürür ölçüler şu anda desteklenmemektedir.

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede kullanıcıların raporlarınızla etkileşim kurarken değiştirebilirsiniz dinamik alanları görsellerinizi başlıklarını dönüştürün DAX ifadeleri oluşturmak nasıl kaydedileceği açıklanır. Aşağıdaki makaleler de yararlı olabilir.

* [Power BI Desktop'ta rapor arası detaylandırma kullanın](desktop-cross-report-drill-through.md)
* [Power BI Desktop'ta detaylandırma özelliğini kullanma](desktop-drillthrough.md)