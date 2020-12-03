---
title: İlişki sorunlarını giderme kılavuzu
description: Model ilişkisi sorunlarını gidermeye yönelik kılavuz.
author: peter-myers
ms.author: v-pemyer
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 03/02/2020
ms.openlocfilehash: e8f76bf1e1947815176a1b24be2b758489093071
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96418544"
---
# <a name="relationship-troubleshooting-guidance"></a>İlişki sorunlarını giderme kılavuzu

Bu makale, Power BI Desktop'la çalışan veri modelleyicilerine yöneliktir. Model ve rapor geliştirirken karşılaşabileceğiniz belirli sorunları giderme konusunda size yol gösterir.

[!INCLUDE [relationships-prerequisite-reading](includes/relationships-prerequisite-reading.md)]

## <a name="troubleshooting-checklist"></a>Sorun giderme denetim listesi

Rapor görseli iki (veya daha fazla) tablodaki alanları kullanacak şekilde yapılandırıldıysa ve doğru sonuç (veya hiç sonuç) göstermiyorsa, sorun model ilişkileriyle ilgili olabilir.

Bu durumda izlenecek genel sorun giderme denetim listesi aşağıda verilmiştir. Sorunları belirleyene kadar denetim listesinde ilerleyebilirsiniz.

1. Görseli bir tablo veya matrise dönüştürün veya "Verileri Görüntüle" bölmesini açın; sorgu sonucunu gördüğünüzde sorunları gidermek daha kolay olur
1. Sorgu sonucu boşsa Veri görünümüne geçin; tabloların veri satırlarıyla doldurulmuş olduğunu doğrulayın
1. Model görünümüne geçin; ilişkileri görmek ve özelliklerini hızla belirlemek daha kolay olur
1. Tablolar arasında ilişkilerin varlığını doğrulayın
1. Kardinalite özelliklerinin doğru yapılandırıldığından emin olun; “çok” tarafındaki bir sütun şu anda benzersiz değerler içeriyorsa ve yanlışlıkla “bir” tarafı olarak yapılandırıldıysa, bu özellikler yanlış olabilir
1. İlişkilerin etkin olduğunu doğrulayın (düz çizgi)
1. Filtre yönlerinin yaymayı desteklediğini doğrulayın (ok başlarına bakın)
1. Doğru sütunların ilişkilendirildiğinden emin olun; ilişkili sütunları ortaya çıkarmak için ilişkiyi seçin veya fareyle üzerine gelin
1. İlişkili sütun veri türlerinin aynı veya en azından uyumlu olduğunu doğrulayın; metin sütununu tamsayı sütunuyla ilişkilendirmek mümkündür ama filtreler yaymak için hiçbir eşleşme bulamaz
1. Veri görünümüne geçin ve ilişkili sütunlarda eşleşen değerlerin bulunabileceğini doğrulayın

## <a name="troubleshooting-guide"></a>Sorun giderme kılavuzu

Aşağıda sorunlar olası çözümleriyle birlikte listelenmiştir.

|Sorun|Olası nedenler|
|---------|---------|
|Görsel hiç sonuç görüntülemiyor|- Model henüz verilerle doldurulmamış<br />- Filtre bağlamı içinde hiç veri yok<br />- Satır düzeyi güvenlik zorunlu tutulmuş<br />- İlişkiler tablolar arasında yayılmıyor; _yukarıdaki denetim listesini izleyin_<br />- Satır düzeyi güvenlik zorunlu tutulmuş ama yayma işlemi için çift yönlü ilişki etkinleştirilmemiş; bkz. [Power BI Desktop ile satır düzeyi güvenlik (RLS)](../create-reports/desktop-rls.md)|
|Görselde her gruplandırma için aynı değer görüntüleniyor |- İlişki yok<br />- İlişkiler tablolar arasında yayılmıyor; _yukarıdaki denetim listesini izleyin_|
|Görselde sonuçlar gösteriliyor ama bunlar doğru değil|- Görsel yanlış yapılandırılmış<br />- Ölçü mantığı yanlış<br />- Model verilerinin yenilenmesi gerekiyor<br />- Kaynak veriler yanlış<br />- İlişki sütunları yanlış ilişkilendirilmiş (örneğin **ProductID** sütunu **CustomerID** ile eşlenmiş)<br />- Bu iki DirectQuery tablosu arasındaki bir ilişki ve ilişkinin "bir" tarafındaki sütun yinelenen değerler içeriyor|
|BOŞ gruplandırmalar veya dilimleyici/filtre öğeleri görüntüleniyor ve kaynak sütunlar BOŞLUK içermiyor|- Bu normal bir ilişki ve "çok" tarafındaki sütun "bir" tarafındaki sütunda depolanmamış değerler içeriyor; bkz. [Power BI Desktop’ta model ilişkileri (Normal ilişkiler)](../transform-model/desktop-relationships-understand.md#regular-relationships)<br />- Bu normal bir bire bir ilişki ve ilişkili sütunlar BOŞLUKLAR içeriyor; bkz. [Power BI Desktop’ta model ilişkileri (Normal ilişkiler)](../transform-model/desktop-relationships-understand.md#regular-relationships)<br />- Etkin olmayan bir ilişki ve "çok" tarafındaki sütun BOŞLUKLAR içeriyor veya "bir" tarafından depolanmamış değerleri var|
|Görselde eksik veriler var|- Yanlış/beklenmeyen filtreler uygulanmış<br />- Satır düzeyi güvenlik zorunlu tutulmuş<br />- Bu sınırlı bir ilişki ve ilişkili sütunlarda BOŞLUKLAR veya veri bütünlüğü sorunları var; bkz. [Power BI Desktop’ta model ilişkileri (sınırlı ilişkiler)](../transform-model/desktop-relationships-understand.md#limited-relationships)<br />- Bu iki DirectQuery tablosu arasındaki bir ilişki, [bilgi tutarlılığı varsayımıyla](../transform-model/desktop-relationships-understand.md#assume-referential-integrity) yapılandırılmış ama veri bütünlüğü sorunları var (ilişkili sütunlarda eşleşmeyen değerler)|
|Satır düzeyi güvenlik doğru zorlanmıyor|- İlişkiler tablolar arasında yayılmıyor; _yukarıdaki denetim listesini izleyin_<br />- Satır düzeyi güvenlik zorunlu tutulmuş ama yayma işlemi için çift yönlü ilişki etkinleştirilmemiş; bkz. [Power BI Desktop ile satır düzeyi güvenlik (RLS)](../create-reports/desktop-rls.md)|
|||

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Desktop’ta model ilişkileri](../transform-model/desktop-relationships-understand.md)
- Sorular? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
