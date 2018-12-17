---
title: Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
description: Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: d1cd68fbb995b7fac420a50f97a8930385086a10
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53026075"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
Ayrıntılı zamanlanmış yenileme adımları için bkz. [Power BI'da verileri yenileme](refresh-data.md).

Azure SQL Veritabanı için zamanlanmış yenilemeyi ayarlama sırasında kimlik bilgilerini düzenlerken hata kodu 400 ile karşılaşıyorsanız uygun güvenlik duvarı kurallarını ayarlamak için aşağıdaki işlemleri gerçekleştirmeyi deneyin:

1. Azure yönetim portalında oturum açın
2. Yenileme yapılandırması yaptığınız Azure SQL sunucusuna gidin
3. İzin verilen hizmetler bölümünde "Windows Azure Hizmetleri"ni açın

![Azure izin verilen hizmetleri](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

