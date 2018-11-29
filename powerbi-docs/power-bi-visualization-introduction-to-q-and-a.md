---
title: Power BI Soru-Cevap’ı kullanmaya başlama
description: Perakende Analizi örneğini kullanarak Power BI hizmetindeki Soru-Cevap özelliğini kullanmaya başlama
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: e76d57f43fc76f5a9c51501daac48b081d9747b6
ms.sourcegitcommit: 35d763dfc75c229204d36fd8b35c1e860786b707
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2018
ms.locfileid: "52331829"
---
# <a name="get-started-with-power-bi-qa"></a>Power BI Soru-Cevap’ı kullanmaya başlama

Bazen verilerinize ilişkin cevaplar edinmenin en hızlı yolu doğal dil kullanarak bir soru sormaktır.  Bu hızlı başlangıçta aynı görselleştirmeyi oluşturmanın iki farklı yoluna göz atacağız: raporda oluşturma ve Soru-Cevap özelliğini kullanarak soru sorma yoluyla oluşturma. Biz Power BI hizmetini kullanacağız ancak Power BI Desktop kullanıldığında da neredeyse aynı işlem gerçekleştirilir.

Birlikte ilerleyebilmeniz için, düzenleyebileceğiniz bir raporu kullanmanız gerekir. Bu nedenle, Power BI'da bulunan örneklerden birini kullanacağız.

## <a name="create-a-visual-in-the-report-editor"></a>Rapor düzenleyicisinde görsel oluşturma

1. Power BI çalışma alanınızda **Veri Al** \> **Örnekler** \> **Perakende Analizi Örneği** > **Bağlan**'ı seçin.
   
2. Panoda "This Year's Sales, Last Year's Sales" adlı, hem geçen yıla ait hem de bu yıla ait satış verilerinin yer aldığı bir alan grafiği kutucuğu bulunur.  Bu kutucuğu seçin. Bu kutucuk Soru-Cevap özelliğiyle oluşturulmuşsa kutucuğu seçtiğinizde Soru-Cevap açılır. Ancak bu kutucuk bir raporda oluşturulduğundan raporda, bu görselleştirmeyi içeren sayfa açılır.

    ![Perakende Analizi örneği panosu](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)

1. **Raporu düzenle**'yi seçerek raporu Düzenleme Görünümü'nde açın.  Raporun sahibi siz değilseniz Düzenleme görünümünde açma seçeneği sağlanmaz.
   
    ![Raporu düzenle düğmesi](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Alan grafiğini seçin ve **Alanlar** bölmesinde ayarları gözden geçirin.  Raporu oluşturan kişi bu grafiği, ilgili üç değeri seçip (**Time > FiscalMonth**, **Sales > This Year Sales**, **Sales > Last Year Sales > Değer**) bunları **Eksen** ve **Değerler** kutularında düzenleyerek oluşturmuştur.
   
    ![Görselleştirmeler bölmesi](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="create-the-same-visual-with-qa"></a>Aynı görseli Soru-Cevap ile oluşturma

Soru-Cevap özelliğini kullanarak aynı çizgi grafiği nasıl oluşturabiliriz?

![Soru sorun kutusu](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. Perakende Analizi Örneği panosuna geri dönün.
2. Doğal dil kullanarak soru kutusuna aşağıdakine benzer bir soru yazın:
   
   **what were this year sales and last year sales by month as area chart** (bu yıla ait satış verileri ile geçen yıla ait satış verilerini alan grafiğinde aylara göre görüntüle)
   
   Siz sorunuzu yazarken Soru-Cevap özelliği, yanıtınızı görüntülemek üzere en iyi görselleştirmeyi seçer. Siz soruyu değiştirdikçe görselleştirmeler de dinamik olarak değiştirilir. Soru-Cevap özelliği öneriler, otomatik tamamlama ve yazım düzeltmeleri ile sorunuzu biçimlendirmenize de yardımcı olur.
   
   Sorunuzu yazmayı bitirdikten sonra sonuç olarak, raporda gördüğümüz grafiğin aynısını elde edersiniz.  Gördüğünüz gibi bu çok daha hızlı oldu!
   
   ![Soru örneği](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. Raporlarla çalışırken olduğu gibi Soru-Cevap özelliğini kullanırken de Görsel Öğeler, Filtreler ve Alanlar bölmelerine erişebilirsiniz.  Görselinizi daha fazla araştırmak ve değiştirmek için bu bölmeleri açın.
4. Grafiği panonuza sabitlemek için raptiye simgesini seçin ![Raptiye simgesi](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png)geçin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki Soru-Cevap](consumer/end-user-q-and-a.md)

[Power BI'daki Soru-Cevap özelliğiyle verilerinizin düzgün çalışmasını sağlama](service-prepare-data-for-q-and-a.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

