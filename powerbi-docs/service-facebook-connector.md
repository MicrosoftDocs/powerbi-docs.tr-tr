---
title: "Üçüncü taraf hizmet: Power BI Desktop için Facebook bağlayıcısı"
description: "Üçüncü taraf hizmet: Power BI Desktop için Facebook bağlayıcısı"
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
ms.date: 07/20/2017
ms.author: davidi
ms.openlocfilehash: ee79f7a677f7f64b05df83b09ffba02978e1ac62
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Power BI Desktop için Facebook bağlayıcısı
**Power BI Desktop**'taki Facebook bağlayıcısı, Facebook Graph API'yi kullanır. Bu nedenle, özellikler ve kullanılabilirlik zaman içinde değişebilir.

[Power BI Desktop için Facebook Bağlayıcısı ile ilgili bir eğitime](desktop-tutorial-facebook-analytics.md) göz atabilirsiniz.

Facebook 30 Nisan<sup></sup> 2015 tarihinde Graph API'nin 1.0 sürümünü kullanımdan kaldırdı. Power BI, Facebook bağlayıcısı için arka planda Graph API'yi kullanır, bu da verilerinize bağlanmanıza ve bunları çözümlemenize olanak tanır.

30 Nisan<sup></sup> 2015 tarihinden önce oluşturulan sorgular artık çalışmayabilir veya daha az veri döndürebilir. 30 Nisan<sup></sup> 2015 tarihinden itibaren Power BI, Facebook API'sine yapılan çağrılarda 2.2 sürümünü kullanmaktadır. Sorgunuz 30 Nisan 2015 tarihinden önce oluşturulduysa ve sorguyu, oluşturulma tarihinden beri kullanmadıysanız, isteyeceğimiz yeni izinleri onaylamak için büyük olasılıkla tekrar kimlik doğrulaması yapmanız gerekir.

Değişiklikler doğrultusunda güncelleştirmeler yayımlamaya çalışsak da API'de, oluşturduğumuz sorguların sonuçlarını etkileyecek değişiklikler meydana gelebilir. Belirli durumlarda, bazı sorgular artık desteklenmiyor olabilir. Söz konusu bağımlılık nedeniyle, bu bağlayıcıyı kullanarak gerçekleştirdiğiniz sorgularınızın sonuçlarını garanti edemeyiz.

Facebook API'sindeki değişiklikle ilgili daha fazla ayrıntıya [buradan](https://developers.facebook.com/docs/apps/changelog#v2_0) ulaşabilirsiniz.

