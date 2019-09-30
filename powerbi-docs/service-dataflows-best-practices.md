---
title: Power BI veri akışları için en iyi yöntemler
description: Power BI veri akışları için en iyi yöntemler
author: mohaali
manager: mohaali
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/19/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: c499a83b87eb15031d75974084468f418a17804a
ms.sourcegitcommit: 200291eac5769549ba5c47ef3951e2f3d094426e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71142302"
---
# <a name="dataflows-best-practice"></a>Veri akışları en iyi yöntemi

Bu makale Power BI'da veri akışları tasarlamaya yönelik en iyi yöntemleri sağlar. Veri akışları oluşturmayı öğrenmek için bu kılavuzu kullanabilir, bu uygulamaları kendi veri akışlarınızda kullanabilirsiniz.

> [!NOTE]
> Bu makalede yapılan öneriler kılavuz ilkelerdir. Bu makaledeki her bir en iyi yöntem için, bu kılavuz ilkeden sapmanın yasal nedenleri olabilir. 
> 
> 

### <a name="split-ingestion-and-transformation-to-use-the-enhanced-compute-engine"></a>Veri alımı ve dönüştürmeyi gelişmiş işlem altyapısını kullanacak şekilde bölme

Veri akışları oluştururken, tek bir yerde tüm varlıklar, dönüşümler, birleşimler ve geliştirmelerle tek bir veri akışı oluşturmayı düşünebilirsiniz. Daha küçük veri kümeleri için tek bir veri akışı etkili olabilir. Ancak daha büyük veri birimleriyle çalışırken, birleşimleri veya belirli dönüşümleri gerçekleştirmek bazen kısıtlamalar veya bellek sınırları ile karşılaşabilir. Bu sorunları gidermek için, çok daha büyük veri birimlerine ölçeklendirme yapan Power BI Premium kullanıcılarına yönelik geliştirilmiş bir altyapı yayınlanmıştır. Geliştirilmiş işlem altyapısı yalnızca bağlı veya hesaplanan varlıklara göre çalışır; bu nedenle, veri alımı için ayrı bir veri akışı ve tüm karmaşık birleştirme ve dönüştürmeleri gerçekleştirmek için bağlı bir veri akışı oluşturulurken gelişmiş altyapıdan yararlanılabilir.

Veri akışlarını bölmek, özellikle de azaltma sınırlarına sahip kaynaklarla çalışırken yenileme sorunlarını tanılamak ve hatalarını ayıklamak için faydalıdır.

### <a name="perform-actions-that-can-use-the-enhanced-compute-engine"></a>Gelişmiş işlem altyapısını kullanabilen eylemler gerçekleştirme

Diğer dönüştürme türlerini gerçekleştirmeden önce, birleştirmeleri ve filtre dönüştürmelerini bir hesaplanan varlıkta gerçekleştirerek gelişmiş işlem altyapısını kullandığınızdan emin olun.

### <a name="split-dataflows-when-connecting-to-sharepoint"></a>SharePoint'e bağlanırken veri akışlarını bölme

SharePoint ile çalışırken ve birden çok dosyaya bağlanırken zaman zaman hatalara karşılaşabilirsiniz. SharePoint, güvenilir olmaya ve yanıt vermeye devam ettiğinden emin olmak için istekleri kısıtlar. Sonuç olarak, SharePoint'ten Excel dosyalarına bağlanırken, tüm dosyaları tek bir veri akışında indirmek isteyebilirsiniz. 20'den fazla dosya indiriyorsanız, yenileme yükünü ayırmak için iki veya daha fazla veri akışı oluşturun ve SharePoint kısıtlamasını aşın.

### <a name="avoid-scheduling-refresh-for-linked-entities-inside-the-same-workspace"></a>Aynı çalışma alanındaki bağlı varlıklar için yenilemeyi zamanlamasından kaçının

