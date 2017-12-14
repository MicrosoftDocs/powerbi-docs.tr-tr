---
title: "Power BI ile Salesforce'a bağlanma"
description: "Power BI için Salesforce"
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
ms.openlocfilehash: 6998f273a7e40cae2c7a50f043f79eec540b4789
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-salesforce-with-power-bi"></a>Power BI ile Salesforce'a bağlanma
Power BI ile Salesforce.com hesabınıza kolayca bağlanabilirsiniz. Bu bağlantıyı oluşturduğunuzda verileriniz çekilerek otomatik olarak bir pano ve ilgili raporlar oluşturulur.

Power BI için [Salesforce içerik paketine](https://app.powerbi.com/getdata/services/salesforce) bağlanın veya Power BI ile [Salesforce tümleştirmesi](https://powerbi.microsoft.com/integrations/salesforce) hakkında daha fazla bilgi edinin.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. **Salesforce**'a tıklayıp **Al**'ı seçin.  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. Oturum açma akışını başlatmak için **Oturum Aç**'ı seçin.
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. İstendiğinde Salesforce kimlik bilgilerinizi girin. Power BI'ın temel Salesforce bilgilerinize ve verilerinize erişebilmesi için **İzin Ver**'e tıklayın.
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. Açılan menüdeki seçenekleri kullanarak Power BI'a aktarmak istediğiniz verileri yapılandırın:
   
   * **Pano**
     
     Belirli bir kişiyi (**Satış Yöneticisi** gibi) temel alan önceden tanımlı panolardan birini seçin. Bu panolar Salesforce'tan belirli bir standart veri kümesini alır ve özel alanları dahil etmez.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **Raporlar**
     
     Salesforce hesabınızdan bir veya daha fazla özel rapor seçin. Bu raporlar Salesforce hizmetindeki görünümlerinizle eşleşir ve özel alan veya nesne verilerini içerebilir.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     Herhangi bir rapor görmüyorsanız Salesforce hesabınızda ekleyebilir veya oluşturabilir ve tekrar bağlanmayı deneyebilirsiniz.
7. İçeri aktarma sürecini başlatmak için **Bağlan**'a tıklayın. İçeri aktarma sırasında içeri aktarma işleminin devam ettiğini gösteren bir bildirim görürsünüz. İçeri aktarma işlemi tamamlandığında sol taraftaki gezinti bölmesinde Salesforce verilerinizden oluşturulan bir pano, rapor ve veri kümesi görürsünüz.
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

Bu panoyu, verilerinizi istediğiniz herhangi bir biçimde görüntüleyecek şekilde değiştirebilirsiniz. Soru-Cevap ile sorular sorabilir veya herhangi bir kutucuğa tıklayarak [bağlantılı raporu açabilir](service-dashboard-tiles.md) ve panodaki [kutucukları değiştirebilirsiniz](service-dashboard-edit-tile.md).

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](service-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md)
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md)
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
* API erişimi etkinleştirilmiş ve etkin olarak kullanılan bir Salesforce hesabına bağlantı
* Oturum açma işlemi sırasında Power BI uygulamasına erişim izni
* Hesapta veri çekme ve yenileme için kullanılabilecek yeterli miktarda API çağrısı olması
* Yenileme için geçerli bir kimlik doğrulama belirteci. Salesforce hizmetinde uygulama başına 5 kimlik doğrulama belirteci sınırı olduğu için 5 veya daha az sayıda Salesforce veri kümesini içeri aktardığınızdan emin olun

## <a name="troubleshooting"></a>Sorun giderme
Herhangi bir hatayla karşılaşırsanız lütfen yukarıdaki gereksinimleri inceleyin. Ayrıca, şu an için özel veya korumalı etki alanında oturum açmanın desteklenmediğini unutmayın.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Veri Alma](service-get-data.md)

