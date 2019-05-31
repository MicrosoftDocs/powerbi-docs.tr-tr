---
title: Power BI ile Microsoft Azure Tüketim Öngörüleri'ne bağlanma
description: Power BI için Microsoft Azure Tüketim Öngörüleri
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 089f8c31a0b1eb11f6871268f2f848949be95d9b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222117"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Power BI ile Microsoft Azure Tüketim Öngörüleri'ne bağlanma
Power BI içerik paketiyle Power BI'daki Microsoft Azure kullanım verilerinizi araştırın ve izleyin. Veriler günde bir kez otomatik olarak yenilenir.

Power BI için [Microsoft Azure Consumption Insights içerik paketine](https://app.powerbi.com/getdata/services/azureconsumption) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. Seçin **Microsoft Azure Consumption Insights** \> **şimdi edinin**. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Son kaç aya ilişkin veriyi içeri aktarmak istediğinizi ve Azure Kurumsal aboneliğinizin kayıt numarasını girin. [Bu parametreleri bulmaya](#FindingParams) ilişkin ayrıntılı bilgi için aşağıya bakın.
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Bağlanmak için Erişim anahtarınızı girin. Kayıt anahtarınızı Azure EA Portal'da bulabilirsiniz. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. İçeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenmesi için zamanlanmış yenileme zamanlamasını değiştirebilir veya kullanarak isteğe bağlı olarak yenilemeyi deneyin **Şimdi Yenile**

## <a name="whats-included"></a>Neleri kapsar?
Microsoft Azure Consumption Insights içerik paketi, aylık raporlama verilerini bağlanma sırasında sağladığınız ay aralığına içerir. Aralığın bir olduğundan, dahil edilen tarihler veri kümesi yenilendikçe olarak güncelleştirilir.

## <a name="system-requirements"></a>Sistem Gereksinimleri
İçerik Paketi, Azure portalında kurumsal özelliklerine erişim gerektirir. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Power BI raporlama EA doğrudan, iş ortağı ve dolaylı müşterileri faturalandırma bilgileri görüntüleyebilirsiniz için kullanılabilir. Bekliyor. her değeri, bağlantı akışı bulma hakkında ayrıntılar için aşağıdaki bölümü okuyun.

**Ay Sayısı**

* Verileri içeri aktarmak istediğiniz bugünden itibaren ay (1-36) sayısı.

**Kayıt Numarası**

* Konumunda bulabilirsiniz, Azure Kurumsal aboneliğinizin kayıt numarasını [Azure Enterprise Portal](https://ea.azure.com/) altında giriş ekranı **kayıt ayrıntıları**.
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**Erişim Anahtarı**

* Azure Enterprise Portal'da erişim anahtarınızı altında bulabilirsiniz **kullanımı indir** > **API erişim anahtarı**.
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**Daha Fazla Yardım**

* Azure Kurumsal Power BI paketini ayarlama ayarı Ek Yardım için Azure Enterprise Portal'da oturum açın ve bölümündeki API Yardım dosyasını görüntüleyin **yardımcı**. Ayrıca bölümündeki ek yönergeleri bulabilirsiniz **raporları** -> **kullanımı indir** -> **API erişim anahtarı**.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

