---
title: Power BI ile Projectplace'e bağlanma
description: Power BI için Projectplace
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 2fb053c5c9754cdba1fde81cca5765799bb71013
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-projectplace-by-planview-with-power-bi"></a>Power BI ile Projectplace by Planview'a bağlanma
Projectplace by Planview içerik paketi ile işbirliğine dayalı proje verilerinizi, tamamen yeni yöntemlerle doğrudan Power BI'da görselleştirebilirsiniz. Önemli proje istatistiklerini etkileşimli olarak görüntülemek, en etkin ve üretken ekip üyelerinizi bulmak ve Projectplace hesabınızdaki projeler arasında risk altında bulunan kartları ve etkinlikleri belirlemek için Projectplace oturum açma kimlik bilgilerinizi kullanın. Ayrıca, sizin için en önemli öngörüleri edinmek üzere kullanıma hazır pano ve raporların kapsamını genişletebilirsiniz.

[Power BI'da Projectplace içerik paketine bağlanma](https://app.powerbi.com/getdata/services/projectplace)

>[!NOTE]
>Projectplace verilerinizi Power BI'a aktarmak için bir Projectplace kullanıcısı olmanız gerekir. Ek gereksinimler için aşağıya bakın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
    ![](media/service-connect-to-projectplace/get.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
    ![](media/service-connect-to-projectplace/services.png)
3. Power BI sayfasında **Projectplace by Planview**'u ve ardından **Al**'ı seçin:  
   
    ![](media/service-connect-to-projectplace/projectplace.png)
4. OData Feed URL (OData Akış URL'si) metin kutusuna, aşağıdaki görüntüde belirtildiği gibi, kullanmak istediğiniz Projectplace OData akışına ilişkin URL'yi girin:
   
    ![](media/service-connect-to-projectplace/params.png)
5. Henüz seçili değilse, Kimlik doğrulama yöntemi listesinde **OAuth** seçeneğini belirleyin. **Oturum Aç**'a tıklayın ve oturum açma akışını takip edin.  
   
   ![](media/service-connect-to-projectplace/creds.png)
6. Sol bölmedeki panolar listesinde **Projectplace**'i seçin. Power BI, Projectplace verilerini panoya aktarır. Veri yükleme işleminin biraz zaman alabileceğini göz önünde bulundurun.  
   
    Panoda, Projectplace veritabanınızdaki verileri görüntüleyen kutucuklar bulunur. Aşağıda, Power BI'daki varsayılan Projectplace panosuna ilişkin bir örnek gösterilmiştir.
   
    ![](media/service-connect-to-projectplace/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
Projectplace verilerinizi Power BI'a aktarmak için bir Projectplace kullanıcısı olmanız gerekir. Bu yordamda, bir Power BI hesabıyla Microsoft Power BI giriş sayfasında oturum açtığınız varsayılmaktadır. Power BI hesabınız yoksa Power BI giriş sayfasında yeni bir ücretsiz Power BI hesabı oluşturun ve Veri Al'a tıklayın.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

