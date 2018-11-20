---
title: Power BI örneklerini kullanma
description: Power BI örneklerini kullanma
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/23/2018
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 10ba57b203c100dffafa6563e85fd06b7af2eecb
ms.sourcegitcommit: 1e4fee6d1f4b7803ea285eb879c8d5a4f7ea8b85
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51718034"
---
# <a name="the-power-bi-samples"></a>Power BI örnekleri

[Power BI için örnek veri kümeleri](sample-datasets.md) makalesiyle başlamanızı öneririz. Söz konusu makalede örnekler hakkında her şeyi, nasıl alındıklarını, nereye kaydedildiklerini ve örneklerin sunduğu içeriklerden bazılarını öğrenebilirsiniz. Temel konuları kavradıktan sonra bu eğitime geri dönebilirsiniz.   

### <a name="prerequisites"></a>Önkoşullar
Örnekler, Power BI hizmetinde ve Power BI Desktop'ta kullanılabilir. Örneği takip etmek için Perakende analizi örneğini kullanacağız.

Bu eğitimde kullanılan *Perakende Analizi* örnek içerik paketi, bir pano, rapor ve veri kümesinden oluşur.
Bu içerik paketine ve senaryosuna aşina olmanız için, başlamadan önce [Perakende Analizi örneğine ilişkin tura katılabilirsiniz](sample-retail-analysis.md).

## <a name="about-this-tutorial"></a>Bu eğitim hakkında
Bu öğreticide aşağıdaki işlemler hakkında bilgi edinirsiniz: 
- Örnek içerik paketini içeri aktarma, Power BI hizmetine ekleme ve içeriği açma. *İçerik paketleri*, veri kümesinin bir pano ve raporla birlikte sunulduğu bir örnek türüdür. 
-  Power BI Desktop'ta bir örnek .pbix dosyası açma.


## <a name="samples-and-power-bi-service"></a>Örnekler ve Power BI hizmeti

1. Power BI hizmetine (app.powerbi.com) gidin ve oturum açın.
2. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin. **Veri Al**'ı görmüyorsanız ![hamburger simgesini](media/sample-tutorial-connect-to-the-samples/expand-nav.png) seçerek gezinti bölmesini genişletin.
   
   ![veri al simgesi](media/sample-tutorial-connect-to-the-samples/pbi_getdata.png)
5. **Örnekler**'i seçin.  
   
   ![Örnekler düğmesi](media/sample-tutorial-connect-to-the-samples/pbi_samplesdownload.png)
6. *Perakende Analizi Örneği*'ni ve ardından **Bağlan**'ı seçin.   
   
   ![sarı bağlan düğmesi](media/sample-tutorial-connect-to-the-samples/pbi_retailanalysissampleconnect.png)

## <a name="what-exactly-was-imported"></a>Tam olarak neler içeri aktarılır?
Örnek içerik paketleri söz konusuysa **Bağlan**'ı seçtiğinizde Power BI, ilgili içerik paketinin bir kopyasını alıp sizin için bulutta depolar. İçerik paketini oluşturan kişi bir veri kümesi, rapor ve de pano eklemiş olduğundan, **Bağlan**a tıkladığınızda bunları edinirsiniz. 

1. Power BI yeni bir Pano oluşturur ve bunu **Panolar** sekmesinde listeler. Sarı yıldız işareti, yeni olduğunu bilmenizi sağlar.
   
   ![başarılı iletisi](media/sample-tutorial-connect-to-the-samples/power-bi-new-dashboard.png)
2. **Raporlar** sekmesini açın.  Burada *Retail Analysis Sample* adlı yeni bir rapor göreceksiniz.
   
   ![Perakende Analizi Örneğinin çevresinde kırmızı kutu ve sarı yıldız](media/sample-tutorial-connect-to-the-samples/power-bi-new-report.png)
   
   Ardından, **Veri Kümeleri** sekmesine bakın.  Yeni bir veri kümesi de vardır.
   
   ![Perakende Analizi Örneğinin çevresinde kırmızı kutu](media/sample-tutorial-connect-to-the-samples/power-bi-new-dataset.png)

