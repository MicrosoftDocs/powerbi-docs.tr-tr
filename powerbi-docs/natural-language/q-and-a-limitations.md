---
title: Power BI Soru-Cevap sınırlamaları
description: Power BI Soru-Cevap için geçerli sınırlamalar
author: mohaali
manager: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/18/2019
ms.author: mohaali
ms.openlocfilehash: fc4a605f1258bcd93e0b49b596cc3a1691ce2edb
ms.sourcegitcommit: 26123c6bb24c8174beb390f4e06fb938d31238ea
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72717910"
---
# <a name="limitations-of-power-bi-qa"></a>Power BI Soru-Cevap sınırlamaları

Power BI Soru-Cevap şu anda bazı sınırlamalara tabidir.

## <a name="data-sources"></a>Veri kaynakları

### <a name="supported-data-sources"></a>Desteklenen veri kaynakları

Power BI Soru-Cevap, Power BI hizmetindeki veri kaynaklarının aşağıdaki yapılandırmalarını destekler:

- İçeri aktarma modu
- Azure Analysis Services'e canlı bağlanma
- Sql Server Analysis Services’e (ağ geçidi ile) canlı bağlanma
- Power BI veri kümeleri. Power BI Desktop bir Power BI veri kümesi kullanırken Soru-Cevap ile ilgili bir hata rapor eder. Ancak, raporu Power BI hizmeti yayımladığınızda hata kaybolur.

Bu yapılandırmaların her birinde, satır düzeyi güvenlik de desteklenir.

### <a name="data-sources-not-supported"></a>Desteklenmeyen veri kaynakları

Power BI Soru-Cevap şu anda aşağıdaki yapılandırmaları desteklemez:

- Herhangi bir veri kaynağı türüyle nesne düzeyi güvenlik
- Herhangi bir kaynağa göre DirectQuery. Bunu desteklemeye yönelik geçici bir çözüm, Live Connect’i DirectQuery kullanan Azure Analysis Services ile birlikte kullanmaktır.
- Bileşik modeller
- Reporting Services 

## <a name="tooling-limitations"></a>Araç sınırlamaları

Yeni araç iletişim kutusu, kullanıcıların Soru-Cevap’taki doğal dili özelleştirip iyileştirmesini sağlar. Araç hakkında daha fazla bilgi edinmek için [Soru-Cevap araçlarına giriş](q-and-a-tooling-intro.md) makalesini okuyun.

## <a name="review-question-limitations"></a>İnceleme sorusu sınırlamaları

İnceleme soruları yalnızca 28 güne kadar veri modeliniz için sorulmuş soruları depolar. Yeni inceleme soruları özelliğini kullanırken bazı soruların kaydedilmediğini fark edebilirsiniz. Doğal dil altyapısı bir kullanıcının her tuş dokunuşunun kaydedilmediğinden veya gösterilmediğinden emin olmak için bir dizi veri temizleme adımı gerçekleştirdiği için bu özellik, tasarıma bilerek eklenmiştir.

Kiracı yöneticileri, soru depolama özelliğini yönetmek için kiracı yöneticisi ayarlarını kullanabilir. İzinler güvenlik gruplarını temel alır. 

Kullanıcılar ayrıca **Ayarlar** > **Genel**’i seçip **Soru-Cevap’ın ifademi kaydetmesine izin ver** kutusunun işaretini kaldırarak sorularının kaydedilmesini engelleyebilir. 

## <a name="teach-qa-limitations"></a>Soru-Cevap Öğretimi sınırlamaları

Soru-Cevap Öğretimi iki tür hatayı düzeltmenize izin verir:

- Bir sözcüğü bir alana atama.
- Bir sözcüğe bir filtre koşulu atama.

Şu anda tanınan bir terimi yeniden tanımlamayı veya diğer koşul ya da tümcecik türlerini tanımlamayı desteklemiyoruz. Ayrıca, filtreleme koşullarını tanımlarken aşağıdakiler de dahil olmak üzere yalnızca sınırlı bir dil alt kümesi kullanabilirsiniz:

- 'ABD' olan 'Ülke'
- 'ABD' olmayan 'Ülke'
- 'Ağırlık' > 2000
- 'Ağırlık' = 2000
- 'Ağırlık' < 2000

> [!NOTE]
> Soru-Cevap Aracı yalnızca içeri aktarma modunu destekler. Henüz bir şirket içi veya Azure Analysis Services veri kaynağına bağlanmayı desteklememektedir. Bu mevcut sınırlama, Power BI’ın sonraki yayınlarında kaldırılacaktır.

### <a name="statements-not-supported"></a>Desteklenmeyen deyimler

- Koşullarda ölçülerin kullanımı şu anda desteklenmemektedir. Bunun yerine, ölçüleri çalıştırmak için hesaplanmış sütunlara dönüştürün.
- Birden fazla koşul desteklenmemektedir. Geçici bir çözüm olarak, çok durumlu bir deyim Boole değerini değerlendiren bir DAX hesaplanmış sütunu oluşturun ve onun yerine bu alanı kullanın.
- Soru-Cevap bir veri alt kümesi sorduğunda filtre koşulu belirtmezseniz, deyimin tamamında kırmızı alt çizgi olmasa bile tanımı kaydedemezsiniz.
