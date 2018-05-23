---
title: Power BI ile Microsoft Dynamics AX içerik paketine bağlanma
description: Power BI için Microsoft Dynamics AX içerik paketi
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 2e84d52d9e26b23380b9fbc12fdaa4086a2ec7ed
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="connect-to-microsoft-dynamics-ax-content-pack-with-power-bi"></a>Power BI ile Microsoft Dynamics AX içerik paketine bağlanma
Microsoft Dynamics AX, farklı işletme kullanıcılarına yönelik üç farklı Power BI içerik paketine sahiptir. CFO'lar için tasarlanmış olan Financial Performance içerik paketi, kuruluşunuzun mali performansıyla ilgili öngörülere erişim sağlar. Kanal yöneticileri için tasarlanmış olan Retail Channel Performance içerik paketi, Perakende ve Ticaret verilerini doğrudan çekerek eğilimleri tahmin etmek ve öngörüleri keşfetmek için satış performansına odaklanır. COO ve CFO'lar için tasarlanmış olan Cost Management, operasyonel performans hakkında ayrıntılı bilgiler sunar.

Power BI için Microsoft Dynamics AX [Retail Channel Performance](https://app.powerbi.com/getdata/services/dynamics-ax-retail-channel-performance), [Financial Performance](https://app.powerbi.com/getdata/services/dynamics-ax-financial-performance) veya [Cost Management](https://app.powerbi.com/getdata/services/dynamics-ax-cost-management) içerik paketine bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/services.png)
3. Dynamics AX içerik paketlerinden birini belirleyip **Al**'ı seçin.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/mdax.png)
4. Dynamics AX 7 ortamınızın URL'sini belirtin. [Bu parametreleri bulma](#FindingParams) konusundaki ayrıntılı bilgileri aşağıda bulabilirsiniz.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/params.png)
5. **Kimlik doğrulama yöntemi** için **OAuth2** \> **Oturum aç** seçeneklerini belirleyin. İstendiğinde Dynamics AX kimlik bilgilerinizi girin.
   
    ![](media/service-connect-to-microsoft-dynamics-ax/creds.png)
   
    ![](media/service-connect-to-microsoft-dynamics-ax/creds2.png)
6. Onayladıktan sonra içeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
     ![](media/service-connect-to-microsoft-dynamics-ax/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
İçerik paketi Dynamics AX 7 OData akışını kullanarak Perakende Kanalı, Mali ve Maliyet Yönetimi performanslarıyla ilgili bilgiler içeri aktarır.

## <a name="system-requirements"></a>Sistem gereksinimleri
Bu içerik paketi için Dynamics AX 7 ortamı URL'si sağlanması ve kullanıcının OData akışına erişim sahibi olması gerekir.

## <a name="finding-parameters"></a>Parametreleri bulma
<a name="FindingParams"></a>

Kullanıcı, Dynamics AX 7 ortamı URL'sine oturum açtıktan sonra tarayıcıdan ulaşabilir. Dynamics AX ortamının kök dizininin URL'sini Power BI iletişim kutusuna kopyalamanız yeterlidir.

## <a name="troubleshooting"></a>Sorun giderme
Örneğinizin boyutuna bağlı olarak verilerin yüklenmesi biraz zaman alabilir. Power BI'da boş raporlar görüyorsanız lütfen raporlar için gerekli olan OData tablolarına erişim sahibi olduğunuzdan emin olun.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

