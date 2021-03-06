---
title: Mobil uygulamalar için Power BI Desktop'ta coğrafi filtreler ayarlama
description: Power BI Desktop'ta modelinizde coğrafi filtreler ayarladığınızda Power BI mobil uygulamalarında konumunuza ait verileri otomatik olarak filtreleyebilirsiniz.
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: pbi-transform-model
ms.topic: how-to
ms.date: 01/16/2018
LocalizationGroup: Model your data
ms.openlocfilehash: 2368732d5f0f5fe6b0c32ac535068725e8620215
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96414002"
---
# <a name="set-geographic-filters-in-power-bi-desktop-for-use-in-the-mobile-app"></a>Mobil uygulamada kullanmak için Power BI Desktop'ta coğrafi filtreler ayarlama
Power BI Desktop'ta bir sütunun [coğrafi verilerini kategorilere ayırarak](desktop-data-categorization.md) Power BI Desktop uygulamasının bir rapordaki görsellerde bulunan değerleri nasıl işlemesi gerektiğini belirleyebilirsiniz. Ayrıca siz veya iş arkadaşlarınız söz konusu raporu Power BI mobil uygulamalarında görüntülediğinizde Power BI, otomatik olarak bulunduğunuz konumlarla eşleşen coğrafi filtreler sağlar. 

Örneğin, müşterilerle toplantı yapmaya giden bir satış yöneticisi olduğunuzu ve ziyaret etmeyi planladığınız müşteriyle ilgili toplam satış ve gelir rakamlarını hızlıca filtrelemek istediğinizi düşünelim. Geçerli konumunuza ait verileri eyalet, şehir veya adres kullanarak detaylandırmak istiyorsunuz. Daha sonra zaman kalırsa yakınlardaki diğer müşterileri de ziyaret etmek istiyorsunuz. [Bu müşterileri bulmak için raporu konumunuza göre filtreleyebilirsiniz](../consumer/mobile/mobile-apps-geographic-filtering.md).

> [!NOTE]
> Mobil uygulamada konuma göre filtreleme işlemini sadece raporda geçen coğrafi adlar "New York City" ya da "Germany" gibi İngilizce yazılmışsa gerçekleştirebilirsiniz.
> 
> 

## <a name="identify-geographic-data-in-your-report"></a>Raporunuzdaki coğrafi verileri tanımlama
1. Power BI Desktop'ta Veri Görünümüne ![Veri Görünümü simgesi](media/desktop-mobile-geofiltering/pbi_desktop_data_icon.png)dokunun.
2. Şehir sütunu gibi coğrafi veriler içeren bir sütun seçin.
   
    ![Şehir sütunu](media/desktop-mobile-geofiltering/power-bi-desktop-geo-column.png)
3. **Modelleme** sekmesinde **Veri Kategorisi**'ni ve ardından ilgili kategoriyi seçin. Bu örnekte **Şehir** kategorisi kullanılmıştır.
   
    ![Veri kategorisi kutusu](media/desktop-mobile-geofiltering/power-bi-desktop-geo-category.png)
4. Modeldeki diğer alanlar için coğrafi veri kategorileri belirlemeye devam edin. 
   
   > [!NOTE]
   > Modeldeki her veri kategorisi için birden fazla sütun ayarlayabilirsiniz ancak bunu yaparsanız model Power BI mobil uygulamasında coğrafi filtre uygulayamaz. Mobil uygulamalarda coğrafi filtreleme özelliğini kullanmak üzere her kategori için yalnızca bir sütun seçin. Örneğin, tek bir **Şehir** sütunu, tek bir **Eyalet veya İl** sütunu ve tek bir **Ülke** sütunu. 
   > 
   > 

## <a name="create-visuals-with-your-geographic-data"></a>Coğrafi verilerinizle görsel oluşturma
1. Rapor Görünümüne ![Rapor Görünümü simgesi](media/desktop-mobile-geofiltering/power-bi-desktop-report-icon.png)geçin ve verilerinizdeki coğrafi alanları kullanan görseller oluşturun. 
   
    ![Harita içeren rapor](media/desktop-mobile-geofiltering/power-bi-desktop-geo-report.png)
   
    Bu örnekte, modelde şehir ve eyaleti tek bir sütunda toplayan hesaplanmış sütun da mevcuttur. [Power BI Desktop'ta hesaplanmış sütun oluşturma](desktop-calculated-columns.md) hakkında bilgi edinin.
   
    ![City + State alanı](media/desktop-mobile-geofiltering/power-bi-desktop-city-state-column.png)
2. Raporu Power BI hizmetinde yayımlayın.

## <a name="view-the-report-in-power-bi-mobile-app"></a>Raporu Power BI mobil uygulamasında görüntüleme
1. Raporu herhangi bir [Power BI mobil uygulamasında](../consumer/mobile/mobile-apps-for-mobile-devices.md) açın.
2. Rapordaki verilerin ait olduğu coğrafi konumlardan birindeyseniz konumunuza göre otomatik olarak filtrelenmesini sağlayabilirsiniz.
   
    ![Mobil uygulamada coğrafi filtre](media/desktop-mobile-geofiltering/power-bi-mobile-geo-map-set-filter.png)

[Power BI mobil uygulamalarında bir raporu konuma göre filtreleme](../consumer/mobile/mobile-apps-geographic-filtering.md) hakkında bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI Desktop'ta verileri kategorilere ayırma](desktop-data-categorization.md)  
* Sorular? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
