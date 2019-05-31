---
title: Power BI nedir?
description: Power BI ve nasıl farklı parçaları bir araya - getireceğinizi genel bakış, Power BI Desktop, Power BI hizmeti, Power BI mobil, rapor sunucusu ve Power BI embedded.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: overview
ms.date: 05/29/2019
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 7236caba1c7a8eb07e93c6f2af7068141b8ac3a7
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413048"
---
# <a name="what-is-power-bi"></a>Power BI nedir?
**Power BI**, birbirinden bağımsız veri kaynaklarınızı tutarlı, görsel olarak sürükleyici ve etkileşimli öngörülere dönüştürmenizi sağlamak için birlikte çalışan yazılım hizmetlerinden, uygulamalardan ve bağlayıcılardan oluşan bir koleksiyondur. Verileriniz bir Excel elektronik tablosu veya bulut tabanlı ve şirket içi hibrit veri ambarları koleksiyonu olabilir. Power BI bir kolayca, veri kaynaklarına bağlanmak, görselleştirmenize ve önemli keşfetmek ve herkes ya da bunları istediğiniz herkesle paylaşmak sağlar.

![Power BI için giriş kaynaklarını gösteren diyagram](media/power-bi-overview/power-bi-input-new.png)

Power BI, basit ve hızlı, hızlı Öngörüler, bir Excel elektronik tablosu veya yerel bir veritabanı oluşturma yeteneğine sahip olabilir. Ancak Power BI ayrıca sağlam ve kurumsal düzeyde, kapsamlı modelleme ve gerçek zamanlı analizler, ek olarak özel geliştirme hazır. Bu, kişisel rapor ve görselleştirme aracınız olması ve analiz ve karar altyapısı grubu projeleri, Departmanlar veya tüm şirketler için de görür.

## <a name="the-parts-of-power-bi"></a>Power BI'ın bileşenleri
Power BI oluşur: 
- Windows masaüstü uygulaması olarak adlandırılan **Power BI Desktop**
- Bir çevrimiçi SaaS (*hizmet olarak yazılım*) adlı hizmeti **Power BI hizmeti** 
- Power BI **mobil uygulamalar** Windows, iOS ve Android cihazlar için

![Power BI Desktop, hizmet, mobil](media/power-bi-overview/power-bi-blocks.png)

Bu üç öğe&mdash;Power BI Desktop, hizmet ve mobil uygulamalar&mdash;oluşturması, paylaşması ve bunları veya kendi rolleri en etkili bir şekilde hizmet veren bir şekilde iş öngörüleri kullanma kişiler sağlayacak şekilde tasarlanmıştır.

Dördüncü bir öğe olarak **Power BI Rapor Sunucusu** Power BI raporlarını Power BI Desktop'ta oluşturduktan sonra şirket içi rapor sunucusuna yayımlamanıza olanak tanır. [Power BI Rapor Sunucusu](#on-premises-reporting-with-power-bi-report-server) hakkında daha fazla bilgi edinin.

## <a name="how-power-bi-matches-your-role"></a>Power BI, rolünüzle nasıl eşleşir?
Power BI'ı nasıl kullandığınız bir projedeki veya ekipteki rolünüze bağlıdır. Diğer kişiler, başka rollerdeki için farklı şekilde Power BI kullanıyor olabilir.

Örneğin, öncelikli olarak **Power BI hizmetini** kullanabilirsiniz. Ancak sürekli hesaplama yapan, iş raporları oluşturan iş arkadaşınız raporları oluşturmak ve sonra da bunları görüntüleyebileceğiniz Power BI hizmetine yayımlamak için **Power BI Desktop**'ı yoğun olarak kullanabilir. Başka bir iş arkadaşınız Satışlar, esas olarak kullanabilir, **Power BI telefon uygulaması** satış kotalarını ilerlemeyi izlemek ve yeni müşteri adayı detaylarına gitmek için.

Geliştiriciyseniz, Power BI API’lerini kullanarak veri kümelerine veri gönderebilir veya pano ve raporları kendi özel uygulamalarınıza ekleyebilirsiniz. Yeni bir görsel için fikriniz mi var? Kendi başınıza oluşturun ve başkalarıyla paylaşın.  

Rolünüz için belirli bir projenin elde etmeye çalıştığınız veya bağlı olarak, farklı zamanlarda Power BI'ın her bir öğe de kullanabilirsiniz.

Power BI'ı nasıl kullandığınız, Power BI'ın hangi özelliğinin veya hizmetinin sizin durumunuza en uygun araç olduğuna bağlı olabilir. Örneğin, Power BI Desktop için kendi team müşteri ilişkilerine yönelik istatistiklerle ilgili raporlar oluşturmak için kullanabileceğiniz ve envanter ve Power BI hizmetindeki gerçek zamanlı bir Panoda ediyor üretim görüntüleyebilirsiniz. Power BI'ın her bölümü kullanılabilir ve onu bu kadar esnek ve cazip yapan da budur.

Rolünüzle ilgili belgeleri keşfetme:
- [***Tasarımcılar***](desktop-what-is-desktop.md) için Power BI
- [***Tüketiciler***](consumer/end-user-consumer.md) için Power BI
- [***Geliştiriciler***](developer/what-can-you-do.md) için Power BI
- [***Yöneticileri***](service-admin-administering-power-bi-in-your-organization.md) için Power BI

## <a name="the-flow-of-work-in-power-bi"></a>Power BI'daki iş akışı
Power bı'daki iş akışı veri kaynaklarına bağlanma ve Power BI Desktop'ta bir rapor oluşturmaya başlar. Ardından bu raporu Power BI Desktop'tan Power BI hizmetinde yayımlama ve son kullanıcıların Power BI hizmetinde ve mobil cihazları görüntüleyebilir ve raporla etkileşim kurmak için paylaşın.
Bu yaygın bir iş akışıdır ve üç ana Power BI öğesinin birbirini nasıl tamamladığını gösterir.

Burada ayrıntılı bir [Power BI Desktop ve Power BI hizmeti karşılaştırması](service-service-vs-desktop.md) bulabilirsiniz.

Ancak buluta taşınmaya hazır değilseniz ve raporlarınızı bir kurumsal güvenlik duvarının arkasında tutmak istiyorsanız ne olur?  Okumaya devam edin.

## <a name="on-premises-reporting-with-power-bi-report-server"></a>Power BI rapor sunucusu ile şirket içi raporlama
Oluşturun, dağıtın ve Power BI mobil ve sayfalandırılmış raporlar şirket içinde çok sayıda kullanıma hazır araç ve Power BI Rapor Sunucusu'nun sunduğu Hizmetleri yönetin.

![şirket içi diyagramı](media/power-bi-overview/power-bi-report-server2.png)

Power BI Rapor Sunucusu, güvenlik duvarınızın arkasında dağıttığınız ve sonra raporlarınızı bir web tarayıcısında, mobil cihazda veya e-posta olarak görüntülemeyi içeren farklı yöntemlerle doğru kullanıcılara ilettiğiniz bir çözümdür. Power BI Rapor Sunucusu bulutta Power BI ile uyumlu olduğundan, hazır olduğunuzda buluta taşıyabilirsiniz. 

[Power BI Rapor Sunucusu](report-server/get-started.md) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
- [Hızlı başlangıç: Power BI hizmetinde kullanacağınızı öğrenin](service-the-new-power-bi-experience.md)   
- [Öğretici: Power BI hizmeti ile çalışmaya başlama](service-get-started.md)
- [Hızlı başlangıç: Power BI Desktop'taki verilere bağlanma](desktop-quickstart-connect-to-data.md)
