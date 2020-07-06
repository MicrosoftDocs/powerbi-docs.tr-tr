---
title: Power BI Desktop görsellerinde görsel tablosu ve kayıtlar
description: Detaya gitmek için Power BI Desktop’ın Görsel tablosu ve Veri noktası tablosu özelliklerini kullanın
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/21/2020
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: f70876b3b8c1815576ed019f88b67296f7aec052
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85238625"
---
# <a name="use-visual-table-and-data-point-table-in-power-bi-desktop"></a>Power BI Desktop’ta Görsel tablosu ve Veri noktası tablosu özelliklerini kullanma
**Power BI Desktop**'ta bir görselleştirmenin detayına gidebilir ve seçilen görsel için temel alınan verilerin metinsel temsilini veya tek tek veri öğelerini görebilirsiniz. Bu özellikler bazen *geçişli tıklama*, *detaylandırma* veya *ayrıntıları görüntüleme* olarak adlandırılır.

Görseldeki verileri bir tablo olarak görüntülemek için **Görsel tablosu** özelliğini veya tek bir veri noktasını hesaplamak için kullanılan verilerin tablosunu görüntülemek için **Veri noktası tablosu** özelliğini kullanabilirsiniz. 

![Görsel tablosu ve Veri noktası tablosu](media/desktop-see-data-see-records/see-data-record.png)

>[!IMPORTANT]
>**Görsel tablosu** ve **Veri noktası tablosu** yalnızca aşağıdaki görselleştirme türlerini destekler:
>  - Çubuk Grafik
>  - Sütun grafiği
>  - Halka grafik
>  - Kartogram
>  - Huni
>  - Harita
>  - Pasta grafiği
>  - Treemap

## <a name="use-visual-table-in-power-bi-desktop"></a>Power BI Desktop’ta Görsel tablosunu kullanma

**Görsel tablosu** bir görselleştirmede temel alınan verileri gösterir. **Görsel tablosu** seçeneği, bir görsel seçildiğinde şeridin **Veri/Detay** sekmesinin **Göster** bölümünde görünür.

![Şeritte Görsel tablosu](media/desktop-see-data-see-records/visual-table-01.png)

Bir görselleştirmeye sağ tıkladıktan sonra görüntülenen menüden **Verileri Göster**’i seçerek veya bir görselleştirmenin sağ üst köşesindeki **Diğer seçenekler** (...) ve sonra **Tablo olarak göster**’i seçerek de verileri görebilirsiniz.

![Verileri Göster sağ tıklama menüsü](media/desktop-see-data-see-records/visual-table-02.png)&nbsp;&nbsp;![Verileri Göster Diğer Seçenekler](media/desktop-see-data-see-records/visual-table-03.png)

> [!NOTE]
> Sağ tıklama menüsünün kullanılabilmesi için görseldeki bir veri noktasının üzerine gelmeniz gerekir.

**Görsel tablosu**’nu veya **Veri noktası tablosu**’nu seçtiğinizde Power BI Desktop tuvalinde verilerin hem görsel hem de metin gösterimi görüntülenir. *Yatay görünümde* görsel öğe tuvalin üst yarısında, veriler ise tuvalin alt yarısında görüntülenir. 

![yatay görünüm](media/desktop-see-data-see-records/visual-table-04.png)

Tuvalin sağ üst köşesindeki simgeyi seçerek yatay görünüm ile *dikey görünüm* arasında geçiş yapabilirsiniz.

![dikey görünüm geçiş](media/desktop-see-data-see-records/visual-table-05.png)

Rapora geri dönmek için tuvalin sol üst köşesindeki **< Rapora Geri Dön** öğesini seçin.

![Rapora Geri Dön](media/desktop-see-data-see-records/visual-table-06.png)

## <a name="use-data-point-table-in-power-bi-desktop"></a>Power BI Desktop’ta Veri noktası tablosunu kullanma

Ayrıca bir görselleştirmedeki tek bir veri kaydına odaklanıp bu öğenin temel aldığı verilerin de detayına gidebilirsiniz. **Veri noktası tablosu** özelliğini kullanmak için bir görselleştirme seçin, ardından şeridin **Veri/Detay** sekmesindeki **Görsel Araçlar** bölümünde bulunan **Veri noktası tablosu**’nu seçin ve ardından görselleştirme üzerinde bir veri noktası ya da satır seçin. 

![Şeritte Veri noktası tablosu](media/desktop-see-data-see-records/visual-table-07.png)

> [!NOTE]
> Şeritteki **Veri noktası tablosu** düğmesinin devre dışı ve gri renkte olması, seçili görselleştirmenin **Veri noktası tablosu** özelliğini desteklemediği anlamına gelir.

Ayrıca bir veri öğesine sağ tıklayarak görüntülenen menüden **Veri noktası tablosu**’nu seçebilirsiniz.

![Sağ tıklamayla Veri noktası tablosu](media/desktop-see-data-see-records/visual-table-08.png)

Bir veri öğesi için **Veri noktası tablosu**’nu seçtiğinizde Power BI Desktop tuvali seçili öğeyle ilişkili tüm verileri gösterir. 

![](media/desktop-see-data-see-records/visual-table-09.png)

Rapora geri dönmek için tuvalin sol üst köşesindeki **< Rapora Geri Dön** öğesini seçin.


> [!NOTE]
>**Veri noktası tablosu** özelliği aşağıdaki sınırlamalara sahiptir:
> - **Veri noktası tablosu** görünümünde verileri değiştiremez ve rapora geri kaydedemezsiniz.
> - Görselinizdeki bir (çok boyutlu) ölçüm grubunda hesaplanmış ölçü kullanılıyorsa **Veri noktası tablosu** özelliğinden yararlanamazsınız.
> - Canlı bir çok boyutlu (MD) modele bağlıyken **Veri noktası tablosu** özelliğini kullanamazsınız.

## <a name="next-steps"></a>Sonraki adımlar
**Power BI Desktop**'ta çok çeşitli rapor biçimlendirme ve veri yönetim özellikleri bulunur. Bazı örnekler için aşağıdaki kaynaklara bakın:

* [Power BI Desktop'ta gruplandırmayı ve gruplamayı kullanma](desktop-grouping-and-binning.md)
* [Power BI Desktop raporlarında kılavuz çizgilerini, kılavuza yaslama işlevini, z düzenini, hizalamayı ve dağıtımı kullanma](desktop-gridlines-snap-to-grid.md)

