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
ms.openlocfilehash: 5a0c29f04e7329373eec5f60af840e503ec22b3c
ms.sourcegitcommit: 73228d0a9038b8369369c059ad06168d2c5ff062
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2019
ms.locfileid: "68729986"
---
# <a name="guidance-for-deploying-a-data-gateway-for-power-bi"></a>Power BI için veri ağ geçidi dağıtmaya ilişkin yönergeler

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Bu makalede, ağ ortamınızda Power BI için bir veri ağ geçidini dağıtmaya ilişkin yönergeler ve önemli noktalar sunulmaktadır.

Şirket içi veri ağ geçidini indirme, yükleme, yapılandırma ve yönetme hakkında bilgi için bkz. [Şirket içi veri ağ geçidi nedir?](/data-integration/gateway/service-gateway-onprem) [Microsoft Power blogunu](https://powerbi.microsoft.com/blog/) ve [Microsoft Power BI Topluluğu](https://community.powerbi.com/) sayfasını ziyaret ederek şirket içi veri ağ geçidi ve Power BI hakkında daha fazla bilgi edinebilirsiniz.

## <a name="installation-considerations-for-the-on-premises-data-gateway"></a>Şirket içi veri ağ geçidini yükleme ile ilgili önemli noktalar

Power BI bulut hizmetiniz için şirket içi veri ağ geçidini yüklemeden önce göz önünde bulundurmanız gereken bazı noktalar vardır. Aşağıdaki bölümler bu noktalar açıklar.

### <a name="number-of-users"></a>Kullanıcı sayısı

Ağ geçidinin kullanıldığı bir rapordan yararlanan kullanıcı sayısı, ağ geçidinin yükleneceği konuma karar vermenizde önemli bir unsurdur. Aşağıda, üzerinde düşünülmesi gereken bazı sorular verilmiştir:

* Kullanıcılar bu raporları günün farklı zamanlarında mı kullanıyor?
* Ne tür bağlantılar (DirectQuery veya İçeri Aktarma) kullanıyorlar?
* Tüm kullanıcılar aynı raporu mu kullanıyor?

Tüm kullanıcılar belirli bir rapora her gün aynı zamanda erişiyorsa, ağ geçidini tüm bu istekleri işleyebilecek bir makineye yüklediğinizden emin olun. Makinenin uygun olup olmadığını saptamanıza yardımcı olabilecek performans sayaçları ve en düşük gereksinimler için aşağıdaki bölümlere bakın.

Power BI'da *rapor* başına *tek bir* ağ geçidine izin veren bir kısıtlama vardır. Rapor birden çok veri kaynağını temel alıyor olsa bile bu veri kaynaklarının tümü tek ağ geçidinden geçmelidir. Panoda *birden çok* rapor temel alınıyorsa, katkıda bulunan her rapor için ayrılmış bir ağ geçidi kullanabilirsiniz. Bu şekilde, ağ geçidi yükünü tek panoya katkıda bulunan birden çok rapor arasında dağıtırsınız.

### <a name="connection-type"></a>Bağlantı türü

Power BI iki tür bağlantı sunar: DirectQuery ve İçeri Aktarma. Veri kaynaklarının tümü iki bağlantı türünü de desteklemez. Birinin yerine diğerini seçmenizde güvenlik gereksinimleri, performans, veri sınırları ve veri modeli boyutları gibi birçok faktör rol oynayabilir. Bağlantı türleri ve desteklenen veri kaynakları hakkında daha fazla bilgi edinmek için [kullanılabilir veri kaynağı türlerinin listesine](service-gateway-data-sources.md#list-of-available-data-source-types) bakın.

Ağ geçidi kullanımı, kullanılmakta olan bağlantı türüne göre değişiklik gösterebilir. Örneğin DirectQuery veri kaynaklarını zamanlanmış yenileme veri kaynaklarından mümkün olduğunca ayırmaya çalışın. Bunların farklı raporlarda yer aldığı ve ayrılabileceği varsayılır. Kaynakları ayırarak, tam da şirketin ana panosu için kullanılan büyük boyutlu bir veri modeli için sabah gerçekleştirilecek zamanlanmış yenilemeyle aynı zamanda, ağ geçidinde binlerce DirectQuery isteğinin birikmesinin önüne geçersiniz. 

Her seçenek için şu noktaları aklınızda bulundurmanız gerekir:

* **Zamanlanmış yenileme**: Sorgunuzun boyutuna ve günlük olarak gerçekleşen yenileme sayısına bağlı olarak, önerilen en düşük donanım gereksinimlerini aşmama veya daha yüksek performans gösteren bir makineye yükseltme arasında seçim yapabilirsiniz. Belirtilen sorgu katlanmadıysa, dönüştürmeler ağ geçidi makinesinde gerçekleşir. Sonuç olarak ağ geçidi makinesi daha fazla kullanılabilir RAM'e sahip olur.

* **DirectQuery**: Herhangi bir kullanıcı raporu her açtığında veya verilere göz attığında bir sorgu gönderilir. 1\.000'den fazla kullanıcının aynı anda verilere erişmesini bekliyorsanız bilgisayarınızın güçlü ve nitelikli donanım bileşenlerinden oluştuğundan emin olun. Daha fazla CPU çekirdeği, DirectQuery bağlantısı için daha iyi bir performans elde edilmesini sağlar.

Makine yükleme gereksinimleri için şirket içi ağ geçidi [yükleme gereksinimleri](/data-integration/gateway/service-gateway-install#requirements) konusuna bakın.

### <a name="location"></a>Konum

Ağ geçidi yüklemesinin konumu sorgu performansınızı önemli ölçüde etkileyebilir. Ağ gecikmesini en aza indirmek için ağ geçidi, veri kaynağı ve Power BI kiracısı konumlarınızın birbirine olabildiğince yakın olmasına dikkat edin. Power BI hizmetinde Power BI kiracınızın konumunu belirlemek için, sağ üst köşede bulunan **?** simgesine dokunun. Ardından **Power BI Hakkında**'yı seçin.

![Power BI kiracısı konumunuzu belirleme](media/service-gateway-deployment-guidance/powerbi-gateway-deployment-guidance_02.png)

Power BI ağ geçidini Azure Analysis Services ile kullanmak istiyorsanız, her ikisindeki veri bölgelerinin eşleştiğinden emin olun. Birden çok hizmetin veri bölgelerini ayarlama hakkında daha fazla bilgi için [bu videoyu](https://guyinacube.com/2018/01/power-bi-azure-analysis-services-gateway-data-region/) izleyin.

## <a name="next-steps"></a>Sonraki adımlar

* [Ara sunucu ayarlarını yapılandırma](/data-integration/gateway/service-gateway-proxy)  
* [Ağ geçidiyle ilgili sorunları giderme - Power BI](service-gateway-onprem-tshoot.md)  
* [Şirket içi veri ağ geçidi hakkında SSS - Power BI](service-gateway-power-bi-faq.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu](http://community.powerbi.com/)'nu deneyin.

