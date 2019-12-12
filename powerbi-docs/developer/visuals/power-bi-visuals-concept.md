---
title: Power BI görsel kavramı
description: Bu makalede görselin Power BI'yla nasıl tümleştirildiği açıklanır
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 36742917829013a6efca9d74f88b01bc686437a8
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700858"
---
# <a name="power-bi-visual-concept"></a>Power BI görsel kavramı

Bu makalede bir kullanıcı ve görselin Power BI ile nasıl etkileşim kurduğu ve bir kullanıcının Power BI görseliyle nasıl etkileşim kurduğu anlatılır. Diyagrama hangi eylemlerin görseli doğrudan veya Power BI aracılığıyla etkilediğini (örneğin, kullanıcının yer işaretlerini seçmesi) görüyorsunuz.

![Power BI görseli](./media/visual-concept.svg)

## <a name="the-visual-gets-update-from-power-bi"></a>Görsel Power BI'dan güncelleştirilir

Görselin `update` yöntemi vardır ve bu yöntem genellikle görselin ana mantığını içerir ve grafiğin işlenmesinden veya verilerin görselleştirilmesinden sorumludur.

Güncelleştirmelerin daha çoğu `update` yönteminin çağrısına gelir.

### <a name="user-interacts-with-visual-through-power-bi"></a>Kullanıcı görselle Power BI aracılığıyla etkileşim kurar

* Kullanıcı görsel özellikleri panelini açar.

    Power BI görselin `capabilities.json` dosyasından desteklenen nesnelerle özellikleri getirir ve özelliklerin gerçek değerlerini almak için Power BI görselin `enumerateObjectInstances` yöntemini çağırır.

    Görselin, özelliklerin gerçek değerlerini döndürmesi gerekir.

    Daha fazla bilgi için [görsel özellikleri konusunu okuyun](capabilities.md).

* Biçim panelinde [kullanıcı görselin özelliğini değiştirir](../../visuals/power-bi-visualization-customize-title-background-and-legend.md).

    Özelliğin değeri değiştirildikten sonra Power BI görselin `update` yöntemini çağırır ve yeni `options` nesnesini nesnelerin yeni değerleriyle update yöntemine geçirir.

    Daha fazla bilgi için [görselin nesneleri ve özellikleri konusunu okuyun](objects-properties.md).

* Kullanıcı görseli yeniden boyutlandırır.

    Kullanıcı görselin boyutunu değiştirdiğinde Power BI yeni `option` nesnesiyle `update` yöntemini çağırır. Seçeneklerde görselin yeni genişliği ve yüksekliğiyle iç içe `viewport` nesnesi vardır.

* Kullanıcı rapor, sayfa veya görsel düzeyi filtresi uygular.

    Power BI verileri filtre koşullarına göre filtreler ve görsele yeni verileri vermek için görselin `update` yöntemini çağırır.

    Görsel iç içe nesnelerden birindeki yeni verilerle yeni `options` güncelleştirmesini alır. Bu görselin veri görünümü eşleme yapılandırmasına bağlıdır.

    Daha fazla bilgi için [veri görünümü eşlemeleri konusunu okuyun](dataview-mappings.md).

* Kullanıcı raporun başka bir görselindeki veri noktasını seçer.

    Power BI seçilen veri noktalarını filtreler veya vurgular ve görselin `update` yöntemini çağırır.

    Görsel yeni filtrelenmiş verileri veya vurgu dizileriyle birlikte aynı verileri alır.

    Daha fazla bilgi için [görsellerdeki verileri vurgulama konusunu okuyun](highlight.md).

* Kullanıcı raporun yer işaretleri panelinde yer işaretini seçer.

    Burada iki eylem gerçekleştirilebilir:

    1. Power BI `registerOnSelectionCallback` yöntemi tarafından kaydedilip geçirilen işlevi çağırır ve geri çağırma işlevi ilgili yer işaretinin seçim dizilerini alır.

    2. Power BI `options` içindeki ilgili filtre nesnesiyle `update` yöntemini çağırır.

    Her iki durumda da görselin alınan seçimler veya filtre nesnesine göre görselleştirme durumunu değiştirmesi gerekir.

    Yer işaretleri hakkındaki diğer ayrıntılar için [yer işaretlerini işleme konusunu okuyun](filter-api.md).

    Filtreler hakkında daha fazla bilgi için [Power BI görsellerinin diğer görsellerdeki verileri nasıl filtreleyebildiği konusunu okuyun](filter-api.md).

