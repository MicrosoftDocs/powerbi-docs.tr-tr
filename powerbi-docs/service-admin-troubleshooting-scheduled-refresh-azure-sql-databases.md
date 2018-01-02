---
title: "Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme"
description: "Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 0b2f5da3fccd1741cb5a9ea02a1aebbd8fbac96f
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2017
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
Ayrıntılı zamanlanmış yenileme adımları için bkz. [Power BI'da verileri yenileme](refresh-data.md).

Azure SQL Veritabanı için zamanlanmış yenilemeyi ayarlama sırasında kimlik bilgilerini düzenlerken hata kodu 400 ile karşılaşıyorsanız uygun güvenlik duvarı kurallarını ayarlamak için aşağıdaki işlemleri gerçekleştirmeyi deneyin:

1. Azure yönetim portalında oturum açın
2. Yenileme yapılandırması yaptığınız Azure SQL sunucusuna gidin
3. İzin verilen hizmetler bölümünde "Windows Azure Hizmetleri"ni açın

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

