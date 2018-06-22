---
title: 'Üçüncü taraf hizmet: Power BI Desktop için Facebook bağlayıcısı'
description: 'Üçüncü taraf hizmet: Power BI Desktop için Facebook bağlayıcısı'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 02/22/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6e33e1a27903cc3fbce5c3f504287fa96dbf8305
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34296630"
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Power BI Desktop için Facebook bağlayıcısı
**Power BI Desktop**'taki Facebook bağlayıcısı, Facebook Graph API'yi kullanır. Bu nedenle, özellikler ve kullanılabilirlik zaman içinde değişebilir.

[Power BI Desktop için Facebook Bağlayıcısı ile ilgili bir eğitime](desktop-tutorial-facebook-analytics.md) göz atabilirsiniz.

Facebook 30 Nisan<sup></sup> 2015 tarihinde Graph API'nin 1.0 sürümünü kullanımdan kaldırdı. Power BI, Facebook bağlayıcısı için arka planda Graph API'yi kullanır, bu da verilerinize bağlanmanıza ve bunları çözümlemenize olanak tanır.

30 Nisan<sup></sup> 2015 tarihinden önce oluşturulan sorgular artık çalışmayabilir veya daha az veri döndürebilir. 30 Nisan<sup></sup> 2015 tarihinden itibaren Power BI, Facebook API’sine yapılan çağrılarda v2.8 sürümünü kullanmaktadır. Sorgunuz 30 Nisan 2015 tarihinden önce oluşturulduysa ve sorguyu, oluşturulma tarihinden beri kullanmadıysanız, isteyeceğimiz yeni izinleri onaylamak için büyük olasılıkla tekrar kimlik doğrulaması yapmanız gerekir.

Değişiklikler doğrultusunda güncelleştirmeler yayımlamaya çalışsak da API'de, oluşturduğumuz sorguların sonuçlarını etkileyecek değişiklikler meydana gelebilir. Belirli durumlarda, bazı sorgular artık desteklenmiyor olabilir. Söz konusu bağımlılık nedeniyle, bu bağlayıcıyı kullanarak gerçekleştirdiğiniz sorgularınızın sonuçlarını garanti edemeyiz.

Facebook API'sindeki değişiklikle ilgili daha fazla ayrıntıya [buradan](https://developers.facebook.com/docs/apps/changelog#v2_0) ulaşabilirsiniz.

