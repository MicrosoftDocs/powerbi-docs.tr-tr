---
title: Power BI ile Azure Audit Logs'a bağlanma
description: Power BI için Azure Audit Logs
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: ee4b4616f264f0bd20e53d999b64301b2a7a693b
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70186054"
---
# <a name="connect-to-azure-audit-logs-with-power-bi"></a>Power BI ile Azure Audit Logs'a bağlanma
Azure Audit Logs içerik paketini kullanarak, denetim günlüklerinde depolanan bilgileri çözümleyebilir ve görselleştirebilirsiniz. Power BI verilerinizi alır, kullanıma hazır bir pano ve söz konusu verilere dayalı raporlar oluşturur.

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

[Azure Audit Logs içerik paketine bağlanın](https://app.powerbi.com/getdata/services/azure-audit-logs) veya Power BI ile [Azure Audit Logs tümleştirmesi](https://powerbi.microsoft.com/integrations/azure-audit-logs) hakkında daha fazla bilgi edinin.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.  
   
    ![](media/service-connect-to-azure-audit-logs/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.  
   
    ![](media/service-connect-to-azure-audit-logs/services.png) 
3. **Azure Audit Logs** > **Al** seçeneklerini belirleyin.  
   
   ![](media/service-connect-to-azure-audit-logs/azureauditlogs.png)
4. İstendiğinde, **Azure Abonelik Kimliğinizi** girin. [Abonelik Kimliğinizi](#FindingParams) bulma ile ilgili ayrıntılara bakın.   
   
    ![](media/service-connect-to-azure-audit-logs/parameters.png)
5. **Kimlik doğrulama yöntemi** için **OAuth2** \> **Oturum aç** seçeneklerini belirleyin.
   
    ![](media/service-connect-to-azure-audit-logs/creds.png)
6. Oturum açma işlemini tamamlamak için hesabınızın kimlik bilgilerini girin.
   
    ![](media/service-connect-to-azure-audit-logs/login.png)
7. Power BI, Azure Audit Logs verilerinizi alır ve kullanıma hazır bir pano ve rapor oluşturur. 
   
    ![](media/service-connect-to-azure-audit-logs/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="system-requirements"></a>Sistem Gereksinimleri
Azure Audit Logs içerik paketi için Azure portalda Denetim Günlükleri erişimi gerekir. [Burada](/azure/azure-resource-manager/resource-group-audit/) daha ayrıntılı bilgilere ulaşabilirsiniz.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Abonelik kimliğinizi bulmanın iki kolay yolu vardır.

1. [https://portal.azure.com](https://portal.azure.com ) -&gt; Gözat - &gt; Abonelikleri - &gt; Abonelik Kimliği bölümünden
2. [https://manage.windowsazure.com](https://manage.windowsazure.com ) -&gt; Ayarları  -&gt; Abonelik Kimliği bölümünden

Abonelik kimliğiniz yukarıda bulunan \#4 numaralı adımdaki örneğe benzer şekilde sayılardan ve karakterlerden oluşan uzun bir dizidir. 

## <a name="troubleshooting"></a>Sorun giderme
Bir kimlik bilgileri hatası veya geçeriz kimlik bilgileri nedeniyle yenileme hatasıyla karşılaşırsanız Azure Audit Logs içerik paketinin tüm örneklerini silin ve yeniden bağlanmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI nedir?](power-bi-overview.md)  
[Power BI hizmetinde tasarımcılar için temel kavramlar](service-basic-concepts.md)  

