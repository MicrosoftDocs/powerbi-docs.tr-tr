---
title: Sayfalandırılmış raporlar için rapor görünümlerini ayarlama - Power BI
description: Bu makalede Power BI hizmetindeki sayfalandırılmış raporlar için sağlanan farklı rapor görünümlerini öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: ''
ms.topic: conceptual
ms.date: 05/14/2020
ms.openlocfilehash: 3816cfe4e1b61b9445e16d7c322c5ba19aa2bc3d
ms.sourcegitcommit: 21b06e49056c2f69a363d3a19337374baa84c83f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83407944"
---
# <a name="set-report-views-for-paginated-reports-in-the-power-bi-service"></a>Power BI hizmetinde sayfalandırılmış raporlar için rapor görünümlerini ayarlama

Power BI hizmetinde sayfalandırılmış raporu işlerken, varsayılan görünüm HTML tabanlı ve etkileşimlidir. PDF gibi sabit sayfa biçimlerine yönelik bir diğer rapor görünümü de yeni Sayfa Görünümü seçeneğidir.

**Varsayılan etkileşimli görünüm**

![Varsayılan Görünüm](media/page-view/power-bi-paginated-default-view.png)

**Sayfa Görünümü**

![Sayfa Görünümü](media/page-view/power-bi-paginated-page-view.png)

Sayfa Görünümünde, işlenen rapor varsayılan görünümde olduğundan farklı görünür. Sayfalandırılmış raporlardaki bazı özellikler ve kavramlar yalnızca sabit sayfalara uygulanır. Görünüm, raporun yazdırılmış veya dışarı aktarılmış haline benzer. Parametre değerleri gibi bazı öğeleri yine değiştirebilirsiniz ama sütun sıralama ve geçişler gibi başka etkileşimli özellikleri yoktur.

Sayfa Görünümü Yakınlaştırma, Uzaklaştırma ve Sayfaya sığdırma gibi tarayıcının PDF Görüntüleyicisinin desteklediği tüm özellikleri destekler.

## <a name="switch-to-page-view"></a>Sayfa Görünümüne geçme

Sayfalandırılmış raporu açtığınızda varsayılan olarak etkileşimli görünümde işlenir. Raporun parametreleri varsa, parametreleri seçin ve ardından raporu görüntüleyin.

1. Araç çubuğunda **Görünüm** > **Sayfa Görünümü**’nü seçin.

    ![Sayfa Görünümüne geçme](media/page-view/power-bi-paginated-page-view-dropdown.png)

2. Araç çubuğundaki **Görünüm** menüsünde **Sayfa Ayarları**’nı seçerek sayfa görünümünün ayarlarını değiştirebilirsiniz. 

    ![Sayfa Ayarları’nı seçme](media/page-view/power-bi-paginated-page-settings-dropdown.png)
    
    **Sayfa Ayarları** iletişim kutusunda, Sayfa Görünümü için **Sayfa Boyutu** ve **Yönlendirme**’yi ayarlama seçenekleri vardır. Siz sayfa ayarlarını uyguladıktan sonra, aynı seçenekler daha sonra sayfayı yazdırdığınızda da geçerli olur.
   
    ![Sayfa Ayarları iletişim kutusu](media/page-view/power-bi-paginated-page-settings-dialog.png)

3. Etkileşimli görünümüne geri dönmek için **Görünüm** açılan kutusunda **Varsayılan**’ı seçin.

## <a name="browser-support"></a>Tarayıcı desteği

Sayfa Görümünü Google Chrome ve Microsoft Edge tarayıcılarında desteklenir. Tarayıcıda PDF görüntülemenin etkinleştirildiğinden emin olun. Söz konusu tarayıcılarda bu varsayılan ayardır.

Sayfa Görünümü Internet Explorer ve Safari’de desteklenmediğinden bu seçenek devre dışı bırakılmıştır. Ayrıca mobil cihazların tarayıcılarında veya yerel Power BI mobil uygulamalarında da desteklenmez.  


## <a name="next-steps"></a>Sonraki adımlar

- [Power BI hizmetinde sayfalandırılmış rapor görüntüleme](../consumer/paginated-reports-view-power-bi-service.md)
- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
