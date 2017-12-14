---
title: "Power BI ile ClickDimensions'a bağlanma"
description: "Power BI için ClickDimensions"
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
ms.openlocfilehash: cde6ca545d37b2ba490578bf43e7de95b10931d7
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-clickdimensions-with-power-bi"></a>Power BI ile ClickDimensions'a bağlanma
Power BI için ClickDimensions içerik paketi, kullanıcıların, ClickDimensions pazarlama verilerini Power BI'da kullanarak yönetim ekiplerine, gerçekleştirdikleri satış ve pazarlama çalışmalarının başarısına ilişkin daha fazla öngörü sunmasına olanak sağlar. Power BI panolarında ve raporlarında e-posta etkileşimlerini, web ziyaretlerini ve form gönderilerini görselleştirip çözümleyin.

Power BI için [ClickDimensions içerik paketine](https://app.powerbi.com/getdata/services/click-dimensions) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-clickdimensions/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-clickdimensions/services.png)
3. **ClickDimensions** \>  **Al**'ı seçin.
   
   ![](media/service-connect-to-clickdimensions/clickdimensions.png)
4. Veri merkezinizin konumunu (US, EU veya AU) girin ve **Sonraki** seçeneğini belirleyin.
   
   ![](media/service-connect-to-clickdimensions/params.png)
5. **Kimlik Doğrulama Yöntemi**  için **Temel** \> **Oturum aç**'ı seçin. İstendiğinde, ClickDimensions kimlik bilgilerinizi girin. [Bu parametreleri bulma](#FindingParams) konusundaki ayrıntılı bilgileri aşağıda bulabilirsiniz
   
    ![](media/service-connect-to-clickdimensions/creds.png)
6. Onayladıktan sonra içeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
     ![](media/service-connect-to-clickdimensions/dashboard.png)

**Sırada ne var?**

* Panonun üst kısmındaki [Soru-Cevap kutusunda soru sormayı](service-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
Power BI içerik paketine bağlanmak için, hesabınıza ilişkin veri merkezini girmeniz ve ClickDimensions hesabıyla oturum açmanız gerekir. Hangi veri merkezini gireceğinizden emin değilseniz lütfen yöneticinize danışın.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Account Key (Hesap Anahtarı), CRM Settings (CRM Ayarları) \> ClickDimensions Settings (ClickDimensions Ayarları) bölümünde bulunur. ClickDimensions Settings (ClickDimensions Ayarları) bölümündeki Account Key'i (Hesap Anahtarı) kopyalayıp Kullanıcı adı alanına yapıştırın.  

![](media/service-connect-to-clickdimensions/crm.png)  

ClickDimensions Settings (ClickDimensions Ayarları) bölümündeki Power BI Token'ı (Power BI Belirteci) kopyalayıp Kullanıcı adı alanına yapıştırın. Power BI Token (Power BI Belirteci), CRM Settings (CRM Ayarları) \> ClickDimensions Settings (ClickDimensions Ayarları) bölümünde bulunur.  

![](media/service-connect-to-clickdimensions/crm2.png)  

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

