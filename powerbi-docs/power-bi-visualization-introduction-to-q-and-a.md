---
title: "Power BI Soru-Cevap özelliğini kullanmaya başlama (Eğitim)"
description: "Eğitim: Perakende Analizi örneğini kullanarak Power BI hizmetindeki Soru-Cevap özelliğini kullanmaya başlama"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 2038fb5bd4a21235c3026c8506ae30b8c3e287e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="get-started-with-power-bi-qa-tutorial"></a>Power BI Soru-Cevap özelliğini kullanmaya başlama (Eğitim)
## <a name="tutorial-use-power-bi-qa-with-the-retail-analysis-sample"></a>Eğitim: Perakende Analizi örneğiyle Power BI Soru-Cevap özelliğini kullanmaya başlama
Bazen verilerinize ilişkin yanıtlar edinmenin en hızlı yolu doğal dil kullanarak bir soru sormaktır.  Bu eğitimde aynı görselleştirmeyi oluşturmanın 2 farklı yoluna göz atacağız: raporda oluşturma ve Soru-Cevap özelliğini kullanarak soru sorma.  

## <a name="method-1-using-the-report-editor"></a>1. Yöntem: rapor düzenleyicisini kullanma
1. Power BI çalışma alanınızda **Veri Al** \> **Örnekler** \> **Perakende Analizi Örneği** > **Bağlan**'ı seçin.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)
2. Panoda "This Year's Sales, Last Year's Sales" adlı, hem geçen yıla ait hem de bu yıla ait satış verilerinin yer aldığı bir alan grafiği kutucuğu bulunur.  Bu kutucuğu seçin. 
   
   * Bu kutucuk Soru-Cevap özelliğiyle oluşturulmuşsa kutucuğu seçtiğinizde Soru-Cevap açılır. 
   * Ancak bu kutucuk bir raporda oluşturulduğundan raporda, bu görselleştirmeyi içeren sayfa açılır.
3. **Raporu düzenle**'yi seçerek raporu Düzenleme Görünümü'nde açın.  Raporun sahibi siz değilseniz Düzenleme görünümü'nde açma seçeneği sunulmaz.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Alan grafiğini seçin ve **Alanlar** bölmesinde ayarları gözden geçirin.  Raporu oluşturan kişi bu grafiği, ilgili 3 değeri seçip (**Time > FiscalMonth**, **Sales > This Year Sales**, **Sales > Last Year Sales > Değer**) bunları **Eksen** ve **Değerler** kutularında düzenleyerek oluşturmuştur.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="method-2-using-qa"></a>2. Yöntem: Soru-Cevap özelliğini kullanma
Soru-Cevap özelliğini kullanarak aynı çizgi grafiği nasıl oluşturabiliriz?

![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. Perakende Analizi Örneği panosuna geri dönün.
2. Doğal dil kullanarak soru kutusuna aşağıdakine benzer bir ifade yazın:
   
   **what were this year sales and last year sales by month as area chart** (bu yıla ait satış verileri ile geçen yıla ait satış verilerini alan grafiğinde aylara göre görüntüle)
   
   Siz sorunuzu yazarken Soru-Cevap özelliği, yanıtınızı görüntülemek üzere en iyi görselleştirmeyi seçer. Siz soruyu değiştirdikçe görselleştirmeler de dinamik olarak değiştirilir. Soru-Cevap özelliği öneriler, otomatik tamamlama ve yazım düzeltmeleri ile sorunuzu biçimlendirmenize de yardımcı olur.
   
   Sorunuzu yazmayı bitirdikten sonra sonuç olarak, raporda gördüğümüz grafiğin aynısını elde edersiniz.  Gördüğünüz gibi bu çok daha hızlı oldu!
   
   ![](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. Raporlarla çalışırken olduğu gibi Soru-Cevap özelliğini kullanırken de Görsel Öğeler, Filtreler ve Alanlar bölmelerine erişebilirsiniz.  Görselinizi daha fazla araştırmak ve değiştirmek için bu bölmeleri açın.
4. Grafiği panonuza sabitlemek için raptiye simgesini ![](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png) seçin.

## <a name="next-steps"></a>Sonraki adımlar
[Soru-Cevap özelliğini kullanarak ne tür sorular sorabilirim?](service-q-and-a.md)

[Power BI'daki Soru-Cevap](service-q-and-a.md)

[Power BI'daki Soru-Cevap özelliğiyle verilerinizin düzgün çalışmasını sağlama](service-prepare-data-for-q-and-a.md)

[Bir çalışma kitabını Soru-Cevap için hazırlama](service-prepare-data-for-q-and-a.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

