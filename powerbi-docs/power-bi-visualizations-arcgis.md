---
title: "Sizinle paylaşılan bir ArcGIS haritasıyla etkileşim kurma"
description: "ArcGis haritasını okuma görünümünde kullanma "
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: power bi, service, desktop, mobile
featuredvideoid: 
qualityfocus: monitoring
qualitydate: 06/23/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/21/2018
ms.author: mihart
ms.openlocfilehash: 797b22ed6f07e64d7e4970f8f0dfe5e93a7c0ec4
ms.sourcegitcommit: 2ae323fbed440c75847dc55fb3e21e9c744cfba0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2018
---
# <a name="interacting-with-arcgis-maps-in-power-bi"></a>Power BI'da ArcGIS haritaları ile etkileşim kurma
Bu konu başlığı, ArcGIS haritasını Power BI hizmeti, Desktop veya mobil sürümünde *kullanan* bir kişinin bakış açısından yazılmıştır. Oluşturan kişi sizinle bir ArcGIS haritası paylaştığında, haritayla etkileşime geçmek için pek çok yol bulunur.  ArcGIS haritası oluşturma hakkında daha fazla bilgi edinmek için [Esri tarafından sunulan ArcGIS haritaları eğitimine](power-bi-visualization-arcgis.md) başvurabilirsiniz.

ArcGIS haritaları ile Power BI'ın birleşimi, eşlemeyi haritada belirli noktaları göstermekten öteye götürüp yepyeni bir düzeye çıkarıyor. Harika, bilgilendirici harita görselleştirmeleri oluşturmak için kullanabileceğiniz seçenekler arasında temel haritalar, konum türleri, temalar, simge stilleri ve başvuru katmanları bulunur. Uzamsal analiz içeren bir haritadaki yetkili veri katmanlarının (nüfus sayımı verileri gibi) birleşimi, görselleştirmenizdeki verilerin daha derinlemesine anlaşılmasını sağlar.

> [!TIP]
> GIS, Coğrafi Bilgi Bilimi anlamına gelir.
> 

Kullanmakta olduğumuz örnek [Esri tarafından sunulan ArcGIS haritaları eğitimi](power-bi-visualization-arcgis.md) kapsamında oluşturulan aynı ArcGIS haritasıdır. Geçen senenin satışlarını şehre göre inceler ve boyutu ifade etmek için bir sokak temel haritası ve kabarcık sembolleri, ortalama hane halkı geliri içinse bir başvuru katmanı kullanır. Harita, 3 raptiye ve bir sürüş süresi yarıçapı (mor renkte) içerir.

![](media/power-bi-visualizations-arcgis/power-bi-arcgis-esri-new.png)

> [!TIP]
> Birçok örneğe bakmak ve referansları okumak için [Esri'nin Power BI sayfasını](https://www.esri.com/powerbi) ziyaret edin. Ardından Esri'nin [ArcGIS Maps for Power BI ile Çalışmaya Başlama sayfasına](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm) bakın.
> 
> 

<br/>

## <a name="user-consent"></a>Kullanıcı onayı
Bir iş arkadaşınız sizinle ilk defa ArcGIS haritası paylaştığında Power BI, ekranda bir komut istemi görüntüler. ArcGIS Maps for Power BI [Esri](https://www.esri.com) tarafından sağlanmakta olup ArcGIS Maps for Power BI'ın kullanımı için Esri'nin şartları ve gizlilik ilkesi geçerlidir. ArcGIS Maps for Power BI görsellerini kullanmak isteyen Power BI kullanıcılarının onay iletişim kutusunu kabul etmesi gerekir.

## <a name="selection-tools"></a>Seçim araçları
ArcGIS Maps for Power BI üç seçim modu sunar. Aynı anda en fazla 250 veri noktası seçilebilir.

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-tools2.png)

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-single2.png) Tek tek veri noktalarını seçer.

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-marquee2.png) Harita üzerinde bir dikdörtgen çizer ve içerdiği veri noktalarını seçer. Birden fazla dikdörtgen alan seçmek için CTRL tuşunu kullanın.

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-reference-layer2.png) İçindeki veri noktalarını seçmek için, kullanılan başvuru katmanlarında sınırlara veya çokgenlere izin verir.

<br/>

## <a name="interacting-with-an-arcgis-map"></a>Bir ArcGIS haritasıyla etkileşim kurma
Kullanabileceğiniz özellikler, haritanın *oluşturucusu* (haritayı oluşturan kişi) ya da *kullanıcısı* (ArcGIS haritası sizinle paylaşıldığında) olmanıza göre farklılık gösterebilir. Bir ArcGIS haritası ile kullanıcı olarak etkileşim kuruyorsanız (bir başka deyişle [Okuma görünümü](service-reading-view-and-editing-view.md)) aşağıdaki işlemleri gerçekleştirebilirsiniz.

* Diğer görselleştirme türleri için geçerli olduğu üzere [panoya sabitle](service-dashboard-pin-tile-from-report.md), [görüntüle](service-reports-show-data.md) ve/veya [temel alınan verileri dışarı aktar](power-bi-visualization-export-data.md) özelliklerinden faydalanabilir ve haritayı [Odak modu](service-focus-mode.md) ve [Tam ekran](service-fullscreen-mode.md) modunda görüntüleyebilirsiniz.    
* Filtre kullanarak haritada gezmek için **Filtreler** bölmesini genişletin. Raporu kapattığınızda, uygulamış olduğunuz filtreler kaydedilmez.    
    ![](media/power-bi-visualizations-arcgis/power-bi-filter-newer.png)  