### <a name="user-interacts-with-visual-directly"></a>Kullanıcı görselle doğrudan etkileşim kurar

* Kullanıcı fareyi veri öğesinin üzerine getirir

    Görsel, Power BI Araç İpuçları API'si aracılığıyla veri noktası hakkında ek bilgiler görüntüleyebilir.
    Kullanıcı fareyi görsel öğesinin üzerine getirir, görsel olayı işleyebilir ve araç ipucu öğesinde verileri görüntüleyebilir.

    Görsel standart araç ipucunu veya rapor sayfası ipucunu görüntüleyebilir.

    Daha fazla bilgi için [araç ipuçlarını ekleme](add-tooltips.md) kılavuzunu okuyun.

* Kullanıcı görsel özelliklerini değiştirir (örneğin, kullanıcı ağacı genişletir ve görsel durumu özelliklere kaydeder)

    Görsel Power BI API'si aracılığıyla özellik değerlerini kaydedebilir. Örneğin kullanıcı görselle etkileşim kurduğunda, görselin özellik değerlerini kaydetmesi veya güncelleştirmesi gerekebilir. Görsel bunun için `presistProperties` yöntemini çağırabilir.

* Kullanıcı URL bağlantısına tıklar.

    Varsayılan olarak görsel URL'yi açamaz. URL'yi yeni sekmede açmak için görselin `launchURL` yöntemini çağırması ve URL'yi parametre olarak geçirmesi gerekir.

    Daha fazla bilgi için bkz. [URL API'sini başlatma](launch-url.md).

* Kullanıcı görseli oluşturan filtreyi uygular

    Görsel `applyJSONFilter` yöntemini çağırarak ve filtre koşullarını filtreye geçirerek başka bir görseldeki verileri filtreler.

    Görsel Temel filtre, Gelişmiş filtre ve Tanımlama grubu filtresi gibi çeşitli türlerde filtre kullanabilir.

    Filtreler hakkında daha fazla bilgi için [Power BI görsellerinin diğer görsellerdeki verileri nasıl filtreleyebildiği konusunu okuyun](filter-api.md).

* Kullanıcı görseldeki öğeleri tıklar/seçer.

    Seçimler hakkında daha fazla bilgi için [görselin nasıl etkileşim kurduğu konusunu okuyun](selection-api.md).

### <a name="the-visual-interacts-with-power-bi"></a>Görsel Power BI ile etkileşim kurar

* Görsel Power BI'dan daha fazla veri ister.

    Görsel verileri parçalar halinde işleyebilir. FetchMoreData API yöntemi veri kümesinin sonraki parçası için istekte bulunur.

    `fetchMoreData` hakkında daha fazla bilgi için [Power BI'dan daha fazla veri getirme konusunu okuyun](fetch-more-data.md)

* Olay hizmeti

    Power BI raporları PDF'ye aktarabilir veya e-postayla gönderebilir (Yalnızca sertifikalı görseller desteklenir). Power BI'a işlemenin tamamlandığını ve PDF/e-posta ile yakalamaya hazır olduğunu bildirmek için görselin Olayları İşleme API'sini çağırması gerekir.

    Daha fazla bilgi için [raporları Power BI'dan PDF'ye dışarı aktarma konusunu okuyun](../../consumer/end-user-pdf.md)

    [Olay Hizmeti'yle ilgili daha fazla bilgi](event-service.md) bulabilirsiniz

## <a name="next-steps"></a>Sonraki adımlar

Bir Web geliştiricisi olarak kendi görselleştirmelerinizi oluşturmak ve bunları AppSource'a eklemek mi istiyorsunuz? [Power BI Görseli geliştirme](./custom-visual-develop-tutorial.md) makalesini inceleyin ve [AppSource’ta Power BI görselleri yayımlamayı](../office-store.md) öğrenin.
