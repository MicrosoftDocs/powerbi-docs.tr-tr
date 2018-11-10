---
title: Power BI raporlarındaki filtreler ve vurgulama hakkında
description: Power BI raporlarındaki filtreler ve vurgulama hakkında
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 09/28/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: e364d2ceac3d1a30b0742ceac2bd56e2bc66d9ba
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973247"
---
# <a name="about-filters-and-highlighting-in-power-bi-reports"></a>Power BI raporlarındaki filtreler ve vurgulama hakkında
 Bu makalede, Power BI hizmetindeki filtreleme ve vurgulama özellikleri tanıtılmaktadır. Power BI Desktop ile sunulan deneyim de neredeyse aynıdır. ***Filtreler***, odaklanmak istedikleriniz dışındaki tüm verileri kaldırır. ***Vurgulama***, filtreleme değildir. Bu işlev verileri kaldırmaz, bunun yerine görünen verilerin bir alt kümesini vurgular. Vurgulanmayan veriler görünür kalır ancak gridir.

Power BI'da raporları çok çeşitli yollarla filtreleyebilir ve vurgulayabilirsiniz. Tüm bu bilgilerin tek bir makalede ele alınması karmaşıklık yaratacağından tüm konuyu aşağıdaki şekilde bölümlere ayırmayı tercih ettik:

* Filtrelere ve vurgulamaya giriş (şu anda okuduğunuz makale)
* Raporlarda [Düzenleme görünümünde filtre oluşturmanın ve kullanmanın](power-bi-report-add-filter.md) yolları. Düzenleme izinlerine sahip olmanız halinde raporlarda filtre oluşturabilir, bunları değiştirebilir ve silebilirsiniz.
* Okuma görünümünde, [sizinle paylaşılan bir raporda filtreleri ve vurgulamayı kullanmanın](consumer/end-user-reading-view.md) yolları. Yapabilecekleriniz daha sınırlıdır ancak yine de çok çeşitli filtreleme ve vurgulama seçeneklerine sahip olursunuz.  
* Filtre türleri (örneğin, tarih ve saat, sayısal, metin) ile temel ve gelişmiş seçenekler arasındaki farka ayrıntılı bakışın da dahil olduğu, [Düzenleme görünümünde kullanılabilen filtre ve vurgulama denetimlerine ilişkin ayrıntılı bir tur](consumer/end-user-report-filter.md).
* Filtrelerin ve vurgulamanın varsayılan olarak nasıl çalıştığını öğrendikten sonra [bir sayfadaki görselleştirmelerin birbirini filtreleme ve vurgulama şeklini nasıl değiştireceğinizi öğrenebilirsiniz](consumer/end-user-interactions.md)

## <a name="intro-to-the-filters-pane"></a>Filtreler bölmesine giriş

Filtreleri **Filtreler** bölmesinden veya doğrudan rapor üzerindeki [dilimleyicilerde seçim yaparak](visuals/power-bi-visualization-slicers.md) uygulayabilirsiniz. Filtreler bölmesi, raporda kullanılan tabloların ve alanların yanı sıra uygulanan filtreleri (varsa ) gösterir. 

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Dört tür filtre vardır.

- **Sayfa filtresi**, rapor sayfasındaki tüm görsellere uygulanır     
- **Görsel filtresi**, bir rapor sayfasındaki tek bir görsele uygulanır. Rapor tuvalinde bir görsel seçtiyseniz yalnızca görsel düzeyi filtrelerini görürsünüz.    
- **Rapor filtresi**, rapordaki tüm sayfalara uygulanır    
- **Detaylandırma filtresi**, bir rapordaki tek bir varlığa uygulanır    

Okuma veya Düzenleme görünümünde sayfa, görsel ve rapor filtrelerinde arama yaparak istediğiniz değeri bulabilir ve seçebilirsiniz. 

![Filtrede arama yapma](media/power-bi-reports-filters-and-highlighting/power-bi-search-filter.png)

Filtrenin yanında **Tümü** ifadesinin bulunması, alandaki tüm değerlerin filtreye dahil edilmiş olduğunu gösterir.  Örneğin, aşağıdaki ekran görüntüsünde **Chain (Tümü)**, bu rapor sayfasının tüm mağaza zincirleriyle ilgili verileri içerdiğini gösterir.  Diğer yandan, **FiscalYear 2013 veya 2014 değeridir** rapor düzeyi filtresi, bize raporun yalnızca 2013 ve 2014 mali yıllarına ilişkin verileri içerdiğini gösterir.

