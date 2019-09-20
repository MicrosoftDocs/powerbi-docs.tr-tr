---
title: Bir tablo veya matristeki görüntüleri raporda görüntüleme
description: Power BI Desktop’ta görüntülerin köprü bağlantılarını içeren bir sütun oluşturun. Ardından Power BI Desktop veya Power BI hizmetinde, bu köprüleri bir rapor tablosu, matris, dilimleyici veya çok satırlı karta ekleyerek görüntüyü gösterin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/11/2019
ms.author: maggies
LocalizationGroup: Visualizations
ms.openlocfilehash: 2ebbc277f2a269ebaf2d1bdb99f1aa800576b466
ms.sourcegitcommit: ba085b248c54e8fb1fd8eb2bb23a814e3fdd7ff6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70936505"
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

## <a name="considerations"></a>Önemli noktalar

- Görüntünün şu dosya biçimlerinden birinde olması gerekir: .bmp, .jpg, .jpeg, .gif, .png veya .svg
- URL'nin SharePoint gibi oturum açma gerektiren bir site üzerinde değil, anonim olarak erişilebilir olması gerekir. Ancak, görüntüler SharePoint veya OneDrive üzerinde barındırılıyorsa, doğrudan bunları işaret eden bir ekleme kodu alabilirsiniz. 


## <a name="next-steps"></a>Sonraki adımlar

[Rapora statik şekiller, metin kutuları ve görüntüler ekleme](https://docs.microsoft.com/power-bi/guided-learning/visualizations?tutorial-step=11)

[Power BI hizmetinde tasarımcılara yönelik temel kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

