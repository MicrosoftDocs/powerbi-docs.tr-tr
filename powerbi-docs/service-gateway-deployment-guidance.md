---
title: Power BI için veri ağ geçidi dağıtmaya ilişkin yönergeler
description: Power BI için ağ geçidi dağıtmaya ilişkin en iyi uygulamaları ve önemli noktaları öğrenin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 4351804330982b32582c4c782ef7c2fa0e92f197
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271716"
---
# <a name="guidance-for-deploying-a-data-gateway-for-power-bi"></a>Power BI için veri ağ geçidi dağıtmaya ilişkin yönergeler

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Bu makalede, ağ ortamınızda Power BI için bir veri ağ geçidini dağıtmaya ilişkin yönergeler ve önemli noktalar sunulmaktadır.

Şirket içi veri ağ geçidini indirme, yükleme, yapılandırma ve yönetme hakkında bilgi için bkz. [Şirket içi veri ağ geçidi nedir?](/data-integration/gateway/service-gateway-onprem). [Microsoft Power blogunu](https://powerbi.microsoft.com/blog/) ve [Microsoft Power BI Topluluğu](https://community.powerbi.com/) sayfasını ziyaret ederek şirket içi veri ağ geçidi ve Power BI hakkında daha fazla bilgi edinebilirsiniz.

## <a name="installation-considerations-for-the-on-premises-data-gateway"></a>Şirket içi veri ağ geçidini yükleme ile ilgili önemli noktalar

Power BI bulut hizmetiniz için şirket içi veri ağ geçidini yüklemeden önce bazı noktaları göz önünde bulundurmanız gerekir. Aşağıdaki bölümler bu noktalar açıklar.

### <a name="number-of-users"></a>Kullanıcı sayısı

Ağ geçidinin kullanıldığı bir rapordan yararlanan kullanıcı sayısı, ağ geçidinin yükleneceği konuma karar vermede önemli bir unsurdur. Aşağıda, üzerinde düşünülmesi gereken bazı sorular verilmiştir:

* Kullanıcılar bu raporları günün farklı zamanlarında mı kullanıyor?
* Ne tür bağlantılar (DirectQuery veya İçeri Aktar) kullanılıyor?
* Tüm kullanıcılar aynı raporu mu kullanıyor?

Tüm kullanıcılar belirli bir rapora her gün aynı anda erişiyorsa ağ geçidini, tüm istekleri işleyebilen bir makineye yüklediğinizden emin olmak istersiniz. (Bu konuda karar vermenize yardımcı olabilecek performans sayaçları ve minimum gereksinimler için aşağıdaki bölümlere bakın.)

**Power BI**'da *rapor* başına yalnızca *bir* ağ geçidine izin veren bir kısıtlama söz konusudur, bu nedenle bir rapor birden çok veri kaynağını temel alıyor olsa bile tüm bu veri kaynaklarının tek bir ağ geçidinden geçmesi gerekir. Ancak, bir pano *birden çok* rapora dayanıyorsa katkı sağlayan her rapor için, ayrılmış bir ağ geçidi kullanabilirsiniz. Böylece ağ geçidi yükünü, tek bir panoya katkı sağlayan birden çok rapor arasında dağıtmış olursunuz.

### <a name="connection-type"></a>Bağlantı türü

**Power BI** iki tür bağlantı sunar: **DirectQuery** ve **İçeri Aktarma**. Tüm veri kaynakları her iki bağlantı türünü de desteklemeyebilir ve güvenlik gereksinimleri, performans, veri sınırları ve veri modeli boyutları gibi birçok nedenden, biri diğerine tercih edilebilir. [Kullanılabilir veri kaynağı türlerinin listesi](service-gateway-data-sources.md#list-of-available-data-source-types) bölümünde, bağlantı türü ve desteklenen veri kaynakları ile ilgili daha fazla bilgiye ulaşabilirsiniz.

Ağ geçidi kullanımı, kullanılmakta olan bağlantı türüne göre değişiklik gösterebilir. Örneğin, mümkün olduğunda **DirectQuery** veri kaynaklarını **Zamanlanmış Yenileme** veri kaynaklarından ayırmanız gerekir (veri kaynaklarının farklı raporlarda olduğu ve ayrılabileceği varsayılmıştır). Bunu gerçekleştirerek, tam da şirketin ana panosu için kullanılan büyük boyutlu bir veri modeli için sabah gerçekleştirilecek zamanlanmış yenilemeyle aynı sırada, ağ geçidinde binlerce DirectQuery isteğinin birikmesinin önüne geçersiniz. Her biri için şu noktaları aklınızda bulundurmanız gerekir:

* **Zamanlanmış yenileme** için: Sorgunuzun boyutuna ve günlük olarak gerçekleşen yenileme sayısına bağlı olarak, önerilen minimum donanım gereksinimlerini aşmama veya daha yüksek performans gösteren bir makineye yükseltme arasında seçim yapabilirsiniz. Belirli bir sorgu katlanmış değilse ağ geçidi makinesinde dönüştürme işlemleri gerçekleştirilir, böylece ağ geçidi makinesi, kullanılabilir daha fazla RAM'den yararlanır.

* **DirectQuery** için: Herhangi bir kullanıcı raporu her açtığında veya verilere göz attığında bir sorgu gönderilir. Bu nedenle, 1.000'den fazla kullanıcının aynı anda verilere erişeceğini öngörüyorsanız bilgisayarınızın güçlü ve nitelikli donanım bileşenlerinden oluştuğundan emin olmak istersiniz. Daha fazla CPU çekirdeği, **DirectQuery** bağlantısı için daha iyi bir performans elde edilmesini sağlar.

Yükleme yaptığınız bir makine için gereksinimler, şirket içi veri ağ geçidi [yükleme gereksinimlerinde](/data-integration/gateway/service-gateway-install#requirements) bulunabilir.

### <a name="location"></a>Konum

Ağ geçidinin yüklendiği konum sorgu performansınızı önemli ölçüde etkiler, bu nedenle ağ gecikmesini en aza indirmek için ağ geçidiniz, veri kaynağı konumlarınız ve Power BI kiracınızın birbirine mümkün olduğunca yakın olduğundan emin olun. Power BI hizmetinde Power BI kiracınızın konumunu belirlemek için, sağ üst köşede bulunan **?** simgesini ve ardından **Power BI Hakkında**'yı seçin.

![Power BI kiracısı konumunuzu belirleme](media/service-gateway-deployment-guidance/powerbi-gateway-deployment-guidance_02.png)

Power BI ağ geçidin Azure Analysis Services ile kullanmak istiyorsanız, her iki veri bölgesinin eşleştiğinden emin olun. Birden çok hizmet için veri bölgesi ayarlama hakkında daha fazla bilgi için [bu videoyu izleyin](https://guyinacube.com/2018/01/power-bi-azure-analysis-services-gateway-data-region/).

## <a name="next-steps"></a>Sonraki adımlar

* [Ara sunucu ayarlarını yapılandırma](/data-integration/gateway/service-gateway-proxy)  
* [Ağ geçidiyle ilgili sorunları giderme - Power BI](service-gateway-onprem-tshoot.md)  
* [Şirket içi veri ağ geçidi hakkında SSS - Power BI](service-gateway-power-bi-faq.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

