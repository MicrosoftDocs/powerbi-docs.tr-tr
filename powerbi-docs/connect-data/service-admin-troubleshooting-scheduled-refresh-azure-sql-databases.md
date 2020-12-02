---
title: Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
description: Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme
author: davidiseminger
ms.author: davidi
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: troubleshooting
ms.date: 09/04/2019
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: a9f69c8177766352d768d86903f15977ae0d8d1c
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96410747"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI'da Azure SQL Veritabanları için zamanlanmış yenileme ile ilgili sorunları giderme

Yenileme hakkında ayrıntılı bilgi için bkz. [Power BI’da verileri yenileme](refresh-data.md) ve [Zamanlanmış yenilemeyi yapılandırma](refresh-scheduled-refresh.md).

Azure SQL veritabanı için zamanlanmış yenilemeyi ayarlama sırasında kimlik bilgilerini düzenlerken hata kodu 400 ile karşılaşıyorsanız uygun güvenlik duvarı kurallarını ayarlamak için aşağıdaki işlemleri gerçekleştirmeyi deneyin:

1. [Azure Portal](https://portal.azure.com) oturum açın.

1. Yenilemeyi yapılandırdığınız Azure SQL veritabanına gidin.

1. **Genel bakış** dikey penceresinin üst kısmında **Sunucu güvenlik duvarı ayarla**’yı seçin.

1. **Güvenlik duvarı ayarları** dikey penceresinde **Azure hizmetlerine erişime izin ver** seçeneğinin **AÇIK** olarak ayarlandığından emin olun.

    ![Azure izin verilen hizmetleri](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
