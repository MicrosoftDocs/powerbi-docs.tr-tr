---
title: Örnek Power BI sayfalandırılmış raporları
description: Bu makalede, örnek Power BI sayfalandırılmış raporlarını nasıl indirip kullanabileceğinizi öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: swgupt
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 11/01/2020
ms.openlocfilehash: cf0e6a6e7cd40a5b8bb97560caf94b71c1b48e7a
ms.sourcegitcommit: ccf53e87ff7cba1fcd9d2cca761a561e62933f90
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2020
ms.locfileid: "93324118"
---
# <a name="sample-power-bi-paginated-reports"></a>Örnek Power BI sayfalandırılmış raporları


[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-service](../includes/yes-service.md)] [!INCLUDE [yes-paginated](../includes/yes-paginated.md)] [!INCLUDE [yes-premium](../includes/yes-premium.md)] [!INCLUDE [no-desktop](../includes/no-desktop.md)]

Bu makalede, indirip keşfedebileceğiniz birkaç örnek Power BI sayfalandırılmış raporuna ilişkin bilgiler ve bağlantılar sağlanır. Bunlar, sayfalandırılmış raporları kullanabileceğiniz yaygın yöntemleri gösterir.

## <a name="prerequisites"></a>Önkoşullar

- Bu raporları düzenleme yapmadan, olduğu gibi çevrimiçi ortamda paylaşabilirsiniz. Bunu yapmak için bir Power BI Pro lisansına ihtiyacınız vardır. [Power BI Pro lisansı için ücretsiz denemeye](../fundamentals/service-self-service-signup-for-power-bi.md#sign-up-for-an-individual-trial-of-power-bi-pro) kaydolun.
- Ayrıca [Premium kapasitede](../admin/service-premium-what-is.md) bulunan bir Power BI çalışma alanına erişiminiz olması gerekir.
- Bu raporları düzenlemek için, Microsoft İndirme Merkezi’nden [Power BI Rapor Oluşturucusu’nu yüklemeniz](https://aka.ms/pbireportbuilder) gerekir.
- Şimdi GitHub’dan [bu örnek sayfalandırılmış raporları indirmeye](https://github.com/microsoft/Reporting-Services/tree/master/PaginatedReportSamples) hazırsınız. GitHub hesabınız olması gerekmez. 


## <a name="invoice"></a>Fatura

:::image type="content" source="media/paginated-reports-samples/paginated-report-invoice.png" alt-text="Örnek Power BI sayfalandırılmış raporu faturasının ekran görüntüsü.":::


Bu sayfalandırılmış rapor, bağımsız bir faturadır. Bu raporun yer aldığı senaryoda piksel bakımından kusursuz, yazdırılabilir bir fatura istiyorsunuz. Öğe açıklamaları, miktarlar, indirimler ve maliyet gibi ayrıntıların listelendiği toplam satışları göstermesi gerekiyor.

Bu örnekte, aşağıdakiler gibi gerçek hayatta kullanılan faturalar oluşturmak için gereken benzersiz özellikler vurgulanır:  

- Tablix (hem tabloları hem de matrisleri içeren veri bölgesi). Bu, hem dinamik olarak oluşturulan ve kullanıcıya özgü olan içeriği hem de temayı görüntüler.
- Rapor gövdesinin tablix’inin her satırına yerleştirilmiş dikdörtgen veri bölgesi.
- Metin kutuları ve satırlar gibi rapor öğeleri.
- İçeriği dinamik olarak seçmeye yönelik bir rapor parametresi. İfade yer tutucularının kullanıldığı bu içerik, belirli bir konuyla ilgilidir. 

Veri kaynağı: .rdl dosyasına dahil

## <a name="labels"></a>Etiketler

:::image type="content" source="media/paginated-reports-samples/paginated-report-labels.png" alt-text="Sayfalandırılmış rapor etiketlerinin ekran görüntüsü.":::

Bu, bağımsız bir sayfalandırılmış rapor örneğidir. Bu çok sütunlu rapor, posta etiket şablonunun yazdırma düzenine kusursuz bir şekilde sığar. 

Etiket raporları basittir, ancak bir sayfalandırılmış etiket oluşturmak için birkaç benzersiz özellik gerekir:

- Tanımlı sütun aralıklarına sahip üç sabit sütun içeren bir tablix.
- Yazdırılan sayfadaki satır ve sütunlarda yinelenen dikdörtgen bir veri bölgesi.
- Her dikdörtgen veri bölgesinde gösterilecek içeriği seçmeye yarayan bir rapor parametresi.

Veri kaynağı: .rdl dosyasına dahil

## <a name="mailing-letter"></a>Posta mektubu

:::image type="content" source="media/paginated-reports-samples/paginated-report-letter.png" alt-text="Örnek Power BI sayfalandırılmış rapor mektubunun ekran görüntüsü.":::

Bu bağımsız sayfalandırılmış rapor örneği, gerçek dünyada kullanılan postalama mektupları oluşturmak için tasarlanmıştır. Bu raporun yer aldığı senaryoda piksel bakımından kusursuz, dinamik içeriğe sahip yazdırılabilir bir mektup istiyorsunuz.

Bu örnekte de aşağıdakiler gibi benzer özellikler vardır: 

- Dikdörtgen veri bölgesi, rapor gövdesinin farklı bölümlerine yerleştirilir. 
- Mektubu kişiselleştirebileceğiniz resimler. 
- Tablix veri bölgesi (hem tabloları hem de matrisleri içeren veri bölgesi). Tablix, dinamik olarak oluşturulan ve kullanıcıya özgü içeriği görüntüler.
- Metin kutuları ve satırlar gibi rapor öğeleri.
- İçeriği dinamik olarak seçmeye yönelik bir rapor parametresi. İfade yer tutucularının kullanıldığı bu içerik, belirli bir konuyla ilgilidir. 

Veri kaynağı: .rdl dosyasına dahil

## <a name="transcript"></a>Döküm

:::image type="content" source="media/paginated-reports-samples/paginated-report-transcript.png" alt-text="Örnek Power BI sayfalandırılmış rapor dökümünün ekran görüntüsü.":::

Bu raporun yer aldığı senaryoda piksel bakımından kusursuz, yazdırılabilir bir döküm istiyorsunuz. Dinamik içerik listelemesi program açıklaması ayrıntılarını ve her öğrenci için tarihleri içermesi gerekir.

Bu bağımsız sayfalandırılmış rapor örneğinde aşağıdakiler gibi benzersiz özellikler yer alır: 

- Tablix veri bölgesi (hem tabloları hem de matrisleri içeren veri bölgesi). Tablix, iç içe yerleştirilmiş satır gruplarını kullanarak dinamik olarak oluşturulan ve kullanıcıya özgü içeriği görüntüler.
- Dikdörtgen veri bölgeleri, rapor gövdesinin farklı bölümlerine yerleştirilir.
- Metin kutuları ve satırlar gibi rapor öğeleri.

Veri kaynağı: .rdl dosyasına dahil

## <a name="sales-performance"></a>Satış Performansı

:::image type="content" source="media/paginated-reports-samples/paginated-report-sales-performance.png" alt-text="Satış Performansı için örnek Power BI sayfalandırılmış rapor dökümünün ekran görüntüsü.":::

Ülke Satış Performansı, bağımsız bir sayfalandırılmış rapor örneğidir. Bu raporun yer aldığı senaryoda toplam satışları ve ayrıntıları görmek için piksel bakımından kusursuz, yazdırılabilir bir fatura istiyorsunuz. Rapor aşağıdaki özelliklere sahiptir:

- Tablodaki ayrıntıları genişletmek için parametre kullanımı.
- Üst bilgiler ve alt bilgiler.
- İfade yer tutucularının kullanıldığı metin kutusu, çizgi ve dikdörtgenler gibi rapor öğeleri.
- Veri çubukları.
- Eğilimler.
- Ölçer panelleri.

Veri kaynağı: .rdl dosyasına dahil
  
## <a name="next-steps"></a>Sonraki adımlar

[Power BI hizmetinde sayfalandırılmış rapor görüntüleme](../consumer/paginated-reports-view-power-bi-service.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)