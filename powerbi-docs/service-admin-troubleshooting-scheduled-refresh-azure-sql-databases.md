---
title: "Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme"
description: "Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme"
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 6e2a4846f199dd71564167045671a8be93fb4f4a
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
Ayrıntılı zamanlanmış yenileme adımları için bkz. [Power BI'da verileri yenileme](refresh-data.md).

Azure SQL Veritabanı için zamanlanmış yenilemeyi ayarlama sırasında kimlik bilgilerini düzenlerken hata kodu 400 ile karşılaşıyorsanız uygun güvenlik duvarı kurallarını ayarlamak için aşağıdaki işlemleri gerçekleştirmeyi deneyin:

1. Azure yönetim portalında oturum açın
2. Yenileme yapılandırması yaptığınız Azure SQL sunucusuna gidin
3. İzin verilen hizmetler bölümünde "Windows Azure Hizmetleri"ni açın

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

