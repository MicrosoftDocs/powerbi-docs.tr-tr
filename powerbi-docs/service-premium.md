---
title: Microsoft Power BI Premium nedir?
description: Power BI Premium, kullanıcı başına lisans satın almanıza gerektirmeden daha güvenilir performans ve daha yüksek veri hacimleri sunan, kuruluşunuz veya ekibiniz için ayrılmış kapasitedir.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/15/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: a048f589b19acd1a7c38a5b81cf781d1e76b7b5b
ms.sourcegitcommit: 187d20180d9bae5a2ec53748cede9e7301e0343e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56725352"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Microsoft Power BI Premium nedir?

Microsoft Power BI Premium, kuruluşunuz için Power BI hizmetinin çalıştırılmasına yönelik olarak ayrılmış kaynaklar sunar. Böylece daha güvenilir performans ve daha yüksek veri hacimleri elde edersiniz. Premium, içerik tüketicileri için kullanıcı başına Pro lisans satın almanız gerekmeden içeriğin geniş kapsamlı dağıtımına da olanak sağlar.  

## <a name="premium-capacity-and-shared-capacity"></a>Premium kapasite ve paylaşılan kapasite

Çalışma alanlarını bir *Premium kapasiteye* atayarak Power BI Premium'dan yararlanabilirsiniz. Premium kapasite, kuruluşunuz için ayrılmış bir kaynaktır. Premium kapasiteye atanmamış çalışma alanları, *paylaşılan kapasitede* bulunur. Paylaşılan kapasitede iş yükleriniz diğer müşterilerle paylaşılan hesaplama kaynaklarında çalışır.

Aşağıdaki görüntüde Contoso kuruluşu örneğiyle Premium kapasite ile paylaşılan kapasite arasındaki ilişki gösterilmiştir.

