---
title: Power BI hizmetindeki raporlar
description: Tüketiciler için Power BI hizmetindeki raporlar
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 28af5cd89e918fad7fc7064479ac95c67ca3cee3
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83277468"
---
# <a name="reports-in-power-bi"></a>Power BI'daki raporlar

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Power BI raporları, bir veri kümesinden edinilen farklı bulguları ve öngörüleri temsil eden görseller yardımıyla bu veri kümesine ilişkin çok yönlü bir yaklaşım sunar.  Bir raporda tek bir görsel olabilir veya rapor, görsellerle dolu sayfalardan oluşabilir. İş rolünüze bağlı olarak, rapor *tasarlayan* kişi olabilirsiniz. Raporları *tüketen* veya kullanan kişi de olabilirsiniz. Bu makale *tüketiciler* içindir.

![Bir rapor sayfasının ekran görüntüsü.](./media/end-user-reports/power-bi-report.png)

A. Bu raporda altı sayfa (veya sekme) bulunuyor ve şu anda **Yaklaşım** sayfasını görüntülüyorsunuz.    
B. Bu sayfada beş farklı görsel ve bir sayfa başlığı bulunuyor.    
C. *Filtreler* bölmesi tüm rapor sayfalarına bir filtre uygulandığını gösteriyor. Filtreler bölmesini daraltmak için oku ( **>** ) seçin.    
D. Power BI başlığı, raporun adını ve son güncelleştirme tarihini görüntüler. Rapor sahibinin adını da gösteren bir menü açmak için oku seçin.    
E. Eylem çubuğu, bu raporda gerçekleştirebileceğiniz eylemleri içerir.  Örneğin, bir yorum ekleyebilir, bir yer işaretini görüntüleyebilir veya verileri rapordan dışarı aktarabilirsiniz.  Ek rapor işlevlerinin listesini göstermek için **Diğer seçenekler** (...) simgesini seçin.    

Power BI'ı kullanmaya yeni başladıysanız [Power BI hizmeti tüketicileri için temel kavramlar](end-user-basic-concepts.md) makalesini okuyarak iyi bir temel oluşturabilirsiniz. Raporlar mobil cihazlarda görüntülenebilir, paylaşılabilir ve raporlara not eklenebilir. Daha fazla bilgi için bkz. [Power BI mobil uygulamalarında raporları araştırma](mobile/mobile-reports-in-the-mobile-apps.md).

## <a name="advantages-of-reports"></a>Raporların avantajları

Power BI bir raporda tek bir veri kümesini temel alır. Rapor *tasarımcıları*, bir rapor içinde bir bilgiyi temsil eden görseller oluşturur. Görseller statik değildir.  Temel alınan veriler değiştikçe güncelleştirilir. İçgörüleri keşfetmek ve yanıt aramak için verilerin ayrıntılarına indikçe görseller ve filtrelerle etkileşimde bulunabilirsiniz. Bir pano gibi, rapor da yüksek oranda etkileşimli ve yüksek oranda özelleştirilebilir niteliktedir.

### <a name="safely-interact-with-content"></a>İçerikle güvenli etkileşim kurma

İçeriğinizi keşfedip filtreleme, dilimleme, abone olma ve dışarı aktarma gibi etkileşimlerde bulundukça, raporları bozamazsınız. Çalışmanız, temel alınan veri kümesini veya özgün paylaşılan içeriği etkilemez. Bu durum panolar, raporlar ve uygulamalar için geçerlidir.

> [!NOTE]
> Verilerinize zarar veremeyeceğinizi unutmayın. Power BI, bir şeyi bozma korkusu duymadan deneyip keşfetmeniz için harika bir yerdir.

### <a name="save-your-changes-or-revert-to-the-default-settings"></a>Değişikliklerinizi kaydedin veya varsayılan ayarlara geri dönün

Bu, değişikliklerinizi kaydedemeyeceğiniz anlamına gelmez. Kaydedebilirsiniz ancak bu değişiklikler yalnızca sizin içeriği nasıl göreceğinizi etkiler. Raporun özgün varsayılan görünümüne geri dönmek için **Varsayılana sıfırla**’yı seçin.

