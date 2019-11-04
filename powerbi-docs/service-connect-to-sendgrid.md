---
title: Power BI ile SendGrid'e bağlanma
description: Power BI için SendGrid
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: c9b844d153cab35938f5070ce4950c57f7964771
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73060533"
---
# <a name="connect-to-sendgrid-with-power-bi"></a>Power BI ile SendGrid'e bağlanma
Power BI'in SendGrid içerik paketi, SendGrid hesabınızdan öngörüler ve istatistikler ayıklamanıza olanak sağlar. SendGrid içerik paketini kullanarak, SendGrid istatistiklerinizi bir panoda görselleştirebilirsiniz.

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="whats-included"></a>Neleri kapsar?
SendGrid panosunda şu ölçümler bulunur:

* Genel e-posta istatistikleri - İstekler, Teslim Edilenler, Geri Dönenler, Engellenen İstenmeyen Postalar, İstenmeyen Posta Raporları vb.
* Kategoriye göre e-posta istatistikleri
* Coğrafyaya göre e-posta istatistikleri
* ISS'ye göre e-posta istatistikleri
* Cihaza, istemciye, tarayıcıya göre e-posta istatistikleri

## <a name="next-steps"></a>Sonraki adımlar
[Power BI nedir?](fundamentals/power-bi-overview.md)

[Veri Alma](service-get-data.md)

