---
title: Power BI Sayfalandırılmış Rapor Oluşturucusu
description: Power BI Sayfalandırılmış Rapor Oluşturucusu, sayfalandırılmış raporlar yazmaya yarayan bir araçtır.
ms.date: 11/27/2019
ms.service: powerbi
ms.subservice: report-builder
featuredvideoid: 78TZeiEhveY
ms.topic: conceptual
ms.assetid: 55bf4f9c-d037-412f-ae57-3fc39ce32fa5
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: faba36a609abd94b2439006fbbcf01a1d193c585
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2020
ms.locfileid: "74565283"
---
# <a name="power-bi-paginated-report-builder"></a>Power BI Sayfalandırılmış Rapor Oluşturucusu

 Power BI Sayfalandırılmış Rapor Oluşturucusu, sayfalandırılmış raporlar yazmaya yarayan bir araçtır.  Sayfalandırılmış rapor tasarlarken hangi verilerin nereden alınacağını ve nasıl görüntüleneceğini belirten bir rapor tanımı oluşturursunuz. Raporu çalıştırdığınızda, rapor işlemcisi belirttiğiniz rapor tanımını alır, verileri alır ve raporu oluşturmak için rapor düzeni ile birleştirir. Rapor Oluşturucusu'nda raporunuzun önizlemesini görüntüleyebilirsiniz. Daha sonra raporunuzu Power BI hizmetinde yayımlayın.

[Uygulamalı laboratuvar: Microsoft Power BI sayfalandırılmış raporu oluşturma](https://www.microsoft.com/handsonlabs/selfpacedlabs/details/SQ00208)’yı deneyin.

Videolardan öğrenmeyi mi tercih ediyorsunuz? Power BI Baş Program Yöneticisi Chris Finlan’ın YouTube'daki Power BI sayfalandırılmış raporlar video serisine göz atın.

<iframe width="560" height="315" src="https://www.youtube.com/embed/78TZeiEhveY?list=PLx7LcKtN_gq-JVzM6L8xNNxX7kts-KflJ" frameborder="0" allowfullscreen></iframe>

Aşağıdaki sayfalandırılmış raporda satır ve sütun grupları, mini grafikler, göstergeler ve köşe hücresinde özet pasta grafiğiyle bir matris bulunur. Bu matrise renklerle ve daire boyutlarıyla gösterilen iki coğrafi veri kümesinin olduğu bir harita eşlik eder.  

![Power BI hizmetinde sayfalandırılmış rapor](media/report-builder-power-bi/report-builder-get-started-paginated-report.png)

##  <a name="JumpStartReptCreation"></a> Rapor oluşturmaya hızlı başlangıç yapın  
 
-   **Tablo, Matris veya Grafik sihirbazıyla başlayın**. Veri kaynağı bağlantısı oluşturun, alanları sürükleyip bırakarak bir veri kümesi sorgusu oluşturun, bir düzen ve stil seçin ve raporunuzu özelleştirin.  
  
-   **Harita sihirbazı ile başlayıp** coğrafi veya geometrik bir arka plana göre toplu verileri gösteren raporlar oluşturun. Harita verileri bir Transact-SQL sorgusundaki uzamsal veriler ya da bir Environmental Systems Research Institute, Inc. (ESRI) şekil dosyaları olabilir. Ayrıca bir Microsoft Bing harita parçası arka planı da ekleyebilirsiniz.  

##  <a name="DesignRept"></a> Raporunuzu tasarlama  
  
-   **Tablo, matris, grafik ve serbest biçimli rapor düzenleri olan sayfalandırılmış raporlar oluşturun.** Sütun tabanlı veriler için tablo raporları, özetlenmiş veriler için matris raporları (çapraz veya PivotTable raporları), grafik verileri için grafik raporları ve diğer her şey için serbest biçimli raporları oluşturun. Dinamik Web tabanlı uygulamalar için raporlara listeler, grafikler ve denetimlerle birlikte başka raporlar ve çizelgeler de eklenebilir.  
  
-   **Çeşitli veri kaynaklarından rapor.** SQL Server ve Analysis Services'ten, Oracle, Power BI veri kümelerinden ve diğer veritabanlarından ilişkisel ve çok boyutlu veriler kullanan raporlar oluşturabilirsiniz.  
  
-   **Mevcut raporları değiştirin.** Rapor Oluşturucusu'nu kullanarak SQL Server Veri Araçları (SSDT) Rapor Tasarımcısı'nda oluşturulmuş olan raporları özelleştirebilir ve güncelleştirebilirsiniz.  
  
-   **Verilerinizi değiştirin**. Verileri filtreleyin, gruplandırın ve sıralayın ya da formüller veya ifadeler ekleyin.  

-   **Grafikler, ölçerler, mini grafikler ve göstergeler ekleyin**. Verileri görsel biçimde özetleyin ve toplanmış çok fazla bilgiyi bir bakışta görünür hale getirin.  
  
-   **Etkileşimli özellikler ekleyin**. Alt raporlara ve detaylandırma raporlarına belge haritaları, göster/gizle düğmeleri ve detaylandırma bağlantıları gibi özellikler ekleyebilirsiniz. Özelleştirilmiş görünümler için verileri filtrelemek üzere parametreler ve filtreler kullanın.  
  
-   **Resimler ekleyin veya bunlara başvurun**, ayrıca dış içerik de dahil olmak üzere diğer kaynakları ekleyin ya da başvurun.  
  
##  <a name="ManageRpt"></a> Raporunuzu yönetme  
  
-   **Raporunuzun tanımını** bilgisayarınıza veya rapor sunucusuna kaydedin; burada tanımı yönetebilir ve diğer kişilerle paylaşabilirsiniz.  
  
-   **Sunu biçimini** raporunuzu açarken veya raporu açtıktan sonra seçin. Web tabanlı, sayfa odaklı ve masaüstü uygulaması biçimlerini seçebilirsiniz. Biçimler MHTML, PDF, XML, CSV, Word ve Excel'dir.  
  
-   **Abonelikleri ayarlayın.** Raporu Power BI hizmetinde yayımladıktan sonra, belirli bir zamanda çalıştırılmak üzere yapılandırabilir ve e-posta aboneliği olarak gönderebilirsiniz.  

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
- [Uygulamalı laboratuvar: Microsoft Power BI sayfalandırılmış raporu oluşturma](https://www.microsoft.com/handsonlabs/selfpacedlabs/details/SQ00208)
- Power BI Baş Program Yöneticisi Chris Finlan’ın YouTube'daki [Power BI sayfalandırılmış raporlar video serisini](https://www.youtube.com/watch?v=78TZeiEhveY&list=PLx7LcKtN_gq-JVzM6L8xNNxX7kts-KflJ) izleyin