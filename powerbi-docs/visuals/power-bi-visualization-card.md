---
title: Kart görselleştirmeleri (diğer adıyla büyük sayı kutucukları)
description: Power BI'da Kart görselleştirmesi oluşturma
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 03/26/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 18c9fe3d50245ff1d0745c0a3ae1e830b3f9be45
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46548339"
---
# <a name="card-visualizations"></a>Kart görselleştirmeleri
Bazen Power BI panonuzda veya raporunuzda izlemek istediğiniz en önemli şey (örneğin, toplam satış, yıldan yıla pazar payı veya toplam fırsat) tek bir sayı olabilir. Bu görselleştirme türüne *Kart* adı verilir. Diğer tüm yerel Power BI görselleştirmelerinde olduğu gibi Kartlar da rapor düzenleyicisi veya Soru-Cevap kullanılarak oluşturulabilir.

![kart görselleştirmesi](./media/power-bi-visualization-card/pbi_opptuntiescard.png)

## <a name="create-a-card-using-the-report-editor"></a>Rapor düzenleyicisini kullanarak kart oluşturma
Bu yönergelerde Perakende Analizi Örneği kullanılmaktadır. Yönergeleri takip etmek için Power BI hizmeti (app.powerbi.com) veya Power BI Desktop [örneğini indirin](../sample-datasets.md).   

1. [Boş rapor sayfasıyla](../power-bi-report-add-page.md) başlayın ve **Store** \> **Open store count** alanını seçin. Power BI hizmetini kullanıyorsanız raporu [Düzenleme Görünümü](../service-interact-with-a-report-in-editing-view.md)'nde açmanız gerekir.

    Power BI, tek sayı içeren bir sütun grafiği oluşturur.

   ![](media/power-bi-visualization-card/pbi_rptnumbertilechart.png)
2. Görsel Öğeler bölmesinde Kart simgesini seçin.

   ![](media/power-bi-visualization-card/pbi_changechartcard.png)
6. Kartın üzerine gelin ve görselleştirmeyi panoya eklemek için raptiye simgesini ![](media/power-bi-visualization-card/pbi_pintile.png) seçin.

   ![](media/power-bi-visualization-card/power-bi-pin-icon.png)
7. Kutucuğu, mevcut bir panoya veya yeni bir panoya sabitleyin.

   * Var olan pano: Açılan listeden panonun adını seçin.
   * Yeni pano: Yeni panonun adını yazın.
8. **Sabitle**'yi seçin.

   Sağ üst köşeye yakın bir noktada çıkan Başarılı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.

   ![](media/power-bi-visualization-card/power-bi-pin-success-message.png)
9. **Panoya git**'i seçin. Burada, sabitlenmiş görselleştirmeyi [düzenleyebilir ve taşıyabilirsiniz](../service-dashboard-edit-tile.md).


## <a name="create-a-card-from-the-qa-question-box"></a>Soru-Cevap soru kutusundan kart oluşturma
Soru-Cevap soru kutusu, Kart oluşturmanın en kolay yoludur. Soru-Cevap soru kutusuna Power BI hizmetinde (app.powerbi.com) bir panodan veya rapordan erişebilirsiniz. Aşağıdaki adımlar Power BI hizmeti panosundan Kart oluşturmayı anlatmaktadır. Power BI Desktop'taki Soru-Cevap özelliğini kullanarak kart oluşturmak isterseniz Desktop raporları için Soru-Cevap önizlemesi [yönergelerini izleyin](https://powerbi.microsoft.com/en-us/blog/power-bi-desktop-december-feature-summary/#QandA).

1. Bir [pano](../consumer/end-user-dashboards.md) oluşturun ve [veri alın](../service-get-data.md). Bu örnekte [Fırsat Analizi Örneği](../sample-opportunity-analysis.md) kullanılmaktadır.

