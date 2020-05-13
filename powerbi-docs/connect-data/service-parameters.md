---
title: Power BI hizmetinde parametre ayarlarını düzenleme
description: Sorgu parametreleri Power BI Desktop'ta oluşturulur ama Power BI hizmetinde gözden geçirilebilir ve güncelleştirilebilir
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 9dad3e306f895e8c8bf2930b8e032ec558f3f7fc
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83308360"
---
# <a name="edit-parameter-settings-in-the-power-bi-service"></a>Power BI hizmetinde parametre ayarlarını düzenleme
Rapor oluşturucular raporlara Power BI Desktop’ta sorgu parametreleri ekler. Parametreler, raporların bölümlerini bir veya birden çok parametre *değerine* bağımlı hale getirmeye olanak sağlar. Örneğin, rapor oluşturucu verileri tek bir ülke/bölge ile kısıtlayan bir parametre veya tarih, saat ve metin gibi alanlara kabul edilebilir biçimler tanımlayan bir parametre oluşturabilir.

![Desktop'ta Parametreleri Yönet seçeneğinin gösterildiği Giriş sekmesi](media/service-parameters/power-bi-manage-parameters.png)

## <a name="review-and-edit-parameters-in-power-bi-service"></a>Power BI hizmetinde parametreleri gözden geçirme ve düzenleme

Rapor oluşturucusu olarak Desktop'ta parametreleri siz belirlersiniz. [Bu raporu Power BI hizmetinde yayımladığınızda](../create-reports/desktop-upload-desktop-files.md), parametre ayarları ve seçimleri de birlikte gelir. Bazı parametre ayarlarını Power BI hizmetinde gözden geçirebilir ve düzenleyebilirsiniz; bunlar kullanılabilir verileri kısıtlayan parametreler değil, kabul edilebilir değerleri tanımlayan ve açıklayan parametrelerdir.

1. Power BI hizmetinde, dişli simgesini ![dişli simgesi](media/service-parameters/power-bi-cog.png) seçerek **Ayarlar**'ı açın.

2. **Veri Kümeleri**'nin sekmesini seçin ve listede bir veri kümesini vurgulayın. 
    
    ![Veri Kümeleri sekmesinin seçili olduğu Ayarlar penceresi](media/service-parameters/power-bi-select-dataset2.png)

3. **Parametreler**'i genişletin.  Seçilen veri kümesinin parametresi yoksa, Sorgu parametreleri hakkında daha fazla bilgi edinin bağlantısını içeren bir ileti görürsünüz. Ancak veri kümesinin parametreleri varsa, **Parametreler** başlığının genişletilmesi söz konusu parametreleri gösterir. 

    ![Parametreler'in genişletildiği Ayarlar penceresi](media/service-parameters/power-bi-settings.png)

    Parametre ayarlarını gözden geçirin ve gereken değişiklikleri yapın. Soluk gösterilen alanlar düzenlenemez. 


## <a name="next-steps"></a>Sonraki adımlar
Basit parametreleri eklemenin geçici bir yolu da [URL'de değişiklik yapmaktır](../collaborate-share/service-url-filters.md).