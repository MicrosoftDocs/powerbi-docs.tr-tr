---
title: Power BI raporuna yeni bir Power App ekleme
description: Aynı veri kaynağını kullanan ve diğer rapor öğeleri gibi filtrelenebilen bir uygulamayı ekleme
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 01/16/2020
ms.author: mblythe
LocalizationGroup: Visualizations
ms.openlocfilehash: bbca812644b82f8a0b848dc16e450f880ccb596c
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76539912"
---
# <a name="tutorial-embed-a-power-apps-visual-in-a-power-bi-report"></a>Öğretici: Power BI raporuna yeni bir Power Apps görseli ekleme

Bu öğreticide, örnek Power BI raporuna eklenecek yeni bir uygulama oluşturmak için Power Apps görselini kullanacaksınız. Bu uygulama, söz konusu rapordaki diğer görsellerle etkileşimde bulunur.

Power Apps aboneliğiniz yoksa başlamadan önce [ücretsiz bir hesap oluşturun](https://web.powerapps.com/signup?redirect=marketing&email=).

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:
> [!div class="checklist"]
> * Power BI raporuna Power Apps görseli ekleme
> * Power BI raporundan verilerin kullanıldığı yeni bir uygulama oluşturmak için Power Apps’te çalışma
> * Raporda Power Apps görselini görüntüleme ve bu görselle etkileşim kurma

## <a name="prerequisites"></a>Önkoşullar

* [Google Chrome](https://www.google.com/chrome/browser/) veya [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) tarayıcı
* [Fırsat Analizi Örneği](https://docs.microsoft.com/power-bi/sample-opportunity-analysis#get-the-content-pack-for-this-sample)’nin yüklü olduğu bir [Power BI aboneliği](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi)
* [Power Apps’te uygulama oluşturma](https://docs.microsoft.com/powerapps/maker/canvas-apps/data-platform-create-app-scratch) ve [Power BI raporlarını düzenleme](https://docs.microsoft.com/power-bi/service-the-report-editor-take-a-tour) hakkında bilgi sahibi olma



## <a name="create-a-new-app"></a>Yeni uygulama oluşturma
Raporunuza Power Apps görseli eklediğinizde Power Apps ile Power BI arasında dinamik bir veri bağlantısıyla Power Apps Studio başlatılır.

1. Fırsat Analizi örnek raporunu açın ve *Upcoming Opportunities* (Yaklaşan Fırsatlar) sayfasını seçin. 


2. Yeni görsele yer açmak için rapor kutucuklarının bazılarını taşıyın ve yeniden boyutlandırın.

    ![Rapor kutucuklarını taşıma ve yeniden boyutlandırma](media/power-bi-visualization-powerapp/power-bi-report-page.jpg)

2. Görselleştirmeler bölmesinden Power Apps simgesini seçin ve görseli açtığınız alana sığacak şekilde yeniden boyutlandırın.

    ![Power Apps simgesinin seçili olduğu Görselleştirmeler bölmesi](media/power-bi-visualization-powerapp/power-bi-powerapps-icon.jpg)

3. **Alanlar** bölmesinde **Ad**, **Ürün Kodu** ve **Satış Aşaması**’nı seçin. 

    ![alanları seçme](media/power-bi-visualization-powerapp/power-bi-fields.jpg)

4. Power Apps görselinde uygulamayı oluşturmak istediğiniz Power Apps ortamını seçin ve sonra da **Yeni oluştur**’u seçin.

    ![Yeni uygulama oluşturma](media/power-bi-visualization-powerapp/power-bi-create-new-powerapp.png)

    Power Apps Studio’da, Power BI’da seçtiğiniz alanlardan birini gösteren bir *galeri* ile birlikte temel bir uygulamanın oluşturulduğunu görürsünüz.

    ![Power Apps açılır](media/power-bi-visualization-powerapp/power-bi-power-app.png)

5.  Galeriyi ekranın yalnızca yarısını kaplayacak şekilde yeniden boyutlandırın. 

6. Sol bölmede **Scren1**’i seçin, ardından ekranın **Fill** özelliğini "LightBlue" olarak (raporda daha iyi gösterilmesi için) ayarlayın.

    ![renk paleti](media/power-bi-visualization-powerapp/power-bi-powerapps-fill.png)

6. Etiket denetimi için biraz yer ayırın. 

    ![galeri boyutlarını değiştirme](media/power-bi-visualization-powerapp/power-bi-powerapps-gallery.png)


8. **Galeri**’nin altına bir metin etiketi denetimi ekleyin.

   ![etiket denetimi](media/power-bi-visualization-powerapp/power-bi-label.png)

7. Etiketi görselinizin alt kısmına sürükleyin. **Text** özelliğini `"Opportunity Count: " & CountRows(Gallery1.AllItems)` olarak ayarlayın. Bu durumda veri kümesindeki toplam fırsat sayısı gösterilir.

    ![Galerisi yeniden boyutlandırılan uygulama](media/power-bi-visualization-powerapp/power-bi-power-app-label.png)

    ![Etiketi güncelleştirilen uygulama](media/power-bi-visualization-powerapp/power-bi-label-live.png)

7. Uygulamayı "Opportunities app" adıyla kaydedin. 

    ![uygulamayı kaydedin](media/power-bi-visualization-powerapp/power-bi-save-powerapp.png)


## <a name="view-the-app-in-the-report"></a>Uygulamayı raporda görüntüleme
Uygulama artık Power BI raporunda kullanılabilir ve aynı veri kaynağını paylaştığından diğer görsellerle etkileşimde bulunur.

![Power BI raporunda uygulama](media/power-bi-visualization-powerapp/power-bi-powerapps-visual.png)

Power BI raporunda, dilimleyiciden uygulamadaki verilerle birlikte tam raporu filtreleyen **Jan** öğesini seçin.

![filtrelenmiş rapor](media/power-bi-visualization-powerapp/power-bi-last.png)

Uygulamadaki fırsat sayısının, raporun sol üst köşesindeki sayıyla eşleştiğine dikkat edin. Rapordaki diğer öğeleri ve uygulama güncelleştirmelerindeki verileri seçebilirsiniz.


## <a name="clean-up-resources"></a>Kaynakları temizleme
Fırsat Analizi Örneğini artık kullanmak istemiyorsanız pano, rapor ve veri kümesini silebilirsiniz.


## <a name="next-steps"></a>Sonraki adımlar
[Soru-Cevap görseli](power-bi-visualization-types-for-reports-and-q-and-a.md)