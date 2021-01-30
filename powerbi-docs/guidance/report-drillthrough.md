---
title: Rapor sayfası detaylandırmayı kullanma
description: Rapor sayfasını detaylandırmayla çalışma yönergeleri.
author: peter-myers
ms.author: kfollis
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 11/28/2019
ms.openlocfilehash: d89e26c0e938504fe64e0f966d27c76e059949a6
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99085533"
---
# <a name="use-report-page-drillthrough"></a>Rapor sayfası detaylandırmayı kullanma

Bu makale Power BI raporları tasarlayan rapor yazarlarına yöneliktir. [Rapor sayfasını detaylandırmayı](../create-reports/desktop-drillthrough.md) oluşturma işlemiyle ilgili öneriler sağlar.

Raporunuzu tasarlarken rapor kullanıcılarının aşağıdaki akışı başarabileceği bir tasarım yapmanızı öneririz:

1. Rapor sayfasını görüntüleme.
2. Daha derin bir analiz için görsel öğeyi belirleme.
3. Detaylandırmak için görsel öğeye sağ tıklama.
4. Tamamlayıcı analiz gerçekleştirme.
5. Kaynak rapor sayfasına dönme.

## <a name="suggestions"></a>Öneriler

İki tür detaylandırma senaryosunu göz önünde bulundurmanızı öneririz:

- [Ek derinlik](#additional-depth)
- [Daha geniş perspektif](#broader-perspective)

### <a name="additional-depth"></a>Ek derinlik

Rapor sayfanızda özetlenmiş sonuçlar görüntülendiğinde, detaylandırma sayfası rapor kullanıcılarını işlem düzeyi ayrıntılarına yönlendirebilir. Bu tasarım yaklaşımı kullanıcıların destekleyen işlemleri yalnızca gerektiğinde görüntüleyebilmesine olanak tanır.

Aşağıdaki örnek, rapor kullanıcısı aylık satış özetinden detaylandırdığında neler olduğunu gösterir. Detaylandırma sayfası belirli bir aya ilişkin siparişlerin ayrıntılı listesini içerir.

!["Sales Summary" başlıklı bir matris görseli, satışları satırlarda yıla ve aya, sütunlarda ise ülkeye göre gruplandırır. Detaylandırma sayfası da görüntülenir.](media/report-drillthrough/suggestion-drillthrough-add-depth.png)

### <a name="broader-perspective"></a>Daha geniş perspektif

Detaylandırma sayfası ek derinliğin tersini sağlayabilir. Bu senaryo bütünsel bir görünümde detaylandırmak için harika bir seçenektir.

Aşağıdaki örnek, rapor kullanıcısı posta kodundan detaylandırdığında neler olduğunu gösterir. Detaylandırma sayfasında bu posta kodu hakkındaki genel bilgiler görüntülenir.

![Tablo görselinin üç sütunu vardır: Zip Code, Average of Violation Points ve Average of Grade Rating. Detaylandırma sayfası da görüntülenir.](media/report-drillthrough/suggestion-drillthrough-broader-perspective.png)

## <a name="recommendations"></a>Öneriler

Rapor tasarımı sırasında aşağıdaki uygulamaları öneririz:

- **Stil:** Detaylandırma sayfanızı raporla aynı temayı ve stili kullanarak tasarlamayı göz önünde bulundurun. Bu şekilde kullanıcılar raporun dışına çıkmamış gibi hissedebilirler.
- **Detaylandırma filtreleri:** Detaylandırma sayfasını tasarlarken gerçekçi bir sonuç önizlemesi elde edebilmek için detaylandırma filtrelerini ayarlayın. Raporu yayımlamadan önce bu filtreleri kaldırmayı unutmayın.
- **Ek özellikler:** Detaylandırma sayfası herhangi bir rapor sayfası gibidir. Hatta dilimleyiciler ve filtreler gibi etkileşimli özelliklerle bu sayfayı geliştirebilirsiniz.
- **Boşluklar:** Detaylandırma filtreleri uygulandığında BOŞLUK görüntüleyebilen veya hata oluşturabilen görseller eklemekten kaçının.
- **Sayfa görünürlüğü:** Detaylandırma sayfalarını gizlemeyi göz önünde bulundurun. Detaylandırma sayfasını görünür tutmaya karar verirseniz, kullanıcıların daha önce ayarlanmış detaylandırma filtrelerini temizlemesini sağlayacak bir düğme eklediğinizden emin olun. Düğmeye bir [yer işareti](../create-reports/desktop-bookmarks.md) atayın. Yer işareti tüm filtreleri kaldıracak şekilde yapılandırılmalıdır.
- **Geri düğmesi:** Bir detaylandırma filtresi atadığınızda otomatik olarak geri [düğmesi](../create-reports/desktop-buttons.md) eklenir. Bunu alıkoymak iyi bir yaklaşımdır. Bu şekilde rapor kullanıcılarınız kaynak sayfaya kolayca dönebilir.
- **Bulma:** Görsel üst bilgisi simge metni ayarlayarak veya bir metin kutusuna yönergeler ekleyerek detaylandırma sayfasıyla ilgili farkındalığı artırmaya yardımcı olun. Ayrıca [bu blog gönderisinde](https://alluringbi.com/2019/10/23/overlays-for-true-self-serve-reporting/) açıklandığı gibi bir katman tasarlayabilirsiniz.

> [!TIP]
> Power BI sayfalandırılmış raporlarınız için detaylandırma yapılandırmak da mümkündür. Bunu, Power BI raporlarına bağlantılar ekleyerek yapabilirsiniz. Bağlantılar [URL parametrelerini](https://powerbi.microsoft.com/blog/url-parameters-for-paginated-reports-are-now-available/) tanımlayabilir.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Desktop'ta detaylandırma özelliğini kullanma](../create-reports/desktop-drillthrough.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
