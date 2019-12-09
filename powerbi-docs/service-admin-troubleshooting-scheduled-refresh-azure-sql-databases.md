---
title: Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
description: Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
author: maggiesMSFT
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 09/04/2019
ms.author: maggies
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 292f80b4fec7da9ff6ce42e3611bf4d6353bae2d
ms.sourcegitcommit: 90bd747b7c460d17b74cd386d3f5714234b1f6c9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74791956"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme

Yenileme hakkında ayrıntılı bilgi için bkz. [Power BI’da verileri yenileme](refresh-data.md) ve [Zamanlanmış yenilemeyi yapılandırma](refresh-scheduled-refresh.md).

Azure SQL veritabanı için zamanlanmış yenilemeyi ayarlama sırasında kimlik bilgilerini düzenlerken hata kodu 400 ile karşılaşıyorsanız uygun güvenlik duvarı kurallarını ayarlamak için aşağıdaki işlemleri gerçekleştirmeyi deneyin:

1. [Azure portalında](https://portal.azure.com) oturum açın.

1. Yenilemeyi yapılandırdığınız Azure SQL veritabanına gidin.

1. **Genel bakış** dikey penceresinin üst kısmında **Sunucu güvenlik duvarı ayarla**’yı seçin.

1. **Güvenlik duvarı ayarları** dikey penceresinde **Azure hizmetlerine erişime izin ver** seçeneğinin **AÇIK** olarak ayarlandığından emin olun.

    ![Azure izin verilen hizmetleri](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
