---
title: Power BI ile Smartsheet'e bağlanma
description: Power BI için Smartsheet
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e91fda3afe74875ed1b785862f13f53d9aff7108
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46544613"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Power BI ile Smartsheet'e bağlanma
Smartsheet, işbirliği ve dosya paylaşımı için basit bir platform sunar. Power BI için Smartsheet içerik paketi, Smartsheet hesabınıza genel bakış bilgilerini gösteren bir pano, raporlar ve veri kümesi sağlar. Ayrıca, [Power BI Desktop](desktop-connect-to-data.md)'ı kullanarak hesabınızdaki her bir sayfaya doğrudan bağlanabilirsiniz. 

Power BI için [Smartsheet içerik paketine](https://app.powerbi.com/groups/me/getdata/services/smartsheet) bağlanın.

>[!NOTE]
>Ek erişim ayrıcalığı olduğundan, Power BI içerik paketine bağlanılması ve içerik paketinin yüklenmesi için Smartsheet yönetici hesabı tercih edilir.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="whats-included"></a>Neleri kapsar?
Power BI için Smartsheet içerik paketi; Smartsheet hesabınıza yönelik olarak, sahip olduğunuz çalışma alanı, rapor ve sayfa sayısı ve bunların ne zaman değiştirildiği gibi bilgileri içeren bir genel bakış sunar. Yönetici kullanıcılar, en çok sayfa oluşturanlar gibi, sistemlerindeki kullanıcılar ile ilgili bazı bilgileri de görür.  

Hesabınızdaki her bir sayfaya doğrudan bağlanmak için [Power BI Desktop](desktop-connect-to-data.md)'taki Smartsheet bağlayıcısını kullanabilirsiniz.  

## <a name="next-steps"></a>Sonraki adımlar:

[Power BI nedir?](power-bi-overview.md)

[Power BI için veri alma](service-get-data.md)