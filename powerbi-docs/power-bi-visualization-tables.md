---
title: Power BI rapor ve panolarındaki tablo görselleştirmeleri
description: Sütun genişliklerini değiştirme dahil olmak üzere Power BI rapor ve panolarındaki tablo görselleştirmeleriyle çalışmaya ilişkin öğretici.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/11/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 37f4e06aee41b8741dd3a1a1a52e3237fbd893a3
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34293272"
---
# <a name="working-with-tables-in-power-bi-reports-and-dashboards"></a>Power BI rapor ve panolarında tablolarla çalışma
Tablo, mantıksal satır ve sütun dizilerinde ilgili verileri içeren bir kılavuzdur. Tabloda başlık ve toplam satırı da bulunabilir. Tablolar, tek bir kategoriye ait birden fazla değeri incelediğiniz nicelik karşılaştırmaları için idealdir. Örneğin bu tabloda **Category** için 5 farklı ölçü gösterilmektedir.

![](media/power-bi-visualization-tables/table.png)

## <a name="when-to-use-a-table"></a>Tablolar ne zaman kullanılır?
Tablolar şunlar için harika seçimdir:

* ayrıntılı verileri ve tam değerleri görüp karşılaştırmak için (görsel gösterimler yerine)
* verileri tablo biçiminde görüntülemek için
* sayısal verileri kategorilere göre ayrılmış şekilde görüntülemek için   

> [!NOTE]
> Bir tabloda çok fazla değer varsa tabloyu matrise dönüştürmeyi ve/veya detaya gitme özelliğini kullanmayı deneyin.
> 
> 
## <a name="prerequisites"></a>Önkoşullar
 - Power BI hizmeti veya Power BI Desktop
 - Perakende Analizi örneği


## <a name="create-a-table"></a>Tablo oluşturma
Yukarıdaki resimde görülen ve ürün kategorisine göre satış değerlerini gösteren tabloyu oluşturacağız. Örneği takip etmek için Power BI hizmetinde oturum açıp **Veri Al \> Örnekler \> Perakende Analizi Örneği > Bağlan**'ı seçtikten sonra **Panoya git seçeneğini belirleyin. Bir görsel öğe oluşturmak için veri kümesinde ve raporda düzenleme izinlerine sahip olmanız gerekir. Neyse ki, Power BI örneklerinin tümü düzenlenebilir. Sizinle bir rapor paylaşıldıysa, raporlarda görsel öğe oluşturamazsınız.

1. Sol gezinti bölmesinden **Çalışma Alanları > Çalışma Alanım**’ı seçin.    
2. Veri Kümeleri sekmesini seçin ve sayfayı kaydırarak yeni eklediğiniz Perakende Analizi Örneği veri kümesini bulun.  **Rapor oluştur** simgesini seçin.
   
    ![](media/power-bi-visualization-tables/power-bi-create-report.png)
2. Rapor düzenleyicisinde **Item** > **Category**'yi seçin.  Power BI otomatik olarak tüm kategorileri listeleyen bir tablo oluşturur.
   
    ![](media/power-bi-visualization-tables/power-bi-table1.png)
3. **Sales > Average Unit Price**, **Sales > Last Year Sales** ve **Sales > This Year Sales** öğelerini seçip 3 seçeneği de (Değer, Hedef, Durum) belirleyin.   
4. Görsel Öğeler bölmesinde **Değerler** kutusunu bulun ve değerleri grafiğinizdeki sıralama bu sayfadaki ilk görüntüdeki gibi olana kadar sürükleyip bırakın.  Değerlerinizin aşağıdaki gibi görünmesi gerekir.
   
    ![](media/power-bi-visualization-tables/power-bi-table2.png)
5. Raptiye simgesini seçerek tabloyu panoya sabitleyin  
   
     ![](media/power-bi-visualization-tables/pbi_pintile.png)

## <a name="format-the-table"></a>Tabloyu biçimlendirme
Bir tabloyu biçimlendirmek için kullanabileceğiniz birçok farklı yöntem vardır. Burada yalnızca birkaç tanesini inceleyeceğiz. Diğer biçimlendirme seçenekleri hakkında bilgi edinmek için Biçimlendirme bölmesini açıp (boya rulosu simgesi ![](media/power-bi-visualization-tables/power-bi-format.png)) kendiniz keşfedebilirsiniz.

* Tablo kılavuzunu biçimlendirmeyi deneyin. Burada mavi dikey kılavuz ekledik, satırlara boşluk ekledik, tablonun ana hatlarını ve metin boyutunu bir miktar artırdık.
  
    ![](media/power-bi-visualization-tables/power-bi-table-gridnew.png)
  
    ![](media/power-bi-visualization-tables/power-bi-table-grid3.png)
* Sütun başlıklarında arka plan rengini değiştirdik, ana hat ekledik ve yazı tipi boyutunu artırdık. 
  
    ![](media/power-bi-visualization-tables/power-bi-table-column-headers.png)

  
    ![](media/power-bi-visualization-tables/power-bi-table-column2.png)

