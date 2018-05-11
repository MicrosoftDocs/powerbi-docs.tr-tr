---
title: 'Rapor düzenleyicisi: Tura katılın'
description: 'Rapor düzenleyicisi: Tura katılın.'
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
featuredvideoid: IkJda4O7oGs
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/11/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 5664cdd69483a98f10e9386db870428f0649aa06
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="the-report-editortake-a-tour"></a>Rapor düzenleyicisi: Tura katılın
## <a name="editing-reports-in-power-bi-service-and-power-bi-desktop"></a>Power BI hizmetinde ve Power BI Desktop'ta raporları düzenleme
Power BI hizmetindeki rapor düzenleyicisi ile Power BI Desktop uygulamasındaki rapor düzenleyicisi benzer özelliklere sahiptir. Videoda Power BI Desktop uygulamasındaki rapor düzenleyicisine, bu makalede ise Power BI hizmetindeki rapor düzenleyicisine yer verilmiştir. 

## <a name="the-difference-between-report-creators-and-report-consumers"></a>Rapor *oluşturucuları* ile rapor *kullanıcıları* arasındaki fark
Bir rapor yalnızca rapor sahipleri (diğer adıyla *oluşturucular*) tarafından oluşturulabilir ve düzenlenebilir. Sizinle paylaşılan bir raporu *kullanıyorsanız*, raporu Power BI hizmetinin yalnızca [Okuma görünümünde](service-reading-view-and-editing-view.md) açıp raporla etkileşimde bulunabilirsiniz ancak rapor oluşturucunun kullanabildiği tüm güçlü ve kapsamlı özelliklere sahip olmazsınız.  

Rapor Okuma görünümü hakkında daha fazla bilgi almak için bkz. [Power BI hizmetinde Okuma görünümü ve Düzenleme görünümü](service-reading-view-and-editing-view.md) 

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

Power BI hizmetinde *rapor düzenleyicisi* yalnızca [Düzenleme Görünümü](service-reading-view-and-editing-view.md)'nde kullanılabilir. Bir raporu Düzenleme görünümünde açabilmek için raporun sahibi veya oluşturucusu olmanız gerekir.

Power BI rapor düzenleyicisi 3 bölümden oluşur:  

1. **Alanlar**, **Görsel Öğeler** ve **Filtreler** bölmeleri
2. üst gezinti çubukları    
3. rapor tuvali     

![](media/service-the-report-editor-take-a-tour/power-bi-report-canvas.png)

## <a name="1-the-report-editor-panes"></a>1. Rapor düzenleyicisi bölmeleri
![Power BI rapor düzenleyicisi](media/service-the-report-editor-take-a-tour/power-bi-report-panes.png)

Bir raporu açtığınızda 3 bölme görürsünüz: Görsel Öğeler, Filtreler ve Alanlar. Sol taraftaki Görsel Öğeler ve Filtreler bölmeleri görselleştirmeler üzerinde tür, renk, filtreleme ve biçimlendirme gibi denetimler gerçekleştirmenizi sağlar.  Sağ taraftaki Alanlar bölmesi ise görselleştirmelerde kullanılan bağlantılı verileri yönetir. 

Rapor düzenleyicisinde görüntülenen içerik, rapor tuvalinde yaptığınız seçimlere göre değişiklik gösterir.  Örneğin, tek bir görsel seçtiğinizde 

|  |  |
| --- | --- |
| ![](media/service-the-report-editor-take-a-tour/power-bi-panes.png) |<ul><li>Görsel Öğeler bölmesinin en üst kısmında, kullanılan görselin türü görüntülenir. Bu örnekte, Kümelenmiş sütun grafik kullanılmaktadır.<br><br></li> <li>Görsel Öğeler bölmesinin en altında (sayfayı kaydırmanız gerekebilir), görselde kullanılan alanlar görüntülenir. Bu grafikte FiscalMonth, DistrictManager ve Total Sales Variance alanları kullanılmaktadır. <br><br></li><li>Filtreler bölmesinde (sayfayı kaydırmanız gerekebilir), uygulanmış olan filtreler görüntülenir. <br><br></li><li>Alanlar bölmesinde, kullanılabilir tablolar listelenir ve bir tablonun adını genişlettiğinizde tablonun içerdiği alanlar görüntülenir. Sarı renkli yazı tipi, tablodaki alanlardan en az birinin görselleştirmede kullanıldığını belirtir.<br><br></li><li>![boya rulosu simgesi](media/service-the-report-editor-take-a-tour/power-bi-paint-roller-icon.png) Seçilen görselleştirmeye ilişkin biçimlendirme bölmesini görüntülemek için boya rulosu simgesini seçin.<br><br></li><li>![büyüteç simgesi](media/service-the-report-editor-take-a-tour/power-bi-magnifying-icon.png) Analiz bölmesini görüntülemek için büyüteç simgesini seçin.</ul> |

## <a name="the-visualizations-pane-from-top-to-bottom"></a>Görsel Öğeler bölmesi (yukarıdan aşağıya doğru)
![Görselleştirme bölmesinin üst kısmı](media/service-the-report-editor-take-a-tour/selectviz.png)