![Varsayılana dön simgesinin ekran görüntüsü.](./media/end-user-reports/power-bi-reset.png)

## <a name="dashboards-versus-reports"></a>Panolarla ve raporları karşılaştırma

[Panolar](end-user-dashboards.md) da görsellerle dolu tuvaller olduklarından genellikle raporlarla karıştırılır. Ancak bazı önemli farklılıklar bulunur.  

| **Özellik** | **Panolar** | **Raporlar** |
| --- | --- | --- |
| Sayfalar |Bir sayfa |Bir veya daha fazla sayfa |
| Veri kaynakları |Pano başına bir veya daha fazla rapor ve bir veya daha fazla veri kümesi |Rapor başına tek bir veri kümesi |
| Filtreleme |Filtreleme veya dilimleme yapamazsınız |Filtreleme, vurgulama ve dilimleme için birçok farklı yol vardır |
| Uyarı ayarlama |Pano belirli koşulları karşıladığında size e-posta gönderilmesini için uyarılar oluşturabilirsiniz |Hayır |
| Özellik |Bir panoyu öne çıkan panonuz olarak ayarlayabilirsiniz |Öne çıkan bir rapor oluşturamazsınız |
| Temel alınan veri kümesi tablolarını ve alanlarını görme |Hayır. Verileri dışarı aktarabilir ancak veri kümesi tablolarını ve alanları panonun kendisinde göremezsiniz |Evet. Veri kümesi tablolarını, alanlarını ve görme iznine sahip olduğunuz değerleri görebilirsiniz |
| Özelleştirme |Hayır  |İlgili içerikleri filtreleyebilir, dışarı aktarabilir, görüntüleyebilir, yer işaretleri ekleyebilir, QR kodları oluşturabilir, Excel’de analiz edebilir ve daha birçok işlem yapabilirsiniz |

<!--| Available in Power BI Desktop |No |Yes, can create and view reports in Desktop |
| Pinning |Can pin existing visuals (tiles) only from current dashboard to your other dashboards |Can pin visuals (as tiles) to any of your dashboards. Can pin entire report pages to any of your dashboards. | -->

## <a name="report-designers-and-report-consumers"></a>Rapor tasarımcıları ve rapor kullanıcıları

İş rolünüze bağlı olarak, kendi kullanımınız veya iş arkadaşlarınızla paylaşmak için rapor oluşturan bir *tasarımcı* olabilirsiniz. Bu durumda raporları nasıl oluşturacağınızı ve paylaşacağınızı öğrenmek istersiniz.

Buna karşılık başkalarından rapor alan bir *kullanıcı* da olabilirsiniz. Bu durumda raporları nasıl anlayacağınızı ve raporlarla nasıl etkileşim kuracağınızı öğrenmek istersiniz. Bir rapor *kullanıcısıysanız*, bu bağlantılar işinize yarayabilir:

* Raporları ve rapor araçlarını nerede bulacağınızı öğrenmek için [Power BI hizmeti turu](end-user-basic-concepts.md) ile başlayın.
* [Bir raporu açmayı](end-user-report-open.md) ve [tüketicilerin kullanabileceği tüm etkileşimleri](end-user-reading-view.md) öğrenin.
* Raporları daha rahat kullanmak için [örneklerimizden](../create-reports/sample-tutorial-connect-to-the-samples.md) biriyle tura katılın.  
* Raporun hangi veri kümesini kullandığını ve hangi panoların rapordaki görselleri (*sabitlemeler*) gösterdiğini görmek için bkz. [Power BI hizmetinde ilişkili içeriği görüntüleme](end-user-related.md).

> [!TIP]
> Aradığınızı burada bulamadıysanız tüm *Rapor* makalelerine göz atmak için sol taraftaki İçindekiler bölümünü kullanın.

## <a name="next-steps"></a>Sonraki adımlar

[Raporu açma ve görüntüleme](end-user-report-open.md)    
[Power BI hizmetindeki panolar](end-user-dashboards.md)

