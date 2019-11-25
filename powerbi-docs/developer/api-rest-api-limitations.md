---
title: Power BI REST API sınırlamaları
description: Power BI REST API sınırlamaları aşağıda verilmiştir
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 97745d93de771d4888dd97717a5e8a8d2d6f5c7c
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74265638"
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
* ‘Saklama ilkesi olmayan’ veri kümesinde tablo başına en çok 5.000.000 satır depolanır  
* Satır Gönderme işlemindeki dize sütunu için değer başına 4.000 karakter
  
## <a name="see-also"></a>Ayrıca bkz.

[Azure AD hizmet sınırlamaları ve kısıtlamaları](https://docs.microsoft.com/azure/active-directory/active-directory-service-limits-restrictions)   
[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](https://docs.microsoft.com/rest/api/power-bi/)