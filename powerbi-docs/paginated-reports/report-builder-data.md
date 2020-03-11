---
title: Power BI Rapor Oluşturucusu’ndaki rapor verileri
description: Power BI Report Builder'da rapor tasarlamanın ilk adımı temel rapor verilerini temsil eden veri kaynaklarını ve veri kümelerini oluşturmaktır.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.custom: seodec18
ms.date: 06/06/2019
ms.openlocfilehash: fea4e4927b009e30bc040593f9237cc49ff73956
ms.sourcegitcommit: ced8c9d6c365cab6f63fbe8367fb33e6d827cb97
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2020
ms.locfileid: "78921459"
---
# <a name="report-data-in-power-bi-report-builder"></a>Power BI Rapor Oluşturucusu’ndaki rapor verileri

Rapor verileri kuruluşunuzdaki çeşitli veri kaynaklarından gelebilir. Power BI Rapor Oluşturucusu raporunu tasarlamanın ilk adımı temel rapor verilerini temsil eden veri kaynaklarını ve veri kümelerini oluşturmaktır. Her veri kaynağı veri bağlantısı bilgileri içerir. Her veri kümesi, veri kaynağından veri olarak kullanılacak alan kümesini tanımlayan bir sorgu komutu içerir. Her veri kümesinden alınan verileri görselleştirmek için tablo, matris, grafik veya harita gibi bir veri bölgesi ekleyin. Rapor işlendiğinde sorgular veri kaynağında çalıştırılır ve veri kümesine ilişkin sorgu sonuçlarını görüntülemek üzere her veri bölgesi gerektiği gibi genişletilir.  

[Power BI Rapor Oluşturucusu'nda sayfalandırılmış raporlar için tümleşik veri kaynağı oluşturmayı](paginated-reports-embedded-data-source.md) öğrenin.


##  <a name="BkMk_ReportDataTerms"></a> Terimleri  
  
- **Veri bağlantısı.** *Veri kaynağı* olarak da bilinir. Veri bağlantısı bir ad ve bağlantı türüne bağımlı olan bağlantı özellikleri içerir. Tasarımı gereği veri bağlantısı kimlik bilgilerini içermez. Dış veri kaynağından hangi verilerin alınacağını veri bağlantısı belirtmez. Bunu yapmak için veri kümesini oluştururken siz bir sorgu belirtirsiniz.  
  
- **Bağlantı dizesi.** Bağlantı dizesi, veri kaynağına bağlanmak için gereken bağlantı özelliklerinin dize sürümüdür. Bağlantı özellikleri veri bağlantısı türüne göre değişiklik gösterir.  
  
- **Eklenmiş veri kaynağı.** *Rapora özgü veri kaynağı* olarak da bilinir. Raporda tanımlanan ve yalnızca o rapor tarafından kullanılan veri kaynağı.  
  
- **Kimlik bilgileri.** Kimlik bilgileri dış verilere erişmenize izin verilmesi için sağlanması gereken kimlik doğrulama bilgileridir.  
  
##  <a name="BkMk_ReportDataTips"></a> Rapor verilerini belirtme ipuçları

 Rapor verileri stratejinizi tasarlamak için aşağıdaki bilgilerden yararlanın.  
  
- **Verileri filtreleme** Rapor verileri sorguda veya raporda filtrelenebilir. Veri kümelerini ve sorgu değişkenlerini kullanarak basamaklı parametreler oluşturabilir ve kullanıcıya binlerce seçenekten daha başa çıkılabilir bir seçenek kümesine daraltma olanağı sunabilirsiniz. Tablo veya grafikteki verileri parametre değerlerine veya belirttiğiniz başka değerlere göre filtreleyebilirsiniz.  
  
- **Parametreler** Sorgu değişkenleri içeren veri kümesi sorgu komutları, eşleşen rapor parametrelerini otomatik olarak oluşturur. Parametreleri el ile de oluşturabilirsiniz. Raporu görüntülediğinizde rapor araç çubuğunda parametreler görüntülenir. Kullanıcılar değerleri seçerek rapor verilerini veya raporun görünümünü denetleyebilir. Rapor verilerini belirli hedef kitlelere göre özelleştirmek için, aynı rapor tanımına bağlı farklı varsayılan değerleri olan bir dizi rapor parametresi oluşturabilir veya yerleşik **UserID** alanını kullanabilirsiniz. 
  
- **Verileri gruplandırma ve toplama** Rapor verileri sorguda veya raporda gruplandırılabilir ve toplanabilir. Sorgudaki verileri toplarsanız, rapordaki değerleri anlamlı sınırlar içinde birleştirmeye devam edebilirsiniz.  
  
- **Verileri sıralama** Rapor verileri sorguda veya raporda sıralanabilir. Tablolarda, kullanıcının sıralama düzenini denetlemesi için etkileşimli bir sıralama düğmesi de ekleyebilirsiniz.  
  
- **İfadeye dayalı veriler** Rapor özelliklerinin çoğu ifadeye dayalı olabileceği ve ifadeler de veri kümesi alanlarına ve rapor parametrelerine başvurular içerebileceği için, raporun verilerini ve görünümünü denetleyen güçlü ifadeler yazabilirsiniz. Parametreler tanımlayarak kullanıcıya gördükleri verileri denetleme olanağı sağlayabilirsiniz.  
  
- **Veri kümesindeki verileri görüntüleme** Veri kümesindeki veriler normalde tablo ve grafik gibi bir veya birden çok veri bölgesinde görüntülenir.  
  
- **Birden çok veri kümesindeki verileri görüntüleme** Bir veri bölgesinde tek bir veri kümesine dayanan ve başka veri kümelerindeki değerleri veya toplamları arayan ifadeler yazabilirsiniz. Tek bir veri kümesine dayanan bir tabloya, başka bir veri kaynağından veriler görüntülemek için alt raporlar ekleyebilirsiniz.  
  
 Aşağıdaki liste raporun veri kaynaklarını tanımlamanıza yardımcı olacaktır.  
  
- Kuruluşunuzun yazılım veri katmanı mimarisini ve veri türlerinden kaynaklanan olası sorunları anlayın. Veri uzantılarının ve veri işleme uzantılarının sorgu sonuçlarını nasıl etkileyebileceğini anlayın. Verilerin kaynağı ve veri sağlayıcıları arasında ve rapor tanımı (.dl) dosyasında depolanan veri türleri farklılık gösterir.  
  
- Veri kaynakları ve veri kümeleri raporda yazılır ve Power BI hizmetinde yayımlanır. Bunlar yayımlandıktan sonra kimlik bilgilerini doğrudan Power BI hizmetinde veya kendi Enterprise Gateway'inizde yapılandırabilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)  
- [Sayfalandırılmış raporlar için veri alma kılavuzu](../guidance/report-paginated-data-retrieval.md)
