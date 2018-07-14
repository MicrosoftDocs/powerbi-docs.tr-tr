---
title: Power BI nedir?
description: Power BI’ya ve farklı bölümlerin (Power BI Desktop, Power BI hizmeti, Power BI mobil, Rapor Sunucusu, Power BI Embedded) birbirine uyumuna genel bakış.
author: mihart
manager: kfile
ms.service: powerbi
ms.component: powerbi-service
ms.topic: overview
ms.date: 06/22/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: c2e0dc401e5927e69ecb9b059042df646b238bd5
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36944411"
---
# <a name="what-is-power-bi"></a>Power BI nedir?
**Power BI**, birbirinden bağımsız veri kaynaklarınızı tutarlı, görsel olarak sürükleyici ve etkileşimli öngörülere dönüştürmenizi sağlamak için birlikte çalışan yazılım hizmetlerinden, uygulamalardan ve bağlayıcılardan oluşan bir koleksiyondur. Verilerinizin basit bir Excel elektronik tablosu veya bulut tabanlı ve şirket içi hibrit veri ambarlarından oluşan bir koleksiyon olması fark etmeksizin **Power BI**, veri kaynaklarınıza kolayca bağlanmanıza, önemli verileri görselleştirmenize (veya araştırmanıza) ve bunları istediğiniz herkesle paylaşmanıza olanak sağlar.

![Power BI için giriş kaynaklarını gösteren diyagram](media/power-bi-overview/power-bi-input.png)

**Power BI**, Excel elektronik tablolarından veya yerel veritabanlarından hızlı öngörüler oluşturma özelliği ile işlemlerinizi basit ve hızlı şekilde gerçekleştirebilir. Ayrıca, **Power BI** özel geliştirmenin yanı sıra kapsamlı modelleme ve gerçek zamanlı analiz işlemlerinizi gerçekleştirmeye hazır, sağlam ve kurumsal sınıf bir hizmettir. Bu nedenle Power BI, kişisel rapor ve görselleştirme aracınız olabileceği gibi grup projeleri, departmanlar veya tüm şirket için analiz ve karar mekanizması olarak da kullanılabilir.

## <a name="the-parts-of-power-bi"></a>Power BI'ın bileşenleri
Power BI; **Power BI Desktop** adlı bir Windows masaüstü uygulamasını, **Power BI hizmeti** adlı bir çevrimiçi SaaS (*Hizmet olarak Yazılım*) hizmetini ve Windows işletim sistemi yüklü telefon ve tabletlerin yanı sıra iOS cihazlarında ve Android cihazlarda kullanılabilen Power BI mobil **uygulamalarını** içerir.

![Power BI Desktop, hizmet, mobil](media/power-bi-overview/power-bi-blocks.png)

Bu üç bileşen (**Desktop**, **hizmet** ve **Mobil**) kullanıcıların ihtiyaçlarına veya sahip oldukları role uygun iş öngörüleri oluşturmasına, paylaşmasına ve kullanmasına olanak sağlamak için tasarlanmıştır.

## <a name="how-power-bi-matches-your-role"></a>Power BI, rolünüzle nasıl eşleşir?
Power BI'ı nasıl kullandığınız bir projedeki veya ekipteki rolünüze bağlıdır. Başka rollerdeki kullanıcılar Power BI'ı farklı şekillerde kullanabilir ve bu oldukça normaldir.

Örneğin, siz en çok **Power BI hizmetini** kullanırken, sürekli hesaplama yapan ve rapor oluşturan (ardından, Desktop raporlarını sizin de daha sonra görüntüleyebileceğiniz Power BI hizmetinde yayımlayan) iş arkadaşınız **Power BI Desktop**'ı çok daha fazla kullanabilir. Satış departmanındaki başka bir iş arkadaşınız ise satış kotalarındaki ilerlemeyi izlemek ve yeni satış fırsatları hakkında ayrıntılı bilgi edinmek için Power BI telefon uygulamasını daha çok kullanabilir.

Geliştiriciyseniz, Power BI API’lerini kullanarak veri kümelerine veri gönderebilir veya pano ve raporları kendi özel uygulamalarınıza ekleyebilirsiniz. Yeni bir görsel için fikriniz mi var? Kendi başınıza oluşturun ve başkalarıyla paylaşın.  

Bununla birlikte, ne elde etmek istediğinize veya belirli bir proje için sahip olduğunuz role bağlı olarak farklı dönemlerde **Power BI**'ın her bir bileşenini kullanabilirsiniz.

Bir yandan Power BI hizmetindeki gerçek zamanlı bir panoda envanter ve üretim sürecini izlerken diğer yandan kendi ekibiniz için müşteri ilişkilerine yönelik istatistiklerle ilgili raporlar oluşturmak üzere **Power BI Desktop**'ı kullanabilirsiniz. Power BI'ı nasıl kullandığınız, Power BI'ın hangi özelliğinin veya hizmetinin durumunuz için en uygun araç olduğuna göre değişiklik gösterebilir. Ancak, Power BI'ın her bir bileşenini kullanabilirsiniz; onu bu kadar esnek ve etkileyici yapan da budur.

## <a name="the-flow-of-work-in-power-bi"></a>Power BI'daki iş akışı
Power BI’da ortak bir iş akışı, veri kaynaklarına bağlanarak ve **Power BI Desktop**’ta rapor oluşturarak başlar. Bu rapor daha sonra **Desktop**’tan **Power BI hizmetine** yayımlanır ve **hizmet** ve **mobil** kullanıcılarının raporu *tüketebilmesi* (görüntüleme ve etkileşimde bulunma) için paylaşılır.
Bazı durumlarda, iş arkadaşlarınızın **hizmeti** rapor düzenlemek, pano oluşturmak ve kendi çalışmalarını da paylaşmak için kullanabilmesi amacıyla onlara kendinizinkine benzer izinler vermek isteyebilirsiniz (*creator* izinleri).

Daha yaygın iş akışlarından biri olmasına rağmen her zaman bu yöntemle gerçekleşmez ve üç ana Power BI öğesinin birbirini nasıl tamamladığını gösterir.

Ancak buluta taşınmaya hazır değilseniz ve raporlarınızı bir kurumsal güvenlik duvarının arkasında tutmak istiyorsanız ne olur?  Okumaya devam edin.

## <a name="on-premises-reporting-with-power-bi-report-server"></a>Power BI rapor sunucusu ile şirket içi raporlama
Power BI Rapor Sunucusu'nun sunduğu, kullanıma hazır çok sayıda araç ve hizmeti kullanarak Power BI raporları, mobil raporlar ve sayfalandırılmış raporlar oluşturun, bunları dağıtın ve yönetin.

![şirket içi diyagramı](media/power-bi-overview/power-bi-report-server2.png)

Power BI Rapor Sunucusu, güvenlik duvarınızın arkasında dağıttığınız ve sonra raporlarınızı bir web tarayıcısında, mobil cihazda veya e-posta olarak görüntülemeyi içeren farklı yöntemlerle doğru kullanıcılara ilettiğiniz bir çözümdür. Power BI Rapor Sunucusu bulutta Power BI ile uyumlu olduğundan, hazır olduğunuzda buluta taşıyabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI hizmetinde oturum açma, bazı verileri alma ve kullanmayı öğrenme](service-the-new-power-bi-experience.md)   
[Öğretici: Power BI hizmetini kullanmaya başlama](service-get-started.md)
