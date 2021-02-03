---
title: Mobil uygulamalarda barkod tarama filtrelemesini etkinleştirmek için Power BI Desktop barkod alanlarını etiketleme
description: Modelinizde Power BI Desktop bir barkod alanını etiketlediğinizde, mobil uygulama kullanıcıları iOS ve Android telefonlarında ve tabletlerinde filtrelenmiş verileri almak için barkodları tarayabilir.
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: pbi-transform-model
ms.topic: how-to
ms.date: 01/20/2021
LocalizationGroup: Model your data
ms.openlocfilehash: 4674347d3acd6520d7d156a7d1634a13df611afe
ms.sourcegitcommit: f7330dabb9cd8bce90bb2efec3e3273a11578f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99494431"
---
# <a name="tag-barcode-fields-in-power-bi-desktop-to-enable-barcode-scan-filtering-in-the-mobile-apps"></a>Mobil uygulamalarda barkod tarama filtrelemesini etkinleştirmek için Power BI Desktop barkod alanlarını etiketleme

Power BI Desktop'ta bir sütundaki [verileri kategorilere ayırarak](desktop-data-categorization.md) Power BI Desktop uygulamasının rapordaki görselde bulunan değerleri nasıl işlemesi gerektiğini belirleyebilirsiniz. Sütun kategorisini **Barkod** olarak da belirleyebilirsiniz. Daha sonra, şirketinizdeki veya kurumunuzdaki bir kişi, iOS veya Android telefonlarındaki veya tabletindeki Power BI mobil uygulamayı kullanarak [bir üründe barkod taradığında](../consumer/mobile/mobile-apps-scan-barcode-iphone.md) , söz konusu barkodu içeren herhangi bir rapor görür. Raporu açtıklarında bu barkod ile ilgili verilere otomatik olarak filtre uygulanır.

## <a name="categorize-barcode-data"></a>Barkod verilerini kategorilere ayır

Barkodları içeren bir raporunuz olduğunu varsayarsak: 

1. Power BI Desktop ' de, veri görünümü ' ne geçin.
2. Barkod verilerinin bulunduğu sütunu seçin. [Desteklenen barkod biçimleri](#supported-barcode-formats) listesi için aşağıya bakın.
3. **Sütun araçları** sekmesinde **veri kategorisi**  >  **barkodu**' nı seçin.
   
    ![Veri kategorisi listesi](media/desktop-mobile-barcodes/power-bi-desktop-barcode.png)

    >[!WARNING]
    >Bir rapordaki tüm veri tablolarında **barkod** olarak birden fazla sütun sınıflandırmayın. Mobil uygulamalar yalnızca tüm rapor verileri tablolarında yalnızca bir barkod sütunu olan raporlar için barkod filtrelemeyi destekler. Raporda birden fazla barkod sütunu varsa, filtreleme yapılmaz.

4. Rapor Görünümü ' nde barkod alanını, barkod tarafından filtrelenmesini istediğiniz görsellere ekleyin.
5. Raporu kaydedin ve Power BI hizmetinde yayımlayın.

Artık tarayıcıyı iOS ve Android telefonlar ve tabletlere yönelik Power BI uygulamalarda açıp bir barkod taradığınızda, bu raporu barkodlara sahip raporlar listesinde görürsünüz. Raporu açtığınızda, görselleri taradığınız ürün barkodu tarafından filtrelenecektir.

## <a name="supported-barcode-formats"></a>Desteklenen barkod biçimleri
Bunlar, bir Power BI raporunda etiketleyebiliyorsanız Power BI barkod biçimleridir: 

* UPCECode 
* Code39Code  
* A39Mod43Code 
* EAN13Code 
* EAN8Code  
* 93Code  
* 128Code 
* PDF417Code 
* Interleaved2of5Code 
* ITF14Code 

## <a name="next-steps"></a>Sonraki adımlar
* [İOS veya Android telefonunuzdaki veya tabletinizdeki Power BI uygulamasından barkod tarama](../consumer/mobile/mobile-apps-scan-barcode-iphone.md)
* [Tarama barkodları ile ilgili sorunlar](../consumer/mobile/mobile-apps-scan-barcode-iphone.md#issues-with-scanning-a-barcode)
* [Power BI Desktop'ta verileri kategorilere ayırma](desktop-data-categorization.md)  
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