## <a name="filters-in-reading-or-editing-view"></a>Okuma veya Düzenleme görünümündeki filtreler
Raporlarla etkileşim kurmak için kullanabileceğiniz iki mod vardır: [Okuma görünümü ve Düzenleme görünümü](consumer/end-user-reading-view.md). Kullanabileceğiniz filtreleme özellikleri hangi modda olduğunuza bağlıdır.

* Düzenleme görünümünde, rapor, sayfa, detaylandırma ve görsel filtreler ekleyebilirsiniz. Raporu kaydettiğinizde, mobil uygulamada açsanız bile filtreler raporla birlikte kaydedilir. Okuma görünümünde rapora göz atan kişiler eklediğiniz filtrelerle etkileşim kurabilir ancak yeni filtreler ekleyemez.
* Okuma görünümünde önceden raporda bulunan filtrelerle etkileşim kurabilir ve yaptığınız seçimi kaydedebilirsiniz. Yeni filtre ekleyemezsiniz.

### <a name="filters-in-reading-view"></a>Okuma görünümündeki filtreler
Bir rapora yalnızca Okuma görünümünde erişim sahibiyseniz Filtreler bölmesi aşağıdaki gibi görünür:

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Raporun bu sayfasında altı sayfa düzeyi filtresi ile bir rapor düzeyi filtresi bulunur.

Bir görselde bulunan tüm alanlara filtre uygulanmış olabilir ve rapor yazarı daha fazla filtre ekleyebilir. Aşağıdaki görüntüde, kabarcık grafiğinde altı filtre vardır.

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

Okuma görünümünde, mevcut filtreleri değiştirerek verileri araştırabilirsiniz. Raporu mobil uygulamada açsanız bile, yaptığınız değişiklikler rapora kaydedilir. Nasıl yapıldığını öğrenmek için [Power BI Filtreler bölmesine ilişkin tura katılın](consumer/end-user-report-filter.md)

Rapordan çıktığınızda filtreleriniz kaydedilir. Filtreleme işlemini geri almak ve rapor yazarı tarafından ayarlanan varsayılan filtreleme, dilimleme, detaylandırma ve sıralamaya geri dönmek için, üst menü çubuğundan **Varsayılana sıfırla**’yı seçin.

![](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

### <a name="filters-in-editing-view"></a>Düzenleme görünümündeki filtreler
Bir rapor için sahip izinleriniz olduğunda ve raporu Düzenleme görünümünde açtığınızda **Filtreler**'in, kullanılabilir birkaç düzenleme bölmesinden yalnızca biri olduğunu görürsünüz.

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Okuma görünümünde olduğu gibi raporun bu sayfasında da altı sayfa düzeyi filtresi ile bir rapor düzeyi filtresi bulunur. Kabarcık grafiği seçtiğimizde ise altı görsel düzeyi filtresinin uygulanmış olduğunu görürüz.

Düzenleme görünümünde filtreler ve vurgulama ile daha fazla işlem gerçekleştirebilirsiniz. Özellikle yeni filtreler ekleyebilirsiniz. [Rapora filtre eklemeyi](power-bi-report-add-filter.md) ve çok daha fazlasını öğrenin.

## <a name="ad-hoc-highlighting"></a>Anlık vurgulama
Sayfadaki diğer görselleri vurgulamak için rapor tuvalinde bir alan seçin. Filtreleme ve vurgulamayı kaldırmak için aynı görselde boş bir alan seçin. Bu türdeki vurgulama işlemleri, veri etkilerini hızla keşfetmenin eğlenceli bir yoludur. [Görsel etkileşimler](consumer/end-user-interactions.md) makalesine giderek bu türdeki çapraz vurgulama işlemlerinin nasıl çalıştığına ilişkin ayrıntılara ulaşabilirsiniz.

![](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)


## <a name="next-steps"></a>Sonraki adımlar
[Bir rapora filtre ekleme (Düzenleme görünümünde)](power-bi-report-add-filter.md)

[Rapor filtrelerine ilişkin bir tura katılın](consumer/end-user-report-filter.md)

[Rapor görsellerinin birbirini çapraz filtreleme ve çapraz vurgulama şeklini değiştirme](consumer/end-user-interactions.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

