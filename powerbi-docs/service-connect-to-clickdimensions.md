---
title: Power BI ile ClickDimensions'a bağlanma
description: Power BI için ClickDimensions
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 9506ab48e48fe04e07de8dcb08ad5234d31045cf
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34242967"
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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
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

