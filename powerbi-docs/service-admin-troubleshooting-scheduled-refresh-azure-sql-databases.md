---
title: Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
description: Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 17ee932bf0331940c7b30b020ab8fc43cdc9fdf5
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54274691"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
Ayrıntılı zamanlanmış yenileme adımları için bkz. [Power BI'da verileri yenileme](refresh-data.md).

Azure SQL Veritabanı için zamanlanmış yenilemeyi ayarlama sırasında kimlik bilgilerini düzenlerken hata kodu 400 ile karşılaşıyorsanız uygun güvenlik duvarı kurallarını ayarlamak için aşağıdaki işlemleri gerçekleştirmeyi deneyin:

1. Azure yönetim portalında oturum açın
2. Yenileme yapılandırması yaptığınız Azure SQL sunucusuna gidin
3. İzin verilen hizmetler bölümünde "Windows Azure Hizmetleri"ni açın

![Azure izin verilen hizmetleri](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

