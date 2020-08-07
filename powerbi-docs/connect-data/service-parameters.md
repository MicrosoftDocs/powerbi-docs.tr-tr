---
title: Power BI hizmetinde parametre ayarlarını düzenleme
description: Sorgu parametreleri Power BI Desktop'ta oluşturulur ama Power BI hizmetinde gözden geçirilebilir ve güncelleştirilebilir
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 08/04/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 3b64c1dd502fd16199fbff9f64cd2c017006d1f1
ms.sourcegitcommit: a7227f6d3236e6e0a7bc1f83ff6099b5cd58bff3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87768486"
---
# <a name="edit-parameter-settings-in-the-power-bi-service"></a>Power BI hizmetinde parametre ayarlarını düzenleme
Rapor oluşturucular raporlara Power BI Desktop’ta sorgu parametreleri ekler. Parametreler, raporların bölümlerini bir veya birden çok parametre *değerine* bağımlı hale getirmeye olanak sağlar. Örneğin, rapor oluşturucu verileri tek bir ülke/bölge ile kısıtlayan bir parametre veya tarih, saat ve metin gibi alanlara kabul edilebilir biçimler tanımlayan bir parametre oluşturabilir.

![Desktop'ta Parametreleri Yönet seçeneğinin gösterildiği Giriş sekmesi](media/service-parameters/power-bi-manage-parameters.png)

## <a name="review-and-edit-parameters-in-power-bi-service"></a>Power BI hizmetinde parametreleri gözden geçirme ve düzenleme

Rapor oluşturucusu olarak Power BI Desktop'ta parametreleri siz belirlersiniz. [Bu raporu Power BI hizmetinde yayımladığınızda](../create-reports/desktop-upload-desktop-files.md), parametre ayarları ve seçimleri de birlikte gelir. Power BI hizmetinde parametre ayarlarını inceleyip düzenleyebilir, ancak bunları oluşturamazsınız.

1. Power BI hizmetinde, dişli simgesini ![dişli simgesi](media/service-parameters/power-bi-cog.png) seçerek **Ayarlar**’ı açın.

2. **Veri Kümeleri**'nin sekmesini seçin ve listede bir veri kümesini vurgulayın. 
    
    ![Veri Kümeleri sekmesinin seçili olduğu Ayarlar penceresi](media/service-parameters/power-bi-select-dataset2.png)

3. **Parametreler**'i genişletin.  Seçilen veri kümesinin parametresi yoksa, Sorgu parametreleri hakkında daha fazla bilgi edinin bağlantısını içeren bir ileti görürsünüz. Veri kümesinin parametreleri varsa, söz konusu parametreleri göstermek için **Parametreler** başlığını genişletin. 

    ![Parametreler'in genişletildiği Ayarlar penceresi](media/service-parameters/power-bi-settings.png)

    Parametre ayarlarını gözden geçirin ve gereken değişiklikleri yapın. Soluk gösterilen alanlar düzenlenemez. 


## <a name="next-steps"></a>Sonraki adımlar
Basit parametreleri eklemenin geçici bir yolu da [URL'de değişiklik yapmaktır](../collaborate-share/service-url-filters.md).
