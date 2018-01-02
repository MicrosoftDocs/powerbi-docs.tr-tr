---
title: "Power BI ile Microsoft Azure Tüketim Öngörüleri'ne bağlanma"
description: "Power BI için Microsoft Azure Tüketim Öngörüleri"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggies
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
ms.openlocfilehash: 99f6f4b9159e2ab7261ab179811154ee2ef4929e
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Power BI ile Microsoft Azure Tüketim Öngörüleri'ne bağlanma
Power BI içerik paketiyle Power BI'daki Microsoft Azure kullanım verilerinizi araştırın ve izleyin. Veriler her gün otomatik olarak yenilenir.

Power BI için [Microsoft Azure Consumption Insights içerik paketine](https://app.powerbi.com/getdata/services/azureconsumption) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. **Microsoft Azure Consumption Insights** \> **Al**'ı seçin. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Son kaç aya ilişkin veriyi içeri aktarmak istediğinizi ve Azure Kurumsal aboneliğinizin kayıt numarasını girin. [Bu parametreleri bulmaya](#FindingParams) ilişkin ayrıntılı bilgi için aşağıya bakın.
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Bağlanmak için Erişim anahtarınızı girin. Kaydınıza ilişkin anahtarı Azure EA Portal'da bulabilirsiniz. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. İçeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](service-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* [Bir kutucuğu seçerek](service-dashboard-tiles.md) bağlantılı raporu açın.
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
Microsoft Azure Consumption Insights içerik paketi, bağlantı akışı sırasında sağladığınız ay aralığına ilişkin aylık raporlama verilerini içerir. Bu değişken bir aralık olduğundan, dahil edilen tarihler veri kümesi yenilendikçe güncelleştirilir.

## <a name="system-requirements"></a>Sistem Gereksinimleri
İçerik paketi için Azure Portal'da Kurumsal özelliklerine erişim gereklidir. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Power BI raporlama özelliği, fatura bilgilerini görüntüleyebilen EA Doğrudan, İş Ortağı ve Dolaylı Müşterileri tarafından kullanılabilir. Bağlantı akışında sağlamanız gereken değerlerin her birini nasıl bulacağınız hakkında ayrıntılı bilgi edinmek için lütfen aşağıdaki bölümü okuyun.

**Ay Sayısı**

* Bu değer, (içinde bulunduğunuz günden itibaren) son kaç aya ilişkin veriyi içeri aktarmak istediğinizi belirten, 1 ila 36 arasında bir sayı olmalıdır.

**Kayıt Numarası**

* Bu, [Azure Enterprise Portal](https://ea.azure.com/)'ın giriş ekranındaki "Kayıt Ayrıntıları" bölümünde bulabileceğiniz Azure Kurumsal kayıt numaranızdır.
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**Erişim Anahtarı**

* Anahtarınızı, Azure Enterprise Portal'da "İndirme Kullanımı" > "API Erişim Anahtarı" bölümünde bulabilirsiniz
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**Daha Fazla Yardım**

* Azure Kurumsal Power BI Paketini ayarlama hakkında daha fazla yardım almak istiyorsanız Azure Enterprise Portal'da oturum açın, "Yardım" bölümündeki API Yardım Dosyasını ve Raporlar -> İndirme Kullanımı -> API Erişim Anahtarı bölümündeki ek yönergeleri görüntüleyin. 

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