## <a name="explore-your-new-content"></a>Yeni içeriğinizi keşfedin
Şimdi pano, veri kümesini ve raporu kendiniz keşfedin. Panolar, raporlar ve veri kümelerinde gezinmek için izleyebileceğiniz birçok farklı yol vardır ve bu yollardan yalnızca biri aşağıda ele alınmıştır.  

> [!TIP]
> Önce ayrıntılı bir açıklama ister misiniz?  Bu örneğe ilişkin adım adım kılavuz için [Perakende Analizi örneğine ilişkin turu](sample-retail-analysis.md) deneyin.
> 
> 

1. **Panolar** sekmenize geri gidin, *Retail Analysis Sample* panonuzu seçerek açın.    
   
   ![Pano sekmesi seçili](media/sample-tutorial-connect-to-the-samples/power-bi-dashboards.png)
2. Pano açılır.  Çeşitli görselleştirme kutucukları bulunur.
   
   ![görselin vurgulandığı pano](media/sample-tutorial-connect-to-the-samples/power-bi-dashboards2new.png)
3. Bağlantılı raporu açmak için bir kutucuk seçin.  Bu örnekte, alan grafiğini seçeceğiz. (Önceki görüntüde pembeyle gösterilmiştir.) Raporun, alan grafiğini içeren sayfası açılır.
   
    ![eşleşen görselin vurgulandığı rapor sayfası](media/sample-tutorial-connect-to-the-samples/power-bi-report.png)
   
   > [!NOTE]
   > Kutucuk eğer [Power BI Soru-Cevap](consumer/end-user-q-and-a.md) kullanılarak oluşturulsaydı bunun yerine Soru-Cevap sayfası açılırdı. Kutucuk [Excel'den sabitlenmişse](service-dashboard-pin-tile-from-excel.md), Power BI içinde Excel Online açılır.
   > 
   > 
1. **Veri Kümeleri** sekmenizde, veri kümenizi araştırmanıza yönelik çeşitli seçenekleriniz vardır.  Açıp tüm satırları ve sütunları (Power BI Desktop veya Excel'de görebildiğiniz gibi) görmeniz mümkün olmayacaktır.  Birisi iş arkadaşlarıyla bir içerik paketi paylaştığında, normalde sadece öngörüleri paylaşmak isterler, iş arkadaşlarına doğrudan veriye erişim vermek istemezler. Ancak bu, veri kümesini araştıramayacağınız anlamına gelmez.  
   
   ![Veri Kümeleri sekmesi](media/sample-tutorial-connect-to-the-samples/power-bi-chart-icon2.png)
   
   * Veri kümesini keşfetmenin bir yolu, sıfırdan kendi görselleştirmelerinizi ve raporlarınızı oluşturmaktır.  Grafik simgesini ![rapor simgesi](media/sample-tutorial-connect-to-the-samples/power-bi-chart-icon4.png) seçerek veri kümesini rapor düzenleme modunda açın.
     
       ![yepyeni bir rapor](media/sample-tutorial-connect-to-the-samples/power-bi-report-editing.png)
   * Veri kümesini keşfetmenin bir başka yolu [Hızlı Öngörüler](consumer/end-user-insights.md) çalıştırmaktır. Üç nokta (...) simgesini ve ardından **Öngörü al**'ı seçin. Öngörüler hazır olduğunda **Öngörüleri görüntüle** seçeneğini belirleyin.
     
       ![İçgörüler raporu](media/sample-tutorial-connect-to-the-samples/power-bi-insights.png)

## <a name="samples-and-power-bi-desktop"></a>Örnekler ve Power BI Desktop 
Örnek PBIX dosyasını ilk kez açtığınızda, görsel öğeler içeren herhangi bir sayıdaki rapor sayfasını keşfedebileceğiniz, oluşturabileceğiniz ve değiştirebileceğiniz Rapor görünümünde gösterilir. Rapor görünümü, Power BI hizmetindeki Düzenleme görünümü ile neredeyse aynı tasarım deneyimini sunar. Görselleştirmeleri taşıma, kopyalayıp yapıştırma ve birleştirme gibi işlemler gerçekleştirebilirsiniz.

Aralarındaki fark şudur: Power BI Desktop'ı kullanırken sorgularla çalışabilir ve verilerinizin raporlarınızdaki en etkileyici öngörüleri desteklediğinden emin olmak için verilerinizi modelleyebilirsiniz. Ardından, Power BI Desktop dosyanızı dilediğiniz yere (ister yerel sürücünüze ister buluta) kaydedebilirsiniz.

1. Power BI Desktop’ta [Perakende Analizi örneği .pbix dosyasını](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) açın. 

    ![Örnek Power BI rapor görünümünde açılır](media/sample-tutorial-connect-to-the-samples/power-bi-samples-desktop.png)

1. Dosya, Rapor görünümünde açılır. Rapor düzenleyicisinin alt kısmındaki 4 sekmeyi fark ettiniz mi? Bunlar, raporda 4 sayfa olduğu anlamına gelir ve o anda "Yeni Depolar" sayfası seçilidir. 

    ![alttaki sekmelerin yakından görünüşü ve Yeni Mağazalar vurgulanmış](media/sample-tutorial-connect-to-the-samples/power-bi-sample-tabs.png)geçin.

3. Rapor düzenleyicisine derinlemesine bakış için bkz. [Rapor düzenleyicisi turuna katılın](service-the-report-editor-take-a-tour.md)

## <a name="what-exactly-was-imported"></a>Tam olarak neler içeri aktarılır?
Desktop’ta örnek PBIX dosyasını ilk kez açtığınızda, Power BI aslında bu verilerin bir kopyasını getirir ve sizin için bulutta depolar. Desktop’tan rapora ***ve temel alınan veri kümesine*** erişebilirsiniz. Veriler yüklendiğinde Power BI Desktop, sizin yerinize bu ilişkileri bulup oluşturmayı dener.  

1. Tablo simgesini ![tablo simgesi](media/sample-tutorial-connect-to-the-samples/power-bi-data-icon.png) seçerek [Veri görünümüne](desktop-data-view.md) geçin.
 
    ![Desktop veri görünümü](media/sample-tutorial-connect-to-the-samples/power-bi-desktop-sample-data.png)

    Veri Görünümü, Power BI Desktop modelinizdeki verileri incelemenize, araştırmanıza ve anlamanıza yardımcı olur. Tabloları, sütunları ve verileri Sorgu Düzenleyicisi'nde görüntülemekten farklıdır. Veri Görünümü ile verilerinizin modele yüklendikten sonraki halini incelersiniz.

    Bazen verilerinizi modellerken rapor tuvalinde görsel oluşturmadan bir tablo veya sütundaki verileri satır düzeyinde görmek istersiniz. Bu durum özellikle ölçü ve hesaplanmış sütun oluşturduğunuzda veya bir veri türü ya da veri kategorisi tanımlamanız gerektiğinde ortaya çıkar.

1. Simgeyi ![3 bağlantılı kutuya benzeyen simge](media/sample-tutorial-connect-to-the-samples/power-bi-desktop-relationship-icon.png) seçerek [İlişkiler görünümüne](desktop-relationship-view.md) geçin.
 
    ![Power BI Desktop'taki ilişki görünümü](media/sample-tutorial-connect-to-the-samples/power-bi-relationships.png)

    İlişki görünümü, modelinizdeki tüm tabloları, sütunları ve ilişkileri gösterir. Buradan ilişkileri görüntüleyebilir, değiştirebilir ve oluşturabilirsiniz.

## <a name="explore-your-new-content"></a>Yeni içeriğinizi keşfedin
Şimdi veri kümesini, ilişkileri ve raporu kendiniz keşfedin. Başlamanıza yardımcı olması için [Desktop Başlarken Kılavuzu](desktop-getting-started.md)’nu ziyaret edin.    


## <a name="next-steps"></a>Sonraki adımlar
[Power BI temel kavramları](consumer/end-user-basic-concepts.md)

[Power BI hizmeti için örnekler](sample-datasets.md)

[Power BI için veri kaynakları](service-get-data.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