Görselleştirme türünü buradan seçebilirsiniz. Küçük resimlere *şablon* adı verilir. Yukarıdaki görüntüde, Kümelenmiş çubuk grafik seçilmiştir. Görselleştirme türü seçmeden alan seçerek bir görselleştirme oluşturmaya başlarsanız Power BI, görselleştirme türünü sizin yerinize belirler. Power BI tarafından yapılan seçimi tutabilir veya farklı bir şablonu seçerek türü değiştirebilirsiniz. Verilerinize en uygun görselleştirme türünü bulmak için istediğiniz kadar değişiklik yapabilirsiniz.

### <a name="manage-the-fields-used-in-your-visual"></a>Görselinizde kullanılan alanları yönetin.
![Görselleştirme bölmesinin ortası](media/service-the-report-editor-take-a-tour/power-bi-field-list.png)

Bu bölmede gösterilen demetler (bazen *kutu* olarak da adlandırılır) seçtiğiniz görselleştirme türüne göre değişiklik gösterir.  Örneğin, bir çubuk grafik seçerseniz şu demetleri görürsünüz: Değerler, Eksen ve Açıklama. Bir alanı seçtiğinizde veya tuvale sürüklediğinizde Power BI, ilgili alanı demetlerden birine ekler.  Dilerseniz Alanlar listesindeki alanları doğrudan demetlerin içine sürükleyebilirsiniz.  Bazı demetler yalnızca belirli veri türlerinde kullanılabilir.  Örneğin, **Değerler** demeti, sayısal olmayan alanlarla kullanılamaz. **employeename** alanını **Değerler** demetine sürüklerseniz Power BI bunu **count of employeename** olarak değiştirir.

### <a name="remove-a-field"></a>Alanları kaldırma
Görselleştirmedeki bir alanı kaldırmak için alan adının sağ tarafında bulunan **X** simgesini seçin.

![StoreType öğesini Açıklama’dan kaldırma](media/service-the-report-editor-take-a-tour/deletefield.png)

Daha fazla bilgi için bkz. [Bir Power BI raporuna görselleştirme ekleme](power-bi-report-add-visualizations-i.md)

### <a name="format-your-visuals"></a>Görsellerinizi biçimlendirme
Biçimlendirme bölmesini açmak için boya rulosu simgesini seçin. Kullanılabilir seçenekler, seçtiğiniz görselleştirme türüne göre değişiklik gösterir.

![Biçimlendirme bölmesi](media/service-the-report-editor-take-a-tour/power-bi-formatting.png)

Biçimlendirme seçenekleri neredeyse sonsuzdur.  Daha fazla bilgi edinmek için kendiniz keşfedin veya şu makaleleri ziyaret edin:

* [Görselleştirme başlığını, arka planı ve açıklamayı özelleştirme](power-bi-visualization-customize-title-background-and-legend.md)
* [Renk biçimlendirme](service-getting-started-with-color-formatting-and-axis-properties.md)
* [X ve Y ekseni özelliklerini özelleştirme](power-bi-visualization-customize-x-axis-and-y-axis.md)

### <a name="add-analytics-to-your-visualizations"></a>Görselleştirmelerinize analiz ekleme
Analiz bölmesini görüntülemek için büyüteç simgesini seçin. Kullanılabilir seçenekler, seçtiğiniz görselleştirme türüne göre değişiklik gösterir.

