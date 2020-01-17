---
title: 'Üçüncü taraf hizmeti: Power BI Desktop için Facebook bağlayıcısı'
description: 'Üçüncü taraf hizmeti: Power BI Desktop için Facebook bağlayıcısı'
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: dcfc695d0371cce21a827ddfe71b3b4b05863935
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75762428"
---
# <a name="use-the-facebook-connector-for-power-bi-desktop"></a>Power BI Desktop için Facebook bağlayıcısını kullanma
**Power BI Desktop**'taki Facebook bağlayıcısı, Facebook Graph API'yi kullanır. Bu nedenle, özellikler ve kullanılabilirlik zaman içinde değişebilir.

[Power BI Desktop için Facebook Bağlayıcısı ile ilgili bir eğitime](desktop-tutorial-facebook-analytics.md) göz atabilirsiniz.

Facebook 30 Nisan 2015 tarihinde Graph API'nin 1.0 sürümünü kullanımdan kaldırdı. Power BI, Facebook bağlayıcısı için arka planda Graph API'yi kullanır, bu da verilerinize bağlanmanıza ve bunları çözümlemenize olanak tanır.

30 Nisan 2015 tarihinden önce oluşturulan sorgular artık çalışmayabilir veya daha az veri döndürebilir. 30 Nisan 2015 tarihinden itibaren Power BI, Facebook API’sine yapılan çağrılarda v2.8 sürümünü kullanmaktadır. Sorgunuz 30 Nisan 2015 tarihinden önce oluşturulduysa ve sorguyu, oluşturulma tarihinden beri kullanmadıysanız, isteyeceğimiz yeni izinleri onaylamak için büyük olasılıkla tekrar kimlik doğrulaması yapmanız gerekir.

Değişiklikler doğrultusunda güncelleştirmeler yayımlamaya çalışsak da API'de, oluşturduğumuz sorguların sonuçlarını etkileyecek değişiklikler meydana gelebilir. Belirli durumlarda, bazı sorgular artık desteklenmiyor olabilir. Söz konusu bağımlılık nedeniyle, bu bağlayıcıyı kullanarak gerçekleştirdiğiniz sorgularınızın sonuçlarını garanti edemeyiz.

Facebook API'sindeki değişiklikle ilgili daha fazla ayrıntıya [buradan](https://developers.facebook.com/docs/apps/changelog#v2_0) ulaşabilirsiniz.

