---
title: "Power BI ile Planview Enterprise'a bağlanma"
description: "Power BI için Planview Enterprise"
services: powerbi
documentationcenter: 
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
ms.openlocfilehash: cd7026fe72bff40fd28aadf4ed3d2f9ee2b5d2fe
ms.sourcegitcommit: c24e5d7bd1806e0d637e974b5143ab5125298fc6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2018
---
# <a name="connect-to-planview-enterprise-with-power-bi"></a>Power BI ile Planview Enterprise'a bağlanma
Planview Enterprise içerik paketi, kaynağınızı ve iş yönetim verilerinizi doğrudan Power BI'da yepyeni yöntemlerle görselleştirmenizi sağlar. Planview Enterprise oturum açma kimlik bilgilerinizi kullanarak portföy yatırım harcamalarınızı etkileşimli olarak görün, hangi noktalarda bütçeyi aştığınızı veya bütçenin altında kaldığınızı anlayın ve projelerinizin kurumsal stratejik önceliklerinizle ne kadar uyumlu olduğunu öğrenin. Ayrıca sizin için en önemli olan öngörüleri almak için kullanıma hazır panoları ve raporları genişletebilirsiniz.

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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
Planview Enterprise verilerinizi Power BI'a aktarmak için rolünde Reporting Portal Viewer (Raporlama Portalı Görüntüleyicisi) özelliği etkin olan bir Planview Enterprise kullanıcısı olmanız gerekir. Ek gereksinimler için aşağıya bakın.

Bu yordamda, bir Power BI hesabıyla Microsoft Power BI giriş sayfasında oturum açtığınız varsayılmaktadır. Power BI hesabınız yoksa Power BI giriş sayfasında yeni bir ücretsiz Power BI hesabı oluşturun ve Veri Al'a tıklayın.

## <a name="next-steps"></a>Sonraki adımlar:

[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI için Veri Alma](service-get-data.md)