---
title: Power BI Desktop görsellerinde veri ve kayıtlara bakma
description: Power BI Desktop'ın Verileri Görüntüle ve Kayıtları Görüntüle özelliklerini kullanarak detaya gitme
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 6e425f146228d0139b9eec914a44ed5dc732fe98
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514783"
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Power BI Desktop görsellerinde Verileri Görüntüle ve Kayıtları Görüntüle özelliklerini kullanma
**Power BI Desktop**'ta bir görselleştirmenin detayına gidebilir ve seçilen görsel için temel alınan verilerin metinsel temsilini veya tek tek veri öğelerini görebilirsiniz. Bu özellikler bazen *geçişli tıklama*, *detaylandırma* veya *ayrıntıları görüntüleme* olarak adlandırılır.

Seçili görselleştirmeler tarafından kullanılan değerlerin metinsel bir sürümünü görüntülemek için **Verileri Görüntüle** ya da seçili bir kayıt veya veri noktasına ait tüm verileri görüntülemek için **Kayıtları Görüntüle** seçeneklerini kullanabilirsiniz. 

![Verileri Görüntüle ve Kayıtları Görüntüle](media/desktop-see-data-see-records/see-data-record.png)

>[!IMPORTANT]
>**Verileri Görüntüle** ve **Kayıtları Görüntüle** seçenekleri yalnızca aşağıdaki görselleştirme türlerini destekler:
>  - Çubuk Grafik
>  - Sütun grafiği
>  - Halka grafik
>  - Kartogram
>  - Huni
>  - Harita
>  - Pasta grafiği
>  - Treemap

## <a name="use-see-data-in-power-bi-desktop"></a>Power BI Desktop'ta Verileri Görüntüle özelliğini kullanma

**Verileri Görüntüle**, bir görselleştirmede temel alınan verileri gösterir. **Verileri Görüntüle** seçeneği, bir görselleştirme seçildiğinde şeridin **Görsel Araçlar** bölümündeki **Veri/Detay** sekmesinde görünür.

![Şeritte Verileri Görüntüle seçeneği](media/desktop-see-data-see-records/see-data1.png)

Bir görselleştirmeye sağ tıkladıktan sonra görüntülenen menüden **Verileri Göster**’i seçerek veya bir görselleştirmenin sağ üst köşesindeki **Diğer seçenekler** üç noktasını (...) ve sonra **Verileri Göster**’i seçerek de verileri görebilirsiniz.

![Verileri Göster sağ tıklama menüsü](media/desktop-see-data-see-records/see-data2.png)&nbsp;&nbsp;![Verileri Göster Diğer Seçenekler](media/desktop-see-data-see-records/see-data3.png)

> [!NOTE]
> Sağ tıklama menüsünün kullanılabilmesi için görseldeki bir veri noktasının üzerine gelmeniz gerekir.

**Verileri Görüntüle** veya **Verileri Göster**’i seçtiğinizde Power BI Desktop tuvalinde verilerin hem görsel hem de metinsel gösterimi görüntülenir. *Yatay görünümde* görsel öğe tuvalin üst yarısında, veriler ise tuvalin alt yarısında görüntülenir. 

![yatay görünüm](media/desktop-see-data-see-records/see-data4a.png)

Tuvalin sağ üst köşesindeki simgeyi seçerek yatay görünüm ile *dikey görünüm* arasında geçiş yapabilirsiniz.

![dikey görünüm geçiş](media/desktop-see-data-see-records/see-data4.png)

Rapora geri dönmek için tuvalin sol üst köşesindeki **< Rapora Geri Dön** öğesini seçin.

![Rapora Geri Dön](media/desktop-see-data-see-records/see-data5.png)

## <a name="use-see-records-in-power-bi-desktop"></a>Power BI Desktop'ta Kayıtları Görüntüle özelliğini kullanma

Ayrıca bir görselleştirmedeki tek bir veri kaydına odaklanıp bu öğenin temel aldığı verilerin de detayına gidebilirsiniz. **Kayıtları Görüntüle** özelliğini kullanmak için bir görselleştirme seçin, ardından şeridin **Görsel Araçlar** bölümündeki **Veri/Detay** sekmesinde bulunan **Kayıtları Görüntüle**’yi seçin ve ardından görselleştirme üzerinde bir veri noktası ya da satır seçin. 

![Şeritte Kayıtları Görüntüle seçeneği](media/desktop-see-data-see-records/see-record1.png)

> [!NOTE]
> Şeritteki **Kayıtları Görüntüle** düğmesi devre dışı ve gri renkteyse, seçili görselleştirmenin **Kayıtları Görüntüle** özelliğini desteklemediği anlamına gelir.

Ayrıca bir veri öğesine sağ tıklayarak görüntülenen menüden **Kayıtları Görüntüle**’yi seçebilirsiniz.

![Sağ tıklama ile Kayıtları Görüntüle seçeneği](media/desktop-see-data-see-records/see-record2.png)

Bir veri öğesi için **Kayıtları Görüntüle**’yi seçtiğinizde Power BI Desktop tuvali seçili öğeyle ilişkili tüm verileri gösterir. 

![](media/desktop-see-data-see-records/see-record3.png)

Rapora geri dönmek için tuvalin sol üst köşesindeki **< Rapora Geri Dön** öğesini seçin.

![](media/desktop-see-data-see-records/see-record4.png)

> [!NOTE]
>**Kayıtları Görüntüle** özelliği aşağıdaki sınırlamalara sahiptir:
> - **Kayıtları Görüntüle** görünümünde verileri değiştiremez ve rapora geri kaydedemezsiniz.
> - Görselinizde hesaplanmış ölçü kullanılıyorsa **Kayıtları Görüntüle** özelliğinden yararlanamazsınız.
> - Canlı bir çok boyutlu (MD) modele bağlıyken **Kayıtları Görüntüle** özelliğini kullanamazsınız.

## <a name="next-steps"></a>Sonraki adımlar
**Power BI Desktop**'ta çok çeşitli rapor biçimlendirme ve veri yönetim özellikleri bulunur. Bazı örnekler için aşağıdaki kaynaklara bakın:

* [Power BI Desktop'ta gruplandırmayı ve gruplamayı kullanma](desktop-grouping-and-binning.md)
* [Power BI Desktop raporlarında kılavuz çizgilerini, kılavuza yaslama işlevini, z düzenini, hizalamayı ve dağıtımı kullanma](desktop-gridlines-snap-to-grid.md)

