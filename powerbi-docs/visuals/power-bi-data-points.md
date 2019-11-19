---
title: Büyük veri kümeleri, veri noktası sınırları ve veri stratejileri
description: Veri azaltma stratejileri ve görseller için veri sınırları
author: mihart
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/07/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 1ae0fc339d3837c8fc28cc604b3ddb840807dcd5
ms.sourcegitcommit: 0d7ad791a2d2bef45d5d60e38e0af4c9fc22187b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74011292"
---
# <a name="data-point-limits-and-strategies-by-visual-type"></a>Görsel türüne göre stratejiler ve veri noktası sınırları

Power BI’da bir görsel işlenirken görselleştirme hızlı ve doğru olmalıdır. Bu, her bir görsel türü için temel algoritmaların yapılandırılmış olmasını gerektirir. Power BI’daki görseller, farklı boyutlarda veri kümelerini işlemek için yeterince esnek olmalıdır. Bazı veri kümelerinin yalnızca bir avuç dolusu veri noktası varken, bazı veri kümelerininse petabaytlarca veri noktası vardır. Bu makalede, görselleştirmeleri işlemek için Power BI tarafından kullanılan stratejiler açıklanmaktadır.

## <a name="data-reduction-strategies"></a>Veri azaltma stratejileri
Her görsel, analiz edilen büyük olabilecek veri hacimlerini işlemek için bir veya daha fazla *veri azaltma stratejisini* devreye alır. Basit bir tablo bile veri kümesinin tamamının istemciye yüklenmesini engellemeye yönelik bir stratejiyi devreye alır.  Kullanılan azaltma stratejisi, görsel türüne göre değişiklik gösterir. Her görsel, sunucuya gönderilen veri isteği oluşturma işleminin parçası olarak desteklenen *veri azaltma stratejileri* arasından seçim yapar. 

Her bir görsel, genel veri miktarını etkilemek için bu stratejiler üzerindeki parametreleri denetler.   

## <a name="strategies"></a>Stratejiler
Her bir strateji için, görselleştirilmekte olan verilerin şekline ve türüne dayalı varsayılanlar vardır. Ancak doğru kullanıcı deneyimini sağlamak için Power BI Biçimlendirme bölmesinde varsayılanlar geçersiz kılınabilir. 

* **Veri Pencereleme** (Segmentlere Ayırma): Kullanıcıların, genel veri kümesi parçalarını aşamalı olarak yükleyerek bir görseldeki verilerde gezinmesine olanak sağlar.
* **TopN**: Yalnızca ilk N öğeyi gösterir
* **Basit Örnek**: İlk öğeyi, son öğeyi ve bunlar arasında eşit olarak dağıtılmış N öğeyi gösterir.
* **BottomN**: Yalnızca son N öğeyi gösterir.  Sık güncelleştirilen verilerin izlenmesi için yararlıdır.
* **Yüksek yoğunluklu örnekleme** - Aykırı değerlere ve/veya bir eğrinin şekline daha iyi uyan, gelişmiş bir örnekleme algoritmasıdır.
    * **Bölünmüş çizgi örnekleme** - Bir eksen boyunca bölmelerdeki aykırı değerlere dayalı örnek veri noktaları
    * **Çakışan noktaları örnekleme** - Aykırı değerleri korumak için çakışan değerlere dayalı örnek veri noktaları

## <a name="statistics"></a>İstatistik
Belirli modeller, belirli sütunlar için değer sayısıyla ilgili istatistikler sağlayabilir. Bu tür bilgiler mevcut olduğunda, bir görselin bir strateji için değer sayısını açıkça geçersiz kılmaması durumunda birden çok hiyerarşi genelinde daha iyi dengeleme sağlamak için bu bilgilerden yararlanırız.