* Haritada başvuru katmanı olması durumunda bir araç ipucunda ayrıntıları görüntülemek için konumları seçin. Bu örnekte Adams County'yi seçtik ve haritayı oluşturan tarafından haritaya eklenen ortalama hane halkı geliri başvuru katmanı verilerini görüntüledik.
  
    ![](media/power-bi-visualizations-arcgis/power-bi-reference-layer.png)  
  
    Bu örnekte ayrıca grafik de elde ediyoruz. Veriyi daha derinlemesine incelemek için grafik üzerinde bulunan bir çubuğu seçin. Burada Adams ilçesinde bulunan 79 hanenin 200.000 Dolar veya üzerinde kazandığını görüyoruz.
  
    ![](media/power-bi-visualizations-arcgis/power-bi-tooltip-chart.png)
  
    Ek grafikleri görüntülemek için oku seçin.
* Bir araç ipucundaki ayrıntıları görüntülemek için temel harita konumu sembolleri üzerine gelin.     
  ![](media/power-bi-visualizations-arcgis/power-bi-arcgis-hover.png)
  
  > [!TIP]
  > Belirli bir konum seçmek için yakınlaştırmanız gerekebilir.  Diğer durumlarda, çakışan konumlar söz konusuysa Power BI size bir seferde 1 adetten fazla araç ipucu sunabilir. Araç ipuçları arasında hareket etmek için okları seçin
  > 
  > ![](media/power-bi-visualizations-arcgis/power-bi-3-screens.png)
  > 
  > 
* Haritayı oluşturan kişinin ArcGIS haritasına İnfografik katmanı eklemesi durumunda haritanın sağ üst köşesinde ek veri görüntülendiğini görebilirsiniz.  Örneğin, haritayı oluşturan kişi burada "Children under 14" (14 yaşın altındaki çocuklar) bilgisi eklemiştir.
  
    ![](media/power-bi-visualizations-arcgis/power-bi-demographics.png)

## <a name="considerations-and-limitations"></a>Önemli Noktalar ve Sınırlamalar
ArcGIS Maps for Power BI aşağıdaki hizmetlerde ve uygulamalarda kullanılabilir:

<table>
<tr><th>Hizmet/Uygulama</th><th>Kullanılabilirlik</th></tr>
<tr>
<td>Power BI Desktop</td>
<td>Evet</td>
</tr>
<tr>
<td>Power BI hizmeti (app.powerbi.com)</td>
<td>Evet</td>
</tr>
<tr>
<td>Power BI mobil uygulamaları</td>
<td>Evet</td>
</tr>
<tr>
<td>Power BI - web'de yayımlama</td>
<td>Hayır</td>
</tr>
<tr>
<td>Power BI Embedded</td>
<td>Hayır</td>
</tr>
<tr>
<td>Power BI hizmeti - ekleme (PowerBI.com)</td>
<td>Hayır</td>
</tr>
</table>

**ArcGIS haritası görüntülenmiyor**    
ArcGIS Maps for Power BI'ın kullanılamadığı hizmet veya uygulamalarda görselleştirme, Power BI logosuyla boş bir görsel gösterir.

**Tüm adreslerimi haritada göremiyorum**    
Posta adreslerinin coğrafi kodlaması yapılırken yalnızca ilk 1500 adresin coğrafi kodlaması yapılır. Yer adlarına veya ülkelere yönelik coğrafi kodlama, 1500 adres sınırına tabi değildir.

**ArcGIS Maps for Power BI kullanımı için herhangi bir ücret ödenir mi?**

Tüm Power BI kullanıcıları, ArcGIS Maps for Power BI'ı hiçbir ek ücret ödemeden kullanılabilir. **Esri** tarafından sağlanan bir bileşendir ve bu makalede daha önce belirtildiği üzere, kullanımınız **Esri** tarafından sağlanan koşullar ve gizlilik ilkesine tabidir.

**Önbelleğimin dolu olduğu hakkında bir hata iletisi alıyorum**

Bu hatanın çözümüne ilişkin çalışmalar sürmektedir.  Çözüm sunulana kadar Power BI önbelleğini temizlemeye yönelik talimatlar için hata iletisinde görüntülenen bağlantıyı seçin.

**ArcGIS haritalarımı çevrimdışı görüntüleyebilir miyim?**

Hayır, Power BI'ın haritaları görüntülemesi için ağ bağlantısı gerekir.

## <a name="next-steps"></a>Sonraki adımlar
Yardım alma: **Esri**, **ArcGIS Maps for Power BI**'ın özellikleri hakkında [kapsamlı belgeler](https://go.microsoft.com/fwlink/?LinkID=828772) sağlamaktadır.

[**ArcGIS Maps for Power BI** ile ilgili Power BI topluluk yazışmalarında](https://go.microsoft.com/fwlink/?LinkID=828771). soru sorabilir, en son bilgileri bulabilir, sorun raporlayabilir ve cevap bulabilirsiniz.

İyileştirme önerileriz varsa lütfen önerilerinizi [Power BI fikirleri listesine](https://ideas.powerbi.com) gönderin.

[ArcGIS Maps for Power BI ürün sayfası](https://www.esri.com/powerbi)

