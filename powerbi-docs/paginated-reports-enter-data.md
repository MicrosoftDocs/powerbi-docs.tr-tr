---
title: Rapor Oluşturucusu'nda verileri doğrudan sayfalandırılmış bir rapora girme (Önizleme)
description: Bu makalede, Rapor Oluşturucusu'nda verileri doğrudan sayfalandırılmış rapora nasıl girebileceğiniz gösterilir.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 11/19/2018
ms.author: maggies
ms.openlocfilehash: 9556a501832502a8d5653967408b9fac8d0704a5
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54295668"
---
# <a name="enter-data-directly-in-a-paginated-report-in-report-builder-preview---power-bi"></a>Rapor Oluşturucusu'nda verileri doğrudan sayfalandırılmış bir rapora girme (Önizleme) - Power BI

Bu makalede, SQL Server 2016 Rapor Oluşturucusu'nun yeni sürümünde sağlanan ve verileri doğrudan RDL raporuna eklenmiş bir veri kümesi olarak girmenize olanak tanıyan özelliği öğreneceksiniz.  Bu özellik, Power BI Desktop'a benzer. Verileri doğrudan raporunuzdaki veri kümesine yazabilir veya Microsoft Excel gibi başka bir programdan yapıştırabilirsiniz. Verileri girerek veri kümesini oluşturduktan sonra, bunu aynı oluşturduğunuz diğer eklenmiş veri kümeleri gibi kullanabilirsiniz. Ayrıca, birden çok tablo ekleyebilir ve bir tabloyu diğeri için filtre olarak kullanabilirsiniz. Bu özellik rapor parametreleri gibi raporunuzda kullanmanız gerekebilecek küçük, statik veri kümelerinde özellikle kullanışlıdır.
 
## <a name="prerequisites"></a>Önkoşullar

