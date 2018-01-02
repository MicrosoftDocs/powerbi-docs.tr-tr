---
title: "Power BI görselleştirmelerini biçimlendirmeye başlama (Eğitim)"
description: "Eğitim: Görselleştirme başlığını, arka planı ve açıklamayı özelleştirme"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
featuredvideoid: IkJda4O7oGs
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: 424e96c5315bd41fc79999555097602f629a1285
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="customize-visualization-titles-legends-and-backgrounds-tutorial"></a>Görselleştirme başlıklarını, açıklamaları ve arka planları özelleştirme (Eğitim)
Bu eğitimde, görselleştirmelerinizi özelleştirmek için izleyebileceğiniz birkaç farklı yol öğreneceksiniz.   Görselleştirmelerinizi özelleştirmeye yönelik pek çok seçenek vardır. Bunların tümü hakkında bilgi edinmenin en iyi yolu, Biçimlendirme bölmesini keşfetmektir (boya rulosu simgesini seçerek).  Başlamanıza yardımcı olmak için, bu makalede, bir görselleştirme başlığını, açıklamayı ve arka planı nasıl özelleştireceğiniz gösterilmektedir.  

Her görselleştirme özelleştirilebilir değildir, [özelleştirilebilir görselleştirmelerin tam listesine bakın](#list).  

Amanda raporundaki görselleştirmeleri özelleştirirken ona eşlik edin. (Videoyu ileri sararak 4:50'ye atlayın.) Ardından, kendi verilerinizle denemek için videonun altında yer alan yönergeleri uygulayın.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>


## <a name="customize-visualization-titles-in-reports"></a>Raporlardaki görselleştirme başlıklarını özelleştirme
Birlikte ilerleyebilmek için, app.powerbi sayfasında oturum açın ve [Perakende Analizi Örneği](sample-datasets.md) raporunu [Düzenleme Görünümü](service-interact-with-a-report-in-editing-view.md)'nde açın.

> [!NOTE]
> Panolara sabitlediğiniz görselleştirmeler birer pano kutucuğu haline gelir.  Kutucuklar da [yeni başlıklar, alt başlıklar ve köprülerle özelleştirilebilir veya yeniden boyutlandırılabilir](service-dashboard-edit-tile.md).
> 
> 

1. Raporun "New Stores" sayfasına gidin ve "Open Month ve Chain tarafından düzenlenen Open Store Count" sütun grafiğini seçin.
2. Görsel Öğeler bölmesinde, biçimlendirme seçeneklerini görüntülemek için boya rulosu simgesini seçin.  Ardından **Başlık** seçeneğini belirleyerek bu bölümü genişletin.  
   
   ![](media/power-bi-visualization-customize-title-background-and-legend/power-bi-formatting-menu.png)
3. Açık (veya Kapalı) kaydırıcısını seçerek **Başlık**'ı etkinleştirebilir ve devre dışı bırakabilirsiniz. Şimdilik **Açık** durumunda bırakın.  
   
   ![](media/power-bi-visualization-customize-title-background-and-legend/onoffslider.png)
4. Metin alanına **Store count by month opened** yazarak **Başlık Metni**'ni değiştirin.  
5. **Yazı tipi rengi**'ni turuncu, **Arka Plan Rengi**'ni ise sarı olarak değiştirin.
   
   * Açılan menüyü seçin ve **Tema Renkleri**, **Son Kullanılan Renkler** veya **Özel renk**'ten bir renk seçin.
   * Renk penceresini kapatmak için, açılan menüyü seçin.  
     ![](media/power-bi-visualization-customize-title-background-and-legend/customizecolorpicker.png)
   
   Renk penceresindeki **Varsayılana geri dön** seçeneğini belirleyerek dilediğiniz zaman varsayılan renklere dönebilirsiniz.
6. Metin boyutunu 12'ye yükseltin.
7. Grafik başlığı için gerçekleştireceğimiz son özelleştirme olarak, başlığı görselleştirmenin ortasına gelecek şekilde hizalayacağız. Başlık konumu varsayılan olarak sola hizalıdır.  
   ![](media/power-bi-visualization-customize-title-background-and-legend/customizealign.png)
   
    Eğitimin bu noktasında, sütun grafiğinizin **başlığının** aşağıdaki gibi görünmesi gerekir:  
    ![](media/power-bi-visualization-customize-title-background-and-legend/tutorialprogress1.png)
   
    Bu ana kadar gerçekleştirdiğimiz tüm başlık özelleştirmelerini geri almak için, **Başlık** özelleştirme bölmesinin altında bulunan **Varsayılana Geri Dön** seçeneğini belirleyin.  
    ![](media/power-bi-visualization-customize-title-background-and-legend/revertall.png)

## <a name="customize-visualization-backgrounds"></a>Görselleştirme arka planlarını özelleştirme
Aynı sütun grafiği seçili durumdayken Arka Plan seçeneklerini genişletin.

1. Açık (veya Kapalı) kaydırıcısını seçerek arka planı etkinleştirebilir ya da devre dışı bırakabilirsiniz. Şimdilik **Açık** durumunda bırakın.
2. Arka plan rengini %74 gri olarak değiştirin.
   
   * Açılan menüyü seçin ve **Tema Renkleri**, **Son Kullanılan Renkler** veya **Özel renk**'ten bir gri tonu belirleyin.
   * Saydamlık ayarını %74 olarak değiştirin.   
     ![](media/power-bi-visualization-customize-title-background-and-legend/power-bi-customize-background.png)
   
   Bu ana kadar gerçekleştirdiğimiz tüm özelleştirmeleri geri almak için **Arka Plan** özelleştirme bölmesinin altında bulunan **Varsayılana Geri Dön** seçeneğini belirleyin.

## <a name="customize-visualization-legends"></a>Görselleştirme açıklamalarını özelleştirme
1. **Overview** adlı rapor sayfasını açın "FiscalMonth ve District Manager tarafından düzenlenen Total Sales Variance" grafiğini seçin.
2. Görsel Öğeler sekmesinde, biçimlendirme bölmesini açmak için boya fırçası simgesini seçin.  
3. **Açıklama** seçeneklerini genişletin.
   
      ![](media/power-bi-visualization-customize-title-background-and-legend/legend.png)
4. Açık (veya Kapalı) kaydırıcısını seçerek açıklamayı etkinleştirin ya da devre dışı bırakın. Şimdilik **Açık** durumunda bırakın.
5. Açıklamayı görselleştirmenin sol tarafına taşıyın.    
6. **Başlık** seçeneğini **Açık** olarak değiştirip **Gösterge adı** alanına **Managers** yazarak bir açıklama başlığı ekleyin.
   ![](media/power-bi-visualization-customize-title-background-and-legend/legend-move.png)
   
   Bu ana kadar gerçekleştirdiğimiz tüm özelleştirmeleri geri almak için **Açıklama** özelleştirme bölmesinin altında bulunan **Varsayılana Geri Dön** seçeneğini belirleyin.

<a name="list"></a>

## <a name="visualization-types-that-can-be-customized"></a>Özelleştirilebilen görselleştirme türleri
| Görselleştirme | Başlık | Arka Plan | Açıklama |
|:--- |:--- |:--- |:--- |
| alan |evet |evet |evet |
| çubuk |evet |evet |evet |
| kart |evet |evet |kullanılamaz |
| çok satırlı kart |evet |evet |kullanılamaz |
| sütun |evet |evet |evet |
| birleşik |evet |evet |evet |
| halka |evet |evet |evet |
| doldurulmuş harita |evet |evet |evet |
| huni |evet |evet |kullanılamaz |
| ölçek |evet |evet |kullanılamaz |
| kpi |evet |evet |kullanılamaz |
| çizgi |evet |evet |evet |
| harita |evet |evet |evet |
| matris |evet |evet |kullanılamaz |
| pasta |evet |evet |evet |
| dağılım |evet |evet |evet |
| dilimleyici |evet |evet |kullanılamaz |
| tablo |evet |evet |kullanılamaz |
| metin kutusu |hayır |evet |kullanılamaz |
| ağaç haritası |evet |evet |evet |
| şelale |evet |evet |evet |

## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md) hakkında daha fazla bilgi  
[X ve Y eksenini özelleştirme](power-bi-visualization-customize-x-axis-and-y-axis.md)  
[Renkleri ve eksen özelliklerini özelleştirme](service-getting-started-with-color-formatting-and-axis-properties.md)  
[Power BI - Temel Kavramlar](service-basic-concepts.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

