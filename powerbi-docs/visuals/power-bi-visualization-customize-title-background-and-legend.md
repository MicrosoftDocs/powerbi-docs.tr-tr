---
title: Power BI görselleştirmelerini biçimlendirmeye başlama
description: Görselleştirme başlıklarını, arka planlarını, etiketlerini ve göstergelerini özelleştirme
author: mihart
ms.author: mihart
ms.reviewer: mihart
featuredvideoid: removed
ms.custom: video-OgjX-pFGgfM, video-RE4IY3L
ms.service: powerbi
ms.subservice: pbi-visuals
ms.topic: how-to
ms.date: 1/13/2021
LocalizationGroup: Visualizations
ms.openlocfilehash: b285d699d71001d8015615fdeb3652ba35274896
ms.sourcegitcommit: 396633fc5f7cff1f7d518f558b20043b2e05a513
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98191850"
---
# <a name="customize-visualization-titles-backgrounds-labels-and-legends"></a>Görselleştirme başlıklarını, arka planlarını, etiketlerini ve göstergelerini özelleştirme

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]    


Bu öğreticide, görselleştirmelerinizi özelleştirmek için izleyebileceğiniz birkaç farklı yol öğreneceksiniz. Görselleştirmelerinizi özelleştirmeye yönelik çok sayıda seçenek vardır. Bunların tümü hakkında bilgi edinmenin en iyi yolu **Biçimlendirme** bölmesi keşfetmektir (boya rulosu simgesini seçin). Başlamanıza yardımcı olmak için bu makalede görselleştirme başlığını, göstergesini, arka planını, etiketini, katmanını özelleştirme ve tema ekleme işlemleri gösterilir.