1. Panonuzun en üstündeki soru kutusuna verilerinizle ilgili olarak öğrenmek istediklerinizi yazmaya başlayın. 

   ![](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

>**İPUCU**: Power BI hizmeti raporunun [Düzenleme görünümü](../consumer/end-user-reading-view.md)'nde üstteki menü çubuğundan **Bir soru sorun**'u seçin. Power BI Desktop raporunda boş alan bulun ve çift tıklayarak soru kutusu açın.

3. Örneğin soru kutusuna "number of opportunities" yazın.

   ![](media/power-bi-visualization-card/power-bi-q-and-a.png)

   Soru kutusu öneri ve ifade önerilerinde bulunduktan sonra toplam sayıyı görüntüler.  
4. Kartı panoya eklemek için sağ üst köşedeki raptiye simgesini ![](media/power-bi-visualization-card/pbi_pintile.png) seçin.

   ![](media/power-bi-visualization-card/power-bi-pin.png)
5. Kartı mevcut bir panoya veya yeni bir panoya kutucuk olarak sabitleyin.

   * Var olan pano: Açılan listeden panonun adını seçin. Seçimleriniz, geçerli çalışma alanındaki panolarla sınırlı olacaktır.
   * Yeni pano: Yeni panonun adını yazarak geçerli çalışma alanınıza eklenmesini sağlayabilirsiniz.
6. **Sabitle**'yi seçin.

   Sağ üst köşeye yakın bir noktada çıkan Başarılı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.  

   ![](media/power-bi-visualization-card/power-bi-success.png)
7. Yeni kutucuğu görmek için **Panoya git**'i seçin. Buradan panonuzda [kutucukla ilgili yeniden adlandırma, yeniden boyutlandırma, köprü ekleme, yeniden konumlandırma ve diğer işlemleri](../service-dashboard-edit-tile.md) gerçekleştirebilirsiniz.

   ![](media/power-bi-visualization-card/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
- Soru kutusu görmüyorsanız sistem veya kiracı yöneticinizle iletişime geçin.    
- Desktop uygulamasını kullanıyorsanız ve rapordaki boş alana çift tıkladığınızda Soru-Cevap açılmıyorsa bu özelliği etkinleştirmeniz gerekebilir.  **Dosya > Seçenekler ve Ayarlar > Seçenekler > Önizleme özellikleri > Soru-Cevap** yolunu izleyip Desktop uygulamasını yeniden başlatın.

## <a name="format-a-card"></a>Kart biçimlendirme
Etiketler, metin, renk ve daha fazlasını değiştirmek için çok sayıda seçeneğiniz vardır. Öğrenmenin en iyi yolu, bir kart oluşturduktan sonra Biçimlendirme bölmesini inceleyin. Biçimlendirme seçeneklerinden birkaçı aşağıda verilmiştir. 

1. Biçimlendirme bölmesini açmak için ilk olarak boya fırçası simgesini seçin. 

    ![](media/power-bi-visualization-card/power-bi-format-card.png)
2. **Veri etiketi**’ni genişletin ve renk, boyut ve yazı tipi ailesini değiştirin. Binlerce deponuz olsaydı, binlerce depo sayısını göstermek ve ondalık basamakları denetlemek için **Görüntüleme birimleri**’ni kullanabilirdiniz. Örneğin, 125.832,00 yerine 125,8 bin.

3.  **Kategori etiketi**’ni genişletin ve renk ile boyutu değiştirin.

    ![](media/power-bi-visualization-card/power-bi-card-format.png)

4. **Arka plan**’ı genişletin ve kaydırıcıyı Açık konuma taşıyın.  Artık arka plan rengini ve saydamlığı değiştirebilirsiniz.

    ![](media/power-bi-visualization-card/power-bi-format-color.png)

5. Kartınız tam olarak istediğiniz şekilde olana kadar biçimlendirme seçeneklerini incelemeye devam edin. 

    ![](media/power-bi-visualization-card/power-bi-formatted.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki pano kutucukları](../consumer/end-user-tiles.md)

[Power BI'daki panolar](../consumer/end-user-dashboards.md)

[Power BI - Temel Kavramlar](../consumer/end-user-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
