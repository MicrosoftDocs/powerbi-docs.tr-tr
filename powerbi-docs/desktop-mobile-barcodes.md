---
title: Mobil uygulamalar için Power BI Desktop'taki bir barkod alanını etiketleme
description: Power BI Desktop'taki modelinizde bir barkod alanını etiketlediğinizde iPhone'unuzdaki Power BI uygulamasında verileri otomatik olarak barkoda göre filtreleyebilirsiniz.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 01/16/2018
ms.author: maggies
LocalizationGroup: Model your data
ms.openlocfilehash: ae6c7ba3603136aeea3daa412595b9f42ed13d6a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34286923"
---
# <a name="tag-barcodes-in-power-bi-desktop-for-the-mobile-apps"></a>Mobil uygulamalar için Power BI Desktop'taki barkodları etiketleme
Power BI Desktop'ta bir sütundaki [verileri kategorilere ayırarak](desktop-data-categorization.md) Power BI Desktop uygulamasının rapordaki görselde bulunan değerleri nasıl işlemesi gerektiğini belirleyebilirsiniz. Sütun kategorisini **Barkod** olarak da belirleyebilirsiniz. Siz veya iş arkadaşlarınız iPhone'da [Power BI uygulamasıyla bir ürün üzerindeki barkodu taradığınızda](mobile-apps-scan-barcode-iphone.md) ilgili barkodu içeren raporu görebilirsiniz. İlgili raporu mobil uygulamada açtığınızda, Power BI raporda taradığınız barkodla ilgili verileri otomatik olarak filtreler.

1. Power BI Desktop'ta Veri Görünümüne geçin.
2. Barkod verilerini içeren sütunu seçin. [Desteklenen barkod biçimleri](#supported-barcode-formats) listesi için aşağıya bakın.
3. **Modelleme** sekmesinde, **Veri Kategorisi** > **Barkod**'u seçin.
   
    ![Veri kategorisi listesi](media/desktop-mobile-barcodes/power-bi-desktop-barcode.png)
4. Rapor Görünümünde barkoda göre filtrelenmesini istediğiniz görsellere bu alanı ekleyin.
5. Raporu kaydedin ve Power BI hizmetinde yayımlayın.

Artık [iPhone için Power BI uygulamasında](mobile-ios-ipad-iphone-apps.md) tarayıcıyı açıp bir barkod taradığınızda rapor listesinde bu raporu görürsünüz. Raporu açtığınızda, görselleri, taradığınız ürün barkoduna göre filtrelenmiş şekilde görüntülenir.

## <a name="supported-barcode-formats"></a>Desteklenen barkod biçimleri
Power BI raporunda etiketlemeniz durumunda Power BI'ın tanıyacağı barkodlar şunlardır: 

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
* [iPhone'unuzdaki Power BI uygulamasından barkod tarama](mobile-apps-scan-barcode-iphone.md)
* [iPhone'da barkod taramayla ilgili sorunlar](mobile-apps-scan-barcode-iphone.md#issues-with-scanning-a-barcode)
* [Power BI Desktop'ta verileri kategorilere ayırma](desktop-data-categorization.md)  
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

