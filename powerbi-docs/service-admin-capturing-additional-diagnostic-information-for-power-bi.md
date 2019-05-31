---
title: Ek tanılama bilgilerini yakalama
description: Bu yönergelerde, Power BI web istemcisinden el ile ek tanılama bilgisi toplamak için kullanabileceğiniz iki seçenek sunulmaktadır.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 710fb4cdcf9efb051434966d47c2eaced17ac9ba
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100199"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Power BI için ek tanılama bilgilerini yakalama

Bu makale el ile Power BI web istemcisinden ek tanılama bilgilerini toplamak için yönergeler sağlar.

1. Gözat [Power BI](https://app.powerbi.com) Microsoft Edge veya Internet Explorer.

1. Tuşuna **F12** Microsoft Edge geliştirici araçlarını açın.

   ![Ekran Microsoft Edge geliştirici araçlarını öğeleri sekmesi.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. **Ağ** sekmesini seçin. Önceden yakalanmış olan trafik listelenir.

   ![Ekran Microsoft Edge geliştirici araçları ağı sekmesini açın.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    Seçenekleriniz şunlardır:

    * Pencereye göz atın ve siz gelebilir arasında karşılaştığınız sorunu tekrarlayabilirsiniz.

    * Geliştirici Araçları penceresini oturum sırasında dilediğiniz zaman F12 tuşuna basarak Göster ve Gizle.

1. Profil oluşturma oturumunu durdurmak için kırmızı kareyi seçebilirsiniz **ağ** sekmesi geliştirici araçları alan.

   ![Ekran Microsoft Edge geliştirici araçları ağı sekmesini Durdur düğmesini dışında bir çağrı ile.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. Verileri bir HTTP Arşivi (HAR) dosyası olarak dışarı aktarmak için disket simgesini seçin.

   ![Disket simgesinin bir belirtme çizgisi içeren ekran Microsoft Edge geliştirici araçları ağı sekmesini.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. Bir dosya adı girin ve HAR dosyasını kaydedin.

    HAR dosyasını tarayıcı penceresi ile Power BI dahil olmak üzere arasındaki ağ istekleri hakkındaki tüm bilgileri içerir:

    * Etkinlik Kimliği her istek için.

    * Her istek için tam zaman damgası.

    * İstemciye döndürülen hata bilgileri.

    Bu izlemede, ekranda gösterilen görselleri doldurmak için kullanılan veriler de yer alır.

1. İnceleme konusunda destek olması için HAR dosyasını iletebilirsiniz.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
