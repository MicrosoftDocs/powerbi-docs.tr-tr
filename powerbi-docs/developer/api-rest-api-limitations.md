---
title: Power BI REST API sınırlamaları
description: Power BI REST API sınırlamaları aşağıda verilmiştir
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: df17563d384359fe33123ed87743754bb33bf04d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54278003"
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