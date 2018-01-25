---
title: "Power BI ile Prevedere'e bağlanma"
description: "Power BI için Prevedere"
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
ms.openlocfilehash: fd9426a8fce0ed1d707184b421a93f989852a33d
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-prevedere-with-power-bi"></a>Power BI ile Prevedere'e bağlanma
İşinizi kendinizden emin ve proaktif bir şekilde ileriye taşımak için özel ve kritik finansal bilgilere erişim elde edin.

Power BI için [Prevedere içerik paketine](https://app.powerbi.com/getdata/services/prevedere) bağlanın.

>[!NOTE]
>Mevcut bir Prevedere kullanıcısı değilseniz lütfen [örnek anahtarı](https://prevederepowerbiconnector.azurewebsites.net/static/learnmore.html) kullanarak bu çözümü deneyin.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-prevedere/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-prevedere/services.png)
3. **Prevedere**'i ve ardından **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-prevedere/connect.png)
4. **Kimlik Doğrulama Yöntemi** için **Anahtar** seçeneğini belirleyin ve Prevedere API anahtarınızı girin.
   
    ![](media/service-connect-to-prevedere/creds.png)
5. İçeri aktarma işlemini başlatmak için **Oturum aç** seçeneğini belirleyin. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
     ![](media/service-connect-to-prevedere/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
İçerik paketi; perakende tahminlerinize, tahmin modellerinize, öncü göstergelerinize ve daha fazlasına ilişkin öngörüler edinir.

## <a name="system-requirements"></a>Sistem gereksinimleri
Bu içerik paketi için Prevedere API anahtarı veya örnek anahtar (aşağıya bakın) gerekir.

## <a name="finding-parameters"></a>Parametreleri bulma
<a name="FindingParams"></a>

Mevcut müşteriler verilerine kendi API anahtarlarını kullanarak erişebilir. Henüz bir müşteri değilseniz [örnek anahtarını](https://prevederepowerbiconnector.azurewebsites.net/static/learnmore.html) kullanarak verilere ve analizlere yönelik bir örneğe göz atabilirsiniz.

## <a name="troubleshooting"></a>Sorun giderme
Örneğinizin boyutuna bağlı olarak verilerin yüklenmesi biraz zaman alabilir.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

