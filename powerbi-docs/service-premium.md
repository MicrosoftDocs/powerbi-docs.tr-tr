---
title: Power BI Premium nedir?
description: Power BI Premium, kullanıcı başına lisans satın almanıza gerektirmeden daha güvenilir performans ve daha yüksek veri hacimleri sunan, kuruluşunuz veya ekibiniz için ayrılmış kapasitedir.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2018
ms.author: mblythe
LocalizationGroup: Premium
ms.openlocfilehash: 15b64b917fed56e9d9ab6be2023060378324c794
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36944572"
---
# <a name="power-bi-premium---what-is-it"></a>Power BI Premium nedir?
Power BI Premium, kuruluşunuz veya ekibiniz için Power BI hizmetinin çalıştırılmasına yönelik olarak ayrılmış kaynaklar sunar, böylece daha güvenilir performans ve daha yüksek veri hacimleri elde edersiniz. Premium, görüntüleyenler için kullanıcı başına lisans satın almanız gerekmeden içeriğin geniş bir şekilde dağıtımına da olanak sağlar.

Çalışma alanlarını bir Premium kapasiteye atayarak Power BI Premium'dan yararlanabilirsiniz. *Premium kapasite*, kuruluşunuz için ayrılmış bir kaynaktır. Premium kapasiteye atanmamış çalışma alanları, paylaşılan kapasitede bulunur.

İş yüklerinizin diğer müşteriler tarafından paylaşılan hesaplama kaynaklarında çalıştırıldığı *paylaşılan kapasite*, Power BI'da alışkın olduğunuz deneyimdir. Paylaşılan kapasitede, tüm kullanıcılar için kaliteli bir deneyim sağlamak üzere her bir kullanıcıya ilişkin olarak daha fazla sınırlama getirilir.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>Kapasite katmanları
Power BI'da iki kapasite türü vardır. Paylaşılan kapasite ve Power BI Premium kapasitesi. Aşağıda, bunlar arasındaki farklara ilişkin bir bakış edinebilirsiniz.

|  | Paylaşılan kapasite | Power BI Premium kapasitesi |
| --- | --- | --- |
| **Yenileme sıklığı** |Günde 8 kez |Kısıtlı değil |
| **Ayrılmış donanımla yalıtım** |![](media/service-premium/not-available.png "Kullanılamaz") |![](media/service-premium/available.png "Kullanılabilir") |
| ***Tüm kullanıcılara*** yönelik **Kurumsal Dağıtım** | | |
| Uygulamalar ve paylaşım |![](media/service-premium/not-available.png "Kullanılamaz") |![](media/service-premium/available.png "Kullanılabilir")<sup>1</sup> |
| Katıştırılmış API ve denetimler |![](media/service-premium/not-available.png "Kullanılamaz") |![](media/service-premium/available.png "Kullanılabilir")<sup>2</sup> |
| **Power BI raporlarını şirket içinde yayımlama** |![](media/service-premium/not-available.png "Kullanılamaz") |![](media/service-premium/available.png "Kullanılabilir") |

*<sup>1</sup> Daha fazla bilgi için bkz. [Power BI Pro ve Power BI Premium işlevselliğiyle kullanıcı özellikleri](service-free-vs-pro.md).*  
*<sup>2</sup> Power BI Premium'un genel kullanıma sunulmasından sonra daha fazla geliştirme sunulacaktır.*

