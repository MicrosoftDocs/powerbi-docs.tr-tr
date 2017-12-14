---
title: "Yenileme için desteklenmeyen veri kaynaklarıyla ilgili sorunları giderme"
description: "Yenileme için desteklenmeyen veri kaynaklarıyla ilgili sorunları giderme"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 93820e12602aa10754e3f905640c5e9b29cd7cc9
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2017
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>Yenileme için desteklenmeyen veri kaynaklarıyla ilgili sorunları giderme
Veri kümelerini zamanlanmış yenileme için yapılandırmaya çalışırken bir hatayla karşılaşabilirsiniz.

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

Bu, Power BI Desktop'ta kullandığınız veri kaynağı için yenileme desteği sunulmaması halinde ortaya çıkar. Kullanmakta olduğunuz veri kaynağını bulmanız ve [Power BI'da verileri yenileme](refresh-data.md) makalesinde bulunan, desteklenen veri kaynakları listesinde aramanız gerekir. 

## <a name="find-the-data-source"></a>Veri kaynağını bulma
Hangi veri kaynağının kullanıldığından emin değilseniz Power BI Desktop'ta aşağıdaki adımları uygulayarak veri kaynağını bulabilirsiniz.  

1. Power BI Desktop'ta, **Rapor** bölmesinde bulunduğunuzdan emin olun.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. Şerit çubuğunda **Sorguları Düzenle**'yi seçin.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. **Gelişmiş Düzenleyici** seçeneğini belirleyin.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. Kaynak için belirtilen sağlayıcıyı not edin.  Bu örnekteki sağlayıcı Active Directory'dir.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. Sağlayıcıyı, [Power BI'da verileri yenileme](refresh-data.md) makalesinde bulunan, desteklenen veri kaynakları listesinde arayın.  Active Directory'nin yenileme için desteklenen bir veri kaynağı olmadığını göreceksiniz.  

## <a name="next-steps"></a>Sonraki adımlar
[Veri Yenileme](refresh-data.md)  
[Power BI Gateway - Personal](personal-gateway.md)  
[Şirket içi veri ağ geçidi](service-gateway-onprem.md)  
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
[Power BI Gateway - Personal ile ilgili sorunları giderme](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

