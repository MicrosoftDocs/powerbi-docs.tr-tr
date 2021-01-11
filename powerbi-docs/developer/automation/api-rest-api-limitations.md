---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerindeki Power BI REST API sınırlamaları
description: Power BI REST API'sinde aşağıdaki sınırlamaları bulunur. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 1196917f0223ccde012d203d75c4e96fbc3b9dcf
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97887673"
---
# <a name="power-bi-rest-api-limitations"></a>Power BI REST API sınırlamaları  
  
**Satır göndermek için**
  
* En çok 75 sütun
* En çok 75 tablo
* Tek bir Satır Gönderme isteği başına en çok 10.000 satır  
* Veri kümesi başına saatte 1.000.000 satır eklenir  
* Veri kümesi başına en çok 5 bekleyen Satır Gönderme isteği  
* Veri kümesi başına dakikada 120 Satır Gönderme isteği
* Tabloda 250.000 veya daha çok satır varsa, veri kümesi başına saatte 120 Satır Gönderme isteği
* FIFO veri kümesinde tablo başına en çok 200.000 satır depolanır
* 'Saklama ilkesi olmayan' veri kümesinde tablo başına en çok 5.000.000 satır depolanır  
* Satır Gönderme işlemindeki dize sütunu için değer başına 4.000 karakter
  
## <a name="see-also"></a>Ayrıca bkz.

* [Azure AD hizmet sınırlamaları ve kısıtlamaları](/azure/active-directory/active-directory-service-limits-restrictions)   
* [Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](/rest/api/power-bi/)