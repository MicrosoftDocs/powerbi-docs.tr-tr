---
title: Yenileme için desteklenmeyen veri kaynaklarıyla ilgili sorunları giderme
description: Yenileme için desteklenmeyen veri kaynaklarıyla ilgili sorunları giderme
author: maggiesMSFT
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 12/06/2017
ms.author: maggies
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: e3fe8626001972acc0b7555f37844b5abb62753b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "74791986"
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>Yenileme için desteklenmeyen veri kaynaklarıyla ilgili sorunları giderme
Veri kümelerini zamanlanmış yenileme için yapılandırmaya çalışırken bir hatayla karşılaşabilirsiniz.

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

Bu, Power BI Desktop'ta kullandığınız veri kaynağı için yenileme desteği sunulmaması halinde ortaya çıkar. Kullanmakta olduğunuz veri kaynağını bulmanız ve [Power BI'da verileri yenileme](refresh-data.md) makalesinde bulunan, desteklenen veri kaynakları listesinde aramanız gerekir. 

## <a name="find-the-data-source"></a>Veri kaynağını bulma
Hangi veri kaynağının kullanıldığından emin değilseniz Power BI Desktop'ta aşağıdaki adımları uygulayarak veri kaynağını bulabilirsiniz.  

1. Power BI Desktop'ta, **Rapor** bölmesinde bulunduğunuzdan emin olun.  
   ![Masaüstü rapor bölmesi](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. Şerit çubuğunda **Sorguları Düzenle**'yi seçin.  
   ![Sorguları düzenle](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. **Gelişmiş Düzenleyici** seçeneğini belirleyin.  
   ![Gelişmiş düzenleyici](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. Kaynak için belirtilen sağlayıcıyı not edin.  Bu örnekteki sağlayıcı Active Directory'dir.  
   ![Veri kaynağı sağlayıcı](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. Sağlayıcıyı, [Power BI veri kaynakları](power-bi-data-sources.md) makalesindeki desteklenen veri kaynakları listesinde arayın.

## <a name="next-steps"></a>Sonraki adımlar
[Veri Yenileme](refresh-data.md)  
[Power BI Gateway - Personal](service-gateway-personal-mode.md)  
[Şirket içi veri ağ geçidi](service-gateway-onprem.md)  
[Şirket içi veri ağ geçidi sorunlarını giderme](service-gateway-onprem-tshoot.md)  
[Power BI Gateway - Personal ile ilgili sorunları giderme](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

