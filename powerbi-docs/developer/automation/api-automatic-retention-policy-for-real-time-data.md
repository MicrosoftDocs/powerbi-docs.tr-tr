---
title: Gerçek zamanlı veriler için otomatik saklama ilkesi kullanan Power BI API'leri
description: Power BI hizmetindeki otomatik saklama ilkesi hakkında daha fazla bilgi edinin
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: cdbf50ee5078eaade7794242b3ed522e043cab22
ms.sourcegitcommit: 87b7cb4a2e626711b98387edaa5ff72dc26262bb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79079658"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Gerçek zamanlı veriler için otomatik elde tutma ilkesi

Power BI hizmetindeki otomatik saklama ilkesi, eski verileri otomatik olarak temizlerken yeni verilerin panonuza sabit akışını sürdürmek için varsayılan saklama ilkesini etkinleştiren bir sorgu dizesi parametresidir. İlk saklama ilkesi *ilk giren ilk çıkar (FIFO)* olarak adlandırılır. Etkinleştirildiğinde, veriler 200.000 satıra ulaşılana kadar tabloda toplanır. Veriler 200.000 satırı aştığında en eski satırlar veri kümesinden bırakılır. Bu şekilde yalnızca 200.000 ile 210.000 satır arasında en son veriler tutulur.  
  
<center>

![saklama ilkesi](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Saklama ilkeleri, veri kümelerinizi ilk oluşturduğunuzda etkinleştirilir. Tek yapmanız gereken POST datasets çağrınıza “default retention policy” sorgu parametresini eklemek ve bunu *basicFIFO*'ya eşit olacak şekilde ayarlamaktır.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}