![Power BI Premium'a ilişkin çizim](media/service-premium/premium-chart.png)

| Alan | Açıklama |
| --- | --- |
| **(1)** Premium kapasitedeki öğeler | <ul><li>Uygulama çalışma alanlarına erişmek (üye veya yönetici olarak) ve uygulama yayımlamak için Power BI Pro lisansı gerekir.<li>Uygulamanın paylaşımı için Pro lisansı gerekir ama kullanımı için gerekmez.<li>Atanan lisanslarından bağımsız olarak tüm pano alıcıları veri uyarıları ayarlayabilir.<li>Eklemeye yönelik REST API'leri, kullanıcı hesabı yerine Pro lisansına sahip bir hizmet hesabından yararlanır.</ul> |
| **(2)** Paylaşılan kapasitede Çalışma Alanım | <ul><li>Uygulamanın hem paylaşımı hem de kullanımı Pro lisansı gerektirir.</ul> |
| **(3)** Paylaşılan kapasitede uygulama çalışma alanları | <ul><li>Tüm uygulama kullanımları için Pro lisansı gerekir.</ul>|
| | |

Paylaşılan kapasitede, Power BI tüm kullanıcılar için kaliteli bir deneyim sağlamak üzere her kullanıcıya daha fazla sınırlama getirir. Varsayılan olarak *Çalışma alanım* ve Uygulama çalışma alanlarının da bulunduğu çalışma alanınız, paylaşılan kapasitede yer alır.

Aşağıdaki tabloda paylaşılan kapasite ve Premium kapasite arasındaki farkların bir özeti verilmiştir:

|  | Paylaşılan kapasite | Power BI Premium kapasitesi |
| --- | --- | --- |
| **Yenileme sıklığı** |Günde 8 kez |48/gün |
| Ayrılmış donanımla yalıtım |![Kullanılamaz](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| *Tüm kullanıcılara* yönelik Kurumsal Dağıtım | | |
| Uygulamalar ve paylaşım |![Kullanılamaz](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| Katıştırılmış API ve denetimler |![Kullanılamaz](media/service-premium/not-available.png) |![](media/service-premium/available.png)<sup>[1](#fnt1)</sup> |
| Power BI raporlarını şirket içinde yayımlama |![Kullanılamaz](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| | | |

<a name="fnt1">1</a> Power BI Premium'da daha fazla geliştirme sunulacaktır.



### <a name="premium-capacity-nodes"></a>Premium kapasite düğümleri

Power BI Premium, farklı sanal çekirdek kapasitelerine sahip düğüm yapılandırmalarıyla kullanılabilir. SKU teklifleri ve maliyetler hakkında daha fazla bilgi için bkz. [Power BI fiyatlandırması](https://powerbi.microsoft.com/pricing/). Ayrıca bir [maliyet hesaplayıcı](https://powerbi.microsoft.com/calculator/) da kullanımınıza sunulmuştur. Katıştırılmış analiz kapasite planlamasıyla ilgili bilgiler için bkz. [Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama) teknik incelemesi](https://aka.ms/pbienterprisedeploy). Özetlemek gerekirse:

* P düğümleri, tümleşik dağıtımlar veya hizmet dağıtımları için kullanılabilir.

* EM düğümleri ise yalnızca tümleşik dağıtımlar için kullanılabilir. EM düğümlerinin, Power BI Pro lisansına sahip olan kullanıcılarla uygulamaları paylaşma gibi üst düzey özelliklere erişimi yoktur.

| Kapasite Düğümü | Toplam sanal çekirdek sayısı<br/>*(Arka uç+ön uç)*  | Arka Uç Sanal Çekirdek Sayısı <sup>[1](#fn1)</sup> | Ön Uç Sanal Çekirdek Sayısı <sup>[2](#fn2)</sup> | DirectQuery/canlı bağlantı sınırları | Maksimum eş zamanlı yenileme sayısı |  Kullanılabilirlik
| --- | --- | --- | --- | --- | --- | --- | --- |
| EM1 (aylık) |1 sanal çekirdek |0,5 sanal çekirdek, 2,5 GB RAM |0,5 sanal çekirdek |Saniyede 3,75 |  1 | Kullanılabilir |
| EM2 (aylık) |2 sanal çekirdek |1 sanal çekirdek, 5 GB RAM |1 sanal çekirdek |Saniyede 7,5 |  2 | Kullanılabilir |
| EM3 (aylık) |4 sanal çekirdek |2 sanal çekirdek, 10 GB RAM |2 sanal çekirdek | | 3 |  Kullanılabilir |
| P1 |8 sanal çekirdek |4 sanal çekirdek, 25 GB RAM |4 sanal çekirdek |saniyede 30 | 6 | Kullanılabilir (aylık olarak da sunulur) |
| P2 |16 sanal çekirdek |8 sanal çekirdek, 50 GB RAM |8 sanal çekirdek |saniyede 60 | 12 | Kullanılabilir |
| P3 |32 sanal çekirdek |16 sanal çekirdek, 100 GB RAM |16 sanal çekirdek |saniyede 120 | 24 | Kullanılabilir |
| | | | | | | |

<a name="fn1">1</a>: Ön uç sanal çekirdekler, web hizmetinden sorumludur. Örneğin pano ve rapor belge yönetimi, erişim hakları yönetimi, zamanlama, API'ler, karşıya yüklemeler ve indirmeler, kısacası kullanıcı deneyimiyle ilgili her şey bunların sorumluluğundadır. 

<a name="fn2">2</a>: Arka uç sanal çekirdekleri ise, sorgu işleme, önbellek yönetimi, R sunucularını çalıştırma, veri yenileme, doğal dil işleme, gerçek zamanlı akışlar ve raporlar ile resimlerin sunucu tarafında işlenmesi gibi işin zor bölümlerinden sorumludur. Arka uç sanal çekirdekleriyle, belirli miktarda bellek de ayrılır. Büyük veri modelleriyle veya çok sayıda etkin veri kümesiyle çalışırken, yeterli belleğe sahip olmak özellikle önemli bir gereksinim haline gelir.

## <a name="workloads-in-premium-capacity"></a>Premium kapasitedeki iş yükleri

Power BI’da iş yükünü kullanıcılarınızın kullanımına sunabileceğiniz çok sayıda hizmetten biri olarak düşünün. Varsayılan olarak, **Power BI Premium** ve **Power BI Embedded** kapasiteleri yalnızca bulutta Power BI sorguları çalıştırmayla ilişkili iş yüklerini destekler.

Şimdi iki ek iş yükü için önizleme desteği sunuyoruz: **Sayfalandırılmış raporlar** ve **Veri akışları**. Bu iş yüklerini Power BI yönetici portalından veya Power BI REST API aracılığıyla etkinleştirebilirsiniz. Ayrıca her iş yükünün tüketebileceği en büyük belleği ayarlayabilir, böylece farklı iş yüklerinin birbirini nasıl etkileyeceğini denetleyebilirsiniz. Daha fazla bilgi için bkz. [İş yüklerini yapılandırma](service-admin-premium-manage.md#configure-workloads).

### <a name="default-memory-settings"></a>Varsayılan bellek ayarları

Aşağıdaki tablolarda, kullanılabilen farklı [kapasite düğümlerine](#premium-capacity-nodes) göre varsayılan ve en küçük bellek değerleri gösterilmektedir. Bellek, dinamik olarak veri akışlarına ayrılsa da istatistiksel olarak sayfalandırılmış raporlara ayrılır. Daha fazla bilgi için, [Sayfalandırılmış raporlar ile ilgili önemli noktalar](#considerations-for-paginated-reports) başlıklı sonraki bölüme bakın.

#### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Hizmet olarak yazılım (SaaS) senaryoları için Microsoft Office SKU'ları

|                     | EM3                      | P1                       | P2                      | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|
| Sayfalandırılmış raporlar | YOK | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük | %20 varsayılan; %2,5 en küçük |
| Veri akışları | %20 varsayılan; %8 en küçük  | %20 varsayılan; %4 en küçük  | %20 varsayılan; %2 en küçük | %20 varsayılan; %1 en küçük  |
| | | | | |

#### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Hizmet olarak platform (PaaS) senaryoları için Microsoft Azure SKU'ları

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| Sayfalandırılmış raporlar | YOK                      | YOK                      | YOK                     | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük | %20 varsayılan; %2,5 en küçük |
| Veri akışları         | %27 varsayılan; %27 en küçük | %20 varsayılan; %16 en küçük | %20 varsayılan; %8 en küçük | %20 varsayılan; %4 en küçük  | %20 varsayılan; %2 en küçük | %20 varsayılan; %1 en küçük   |

### <a name="considerations-for-paginated-reports"></a>Sayfalandırılmış raporlar ile ilgili önemli noktalar

Sayfalandırılmış raporlar iş yükünü kullanıyorsanız, sayfalandırılmış raporların bir raporu işlerken (örneğin, içeriğe göre metin rengini dinamik olarak değiştirme) kendi kodunuzu çalıştırmanıza olanak tanıdığını unutmayın. Bu durum göz önünde bulundurulduğunda, sayfalandırılmış raporları kapasite dahilindeki sınırlı bir alanda çalıştırarak Power BI Premium kapasitesinin güvenliğini sağlarız. İş yükünün etkin olup olmadığına bakılmaksızın, bu alanı belirtmek için en büyük belleği atarız. Power BI raporlarını veya veri akışlarını aynı kapasitede kullanıyorsanız, sayfalandırılmış raporlar için diğer iş yüklerini olumsuz yönde etkilemeyecek kadar düşük bellek ayarladığınızdan emin olun.

Nadir durumlarda sayfalandırılmış raporlar iş yükü kullanılamaz hale gelebilir. Böyle bir durumda iş yükü, yönetici portalında bir hata durumu gösterir ve kullanıcılar rapor işleme için zaman aşımı değerlerini görürler. Bu sorunu gidermek için iş yükünü devre dışı bırakın, sonra yeniden etkinleştirin.

## <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu

Power BI Premium ile kuruluşunuzun şirket içindeki Power BI Rapor Sunucusu'nu da çalıştırabilirsiniz. Daha fazla bilgi edinmek için bkz. [Power BI Rapor Sunucusu ile çalışmaya başlama](report-server/get-started.md).

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium Hakkında SSSS](service-premium-faq.md)
[Power BI Premium'u satın alma](service-admin-premium-purchase.md)
[Power BI Premium'u yönetme](service-admin-premium-manage.md)
[Microsoft Power BI Premium teknik incelemesi](https://aka.ms/pbipremiumwhitepaper)
[Power BI Kuruluş Dağıtımını Planlama teknik incelemesi](https://aka.ms/pbienterprisedeploy)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
