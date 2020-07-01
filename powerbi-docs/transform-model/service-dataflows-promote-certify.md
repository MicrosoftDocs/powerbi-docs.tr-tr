---
title: Veri akışlarını yükseltme veya onaylama (önizleme)
description: Veri akışlarını yükseltme veya onaylamayı öğrenin.
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 06/15/2020
ms.author: painbar
LocalizationGroup: Share your work
ms.openlocfilehash: 473d1375ed35e638a94f82970b29809d35482584
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85237691"
---
# <a name="promote-or-certify-dataflows-preview"></a>Veri akışlarını yükseltme veya onaylama (önizleme)

Power BI değerli, yüksek kaliteli veri akışlarınızın görünürlüğünü artırmak için iki yol sağlar: **yükseltme** ve **onaylama**.

* **Yükseltme**: Yükseltme, kullanıcıların değerli olduğunu ve başkalarının da kullanabileceğini düşündüğü veri akışlarını vurgulamasına olanak tanır. Bu yolla kuruluş içinde veri akışlarının işbirliğine dayayı yayılmasını teşvik eder. Tüm veri akışı sahipleri ve veri akışının bulunduğu çalışma alanı üzerinde yazma izinleri olan tüm üyeler, paylaşım için yeterince iyi olduğunu düşündükleri veri akışlarını doğrudan yükseltebilir.

* **Onaylama**: Onaylama veri akışının yetkili bir gözden geçiren tarafından denetlendiği ve gerçekten kuruluş genelinde kullanılmaya hazır, güvenilir ve yetkili bir veri kaynağı olduğu anlamına gelir. Hangi veri akışlarının onaylanacağına, Power BI kiracı yöneticisi tarafından seçilen bir grup gözden geçiren karar verir. Belirli bir veri akışının onaylanması gerektiğini düşünen ama onaylama yetkisi olmayan bir kullanıcı kiracı yöneticisiyle iletişim kurmalıdır.

  Veri akışının onaylanması ancak [Power BI kiracı yöneticisi tarafından etkinleştirilmişse](../admin/service-admin-setup-certification.md) mümkündür.

Veri akışını yükseltme veya onaylama işlemine *onay* adı verilir. Power BI rapor oluşturucularının çoğunlukla aralarından seçim yapabilecekleri birçok farklı veri akışı vardır ve onay işlemi onları güvenilir ve yetkili veri akışlarına yönlendirmeye yardımcı olur.

Onaylanmış veri akışları Power BI’ın birçok yerinde açıkça etiketlenmiştir ve bu da güvenilir veriler arayan rapor oluşturucularının bunları bulmasını kolaylaştırır. Ayrıca yöneticiler ve rapor oluşturucuları kuruluş genelinde bunların nasıl kullanıldığını kolayca izleyebilirler.

Aşağıdaki resimde yükseltilen ve onaylanan veri akışlarının Power Query’de nasıl kolayca belirlenebildiği gösterilir.

![Power Query’de vurgulanan onaylanmış veri akışları](media/service-dataflows-promote-certify/powerbi-dataflow-endorsement-power-query.png)

Bu makalede şunlar açıklanmaktadır:
* Veri akışını yükseltme (veri akışı sahibi veya veri akışının bulunduğu çalışma alanı üzerinde üye izinleri olan herhangi bir kullanıcı)
* Veri akışını onaylama (kiracı yöneticisi tarafından belirlenen yetkili veri akışı onaylayıcısı)

Veri akışı onaylamasını ayarlama (kiracı yöneticisi) hakkında bilgi için bkz. [Veri kümesi ve veri akışı onaylamasını ayarlama](../admin/service-admin-setup-certification.md)


## <a name="promote-a-dataflow"></a>Veri akışını yükseltme

Veri akışını yükseltmek için, yükseltmek istediğiniz veri akışının bulunduğu çalışma alanında yazma izinleriniz olmalıdır.

1. Çalışma alanındaki veri akışları listesine gidin.
 
1. Yükseltmek istediğiniz veri akışında **Diğer seçenekler** (...) öğesini seçin ve sonra da **Ayarlar**’ı seçin.

    ![Veri akışındaki üç noktayı seçin](media/service-dataflows-promote-certify/power-bi-dataflow-settings.png)

1. Onay bölümünü genişletin ve **Yükseltildi** öğesini seçin.

    ![Yükseltilen ve Uygula seçeneklerini belirleyin](media/service-dataflows-promote-certify/power-bi-dataflow-promoted-endorsement.png)

1. **Apply** (Uygula) seçeneğini belirleyin.

## <a name="certify-a-dataflow"></a>Veri akışını onaylama

Bu bölüm kiracı yöneticisi tarafından veri akışlarını onaylama yetkisi verilmiş kullanıcılara yöneliktir. Veri akışlarını onaylamak büyük bir sorumluluktur. Bu bölümde izleyeceğiniz onaylama süreci açıklanır.

1. Onaylamak istediğiniz veri akışının bulunduğu çalışma alanı üzerinde yazma izinleri alın. Bu izinler veri akışı sahibinden veya çalışma alanı üzerinde yönetici izinleri olan herhangi birinden alınabilir. 

1. Veri akışını dikkatle gözden geçirin ve onaylamaya değer olup olmadığını saptayın.

1. Veri akışını onaylamaya karar verirseniz, bunun bulunduğu çalışma alanına gidin.
 
1. Aradığınız veri akışını bulun, **Diğer seçenekler** (...) öğesine tıklayın ve **Ayarlar**’ı seçin.

    ![Veri kümesindeki veya veri akışındaki üç noktayı seçin](media/service-dataflows-promote-certify/power-bi-dataflow-settings.png)

1. Onay bölümünü genişletin ve **Onaylandı** öğesine tıklayın. 

    ![Daha fazla bilgi edinin bağlantısına tıklayın](media/service-dataflows-promote-certify/service-certify-datasets-dataflows.png)

2. **Uygula**'ya tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

* [Veri kümesi ve veri akışı onaylamasını ayarlama](../admin/service-admin-setup-certification.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)