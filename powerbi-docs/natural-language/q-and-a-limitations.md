---
title: Power BI Soru-Cevap sınırlamaları
description: Power BI Soru-Cevap için geçerli sınırlamalar
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/21/2020
ms.author: maggies
ms.openlocfilehash: eebb40d81e9b59b545b30ce55dbf4a362b826455
ms.sourcegitcommit: 13c4bec679313f2951f1833033316cb8176da8a1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88937597"
---
# <a name="limitations-of-power-bi-qa"></a>Power BI Soru-Cevap sınırlamaları

Power BI Soru-Cevap şu anda bazı sınırlamalara tabidir.

## <a name="data-sources"></a>Veri kaynakları

### <a name="supported-data-sources"></a>Desteklenen veri kaynakları

Power BI Soru-Cevap, Power BI hizmetindeki veri kaynaklarının aşağıdaki yapılandırmalarını destekler:

- İçeri aktarma modu
- Azure Analysis Services'e canlı bağlanma
- SQL Server Analysis Services’e (ağ geçidi ile) canlı bağlanma
- Power BI veri kümeleri.

Bu yapılandırmaların her birinde, satır düzeyi güvenlik de desteklenir.

### <a name="data-sources-not-supported"></a>Desteklenmeyen veri kaynakları

Power BI Soru-Cevap şu anda aşağıdaki yapılandırmaları desteklemez:

- Herhangi bir veri kaynağı türüyle nesne düzeyi güvenlik
- Herhangi bir kaynağa göre DirectQuery. Geçici bir çözüm, DirectQuery kullanan Azure Analysis Services’le Canlı bağlantı kullanmaktır.
- Bileşik modeller
- Reporting Services 

## <a name="tooling-limitations"></a>Araç sınırlamaları

Yeni araç iletişim kutusu, kullanıcıların Soru-Cevap’taki doğal dili özelleştirip iyileştirmesini sağlar. Araç hakkında daha fazla bilgi edinmek için [Soru-Cevap araçlarına giriş](q-and-a-tooling-intro.md) makalesini okuyun.

## <a name="review-question-limitations"></a>İnceleme sorusu sınırlamaları

İnceleme soruları yalnızca 28 güne kadar veri modeliniz için sorulmuş soruları depolar. Yeni inceleme soruları özelliğini kullanırken bazı soruların kaydedilmediğini fark edebilirsiniz. Doğal dil altyapısı bir kullanıcının her tuş dokunuşunun kaydedilmediğinden veya gösterilmediğinden emin olmak için bir dizi veri temizleme adımı gerçekleştirdiği için, bunların kaydedilmemesi tasarıma bilerek eklenmiştir.

Kiracı yöneticileri, soru depolama özelliğini yönetmek için kiracı yöneticisi ayarlarını kullanabilir. İzinler güvenlik gruplarını temel alır. 

Kullanıcılar ayrıca **Ayarlar** > **Genel**’i seçip **Soru-Cevap’ın ifademi kaydetmesine izin ver** kutusunun işaretini kaldırarak sorularının kaydedilmesini engelleyebilir. 

## <a name="teach-qa-limitations"></a>Soru-Cevap Öğretimi sınırlamaları

Soru-Cevap Öğretimi iki tür hatayı düzeltmenize izin verir:

- Bir sözcüğü bir alana atama.
- Bir sözcüğe bir filtre koşulu atama.

Şu anda tanınan bir terimi yeniden tanımlamayı veya diğer koşul ya da tümcecik türlerini tanımlamayı desteklemiyoruz. Ayrıca, filtreleme koşullarını tanımlarken aşağıdakiler de dahil olmak üzere yalnızca sınırlı bir dil alt kümesi kullanabilirsiniz:

- ABD olan Ülke
- ABD olmayan Ülke
- Ürünler > 100
- 100’den büyük olan Ürünler
- Ürünler = 100
- 100’e eşit Ürünler
- Ürünler < 100
- 100’den küçük olan Ürünler

> [!NOTE]
> Soru-Cevap Aracı yalnızca içeri aktarma modunu destekler. Henüz bir şirket içi veya Azure Analysis Services veri kaynağına bağlanmayı desteklememektedir. Bu mevcut sınırlama, Power BI’ın sonraki yayınlarında kaldırılacaktır.

### <a name="statements-not-supported"></a>Desteklenmeyen deyimler

- Birden fazla koşul desteklenmemektedir. Geçici bir çözüm olarak, çok durumlu bir deyim Boole değerini değerlendiren bir DAX hesaplanmış sütunu oluşturun ve onun yerine bu alanı kullanın.
- Soru-Cevap bir veri alt kümesi sorduğunda filtre koşulu belirtmezseniz, deyimin tamamında kırmızı alt çizgi olmasa bile tanımı kaydedemezsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Doğal dil altyapısını iyileştirmeye yönelik birkaç en iyi yöntem vardır. Daha fazla bilgi için bkz. [Soru-Cevap ile ilgili en iyi yöntemler](q-and-a-best-practices.md).