Bağlı varlıkları içeren veri akışlarınıza erişmeniz düzenli olarak engelleniyorsa, bunun nedeni veri yenileme sırasında aynı çalışma alanı içinde karşılık gelen, bağımlı bir veri akışının kilitlenmesi olabilir. Bu tür bir kilitleme işlem doğruluğu sağlar ve her iki veri akışının da başarıyla yenilenmesini sağlar, ancak düzenleme yapmanızı engelleyebilir. 

Bağlı veri akışı için ayrı bir zamanlama ayarlarsanız, veri akışları gereksiz şekilde yenileyebilir ve veri akışını düzenlemenizi engelleyebilir. Bu sorundan kaçınmak için iki öneri vardır: 

* Kaynak veri akışı ile aynı çalışma alanındaki bağlı veri akışı için yenileme zamanlaması ayarlamaktan kaçının
* Yenileme zamanlamasını ayrı olarak yapılandırmak ve kilitleme davranışının önüne geçmek istiyorsanız, veri akışını farklı bir çalışma alanına ayırın.

### <a name="create-a-separate-workspace-for-ingestion-transformation"></a>Veri alımı ve dönüştürme için ayrı bir çalışma alanı oluşturma

Temel alınan kaynak sistemin ham verilerine erişim izni vermeden birçok kullanıcının temel alınan veri akışı verilerine erişimini sağlamak için, paylaşmak için gereken tüm verileri içeren ayrı bir çalışma alanı oluşturun ve izinler atayın. Bireysel veri akışı izinleri şu anda desteklenmemektedir.

### <a name="ensure-capacity-is-in-the-same-region"></a>Kapasitenin aynı bölgede olduğundan emin olun

Veri akışları şu anda birden çok coğrafi bölgeyi desteklememektedir. Premium kapasite, Power BI kiracınızla aynı bölgede olmalıdır.

### <a name="separate-on-premises-sources-from-cloud-sources"></a>Şirket içi kaynakları bulut kaynaklarından ayırma

Daha önce açıklanan en iyi yöntemlere ek olarak şirket içi, bulut, SQL Server, Spark, Dynamics gibi her bir kaynak türü için ayrı bir veri akışı oluşturabilirsiniz. Veri akışınızı veri kaynağı türüne göre bölmeniz kesinlikle önerilir. Kaynak türüne göre böyle bir ayrım, hızlı sorun gidermeyi kolaylaştırır ve veri akışlarınızı yenilerken dahili sınırlamaları önler.

### <a name="separate-dataflows-into-a-separate-capacity"></a>Veri akışlarını farklı bir kapasiteye ayırma

Ağ kapasitesi azaltma sınırlarıyla karşılaşıyor veya kapasitenizdeki bellek sınırları nedeniyle düzenli arızalar yaşıyorsanız, veri akışlarınızı ayırmayı düşünün ek bellek için ölçeği Premium kapasiteye artırmayı düşünün.

## <a name="next-steps"></a>Sonraki Adımlar

Bu makalede veri akışlarına yönelik en iyi yöntemler hakkında bilgi verilmiştir. Veri akışları hakkında daha fazla bilgi için aşağıdaki makaleler yararlı olabilir:

* [Veri akışları ile self servis veri hazırlığı](service-dataflows-overview.md)
* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Power BI Premium'da hesaplanan varlıkları kullanma](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma](service-dataflows-on-premises-gateways.md)

CDM geliştirme ve öğretici kaynakları hakkında bilgi için aşağıdakilere bakın:
* [Ortak Veri Modeli - genel bakış ](https://docs.microsoft.com/powerapps/common-data-model/overview)
* [CDM klasörleri](https://go.microsoft.com/fwlink/?linkid=2045304)
* [CDM model dosyası tanımı](https://go.microsoft.com/fwlink/?linkid=2045521)


Power Query ve zamanlanmış yenileme hakkında daha fazla bilgi için şu makaleleri okuyabilirsiniz:
* [Power BI Desktop'ta sorgulara genel bakış](desktop-query-overview.md)
* [Zamanlanmış yenileme yapılandırma](refresh-scheduled-refresh.md)
