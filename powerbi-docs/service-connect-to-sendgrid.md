---
title: "Power BI ile SendGrid'e bağlanma"
description: "Power BI için SendGrid"
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
ms.openlocfilehash: b4f4a999ed9929366f58f719030490fc56f5364d
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-sendgrid-with-power-bi"></a>Power BI ile SendGrid'e bağlanma
Power BI'in SendGrid içerik paketi, SendGrid hesabınızdan öngörüler ve istatistikler ayıklamanıza olanak sağlar. SendGrid içerik paketini kullanarak, SendGrid istatistiklerinizi bir panoda görselleştirebilirsiniz.

Power BI için [SendGrid içerik paketine](https://app.powerbi.com/getdata/services/sendgrid) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-sendgrid/pbi_getdata.png) 
2. **Hizmetler** kutusundaki **Al**'ı seçin.
   
   ![](media/service-connect-to-sendgrid/pbi_getservices.png) 
3. **SendGrid** içerik paketini seçin ve **Al**'a tıklayın.
   
   ![](media/service-connect-to-sendgrid/sendgrid.png) 
4. İstendiğinde, SendGrid kullanıcı adınızı ve parolanızı sağlayın. **Oturum Aç**'ı seçin.
   
   ![](media/service-connect-to-sendgrid/pbi_sendgridsignin.png)
5. Power BI verileri içeri aktardıktan sonra sol gezinti bölmesinde, son 90 günlük e-posta istatistiklerinizle doldurulmuş yeni bir pano, rapor ve veri kümesi görürsünüz. Yeni öğeler sarı yıldız işareti \* ile gösterilir.
   
   ![](media/service-connect-to-sendgrid/pbi_sendgriddash.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](service-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
SendGrid panosunda şu ölçümler bulunur:

* Genel e-posta istatistikleri - İstekler, Teslim Edilenler, Geri Dönenler, Engellenen İstenmeyen Postalar, İstenmeyen Posta Raporları vb.
* Kategoriye göre e-posta istatistikleri
* Coğrafyaya göre e-posta istatistikleri
* ISS'ye göre e-posta istatistikleri
* Cihaza, istemciye, tarayıcıya göre e-posta istatistikleri

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Veri Alma](service-get-data.md)

