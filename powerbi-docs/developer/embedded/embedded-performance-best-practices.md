---
title: Performans açısından en iyi Power BI Embedded yöntemleri
description: Bu makalede en iyi tümleşik analiz yöntemlerine yönelik rehberlik sağlanır
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: c619f37ac062eec02eb379ba7cd97731254a171a
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279400"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Performans açısından en iyi Power BI Embedded yöntemleri

Bu makalede uygulamanızdaki raporları, panoları ve kutucukları daha hızlı işlemeye yönelik öneriler sağlanır.

> [!Note]
> Yükleme süresinin temel olarak raporla ilgili öğelere ve görsellerin, verilerin boyutuna ve sorgu ve hesaplanan ölçülere ilişkin karmaşıklığa bağlı olduğunu unutmayın. Daha fazla bilgi için bkz. [Power BI iyileştirme kılavuzu](../../guidance/power-bi-optimization.md).

## <a name="update-tools-and-sdk-packages"></a>Araçları ve SDK paketlerini güncelleştirme

Araçların ve SDK paketlerinin güncel kalmasını sağlayın.

* Her zaman [Power BI Desktop](https://powerbi.microsoft.com/desktop/)'ın en son sürümünü kullanın.

* [Power BI istemci SDK'sının](https://github.com/Microsoft/PowerBI-JavaScript) en son sürümünü yükleyin. Sürekli başka iyileştirmeler yayınlama devam ediyoruz, bu nedenle zaman zaman takip etmeyi unutmayın.

## <a name="embed-parameters"></a>Ekleme parametreleri

`powerbi.embed(element, config)` yöntemi bir öğe ve bir yapılandırma alır. Yapılandırma parametresi, performans etkilerine sahip alanlar içerir.

### <a name="embed-url"></a>Ekleme URL'si

Ekleme URL'sini kendiniz oluşturmaktan kaçının. Bunun yerine, [Get reports](/rest/api/power-bi/reports/getreportsingroup), [Get dashboards](/rest/api/power-bi/dashboards/getdashboardsingroup) veya [Get tiles](/rest/api/power-bi/dashboards/gettilesingroup) API'sini çağırarak Ekleme URL'sini aldığınızdan emin olun. Performans geliştirmeleri için kullanmak üzere URL'ye **_config_** adlı yeni bir parametre ekledik.

### <a name="permissions"></a>İzinler

Raporu Düzenleme modunda eklemeyi düşünmüyorsanız, **Görüntüleme** izinleri sağlayın. Bu şekilde, ekleme kodu düzenleme modunda kullanılan bileşenleri başlatmaz.

### <a name="filters-bookmarks-and-slicers"></a>Filtreler, yer işaretleri ve dilimleyiciler

Genellikle, rapor görselleri önbelleğe alınmış verilerle birlikte kaydedilir. Önbelleğe alınmış veriler, algılanan performansı vermek için kullanılır. Sorgular yürütülürken raporlar önbelleğe alınmış verileri işler. Filtreler, yer işaretleri veya dilimleyiciler sağlanmışsa, önbelleğe alınmış veriler ilgili değildir ve görseller yalnızca görsel sorgusu sona erdikten sonra işlenir.

Aynı filtre, yer işareti ve dilimleyicilerle rapor eklerseniz, performansı artırmak için raporu daha önce uygulanan filtre, yer işareti ve dilimleyicilerle kaydedin. Bunun yapılması, raporu filtreler, yer işaretleri ve dilimleyicileri içeren önbelleğe alınmış verilerle birlikte oluşturur.

## <a name="switching-between-reports"></a>Raporlar arasında geçiş yapma

Aynı iframe’e birden fazla rapor eklerken her rapor için yeni bir iframe oluşturmayın. Bunun yerine, yeni raporu eklemek için farklı bir yapılandırmaya sahip olan `powerbi.embed(element, config)` kullanın.

> [!NOTE]
> 'Uygulama verilerin sahibidir' senaryosu için raporlar arasında geçiş yapmak, yeni bir ekleme belirteci oluşturma gerekliliği nedeniyle çok etkili olmayabilir.

## <a name="query-caching"></a>Sorgu önbelleğe alma

Power BI Premium kapasitesi veya Power BI Embedded kapasitesi ile kuruluşlar bir veri kümesiyle ilişkili raporları hızlandırmak için sorguları önbelleğe alma özelliğinden yararlanabilir.

[Power BI’da sorgu önbelleğe alma hakkında daha fazla bilgi edinin](../../connect-data/power-bi-query-caching.md).

## <a name="preload"></a>Önceden yükleme

Son kullanıcı performansını iyileştirmek için `powerbi.preload()` kullanın. `powerbi.preload()` yöntemi, daha sonra raporu ekleme amacıyla kullanılacak javascript kodlarını, css dosyalarını ve diğer yapıtları indirir.

Raporu hemen eklemiyorsanız `powerbi.preload()` çağrısı yapın. Örneğin, Power BI Embedded içeriği giriş sayfasında görünmezse, içeriği eklemek için kullanılan yapıtları indirmek ve önbelleğe almak için `powerbi.preload()` kullanın.

## <a name="bootstrapping-the-iframe"></a>Iframe'i önyükleme

> [!NOTE]
> Iframe’i önyüklemek için [Power BI istemci SDK’sı](https://github.com/Microsoft/PowerBI-JavaScript) sürüm 2.9 gereklidir.

`powerbi.bootstrap(element, config)`, gerekli tüm parametreler kullanılabilir olmadan önce eklemeye başlamanızı sağlar. Önyükleme API’si, iframe’i hazırlar ve başlatır.
Önyükleme API’sini kullanırken, aynı HTML öğesinde `powerbi.embed(element, config)` çağrısı yapılması yine de gereklidir.

Örneğin, bu özelliğin kullanım örneklerinden birinde, iframe önyüklemesi ve ekleme için arka uç çağrıları paralel olarak çalıştırılır.
> [!TIP]
> Iframe’i son kullanıcıya görüntülenmeden önce oluşturmanızın mümkün olduğu durumlarda önyükleme API’sini kullanın.

[Iframe önyüklemesi hakkında daha fazla bilgi edinin](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bootstrap-For-Better-Performance).

## <a name="measure-performance"></a>Performansı ölçme

### <a name="performance-events"></a>Performans olayları

Gömülü performansı ölçmek için iki olayı kullanabilirsiniz:

1. Yüklendi olayı: Rapor başlatılmadan önce geçen süre (yükleme tamamlandığında Power BI logosu kaybolur).
2. İşlendi olayı: Rapor gerçek veriler kullanılarak tamamen işlenene kadar geçen süre. Rapor yeniden her işlendiğinde (örneğin, filtreler uygulandıktan sonra), İşlendi olayı tetiklenir. Raporu ölçmek için, hesaplamaları ilk tetiklenen olayda yaptığınızdan emin olun.

Önbelleğe alınmış veriler kullanılabilir olduğunda işlenir ancak başka bir olay oluşturulmaz.

[Olay işleme hakkında daha fazla bilgi edinin](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

### <a name="performance-analyzer"></a>Performans Analizi

Rapor öğelerinin performansını incelemek için Power BI Desktop'ta Performans Analizi'ni kullanabilirsiniz.
Performans Analizi, rapor öğelerinizin her birinin nasıl performans gösterdiğini ölçen günlükleri görüp kaydetmenize izin verir.

[Performans Analizi hakkında daha fazla bilgi edinin](../../create-reports/desktop-performance-analyzer.md).

> [!NOTE]
> Her zaman ekli rapor performansını powerbi.com üzerindeki performansla karşılaştırmayı unutmayın. Bunun yapılması, performans sorunlarınızın kaynağını anlamanıza yardımcı olur

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI iyileştirme kılavuzu](../../guidance/power-bi-optimization.md)
* [Power BI Embedded sorunlarını giderme](embedded-troubleshoot.md)
* [Power BI Embedded SSS](embedded-faq.md)