Daha fazla bilgi için bkz. [Analysis Services’taki yenilikler](https://docs.microsoft.com/sql/analysis-services/what-s-new-in-analysis-services?view=sql-server-2017)

## <a name="dynamic-limits"></a>Dinamik sınırlar
Yukarıdaki stratejilere ek olarak, iki gruplandırma sütunu hiyerarşisi (eksen ve gösterge veya kategori ve seri) içeren görseller, *dinamik sınırlar* adı verilen ek bir strateji kullanır.  Dinamik sınırlar, veri noktalarını daha iyi dengelemek için tasarlanmıştır. 

Dinamik sınırlar, seyrek veriler için statik sınırlardan daha iyi nokta seçimi sağlar. Bir görsel, örneğin, 100 kategori ve toplam 1000 nokta içeren 10 seri seçilecek şekilde yapılandırılabilir. Ancak gerçek veriler 50 kategori ve 20 seri içerir.  Sorgu çalışma zamanında dinamik sınırlar, istenen 1000 noktayı doldurmak için 20 serinin tümünü seçer.

Sunucu aşağıda ayrıntıları verilen özelliklere sahip olduğunda dinamik sınırlar otomatik olarak uygulanır:

* [Sunucudaki SuperDax özelliklerinden yararlanılarak](https://blogs.msdn.microsoft.com/analysisservices/2015/09/02/whats-new-in-microsoft-sql-server-analysis-services-tabular-models-in-sql-server-2016-ctp-2-3/) Şirket içi SSAS 2016 veya daha yüksek sürüm ile Power BI Desktop’ta

* İçeri aktarılan bir model, Doğrudan Sorgu, hizmetle canlı bağlantı veya AS PaaS ile canlı bağlantı kullanılırken Masaüstü ve Power BI hizmetinde. 

* Şirket içi SSAS’a şirket içi bir ağ geçidi üzerinden bağlanılırken Power BI Hizmetinde dinamik sınırları kullanamayız. Şirket içi ağ geçidi, şirket içi SSAS’tan farklı sonuç kümeleri yapısı döndüren dinamik sınırlar stratejisini tamamen desteklemez.  

## <a name="strategies-and-data-point-limits-by-visual-type"></a>Görsel türüne göre stratejiler ve veri noktası sınırları

### <a name="area-chart"></a>Alan grafiği
Bkz. [Satır örnekleme nasıl çalışır?](../desktop-high-density-sampling.md#how-the-new-line-sampling-algorithm-works)

### <a name="barcolumn-chart"></a>Çubuk/sütun grafik
- Kategorik moddayken
    - Kategoriler: Aynı anda 500 satırlık Pencere kullanılarak sanallaştırma
    - Seri: İlk 60
    - Skaler modundayken (dinamik sınırları kullanabilir)
        - Maksimum nokta sayısı: 10.000
        - Kategoriler: 500 değerlik örnek
        - Seri: İlk 20 değer

### <a name="card-multirow"></a>Kart (çok satırlı) 
- Değerler: Aynı anda 200 satırlık Pencere kullanılarak sanallaştırma

### <a name="combo-chart"></a>Birleşik grafik
 Aynı stratejileri sütun grafik olarak kullanır. **Birleşik grafikteki** satırın, **çizgi grafiğin** kullandığı yüksek yoğunluklu algoritmayı kullanmadığına dikkat edin.

### <a name="custom-visuals"></a>Özel görseller
En fazla 30.000 olabilir, ancak hangi stratejilerin kullanılacağını belirtmek görsel yazarlarına bağlıdır

### <a name="doughnut"></a>Halka
- Maksimum nokta sayısı: 3.500
- Grup: İlk 500
- Ayrıntılar: İlk 20

### <a name="filled-map-choropleth"></a>Kartogram koroplet 
Kartogram, istatistikleri veya dinamik sınırları kullanabilir. Power BI, azaltmayı şu sırayla kullanmaya çalışır: dinamik sınırlar, istatistikler ve son olarak yapılandırma. 
- Maksimum nokta sayısı: 10000
- Kategoriler: İlk 500
- Seri (hem X hem Y mevcut olduğunda): İlk 20

### <a name="funnel"></a>Huni
- Maksimum nokta sayısı: 3.500
- Kategoriler: İlk 3.500

### <a name="kpi"></a>KPI
- Eğilim ekseni
- Son 3.500

### <a name="line-chart"></a>Çizgi grafik
Bkz. [Satır örnekleme nasıl çalışır?](../desktop-high-density-sampling.md#how-the-new-line-sampling-algorithm-works)

### <a name="line-chart-high-density"></a>Çizgi grafik, yüksek yoğunluklu
Bkz. [Yüksek yoğunluklu örnekleme](../desktop-high-density-sampling.md)

### <a name="map"></a>Harita 
- Maksimum nokta sayısı: 3.500

Yapılandırmaya bağlı olarak bir haritada şunlar bulunabilir:
- Konum: İlk 3.500
- Konum, Boyut: İlk 3.500
- Konum, Enlem ve Boylam toplamları (+/-Boyut): İlk 3.500
- Enlem, Boylam: bkz. [Yüksek yoğunluklu dağılım](desktop-high-density-scatter-charts.md)
- Enlem, Boylam, Boyut: İlk 3.500
- Gösterge, Enlem, Boylam: bkz. [Yüksek yoğunluklu dağılım](desktop-high-density-scatter-charts.md)
- Gösterge, Enlem, Boylam, Boyut: İlk 233 gösterge, İlk 15 enlem ve boylam (istatistikleri veya dinamik sınırları kullanabilir)
- Toplamalar olarak Konum, Gösterge, Enlem ve Boylam (+/-Boyut): İlk 233 konum, İlk 15 gösterge (istatistikleri veya dinamik sınırları kullanabilir)

### <a name="matrix"></a>Matris
- Satırlar: Aynı anda 500 satırlık Pencere kullanılarak sanallaştırma
- Sütunlar: İlk 100 gruplandırma sütunu 
- Değerler: veri azaltmaya karşı birden çok değer sayılmaz

### <a name="radial-gauge"></a>Radyal ölçer
Azaltma stratejisi yoktur

### <a name="slicer"></a>Dilimleyici
- Değerler: Aynı anda 200 satırlık Pencere kullanılarak sanallaştırma

### <a name="scatter-chart-high-density"></a>Dağılım grafiği (yüksek yoğunluklu)
Bkz. [Yüksek yoğunluklu dağılım](https://docs.microsoft.com/power-bi/visuals/desktop-high-density-scatter-charts)

### <a name="pie"></a>Pasta
- Maksimum nokta sayısı: 3.500
- Grup: İlk 500
- Ayrıntılar: İlk 20

### <a name="r--python-visuals"></a>R ve Python görselleri
150.000 satırla sınırlıdır. 150.000’den fazla satır seçilirse yalnızca ilk 150.000 satır kullanılır

### <a name="ribbon-chart"></a>Şerit grafik
- Kategorik moddayken
    - Kategoriler: Aynı anda 500 satırlık Pencere kullanılarak sanallaştırma (veri pencereleme)
    - Seri: İlk 60
    - Skaler modundayken (dinamik sınırları kullanabilir)
        - Maksimum nokta sayısı: 10.000
        - Kategoriler: 500 değerlik örnek
        - Seri: İlk 20 değer

### <a name="shape-map-preview"></a>Şekil haritası (Önizleme)
Şekil haritası, istatistikleri veya dinamik sınırları kullanabilir. 
- Maksimum nokta sayısı: 1.500
- Kategoriler: İlk 500

### <a name="table"></a>Tablo
- Değerler: Aynı anda 500 satırlık Pencere kullanılarak sanallaştırma (veri pencereleme)

### <a name="tree-map-could-use-statistics-or-dynamic-limits"></a>Ağaç harita (istatistikleri veya dinamik sınırları kullanabilir)
- Maksimum nokta sayısı: 3.500
- Grup: İlk 500
- Ayrıntılar: İlk 20

### <a name="waterfall-chart"></a>Şelale grafiği
- Yalnızca kategori demeti olduğunda
    - Maksimum nokta sayısı: 3.500
    - Yalnızca kategori - ilk 3.500
- Hem kategori hem çözümleme mevcut olduğunda
    - Kategori: Aynı anda 30 satırlık Pencere kullanılarak sanallaştırma (veri pencereleme)
    - Çözümleme - İlk 200 değer


## <a name="next-steps"></a>Sonraki adımlar
[Görselleştirme türleri](power-bi-report-visualizations.md)
