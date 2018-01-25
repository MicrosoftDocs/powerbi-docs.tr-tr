---
title: "Power BI ile Stripe'a bağlanma"
description: "Power BI için Stripe"
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
ms.openlocfilehash: 5ed68a3ee64803fa895ad9837fe37351163d09af
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-stripe-with-power-bi"></a>Power BI ile Stripe'a bağlanma
Power BI içerik paketi ile Power BI'da Stripe verilerinizi görselleştirin ve araştırın. Power BI Stripe içerik paketi Müşterileriniz, Ödemeleriniz, Olaylarınız ve Faturalarınız ile ilgili verileri çeker. Veriler, son 30 günde gerçekleşen en yeni on bin olayı ve beş bin ödemeyi içerir. İçerik, sizin denetiminizde olan bir zamanlamada her gün otomatik olarak bir kez yenilenir. 

[Power BI için Stripe içerik paketine](https://app.powerbi.com/getdata/services/stripe) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmındaki Veri Al seçeneğini belirleyin.  
   
    ![](media/service-connect-to-stripe/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.  
   
    ![](media/service-connect-to-stripe/services.png)  
3. **Stripe** &gt; **Al** seçeneğini belirleyin.  
   
    ![](media/service-connect-to-stripe/stripe.png)  
4. Bağlanmak için Stripe [API anahtarınızı](https://dashboard.stripe.com/account/apikeys) girin.  
   
    ![](media/service-connect-to-stripe/creds.png)
5. İçeri aktarma süreci otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yıldız ile işaretlenmiş yeni bir pano, rapor ve model görüntülenir. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
    ![](media/service-connect-to-stripe/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI için Veri Alma](service-get-data.md)

