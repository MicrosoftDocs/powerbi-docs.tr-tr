---
title: Power BI Desktop'taki öngörüleri kullanma (Önizleme)
description: Power BI Desktop'ta artışlar veya düşüşler hakkında kolayca öngörü elde edin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/23/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 8f69eec2ce7273898698fb086f372daa2201eed8
ms.sourcegitcommit: 6faeb642721ee5abb41c04a8b729880c01c4d40e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39210273"
---
# <a name="use-insights-in-power-bi-desktop-preview"></a>Power BI Desktop'taki öngörüleri kullanma (Önizleme)
**Power BI Desktop**'tan grafiklerdeki artışları veya düşüşleri açıklamasını, dağıtım faktörlerini grafikte görmeyi ve verileriniz hakkında hızlı, otomatik ve içgörü sunan analizler elde etmeyi isteyebilirsiniz. Tek yapmanız gereken bir veri noktasına sağ tıklayıp **Analiz > Düşüşü açıkla**'yı (veya önceki değer daha düşükse artışı) veya **Analiz > Bu dağıtımın nerede farklı olduğunu bul**'u seçmektir. İçgörü, kullanışlı bir pencerede gösterilir.

![](media/desktop-insights/insights_01.png)

Öngörü özelliği bağlamsaldır ve bir önceki veri noktasını (bir önceki çubuk veya sütun gibi) temel alır.

> [!NOTE]
> Bu özellik önizleme sürümündedir ve değişikliğe tabidir. Öngörü özelliği **Power BI Desktop** uygulamasının Eylül 2017 sürümünden itibaren varsayılan olarak etkindir. (Etkinleştirmek için Önizleme kutusunu işaretlemenize gerek yoktur.)
> 
> 

## <a name="using-insights"></a>Öngörüleri kullanma
Öngörüleri kullanmak için tek yapmanız gereken herhangi bir çubuk veya çizgi görselindeki veri noktalarından birine sağ tıklayıp **Analiz > Artışı açıkla** (veya *Düşüşü açıkla*, tüm öngörülerde önceki veri noktası temel alındığı için) seçeneğini belirlemektir.

![](media/desktop-insights/insights_02.png)

**Power BI Desktop** uygulaması verileri makine öğrenimi algoritmalarından geçirerek pencerede bir görselin yanı sıra artışa veya düşüşe en çok etki eden kategorileri belirten bir açıklama görüntüler. Öngörüler varsayılan olarak, aşağıdaki görüntüde gösterildiği gibi *şelale* görseli ile sunulur.

![](media/desktop-insights/insights_03.png)

Şelale görselinin en altında bulunan küçük simgeleri seçerek öngörülerin dağılım grafiği, yığılmış sütun grafik veya şerit grafik şeklinde görüntülenmesini sağlayabilirsiniz.

![](media/desktop-insights/insights_04.png)

Sayfanın en üstündeki *başparmak yukarı* ve *başparmak aşağı* simgelerini kullanarak görsel ve özellik hakkında geri bildirimde bulunabilirsiniz.

Daha da önemlisi, görselin en üstünde bulunan **+** düğmesini kullanarak görseli tıpkı kendi oluşturduğunuz bir görsel gibi raporunuza ekleyebilirsiniz. Ardından, raporunuzdaki diğer görsellerde olduğu gibi biçimlendirme ve ayarlama yapabilirsiniz. Seçtiğiniz öngörü görselini yalnızca **Power BI Desktop** uygulamasında rapor düzenleme sırasında ekleyebilirsiniz.

Öngörüleri, okuma veya görüntüleme modunda kullanabilir, bu sayede hem verileri çözümleyebilir hem de raporlarınıza kolayca ekleyebileceğiniz görseller oluşturabilirsiniz.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar
Öngörüler bir önceki veri noktasına göre gerçekleşen değişimi temel aldığından, görseldeki ilk veri noktasını seçtiğinizde bu özellik etkin değildir. 

**Öngörüler** için desteklenmeyen senaryoların listesi aşağıda verilmiştir:

* Üst N filtreleri
* Ekle/dışla filtreleri
* Ölçü filtreleri
* Eklenebilir olmayan ölçüler ve toplamlar
* Değeri şu şekilde göster
* Filtrelenmiş ölçüler (öngörülerde dağılım grafiği için kullandığımız yeni özellik)
* Skaler sıralama ölçütü tanımlamayan X ekseni üzerindeki kategorik sütunlar. Hiyerarşi kullanıyorsanız etkin hiyerarşideki tüm sütunların bu koşula uygun olması gerekir
* Sayısal olmayan ölçüler

Ayrıca aşağıdaki model türleri ve veri kaynakları da öngörüler için desteklenmemektedir:

* DirectQuery
* Canlı bağlantı
* Şirket içi Reporting Services
* Ekleme

## <a name="next-steps"></a>Sonraki adımlar
**Power BI Desktop** ve Power BI Desktop'la çalışmaya başlama hakkında daha fazla bilgi için aşağıdaki makalelere başvurun.

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop ile Sorgulara Genel Bakış](desktop-query-overview.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'taki Verilere Bağlanma](desktop-connect-to-data.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki Genel Sorgu Görevleri](desktop-common-query-tasks.md)   

