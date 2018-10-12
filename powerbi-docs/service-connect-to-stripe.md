---
title: Power BI ile Stripe'a bağlanma
description: Power BI için Stripe
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 550d3bc609afbbac69c63c373e452eac11244152
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46549479"
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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI nedir?](power-bi-overview.md)

[Power BI için veri alma](service-get-data.md)

