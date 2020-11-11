---
title: Power BI görselleştirmesini oluşturmak için kullanılan verileri gösterme
description: Bu belgede Power BI'daki bir görseli oluşturmak için kullanılan verileri gösterme ve bu verileri .csv dosyası biçiminde dışarı aktarma adımları açıklanmaktadır.
author: msftrien
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 12/4/2019
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: c3e996da62b71c008f4f7a5929cc8b91d38cc26e
ms.sourcegitcommit: 5ccab484cf3532ae3a16acd5fc954b7947bd543a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2020
ms.locfileid: "93412798"
---
# <a name="display-a-visualizations-underlying-data"></a>Görselleştirmenin temel alınan verilerini görüntüleme

[!INCLUDE[consumer-appliesto-yyyn](../includes/consumer-appliesto-nyyn.md)]    

## <a name="show-data"></a>Verileri göster
Power BI görselleştirmeleri, veri kümelerinizdeki veriler kullanılarak oluşturulur. Verilerin kaynağını merak ediyorsanız Power BI, görseli oluşturmak için kullanılan verileri *görüntülemenizi* sağlar. **Verileri Göster** 'i seçtiğinizde, Power BI ilgili verileri görselleştirmenin altında (veya yanında) görüntüler.

İsterseniz görselleştirmeyi oluşturmak için kullanılan verileri .xlsx veya .csv biçiminde dışarı aktarıp Excel'de görüntüleyebilirsiniz. Daha fazla bilgi için bkz. [Power BI görselleştirmelerindeki verileri dışarı aktarma](power-bi-visualization-export-data.md).

> [!NOTE]
> *Verileri Göster* ve *Verileri Dışarı Aktar* seçenekleri hem Power BI hizmetinde hem de Power BI Desktop uygulamasında kullanılabilir. Ancak Power BI Desktop uygulaması ek bir ayrıntı katmanı daha sunar. [*Kayıtları Göster* seçeneği veri kümesindeki satırları görüntüler](../create-reports/desktop-see-data-see-records.md).
> 
> 

## <a name="using-show-data"></a>*Verileri Göster* seçeneğini kullanma 
1. Power BI Desktop'ta etkin duruma getirmek için bir görselleştirmeyi seçin.

2. **Diğer eylemler** (...) ve **Verileri göster** öğelerini seçin. 
    ![Verileri Göster için görüntüleme seçenekleri](media/service-reports-show-data/power-bi-more-action.png)


3. Veriler varsayılan olarak görselin altında gösterilir.
   
   ![görsel ve veri dikey görüntüsü](media/service-reports-show-data/power-bi-show-data-below.png)

4. Yönü değiştirmek için, görselleştirmenin sağ üst köşesinde dikey düzeni ![dikey yerleşime geçmek için kullanılan simgenin küçük ekran görüntüsü](media/service-reports-show-data/power-bi-vertical-icon-new.png) seçin.
   
   ![görsel ve veri yatay görüntüsü](media/service-reports-show-data/power-bi-show-data-side.png)
5. Verileri .csv biçiminde dışarı aktarmak için üç noktayı ve ardından **Verileri dışarı aktar** 'ı seçin.
   
    ![Verileri dışarı aktar’ı seçme](media/service-reports-show-data/power-bi-export-data-new.png)
   
    Verileri Excel'e aktarma hakkında daha fazla bilgi için bkz. [Power BI görselleştirmelerindeki verileri dışarı aktarma](power-bi-visualization-export-data.md).
6. Verileri gizlemek için **Araştır** > **verileri göster** seçimini kaldırın.

## <a name="using-show-records"></a>Kayıtları göster seçeneğini kullanma
Ayrıca bir görselleştirmedeki tek bir veri kaydına odaklanıp bu öğenin temel aldığı verilerin de detayına gidebilirsiniz. 

1. **Kayıtları görüntüle** seçeneğini kullanmak için, bir görselleştirmeyi seçerek etkin duruma getirin. 

2. Masaüstü şeridinde **Görsel araçlar** > **Veri/Detay** > **Kayıtları görüntüle** sekmesini seçin. 

    ![Kayıtları Görüntüle özelliğinin seçili olduğunu gösteren ekran görüntüsü.](media/service-reports-show-data/power-bi-see-record.png)

3. Görselleştirme üzerinde bir veri noktası veya satır seçin. Bu örnekte soldan dördüncü sütunu seçtik. Power BI, bu veri noktasına ait olan veri kümesi kaydını gösterir.

    ![Veri kümesindeki tek bir kaydın ekran görüntüsü.](media/service-reports-show-data/power-bi-row.png)

4. Masaüstü rapor tuvaline geri dönmek için **Rapora geri dön** 'ü seçin. 

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

- Şeritteki **Kayıtları görüntüle** düğmesinin devre dışı ve gri renkte olması, seçili görselleştirmenin Kayıtları Görüntüle özelliğini desteklemediği anlamına gelir.
- Kayıtları Görüntüle görünümünde verileri değiştiremez ve rapora geri kaydedemezsiniz.
- Görselinizdeki çok boyutlu bir modelde hesaplanmış ölçü kullanılıyorsa Kayıtları Görüntüle özelliğinden yararlanamazsınız.
- Canlı bir çok boyutlu (MD) modele bağlıyken Kayıtları Görüntüle özelliğini kullanamazsınız.  

## <a name="next-steps"></a>Sonraki adımlar
[Power BI görselleştirmelerindeki verileri dışarı aktarma](power-bi-visualization-export-data.md)    

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)


