---
title: 'Üçüncü taraf hizmeti: Google Analytics bağlayıcısı'
description: 'Üçüncü taraf hizmeti: Power BI Desktop için Google Analytics bağlayıcısı'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b7451f156503d88baf4bdf3f3ae2cb99c04a94c1
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53025615"
---
# <a name="google-analytics-connector-for-power-bi-desktop"></a>Power BI Desktop için Google Analytics bağlayıcısı
> [!NOTE]
> Power BI Desktop'taki Google Analytics içerik paketi ve bağlayıcı, Google Analytics Core Reporting API'sini kullanır. Bu nedenle, özellikler ve kullanılabilirlik zaman içinde değişebilir.

**Google Analytics** bağlayıcısını kullanarak Google Analytics verilerine bağlanabilirsiniz. Bağlanmak için şu adımları uygulayın:

1. **Power BI Desktop**'taki **Giriş** şerit sekmesinde **Veri Al**'ı seçin.
2. **Veri Al** penceresinde, sol bölmedeki kategoriler arasından **Online Services**’i seçin.
3. Sağ bölmedeki seçimler arasından **Google Analytics**'i seçin.
4. Pencerenin en altında bulunan **Bağlan**'ı seçin.  
   ![](media/service-google-analytics-connector/tps_googleanalytics_1.png)

Bağlayıcının bir Üçüncü Taraf Hizmet olduğunu açıklayan, özelliklerin ve kullanılabilirliğin zaman içinde değişebileceği konusunda uyarıda bulunan ve başka açıklamalar sağlayan bir iletişim kutusu gösterilir.  
![](media/service-google-analytics-connector/tps_googleanalytics_2.png)

**Devam**'ı seçtiğinizde, Google Analytics'te oturum açmanız istenir.  
![](media/service-google-analytics-connector/tps_googleanalytics_3.png)

Kimlik bilgilerinizi girdiğinizde, Power BI'ın çevrimdışı erişim istediği bildirilir. **Power BI Desktop**'ı kullanarak Google Analytics verilerinize bu şekilde erişirsiniz.  

Kabul ettikten sonra **Power BI Desktop**, şu anda oturum açtığınızı gösterir.  
![](media/service-google-analytics-connector/tps_googleanalytics_5.png)

**Bağlan**'ı seçtiğinizde Google Analytics verileriniz **Power BI Desktop**'a bağlanır ve verileri yükler.  
![](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>API'de yapılan değişiklikler
Değişiklikler doğrultusunda güncelleştirmeler yayımlamaya çalışsak da API'de, oluşturduğumuz sorguların sonuçlarını etkileyecek değişiklikler meydana gelebilir. Belirli durumlarda, bazı sorgular artık desteklenmiyor olabilir. Bu bağımlılık nedeniyle, bu bağlayıcıyı kullandığınızda sorgularınızın sonuçlarını garanti edemeyiz.

Google Analytics API'sindeki değişiklikler hakkında daha fazla bilgiyi kendi [değişiklik günlüğünde](https://developers.google.com/analytics/devguides/changelog) bulabilirsiniz.

