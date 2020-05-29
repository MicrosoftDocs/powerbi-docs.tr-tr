---
title: Ek tanılama bilgilerini yakalama
description: Bu yönergelerde, Power BI web istemcisinden el ile ek tanılama bilgisi toplamak için kullanabileceğiniz iki seçenek sunulmaktadır.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/17/2019
ms.author: kfollis
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 670373afb5cb890c87a24a129cd43fde7bd5d892
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83128924"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Power BI için ek tanılama bilgilerini yakalama

Bu makalede Power BI web istemcisinden el ile ek tanılama bilgisi toplamak için kullanabileceğiniz yönergeler sunulmaktadır.

1. Microsoft Edge veya Internet Explorer kullanarak [Power BI](https://app.powerbi.com)'a gidin.

1. Microsoft Edge geliştirici araçlarını açmak için **F12** tuşuna basın.

   ![Microsoft Edge Geliştirici araçları Öğeler sekmesinin ekran görüntüsü.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. **Ağ** sekmesini seçin. Önceden yakalanmış olan trafik listelenir.

   ![Microsoft Edge Geliştirici araçları Ağ sekmesinin ekran görüntüsü.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    Seçenekleriniz şunlardır:

    * Pencereye göz atın ve karşılaştığınız sorunu tekrarlayın.

    * Oturum sırasında dilediğiniz zaman F12'ye basarak geliştirici araçları penceresini gizleyin ve gösterin.

1. Oturum profilini oluşturmayı durdurmak için geliştirici araçları bölümünün **Ağ** sekmesindeki kırmızı kareyi seçebilirsiniz.

   ![Durdur düğmesinin öne çıkarıldığı Microsoft Edge Geliştirici araçları Ağ sekmesinin ekran görüntüsü.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. Verileri bir HTTP Arşivi (HAR) dosyası olarak dışarı aktarmak için disket simgesini seçin.

   ![Disket simgesinin öne çıkarıldığı Microsoft Edge Geliştirici araçları Ağ sekmesinin ekran görüntüsü.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. Bir dosya adı girin ve HAR dosyasını kaydedin.

    HAR dosyası, tarayıcı penceresi ile Power BI arasındaki tüm ağ istekleri hakkındaki aşağıdaki bilgileri içerir:

    * Her istek için etkinlik kimlikleri.

    * Her istek için kesin zaman damgası.

    * İstemciye döndürülen tüm hata bilgileri.

    Bu izlemede, ekranda gösterilen görselleri doldurmak için kullanılan veriler de yer alır.

1. İnceleme konusunda destek olması için HAR dosyasını iletebilirsiniz.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)