Tüm görselleştirmeler özelleştirilemez. Ayrıntılar için görselleştirmelerin [tam listesine](#visualization-types-that-you-can-customize) bakın.


## <a name="prerequisites"></a>Önkoşullar

- Power BI hizmeti veya Power BI Desktop

- Perakende Analizi Örneği raporu

> [!NOTE]
> Raporunuzu bir Power BI iş arkadaşınızla paylaşmak için her ikinizin de bireysel Power BI Pro lisanslarınızın olması veya raporun Premium kapasitede depolanması gerekir. Bkz. [Raporları paylaşma](../collaborate-share/service-share-reports.md).

## <a name="customize-visualization-titles-in-reports"></a>Raporlardaki görselleştirme başlıklarını özelleştirme

Birlikte ilerleyebilmek için Power BI Desktop'ta oturum açın ve [Perakende Analizi Örneği](../create-reports/sample-datasets.md) raporunu açın.

> [!NOTE]
> Panolara sabitlediğiniz görselleştirmeler birer pano kutucuğu haline gelir. Kutucukları da [yeni başlıklar, alt başlıklar ve köprülerle özelleştirebilir veya yeniden boyutlandırabilirsiniz](../create-reports/service-dashboard-edit-tile.md).

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
    
    ![Yazı tipi rengi ve arka plan rengi seçenekleri.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-color.png)

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

## <a name="customize-total-labels-for-stacked-visuals"></a>Yığılmış görseller için toplam etiketlerini özelleştirme
Yığılmış görseller veri etiketlerini ve toplam etiketlerini görüntüleyebilir. Yığılmış sütun grafiğinde veri etiketleri sütunun her bölümü için değeri tanımlar. Toplam etiketleri sütunun tamamı için toplam değeri görüntüler. 

Rien'in yığılmış grafiğe toplam etiketlerini eklemesini izleyin ve ardından aşağıdaki adımları izleyerek bu işlemi kendiniz deneyin.

> [!VIDEO https://www.youtube.com/embed/OgjX-pFGgfM]

1. **Genel bakış** rapor sayfasını açın ve **Zincir ve mağaza türüne göre ortalama satış alanı** çubuk grafiğini seçin.

1. **Görselleştirme** sekmesinde ![yığılmış çubuk grafik simgesini](media/power-bi-visualization-customize-title-background-and-legend/power-bi-stacked-bar.png) seçerek bu çubuk grafiği yığılmış çubuk grafiğe dönüştürün. Görselin veri etiketlerini koruduğuna dikkat edin. 

    ![Yeni yığılmış çubuk grafiğin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-stacked-chart.png)

1. **Görselleştirme** sekmesinde, Biçimlendirme bölmesini açmak için boya fırçası simgesini seçin.

1. **Toplam etiketleri** kaydırıcısını **Açık** konumuna getirin. 

    ![Toplam etiketi kaydırıcısının Açık olarak ayarlandığını gösteren ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-totals.png)

1. İsteğe bağlı olarak toplam etiketlerini biçimlendirin. Bu örnekte rengini siyah olarak değiştirdik, yazı tipi boyutunu artırdık ve değerleri **Binler** olarak görüntülemeyi kabul ettik.

    ![Toplam etiketlerini içeren yeni yığılmış çubuk grafiğin ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-bar-totals.png)


## <a name="customize-layer-order"></a>Katman sırasını özelleştirme
Raporlarınızda bulunan görsellerin ve şekillerin katman sırasını değiştirin. Katman sırası, seçildiğinde öne getirilecek olan nesneleri belirler. Rapor tuvalinde bir nesneyi seçtiğinizde bu nesne etkin hale gelir ve en üst katmana taşınır. Bu özellik seçilen görsellerle etkileşim kurmayı kolaylaştırır. Ancak şekiller ve arka planları en alt katmana sabitlemek isteyebilirsiniz. Bu sayede yanlışlıkla seçip rapor görsellerinizin üzerini kapatma olasılığını ortadan kaldırmış olursunuz. 

Katman denetimleri Power BI hizmeti, Power BI Desktop, mobil ve Rapor Sunucusu ile kullanılabilir. Bu makalede Power BI hizmetindeki katman sıralaması davranışını değiştirme adımları gösterilmiştir.

Rien'in katman davranışını değiştirmesini izleyin ve ardından aşağıdaki adımları izleyerek bu işlemi kendiniz deneyin.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4IY3L]

1. Sarı artı simgesini seçerek yeni bir rapor sayfası ekleyin. 

1. Tuvale bir şekil ekleyin. Burada mavi bir dikdörtgen ekledik. 

    ![Mavi dikdörtgenin bulunduğu yeni rapor sayfasının ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-shape.png)

1. Raporun başka bir sayfasında bulunan görsellerden birini kopyalayıp yapıştırın. 

    ![Mavi dikdörtgenin ve pasta grafiğinin bulunduğu yeni rapor sayfasının ekran görüntüsü.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-layer.png)

    Artık 2 katmanınız var. Önce pasta grafiğini, ardından da arka planı seçmeyi deneyin. Pasta grafiğini seçtiğinizde Power BI nesneyi etkin hale getirir ve üst bilgi menüsünü görüntüler. Dikdörtgeni seçtiğinizde Power BI nesneyi etkin hale getirir ve öne getirerek pasta grafiğinin arkada kalmasına neden olur. Bu varsayılan davranışı değiştirebilirsiniz.

1. Dikdörtgeni seçin ve Biçimlendirme bölmesini açın. **Genel** bölümünü genişletip **Katman sırasını koruyun** iki durumlu düğmesini bulun. Raporda yaptığınız değişiklikleri kaydedin ve Okuma görünümüne geçin.

    ![Yeni rapor sayfasının ekran görüntüsü; Katman sırasını koruyun seçeneği Açık olarak ayarlanmış.](media/power-bi-visualization-customize-title-background-and-legend/power-bi-maintain-layer.png)

1. Okuma görünümünde mavi dikdörtgeni seçtiğinizde arka katmanında kalır.


## <a name="customize-colors-using-a-theme"></a>Tema kullanarak renkleri özelleştirme

Rapor temalarıyla raporunuzun tamamında kurumsal renkler kullanmak, simge kümelerini değiştirmek veya yeni varsayılan görsel biçimlendirmeyi uygulamak gibi tasarım değişiklikleri uygulayabilirsiniz. Rapor teması uyguladığınızda, raporunuzdaki tüm görsellerde seçtiğiniz temanın renkleri ve biçimlendirmesi kullanılır.

Raporunuza tema uygulamak için menü çubuğundan **Temayı değiştir**'i seçin. Tema seçin.  Aşağıdaki raporda **Güneş** teması kullanılmıştır.

 
![Sarılar, turuncular ve kırmızılar içeren Güneş temasının kullanıldığı rapor](media/power-bi-visualization-customize-title-background-and-legend/power-bi-theme.png)

## <a name="visualization-types-that-you-can-customize"></a>Özelleştirebileceğiniz görselleştirme türleri

Görselleştirmelerin ve her biri için kullanılabilir özelleştirme seçeneklerinin bir listesi aşağıda verilmiştir:

| Görselleştirme | Başlık | Arka Plan | Gösterge | Toplam etiketleri
|:--- |:--- |:--- |:--- |:--- |
| Alan | evet | evet |evet | evet  |
| Çubuk | evet | evet |evet | evet |
| Kart | evet | evet |yok | yok |
| Çok Satırlı Kart | evet | evet | yok | yok |
| Sütun | evet | evet | evet |  evet |
| Birleşik | evet | evet | evet | evet |
| Halka | evet | evet | evet | yok |
| Kartogram | evet | evet | evet |yok |
| Huni | evet | evet | yok |yok |
| Ölçer | evet | evet | yok |yok |
| Ana Etmen | evet | evet | yok |yok |
| KPI | evet | evet | yok |yok |
| Çizgi | evet | evet | evet |yok |
| Harita | evet | evet | evet |yok |
| Matris | evet | evet | yok |evet |
| Pasta | evet | evet | evet |yok |
| Soru-Cevap | evet | evet | yok |yok |
| Dağılım | evet | evet | evet |yok |
| Şekil | evet | evet | evet |yok |
| Dilimleyici | evet | evet | yok |yok |
| Tablo | evet | evet | yok |evet |
| Metin Kutusu | hayır | evet | yok |yok |
| Treemap | evet | evet | evet |yok |
| Şelale | evet | evet | evet |yok |

## <a name="next-steps"></a>Sonraki adımlar

- [X Ekseni ve Y Ekseni özelliklerini özelleştirme](power-bi-visualization-customize-x-axis-and-y-axis.md)

- [Renk biçimlendirme ve eksen özelliklerini kullanmaya başlama](service-getting-started-with-color-formatting-and-axis-properties.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)


