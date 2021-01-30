---
title: Power Query arka plan yenilemesini devre dışı bırakma
description: Power Query arka plan yenilemesinin ne zaman devre dışı bırakılacağına ilişkin yönergeler.
author: peter-myers
ms.author: kfollis
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 09/26/2019
ms.openlocfilehash: e620841089cd7a039fc157fe8b3f8f0857773cb8
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99087465"
---
# <a name="disable-power-query-background-refresh"></a>Power Query arka plan yenilemesini devre dışı bırakma

Bu makale, Power BI Desktop'ta içeri aktarılan veri modelleyicilerine yöneliktir.

Varsayılan olarak Power Query verileri içeri aktardığında ayrıca her sorgu için en çok 1000 satır önizleme verisini önbelleğe alır. Önizleme verileri, sorgularınızın her satırı için size kaynak verilerin ve dönüştürme sonuçlarının hızlı bir önizlemesini göstermeye yardımcı olur. Bunlar Power BI Desktop dosyasının içinde değil diskte ayrı olarak depolanır.

Öte yandan Power BI Desktop dosyanız birçok sorgu içerdiğinde, önizleme verilerini almak ve depolamak bir yenilemenin tamamlanma süresini uzatabilir.

## <a name="recommendation"></a>Öneri

Power BI Desktop dosyasını önizleme önbelleğinin _arka planda_ güncelleştirileceği şekilde ayarlayarak yenilemeyi hızlandırabilirsiniz. Power BI Desktop'ta _Dosya > Seçenekler ve ayarlar > Seçenekler_'i ve sonra da _Veri Yükleme_ sayfasını seçerek bunu etkinleştirirsiniz. Ardından **Veri önizlemesinin arka plana indirilmesine izin verme** seçeneğini açabilirsiniz. Bu seçeneğin yalnızca geçerli dosya için ayarlanabileceğine dikkat edin.

![Arka plan veri seçeneklerini gösteren Power BI Desktop’ın ekran görüntüsü.](media/power-query-background-refresh/power-query-options-background-data.png)

Arka planda yenileme etkinleştirildiğinde, sonuçta önizleme verilerinin süresi dolabilir. Böyle bir durumda Power Query Düzenleyicisi size aşağıdaki uyarıyı bildirir:

![Power Query Düzenleyicisi’nin eski önizleme verileri hakkındaki uyarısını gösteren Power BI Desktop’ın ekran görüntüsü.](media/power-query-background-refresh/power-query-preview-data-old.png)

Önizleme önbelleğini güncelleştirmek her zaman mümkündür. **Önizlemeyi Yenile** komutu kullanarak bunu tek sorgu için veya tüm sorgular için güncelleştirebilirsiniz. Bunu Power Query Düzenleyicisi penceresinin **Giriş** şeridinde bulabilirsiniz.

![Önizleme verilerini yenilemeye yönelik Power Query Düzenleyicisi komutlarını gösteren Power BI Desktop’ın ekran görüntüsü.](media/power-query-background-refresh/power-query-refresh-preview-data.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power Query Belgeleri](/power-query/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
