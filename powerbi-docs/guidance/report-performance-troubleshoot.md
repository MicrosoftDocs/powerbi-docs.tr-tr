---
title: Power BI’da rapor performansı sorunlarını giderme
description: Power BI'da yavaş rapor performansını tanılamak için sorun giderme kılavuzu.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2020
ms.author: v-pemyer
ms.openlocfilehash: a5230a39706ce5d6941c00386160fe10114442e1
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "81528003"
---
# <a name="troubleshoot-report-performance-in-power-bi"></a>Power BI’da rapor performansı sorunlarını giderme

Bu makalede geliştiricilerin ve yöneticilerin yavaş rapor performansı sorunlarını gidermesine olanak tanıyan yönergeler sağlanır. Bu yönergeler Power BI raporları ve ayrıca Power BI sayfalandırılmış raporları için de geçerlidir.

Yavaş raporlar, dilimleyiciler veya diğer özelliklerle etkileşime girerken yavaş yüklenen ya da yavaş güncelleştirilen raporlarla karşılaşan rapor kullanıcıları tarafından belirlenebilir. Raporlar Premium kapasitede barındırıldığında, yavaş raporlar [Power BI Premium Metrics uygulaması](../service-admin-premium-monitor-capacity.md) izlenerek de belirlenebilir. Bu uygulama, Power BI Premium aboneliğinizin sistem durumunu ve kapasitesini izlemenize yardımcı olur.

## <a name="follow-flowchart-steps"></a>Akış çizelgesi adımlarını izleme

Yavaş performansın nedenini anlamaya yardımcı olmak ve hangi eylemin yapılacağını belirlemek için aşağıdaki akış çizelgesini kullanın.

:::image type="content" source="media/report-performance-troubleshoot/flowchart.png" alt-text="Resimde, makale metninde tam olarak açıklanan akış çizelgesi gösterilmektedir." border="true":::

Her biri gerçekleştirilecek eylemi açıklayan altı akış çizelgesi sonlandırıcı vardır:

|Sonlandırıcı|Eylemler|
|---------|---------|
|![Akış çizelgesi sonlandırıcı 1.](media/common/icon-01-red-30x30.png)|Kapasiteyi yönetme<br />Kapasite ölçeklendirme |
|![Akış çizelgesi sonlandırıcı 2.](media/common/icon-02-red-30x30.png)|Normal rapor kullanımı sırasında kapasite etkinliğini araştırma|
|![Akış çizelgesi sonlandırıcı 3.](media/common/icon-03-red-30x30.png)|Mimari değişikliği<br />Azure Analysis Services’ı deneyin<br />Şirket içi ağ geçidini denetleme|
|![Akış çizelgesi sonlandırıcı 4.](media/common/icon-04-red-30x30.png)|Azure Analysis Services’ı deneyin<br />Power BI Premium'u deneyin|
|![Akış çizelgesi sonlandırıcı 5.](media/common/icon-05-red-30x30.png)|Power BI Desktop Performans Analizi’ni kullanma<br />Rapor, model veya DAX iyileştirme|
|![Akış çizelgesi sonlandırıcı 6.](media/common/icon-06-red-30x30.png)|Destek bileti oluşturma|

## <a name="take-action"></a>Eylem gerçekleştirme

Dikkate alınması gereken ilk nokta, yavaş raporun Premium kapasitede barındırılıp barındırılmadığını anlamaktır.

### <a name="premium-capacity"></a>Premium kapasite

Rapor Premium kapasitede barındırıldığında, rapor barındırma kapasitesinin kapasite kaynaklarını sıklıkla aşıp aşmadığını belirlemek için **Power BI Premium Metrics uygulamasını** kullanın. Bu durum CPU için %80’i sıklıkla aştığında geçerli olur. Bellek için, [etkin bellek ölçümü](../service-premium-metrics-app.md#the-active-memory-metric) 50’yi aştığında geçerli olur. Kaynaklar üzerinde baskı söz konusu olduğunda, [kapasiteyi yönetme veya ölçeklendirme](../service-admin-premium-manage.md) zamanı gelmiş olabilir (akış çizelgesi sonlandırıcı 1). Yeterli kaynak olduğunda, normal rapor kullanımı sırasında kapasite etkinliğini araştırın (akış çizelgesi sonlandırıcı 2).

### <a name="shared-capacity"></a>Paylaşılan kapasite

Rapor paylaşılan kapasitede barındırıldığında, kapasite sistem durumunu izlemek mümkün değildir. Farklı bir araştırma yaklaşımı uygulamanız gerekir.

İlk olarak, yavaş performansın günün veya ayın belirli saatlerinde oluşup oluşmadığını belirleyin. Oluşuyorsa ve birçok kullanıcı raporu bu saatlerde açıyorsa, iki seçeneği göz önünde bulundurun:

- Veri kümesini [Azure Analysis Services](/azure/analysis-services/analysis-services-overview) veya Premium kapasiteye geçirerek sorgu aktarım hızını artırın (akış çizelgesi sonlandırıcı 4).
- Rapor öğelerinizden her birinin, örneğin görsellerin ve DAX formüllerinin nasıl performans gösterdiğini anlamak için Power BI Desktop [Performans Analizi](../desktop-performance-analyzer.md)’ni kullanın. Özellikle performans sorunlarına sorgunun mu yoksa görseli işleme işleminin mi yol açtığını belirleme açısından yararlıdır (akış çizelgesi sonlandırıcı 5).

Sorunun zamanla ilgisi olmadığını belirlerseniz, düşük performansın belirli bir coğrafya veya bölgeye yalıtılmış olup olmadığını değerlendirin. Öyleyse, büyük olasılıkla veri kaynağı uzak bir konumdadır ve ağ iletişimi yavaştır. Bu durumda şunları göz önünde bulundurun:

- [Azure Analysis Services](/azure/analysis-services/analysis-services-overview) kullanarak mimariyi değiştirme (akış çizelgesi sonlandırıcı 3).
- [Şirket içi veri ağ geçidi performansını](/data-integration/gateway/service-gateway-performance) iyileştirme (akış çizelgesi sonlandırıcı 3).

Son olarak, sorunun zamanla ilgisi olmadığını _ve_ performansın tüm bölgelerde meydana geldiğini belirlerseniz, yavaş performansın belirli cihazlarda, istemcilerde veya web tarayıcılarında oluşup oluşmadığını araştırın. Aksi takdirde, rapor veya modeli iyileştirmek için daha önce açıklandığı gibi Power BI Desktop [Performans Analizi](../desktop-performance-analyzer.md)’ni kullanın (akış çizelgesi sonlandırıcı 5).

Belirli cihazların, istemcilerin veya web tarayıcılarının düşük performansa neden olduğunu belirlerseniz, [Power BI destek sayfası](https://powerbi.microsoft.com/support/) aracılığıyla bir destek bileti oluşturmanızı öneririz (akış çizelgesi sonlandırıcı 6).

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI kılavuzu](index.yml)
- [Rapor performansını izleme](monitor-report-performance.md)
- [Performans Analizi](../desktop-performance-analyzer.md)
- Teknik İnceleme: [Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama)](https://go.microsoft.com/fwlink/?linkid=2057861)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
