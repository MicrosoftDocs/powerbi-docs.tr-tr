---
title: Power BI raporlarındaki filtreler ve vurgulama
description: Power BI raporlarındaki filtreler ve vurgulama hakkında
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: conceptual
ms.date: 01/29/2021
LocalizationGroup: Reports
ms.openlocfilehash: 572bbc8b24fc3ebf8ee2890480eff25eab87d37d
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99087833"
---
# <a name="filters-and-highlighting-in-power-bi-reports"></a>Power BI raporlarındaki filtreler ve vurgulama
 Bu makalede, Power BI hizmetindeki filtreleme ve vurgulama özellikleri tanıtılmaktadır. Power BI Desktop ile sunulan deneyim de neredeyse aynıdır. *Filtreler*, odaklanmak istedikleriniz dışındaki tüm verileri kaldırır. Genel olarak, *vurgulama* filtrelememez. Çoğu görselde, ilgisiz verileri kaldırmaz. Bunun yerine, ilgili verilerin alt kümesini vurgular. Verilerin geri kalanı görünür kalır ancak soluk kalır. Ayrıntılar için bu makalenin ilerleyen kısımlarında geçici [filtreleme ve çapraz vurgulama](#ad-hoc-cross-filtering-and-cross-highlighting) bölümüne bakın.

Power BI'da raporları çok çeşitli yollarla filtreleyebilir ve vurgulayabilirsiniz. Tüm bu bilgilerin tek bir makalede ele alınması karmaşıklık yaratacağından tüm konuyu aşağıdaki şekilde bölümlere ayırmayı tercih ettik:

* Filtrelere ve vurgulamaya giriş (şu anda okuduğunuz makale).
* Power BI Desktop ve Power BI hizmetindeki raporlarda [Düzenleme görünümünde filtre oluşturma ve kullanma](power-bi-report-add-filter.md) Düzenleme izinlerine sahip olmanız halinde raporlarda filtre oluşturabilir, bunları değiştirebilir ve silebilirsiniz.
* Power BI hizmetindeki rapor Okuma görünümünde, [bir rapordaki filtre ve vurgulama görselleri sizinle nasıl paylaşılır](../consumer/end-user-interactions.md). Yapabilecekleriniz daha sınırlıdır ancak yine de çok çeşitli filtreleme ve vurgulama seçeneklerine sahip olursunuz.  
* Power BI Desktop ve Power BI hizmetinde [Düzenleme görünümünde kullanılabilir olan filtreleme ve vurgulama denetimlerinin](power-bi-report-add-filter.md) ayrıntılı turu. Bu makale, tarih ve saat, sayısal ve metin gibi filtre türlerini derinlemesine inceler. Temel ve gelişmiş seçenekler arasındaki farkları da ele alır.
* Filtrelerin ve vurgulamanın varsayılan olarak nasıl çalıştığını öğrendikten sonra [bir sayfadaki görselleştirmelerin birbirini filtreleme ve vurgulama şeklini nasıl değiştireceğinizi öğrenebilirsiniz](service-reports-visual-interactions.md)

**Biliyor muydunuz?** Power BI yeni bir filtre deneyimine sahiptir. [Power BI raporlarında yeni filtre deneyimi](power-bi-report-filter.md) hakkında daha fazla bilgi edinin.

![Yeni filtre deneyimi](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading.png)


## <a name="intro-to-the-filters-pane"></a>Filtreler bölmesine giriş

Filtreleri **Filtreler** bölmesinden veya doğrudan rapor üzerindeki [dilimleyicilerde seçim yaparak](../visuals/power-bi-visualization-slicers.md) uygulayabilirsiniz. Filtreler bölmesi, raporda kullanılan tabloların ve alanların yanı sıra uygulanan filtreleri (varsa ) gösterir. 

![Filtreler bölmesi](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Dört tür filtre vardır.

- **Sayfa filtresi**, rapor sayfasındaki tüm görsellere uygulanır     
- **Görsel filtresi** , bir rapor sayfasındaki tek bir görsel için geçerlidir. Rapor tuvalinde bir görsel seçtiyseniz yalnızca görsel düzeyi filtrelerini görürsünüz.    
- **Rapor filtresi**, rapordaki tüm sayfalara uygulanır    
- **Detaylandırma filtresi**, bir rapordaki tek bir varlığa uygulanır    

Okuma veya Düzenleme görünümünde sayfa, görsel ve rapor filtrelerinde arama yaparak istediğiniz değeri bulabilir ve seçebilirsiniz. 

![Filtrede arama yapma](media/power-bi-reports-filters-and-highlighting/power-bi-search-filter.png)

Filtrenin yanında **Tümü** ifadesinin bulunması, alandaki tüm değerlerin filtreye dahil edilmiş olduğunu gösterir.  Örneğin, aşağıdaki ekran görüntüsünde **Chain (Tümü)**, bu rapor sayfasının tüm mağaza zincirleriyle ilgili verileri içerdiğini gösterir.  Diğer yandan, **FiscalYear 2013 veya 2014 değeridir** rapor düzeyi filtresi, bize raporun yalnızca 2013 ve 2014 mali yıllarına ilişkin verileri içerdiğini gösterir.

## <a name="filters-in-reading-or-editing-view"></a>Okuma veya Düzenleme görünümündeki filtreler
Raporlarla etkileşim kurmak için kullanabileceğiniz iki mod vardır: [Okuma görünümü ve Düzenleme görünümü](../consumer/end-user-reading-view.md). Kullanabileceğiniz filtreleme özellikleri hangi modda olduğunuza bağlıdır.

* Düzenleme görünümünde, rapor, sayfa, detaylandırma ve görsel filtreler ekleyebilirsiniz. Raporu kaydettiğinizde, mobil uygulamada açsanız bile filtreler raporla birlikte kaydedilir. Okuma görünümünde rapora göz atan kişiler eklediğiniz filtrelerle etkileşim kurabilir ancak yeni filtreler ekleyemez.
* Okuma görünümünde önceden raporda bulunan filtrelerle etkileşim kurabilir ve yaptığınız seçimi kaydedebilirsiniz. Yeni filtre ekleyemezsiniz.

### <a name="filters-in-reading-view"></a>Okuma görünümündeki filtreler
Bir rapora yalnızca Okuma görünümünde erişim sahibiyseniz Filtreler bölmesi aşağıdaki gibi görünür:

![Okuma görünümündeki filtreler](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Raporun bu sayfasında altı sayfa düzeyi filtresi ile bir rapor düzeyi filtresi bulunur.

Bir görselde bulunan tüm alanlara filtre uygulanmış olabilir ve rapor yazarı daha fazla filtre ekleyebilir. Aşağıdaki görüntüde, kabarcık grafiğinde altı filtre vardır.

![Görsel düzeyde filtre](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

Okuma görünümünde, mevcut filtreleri değiştirerek verileri araştırabilirsiniz. Raporu mobil uygulamada açsanız bile, yaptığınız değişiklikler rapora kaydedilir. Nasıl yapıldığını öğrenmek için [Power BI Filtreler bölmesine ilişkin tura katılın](../consumer/end-user-report-filter.md)

Siz rapordan çıkarken filtreleriniz kaydedilir. Filtreleme işlemini geri almak ve rapor yazarı tarafından ayarlanan varsayılan filtreleme, dilimleme, detaylandırma ve sıralamaya geri dönmek için, üst menü çubuğundan **Varsayılana sıfırla**’yı seçin.

![Varsayılana sıfırla simgesi](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

### <a name="filters-in-editing-view"></a>Düzenleme görünümündeki filtreler
Bir rapor için sahip izinleriniz olduğunda ve raporu Düzenleme görünümünde açtığınızda **Filtreler**'in, kullanılabilir birkaç düzenleme bölmesinden yalnızca biri olduğunu görürsünüz.

![Düzenleme Görünümü'nde filtreler bölmesi](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Okuma görünümünde olduğu gibi raporun bu sayfasında da altı sayfa düzeyi filtresi ile bir rapor düzeyi filtresi bulunur. Kabarcık grafiği seçtiğimizde ise altı görsel düzeyi filtresinin uygulanmış olduğunu görürüz.

Düzenleme görünümünde filtreler ve vurgulama ile daha fazla işlem gerçekleştirebilirsiniz. Özellikle yeni filtreler ekleyebilirsiniz. [Rapora filtre eklemeyi](power-bi-report-add-filter.md) ve çok daha fazlasını öğrenin.

## <a name="ad-hoc-cross-filtering-and-cross-highlighting"></a>Geçici çapraz filtreleme ve çapraz vurgulama
Çapraz filtrelemek için bir görselde bir değer veya eksen etiketi seçin veya sayfadaki diğer görsellerdeki ilgili değerleri çapraz olarak vurgulayın. Çoğu görselde, bir görselde bir değer seçmek diğer görsellerdeki ilgisiz verileri kaldırmaz. Bunun yerine, ilgili verilerin alt kümesini vurgular. İlişkisiz veriler görünür kalır ancak soluk kalır. Ancak, bazı görsellerde bir görselde bir değer seçmek diğer görsellerde bir filtre gibi davranır. Örneğin, çizgi grafiklerde ve dağılım grafiklerinde yalnızca ilgili veriler görünür kalır. İlişkisiz veriler, tıpkı bir filtreyle gördüğünüz gibi görünmez. 

Vurgulamayı kaldırmak için değeri yeniden seçin veya aynı görselde herhangi bir boş alanı seçin. Vurgulama, veri etkilerini hızla keşfetmenin eğlenceli bir yoludur. Daha fazla örnek için, "bir Power BI raporundaki görsellerin çapraz filtrelenmesi [ve çapraz vurgulama" bölümüne](../consumer/end-user-interactions.md#cross-filtering-and-cross-highlighting) bakın.

![Çapraz filtrelemeyi ve çapraz vurgulamayı gösteren animasyon.](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)

Rapor düzenleyicileri görsellerin etkileşim yöntemini değiştirebilir. Çapraz vurgulamanın nasıl çalıştığına ilişkin ince ayar yapmak için bkz. [görsellerin raporda nasıl etkileşime gireceğini değiştirme](service-reports-visual-interactions.md).

## <a name="next-steps"></a>Sonraki adımlar

[Power BI raporlarındaki yeni filtre deneyimi](power-bi-report-filter.md)

[Rapora filtre ekleme (Düzen görünümü 'nde)](power-bi-report-add-filter.md)

[Rapor filtrelerine ilişkin bir tura katılın](../consumer/end-user-report-filter.md)

[Raporda bir raporda çapraz filtreleme ve çapraz vurgulama gibi rapor görselleri](../consumer/end-user-interactions.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
