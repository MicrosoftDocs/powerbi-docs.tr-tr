---
title: Power BI görselleştirmelerini biçimlendirmeye başlama
description: Görselleştirme başlığını, arka planı ve açıklamayı özelleştirme
author: mihart
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/04/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 1e2465273368c6b76e602e5ffbdf4ec3a1d121a3
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75757845"
---
# <a name="customize-visualization-titles-backgrounds-and-legends"></a>Görselleştirme başlıklarını, arka planlarını ve göstergelerini özelleştirme

Bu öğreticide, görselleştirmelerinizi özelleştirmek için izleyebileceğiniz birkaç farklı yol öğreneceksiniz. Görselleştirmelerinizi özelleştirmeye yönelik çok sayıda seçenek vardır. Bunların tümü hakkında bilgi edinmenin en iyi yolu **Biçimlendirme** bölmesi keşfetmektir (boya rulosu simgesini seçin). Başlamanıza yardımcı olmak için bu makalede görselleştirme başlığını, göstergesini, arka planını özelleştirme ve tema ekleme işlemleri gösterilir.

Tüm görselleştirmeler özelleştirilemez. Ayrıntılar için görselleştirmelerin [tam listesine](#visualization-types-that-you-can-customize) bakın.


## <a name="prerequisites"></a>Önkoşullar

- Power BI hizmeti veya Power BI Desktop

- Perakende Analizi Örneği raporu

## <a name="customize-visualization-titles-in-reports"></a>Raporlardaki görselleştirme başlıklarını özelleştirme

Birlikte ilerleyebilmek için Power BI Desktop'ta oturum açın ve [Perakende Analizi Örneği](../sample-datasets.md) raporunu açın.

> [!NOTE]
> Panolara sabitlediğiniz görselleştirmeler birer pano kutucuğu haline gelir. Kutucukları da [yeni başlıklar, alt başlıklar ve köprülerle özelleştirebilir veya yeniden boyutlandırabilirsiniz](../service-dashboard-edit-tile.md).

1. **Perakende Analizi Örneğinin** **Yeni Depolar** sayfasına gidin.

1. **Open Store Count by Open Month and Chain** kümelenmiş sütun grafiğini seçin.

1. **Görsel Öğeler** bölmesinde biçimlendirme seçeneklerini görüntülemek için boya rulosu simgesini seçin.

1. **Başlık** seçeneğini belirleyerek bu bölümü genişletin.

   ![Vurgulanan boya rulosu simgesini ve Başlık açılır menüsünü işaret eden bir ok işaretini gösteren Biçimlendirme bölmesi ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-format-menu.png)

1. **Başlık** kaydırıcısını **Açık** konumuna getirin.

1. Başlığı değiştirmek için, **Başlık metni** alanına *Store count by month opened* yazın.

    ![Başlık metninin girildiği Biçim bölmesinin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-title.png)

1. **Yazı tipi rengi**’ni beyaz, **Arka plan rengi**’ni ise mavi olarak değiştirin.    

    a. Açılan menüyü seçin ve **Tema renkleri**, **Son kullanılan renkler** veya **Özel renk**’ten bir renk seçin.

        ![Screenshot of the Font color and Background color options.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-color.png)

    b. Renk penceresini kapatmak için, açılan menüyü seçin.


1. Metin boyutunu **16 puntoya** yükseltin.

1. Grafik başlığı için gerçekleştireceğiniz son özelleştirme olarak, başlığı görselleştirmenin ortasına gelecek şekilde hizalayacaksınız.

    ![Merkez seçeneği işaretliyken Hizalama denetimlerinin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-align.png)

    Öğreticinin bu noktasında, kümelenmiş sütun grafiğinizin başlığı aşağıdaki gibi görünür:

    ![Yeni yapılandırılan kümelenmiş sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-table.png)

Yaptığınız değişiklikleri kaydedin ve sonraki bölüme geçin.

Yaptığınız tüm değişiklikleri geri almanız gerekirse, **Başlık** özelleştirme bölmesinin altındaki **Varsayılana dön** seçeneğini belirleyin.

![Varsayılana dön seçeneğinin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-revert.png)

## <a name="customize-visualization-backgrounds"></a>Görselleştirme arka planlarını özelleştirme

Aynı kümelenmiş sütun grafiği seçili durumdayken **Arka Plan** seçeneklerini genişletin.

1. **Arka plan** kaydırıcısını **Açık** konumuna getirin.

1. Açılır menüyü seçin ve bir gri tonu belirleyin.

1. **Saydamlık** ayarını **%74** olarak değiştirin.

Öğreticinin bu noktasında, kümelenmiş sütun grafiğinizin arka planı aşağıdaki gibi görünür:

![Güncelleştirilmiş arka plan rengiyle kümelenmiş sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-background.png)

Yaptığınız değişiklikleri kaydedin ve sonraki bölüme geçin.

Yaptığınız tüm değişiklikleri geri almanız gerekirse, **Arka plan** özelleştirme bölmesinin altındaki **Varsayılana dön** seçeneğini belirleyin.

## <a name="customize-visualization-legends"></a>Görselleştirme açıklamalarını özelleştirme

1. **Genel bakış** adlı rapor sayfasını açın **Total Sales Variance by FiscalMonth and District Manager** grafiğini seçin.

1. **Görselleştirme** sekmesinde, Biçimlendirme bölmesini açmak için boya fırçası simgesini seçin.

1. **Gösterge** seçeneklerini genişletin:

    ![Gösterge kartının ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-legends.png)

1. **Gösterge** kaydırıcısını **Açık** konumuna getirin.

1. Açıklamayı görselleştirmenin sol tarafına taşıyın.

1. **Başlık** seçeneğini **Açık** olarak ayarlayarak bir gösterge başlığı ekleyin.

1. **Gösterge adı** alanına *Yönetici* yazın.

1. **Renk** değerini siyah olarak değiştirin.

Yaptığınız değişiklikleri kaydedin ve sonraki bölüme geçin.

Yaptığınız tüm değişiklikleri geri almanız gerekirse, **Gösterge** özelleştirme bölmesinin altındaki **Varsayılana dön** seçeneğini belirleyin.

## <a name="customize-colors-using-a-theme"></a>Tema kullanarak renkleri özelleştirme

Rapor temalarıyla raporunuzun tamamında kurumsal renkler kullanmak, simge kümelerini değiştirmek veya yeni varsayılan görsel biçimlendirmeyi uygulamak gibi tasarım değişiklikleri uygulayabilirsiniz. Rapor teması uyguladığınızda, raporunuzdaki tüm görsellerde seçtiğiniz temanın renkleri ve biçimlendirmesi kullanılır.

Raporunuza tema uygulamak için menü çubuğundan **Temayı değiştir**'i seçin. Tema seçin.  Aşağıdaki raporda **Güneş** teması kullanılmıştır.

 
![Sarılar, turuncular ve kırmızılar içeren Güneş temasının kullanıldığı rapor](media/power-bi-visualization-customize-title-background-and-legend/power-bi-theme.png)

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
| Ana Etmen | evet | evet | yok |
| KPI | evet | evet | yok |
| Çizgi | evet | evet | evet |
| Harita | evet | evet | evet |
| Matris | evet | evet | yok |
| Pasta | evet | evet | evet |
| Soru-Cevap | evet | evet | yok |
| Dağılım | evet | evet | evet |
| Şekil | evet | evet | evet |
| Dilimleyici | evet | evet | yok |
| Tablo | evet | evet | yok |
| Metin Kutusu | hayır | evet | yok |
| Treemap | evet | evet | evet |
| Şelale | evet | evet | evet |

## <a name="next-steps"></a>Sonraki adımlar

- [X Ekseni ve Y Ekseni özelliklerini özelleştirme](power-bi-visualization-customize-x-axis-and-y-axis.md)

- [Renk biçimlendirme ve eksen özelliklerini kullanmaya başlama](service-getting-started-with-color-formatting-and-axis-properties.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
