---
title: Microsoft Power BI Premium nedir?
description: Power BI Premium, kullanıcı başına lisans satın almanıza gerektirmeden daha güvenilir performans ve daha yüksek veri hacimleri sunan, kuruluşunuz veya ekibiniz için ayrılmış kapasitedir.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/21/2018
LocalizationGroup: Premium
ms.openlocfilehash: 2ca75f191f27bd158b9fab67c7be6902154f8ac1
ms.sourcegitcommit: a764e4b9d06b50d9b6173d0fbb7555e3babe6351
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2018
ms.locfileid: "49641241"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Microsoft Power BI Premium nedir?

Microsoft Power BI Premium, kuruluşunuz için Power BI hizmetinin çalıştırılmasına yönelik olarak ayrılmış kaynaklar sunar. Böylece daha güvenilir performans ve daha yüksek veri hacimleri elde edersiniz. Premium, içerik tüketicileri için kullanıcı başına Pro lisans satın almanız gerekmeden içeriğin geniş kapsamlı dağıtımına da olanak sağlar. Satın alma hakkında daha fazla bilgi için bkz. [Power BI Premium'u satın alma](service-admin-premium-purchase.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

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

Aşağıdaki tabloda paylaşılan kapasite ve Premium kapasite arasındaki farkların bir özeti verilmiştir.

|  | Paylaşılan kapasite | Power BI Premium kapasitesi |
| --- | --- | --- |
| **Yenileme sıklığı** |Günde 8 kez |48/gün |
| **Ayrılmış donanımla yalıtım** |![](media/service-premium/not-available.png "Kullanılamaz") |![](media/service-premium/available.png "Kullanılabilir") |
| ***Tüm kullanıcılara*** yönelik **Kurumsal Dağıtım** | | |
| Uygulamalar ve paylaşım |![](media/service-premium/not-available.png "Kullanılamaz") |![](media/service-premium/available.png "Kullanılabilir")<sup>1</sup> |
| Katıştırılmış API ve denetimler |![](media/service-premium/not-available.png "Kullanılamaz") |![](media/service-premium/available.png "Kullanılabilir")<sup>2</sup> |
| **Power BI raporlarını şirket içinde yayımlama** |![](media/service-premium/not-available.png "Kullanılamaz") |![](media/service-premium/available.png "Kullanılabilir") |
| | | |

*<sup>1</sup> Daha fazla bilgi için bkz. [Lisans türüne göre özellikler](service-features-license-type.md).*  
*<sup>2</sup> Power BI Premium'da daha fazla geliştirme sunulacaktır.*

Çalışma alanlarını premium kapasiteye atama hakkında daha fazla bilgi için bkz. [Power BI Premium'u yönetme](service-admin-premium-manage.md).

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Premium kapasite düğümleri

Power BI Premium, farklı sanal çekirdek kapasitelerine sahip düğüm yapılandırmalarıyla kullanılabilir. SKU teklifleri ve maliyetler hakkında daha fazla bilgi için bkz. [Power BI fiyatlandırması](https://powerbi.microsoft.com/pricing/). Ayrıca bir [maliyet hesaplayıcı](https://powerbi.microsoft.com/calculator/) da kullanımınıza sunulmuştur. Katıştırılmış analiz kapasite planlamasıyla ilgili bilgiler için bkz. [Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama) teknik incelemesi](https://aka.ms/pbienterprisedeploy). Özetlemek gerekirse:

* P düğümleri, tümleşik dağıtımlar veya hizmet dağıtımları için kullanılabilir.

* EM düğümleri ise yalnızca tümleşik dağıtımlar için kullanılabilir. EM düğümlerinin, Power BI Pro lisansına sahip olan kullanıcılarla uygulamaları paylaşma gibi üst düzey özelliklere erişimi yoktur.

>[!NOTE]
>Bu tablodaki bağlantılar yalnızca Office 365 Genel Yöneticisi rolüne sahip olan kullanıcılar için düzgün çalışır. Diğer kullanıcılar 404 hatasıyla karşılaşır.

| Kapasite Düğümü | Toplam sanal çekirdek sayısı<br/>*(Arka uç + ön uç)* | Arka uç sanal çekirdek sayısı | Ön uç sanal çekirdek sayısı | DirectQuery/canlı bağlantı sınırları | Yoğun saatlerde işlenen maksimum sayfa sayısı | Kullanılabilirlik |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (aylık)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 sanal çekirdek |0,5 sanal çekirdek, 2,5 GB RAM |0,5 sanal çekirdek |Saniyede 3,75 |150-300 |Kullanılabilir |
| [EM2 (aylık)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 sanal çekirdek |1 sanal çekirdek, 5 GB RAM |1 sanal çekirdek |Saniyede 7,5 |301-600 |Kullanılabilir |
| [EM3 (aylık)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 sanal çekirdek |2 sanal çekirdek, 10 GB RAM |2 sanal çekirdek | |601-1200 |Kullanılabilir |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 sanal çekirdek |4 sanal çekirdek, 25 GB RAM |4 sanal çekirdek |saniyede 30 |1.201-2.400 |Kullanılabilir ([aylık](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1) olarak da sunulur) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 sanal çekirdek |8 sanal çekirdek, 50 GB RAM |8 sanal çekirdek |saniyede 60 |2.401-4.800 |Kullanılabilir |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 sanal çekirdek |16 sanal çekirdek, 100 GB RAM |16 sanal çekirdek |saniyede 120 |4.801-9.600 |Kullanılabilir |
| | | | | | | |

* Ön uç sanal çekirdekleri; web hizmetinden, pano ve rapor belge yönetiminden, erişim hakları yönetiminden, zamanlamadan, API'lerden, karşıya yüklemelerden ve indirmelerden, kısacası kullanıcı deneyimiyle ilgili her şeyden sorumludur.

* Arka uç sanal çekirdekleri ise işin zor bölümünden sorumludur: sorgu işleme, önbellek yönetimi, R sunucularını çalıştırma, veri yenileme, doğal dil işleme, gerçek zamanlı akışlar ve raporlar ile resimlerin sunucu tarafında işlenmesi. Arka uç sanal çekirdekleriyle, belirli miktarda bellek de ayrılır. Büyük veri modelleriyle veya çok sayıda etkin veri kümesiyle çalışırken, yeterli belleğe sahip olmak özellikle önemli bir gereksinim haline gelir.

## <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu

Power BI Premium ile kuruluşunuzun şirket içindeki Power BI Rapor Sunucusu'nu da çalıştırabilirsiniz. Daha fazla bilgi edinmek için bkz. [Power BI Rapor Sunucusu ile çalışmaya başlama](report-server/get-started.md).

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium Hakkında SSSS](service-premium-faq.md)
[Power BI Premium'u satın alma](service-admin-premium-purchase.md)
[Power BI Premium'u yönetme](service-admin-premium-manage.md)
[Microsoft Power BI Premium teknik incelemesi](https://aka.ms/pbipremiumwhitepaper)
[Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama) teknik incelemesi](https://aka.ms/pbienterprisedeploy)
[Kuruluşunuzda Power BI uygulamasını yönetme](service-admin-administering-power-bi-in-your-organization.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
