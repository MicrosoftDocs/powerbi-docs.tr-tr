---
title: Power BI hizmetinde sayfalandırılmış raporlar için tümleşik veri kaynakları (Önizleme)
description: Bu makalede, Power BI hizmetindeki sayfalandırılmış bir rapor için tümleşik bir veri kaynağı oluşturma ve değiştirme işlemini öğreneceksiniz.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 11/05/2018
ms.openlocfilehash: 340b4d26b8beed4dfda5f7af4dc949088f3857ae
ms.sourcegitcommit: d2805894fd372c35e11d519f724de2be98407fda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59070034"
---
# <a name="create-an-embedded-data-source-for-paginated-reports-in-the-power-bi-service-preview"></a>Power BI hizmetinde sayfalandırılmış raporlar için tümleşik veri kaynağı oluşturma (Önizleme)

Bu makalede, Power BI hizmetindeki sayfalandırılmış bir rapor için tümleşik bir veri kaynağı oluşturma ve değiştirme işlemini öğreneceksiniz. Tümleşik bir veri kaynağını tek bir raporda tanımlayabilir ve yalnızca o raporda kullanabilirsiniz. Şu anda, Power BI hizmetinde yayımlanan sayfalandırılmış raporlar için tümleşik veri kümeleri ve tümleşik veri kaynakları gereklidir ve şu veri kaynaklarına bağlanılabilir:

- Azure SQL Veritabanı ve Veri Ambarı
- SQL Server
- SQL Server Analysis Services
- Azure Analysis Services

Sayfalandırılmış raporlar, bir ağ geçidi üzerinden şirket içi veri kaynaklarına bağlanır. Raporu Power BI hizmetinde yayımladıktan sonra ağ geçidini ayarlayabilirsiniz. [Power BI ağ geçitleri](service-gateway-getting-started.md) hakkında daha fazla bilgi edinin. 

## <a name="create-an-embedded-data-source"></a>Eklenmiş veri kaynağı oluşturma
  
1. Rapor Oluşturucusu’nu açın.

1. Rapor Verileri bölmesindeki araç çubuğunda **Yeni** > **Veri Kaynağı**’nı seçin. **Veri Kaynağı Özellikleri** iletişim kutusu açılır.

    ![Yeni Veri Kaynağı](media/paginated-reports-embedded-data-source/power-bi-paginated-new-data-source.png)
  
2.  **Ad** metin kutusuna veri kaynağı için bir ad girin ya da varsayılan adı kabul edin.  
  
3.  **Raporuma katıştırılmış bağlantı kullan**’ı seçin.  
  
1.  **Bağlantı türünü seçin** listesinden bir veri kaynağı türü seçin. 

1.  Aşağıdaki yöntemlerden birini kullanarak bir bağlantı dizesi belirtin:  
  
    -   Bağlantı dizesini doğrudan **Bağlantı dizesi** metin kutusuna yazın. 
  
    -   Bağlantı dizesini değerlendiren bir ifade oluşturmak için ifade (**fx)** düğmesini seçin. **İfade** iletişim kutusunda, ifadeyi İfade bölmesine girin. **Tamam**'ı seçin. 
  
    -   2. adımda seçtiğiniz veri kaynağına ait **Bağlantı Özellikleri** iletişim kutusunu açmak için **Derleme**’yi seçin.  
  
        **Bağlantı Özellikleri** iletişim kutusundaki alanları veri kaynağı türüne uygun şekilde doldurun. Bağlantı özellikleri; veri kaynağı türünü, veri kaynağının adını ve kullanılacak kimlik bilgilerini içerir. Bu iletişim kutusunda değerleri belirttikten sonra, veri kaynağının kullanılabilir olduğunu doğrulamak ve belirttiğiniz kimlik bilgilerinin doğruluğunu onaylamak için **Bağlantıyı Sına**’yı seçin.  
  
4.  **Kimlik Bilgileri**’ni seçin.  
  
     Bu veri kaynağı için kullanılacak kimlik bilgilerini belirtin. Veri kaynağının sahibi, desteklenen kimlik bilgilerinin türünü seçer. Daha fazla bilgi için bkz. [Rapor Veri Kaynakları için Kimlik Bilgisi ve Bağlantı Bilgilerini Belirtme](https://docs.microsoft.com/sql/reporting-services/report-data/specify-credential-and-connection-information-for-report-data-sources).
  
5.  **Tamam**'ı seçin.  
  
     Veri kaynağı, Rapor Verileri bölmesinde görünür.  

## <a name="next-steps"></a>Sonraki adımlar

- [Sayfalandırılmış rapor için Power BI hizmetinde tümleşik veri kümesi oluşturma](paginated-reports-create-embedded-dataset.md)
- [Power BI Premium’da sayfalandırılmış raporlar nelerdir? (Önizleme)](paginated-reports-report-builder-power-bi.md)
