---
title: "Power BI Desktop görsellerinde veri ve kayıtlara bakma"
description: "Power BI Desktop'ın Verileri Görüntüle ve Kayıtları Görüntüle özelliklerini kullanarak detaya gitme"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/09/2017
ms.author: davidi
ms.openlocfilehash: c43ec48d1bd34a5df2578c6cc117dd3e3bbdb64f
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Power BI Desktop görsellerinde Verileri Görüntüle ve Kayıtları Görüntüle özelliklerini kullanma
**Power BI Desktop**'ta herhangi bir görselin detayına gidebilir ve seçilen görsel için verilerin metinsel temsilini veya tek tek veri öğelerini görebilirsiniz. Bu özellikler bazen *geçişli tıklama*, *detaylandırma* veya *ayrıntıları görüntüleme* olarak adlandırılır.

Bir görseldeki seçili bir veri öğesi için temel alınan satırları görüntülemek için **Kayıtları Görüntüle** özelliğini veya görseldeki değerlerin metin sürümünü görüntülemek için **Verileri Görüntüle** özelliğini kullanabilirsiniz. **Verileri Görüntüle** ve **Kayıtları Görüntüle** özelliklerini kullanmaya ilişkin bazı sınırlamalar vardır. Bu sınırlamalar, bu makalenin sonunda ele alınmaktadır.

![](media/desktop-see-data-see-records/see-data-see-records_1.png)

## <a name="using-see-data-in-power-bi-desktop"></a>Power BI Desktop'ta Verileri Görüntüle özelliğini kullanma
**Verileri Görüntüle** düğmesi, şeridin **Görsel Araçlar** bölümündeki **Veri/Detay** sekmesinde bulunur.

![](media/desktop-see-data-see-records/see-data-see-records_2.png)

Ayrıca bir görsele sağ tıklayıp görüntülenen menüden **Verileri Görüntüle** seçeneğini belirleyerek de **Verileri Görüntüle** özelliğini kullanabilirsiniz.

![](media/desktop-see-data-see-records/see-data-see-records_3.png)

> [!NOTE]
> Sağ tıklama menüsünün kullanılabilmesi için görseldeki bir veri noktasının üzerine gelmeniz gerekir.
> 
> 

**Verileri Görüntüle** seçeneğini belirlediğinizde **Power BI Desktop**, seçtiğiniz görsele ve verilere odaklanıp tuval alanını verilerin görsel ve metinsel gösterimine ayırır. Aşağıdaki görüntüde gösterildiği gibi, görsel tuvalin üst yarısında, veriler ise tuvalin alt yarısında görüntülenir. Bu, *yatay* görünümdür.

![](media/desktop-see-data-see-records/see-data-see-records_4.png)

Ayrıca sağ üst köşedeki simgeyi seçerek *dikey görünüme* de geçiş yapabilirsiniz (veya *yatay görünüme* geri dönebilirsiniz).

![](media/desktop-see-data-see-records/see-data-see-records_5.png)

Rapora geri dönmek için tuvalin sol üst köşesindeki **< Rapora Geri Dön** öğesini seçin.

![](media/desktop-see-data-see-records/see-data-see-records_6.png)

## <a name="using-see-records-in-power-bi-desktop"></a>Power BI Desktop'ta Kayıtları Görüntüle özelliğini kullanma
Ayrıca görsellerdeki tek bir veri öğesine odaklanıp bu öğenin temel aldığı verilerin de detayına gidebilirsiniz. Bir görsel seçildiğinde **Kayıtları Görüntüle** özelliğini kullanmak için izleyebileceğiniz iki yol bulunur: **Veri/Detay** şeridindeki **Kayıtları Görüntüle** iki durumlu düğmesini etkinleştirebilir veya bir veri öğesine sağ tıklayıp görüntülenen menüden **Kayıtları Görüntüle** seçeneğini belirleyebilirsiniz.

![](media/desktop-see-data-see-records/see-data-see-records_7.png)

> [!NOTE]
> Seçilen görsel **Kayıtları Görüntüle** özelliğini desteklemiyorsa şeritteki düğme gri renkte gösterilir.
> 
> 

**Kayıtları Görüntüle** özelliği seçildiğinde **Power BI Desktop**, aşağıdaki görüntüde gösterildiği gibi bu tek veri öğesine odaklanıp tuval alanını ilgili verileri görüntülemeye ayırır.

![](media/desktop-see-data-see-records/see-data-see-records_8.png)

Rapora geri dönmek için tuvalin sol üst köşesindeki **Rapora Geri Dön** düğmesini seçin.

## <a name="limitations"></a>Sınırlamalar
**Verileri Görüntüle** veya **Kayıtları Görüntüle** özelliklerini kullanırken göz önünde bulundurulması gereken birkaç sınırlama vardır:

* Yalnızca aşağıdaki görsel türleri desteklenir:
  * **Çubuk**
  * **Sütun**
  * **Harita**
  * **Ağaç Haritası**
  * **Doldurulmuş Harita**
  * **Pasta**
  * **Halka**
  * **Huni**
* Görselinizde hesaplanmış ölçü kullanılıyorsa **Kayıtları Görüntüle** özelliğinden yararlanamazsınız
* Canlı bir çok boyutlu (MD) modele bağlıyken **Kayıtları Görüntüle** özelliğini kullanamazsınız

## <a name="next-steps"></a>Sonraki adımlar
**Power BI Desktop**'ta çok çeşitli rapor biçimlendirme ve veri yönetim özellikleri bulunur. Bazı örnekler için aşağıdaki kaynaklara bakın:

* [Power BI Desktop'ta gruplandırmayı ve gruplamayı kullanma](desktop-grouping-and-binning.md)
* [Power BI Desktop raporlarında kılavuz çizgilerini, kılavuza yaslama işlevini, z düzenini, hizalamayı ve dağıtımı kullanma](desktop-gridlines-snap-to-grid.md)

