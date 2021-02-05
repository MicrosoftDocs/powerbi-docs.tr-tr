---
title: Power BI Soru-Cevap sınırlamaları
description: Power BI Soru-Cevap için geçerli sınırlamalar
author: maggiesMSFT
ms.author: maggies
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: conceptual
ms.date: 09/09/2020
ms.openlocfilehash: 74e99f42677c6adda73a8b5e2e3043e2d039f5b3
ms.sourcegitcommit: afdc9d41da6a4fced63030648d3f976425131732
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2021
ms.locfileid: "99569911"
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

**Soru-Cevap için DirectQuery desteği** (önizleme)

Soru-Cevap artık SQL Server 2019, Azure SQL Veritabanı ve Azure Synapse Analytics gibi SQL DirectQuery kaynaklarını destekler. Bu veri kaynaklarına karşı doğal dil soruları sormak için Soru-Cevap özelliğini kullanabilirsiniz. DirectQuery modundayken Soru-Cevap davranışı üzerinde küçük bir değişiklik vardır: Sorunuzu yazdıktan sonra **Gönder** düğmesini seçersiniz. Bu değişiklik, siz yazarken gereksiz sorgularla DirectQuery kaynağının aşırı yüklenmesini engeller.

### <a name="data-sources-not-supported"></a>Desteklenmeyen veri kaynakları

Power BI Soru-Cevap şu anda aşağıdaki yapılandırmaları desteklemez:

- Herhangi bir veri kaynağı türüyle nesne düzeyi güvenlik
- Bileşik modeller
- Reporting Services 

## <a name="tooling-limitations"></a>Araç sınırlamaları

Yeni araç iletişim kutusu, kullanıcıların Soru-Cevap’taki doğal dili özelleştirip iyileştirmesini sağlar. Araç hakkında daha fazla bilgi edinmek için [Soru-Cevap araçlarına giriş](q-and-a-tooling-intro.md) makalesini okuyun.

## <a name="review-question-limitations"></a>İnceleme sorusu sınırlamaları

İnceleme soruları yalnızca 28 güne kadar veri modeliniz için sorulmuş soruları depolar. Yeni inceleme soruları özelliğini kullanırken bazı soruların kaydedilmediğini fark edebilirsiniz. Doğal dil altyapısı bir kullanıcının her tuş dokunuşunun kaydedilmediğinden veya gösterilmediğinden emin olmak için bir dizi veri temizleme adımı gerçekleştirdiği için, bunların kaydedilmemesi tasarıma bilerek eklenmiştir.

Power BI yöneticileri, soru depolama özelliğini yönetmek için kiracı ayarlarını kullanabilir. İzinler güvenlik gruplarını temel alır. 

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
