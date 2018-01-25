---
title: "Power BI ile AT Internet Bridge'e bağlanma"
description: "Power BI için AT Internet Bridge"
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
ms.openlocfilehash: 67ed59961ca5bc4b382adf105bbc5c97ff470118
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-at-internet-bridge-with-power-bi"></a>Power BI ile AT Internet Bridge'e bağlanma
AT Internet, sahip olduğu birleşik dijital analiz platformu Analytics Suite'i kullanarak verilerinizden anında faydalanabilmenize yardımcı olur. Power BI için AT Internet Bridge içerik paketinde siteniz için ziyaretler, kaynaklar, yerelleştirme ve cihazlar ile ilgili veriler bulunur.

Power BI için [AT Internet Bridge içerik paketine](https://app.powerbi.com/getdata/services/at-internet-bridge) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-at-internet/pbi_getdata.png) 
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-at-internet/pbi_getservices.png) 
3. **AT Internet Bridge** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-at-internet/atinternet.png)
4. Bağlanmak istediğiniz AT Internet Website Number'ı (AT Internet Web Sitesi Numarası) girin.
   
   ![](media/service-connect-to-at-internet/params.png)
5. Kimlik Doğrulama Yöntemi olarak **Temel** seçeneğini belirleyin, AT Internet kullanıcı adınızı ve parolanızı girin ve **Oturum aç**'ı seçin.
   
   ![](media/service-connect-to-at-internet/creds.png)
6. İçeri aktarma sürecini başlatmak için **Bağlan**'a tıklayın. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
    ![](media/service-connect-to-at-internet/atinternet.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
Bu içerik paketinde, aşağıdaki tablolarda yer alan veriler (son 45 güne ait) bulunur:  

    - Conversion (Dönüştürme)  
    - Devices (Cihazlar)  
    - Localization (Yerelleştirme)  
    - Sources (Kaynaklar)  
    - Global Visits (Genel Ziyaretler)  

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

