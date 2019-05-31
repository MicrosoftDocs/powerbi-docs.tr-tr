---
title: Filtreler ve vurgulama Power BI raporları
description: Power BI raporlarındaki filtreler ve vurgulama hakkında
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 8084b8dbbc27c856633d84c6628727dcd426964d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187549"
---
# <a name="filters-and-highlighting-in-power-bi-reports"></a>Filtreler ve vurgulama Power BI raporları
 Bu makalede, filtreleme ve vurgulama Power BI hizmetinde tanıtılmaktadır. Power BI Desktop ile sunulan deneyim de neredeyse aynıdır. *Filtreler*, odaklanmak istedikleriniz dışındaki tüm verileri kaldırır. *Vurgulama* filtreleme değildir. Veri kaldırmaz, ancak bunun yerine görünen verilerin bir alt kümesini vurgular. Vurgulanan olmayan veriler görünür ancak devre dışı kalır.

Power BI'da raporları çok çeşitli yollarla filtreleyebilir ve vurgulayabilirsiniz. Tüm bu bilgilerin tek bir makalede ele alınması karmaşıklık yaratacağından tüm konuyu aşağıdaki şekilde bölümlere ayırmayı tercih ettik:

* Şu anda giriş filtreler ve vurgulama, makaleyi okuduğunuz.
* Nasıl yapılır [oluşturma ve düzenleme Görünümü'nde filtreleri kullanma](power-bi-report-add-filter.md) Power BI Desktop ve Power BI hizmeti raporlarındaki. Düzenleme izinlerine sahip olmanız halinde raporlarda filtre oluşturabilir, bunları değiştirebilir ve silebilirsiniz.
* Nasıl görselleri [filtreleyebilir ve vurgulayabilirsiniz sizinle paylaşılan bir raporda](consumer/end-user-interactions.md), rapor Power BI hizmetinde Okuma Görünümü. Yapabilecekleriniz daha sınırlıdır ancak yine de çok çeşitli filtreleme ve vurgulama seçeneklerine sahip olursunuz.  
* İlişkin ayrıntılı bir tur [filtre ve vurgulama düzenleme Görünümü'nde kullanılabilir denetimleri](power-bi-report-add-filter.md) Power BI Desktop ve Power BI hizmetinde. Makale, bir tarih ve saat, sayısal, gibi filtre türleri ilişkin kapsamlı bir bakış ve metin alır. Ayrıca, temel ve Gelişmiş Seçenekler arasındaki farkları da kapsar.
* Filtrelerin ve vurgulamanın varsayılan olarak nasıl çalıştığını öğrendikten sonra [bir sayfadaki görselleştirmelerin birbirini filtreleme ve vurgulama şeklini nasıl değiştireceğinizi öğrenebilirsiniz](service-reports-visual-interactions.md)

**Biliyor muydunuz?** Power BI, şu an önizleme aşamasında olan yeni bir filtre deneyimine sahiptir. [Power BI raporlarında yeni filtre deneyimi](power-bi-report-filter-preview.md) hakkında daha fazla bilgi edinin.

![Yeni filtre deneyimi](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading.png)


## <a name="intro-to-the-filters-pane"></a>Filtreler bölmesine giriş

Filtreleri **Filtreler** bölmesinden veya doğrudan rapor üzerindeki [dilimleyicilerde seçim yaparak](visuals/power-bi-visualization-slicers.md) uygulayabilirsiniz. Filtreler bölmesi, raporda kullanılan tabloların ve alanların yanı sıra uygulanan filtreleri (varsa ) gösterir. 

![Filtreler bölmesi](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Dört tür filtre vardır.

- **Sayfa filtresi**, rapor sayfasındaki tüm görsellere uygulanır     
- **Görsel filtresi**, bir rapor sayfasındaki tek bir görsele uygulanır. Rapor tuvalinde bir görsel seçtiyseniz yalnızca görsel düzeyi filtrelerini görürsünüz.    
- **Rapor filtresi**, rapordaki tüm sayfalara uygulanır    
- **Detaylandırma filtresi**, bir rapordaki tek bir varlığa uygulanır    

Okuma veya Düzenleme görünümünde sayfa, görsel ve rapor filtrelerinde arama yaparak istediğiniz değeri bulabilir ve seçebilirsiniz. 

![Filtrede arama yapma](media/power-bi-reports-filters-and-highlighting/power-bi-search-filter.png)

Filtrenin yanında **Tümü** ifadesinin bulunması, alandaki tüm değerlerin filtreye dahil edilmiş olduğunu gösterir.  Örneğin, aşağıdaki ekran görüntüsünde **Chain (Tümü)** , bu rapor sayfasının tüm mağaza zincirleriyle ilgili verileri içerdiğini gösterir.  Diğer yandan, **FiscalYear 2013 veya 2014 değeridir** rapor düzeyi filtresi, bize raporun yalnızca 2013 ve 2014 mali yıllarına ilişkin verileri içerdiğini gösterir.

## <a name="filters-in-reading-or-editing-view"></a>Okuma veya Düzenleme görünümündeki filtreler
Raporlarla etkileşimli çalışmak için kullanabileceğiniz iki mod vardır: [Okuma görünümü](consumer/end-user-reading-view.md) ve Düzenleme görünümü. Kullanabileceğiniz filtreleme özellikleri hangi modda olduğunuza bağlıdır.

* Düzenleme görünümünde, rapor, sayfa, detaylandırma ve görsel filtreler ekleyebilirsiniz. Raporu kaydettiğinizde, mobil uygulamada açsanız bile filtreler raporla birlikte kaydedilir. Okuma görünümünde rapora göz atan kişiler eklediğiniz filtrelerle etkileşim kurabilir ancak yeni filtreler ekleyemez.
* Okuma görünümünde önceden raporda bulunan filtrelerle etkileşim kurabilir ve yaptığınız seçimi kaydedebilirsiniz. Yeni filtre ekleyemezsiniz.

### <a name="filters-in-reading-view"></a>Okuma görünümündeki filtreler
Bir rapora yalnızca Okuma görünümünde erişim sahibiyseniz Filtreler bölmesi aşağıdaki gibi görünür:

![Okuma görünümündeki filtreler](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Raporun bu sayfasında altı sayfa düzeyi filtresi ile bir rapor düzeyi filtresi bulunur.

Bir görselde bulunan tüm alanlara filtre uygulanmış olabilir ve rapor yazarı daha fazla filtre ekleyebilir. Aşağıdaki görüntüde, kabarcık grafiğinde altı filtre vardır.

![Görsel düzeyi filtresi](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

Okuma görünümünde, mevcut filtreleri değiştirerek verileri araştırabilirsiniz. Raporu mobil uygulamada açsanız bile, yaptığınız değişiklikler rapora kaydedilir. Nasıl yapıldığını öğrenmek için [Power BI Filtreler bölmesine ilişkin tura katılın](consumer/end-user-report-filter.md)

Rapordan çıktığınızda filtreleriniz kaydedilir. Filtreleme işlemini geri almak ve rapor yazarı tarafından ayarlanan varsayılan filtreleme, dilimleme, detaylandırma ve sıralamaya geri dönmek için, üst menü çubuğundan **Varsayılana sıfırla**’yı seçin.

![Varsayılan simge Sıfırla](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

### <a name="filters-in-editing-view"></a>Düzenleme görünümündeki filtreler
Bir rapor için sahip izinleriniz olduğunda ve raporu Düzenleme görünümünde açtığınızda **Filtreler**'in, kullanılabilir birkaç düzenleme bölmesinden yalnızca biri olduğunu görürsünüz.

![Düzenleme Görünümü'nde filtreler bölmesi](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Okuma görünümünde olduğu gibi raporun bu sayfasında da altı sayfa düzeyi filtresi ile bir rapor düzeyi filtresi bulunur. Kabarcık grafiği seçtiğimizde ise altı görsel düzeyi filtresinin uygulanmış olduğunu görürüz.

Düzenleme görünümünde filtreler ve vurgulama ile daha fazla işlem gerçekleştirebilirsiniz. Özellikle yeni filtreler ekleyebilirsiniz. [Rapora filtre eklemeyi](power-bi-report-add-filter.md) ve çok daha fazlasını öğrenin.

## <a name="ad-hoc-highlighting"></a>Geçici vurgulama
Sayfadaki diğer görsellerin vurgulamak için görselin bir değer veya eksen etiketi seçin. Vurgulamayı kaldırmak için değer yeniden seçin veya aynı görselde boş alanın seçin. Eğlenceli bir vurgulama, veri etkilerini hızla Keşfetmenin bir yolu. [Görsel etkileşimler](service-reports-visual-interactions.md) makalesine giderek bu türdeki çapraz vurgulama işlemlerinin nasıl çalıştığına ilişkin ayrıntılara ulaşabilirsiniz.

![Çapraz vurgulama](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)


## <a name="next-steps"></a>Sonraki adımlar

[Power BI raporlarındaki yeni filtre deneyimi](power-bi-report-filter-preview.md)

[Bir rapora filtre ekleme (Düzenleme görünümünde)](power-bi-report-add-filter.md)

[Rapor filtrelerine ilişkin bir tura katılın](consumer/end-user-report-filter.md)

[Rapor görsellerinin birbirini çapraz filtreleme ve çapraz vurgulama şeklini değiştirme](consumer/end-user-interactions.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

