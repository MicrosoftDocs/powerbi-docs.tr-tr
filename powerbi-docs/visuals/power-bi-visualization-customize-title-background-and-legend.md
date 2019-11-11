---
title: Power BI görselleştirmelerini biçimlendirmeye başlama
description: Görselleştirme başlığını, arka planı ve açıklamayı özelleştirme
author: mihart
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 011e2b6d3bf5cc998f7db76e96536d2ddab09888
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880860"
---
# <a name="customize-visualization-titles-legends-and-backgrounds"></a>Görselleştirme başlıklarını, açıklamaları ve arka planları özelleştirme

Bu öğreticide, görselleştirmelerinizi özelleştirmek için izleyebileceğiniz birkaç farklı yol öğreneceksiniz. Görselleştirmelerinizi özelleştirmeye yönelik çok sayıda seçenek vardır. Bunların tümü hakkında bilgi edinmenin en iyi yolu **Biçimlendirme** bölmesi keşfetmektir (boya rulosu simgesini seçin). Başlamanıza yardımcı olmak için, bu makalede, bir görselleştirme başlığını, açıklamayı ve arka planı nasıl özelleştireceğiniz gösterilmektedir.

Tüm görselleştirmeler özelleştirilemez. Ayrıntılar için görselleştirmelerin [tam listesine](#visualization-types-that-you-can-customize) bakın.

Görselleştirmeleri özelleştirme konusunda bir örnek için videoda 4:50 noktasına ilerleyelim:

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

Şimdi, kendi verilerinizle denemek için aşağıda yer alan yönergeleri uygulayın.

## <a name="prerequisites"></a>Önkoşullar

- Power BI hizmeti veya Power BI Desktop

- Perakende Analizi Örneği raporu

## <a name="customize-visualization-titles-in-reports"></a>Raporlardaki görselleştirme başlıklarını özelleştirme

Örneği takip etmek için [Power BI hizmetinde](https://app.powerbi.com) oturum açın ve [Perakende Analizi Örneği](../sample-datasets.md) raporunu [Raporu düzenleme](../service-interact-with-a-report-in-editing-view.md) görünümünde açın.

> [!NOTE]
> Panolara sabitlediğiniz görselleştirmeler birer pano kutucuğu haline gelir. Kutucukları da [yeni başlıklar, alt başlıklar ve köprülerle özelleştirebilir veya yeniden boyutlandırabilirsiniz](../service-dashboard-edit-tile.md).

1. **Perakende Analizi Örneğinin** **Yeni Depolar** sayfasına gidin.

1. **Open Store Count by Open Month and Chain** kümelenmiş sütun grafiğini seçin.

1. **Görsel Öğeler** bölmesinde biçimlendirme seçeneklerini görüntülemek için boya rulosu simgesini seçin.

1. **Başlık** seçeneğini belirleyerek bu bölümü genişletin.

   ![Vurgulanan boya rulosu simgesini ve Başlık açılır menüsünü işaret eden bir ok işaretini gösteren Biçimlendirme bölmesi ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-formatting-menu.png)

1. **Başlık** kaydırıcısını **Açık** konumuna getirin.

   ![Açık kaydırıcının ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/onoffslider.png)

1. Başlığı değiştirmek için, **Başlık metni** alanına *Store count by month opened* yazın.

1. **Yazı tipi rengi**’ni turuncu, **Arka plan rengi**’ni ise sarı olarak değiştirin.

    1. Açılan menüyü seçin ve **Tema renkleri**, **Son kullanılan renkler** veya **Özel renk**’ten bir renk seçin.

        ![Yazı tipi rengi ve arka plan rengi seçenekleri.](media/power-bi-visualization-customize-title-background-and-legend/customizecolorpicker.png)

    1. Renk penceresini kapatmak için, açılan menüyü seçin.

       Yapmış olduğunuz değişiklikleri kaydedin.

       Tüm değişiklikleri geri almanız gerekirse, renk penceresinde **Varsayılana dön**’ü seçerek varsayılan renklere dönebilirsiniz.

1. Metin boyutunu **12 puntoya** yükseltin.

1. Grafik başlığı için gerçekleştireceğiniz son özelleştirme olarak, başlığı görselleştirmenin ortasına gelecek şekilde hizalayacaksınız.

    ![Merkez seçeneği işaretliyken Hizalama denetimlerinin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/customizealign.png)

Öğreticinin bu noktasında, kümelenmiş sütun grafiğinizin başlığı aşağıdaki gibi görünür:

![Yeni yapılandırılan kümelenmiş sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/tutorialprogress1.png)

Yaptığınız değişiklikleri kaydedin ve sonraki bölüme geçin.

Yaptığınız tüm değişiklikleri geri almanız gerekirse, **Başlık** özelleştirme bölmesinin altındaki **Varsayılana dön** seçeneğini belirleyin.

![Varsayılana dön seçeneğinin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/revertall.png)

## <a name="customize-visualization-backgrounds"></a>Görselleştirme arka planlarını özelleştirme

Aynı kümelenmiş sütun grafiği seçili durumdayken **Arka Plan** seçeneklerini genişletin.

1. **Arka plan** kaydırıcısını **Açık** konumuna getirin.

1. Açılır menüyü seçin ve bir gri tonu belirleyin.

1. **Saydamlık** ayarını **%74** olarak değiştirin.

Öğreticinin bu noktasında, kümelenmiş sütun grafiğinizin arka planı aşağıdaki gibi görünür:

![Güncelleştirilmiş arka plan rengiyle kümelenmiş sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-customize-background.png)

Yaptığınız değişiklikleri kaydedin ve sonraki bölüme geçin.

Yaptığınız tüm değişiklikleri geri almanız gerekirse, **Arka plan** özelleştirme bölmesinin altındaki **Varsayılana dön** seçeneğini belirleyin.

## <a name="customize-visualization-legends"></a>Görselleştirme açıklamalarını özelleştirme

1. **Genel bakış** adlı rapor sayfasını açın **Total Sales Variance by FiscalMonth and District Manager** grafiğini seçin.

1. **Görselleştirme** sekmesinde, Biçimlendirme bölmesini açmak için boya fırçası simgesini seçin.

1. **Gösterge** seçeneklerini genişletin:

      ![Gösterge seçeneğinin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/legend.png)

1. **Gösterge** kaydırıcısını **Açık** konumuna getirin.

1. Açıklamayı görselleştirmenin sol tarafına taşıyın.

1. **Başlık** seçeneğini **Açık** olarak ayarlayarak bir gösterge başlığı ekleyin.

1. **Gösterge adı** alanına *Yöneticiler* yazın.

Öğreticinin bu noktasında, kümelenmiş sütun grafiğinizin göstergesi aşağıdaki gibi görünür:

![Kümelenmiş sütun grafiğinde güncelleştirilmiş Göstergenin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/legend-move.png)

Yaptığınız değişiklikleri kaydedin ve sonraki bölüme geçin.

Yaptığınız tüm değişiklikleri geri almanız gerekirse, **Gösterge** özelleştirme bölmesinin altındaki **Varsayılana dön** seçeneğini belirleyin.

## <a name="visualization-types-that-you-can-customize"></a>Özelleştirebileceğiniz görselleştirme türleri

Görselleştirmelerin ve her biri için kullanılabilir özelleştirme seçeneklerinin bir listesi aşağıda verilmiştir:

| Görselleştirme | Başlık | Arka Plan | Gösterge |
|:--- |:--- |:--- |:--- |
| Alan | evet | evet |evet |
| Çubuk | evet | evet |evet |
| Kart | evet | evet |yok |
| Çok Satırlı Kart | evet | evet | yok |
| Sütun | evet | evet | evet |
| Birleşik | evet | evet | evet |
| Halka | evet | evet | evet |
| Kartogram | evet | evet | evet |
| Huni | evet | evet | yok |
| Ölçer | evet | evet | yok |
| KPI | evet | evet | yok |
| Çizgi | evet | evet | evet |
| Harita | evet | evet | evet |
| Matris | evet | evet | yok |
| Pasta | evet | evet | evet |
| Dağılım | evet | evet | evet |
| Dilimleyici | evet | evet | yok |
| Tablo | evet | evet | yok |
| Metin Kutusu | hayır | evet | yok |
| Treemap | evet | evet | evet |
| Şelale | evet | evet | evet |

## <a name="next-steps"></a>Sonraki adımlar

- [X Ekseni ve Y Ekseni özelliklerini özelleştirme](power-bi-visualization-customize-x-axis-and-y-axis.md)

- [Renk biçimlendirme ve eksen özelliklerini kullanmaya başlama](service-getting-started-with-color-formatting-and-axis-properties.md)

- [Power BI hizmeti müşterilerine yönelik temel kavramlar](../consumer/end-user-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
