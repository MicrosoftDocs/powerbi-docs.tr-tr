---
title: Power BI veri modeli sürümü oluşturma
description: OData Hizmeti tarafından uygulanan Veri Modeli
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 76947b1e311bbd1a21e09ce39461a70bed61d926
ms.sourcegitcommit: 87b7cb4a2e626711b98387edaa5ff72dc26262bb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79079612"
---
# <a name="data-model-versioning"></a>Veri Modeli sürümü oluşturma

OData Hizmeti tarafından uygulanan Veri Modeli, örneğin Power BI veri modeli OData hizmetiyle onun istemcileri arasında bir anlaşma tanımlar. Hizmetlerin modellerini ancak mevcut istemcilerde hataya neden olmayacak kadar genişletmelerine izin verilir. Özellikleri kaldırma veya mevcut özelliklerin türün değiştirme gibi hataya neden olan değişiklikler, yeni model için farklı bir hizmet kök URL'sinde yeni bir hizmet sürümü sağlanmasını gerektirir.  
  
Aşağıdaki Veri Modeli eklemeleri güvenli kabul edilir ve giriş noktasında hizmetlerin sürümünü oluşturmayı gerektirmez.  
  
* Null değeri alabilen veya varsayılan değeri olan bir özellik ekleme; mevcut bir dinamik özellikle aynı ada sahipse, mevcut dinamik özellikle aynı türde (veya temel türde) olması gerekir  
* Null değer alabilen veya koleksiyondan değer alan bir gezinti özelliği ekleme; mevcut bir dinamik gezinti özelliğiyle aynı ada sahipse, mevcut dinamik gezinti özelliğiyle aynı türde (veya temel türde) olması gerekir  
* Modele yeni bir varlık türü ekleme  
* Modele yeni bir karmaşık tür ekleme  
* Yeni bir varlık kümesi ekleme  
* Yeni bir tekil ekleme  
* Eylem, işlev, eylem içeri aktarması veya işlev içeri aktarması ekleme
* Null değer alabilen bir eylem parametresi ekleme  
* Tür tanımı veya sabit listesi ekleme  
* Model öğesine, hizmetle doğru etkileşim kurmak için istemci tarafından anlaşılması gerekmeyen açıklamalar ekleme  
  
Modelde böyle artımlı değişiklikler yapabilmek için istemcilerin hizmetlere hazırlanması ***GEREKİR***. Özellikle, istemciler daha önce hizmet tarafından tanımlanmamış özellikleri ve türetilmiş türleri almaya hazırlanmalıdır.  
  
Hizmetlerin kimliği doğrulanmış kullanıcıya göre veri modellerini değiştirmemeleri ***GEREKİR***. Veri modeli kullanıcıya veya kullanıcı grubuna bağımlı olursa, tam model ile sınırlı yetkilendirmeye sahip kullanıcılara gösterilen model karşılaştırıldığında tüm değişiklikler güvenlik değişiklik OLMALIDIR.  
  
OData Veri Modeli standartları hakkında daha fazla bilgi için bkz. [OData Version 4.0 Part 1: Protocol Plus Errata 02](https://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html).  
  
## <a name="see-also"></a>Ayrıca bkz.
[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](https://docs.microsoft.com/rest/api/power-bi/)