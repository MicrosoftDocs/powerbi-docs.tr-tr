---
title: Power BI'da görüntülemek üzere bir Excel çalışma kitabının boyutunu azaltma
description: Power BI'da görüntülemek üzere bir Excel çalışma kitabının boyutunu azaltma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/10/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 111e38fd37bcdfa2a72986bb08a37d89345bbe69
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282276"
---
# <a name="reduce-the-size-of-an-excel-workbook-to-view-it-in-power-bi"></a>Power BI'da görüntülemek üzere bir Excel çalışma kitabının boyutunu azaltma
Power BI'a boyutu 1 GB'ın altındaki herhangi bir Excel çalışma kitabını yükleyebilirsiniz. Bir Excel çalışma kitabı iki bölümden oluşabilir: Veri Modeli ve raporun geri kalanını oluşturan temel çalışma sayfası içeriği. Aşağıdaki boyut sınırlarına uygunsa, raporu **OneDrive İş**'e kaydedebilir, Excel Online'da görüntüleyebilir veya Power BI'dan rapora bağlanabilirsiniz:

* Çalışma kitabının tamamı en fazla 1 GB olabilir.
* Temel çalışma sayfası içeriği en fazla 30 MB olabilir.

## <a name="what-makes-core-worksheet-contents-larger-than-30-mb"></a>Temel çalışma sayfası içeriğinin 30 MB'ın üzerine çıkmasına neden olan öğeler
Temel çalışma sayfası içeriğinin 30 MB'ın üzerine çıkmasına neden olabilecek bazı öğeler şunlardır:

* Görüntüler.
* Gölgeli hücreler. [Hücre gölgelendirme biçimini kaldırma](https://support.office.com/article/Add-or-change-the-background-color-of-cells-ac10f131-b847-428f-b656-d65375fb815e).
* Renkli çalışma sayfaları. [Sayfa arka planını kaldırma](https://support.office.com/article/add-or-remove-a-sheet-background-3577a762-8450-4556-96a2-cc265abc00a8).
* Metin kutuları.
* Küçük resimler.

Mümkünse, bu öğeleri kaldırabilirsiniz. 

Raporda Veri Modeli varsa başka seçenekleriniz de vardır: 

* Verileri Excel çalışma sayfalarından kaldırıp Veri Modelinde depolayabilirsiniz. Ayrıntılar için aşağıda bulunan, "Çalışma sayfalarındaki verileri kaldırma" bölümüne bakın. 
* Raporun toplam boyutunu azaltmak için [belleği verimli kullanan bir Veri Modeli oluşturun](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70).

Bu değişikliklerin herhangi birini yapmak için çalışma kitabını Excel'de düzenlemeniz gerekir.

[SharePoint Online'daki Excel çalışma kitapları için dosya boyutu sınırları](https://support.office.com/article/File-size-limits-for-workbooks-in-SharePoint-Online-9e5bc6f8-018f-415a-b890-5452687b325e) hakkında daha fazla bilgi edinin.

## <a name="remove-data-from-worksheets"></a>Çalışma sayfalarındaki verileri kaldırma
Excel'e Power Query sekmesinden veya Excel Veri sekmesinden veri aktarırsanız, çalışma kitabı, hem Excel tablosunda hem de Veri Modelinde aynı verileri içerebilir. Excel çalışma sayfalarındaki büyük tablolar temel çalışma sayfası içeriğinin 30 MB'ın üzerinde olmasına neden olabilir. Tabloyu Excel'den kaldırıp verileri Veri Modelinde tutmak raporun temel çalışma sayfası içeriğini önemli ölçüde azaltabilir. 

Excel'e veri aktarırken şu ipuçlarını aklınızda bulundurun:

* **Power Query'de**: **Çalışma sayfasına yükle** kutusunun işaretini kaldırın.
  
  Veriler yalnızca Veri Modeline aktarılır; Excel çalışma sayfalarında veri bulunmaz.
* **Excel Verileri sekmesinde**, daha önce içeri aktarma sihirbazında **Tablo**'yu işaretlediyseniz: **Varolan Bağlantılar**'a gidin \> bağlantıya tıklayın \> **Yalnızca bağlantı oluştur**'a tıklayın. Özgün tabloyu veya ilk içeri aktarma işlemi sırasında oluşturulmuş olan tabloları silin.
* **Excel Veri sekmesinde**: **Verileri İçeri Aktar** kutusundaki **Tablo** seçeneğini işaretlemeyin.

## <a name="workbook-size-optimizer"></a>Workbook Size Optimizer
Çalışma kitabınızda veri modeli varsa Workbook Size Optimizer aracını çalıştırarak çalışma kitabınızın boyutunu küçültebilirsiniz. [Workbook Size Optimizer'ı indirin](https://www.microsoft.com/download/details.aspx?id=38793).

## <a name="related-info"></a>İlgili bilgiler
[Belleği verimli kullanan bir Veri Modeli oluşturma](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)

[Power BI Desktop'ta OneDrive İş bağlantılarını kullanma](desktop-use-onedrive-business-links.md)