* Hatta tek sütunlara ve sütun başlıklarına bile biçimlendirme uygulayabilirsiniz. İlk olarak **Alan biçimlendirme**’yi genişletin ve açılır listeden biçimlendirilecek sütunu seçin. Sütun değerlerine bağlı olarak, Alan biçimlendirme şunun gibi ayarları yapmanızı sağlar: görüntüleme birimleri, yazı tipi rengi, ondalık basamak sayısı, arka plan, hizalama ve daha fazlası. Ayarları düzenledikten sonra bu ayarları üst bilgiye ve toplamlar satırına da uygulayıp uygulamayacağınıza karar verin.

    ![](media/power-bi-visualization-tables/power-bi-field-formatting.png)

* Birkaç ek biçimlendirme sonrasında tablonun son halini aşağıda görebilirsiniz. Çok sayıda biçimlendirme seçeneği olduğundan öğrenmenin en iyi yolu varsayılan biçimlendirme ile başlayıp Biçimlendirme bölmesini  ![](media/power-bi-visualization-tables/power-bi-format.png) açmak ve seçenekleri keşfetmeye başlamaktır. 
  
    ![](media/power-bi-visualization-tables/power-bi-table-format.png)

### <a name="conditional-formatting"></a>Koşullu biçimlendirme
Biçimlendirme türlerinden biri de *koşullu biçimlendirmedir* ve Power BI hizmetinde veya Desktop uygulamasında **Görsel Öğeler** bölmesinin **Değerler** kutusundaki alanlara uygulanır. 

Tablolar için koşullu biçimlendirme sayesinde gradyan renklerini kullanma dahil olmak üzere hücre değerlerine göre özel hücre arka plan renkleri ve yazı tipi renkleri belirtebilirsiniz. 

1. Power BI hizmetinin veya Desktop uygulamasının **Görsel Öğeler** bölmesinde, **Değerler** kutusunda yer alan değerlerden biçimlendirmek istediğiniz değerin yanındaki aşağı oku seçin (veya alana sağ tıklayın). Koşullu biçimlendirmeyi yalnızca **Alanlar** kutusunun **Değerler** alanındaki alanlar için yönetebilirsiniz.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-background.png)
2. **Arka plan renk ölçekleri**'ni seçin. Açılan iletişim kutusunda rengin yanı sıra *Minimum* ve *Maksimum* değerleri yapılandırabilirsiniz. **Ayrılan** kutusunu seçerseniz isteğe bağlı bir *Orta* değer de yapılandırabilirsiniz.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)
   
    Şimdi Average Unit Price değerlerine özel biçimlendirme uygulayalım. **Ayrılan**'ı seçin, birkaç renk ekleyin ve **Tamam**'ı seçin. 
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
3. Tabloya hem pozitif hem de negatif değerler içeren yeni bir alan ekleyin.  **Sales > Total Sales Variance** öğesini seçin. 
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)
4. **Total Sales Variance** öğesinin yanındaki aşağı oku seçip **Koşullu biçimlendirme > Veri çubukları** yolunu izleyerek veri çubuğu koşullu biçimlendirmesi ekleyin.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars.png)
5. Açılan iletişim kutusunda **Pozitif çubuk** ve **Negatif çubuk** renklerini ayarlayın, **Yalnızca çubuğu göster**'in yanına onay işareti ekleyin ve istediğiniz diğer değişiklikleri yapın.
   
    ![](media/power-bi-visualization-tables/power-bi-data-bars.png)
   
    **Tamam**'ı seçtiğinizde tabloda sayısal değerler verine veri çubukları gösterilir ve bu sayede tablo daha kolay anlaşılır hale gelir.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)
6. Bir görselleştirmedeki koşullu biçimlendirmeyi kaldırmak için alana tekrar sağ tıklayın ve **Koşullu Biçimlendirmeyi Kaldır**'ı seçin.

> [!TIP]
> Koşullu biçimlendirmeye Biçimlendirme bölmesinden (boya rulosu simgesi) de erişebilirsiniz. Biçimlendirmek istediğiniz değeri seçip **Renk ölçekleri** veya **Veri çubukları** seçeneklerini Açık konumuna getirerek varsayılan ayarları uygulayabilir veya **Gelişmiş denetimler**'i seçerek ayarları özelleştirebilirsiniz.
> 
> 

## <a name="adjust-the-column-width-of-a-table"></a>Tablonun sütun genişliğini ayarlama
Bazen Power BI bir rapordaki veya bir panodaki sütun başlığını kısaltabilir. Sütun adının tamamını göstermek için başlığın sağ tarafındaki boşluğa giderek ikili okun görünmesini bekleyin, ardından seçin ve sürükleyin.

![](media/power-bi-visualization-tables/resizetable.gif)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

