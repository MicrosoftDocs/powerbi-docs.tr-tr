---
title: Power BI ile Planview Enterprise'a bağlanma
description: Power BI için Planview Enterprise
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 64b8b0cce79e2c859ea4d926e1f0d3dfc0c1b83b
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70185853"
---
# <a name="connect-to-planview-enterprise-with-power-bi"></a>Power BI ile Planview Enterprise'a bağlanma
Planview Enterprise içerik paketi, kaynağınızı ve iş yönetim verilerinizi doğrudan Power BI'da yepyeni yöntemlerle görselleştirmenizi sağlar. Planview Enterprise oturum açma kimlik bilgilerinizi kullanarak portföy yatırım harcamalarınızı etkileşimli olarak görün, hangi noktalarda bütçeyi aştığınızı veya bütçenin altında kaldığınızı anlayın ve projelerinizin kurumsal stratejik önceliklerinizle ne kadar uyumlu olduğunu öğrenin. Ayrıca sizin için en önemli olan öngörüleri almak için kullanıma hazır panoları ve raporları genişletebilirsiniz.

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

[Power BI'da Planview Enterprise içerik paketine](https://app.powerbi.com/getdata/services/planview-enterprise) bağlanma

>[!NOTE]
>Planview Enterprise verilerinizi Power BI'a aktarmak için rolünde Reporting Portal Viewer (Raporlama Portalı Görüntüleyicisi) özelliği etkin olan bir Planview Enterprise kullanıcısı olmanız gerekir. Ek gereksinimler için aşağıya bakın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
    ![](media/service-connect-to-planview/get.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
    ![](media/service-connect-to-planview/services.png)
3. Power BI sayfasında **Planview Enterprise**'ı ve ardından **Al**'ı seçin:  
    ![](media/service-connect-to-planview/planview.png)
4. Planview Enterprise URL'si metin kutusuna kullanmak istediğiniz Planview Enterprise sunucusunun URL'sini girin. Planview Enterprise Veritabanı metin kutusuna Planview Enterprise veritabanının adını girip Sonraki düğmesine tıklayın.  
    ![](media/service-connect-to-planview/params.png)
5. Henüz seçili değilse, Kimlik Doğrulama Yöntemi listesinde **Temel** seçeneğini belirleyin. Hesabınızın **Kullanıcı adı** ve **Parola** kimlik bilgilerini girin ve **Oturum aç**'ı seçin.  
   ![](media/service-connect-to-planview/creds.png)
6. Sol bölmedeki pano listesinden Planview Enterprise'ı seçin.  
     Power BI, Planview Enterprise verilerini panoya aktarır. Veri yükleme işleminin biraz zaman alabileceğini göz önünde bulundurun.  
    ![](media/service-connect-to-planview/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="system-requirements"></a>Sistem Gereksinimleri
Planview Enterprise verilerinizi Power BI'a aktarmak için rolünde Reporting Portal Viewer (Raporlama Portalı Görüntüleyicisi) özelliği etkin olan bir Planview Enterprise kullanıcısı olmanız gerekir. Ek gereksinimler için aşağıya bakın.

Bu yordamda, bir Power BI hesabıyla Microsoft Power BI giriş sayfasında oturum açtığınız varsayılmaktadır. Power BI hesabınız yoksa [powerbi.com](https://powerbi.microsoft.com/get-started/) adresine gidip **Power BI - Bulut işbirliği ve paylaşımı** bölümünde **Ücretsiz olarak deneyin**’i seçin. Ardından **Veri Al**’a tıklayın.

## <a name="next-steps"></a>Sonraki adımlar:

[Power BI nedir?](power-bi-overview.md)

[Power BI için veri alma](service-get-data.md)