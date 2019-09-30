---
title: Bir sayfalandırılmış rapor için URL’de rapor parametresi geçirme - Power BI Rapor Oluşturucusu
description: Bu konu başlığı altında, rapor parametrelerini bir sayfalandırılmış rapor URL’sine ekleyerek geçirme açıklanır.
ms.service: powerbi
ms.subservice: report-builder
ms.custom: ''
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.date: 08/29/2019
ms.openlocfilehash: f7f1b777e7c4e54dbdcfb1757fe4df274624a580
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71075996"
---
# <a name="pass-a-report-parameter-in-a-url-for-a-paginated-report-in-power-bi"></a>Power BI’da, bir sayfalandırılmış rapor için URL’de rapor parametresi geçirme 

Rapor parametrelerini, bir sayfalandırılmış rapor URL’sine ekleyerek geçirebilirsiniz. Tüm sorgu parametrelerinin karşılık gelen rapor parametreleri olabilir. Böylelikle, karşılık gelen rapor parametresini geçirerek bir sorgu parametresini rapora geçirirsiniz. Power BI’ın parametre adını URL’de tanıması için, parametre adına `rp:` ön eki getirmeniz gerekir. 

Rapor parametreleri büyük/küçük harfe duyarlıdır ve şu özel karakterleri kullanır: 

- URL’nin parametre bölümündeki bir boşluk, artı işaretiyle (+) değiştirilir.  Örnek: 

    ```rp:Holiday=Christmas+Day```

- Dizenin herhangi bir bölümündeki noktalı virgül, `%3A` karakterleriyle değiştirilir.

Tarayıcıların doğru URL kodlamasını otomatik olarak gerçekleştirmesi gerekir. Karakterlerin hiçbirini el ile kodlamanız gerekmez. 

URL içinde bir rapor parametresi ayarlamak için aşağıdaki söz dizimini kullanın: 

```
rp:parameter=value
```

Örneğin, Çalışma Alanım’da bulunan bir raporda tanımlanan “Satış temsilcisi” ve “Eyalet” şeklinde iki parametre belirtmek için aşağıdaki URL’yi kullanmanız gerekir: 

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:Salesperson=Tie+Bear&rp:State=Utah 
```

Bir uygulamada bulunan rapordaki iki parametreyi belirtmek için aşağıdaki URL’yi kullanmanız gerekir: 

```
https://app.powerbi.com/groups/me/apps/xxxxxxx-c4c4-4217-afd9-3920a0d1e2b0/rdlreports/b1d5e659-639e-41d0-b733-05d2bca9853c?rp:Salesperson=Tiggee&State=Utah 
```

Bir parametreye null değerini geçirmek için aşağıdaki söz dizimini kullanın: 

```
parameter:isnull=true
```

Örnek:

```
rp:SalesOrderNumber:isnull=true
```

Bir Boole değerini geçirmek için, false için 0 ve true için 1 kullanın. Bir Float değeri geçirmek için, sunucu yerel ayarının ondalık ayırıcısını ekleyin.

> [!NOTE]
> Raporunuz, varsayılan değeri bulunan bir rapor parametresini içeriyorsa ve **İstem** özelliğinin değeri **false** ise (bu durumda **Kullanıcı İstemi** özelliği Rapor Yöneticisi’nde seçilmemiştir), URL içinde yer alan rapor parametresi için değer geçiremezsiniz. Bu, yöneticilere son kullanıcıların belirli rapor parametrelerini eklemesini veya değiştirmesini önleme seçeneğini sunar.

## <a name="additional-examples"></a>Ek örnekler 

Aşağıdaki URL örneği, çok değerli “satış temsilcisi” parametresini içerir. Çok değerli parametrenin biçimi, parametre adını her değer için tekrarlamaya yöneliktir. 

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:Salesperson=Tie+Bear&rp:Salesperson=Mickey 
```

Aşağıdaki URL örneği, yerel mod rapor sunucusu için "1/7/2005" değeriyle tek bir SellStartDate parametresi geçirir.

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:SellStartDate=7/1/2005
```

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI’da bulunan sayfalandırılmış raporlardaki URL parametreleri](report-builder-url-parameters.md)
- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
