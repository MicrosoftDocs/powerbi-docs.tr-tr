---
title: Gerçek zamanlı veriler için otomatik saklama ilkesi kullanan Power BI API'leri
description: Power BI hizmetindeki otomatik saklama ilkesi hakkında daha fazla bilgi edinin
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 9b5923c7bd92b1fe53ebb7ab9416aca8cece3cfa
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54294392"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Gerçek zamanlı veriler için otomatik elde tutma ilkesi

Power BI hizmetindeki otomatik saklama ilkesi, eski verileri otomatik olarak temizlerken yeni verilerin panonuza sabit akışını sürdürmek için varsayılan saklama ilkesini etkinleştiren bir sorgu dizesi parametresidir. İlk saklama ilkesi *temel ilk giren ilk çıkar (FIFO)* olarak adlandırılır. Etkinleştirildiğinde, veriler 200.000 satıra ulaşılana kadar tabloda toplanır. Veriler 200.000 satırı aştığında en eski satırlar veri kümesinden bırakılır. Bu şekilde yalnızca 200.000 ile 210.000 satır arasında en son veriler tutulur.  
  
<center>

![saklama ilkesi](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Saklama ilkeleri, veri kümelerinizi ilk oluşturduğunuzda etkinleştirilir. Tek yapmanız gereken POST datasets çağrınıza “defaultRetentionPolicy” sorgu parametresini eklemek ve bunu *basicFIFO*'ya eşit olarak ayarlamaktır.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}