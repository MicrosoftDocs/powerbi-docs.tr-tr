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
ms.date: 03/12/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: f327cb95c10756f079778d20e62cba4871b95c02
ms.sourcegitcommit: ac63b08a4085de35e1968fa90f2f49ea001b50c5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/18/2019
ms.locfileid: "57964951"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Microsoft Power BI Premium nedir?

> [!NOTE]
> Bu makale yeni özellikleri açıklamak, daha fazla ayrıntı sağlamak ve okunabilirliği iyileştirmek için şu anda güncelleştiriliyor. En son bilgiler için bkz. [Power BI Premium Kapasitelerini Dağıtma ve Yönetme](whitepaper-powerbi-premium-deployment.md).

Power BI Premium, kuruluşunuz için Power BI hizmetinin çalıştırılmasına yönelik olarak ayrılmış kaynaklar sunar. Böylece daha güvenilir performans ve daha yüksek veri hacimleri elde edersiniz. Premium, içerik tüketicileri için kullanıcı başına Pro lisans satın almanız gerekmeden içeriğin geniş kapsamlı dağıtımına da olanak sağlar.  

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

| Kapasite Düğümü | Toplam sanal çekirdek sayısı<br/>*(Arka uç+ön uç)*  | Arka Uç Sanal Çekirdek Sayısı <sup>[1](#fn1)</sup> | Ön Uç Sanal Çekirdek Sayısı <sup>[2](#fn2)</sup> | DirectQuery/canlı bağlantı sınırları | Maksimum eş zamanlı yenileme sayısı |
| --- | --- | --- | --- | --- | --- |
| EM1 (aylık) |1 sanal çekirdek |0,5 sanal çekirdek, 2,5 GB RAM |0,5 sanal çekirdek |Saniyede 3,75 |  1 |
| EM2 (aylık) |2 sanal çekirdek |1 sanal çekirdek, 5 GB RAM |1 sanal çekirdek |Saniyede 7,5 |  2 |
| EM3 (aylık) |4 sanal çekirdek |2 sanal çekirdek, 10 GB RAM |2 sanal çekirdek | 15 | 3 |
| P1 |8 sanal çekirdek |4 sanal çekirdek, 25 GB RAM |4 sanal çekirdek |saniyede 30 | 6 |
| P2 |16 sanal çekirdek |8 sanal çekirdek, 50 GB RAM |8 sanal çekirdek |saniyede 60 | 12 |
| P3 |32 sanal çekirdek |16 sanal çekirdek, 100 GB RAM |16 sanal çekirdek |saniyede 120 | 24 |
| | | | | | |

<a name="fn1">1</a>: Ön uç sanal çekirdekler, web hizmetinden sorumludur. Örneğin pano ve rapor belge yönetimi, erişim hakları yönetimi, zamanlama, API'ler, karşıya yüklemeler ve indirmeler, kısacası kullanıcı deneyimiyle ilgili her şey bunların sorumluluğundadır. 

<a name="fn2">2</a>: Arka uç sanal çekirdekleri ise, sorgu işleme, önbellek yönetimi, R sunucularını çalıştırma, veri yenileme, doğal dil işleme, gerçek zamanlı akışlar ve raporlar ile resimlerin sunucu tarafında işlenmesi gibi işin zor bölümlerinden sorumludur. Arka uç sanal çekirdekleriyle, belirli miktarda bellek de ayrılır. Büyük veri modelleriyle veya çok sayıda etkin veri kümesiyle çalışırken, yeterli belleğe sahip olmak özellikle önemli bir gereksinim haline gelir.

## <a name="workloads-in-premium-capacity"></a>Premium kapasitedeki iş yükleri

Varsayılan olarak, Power BI Premium ve Power BI Embedded kapasiteleri yalnızca bulutta Power BI sorguları çalıştırmayla ilişkili iş yüklerini destekler. Premium ayrıca **Yapay zeka**, **Veri akışları** ve **Sayfalandırılmış raporlar** için ek iş yüklerini destekler. Bu iş yüklerinin kapasitenizin kaynaklarını kullanabilmesi için, önce Power BI yönetim portalında veya Power BI REST API aracılığıyla etkinleştirilmeleri gerekir. Her iş yükünün kullanabileceği bellek miktarı üst sınırını belirten varsayılan ayarları vardır. Bununla birlikte, iş yüklerinin birbirini nasıl etkileyeceğini ve kapasite kaynaklarınızı nasıl kullanacağını belirlemek için farklı bellek tüketim ayarları yapılandırabilirsiniz. Daha fazla bilgi için bkz. [İş yüklerini yapılandırma](service-admin-premium-workloads.md).

## <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu

Power BI Premium ile kuruluşunuzun şirket içindeki Power BI Rapor Sunucusu'nu da çalıştırabilirsiniz. Daha fazla bilgi edinmek için bkz. [Power BI Rapor Sunucusu ile çalışmaya başlama](report-server/get-started.md).

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium Kapasitelerini Dağıtma ve Yönetme](whitepaper-powerbi-premium-deployment.md)   
[Power BI Premium'u satın alma](service-admin-premium-purchase.md)   
[Power BI Premium hakkında SSS](service-premium-faq.md)   



Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
