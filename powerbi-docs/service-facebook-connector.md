---
title: 'Üçüncü taraf hizmeti: Power BI Desktop için Facebook bağlayıcısı'
description: 'Üçüncü taraf hizmeti: Power BI Desktop için Facebook bağlayıcısı'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6b02717c49a1207dfec39ebb1529e7e9b222fa62
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65512871"
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Power BI Desktop için Facebook bağlayıcısı
**Power BI Desktop**'taki Facebook bağlayıcısı, Facebook Graph API'yi kullanır. Bu nedenle, özellikler ve kullanılabilirlik zaman içinde değişebilir.

[Power BI Desktop için Facebook Bağlayıcısı ile ilgili bir eğitime](desktop-tutorial-facebook-analytics.md) göz atabilirsiniz.

Facebook 30 Nisan 2015 tarihinde Graph API'nin v1.0 süresi doldu. Power BI, Facebook bağlayıcısı için arka planda Graph API'yi kullanır, bu da verilerinize bağlanmanıza ve bunları çözümlemenize olanak tanır.

30 Nisan 2015'den önce oluşturulan sorgular artık çalışmayabilir veya daha az veri döndürebilir. Den 30 Nisan 2015, Power BI Facebook API'sine yapılan çağrılarda v2.8 yararlanır. Sorgunuz 30 Nisan 2015 tarihinden önce oluşturulduysa ve sorguyu, oluşturulma tarihinden beri kullanmadıysanız, isteyeceğimiz yeni izinleri onaylamak için büyük olasılıkla tekrar kimlik doğrulaması yapmanız gerekir.

Değişiklikler doğrultusunda güncelleştirmeler yayımlamaya çalışsak da API'de, oluşturduğumuz sorguların sonuçlarını etkileyecek değişiklikler meydana gelebilir. Belirli durumlarda, bazı sorgular artık desteklenmiyor olabilir. Bu bağımlılık nedeniyle, biz sorgularınızın sonuçlarını bu bağlayıcı kullanılırken garanti edemez.

Facebook API'sindeki değişiklikle ilgili daha fazla ayrıntıya [buradan](https://developers.facebook.com/docs/apps/changelog#v2_0) ulaşabilirsiniz.

