---
title: Power BI raporlarında sayfa görüntüleme ayarları
description: Rapor sayfa görüntüleme ayarları ve sayfa görünüm ayarları
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 05/29/2019
LocalizationGroup: Reports
ms.openlocfilehash: 9452a4a6340480bcb6c8b646c16125fe73f68235
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96393497"
---
# <a name="apply-page-display-settings-in-a-power-bi-report"></a>Power BI raporuna sayfa görüntüleme ayarlarını uygulama
Rapor düzeninizin kusursuz görünmesinin sizin için çok önemli olduğunu anlıyoruz. Siz ve iş arkadaşlarınız bu raporları farklı en boy oranlarına ve boyutlara sahip ekranlarda görüntülediğiniz için, bu bazen güç olabilir. 

Varsayılan ekran görünümü **Sayfaya sığdır**, varsayılan görüntüleme boyutu ise **16:9** şeklindedir. Farklı bir en boy oranı kullanmak veya raporunuzu farklı şekilde sığdırmak istiyorsanız şu iki araçtan faydalanabilirsiniz: **_Sayfa görünümü_* _ ayarları ve _*_Sayfa boyutu_*_ ayarları.


<iframe width="560" height="315" src="https://www.youtube.com/embed/5tg-OXzxe2g" frameborder="0" allowfullscreen></iframe>


## <a name="where-to-find-page-view-settings-in-the-power-bi-service-and-power-bi-desktop"></a>Power BI hizmetinde ve Power BI Desktop'ta Sayfa görünümü ayarlarının yeri
Sayfa görünümü ayarları hem Power BI hizmetinde hem de Power BI Desktop'ta bulunmaktadır ancak arabirimi biraz farklıdır. Aşağıdaki bölümde, her Power BI aracında Görünüm ayarlarını nerede bulabileceğiniz açıklanmaktadır.

### <a name="in-power-bi-desktop"></a>Power BI Desktop'ta
Rapor görünümü'nde Sayfa görünümü ayarlarını ve telefon düzeni ayarlarını açmak için _ *Görünüm** sekmesini seçin.

  ![Masaüstü sayfa görünümü ayarları](media/power-bi-report-display-settings/power-bi-desktop-view-settings.png)

### <a name="in-the-power-bi-service-apppowerbicom"></a>Power BI hizmetinde (app.powerbi.com)
Power BI hizmetinde, bir rapor açın ve sol üst menü çubuğundan **Görünüm**'ü seçin.

![hizmet sayfası görünümü ayarları](media/power-bi-report-display-settings/power-bi-change-page-view.png)

Sayfa görünümü ayarları, [Okuma görünümü ve Düzenleme görünümü](../consumer/end-user-reading-view.md)'nde bulunmaktadır. Düzenleme görünümünde, rapor sahibi bireysel rapor sayfalarına sayfa görünümü ayarları atayabilir ve bu ayarlar raporla birlikte kaydedilir. İş arkadaşlarınızdan biri söz konusu raporu Okuma görünümü'nde açtığında, rapor sayfalarını rapor sahibinin ayarlarını kullanarak görüntüler. İş arkadaşlarınız Okuma görünümünde *bazı* **Sayfa görünümü** ayarlarını değiştirebilir ancak bu değişiklikler rapordan çıktıklarında kaydedilmez.

## <a name="page-view-settings"></a>Sayfa görünümü ayarları
Birinci Sayfa görünümü ayarları kümesi, rapor sayfanızın tarayıcı penceresiyle ilgili görüntülenmesini denetler. Şunlardan birini seçin:

* **Sayfaya sığdır** (varsayılan): İçerikler sayfaya en iyi sığacak şekilde ölçeklendirilir
* **Genişliğe uydur**: İçerikler sayfanın genişliğine sığacak şekilde ölçeklendirilir
* **Gerçek boyut**: İçerikler tam boyutta görüntülenir

İkinci Sayfa görünümü ayarları kümesi, rapor tuvalindeki nesnelerin konumlandırılmasını denetler. Şunlardan birini seçin:

* **Kılavuz çizgilerini göster**: Rapor tuvali üzerindeki nesneleri konumlandırmanıza yardımcı olması için kılavuz çizgilerini açın.
* **Kılavuza yasla**: Rapor tuvalindeki nesneleri tam olarak konumlandırmak ve hizalamak için **Kılavuz çizgilerini göster** seçeneğiyle birlikte kullanın. 
* **Nesneleri kilitle**: Taşınamamaları veya yeniden boyutlandırılmamaları için tuvaldeki tüm nesneleri kilitleyin.
* **Seçim bölmesi**: **Seçim** bölmesi, tuvaldeki tüm nesneleri listeler. Hangisinin gösterileceğine, hangisinin gizleneceğine karar verebilirsiniz.

    ![seçim bölmesi](media/power-bi-report-display-settings/power-bi-selection-pane.png)



## <a name="page-size-settings"></a>Sayfa boyutu ayarları
![sayfa boyutu ayarlarını değiştirme](media/power-bi-report-display-settings/power-bi-page-size.png)

**Sayfa boyutu** ayarları yalnızca rapor sahipleri tarafından kullanılabilir. Bu, Power BI hizmetinde (app.powerbi.com) raporun [Düzenleme görünümü](../consumer/end-user-reading-view.md)'nde açabileceği anlamına gelmektedir. **Sayfa boyutu** ayarları **Görsel öğeler** bölmesindedir ve rapor tuvalinin görüntü birimi oranı ile gerçek boyutunu (piksel olarak) denetler:   

* 4:3 oranı
* 16:9 oranı (varsayılan)
* Letter
* Özel (piksel cinsinden yükseklik ve genişlik)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Desktop'ta rapor görünümü](desktop-report-view.md)

[Sahip olduğunuz Power BI raporlarında Sayfa görünümü ve Sayfa boyutu ayarlarını değiştirme](../consumer/end-user-report-view.md)

[Power BI'daki raporlar](../consumer/end-user-reports.md) hakkında daha fazla bilgi edinin

[Power BI hizmetinde tasarımcılara yönelik temel kavramlar](../fundamentals/service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
