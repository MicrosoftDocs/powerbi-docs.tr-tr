---
title: Bir tablo veya matristeki görüntüleri raporda görüntüleme
description: Power BI Desktop’ta görüntülerin köprü bağlantılarını içeren bir sütun oluşturun. Ardından Power BI Desktop veya Power BI hizmetinde, bu köprüleri bir rapor tablosu, matris, dilimleyici veya çok satırlı karta ekleyerek görüntüyü gösterin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 09/11/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: 4ba0042804d366ddfd80935c48246cadeadf3614
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96417969"
---
# <a name="display-images-in-a-table-matrix-or-slicer-in-a-report"></a>Bir tablo, matris veya dilimleyicideki görüntüleri raporda görüntüleme

Raporlara görüntüler eklemek, raporlarınızı geliştirmenin iyi bir yoludur. Sayfadaki statik görüntüler bazı amaçlar için iyidir. Ancak bazen raporunuzdaki verilerle ilgili görüntülerin olmasını isteyebilirsiniz. Bu konu başlığı altında, görüntüleri bir tablo, matris, dilimleyici veya çok satırlı bir kartta nasıl görüntüleyeceğiniz öğretilir. 

![Tablodaki URL görüntüleri](media/power-bi-images-tables/power-bi-url-images-table.png)

## <a name="add-images-to-your-report"></a>Raporunuza görüntü ekleme

1. Görüntülerin URL'leriyle bir sütun oluşturun. Gereksinimler için bu makalenin ilerleyen kısımlarında yer alan [Dikkat Edilmesi Gerekenler](#considerations) kısmına bakın.

1. O sütunu seçin. **Modelleme** şeridinde **Veri kategorisi** için **Görüntü URL’si** seçeneğini belirleyin.

    ![Veri kategorisini Görüntü URL'sine ayarlama](media/power-bi-images-tables/power-bi-set-url-image.png)

1. Sütunu bir tablo, matris, dilimleyici veya çok satırlı karta ekleyin.

    ![Görüntülerle birlikte dilimleyici](media/power-bi-images-tables/power-bi-url-images-slicer.png)

## <a name="considerations"></a>Dikkat edilmesi gereken noktalar

- Görüntünün şu dosya biçimlerinden birinde olması gerekir: .bmp, .jpg, .jpeg, .gif, .png veya .svg
- URL'nin SharePoint gibi oturum açma gerektiren bir site üzerinde değil, anonim olarak erişilebilir olması gerekir. Ancak, görüntüler SharePoint veya OneDrive üzerinde barındırılıyorsa, doğrudan bunları işaret eden bir ekleme kodu alabilirsiniz. 


## <a name="next-steps"></a>Sonraki adımlar

[Sayfa düzeni ve biçimlendirme](/learn/modules/visuals-in-power-bi/12-formatting)

[Power BI hizmetinde tasarımcılar için temel kavramlar](../fundamentals/service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