- Verileri doğrudan sayfalandırılmış rapora girmek için, [Microsoft İndirme Merkezi'nden Rapor Oluşturucusu](https://www.microsoft.com/download/details.aspx?id=53613)'nun yeni sürümünü yükleyin. 
- Sayfalandırılmış raporunuzu Power BI hizmetine kaydetmek için, [Power BI Pro hesabınız](service-self-service-signup-for-power-bi.md) ve [Power BI Premium kapasitesindeki](service-premium.md) bir çalışma alanına yazma erişiminiz olmalıdır.
- Sayfalandırılmış raporunuzu bir rapor sunucusuna kaydetmek için, [RsReportServer.config dosyasını düzenleme](#upload-the-paginated-report-to-a-report-server) izinleriniz olmalıdır.

## <a name="get-started"></a>Başlangıç

Rapor Oluşturucusu'nu indirip yükledikten sonra, raporunuza eklenmiş bir veri kaynağı ve veri kümesi yerleştirmek için kullandığınız iş akışının aynısını izlersiniz. Aşağıdaki yordamda, **Veri Kaynakları**'nın altında yeni bir seçenek görürsünüz: **Verileri Girin**.  Bu veri kaynağını raporda tek bir kez ayarlamanız yeterlidir. Bundan sonra, girilen verilerden (ayrı veri kümeleri olarak) hepsi bu tek veri kaynağını kullanan birden çok tablo oluşturabilirsiniz.

1. **Rapor Verileri** bölmesinde **Yeni** > **Veri Kümesi**’ni seçin.

    ![Rapor Oluşturucusu Yeni Veri Kümesi](media/paginated-reports-enter-data/paginated-new-dataset.png)

1. **Veri Kümesi Özellikleri** iletişim kutusunda **Raporumda katıştırılmış veri kümesini kullan**'ı seçin.

1. **Veri kaynağı**'nın yanında **Yeni**'yi seçin.

    ![Yeni eklenmiş veri kaynağı](media/paginated-reports-enter-data/paginated-new-data-source.png)

1. **Veri Kaynağı Özellikleri** iletişim kutusunda **Raporumda katıştırılmış bağlantıyı kullan**'ı seçin.
2. **Bağlantı türünü seçin** kutusunda **VERİ GİR** > **Tamam**'ı seçin.

    ![VERİ GİR veri kaynağı](media/paginated-reports-enter-data/paginated-data-source-properties-enter-data.png)

1. **Veri Kümesi Özellikleri** iletişim kutusuna dönüp **Sorgu Tasarımcısı**'nı seçin.
2. **Sorgu Tasarımcısı** bölmesinde, sağ tıklayıp verilerinizi tabloya yapıştırın.

    ![Sorgu Tasarımcısı'nda verileri girme](media/paginated-reports-enter-data/paginated-enter-data.png)

1. Sütun adlarını ayarlamak için, her **NewColumn** öğesine çift tıklayın ve sütun adını yazın.

    ![Sütun adlarını ayarlama](media/paginated-reports-enter-data/paginated-column-name.png)

1. İlk satır özgün verilerden sütun başlıklarını içeriyorsa, sağ tıklayın ve bunları silin.
    
9. Varsayılan olarak, her sütunun veri türü Dize'dir. Veri türünü değiştirmek için, sütun başlığına sağ tıklayın > **Türü Değiştir**'e tıklayın ve bunu Tarih veya Kayan gibi farklı bir veri türüne ayarlayın.

    ![Veri türünü değiştirme](media/paginated-reports-enter-data/paginated-data-type.png)

1. Tabloyu oluşturmayı bitirdiğinizde **Tamam**'ı seçin.  

    Oluşturulan sorgu bir XML veri kaynağıyla görebileceğiniz sorguyla aynıdır. Arka planda, güvenli veri sağlayıcısı olarak XML kullanıyoruz.  Bu senaryoya da olanak tanımak için bunun amacını yeniden belirledik.

    ![XML veri yapısı](media/paginated-reports-enter-data/paginated-xml-data.png)

12. **Veri Kümesi Özellikleri** iletişim kutusunda **Tamam**'ı seçin.

13. Veri kaynağınızı ve veri kümenizi **Rapor Verileri** bölmesinde görürsünüz.

    ![Rapor Verileri bölmesinde veri kümesi](media/paginated-reports-enter-data/paginated-report-data-pane.png)

Raporunuzdaki veri görselleştirmeleri için, veri kümenizi temel olarak kullanabilirsiniz. Ayrıca bir veri kümesi daha ekleyebilir ve bunun için aynı veri kaynağını kullanabilirsiniz.

## <a name="upload-the-paginated-report-to-the-power-bi-service"></a>Power BI hizmetinde sayfalandırılmış raporu karşıya yükleme

Artık sayfalandırılmış raporlar Power BI hizmetinde önizlemede desteklendiği için, sayfalandırılmış raporunuzu Premium kapasiteye yükleyebilirsiniz. Ayrıntılar için bkz. [Sayfalandırılmış raporu karşıya yükleme](paginated-reports-save-to-power-bi-service.md#upload-a-paginated-report).

## <a name="upload-the-paginated-report-to-a-report-server"></a>Sayfalandırılmış raporu rapor sunucusuna yükleme

Sayfalandırılmış raporunuzu Power BI Rapor Sunucusu'na, SQL Server Reporting Services 2016 veya 2017 rapor sunucusuna da yükleyebilirsiniz. Bunu yapmadan önce, aşağıdaki öğeyi ek veri uzantısı olarak RsReportServer.config dosyanıza eklemeniz gerekir. Herhangi bir sorunla karşılaşma olasılığına karşı, değişikliği yapmadan önce RsReportServer.config dosyanızı yedekleyin.

```
<Extension Name=”ENTERDATA” Type=”Microsoft.ReportingServices.DataExtensions.XmlDPConnection,Microsoft.ReportingServices.DataExtensions”>
<Configuration>
<ConfigName>ENTERDATA</ConfigName>
</Configuration>
</Extension>
```

Dosyayı düzenledikten sonra, yapılandırma dosyasındaki veri sağlayıcıları listesi şöyle görünmelidir:

![RsReportServer yapılandırma dosyası](media/paginated-reports-enter-data/paginated-rsreportserver-config-file.png)

İşte bu kadar. Artık bu yeni işlevselliği kullanan raporları rapor sunucunuzda yayımlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir? (Önizleme)](paginated-reports-report-builder-power-bi.md)
- [Power BI Rapor Sunucusu nedir?](report-server/get-started.md)
