---
title: Power BI Rapor Oluşturucusu
description: Power BI Report Builder, sayfalandırılmış raporlar yazmaya yarayan bir araçtır.
author: maggiesMSFT
ms.author: maggies
ms.date: 07/08/2020
ms.service: powerbi
ms.subservice: report-builder
featuredvideoid: 78TZeiEhveY
ms.topic: conceptual
ms.assetid: 55bf4f9c-d037-412f-ae57-3fc39ce32fa5
ms.openlocfilehash: ce45260c536733dde9dcfe7c654ed4f56c58c7ea
ms.sourcegitcommit: 1872a167d1e4d731ad00cf8a6d951c31aa54bcce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/28/2021
ms.locfileid: "98925750"
---
# <a name="power-bi-report-builder"></a>Power BI Rapor Oluşturucusu

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-service](../includes/yes-service.md)] [!INCLUDE [yes-paginated](../includes/yes-paginated.md)] [!INCLUDE [yes-premium](../includes/yes-premium.md)] [!INCLUDE [no-desktop](../includes/no-desktop.md)] 

Power BI Rapor Oluşturucusu, Power BI hizmetinde yayımlayabileceğiniz sayfalandırılmış raporlar yazmaya yarayan bir araçtır.  Sayfalandırılmış rapor tasarlarken hangi verilerin nereden alınacağını ve nasıl görüntüleneceğini belirten bir rapor tanımı oluşturursunuz. Raporu çalıştırdığınızda, rapor işlemcisi belirttiğiniz rapor tanımını alır, verileri alır ve raporu oluşturmak için rapor düzeni ile birleştirir. Rapor Oluşturucusu'nda raporunuzun önizlemesini görüntüleyebilirsiniz. Daha sonra raporunuzu Power BI hizmetinde yayımlayın.
 
Yazmaya başlamaya hazır mısınız? Microsoft İndirme Merkezi’nden [Power BI Rapor Oluşturucusu’nu yükleyin](https://go.microsoft.com/fwlink/?linkid=2086513).

Videolardan öğrenmeyi mi tercih ediyorsunuz? [Video temelli kurs: Bir Gündeki Power BI Sayfalandırılmış Raporları](../learning-catalog/paginated-reports-online-course.md)’na göz atın.

Aşağıdaki sayfalandırılmış raporda satır ve sütun grupları, mini grafikler, göstergeler ve köşe hücresinde özet pasta grafiğiyle bir matris bulunur. Bu matrise renklerle ve daire boyutlarıyla gösterilen iki coğrafi veri kümesinin olduğu bir harita eşlik eder.  

![Power BI hizmetinde sayfalandırılmış rapor](media/report-builder-power-bi/report-builder-get-started-paginated-report.png)

##  <a name="jump-start-report-creation"></a><a name="JumpStartReptCreation"></a> Rapor oluşturmaya hızlı başlangıç yapın  
 
-   **Tablo, Matris veya Grafik sihirbazıyla başlayın**. Veri kaynağı bağlantısı oluşturun, alanları sürükleyip bırakarak bir veri kümesi sorgusu oluşturun, bir düzen ve stil seçin ve raporunuzu özelleştirin.  
  
-   **Harita sihirbazı ile başlayıp** coğrafi veya geometrik bir arka plana göre toplu verileri gösteren raporlar oluşturun. Harita verileri bir Transact-SQL sorgusundaki uzamsal veriler ya da bir Environmental Systems Research Institute, Inc. (ESRI) şekil dosyaları olabilir. Ayrıca bir Microsoft Bing harita parçası arka planı da ekleyebilirsiniz.  

##  <a name="design-your-report"></a><a name="DesignRept"></a> Raporunuzu tasarlama  
  
-   **Tablo, matris, grafik ve serbest biçimli rapor düzenleri olan sayfalandırılmış raporlar oluşturun.** Sütun tabanlı veriler için tablo raporları, özetlenmiş veriler için matris raporları (çapraz veya PivotTable raporları), grafik verileri için grafik raporları ve diğer her şey için serbest biçimli raporları oluşturun. Dinamik Web tabanlı uygulamalar için raporlara listeler, grafikler ve denetimlerle birlikte başka raporlar ve çizelgeler de eklenebilir.  
  
-   **Çeşitli veri kaynaklarından rapor.** SQL Server ve Analysis Services'ten, Oracle, Power BI veri kümelerinden ve diğer veritabanlarından ilişkisel ve çok boyutlu veriler kullanan raporlar oluşturabilirsiniz.  
  
-   **Mevcut raporları değiştirin.** Rapor Oluşturucusu'nu kullanarak SQL Server Veri Araçları (SSDT) Rapor Tasarımcısı'nda oluşturulmuş olan raporları özelleştirebilir ve güncelleştirebilirsiniz.  
  
-   **Verilerinizi değiştirin**. Verileri filtreleyin, gruplandırın ve sıralayın ya da formüller veya ifadeler ekleyin.  

-   **Grafikler, ölçerler, mini grafikler ve göstergeler ekleyin**. Verileri görsel biçimde özetleyin ve toplanmış çok fazla bilgiyi bir bakışta görünür hale getirin.  
  
-   **Etkileşimli özellikler ekleyin**. Alt raporlara ve detaylandırma raporlarına belge haritaları, göster/gizle düğmeleri ve detaylandırma bağlantıları gibi özellikler ekleyebilirsiniz. Özelleştirilmiş görünümler için verileri filtrelemek üzere parametreler ve filtreler kullanın.  
  
-   **Resimler ekleyin veya bunlara başvurun**, ayrıca dış içerik de dahil olmak üzere diğer kaynakları ekleyin ya da başvurun.  
  
##  <a name="manage-your-report"></a><a name="ManageRpt"></a> Raporunuzu yönetme  
  
-   **Raporunuzun tanımını** bilgisayarınıza veya rapor sunucusuna kaydedin; burada tanımı yönetebilir ve diğer kişilerle paylaşabilirsiniz.  
  
-   **Sunu biçimini** raporunuzu açarken veya raporu açtıktan sonra seçin. Web tabanlı, sayfa odaklı ve masaüstü uygulaması biçimlerini seçebilirsiniz. Biçimler MHTML, PDF, XML, CSV, Word ve Excel'dir.  
  
-   **Abonelikleri ayarlayın.** Raporu Power BI hizmetinde yayımladıktan sonra, belirli bir zamanda çalıştırılmak üzere yapılandırabilir ve e-posta aboneliği olarak gönderebilirsiniz.  

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
- [Video temelli kurs: Bir Gündeki Power BI Sayfalandırılmış Raporları](../learning-catalog/paginated-reports-online-course.md)
