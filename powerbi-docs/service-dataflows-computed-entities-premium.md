---
title: Power BI Premium’da hesaplanan varlıkları kullanma
description: Power BI Premium’da hesaplanan varlıkları kullanmayı öğrenin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/06/2018
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 8131722d0e035f28fcb88827b1a68c2da97959cb
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51268930"
---
# <a name="using-computed-entities-on-power-bi-premium-preview"></a>Power BI Premium’da hesaplanan varlıkları kullanma (Önizleme)

Bir Power BI Premium aboneliği ile **veri akışlarını** kullanırken **depolama içi hesaplamalar** yapabilirsiniz. Bu özellik, mevcut veri akışlarınızda hesaplamalar yapmanıza ve rapor oluşturma ve analizine odaklanmanızı sağlayan sonuçlar döndürmenize olanak sağlar. 

![Power BI Premium’da hesaplanan varlıklar](media/service-dataflows-computed-entities-premium/computed-entities-premium_00.png)

**Depolama içi hesaplamalar** yapmak için ilk olarak veri akışını oluşturmanız ve verileri Power BI veri akışı depolama alanına getirmeniz gerekir. Veri içeren bir veri akışı elde ettikten sonra, depolama içi hesaplamalar yapan varlıklar olan **hesaplanan varlıklar** oluşturabilirsiniz. 

Veri akışı verilerini Power BI'a iki yolla bağlayabilirsiniz:

* [Veri akışının self servis yazma özelliğini kullanarak](service-dataflows-create-use.md)
* Dış veri akışı kullanarak

Aşağıdaki bölümlerde, veri akışı verileriniz üzerinde hesaplanan varlıkların nasıl oluşturulacağı açıklanmaktadır.

> [!NOTE]
> Veri akışları işlevselliği önizleme aşamasındadır ve genel kullanıma sunulmadan önce değiştirilip güncelleştirilebilir.


## <a name="how-to-create-computed-entities"></a>Hesaplanan varlık oluşturma 

Varlık listesini içeren bir veri akışı oluşturduktan sonra, bu varlıklar üzerinde hesaplamalar yapabilirsiniz.

Power BI hizmetindeki veri akışı yazma aracında **Varlıkları düzenle**’yi seçin, ardından hesaplanmış varlığınızın temeli olarak kullanmak ve üzerinde hesaplamalar yapmak istediğiniz varlığa sağ tıklayın. Bağlam menüsünde **Başvuru**’yu seçin.

Varlığın hesaplanan varlık olarak kabul edilmesi için, aşağıdaki görüntüde gösterildiği gibi **Yükü etkinleştir** seçiminin işaretlenmesi gerekir. Bu bağlam menüsünü görüntülemek için varlığa sağ tıklayın.

![Sağ tıklama bağlam menüsünde Yükü etkinleştir’i işaretleyin](media/service-dataflows-computed-entities-premium/computed-entities-premium_01.png)

**Yükü etkinleştir**’i seçerek, kaynağı başvurulan varlık olan yeni bir varlık oluşturursunuz. Simge değişir ve aşağıdaki görüntüde gösterildiği gibi **hesaplanan** simgesini gösterir.

![Power BI Premium’da hesaplanan varlıklar](media/service-dataflows-computed-entities-premium/computed-entities-premium_00.png)

Bu yeni oluşturulan varlık üzerinde gerçekleştirdiğiniz tüm dönüşümler, Power BI veri akışı deposunda zaten mevcut olan veriler üzerinde çalıştırılır. Bunun anlamı, sorgunun verilerin içeri aktarıldığı dış veri kaynağına göre çalıştırılmayacağı (örneğin, verilerin çekildiği SQL veritabanı), bunun yerine veri akışı depolama alanında bulunan veriler üzerinde gerçekleştirileceğidir.

### <a name="example-use-cases"></a>Kullanım örnekleri
Hesaplanan varlıklarla ne tür dönüşümler gerçekleştirilebilir? Depolama içi hesaplama yaparken Power BI’daki dönüşüm kullanıcı arabirimini veya M düzenleyicisini kullanarak genellikle belirttiğiniz tüm dönüşümler desteklenir. 

Şu örneği düşünün: Dynamics 365 aboneliğinizdeki tüm müşteriler için ham verileri içeren bir *Account* varlığınız var. Ayrıca, yılın her gününde farklı hesaptan gerçekleştirilen destek çağrılarının verileri ile birlikte Hizmet Merkezi’nden *ServiceCalls* ham verilerine sahipsiniz.

*Account* varlığını *ServiceCalls* verileri ile zenginleştirmek istediğinizi hayal edin. 

İlk olarak her hesap için önceki yıl içinde yapılan destek aramalarının sayısını hesaplamak için ServiceCalls’dan gelen verileri toplamanız gerekir. 

![Power BI Premium'da hesaplanan varlık örneği](media/service-dataflows-computed-entities-premium/computed-entities-premium_02.png)

Sonra, zenginleştirilmiş **Hesap** tablosunu hesaplamak için *Account* varlığını *ServiceCallsAggregated* varlığı ile birleştirmek istersiniz.

![Power BI Premium'da hesaplanan varlık örneği](media/service-dataflows-computed-entities-premium/computed-entities-premium_03.png)

Bundan sonra, aşağıdaki görüntüde *EnrichedAccount* olarak gösterilen sonuçları görebilirsiniz.

![Power BI Premium'da hesaplanan bir varlığın sonuçları](media/service-dataflows-computed-entities-premium/computed-entities-premium_04.png)

İşte bu kadar. Dönüşüm kaynak verileriniz üzerinde değil Power BI Premium aboneliğinizde bulunan veri akışındaki veriler üzerinde gerçekleştirilir.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Çalışma alanını Power BI Premium kapasitesinden çıkarırsanız ilişkili veri akışının da artık yenilenmeyeceği unutulmamalıdır. 


## <a name="next-steps"></a>Sonraki Adımlar

Bu makalede, Power BI hizmetinde kullanılabilen hesaplanan varlıklar ve veri akışları açıklanmıştır. Yararlı olabilecek diğer makalelerden bazıları ise aşağıda verilmiştir.


* [Veri akışları ile self servis veri hazırlığı](service-dataflows-overview.md)
* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma (Önizleme)](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışları için geliştirici kaynakları (Önizleme)](service-dataflows-developer-resources.md)

Power Query ve zamanlanmış yenileme hakkında daha fazla bilgi için şu makaleleri okuyabilirsiniz:
* [Power BI Desktop'ta sorgulara genel bakış](desktop-query-overview.md)
* [Zamanlanmış yenileme yapılandırma](refresh-scheduled-refresh.md)

Ortak Veri Modeli hakkında daha fazla bilgi için genel bakış makalesini okuyabilirsiniz:
* [Ortak Veri Modeli - genel bakış ](https://docs.microsoft.com/powerapps/common-data-model/overview)
