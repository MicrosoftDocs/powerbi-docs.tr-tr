---
title: 'Üçüncü taraf hizmeti: Google Analytics bağlayıcısı'
description: 'Üçüncü taraf hizmeti: Power BI Desktop için Google Analytics bağlayıcısı'
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: ec290ce53155f24a9213a4849ecb82abd6cfc592
ms.sourcegitcommit: e8ed3d120699911b0f2e508dc20bd6a9b5f00580
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2020
ms.locfileid: "86263653"
---
# <a name="use-the-google-analytics-connector-for-power-bi-desktop"></a>Power BI Desktop için Google Analytics bağlayıcısını kullanma
> [!NOTE]
> Power BI Desktop'taki Google Analytics içerik paketi ve bağlayıcı, Google Analytics Core Reporting API'sini kullanır. Bu nedenle özellikler ve kullanılabilirlik durumu zaman içinde değişebilir.

**Google Analytics** bağlayıcısını kullanarak Google Analytics verilerine bağlanabilirsiniz. Bağlanmak için şu adımları uygulayın:

1. **Power BI Desktop**'taki **Giriş** şerit sekmesinde **Veri Al**'ı seçin.
2. **Veri Al** penceresinde, sol bölmedeki kategoriler arasından **Online Services**’i seçin.
3. Sağ bölmedeki seçimler arasından **Google Analytics**'i seçin.
4. Pencerenin en altında bulunan **Bağlan**'ı seçin.  
   ![Google Analytics’in ve Bağlan düğmesinin seçili olduğu Veri Al sekmesini gösteren Giriş sekmesinin ekran görüntüsü.](media/service-google-analytics-connector/tps_googleanalytics_1.png)

Bağlayıcının bir Üçüncü Taraf Hizmet olduğunu açıklayan, özelliklerin ve kullanılabilirliğin zaman içinde değişebileceği konusunda uyarıda bulunan ve başka açıklamalar sağlayan bir iletişim kutusu gösterilir.  
![Bağlayıcının bir Üçüncü Taraf Hizmetini kullandığına ilişkin uyarı gösteren bağlantı iletişim kutusunun ekran görüntüsü.](media/service-google-analytics-connector/tps_googleanalytics_2.png)

**Devam**'ı seçtiğinizde, Google Analytics'te oturum açmanız istenir.  
![Bağlanmak için oturum açmanız gerektiği bilgisini gösteren Google Analytics isteminin ekran görüntüsü.](media/service-google-analytics-connector/tps_googleanalytics_3.png)

Kimlik bilgilerinizi girdiğinizde, Power BI'ın çevrimdışı erişim istediği bildirilir. **Power BI Desktop**'ı kullanarak Google Analytics verilerinize bu şekilde erişirsiniz.  

Kabul ettikten sonra **Power BI Desktop**, şu anda oturum açtığınızı gösterir.  
![Oturum açtığınızı gösteren Google Analytics isteminin ekran görüntüsü.](media/service-google-analytics-connector/tps_googleanalytics_5.png)

**Bağlan**'ı seçtiğinizde Google Analytics verileriniz **Power BI Desktop**'a bağlanır ve verileri yükler.  
![Google Analytics verilerinin bağlandığını ve yüklendiğini gösteren Yükleme iletişim kutusunun ekran görüntüsü.](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>API'de yapılan değişiklikler
Değişiklikler doğrultusunda güncelleştirmeler yayımlamaya çalışsak da API'de, oluşturduğumuz sorguların sonuçlarını etkileyecek değişiklikler meydana gelebilir. Belirli durumlarda, bazı sorgular artık desteklenmiyor olabilir. Bu bağımlılık nedeniyle, bu bağlayıcıyı kullandığınızda sorgularınızın sonuçlarını garanti edemeyiz.

Google Analytics API'sindeki değişiklikler hakkında daha fazla bilgiyi kendi [değişiklik günlüğünde](https://developers.google.com/analytics/devguides/changelog) bulabilirsiniz.

