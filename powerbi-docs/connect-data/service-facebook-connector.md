---
title: 'Üçüncü taraf hizmeti: Power BI Desktop için Facebook bağlayıcısı'
description: 'Üçüncü taraf hizmeti: Power BI Desktop için Facebook bağlayıcısı'
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/20/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 882cddf7728a27e78056a35c14fde20f00678e33
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83309556"
---
# <a name="use-the-facebook-connector-for-power-bi-desktop"></a>Power BI Desktop için Facebook bağlayıcısını kullanma
**Power BI Desktop**'taki Facebook bağlayıcısı, Facebook Graph API'yi kullanır. Bu nedenle, özellikler ve kullanılabilirlik zaman içinde değişebilir.

[Power BI Desktop için Facebook Bağlayıcısı ile ilgili bir eğitime](desktop-tutorial-facebook-analytics.md) göz atabilirsiniz.

> [!IMPORTANT]
> **Facebook veri bağlayıcısı bildiriminin kullanımdan kaldırılması:** Excel’de verileri Facebook’tan içeri aktarma ve yenileme özelliği Nisan 2020’den itibaren düzgün çalışmayacaktır. Bu tarihe kadar Facebook *Al ve Dönüştür (Power Query)* bağlayıcısını kullanabilirsiniz. Bu tarihten sonra Facebook'a bağlanamayacak ve bir hata iletisiyle karşılaşacaksınız. Beklenmedik sonuçlardan kaçınmak için Facebook bağlayıcısını kullanan tüm mevcut *Al ve Dönüştür (Power Query)* sorgularını en kısa zamanda düzeltmenizi ve kaldırmanızı öneririz.


Facebook 30 Nisan 2015 tarihinde Graph API'nin 1.0 sürümünü kullanımdan kaldırdı. Power BI, Facebook bağlayıcısı için arka planda Graph API'yi kullanır, bu da verilerinize bağlanmanıza ve bunları çözümlemenize olanak tanır.

30 Nisan 2015 tarihinden önce oluşturulan sorgular artık çalışmayabilir veya daha az veri döndürebilir. 30 Nisan 2015 tarihinden itibaren Power BI, Facebook API’sine yapılan çağrılarda v2.8 sürümünü kullanmaktadır. Sorgunuz 30 Nisan 2015 tarihinden önce oluşturulduysa ve sorguyu, oluşturulma tarihinden beri kullanmadıysanız, isteyeceğimiz yeni izinleri onaylamak için büyük olasılıkla tekrar kimlik doğrulaması yapmanız gerekir.

Değişiklikler doğrultusunda güncelleştirmeler yayımlamaya çalışsak da API'de, oluşturduğumuz sorguların sonuçlarını etkileyecek değişiklikler meydana gelebilir. Belirli durumlarda, bazı sorgular artık desteklenmiyor olabilir. Söz konusu bağımlılık nedeniyle, bu bağlayıcıyı kullanarak gerçekleştirdiğiniz sorgularınızın sonuçlarını garanti edemeyiz.

Facebook API'sindeki değişiklikle ilgili daha fazla ayrıntıya [buradan](https://developers.facebook.com/docs/apps/changelog#v2_0) ulaşabilirsiniz.