![](media/service-the-report-editor-take-a-tour/power-bi-analytics.png)    
Power BI hizmetindeki Analiz bölmesini kullanarak görselleştirmelere dinamik başvuru çizgileri ekleyebilir ve önemli eğilimlere veya öngörülere odaklanılmasını sağlayabilirsiniz. Daha fazla bilgi için bkz. [Power BI hizmetindeki Analiz bölmesi](service-analytics-pane.md) veya [Power BI Desktop'taki Analiz bölmesi](desktop-analytics-pane.md).

- - -
## <a name="the-filters-pane"></a>Filtreler bölmesi
Raporunuzda sayfa, rapor, detaylandırma ve görsel öğe düzeyinde kalıcı filtreler görüntülemek, ayarlamak ve değiştirmek için Filtreler bölmesini kullanın. Evet, görsellerin öğelerini seçerek ya da dilimleyici gibi araçlar kullanarak rapor sayfalarında ve görsel öğelerde geçici filtreleme yapabilirsiniz, ancak Filtreler bölmesi kullanıldığında filtrelerin durumu raporla birlikte kaydedilir. 

Filtreler bölmesinin bir diğer güçlü özelliği: ***halihazırda raporunuzdaki görsel öğelerden biri tarafından kullanılmayan*** bir alan kullanarak filtreleme olanağı. Biraz açıklayayım. Bir rapor sayfası oluşturduğunuzda Power BI, görsel öğelerinizde kullandığınız tüm alanları, Filtreler bölmesinin Görsel düzey filtreleri alanına otomatik olarak ekler.  Ancak, o anda bir görsel öğede kullanılmayan bir alanı kullanarak görsel öğe, sayfa, detaylandırma veya rapor filtresi ayarlamak istiyorsanız, ilgili öğeyi Filtreler demetlerinden birine sürüklemeniz yeterlidir.   

![Filtreler bölmesi](media/service-the-report-editor-take-a-tour/power-bi-formatting-pane.png)

Daha fazla bilgi için bkz. [Bir rapora filtre ekleme](power-bi-report-add-filter.md).

- - -
## <a name="the-fields-pane"></a>Alanlar bölmesi
Alanlar bölmesinde, verilerinizde bulunan ve görselleştirme oluşturmak için kullanabileceğiniz tablolar ve alanlar görüntülenir.

|  |  |
| --- | --- |
| ![Alanlar bölmesi](media/service-the-report-editor-take-a-tour/reportfields.png) |<ul><li>Yeni bir görselleştirme başlatmak için alanlardan birini sayfaya sürükleyin.  Dilerseniz bir alanı, var olan bir görselleştirmenin üzerine sürükleyerek görselleştirmeye ekleyebilirsiniz.<br><br></li> <li>Bir alanın yanındaki onay kutusunu işaretlediğinizde Power BI, ilgili alanı etkin (veya yeni) görselleştirmeye ekler. Ayrıca söz konusu alanın yerleştirileceği demeti de belirler.  Örneğin, eklediğiniz alan bir açıklama, eksen veya değer olabilir. Power BI en iyi tahmini yapar ve gerekirse söz konusu alanı, belirlenen demetten bir başkasına taşıyabilirsiniz. <br><br></li><li>Her iki durumda da seçili alanlar, rapor düzenleyicisindeki Görsel Öğeler bölmesine eklenir.</li></ul> |

**NOT**: Power BI Desktop uygulamasını kullanıyorsanız alanları gösterme/gizleme ve hesaplama ekleme gibi seçeneklere de sahip olursunuz.

### <a name="what-do-the-field-icons-mean"></a>Alan simgeleri ne anlama gelir?
* **∑ Toplamlar** Toplam, toplaması yapılacak veya ortalaması alınacak bir sayısal değerdir. Toplamlar, verilerle (raporunuzun temel aldığı veri modelinde tanımlanan) birlikte içeri aktarılır.
  Daha fazla bilgi için bkz. [Power BI raporlarındaki toplamlar](service-aggregates.md).
* ![hesap makinesi simgesi](media/service-the-report-editor-take-a-tour/pbi_calculated_icon.png) **Hesaplanan ölçüler (hesaplanan alanlar olarak da adlandırılır)**  
   Her hesaplanan alanın kendi sabit kodlanmış formülü vardır. Hesaplama türünü değiştiremezsiniz. Örneğin, tür toplam olarak ayarlanmışsa bu şekilde olarak kalır. Daha fazla bilgi için bkz. [Ölçüleri anlama](desktop-measures.md)
* ![Benzersiz alan simgesi](media/service-the-report-editor-take-a-tour/icon.png) **Benzersiz alanlar**  
   Bu simgeye sahip alanlar Excel'den aktarılmıştır ve yinelenen değerlere sahip olsalar bile tüm değerleri gösterecek şekilde ayarlanmıştır. Örneğin, verilerinizde "Can Kaya" adlı iki kişinin kaydı olabilir ve bu değerler benzersiz kabul edilir, toplama yapılmaz.  
* **![Coğrafya simgesi](media/service-the-report-editor-take-a-tour/pbi_geo_icon.png) Coğrafya alanları**  
   Konum alanları kullanılarak harita görselleştirmeleri oluşturulabilir. 
* **![Hiyerarşi simgesi](media/service-the-report-editor-take-a-tour/power-bi-hierarchy-icon.png) Hiyerarşi**  
   Hiyerarşiyi oluşturan alanları göstermek için oku seçin. 

- - -
## <a name="2-the-top-navigation-bar"></a>2. Üst gezinti çubuğu
Üst gezinti çubuğundan birçok farklı eylem gerçekleştirilebilir ve sürekli olarak bu eylemlere yenileri eklenmektedir. Belirli bir eylem hakkında bilgi almak için Power BI Belgeleri İçindekiler Tablosunu veya Arama kutusunu kullanın.

## <a name="3-the-report-canvas"></a>3. Rapor tuvali
Rapor tuvali, çalışmanızın görüntülendiği yerdir. Alanlar, Filtreler ve Görsel Öğeler bölmelerini kullanarak oluşturduğunuz görseller rapor tuvalinizde oluşturulur ve görüntülenir. Tuvalin en alt bölümündeki her sekme raporun bir sayfasına karşılık gelir. Açmak istediğiniz sayfaya ait sekmeyi seçebilirsiniz. 

## <a name="next-steps"></a>Sonraki Adımlar:
[Rapor oluşturma](service-report-create-new.md)

[Power BI hizmeti](service-reports.md), [Power BI Desktop](desktop-report-view.md) ve [Power BI mobil](mobile-apps-view-phone-report.md)’de raporlar hakkında daha fazla bilgi edinin.

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

