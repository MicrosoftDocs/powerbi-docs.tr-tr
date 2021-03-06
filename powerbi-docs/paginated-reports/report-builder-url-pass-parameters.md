---
title: Bir sayfalandırılmış rapor için URL’de rapor parametresi geçirme - Power BI Rapor Oluşturucusu
description: Bu konu başlığı altında, rapor parametrelerini bir sayfalandırılmış rapor URL’sine ekleyerek geçirme açıklanır.
author: maggiesMSFT
ms.author: maggies
ms.service: powerbi
ms.subservice: report-builder
ms.topic: how-to
ms.reviewer: cfinlan
ms.custom: ''
ms.date: 05/01/2020
ms.openlocfilehash: ac3cd10ec4c356da92aca6983292ff57b16f58b3
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96415600"
---
# <a name="pass-a-report-parameter-in-a-url-for-a-paginated-report-in-power-bi"></a>Power BI’da, bir sayfalandırılmış rapor için URL’de rapor parametresi geçirme 

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-service](../includes/yes-service.md)] [!INCLUDE [yes-paginated](../includes/yes-paginated.md)] [!INCLUDE [yes-premium](../includes/yes-premium.md)] [!INCLUDE [no-desktop](../includes/no-desktop.md)] 

Rapor parametrelerini, bir sayfalandırılmış rapor URL’sine ekleyerek geçirebilirsiniz. Tüm sorgu parametrelerinin karşılık gelen rapor parametreleri olabilir. Böylelikle, karşılık gelen rapor parametresini geçirerek bir sorgu parametresini rapora geçirirsiniz. Power BI’ın parametre adını URL’de tanıması için, parametre adına `rp:` ön eki getirmeniz gerekir. 

Rapor parametreleri büyük/küçük harfe duyarlıdır ve şu özel karakterleri kullanır: 

- URL’nin parametre bölümündeki bir boşluk, artı işaretiyle (+) değiştirilir.  Örneğin: 

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
https://app.powerbi.com/groups/me/apps/xxxxxxx-c4c4-4217-afd9-3920a0d1e2b0/rdlreports/b1d5e659-639e-41d0-b733-05d2bca9853c?rp:Salesperson=Tiggee&rp:State=Utah 
```

Bir parametreye null değerini geçirmek için aşağıdaki söz dizimini kullanın: 

```
parameter:isnull=true
```

Örneğin:

```
rp:SalesOrderNumber:isnull=true
```

Bir Boole değerini geçirmek için, false için 0 ve true için 1 kullanın. Bir Float değeri geçirmek için, sunucu yerel ayarının ondalık ayırıcısını ekleyin.

> [!NOTE]
> Raporunuz, varsayılan değeri bulunan bir rapor parametresini içeriyorsa ve **İstem** özelliğinin değeri **false** ise (bu durumda **Kullanıcı İstemi** özelliği Rapor Yöneticisi’nde seçilmemiştir), URL içinde yer alan rapor parametresi için değer geçiremezsiniz. Bu, yöneticilere son kullanıcıların belirli rapor parametrelerini eklemesini veya değiştirmesini önleme seçeneğini sunar.
> 
> Power BI 2,000 karakterden uzun sorgu dizelerini desteklemez.  Sayfalandırılmış raporunuzu görüntülemek için URL parametrelerini kullandığınızda bu değer aşılabilir.  Özellikle çok değerli parametreler kullanıyorsanız bu durumla karşılaşabilirsiniz.

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
