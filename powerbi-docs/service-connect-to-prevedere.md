---
title: Power BI ile Prevedere'e bağlanma
description: Power BI için Prevedere
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e15333af4e2fb8508f76517b193ca4351c2782c7
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007938"
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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

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

