---
title: "Power BI ile Smartsheet'e bağlanma"
description: "Power BI için Smartsheet"
services: powerbi
documentationcenter: 
author: joeshoukry
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
ms.author: yshoukry
ms.openlocfilehash: 6e212f1a3cf114ebdd4eeba59aee20cfa4e02182
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Power BI ile Smartsheet'e bağlanma
Smartsheet, işbirliği ve dosya paylaşımı için basit bir platform sunar. Power BI için Smartsheet içerik paketi, Smartsheet hesabınıza genel bakış bilgilerini gösteren bir pano, raporlar ve veri kümesi sağlar. Ayrıca, [Power BI Desktop](desktop-connect-to-data.md)'ı kullanarak hesabınızdaki her bir sayfaya doğrudan bağlanabilirsiniz. 

Power BI için [Smartsheet içerik paketine](https://app.powerbi.com/groups/me/getdata/services/smartsheet) bağlanın.

>[!NOTE]
>Ek erişim ayrıcalığı olduğundan, Power BI içerik paketine bağlanılması ve içerik paketinin yüklenmesi için Smartsheet yönetici hesabı tercih edilir.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmındaki **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-smartsheet/pbi_getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-smartsheet/pbi_getservices.png) 
3. **Smartsheet \> Al**'ı seçin.
   
   ![](media/service-connect-to-smartsheet/smartsheet.png)
4. Kimlik doğrulama yöntemi için **OAuth2\> Oturum aç** seçeneğini belirleyin.
   
   İstendiğinde Smartsheet kimlik bilgilerinizi girin ve kimlik doğrulaması işlemindeki diğer adımları uygulayın.
   
   ![](media/service-connect-to-smartsheet/creds.png)
   
   ![](media/service-connect-to-smartsheet/creds2.png)
5. Veriler Power BI tarafından içeri aktarıldıktan sonra sol gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz. Yeni öğeler sarı bir yıldız işareti \* ile gösterilir; Smartsheet girişini seçin.
   
   ![](media/service-connect-to-smartsheet/dashboard.png)

**Sırada ne var?**

* Panonun üst kısmındaki [Soru-Cevap kutusunda soru sormayı](service-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
Power BI için Smartsheet içerik paketi; Smartsheet hesabınıza yönelik olarak, sahip olduğunuz çalışma alanı, rapor ve sayfa sayısı ve bunların ne zaman değiştirildiği gibi bilgileri içeren bir genel bakış sunar. Yönetici kullanıcılar, en çok sayfa oluşturanlar gibi, sistemlerindeki kullanıcılar ile ilgili bazı bilgileri de görür.  

Hesabınızdaki her bir sayfaya doğrudan bağlanmak için [Power BI Desktop](desktop-connect-to-data.md)'taki Smartsheet bağlayıcısını kullanabilirsiniz.  

## <a name="next-steps"></a>Sonraki adımlar:

[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI için veri alma](service-get-data.md)