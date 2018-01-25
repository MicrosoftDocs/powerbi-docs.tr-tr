---
title: "Power BI ile Azure Audit Logs'a bağlanma"
description: "Power BI için Azure Audit Logs"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: 9a00183a81e549f873fab53807072b1beeaec7c2
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-azure-audit-logs-with-power-bi"></a>Power BI ile Azure Audit Logs'a bağlanma
Azure Audit Logs içerik paketini kullanarak, denetim günlüklerinde depolanan bilgileri çözümleyebilir ve görselleştirebilirsiniz. Power BI verilerinizi alır, kullanıma hazır bir pano ve söz konusu verilere dayalı raporlar oluşturur.

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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
Azure Audit Logs içerik paketi için Azure Portal'da Denetim Günlükleri erişimi gerekir. [Burada](https://azure.microsoft.com/en-us/documentation/articles/insights-debugging-with-events/) daha ayrıntılı bilgilere ulaşabilirsiniz.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Abonelik kimliğinizi bulmanın iki kolay yolu vardır.

1. https://portal.azure.com -&gt; Gözat -&gt; Abonelikler -&gt; ABONELİK KİMLİĞİ'ne giderek
2. https://manage.windowsazure.com -&gt; Ayarlar -&gt; Abonelik Kimliği'ne giderek

Abonelik kimliğiniz yukarıda bulunan \#4 numaralı adımdaki örneğe benzer şekilde sayılardan ve karakterlerden oluşan uzun bir dizidir. 

## <a name="troubleshooting"></a>Sorun giderme
Bir kimlik bilgileri hatası veya geçeriz kimlik bilgileri nedeniyle yenileme hatasıyla karşılaşırsanız lütfen Azure Audit Logs içerik paketinin tüm örneklerini silin ve yeniden bağlanmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)  
[Power BI - Temel Kavramlar](service-basic-concepts.md)  

