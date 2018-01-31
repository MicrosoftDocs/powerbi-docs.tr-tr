---
title: "DirectQuery ile Azure SQL Veri Ambarı"
description: "DirectQuery ile Azure SQL Veri Ambarı"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.author: maghan
ms.openlocfilehash: 6f15cd13c26fcd120c92288c117bd9d97dd9e68b
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="azure-sql-data-warehouse-with-directquery"></a>DirectQuery ile Azure SQL Veri Ambarı
DirectQuery ile Azure SQL Veri Ambarı, Azure SQL Veri Ambarı'ndaki hazır verilerinizi ve ölçümlerinizi temel alan dinamik raporlar oluşturmanızı sağlar. DirectQuery ile, siz verileri keşfederken sorgular Azure SQL Veri Ambarı'nıza gerçek zamanlı olarak geri gönderilir. Bu özellik SQL Veri Ambarı'nın ölçeğiyle birleştirildiğinde kullanıcıların terabaytlarca veriden birkaç dakika içinde dinamik rapor oluşturmasını sağlar. Ayrıca, **Power BI'da aç** düğmesi sayesinde kullanıcılar el ile bilgi girmek zorunda kalmadan Power BI'ı doğrudan SQL Veri Ambarı hizmetlerine bağlayabilir.

SQL Veri Ambarı bağlayıcısını kullanırken:

* Bağlanırken tam sunucu adını belirtin (ayrıntılar için aşağıya bakın)
* Sunucu güvenlik duvarı kurallarının "Azure hizmetlerine erişime izin ver" şeklinde yapılandırıldığından emin olun
* Sütun seçme veya filtre ekleme gibi her işlem, veri ambarına doğrudan sorgu gönderir
* Kutucuklar yaklaşık olarak 15 dakikada bir yenilenecek şekilde ayarlanmıştır ve yenileme işleminin zamanlanması gerekmez.  Bu, bağlandığınızda Gelişmiş ayarlar bölümünden ayarlanabilir.
* Soru-Cevap, DirectQuery veri kümeleri için kullanılamaz
* Şema değişiklikleri otomatik olarak alınmaz

Bu kısıtlamalar ve notlar, biz deneyimleri iyileştirmeye devam ettikçe değişebilir. Bağlanma adımları aşağıda ayrıntılı şekilde verilmiştir.

## <a name="using-the-open-in-power-bi-button"></a>"Power BI'da aç" düğmesini kullanma
SQL Veri Ambarı'nızla Power BI arasında veri alışverişi yapmanın en kolay yolu Azure Preview Portal'daki **Power BI'da aç** düğmesidir. Bu düğme, sorunsuz bir şekilde Power BI'da yeni panolar oluşturmaya başlamanızı sağlar.

1. Başlamak için Azure Preview Portal'daki SQL Veri Ambarı örneğinize gidin. SQL Veri Ambarı'nın şu an için yalnızca Azure Preview Portal'da bulunduğunu lütfen unutmayın.
2. **Power BI'da aç** düğmesine tıklayın
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/openinpowerbi.png)
3. Oturumunuzu doğrudan açamazsak veya Power BI hesabınız yoksa oturum açmanız gerekir.
4. SQL Veri Ambarı bağlantı sayfası açılır ve SQL Veri Ambarı bilgileriniz önceden doldurulmuş şekilde gelir. Bağlantı oluşturmak için kimlik bilgilerinizi girip Bağlan'ı seçin.

## <a name="connecting-through-power-bi"></a>Power BI aracılığıyla bağlanma
SQL Veri Ambarı, Power BI Veri Al sayfasında da bulunmaktadır. 

1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.  
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/getdatabutton.png)
2. **Veritabanları**'ndan **Al**'ı seçin.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/databases.png)
3. **SQL Data Warehouse** \> **Bağlan**'ı seçin.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/azuresqldatawarehouseconnect.png)
4. Bağlanmak için gerekli bilgileri girin. Aşağıdaki **Parametreleri Bulma** bölümünde bu verileri Azure Portal'ınızın neresinde bulabileceğinizi gösterilmektedir.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/servername.png)
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/servernamewithadvanced.png)
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/username.png)
   
   > [!NOTE]
   > Kullanıcı adı, Azure SQL Veri Ambarı örneğinizde tanımlanmış bir kullanıcıdır.
   > 
   > 
5. Yıldız işaretiyle belirtilen yeni kutucuğu veya yeni oluşturulan veri kümesini seçerek veri kümesini detaylandırabilirsiniz. Bu veri kümesinin adı veritabanınızın adıyla aynı olur.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/dataset2.png)
6. Tüm tabloları ve sütunları keşfedebilirsiniz. Bir sütunu seçtiğinizde kaynağa sorgu gönderilerek görseliniz dinamik olarak oluşturulur. Filtreler de sorgulara çevrilip veri ambarınıza geri gönderilir. Bu görseller yeni bir rapora kaydedilerek panonuza sabitlenebilir.
   
    ![](media/service-azure-sql-data-warehouse-with-direct-connect/explore3.png)

## <a name="finding-parameter-values"></a>Parametre Değerlerini Bulma
Tam sunucu adınız ve veritabanınızın adı Azure Preview Portal'da bulunabilir. SQL Veri Ambarı'nın şu an için yalnızca Azure Preview Portal'da bulunduğunu lütfen unutmayın.

![](media/service-azure-sql-data-warehouse-with-direct-connect/azureportal.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)  
[Power BI için veri alma](service-get-data.md)  
[Azure SQL Veri Ambarı](https://azure.microsoft.com/en-us/documentation/services/sql-data-warehouse/)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

