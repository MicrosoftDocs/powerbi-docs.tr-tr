---
title: "Power BI örneklerini kullanma eğitimi."
description: "Eğitim: Power BI örneklerini kullanma"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 03/08/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: d92edce9ae1332c4a0c73be5db93201c9b87dc86
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="the-power-bi-samples-a-tutorial"></a>Power BI örnekleri eğitimi
<!-- Shared newnav Include -->
[!INCLUDE [newnavbydefault](./includes/newnavbydefault.md)]

[Power BI için örnek veri kümeleri](sample-datasets.md) makalesiyle başlamanızı öneririz. Söz konusu makalede örnekler hakkında her şeyi, nasıl alındıklarını, nereye kaydedildiklerini ve örneklerin sunduğu içeriklerden bazılarını öğrenebilirsiniz. Temel konuları kavradıktan sonra bu eğitime geri dönebilirsiniz.   

## <a name="about-this-tutorial"></a>Bu eğitim hakkında
Bu eğitimde, örnek içerik paketlerini içeri aktarma, Power BI hizmetine ekleme ve içeriği açma ile ilgili bilgiler sağlanmaktadır. *İçerik paketleri*, veri kümesinin bir pano ve raporla birlikte sunulduğu bir örnek türüdür. Örnek içerik paketlerine Power BI'da **Veri Al** seçeneğini belirleyerek ulaşabilirsiniz.

> [!NOTE]
> Bu eğitim, Power BI Desktop'a değil, Power BI hizmetine yöneliktir.
> 
> 

Bu eğitimde kullanılan *Perakende Analizi* örnek içerik paketi, bir pano, rapor ve veri kümesinden oluşur.
Bu içerik paketine ve senaryosuna aşina olmanız için, başlamadan önce [Perakende Analizi örneğine ilişkin tura katılabilirsiniz](sample-retail-analysis.md).

## <a name="get-data-in-this-case-get-a-sample-content-pack"></a>Veri alma (bu durumda, bir örnek içerik paketi alma)
1. Power BI hizmetine (app.powerbi.com) gidin ve oturum açın.
2. Çalışma alanı seçin ve yeni bir pano oluşturun.  
   
    ![](media/sample-tutorial-connect-to-the-samples/power-bi-create-dashboard2.png)
3. **Retail analysis sample** olarak adlandırın.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-name-dashboard.png)
4. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin. **Veri Al**'ı görmüyorsanız ![](media/sample-tutorial-connect-to-the-samples/expand-nav.png) seçeneğini belirleyerek gezinti bölmesini genişletin.
   
   ![](media/sample-tutorial-connect-to-the-samples/pbi_getdata.png)
5. **Örnekler**'i seçin.  
   
   ![](media/sample-tutorial-connect-to-the-samples/pbi_samplesdownload.png)
6. *Perakende Analizi Örneği*'ni ve ardından **Bağlan**'ı seçin.   
   
   ![](media/sample-tutorial-connect-to-the-samples/pbi_retailanalysissampleconnect.png)

## <a name="what-exactly-was-imported"></a>Tam olarak neler içeri aktarılır?
Örnek içerik paketleri söz konusuysa **Bağlan**'ı seçtiğinizde Power BI, ilgili içerik paketinin bir kopyasını alıp sizin için bulutta depolar. İçerik paketini oluşturan kişi bir veri kümesi, rapor ve de pano eklemiş olduğundan, **Bağlan**a tıkladığınızda bunları edinirsiniz.

1. Power BI yeni bir Pano oluşturur ve bunu **Panolar** sekmesinde listeler. Sarı yıldız işareti, yeni olduğunu bilmenizi sağlar.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-new-dashboard.png)
2. **Raporlar** sekmesini açın.  Burada *Retail Analysis Sample* adlı yeni bir rapor göreceksiniz.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-new-report.png)
   
   Ardından, **Veri Kümeleri** sekmesine bakın.  Yeni bir veri kümesi de vardır.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-new-dataset.png)

## <a name="explore-your-new-content"></a>Yeni içeriğinizi keşfedin
Şimdi pano, veri kümesini ve raporu kendiniz keşfedin. Panolar, raporlar ve veri kümelerinde gezinmek için izleyebileceğiniz birçok farklı yol vardır ve bu yollardan yalnızca biri aşağıda ele alınmıştır.  

> [!TIP]
> Önce ayrıntılı bir açıklama ister misiniz?  Bu örneğe ilişkin adım adım kılavuz için [Perakende Analizi örneğine ilişkin turu](sample-retail-analysis.md) deneyin.
> 
> 

1. **Panolar** sekmenize geri gidin, *Retail Analysis Sample* panonuzu seçerek açın.    
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-dashboards.png)
2. Pano açılır.  Çeşitli görselleştirme kutucukları bulunur.
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-dashboards2new.png)
3. Bağlantılı raporu açmak için bir kutucuk seçin.  Bu örnekte, alan grafiğini seçeceğiz. (Önceki görüntüde pembeyle gösterilmiştir.) Raporun, alan grafiğini içeren sayfası açılır.
   
    ![](media/sample-tutorial-connect-to-the-samples/power-bi-report.png)
   
   > [!NOTE]
   > Kutucuk eğer [Power BI Soru-Cevap](power-bi-q-and-a.md) kullanılarak oluşturulsaydı bunun yerine Soru-Cevap sayfası açılırdı.
   > 
   > 
4. **Veri Kümeleri** sekmenizde, veri kümenizi araştırmanıza yönelik çeşitli seçenekleriniz vardır.  Açıp tüm satırları ve sütunları (Power BI Desktop veya Excel'de görebildiğiniz gibi) görmeniz mümkün olmayacaktır.  Birisi iş arkadaşlarıyla bir içerik paketi paylaştığında, normalde sadece öngörüleri paylaşmak isterler, iş arkadaşlarına doğrudan veriye erişim vermek istemezler. Ancak bu, veri kümesini araştıramayacağınız anlamına gelmez.  
   
   ![](media/sample-tutorial-connect-to-the-samples/power-bi-chart-icon2.png)
   
   * Veri kümesini keşfetmenin bir yolu, sıfırdan kendi görselleştirmelerinizi ve raporlarınızı oluşturmaktır.  Grafik simgesini ![](media/sample-tutorial-connect-to-the-samples/power-bi-chart-icon4.png) seçerek veri kümesini rapor düzenleme modunda açın.
     
       ![](media/sample-tutorial-connect-to-the-samples/power-bi-report-editing.png)
   * Veri kümesini keşfetmenin bir başka yolu [Hızlı Öngörüler](service-insights.md) çalıştırmaktır. Üç nokta (...) simgesini ve ardından **Öngörü al**'ı seçin. Öngörüler hazır olduğunda **Öngörüleri görüntüle** seçeneğini belirleyin.
     
       ![](media/sample-tutorial-connect-to-the-samples/power-bi-insights.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI temel kavramları](service-basic-concepts.md)

[Power BI hizmeti için örnekler](sample-datasets.md)

[Power BI için veri kaynakları](service-get-data.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

