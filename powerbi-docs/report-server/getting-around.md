---
title: Power BI Rapor Sunucusu web portalında içeriği yönetme
description: Power BI Rapor Sunucusu web portalında içeriği yönetme hakkında bilgi edinin.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.date: 05/24/2018
ms.author: maggies
ms.openlocfilehash: 35cbfd905db3d6d8464add0fe0e67060c41c9d0a
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85239403"
---
# <a name="manage-content-in-the-web-portal"></a>Web portalında içeriği yönetme 
Power BI Rapor Sunucusu web portalı, Power BI, mobil ve sayfalandırılmış raporlarınızın yanı sıra KPI'lerinizi yönetebileceğiniz şirket içi bir konumdur.

![Rapor Sunucusu web portalı](media/getting-around/report-server-web-portal.png)

Web portalını herhangi bir modern tarayıcıda görüntüleyebilirsiniz. Web portalında raporlar ve KPI'ler klasörler halinde düzenlenir ve bunları sık kullanılan olarak işaretleyebilirsiniz. Burada Excel çalışma kitaplarını da depolayabilirsiniz. Web portalından rapor oluşturmak için ihtiyacınız olan araçları başlatabilirsiniz:

* Power BI Desktop ile oluşturulan **Power BI raporları**: Bunları web portalında ve Power BI mobil uygulamalarında görüntüleyin.
* Rapor Oluşturucusu'nda oluşturulmuş **sayfalandırılmış raporlar**: Yazdırma için iyileştirilmiş modern görünümlü, sabit düzenli belgeler.
* Doğrudan web portalında oluşturulan **KPI'ler**.

Web portalında rapor sunucusu klasörlerine göz atabilir veya belirli raporları arayabilirsiniz. Rapor geçmişinde bir raporu, raporun genel özelliklerini ve eski kopyalarını görüntüleyebilirsiniz. Ayrıca izinlerinize bağlı olarak, e-posta gelen kutusuna veya dosya sistemindeki paylaşılan bir klasöre dağıtım amacıyla raporlara abone olabilirsiniz.

## <a name="web-portal-roles-and-permissions"></a>Web portalı rolleri ve izinleri
Web portalı uygulaması bir tarayıcıda çalışır. Web portalını başlattığınızda gördüğünüz sayfalar, bağlantılar ve seçenekler rapor sunucusunda sahip olduğunuz izinlere bağlı olarak değişiklik gösterir. Tam izinleri olan bir role atanırsanız bir rapor sunucusunu yönetmek için uygulama menülerinin ve sayfaların tamamına erişim sahibi olursunuz. Raporları görüntüleme ve çalıştırma izinlerini içeren bir role atanırsanız yalnızca söz konusu etkinlikler için ihtiyacınız olan menüleri ve sayfaları görürsünüz. Farklı rapor sunucuları için, hatta tek bir rapor sunucusu üzerindeki çeşitli raporlar ve klasörler için farklı rol atamalarına sahip olabilirsiniz.

## <a name="start-the-web-portal"></a>Web portalını başlatma
1. Web tarayıcınızı açın.
   
    [Desteklenen web tarayıcıları ve sürümleri](browser-support.md) listesine göz atın.
2. Adres çubuğuna web portalı URL'sini yazın.
   
    Varsayılan olarak, URL <em>https://[BilgisayarAdı]/reports</em> şeklindedir.
   
    Rapor sunucusu belirli bir bağlantı noktasını kullanacak şekilde yapılandırılmış olabilir. Örneğin, <em>https://[BilgisayarAdı]:80/reports</em> veya <em>https://[BilgisayarAdı]:8080/reports</em>
   
    Web portalının, öğeleri şu kategorilerde gruplandırdığını görürsünüz:
   
   * KPI'ler
   * Mobil raporlar
   * Sayfalandırılmış raporlar
   * Power BI Desktop raporları
   * Excel çalışma kitapları
   * Veri kümeleri
   * Veri kaynakları
   * Kaynaklar

## <a name="manage-items-in-the-web-portal"></a>Web portalındaki öğeleri yönetme
Power BI Rapor Sunucusu, web portalında depoladığınız öğeler üzerinde ayrıntılı denetim sağlar. Örneğin, her sayfalandırılmış rapor üzerinde abonelik, önbelleğe alma, anlık görüntü ve güvenlik ayarları yapabilirsiniz.

1. Bir öğenin sağ üst köşesindeki **Diğer seçenekler**’i (...) ve sonra **Yönet**’i seçin.
   
    ![Manage (Yönet) seçeneğini belirleme](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. Ayarlamak istediğiniz özelliği seçin.
   
    ![Özellik seçme](media/getting-around/report-server-web-portal-manage-properties.png)
3. **Uygula**’yı seçin.

[Working with subscriptions in the web portal (Web portalında aboneliklerle çalışma)](https://docs.microsoft.com/sql/reporting-services/working-with-subscriptions-web-portal) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Rapor Sunucusu nedir?](get-started.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

