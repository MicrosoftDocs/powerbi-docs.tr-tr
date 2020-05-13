---
title: Power BI ile Salesforce'a bağlanma
description: Power BI için Salesforce
author: SarinaJoan
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/30/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b30d3052f9795ffc46a40c470cf2ca342576cc8d
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83307900"
---
# <a name="connect-to-salesforce-with-power-bi"></a>Power BI ile Salesforce'a bağlanma
Power BI ile Salesforce.com hesabınıza kolayca bağlanabilirsiniz. Bu bağlantıyla Salesforce verilerinizi alabilirsiniz ve panoyla raporlar otomatik olarak sağlanır.

Power BI ile [Salesforce tümleştirmesi](https://powerbi.microsoft.com/integrations/salesforce) hakkında daha fazla bilgi edinin.

## <a name="how-to-connect"></a>Bağlanma
1. Power BI gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. **Analytics for Salesforce**'u ve **Al**'ı seçin.  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. **Oturum Aç**'ı seçerek oturum açma akışını başlatın.
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. İstendiğinde Salesforce kimlik bilgilerinizi girin. **İzin Ver**'i seçin ve Power BI'ın temel Salesforce bilgilerinizle verilerinize erişmesini sağlayın.
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. Açılan menüdeki seçenekleri kullanarak Power BI'a aktarmak istediğiniz verileri yapılandırın:
   
   * **Pano**
     
     Belirli bir kişiyi (**Satış Yöneticisi** gibi) temel alan önceden tanımlı panolardan birini seçin. Bu panolar belirli bir Salesforce standart veri kümesini alır; özel alanlar dahil edilmez.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **Raporlar**
     
     Salesforce hesabınızdan bir veya daha fazla özel rapor seçin. Bu raporlar Salesforce hizmetindeki görünümlerinizle eşleşir ve özel alan veya nesne verilerini içerebilir.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     Herhangi bir rapor görmüyorsanız Salesforce hesabınızda ekleyebilir veya oluşturabilir ve tekrar bağlanmayı deneyebilirsiniz.

7. İçeri aktarma işlemini başlatmak için **Bağlan**'ı seçin. İçeri aktarma sırasında içeri aktarma işleminin devam ettiğini gösteren bir bildirim görürsünüz. İçeri aktarma işlemi tamamlandığında gezinti bölmesinde Salesforce verilerinizden oluşturulan bir pano, rapor ve veri kümesi görürsünüz.
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

Panoyu, verilerinizi istediğiniz gibi görüntüleyecek şekilde değiştirebilirsiniz. Soru-Cevap ile sorular sorabilir veya [bir kutucuk seçip](../consumer/end-user-tiles.md) bağlantılı raporu açabilir ve [panodaki kutucukları düzenleyebilir veya kaldırabilirsiniz](../create-reports/service-dashboard-edit-tile.md).

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](../consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucuğu düzenleme veya kaldırma](../create-reports/service-dashboard-edit-tile.md)
* Bağlantılı raporu açmak için [bir kutucuk seçin](../create-reports/service-dashboard-tiles.md)
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements-and-considerations"></a>Sistem gereksinimleri ve önemli noktalar

- API erişimi etkinleştirilmiş ve etkin olarak kullanılan bir Salesforce hesabına bağlantı

- Oturum açma işlemi sırasında Power BI uygulamasına erişim izni

- Hesapta veri çekme ve yenileme için kullanılabilecek yeterli miktarda API çağrısı olması

- Yenileme için geçerli bir kimlik doğrulama belirteci. Salesforce hizmetinde uygulama başına beş kimlik doğrulama belirteci sınırı olduğu için beş veya daha az sayıda Salesforce veri kümesinin içeri aktarıldığından emin olun.

- Salesforce Raporları API’si, en fazla 2.000 veri satırını destekleyen bir kısıtlamaya sahiptir.


## <a name="troubleshooting"></a>Sorun giderme

Herhangi bir hatayla karşılaşırsanız lütfen yukarıdaki gereksinimleri inceleyin. 

Özel veya korumalı alan etki alanında oturum açma işlemi şu anda desteklenmemektedir.

### <a name="unable-to-connect-to-the-remote-server-message"></a>"Uzak sunucuya bağlanılamıyor" iletisi

Salesforce hesabınıza bağlanmaya çalışırken "Uzak sunucuya bağlanılamıyor" iletisi alırsanız, aşağıdaki forumunda bu çözüme bakın: [Salesforce Bağlayıcısı Oturum Açma Hata İletisi: Uzak sunucuya bağlanılamıyor](https://www.outsystems.com/forums/Forum_TopicView.aspx?TopicId=17674&TopicName=log-in-error-message-unable-to-connect-to-the-remote-server&)


## <a name="next-steps"></a>Sonraki adımlar
[Power BI nedir?](../fundamentals/power-bi-overview.md)

[Power BI hizmeti için veri kaynakları](service-get-data.md)
