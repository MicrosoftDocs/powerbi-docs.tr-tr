---
title: Power BI hizmetindeki veri kümesi parametrelerinin ayarlarını görüntüleme ve düzenleme
description: Sorgu parametreleri Power BI Desktop'ta oluşturulur ama Power BI hizmetinde gözden geçirilebilir ve güncelleştirilebilir
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/26/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: ac271e8013bce5824931153351a651644a716a2f
ms.sourcegitcommit: 5eb8632f653b9ea4f33a780fd360e75bbdf53b13
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965171"
---
# <a name="what-is-a-query-parameter"></a>Sorgu parametresi nedir?
Sorgu parametreleri, Power BI Desktop'ta rapor oluşturucular tarafından eklenir. Parametreler, raporların bölümlerini bir veya birden çok parametre *değerine* bağımlı hale getirmeye olanak sağlar. Örneğin, rapor oluşturucu verileri tek bir countryregion'la kısıtlayan bir parametre veya tarih, saat ve metin gibi alanlara kabul edilebilir biçimler tanımlayan bir parametre oluşturabilir.

![Desktop'ta Parametreleri Yönet seçeneğinin gösterildiği Giriş sekmesi](media/service-parameters/power-bi-manage-parameters.png)


## <a name="review-and-edit-parameters-in-power-bi-service"></a>Power BI hizmetinde parametreleri gözden geçirme ve düzenleme

Parametreler Desktop'ta tanımlandıktan sonra, [rapor Power BI hizmetinde yayımlandığında](desktop-upload-desktop-files.md), parametre ayarlarıyla seçimleri söz konusu raporla birlikte gezinir. Bazı parametre ayarları Power BI hizmetinde gözden geçirilebilir ve düzenlenebilir; bunlar kullanılabilir verileri kısıtlayan parametreler değil, kabul edilebilir değerleri tanımlayan ve açıklayan parametrelerdir.

1. Power BI hizmetinde, dişli simgesini ![dişli simgesi](media/service-parameters/power-bi-cog.png) seçerek **Ayarlar**'ı açın.

2. **Veri Kümeleri**'nin sekmesini seçin ve listede bir veri kümesini vurgulayın. 
    
    ![Veri Kümeleri sekmesinin seçili olduğu Ayarlar penceresi](media/service-parameters/power-bi-select-dataset2.png)

3. **Parametreler**'i genişletin.  Seçilen veri kümesinin parametresi yoksa, Sorgu parametreleri hakkında daha fazla bilgi edinin bağlantısını içeren bir ileti görürsünüz. Ancak veri kümesinin parametreleri varsa, **Parametreler** başlığının genişletilmesi söz konusu parametreleri gösterir. 

    ![Parametreler'in genişletildiği Ayarlar penceresi](media/service-parameters/power-bi-settings.png)

    Parametre ayarlarını gözden geçirin ve gereken değişiklikleri yapın. Soluk gösterilen alanlar düzenlenemez. 


## <a name="next-steps"></a>Sonraki adımlar
Basit parametreleri eklemenin geçici bir yolu da [URL'de değişiklik yapmaktır](service-url-filters.md).