---
title: Power BI’da veri akışları ile DirectQuery kullanma (önizleme)
description: Power BI’da veri akışları ile DirectQuery kullanmayı öğrenin
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/21/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 469b8b13f77c56f9371ae8c1c81dcb94278c62e0
ms.sourcegitcommit: 5e5a7e15cdd55f71b0806016ff91256a398704c1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83794010"
---
# <a name="use-directquery-with-dataflows-in-power-bi-preview"></a>Power BI’da veri akışları ile DirectQuery kullanma (önizleme)

Veri akışlarına doğrudan bağlanmak için DirectQuery’yi kullanabilir ve böylece verilerini içeri aktarmak zorunda kalmadan veri akışınıza doğrudan bağlanabilirsiniz. 

Veri akışlarıyla DirectQuery’nin kullanılması Power BI ve veri akışı işlemlerinizde şu geliştirmelere olanak tanır:

* **Ayrı yenileme zamanlamalarından kaçınma** - DirectQuery doğrudan veri akışına bağlandığından içeri aktarılan bir veri kümesi oluşturma ihtiyacını ortadan kaldırır. Dolayısıyla veri akışlarınız için DirectQuery’yi kullandığınızda artık veri akışı için ayrı yenileme zamanlamalarına ve verilerinizin eşitlendiğinden emin olmak için bir veri kümesine gerek kalmaz.

* **Verileri filtreleme** - DirectQuery, veri akışının içinde verilerin filtrelenmiş görünümüyle çalışmak için yararlıdır. Verileri filtrelemek ve böylece veri akışınızdaki verilerin daha küçük bir alt kümesiyle çalışmak istiyorsanız DirectQuery’yi (ve işlem altyapısını) kullanarak veri akışı verilerini filtreleyebilir ve ihtiyacınız olan filtrelenmiş alt kümeyle çalışabilirsiniz.


## <a name="using-directquery-for-dataflows"></a>Veri akışları için DirectQuery kullanma

Veri akışlarıyla DirectQuery kullanma, Power BI Desktop’ın Mayıs 2020 sürümünden başlayarak kullanıma sunulan bir önizleme özelliğidir. 

Veri akışlarıyla DirectQuery kullanmanın önkoşulları da vardır:

* Veri akışınız Power BI Premium etkinleştirilmiş bir çalışma alanının içinde yer almalıdır
* **İşlem altyapısı** açık olmalıdır. İşlem altyapısı hakkında daha fazla bilgi için bkz. [Gelişmiş işlem altyapısı](service-dataflows-enhanced-compute-engine.md).

## <a name="enable-directquery-for-dataflows"></a>Veri akışları için DirectQuery’yi etkinleştirme

Veri akışınızın DirectQuery erişiminde kullanılabildiğinden emin olmak için gelişmiş işlem altyapısının iyileştirilmiş durumda olması gerekir. Veri akışlarında DirectQuery’yi etkinleştirmek için yeni **Gelişmiş işlem altyapısı ayarları** seçeneğini **Açık** olarak ayarlayın. Aşağıdaki resimde düzgün bir şekilde seçilmiş ayar gösterilir.

![Veri akışlarında gelişmiş işlem altyapısını etkinleştirme](media/service-dataflows-directquery/dataflows-directquery-01.png)

Bu ayarı uyguladıktan sonra, iyileştirmenin geçerlilik kazanması için veri akışını yenileyin. 


## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

DirectQuery ve veri akışlarıyla ilgili bilinen birkaç sınırlama vardır ve bunlar aşağıdaki listede açıklanmaktadır.

* Veri akışları için DirectQuery, **gelişmiş meta veri önizleme** özelliği etkinleştirildiğinde çalışmaz. Bu dışlamanın Power BI Desktop’ın önümüzdeki aylarda kullanıma sunulacak bir sürümde kaldırılması beklenmektedir.

* Bu özelliğin önizleme dönemi boyunca bazı müşteriler veri akışlarıyla DirectQuery’yi kullanırken zaman aşımlarıyla veya performans sorunlarıyla karşılaşabilir. Bu önizleme döneminde bu tür sorunlar üzerinde etkin bir şekilde çalışılmaktadır.

* İçeri aktarma ve DirectQuery veri kaynaklarına sahip bileşik/karışık modeller şu anda desteklenmiyor.

* Büyük veri akışlarında görselleştirmeler görüntülenirken zaman aşımı sorunları ortaya çıkabilir. Özelliğin genel kullanılabilirliğinin bir parçası olarak bu sınırın kaldırılması beklenmektedir. Öte yandan, zaman aşımı sorunlarıyla karşılaşılan büyük veri akışlarında İçeri aktarma modu kullanılmalıdır.

* DirectQuery kullanıyorsanız veri akışı bağlayıcısı, veri kaynağı ayarları bölümünde geçersiz kimlik bilgileri gösterir. Bu, davranışı etkilemez ve veri kümesi düzgün bir şekilde çalışır. Genel kullanılabilirlik aşamasına yaklaştığımızdan, bu sorun ortadan kalkacaktır.



## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki makaleler, veri akışlarını kullanırken gerekecek diğer bilgiler ve senaryolar açısından yararlıdır:

* [Veri akışları ile self servis veri hazırlığı](service-dataflows-overview.md)
* [Power BI Premium'da hesaplanan varlıkları kullanma](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışları için geliştirici kaynakları](service-dataflows-developer-resources.md)
* [Veri akışları ve Azure Data Lake tümleştirmesi (Önizleme)](service-dataflows-azure-data-lake-integration.md)

Ortak Veri Modeli hakkında daha fazla bilgi için genel bakış makalesini okuyabilirsiniz:
* [Ortak Veri Modeli - genel bakış ](https://docs.microsoft.com/powerapps/common-data-model/overview)
* [GitHub'da Ortak Veri Modeli şeması ve varlıkları hakkında daha fazla bilgi edinin](https://github.com/Microsoft/CDM)

İlgili Power BI Desktop makaleleri:

* [Power BI Desktop'tan Power BI hizmetindeki veri kümelerine bağlanma](../connect-data/desktop-report-lifecycle-datasets.md)
* [Power BI Desktop'ta sorgulara genel bakış](desktop-query-overview.md)

İlgili Power BI hizmeti makaleleri:
* [Zamanlanmış yenileme yapılandırma](../connect-data/refresh-scheduled-refresh.md)
