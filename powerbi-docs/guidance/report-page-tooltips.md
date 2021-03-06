---
title: Rapor sayfası araç ipuçlarıyla görselleri genişletme
description: Rapor sayfası araç ipuçlarıyla çalışma yönergeleri.
author: peter-myers
ms.author: kfollis
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 11/24/2019
ms.openlocfilehash: 1adb33dbff1de368d8d9b98ff0e7ad5f5f88387c
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99087856"
---
# <a name="extend-visuals-with-report-page-tooltips"></a>Rapor sayfası araç ipuçlarıyla görselleri genişletme

Bu makale Power BI raporları tasarlayan rapor yazarlarına yöneliktir. [Rapor sayfası araç ipuçları](../create-reports/desktop-tooltips.md) oluşturma işlemiyle ilgili öneriler sağlar.

## <a name="suggestions"></a>Öneriler

Rapor sayfası araç ipuçları, rapor kullanıcılarınızın deneyimini geliştirebilir. Sayfa araç ipuçları rapor kullanıcılarınızın görselden hızla ve verimli bir şekilde daha derin içgörüler elde etmesine olanak tanır. Bunlar farklı rapor nesneleriyle ilişkilendirilebilir:

- **Görseller:** Tek tek görseller temelinde, hangi görsellerin sayfa araç ipucunu göstereceğini yapılandırabilirsiniz. Her görselde, görselin hiç araç ipucu göstermemesini sağlamak, görsel araç ipuçlarını varsayılan olarak kullanmak (görsel alanları bölmesinde yapılandırılır) veya belirli bir sayfa araç ipucunu kullanmak mümkündür.
- **Görsel üst bilgileri:** Belirli görselleri sayfa araç ipucunu görüntüleyecek şekilde yapılandırabilirsiniz. Rapor kullanıcılarınız imleci görsel üst bilgisi simgesinin üzerine getirerek sayfa araç ipucunu ortaya çıkarabilir. Kullanıcılarınıza bu simgeyi öğrettiğinizden emin olun.

> [!NOTE]
> Rapor görselinin bir sayfa araç ipucunu görüntüleyebilmesi için araç ipucu sayfa filtrelerinin görselin tasarımıyla uyumlu olması gerekir. Örneğin _ürüne_ göre gruplandıran bir görsel _ürüne_ göre filtreleyen araç ipucu sayfasıyla uyumludur.
>
> Sayfa araç ipuçları etkileşimli çalışmayı desteklemez. Rapor kullanıcılarınızın etkileşim kurmasını istiyorsanız bunun yerine [detaylandırma sayfası](../create-reports/desktop-drillthrough.md) oluşturun.
>
> Power BI görselleri, sayfa araç ipuçlarını desteklemez.

İşte önerilen bazı tasarım senaryoları:

- [Farklı bir perspektif](#different-perspective)
- [Ayrıntı ekleme](#add-detail)
- [Yardım ekleme](#add-help)

### <a name="different-perspective"></a>Farklı bir perspektif

Sayfa araç ipucu, kaynak görselle aynı verileri görselleştirebilir. Bu, aynı görsel veya özetleme grupları ya da farklı görsel türleri kullanılarak yapılabilir. Sayfa araç ipuçları, kaynak görsele uygulanan filtrelerden farklı filtreler de uygulayabilir.

Aşağıdaki örnekte rapor kullanıcısı imlecini **EnabledUsers** değerinin üzerine getirdiğinde neler olduğu gösterilir. Değerin filtre bağlamı November 2018 (Kasım 2018) tarihli Yammer'dır.

![Matris görseli satırlarda yıla ve aya göre gruplandırılmış bir değerler kılavuzu görüntüler. Rapor kullanıcısı imlecini tek bir değerin üzerine getirir. Sayfa araç ipucu görüntülenir.](media/report-page-tooltips/suggestion-different-perspective.png)

Sayfa araç ipucu ortaya çıkarılır. Farklı bir veri görseli (çizgi ve kümelenmiş sütun grafiği) sunar ve çakışan bir zaman filtresi uygular. Veri noktası için filtre bağlamının November 2018 olduğuna dikkat edin. Sayfa araç ipucu ise _tam bir yılın ayları_ boyunca ortaya çıkan eğilimi görüntüler.

### <a name="add-detail"></a>Ayrıntı ekleme

Sayfa araç ipucu ek ayrıntılar görüntüleyebilir ve bağlam ekleyebilir.

Aşağıdaki örnekte rapor kullanıcısı imlecini 98022 posta kodu için **Average of Violation Points** değerinin üzerine getirdiğinde neler olduğu gösterilir.

![Tablo görseli değer ızgarasını görüntüler ve tablo üç sütun içerir. Sayfa araç ipucu görüntülenir.](media/report-page-tooltips/suggestion-add-details.png)

Sayfa araç ipucu ortaya çıkarılır. 98022 posta koduna ilişkin belirli öznitelikleri ve istatistikleri sunar.

### <a name="add-help"></a>Yardım ekleme

Görsel üst bilgileri sayfa araç ipuçlarını görsel üst bilgilerinde ortaya çıkaracak şekilde yapılandırılabilir. Zengin biçimlendirilmiş metin kutuları kullanarak sayfa araç ipucuna yardım belgeleri ekleyebilirsiniz. Resimler ve şekiller eklemek de mümkündür.

Burada ilginç olan düğmelerin, resimlerin, metin kutularının ve şekillerin de bir görsel üst bilgisi sayfa araç ipucunu ortaya çıkarabilmesidir.

Aşağıdaki örnekte rapor kullanıcısı imlecini [görsel üst bilgisi simgesinin](../create-reports/desktop-visual-elements-for-reports.md) üzerine getirdiğinde neler olduğu gösterilir.

![Rapor kullanıcısı imlecini görsel üst bilgisi simgesinin (soru işareti simgesi) üzerine getirmiştir. Zengin biçimlendirilmiş bir araç ipucu gösterilir.](media/report-page-tooltips/suggestion-add-help.png)

Sayfa araç ipucu ortaya çıkarılır. Zengin biçimlendirilmiş metin dört metin kutusunda ve bir şekilde (çizgi) gösterir. Sayfa araç ipucu görselde görüntülenen her kısaltmayı açıklayarak yardım sağlar.

## <a name="recommendations"></a>Öneriler

Rapor tasarımı sırasında aşağıdaki uygulamaları öneririz:

- **Sayfa boyutu:** Sayfa araç ipucunuzu küçük olacak şekilde yapılandırın. Yerleşik **Araç İpucu** seçeneğini (320 piksel genişliğinde, 240 piksel yüksekliğinde) kullanabilirsiniz. İsterseniz özel boyutlar da ayarlayabilirsiniz. Fazla büyük bir sayfa boyutu kullanmamaya dikkat edin çünkü kaynak sayfadaki görselliğin üstünü kapatabilir.
- **Sayfa görünümü:** Rapor tasarımcısında sayfa görünümünü **Gerçek Boyut** olarak ayarlayın (sayfa görünümünün varsayılan değeri **Sayfaya Sığdır**'dır). Bu şekilde sayfa araç ipucunu tasarlarken gerçek boyutu görebilirsiniz.
- **Stil:** Sayfa araç ipucunuzu raporla aynı temayı ve stili kullanarak tasarlamayı göz önünde bulundurun. Bu şekilde kullanıcılar raporun dışına çıkmamış gibi hissedebilirler. Öte yandan araç ipuçlarınız için tamamlayıcı bir stil tasarlayabilir ve tüm sayfa araç ipuçlarına bu stili uygulamaya özen gösterebilirsiniz.
- **Araç ipucu filtreleri:** Tasarımını yaparken gerçekçi bir önizleme sonucu elde edebilmek için sayfa araç ipucuna filtreler atayın. Raporunuzu yayımlamadan önce bu filtreleri kaldırmayı unutmayın.
- **Sayfa görünürlüğü:** Araç ipucu sayfalarını her zaman gizleyin; kullanıcıların bunlara doğrudan gidememeleri gerekir.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Desktop’ta rapor sayfalarına dayalı olarak araç ipuçları oluşturma](../create-reports/desktop-tooltips.md)
- [Power BI Desktop'taki araç ipuçlarını özelleştirme](../create-reports/desktop-custom-tooltips.md)
- [Görsel öğeler kullanarak Power BI raporlarını geliştirme](../create-reports/desktop-visual-elements-for-reports.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
