---
title: Power BI Embedded analizinin bir parçası olarak açıklanan Power BI Embedded oluşturma 2
description: Power BI Embedded Analytics 'te Power BI Embedded oluşturma 2 teklifi hakkında bilgi edinin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
ms.date: 02/03/2021
ms.openlocfilehash: fa72ab380cac1a1ac6d12cb431bdacfb5964ee83
ms.sourcegitcommit: c33e53e1fab1f29872297524a7b4f5af6c806798
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2021
ms.locfileid: "99534506"
---
# <a name="power-bi-embedded-generation-2-preview"></a>Power BI Embedded 2. nesil (Önizleme)

Power BI Embedded son zamanlarda Power BI Embedded, **Power BI Embedded 2. nesil** yeni bir sürümünü kullanıma sundu.  Katıştırılmış Gen2 Şu anda önizlemededir ve önizleme döneminde kullanılmak üzere eklenmiş aboneler için kullanılabilir. Power BI Embedded kaynağın özgün sürümünü oluşturmaya devam edebilir, *gömülü Gen 1* adı verilir veya yeni bir *Embedded Gen 2* kaynağı oluşturabilirsiniz. Önizleme dönemi boyunca her iki tür Power BI Embedded kapasitesini paralel olarak çalıştırabilir ve herhangi bir çalışma alanını Gen1 veya Gen2 kapasitesine atayabilirsiniz.

Kapasiteyi duraklatma ve sürdürme gibi Power BI Embedded Gen 1 özellikleri, Gen 2 ' de korunur. Ayrıca, Gen 2 kapasite kaynağı aşağıdaki güncelleştirmeleri ve geliştirilmiş deneyimi sağlar:

* **Gelişmiş performans** -her zaman herhangi bir kapasite boyutu üzerinde daha iyi performans. İşlemler her zaman en yüksek hızda gerçekleştirilir ve kapasitedeki yük miktarı kapasite sınırına yaklaştığında yavaşlamaz.

* **Daha büyük ölçekli** , aşağıdaki geliştirmeler de dahil:

    * *Yenileme eşzamanlılık üzerinde sınırlama yok* -artık kapasiteniz üzerinde yenilenmekte olan veri kümelerinin zamanlamalarını izlemenize gerek yok

    * *Daha az bellek kısıtlaması*

    * *Rapor etkileşimi ve zamanlanmış yenilemeler arasında eksiksiz ayrım*

* **Sayfalandırılmış raporlar ve AI iş yükleri Için düşük giriş düzeyi** – bir *a1* SKU 'su ile başlayın ve ihtiyacınız olduğu kadar büyür.

* **Kaynak ölçekleme** Power BI Embedded kaynağınızı anında ölçeklendirin. Dakikalar içinde bir Gen1 kaynağını ölçeklendirerek bir Gen2 kaynağını Saniyeler içinde ölçeklendirin.

* **Kapalı kalma süresi olmadan ölçekleme** -gömülü Gen2, Power BI Embedded kaynağınızı herhangi bir kesinti olmadan ölçeklendirebilirsiniz.

* Açık ve normalleştirilmiş kapasite kullanımı verileri dahil olmak üzere, yalnızca kapasitenin yaptığı analiz işlemlerinin karmaşıklığına bağlı olarak, **geliştirilmiş ölçümler** . Ölçümler, kapasitenin boyutu ve analiz gerçekleştirilirken sistemdeki yükün düzeyi gibi diğer faktörlerden etkilenmez. Geliştirilmiş ölçümler kullanılırken, yerleşik raporlama aracı şunları açıkça görmenizi sağlar:
    * Kullanım Analizi
    * Bütçe planlaması
    * Ücret
    * Kapasitenizi yükseltme ihtiyacı

    >[!NOTE]
    >İyileştirilmiş ölçümler sonra önizleme süresinde daha sonra kullanıma sunulacaktır. Son yedi güne ait kullanım ölçümlerine erişim arayan müşteriler, müşteri desteğiyle iletişim kurarak bunu yapabilir.

## <a name="using-embedded-gen2"></a>Gömülü Gen2 kullanma

Güncelleştirmelerinden yararlanmak için gömülü bir Gen2 kapasite kaynağı oluşturun. Gömülü bir Gen2 kapasitesi kaynağı oluşturmak için, [Azure portal Power BI Embedded kapasite oluşturma](azure-pbie-create-capacity.md)bölümündeki yönergeleri izleyin.

## <a name="known-limitations"></a>Bilinen sınırlamalar

* Ekli Gen2 kapasitesi kullanımı, [ölçüm](../../admin/service-admin-premium-monitor-capacity.md)uygulamasında izlenemez. Daha fazla bilgi için bkz. [Premium Gen2 Monitor Updates](../../admin/service-premium-what-is.md#updates-for-premium-gen2-preview-2).

* Belirli iş yükleri için bellek ayırma ayarları gömülü Gen2 kapasiteye uygulanmaz. Daha fazla bilgi için bkz. [ekli Gen 2 bellek geliştirmeleri](embedded-capacity.md#embedded-gen-2-memory-enhancements-preview)

* Gömülü Gen2 ile XMLA kullanıyorsanız, veri modelleme ve yönetim araçlarının en son sürümlerini kullandığınızdan emin olun.

* Katıştırılmış Gen2 içindeki Analysis Services özellikleri yalnızca en son istemci kitaplıklarında desteklenir. Bu gereksinimi desteklemeye yönelik bağımlı araçların tahmini yayın tarihleri [Premium Gen2 'Daki bilinen sınırlamalar](../../admin/service-premium-what-is.md#known-limitations-in-premium-gen2)bölümünde listelenmiştir.

* Power BI Embedded için tüm geçerli Azure ölçümleri ve günlük tanılama, yalnızca Gen1 kapasitelerin desteklenmesi desteklenir.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Azure portalda Power BI Embedded kapasitesi oluşturma](azure-pbie-create-capacity.md)

> [!div class="nextstepaction"]
> [Power BI tümleşik analizinde kapasite ve SKU’lar](embedded-capacity.md)

> [!div class="nextstepaction"]
> [Power BI Premium nedir?](../../admin/service-premium-what-is.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)