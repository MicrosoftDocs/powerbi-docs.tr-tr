---
title: "SQL Database Auditing içerik paketi"
description: "Power BI için SQL Database Auditing içerik paketi"
services: powerbi
documentationcenter: 
author: SarinaJoan
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: eec1af16156e4d4180dd130f4dd285bb78b19903
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="sql-database-auditing-content-pack-for-power-bi"></a>Power BI için SQL Database Auditing içerik paketi
Power BI için Azure [SQL Database Auditing](http://azure.microsoft.com/documentation/articles/sql-database-auditing-get-started/) içerik paketi, veritabanınızdaki etkinlikleri anlamanıza, işle ilgili endişeleri ifade eden tutarsızlıklar ve anomaliler veya şüphe duyulan güvenlik ihlalleri hakkında daha fazla bilgi almanıza olanak sağlar. 

Power BI için [SQL Database Auditing içerik](https://app.powerbi.com/getdata/services/sql-db-auditing) paketine bağlanın.

>[!NOTE]
>İçerik paketi, adında "AuditLogs" bulunan tüm tablolardaki verileri içeri aktarıp "AuditLogs" olarak adlandırılan tek bir veri modeli tablosuna ekler. Son 250.000 olay eklenir ve veriler günlük olarak yenilenir.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmındaki **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getdata.png) 
2. Hizmetler kutusundaki Al düğmesini seçin.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getservices.png) 
3. **SQL Database Auditing** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-azure-sql-database-auditing/sqldbaudit.png)
4. Bağlan: SQL Database Auditing penceresinde:
   
   - Günlüklerinizin depolandığı Azure Tablo Depolaması hesabının adını veya URL'sini girin.
   
   - Bağlanmak istediğiniz SQL sunucusunun adını girin. Tüm sunuculara ilişkin denetim günlüklerini yüklemek için "\*" yazın.
   
   - Bağlanmak istediğiniz SQL veritabanının adını girin. Tüm veritabanlarına ilişkin denetim günlüklerini yüklemek için "\*" yazın.
   
   - Almak istediğiniz günlükleri içeren Azure tablosunun adını girin. Adında "AuditLogs" bulunan tüm tablolardaki denetim günlüklerini yüklemek için "\*" yazın.
   
   >[!IMPORTANT]
   >Tüm denetim günlükleri tek bir tabloda depolanıyor olsa da performans açısından daima açık bir tablo adı belirtilmesi önerilir.
   
   - Hangi tarihten sonrasına ait denetim günlüklerini almak istediğinizi belirtin. Denetim günlüklerini alt süre sınırı olmadan yüklemek için "\*", son güne ait denetim günlüklerini yüklemek için "1d" yazın.
   
   - Hangi tarihe kadar olan denetim günlüklerini almak istediğinizi belirtin. Denetim günlüklerini üst süre sınırı olmadan yüklemek için "\*" yazın.
   
   ![](media/service-connect-to-azure-sql-database-auditing/dbauditing_param.png)
5. Kimlik Doğrulaması Yöntemi olarak **Anahtar**’ı seçin, **Hesap Anahtarı** bilgisini sağlayın ve \> **Oturum açın** seçeneğini belirleyin.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqlauditing3.png)
6. Veriler Power BI tarafından içeri aktarıldıktan sonra sol gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz. Yeni öğeler sarı yıldız işareti \* ile gösterilir.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqldbauditingnewdash.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="next-steps"></a>Sonraki adımlar
[Power BI için veri alma](service-get-data.md)
[Power BI ile çalışmaya başlama](service-get-started.md)