### <a name="premium-capacity"></a>Premium kapasite
Power BI Premium kapasitesini kullanmaya başlamak için bir kapasiteye çalışma alanı atamanız gerekir. Bir çalışma alanını premium kapasiteye atama ile ilgili daha fazla bilgi için bkz. [Power BI Premium'u yönetme](service-admin-premium-manage.md).

Bir çalışma alanı premium kapasiteyle desteklendiğinde Power BI Premium'un sunduğu avantajlardan yararlanırsınız.

* Zamanlanmış yenilemeler: Daha önceki kullanıcılar için içeri aktarılan modellerle yenileme zamanlama, günde 8 kez ile sınırlıydı. Premium çalışma alanlarındaki veri kümeleri için bu sınırlama kaldırılır. Söz konusu sınırlama, DirectQuery'ye yönelik zamanlanmış önbellek yenileme ayarları için geçerli değildir. Bu ayarlar Premium ve Paylaşılan kapasitelerde aynı kalır.
* Ayrılmış donanımla yalıtım: Paylaşılan kapasitenin yapısı gereği, raporlarınızın ve panolarınızın performansı, kapasitedeki diğer iş yüklerinin isteklerinden etkilenebilir (bu duruma karşı aldığımız önlemlere rağmen). Buna karşılık, Premium, iş yükleriniz için daha tutarlı ve güvenilir bir performans sunmak üzere bunları ilgisiz iş yüklerinden yalıtır.

Bir uygulama, premium kapasite ile destekleniyorsa (Premium'a atanmış olan bir uygulama çalışma alanından yayımlandıysa) yayımlanmış uygulama ve atanmış oldukları lisans fark etmeksizin kuruluşunuzdaki tüm kullanıcılar tarafından kullanılabilir.

### <a name="shared-capacity"></a>Paylaşılan kapasite
Varsayılan olarak, çalışma alanınız paylaşılan kapasitede yer alır. Bu, Uygulama çalışma alanlarının yanı sıra kişisel *Çalışma alanınızı* içerir. İş yüklerinizin diğer müşteriler tarafından paylaşılan hesaplama kaynaklarında çalıştırıldığı paylaşılan kapasite, Power BI'da alışkın olduğunuz deneyimdir.

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Premium kapasite düğümleri
Power BI Premium, farklı sanal çekirdek kapasitelerine sahip düğüm yapılandırmalarıyla kullanılabilir. SKU teklifleri ve maliyet hakkında daha fazla bilgi için bkz. [Power BI fiyatlandırması](https://powerbi.microsoft.com/pricing/). Ayrıca bir [maliyet hesaplayıcı](https://powerbi.microsoft.com/calculator/) da kullanımınıza sunulmuştur. Katıştırılmış analiz kapasite planlamasıyla ilgili bilgiler için bkz. [Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama) teknik incelemesi](https://aka.ms/pbienterprisedeploy).

* P düğümleri, tümleşik dağıtımlar veya hizmet dağıtımları için kullanılabilir.
* EM düğümleri ise yalnızca tümleşik dağıtımlar için kullanılabilir. EM düğümlerinin, Power BI Pro lisansına sahip olan kullanıcılarla uygulamaları paylaşma gibi üst düzey özelliklere erişimi yoktur.

>[!NOTE]
>Bu tablodaki bağlantılar yalnızca Office 365 genel yöneticisi olan kullanıcılar için düzgün bir şekilde görüntülenir, diğer kullanıcılar ise bir 404 hatasıyla karşılaşır. 

| Kapasite Düğümü | Toplam sanal çekirdek sayısı<br/>*(Arka uç + ön uç)* | Arka uç sanal çekirdek sayısı | Ön uç sanal çekirdek sayısı | DirectQuery/canlı bağlantı sınırları | Yoğun saatlerde işlenen maksimum sayfa sayısı | Kullanılabilirlik |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (aylık)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 sanal çekirdek |0,5 sanal çekirdek, 2,5 GB RAM |0,5 sanal çekirdek |Saniyede 3,75 |150-300 |Kullanılabilir |
| [EM2 (aylık)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 sanal çekirdek |1 sanal çekirdek, 5 GB RAM |1 sanal çekirdek |Saniyede 7,5 |301-600 |Kullanılabilir |
| [EM3 (aylık)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 sanal çekirdek |2 sanal çekirdek, 10 GB RAM |2 sanal çekirdek | |601-1200 |Kullanılabilir |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 sanal çekirdek |4 sanal çekirdek, 25 GB RAM |4 sanal çekirdek |saniyede 30 |1.201-2.400 |Kullanılabilir ([aylık](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1) olarak da sunulur) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 sanal çekirdek |8 sanal çekirdek, 50 GB RAM |8 sanal çekirdek |saniyede 60 |2.401-4.800 |Kullanılabilir |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 sanal çekirdek |16 sanal çekirdek, 100 GB RAM |16 sanal çekirdek |saniyede 120 |4.801-9.600 |Kullanılabilir |

* Ön uç sanal çekirdekleri; web hizmetinden, pano ve rapor belge yönetiminden, erişim hakları yönetiminden, zamanlamadan, API'lerden, karşıya yüklemelerden ve indirmelerden, kısacası kullanıcı deneyimiyle ilgili her şeyden sorumludur.
* Arka uç sanal çekirdekleri ise işin zor bölümünden sorumludur: sorgu işleme, önbellek yönetimi, R sunucularını çalıştırma, veri yenileme, doğal dil işleme, gerçek zamanlı akışlar ve raporlar ile resimlerin sunucu tarafında işlenmesi. Arka uç sanal çekirdekleriyle, belirli miktarda bellek de ayrılır. Büyük veri modelleriyle veya çok sayıda etkin veri kümesiyle çalışırken, yeterli belleğe sahip olmak özellikle önemli bir gereksinim haline gelir.

## <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu
Power BI Premium, Power BI Rapor Sunucusu'nu şirket içinde çalıştırma hakkı sağlar. Daha fazla bilgi için bkz. [Power BI Rapor Sunucusu ile çalışmaya başlama](report-server/get-started.md).

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Premium hakkında SSS](service-premium-faq.md)  
[Power BI Premium sürüm notları](service-premium-release-notes.md)  
[Power BI Premium'u satın alma](service-admin-premium-purchase.md)  
[Power BI Premium'u yönetme](service-admin-premium-manage.md)  
[Microsoft Power BI Premium teknik incelemesi](https://aka.ms/pbipremiumwhitepaper)  
[Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama) teknik incelemesi](https://aka.ms/pbienterprisedeploy)  
[Kuruluşunuzda Power BI'ı yönetme](service-admin-administering-power-bi-in-your-organization.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

