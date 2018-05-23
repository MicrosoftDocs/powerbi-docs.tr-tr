---
title: Ek tanılama bilgilerini yakalama
description: Ek tanılama bilgilerini yakalama
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 76860e740d43a1907692a7cd4fed1a6df68c93d4
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="capturing-additional-diagnostic-information"></a>Ek tanılama bilgilerini yakalama
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Power BI için Ek Tanılama Bilgilerini Yakalama
Bu yönergelerde, Power BI web istemcisinden el ile ek tanılama bilgisi toplamak için kullanabileceğiniz iki seçenek sunulmaktadır.  Bu seçeneklerden yalnızca birinin kullanılması gerekir.

## <a name="network-capture---edge--internet-explorer"></a>Ağ Yakalama - Edge ve Internet Explorer
1. Edge veya Internet Explorer kullanarak [Power BI](https://app.powerbi.com)'a gidin.
2. F12'ye basarak Edge geliştirici araçlarını açın.
3. Geliştirici Araçları penceresi açılır: 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. Ağ sekmesine gidin. Önceden yakalanmış olan trafik listelenir. 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. Pencereye göz atabilir ve karşılaştığınız sorunu tekrarlayabilirsiniz. Oturum sırasında dilediğiniz zaman F12'ye basarak geliştirici araçları penceresini gizleyebilir ve gösterebilirsiniz.
6. Yakalamayı durdurmak için geliştirici araçları bölümünün ağ sekmesindeki kırmızı kareyi seçebilirsiniz.
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. Disket simgesini seçip **HAR olarak dışarı aktar**'a tıklayın
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. Bir dosya adı girin ve HAR dosyasını kaydedin.
   
    HAR dosyası, tarayıcı penceresi ile Power BI arasındaki tüm ağ istekleri hakkındaki bilgileri içerir.  Bunlar arasında her bir isteğin etkinlik kimliği, tam zaman damgası ve istemciye döndürülen hata bilgileri bulunur.  Bu izlemede, ekranda gösterilen görselleri doldurmak için kullanılan veriler de yer alır.
9. İnceleme konusunda destek olması için HAR dosyasını iletebilirsiniz.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

