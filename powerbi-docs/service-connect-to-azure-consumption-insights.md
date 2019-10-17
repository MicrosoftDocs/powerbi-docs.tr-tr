---
title: Power BI ile Microsoft Azure Tüketim Öngörüleri'ne bağlanma
description: Power BI için Microsoft Azure Tüketim Öngörüleri
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 09/25/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e51f936e44e8c8ee3442aedfb2389675774c0a47
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72020423"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Power BI ile Microsoft Azure Tüketim Öngörüleri'ne bağlanma
Power BI içerik paketiyle Power BI hizmetindeki Microsoft Azure kullanım verilerinizi araştırın ve izleyin. Veriler günde bir kez otomatik olarak yenilenir.

Power BI hizmeti için [Microsoft Azure Consumption Insights içerik paketine](https://app.powerbi.com/getdata/services/azureconsumption) bağlanın.

> [!NOTE]
> Daha özelleştirilmiş bir kurulum için Power BI Desktop’taki [Azure Consumption Insights bağlayıcısını](desktop-connect-azure-consumption-insights.md) kullanmayı deneyin.

## <a name="how-to-connect"></a>Bağlanma
1. Power BI hizmetinde, sol gezinti bölmesinin alt kısmında bulunan **Veri Al** seçeneğini belirleyin.
   
    ![Veri Al](media/service-connect-to-azure-consumption-insights/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![Hizmet alın](media/service-connect-to-azure-consumption-insights/services.png)
3. **Microsoft Azure Consumption Insights** \> **Hemen al**’ı seçin. 
   
   ![Şimdi edinin](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Son kaç aya ilişkin veriyi içeri aktarmak istediğinizi ve Azure Kurumsal aboneliğinizin kayıt numarasını girin. [Bu parametreleri bulmaya](#FindingParams) ilişkin ayrıntılı bilgi için aşağıya bakın.
   
    ![Microsoft Azure Consumption Insights’a bağlan](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Bağlanmak için Erişim anahtarınızı girin. Kayıt anahtarınızı Azure EA Portal’da bulabilirsiniz. 
   
    ![Microsoft Azure Consumption Insights: anahtar](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. İçeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
   ![Microsoft Azure Consumption Insights panosu](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
Microsoft Azure Consumption Insights içerik paketi, bağlanırken sağladığınız ay aralığına ilişkin aylık raporlama verilerini içerir. Bu değişken bir aralık olduğundan, dahil edilen tarihler veri kümesi yenilendikçe güncelleştirilir.

## <a name="system-requirements"></a>Sistem Gereksinimleri
İçerik paketi için Azure portalının Kurumsal özelliklerine erişim gereklidir. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Power BI raporlama özelliği, fatura bilgilerini görüntüleyebilen EA Doğrudan, İş Ortağı ve Dolaylı Müşterilerine sunulur. Bağlantı akışında sağlamanız gereken değerlerin her birini nasıl bulacağınıza ilişkin ayrıntılı bilgi edinmek için aşağıdaki bölümü okuyun.

**Ay Sayısı**

* Bugünden geriye doğru kaç aylık veriyi (1-36) içeri aktarmak istediğinizi belirtmenizi sağlar.

**Kayıt Numarası**

* [Azure Enterprise Portal](https://ea.azure.com/) giriş ekranındaki **Kayıt Ayrıntıları** bölümünde bulabileceğiniz Azure Kurumsal kayıt numaranız.
  
    ![Kayıt Numarası](media/service-connect-to-azure-consumption-insights/params2.png)

**Erişim Anahtarı**

* Erişim anahtarınızı, Azure Enterprise Portal’da **İndirme Kullanımı** > **API Erişim Anahtarı** bölümünde bulabilirsiniz.
  
    ![Erişim Anahtarı](media/service-connect-to-azure-consumption-insights/creds2.png)

**Daha Fazla Yardım**

* Azure Kurumsal Power BI Paketini ayarlamayla ilgili daha fazla yardım almak için Azure Enterprise Portal’da oturum açıp **Yardım** bölümünde API Yardım Dosyası’nı görüntüleyin. **Raporlar** -> **İndirme Kullanımı** -> **API Erişimi Anahtarı** bölümünde de buna ilişkin ek yönergeler bulabilirsiniz.
* Daha özelleştirilmiş bir kurulum için Power BI Desktop’taki [Azure Consumption Insights bağlayıcısını](desktop-connect-azure-consumption-insights.md) kullanmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar

Power BI Desktop’ta [Azure Consumption Insights bağlayıcısı](desktop-connect-azure-consumption-insights.md)

[Power BI'da veri alma](service-get-data.md)

