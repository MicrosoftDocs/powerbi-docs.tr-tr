---
title: Sayfalandırılmış raporları yazdırırken boş sayfalardan kaçınma
description: Sayfalandırılmış raporları yazdırırken boş sayfalardan kaçınacak şekilde tasarlama yönergeleri.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 01/14/2020
ms.author: v-pemyer
ms.openlocfilehash: 349459b95a815a52665e50687554f81f90a9c81b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "78920818"
---
# <a name="avoid-blank-pages-when-printing-paginated-reports"></a>Sayfalandırılmış raporları yazdırırken boş sayfalardan kaçınma

Bu makale Power BI [sayfalandırılmış raporları](../paginated-reports/paginated-reports-report-builder-power-bi.md) tasarlayan rapor yazarlarına yöneliktir. Raporunuz sabit sayfa biçimine aktarıldığında (PDF veya Microsoft Word gibi) veya yazdırıldığında boş sayfalar içermesini önlemenize yardımcı olacak öneriler sağlar.

## <a name="page-setup"></a>Sayfa yapısı

Rapor sayfa boyutu özellikleri sayfa yönlendirmesini, boyutlarını ve kenar boşluklarını belirler. Bu rapor özelliklerine şöyle erişebilirsiniz:

- Raporun **Özellik Sayfasını** kullanarak: Rapor tuvalinin dışındaki koyu gri alana sağ tıklayın ve _Rapor Özellikleri_’ni seçin.
- [**Özellikler** bölmesini](../paginated-reports/paginated-reports-report-design-view.md#4-properties-pane) kullanarak: Rapor tuvalinin dışındaki koyu gri alana sağ tıklayarak rapor nesnesini seçin. **Özellikler** bölmesinin açık olmasına dikkat edin.

Rapor **Özellik Sayfasının** **Sayfa Yapısı** sayfası, sayfa yapısı özelliklerini görüntülemek ve güncelleştirmek için kullanımı kolay bir arabirim sağlar.

![Resimde Sayfa Yapısı sayfasının vurgulandığı Rapor Özellikleri penceresi gösterilir.](media/report-paginated-blank-page/report-page-setup-properties.png)

Tüm sayfa boyutu özelliklerinin doğru yapılandırıldığından emin olun:

|Özellik|Öneri|
|---------|---------|
|Sayfa birimleri|Uygun birimleri (inç veya santimetre) seçin.|
|Yön|Doğru seçeneği (dikey veya yatay) seçin.|
|Kağıt boyutu|Kağıt boyutunu seçin veya özel genişlik ve yükseklik değerleri atayın.|
|Kenar boşlukları|Sol, sağ, üst ve alt kenar boşlukları için uygun değerleri ayarlayın.|
|||

## <a name="report-body-width"></a>Rapor gövdesi genişliği

Sayfa boyutu özellikleri rapor nesneleri için kullanılabilecek alanı belirler. Rapor nesneleri veri bölgeleri, veri görselleştirmeleri veya diğer rapor öğeleri olabilir.

Çıkıştı boş sayfaların bulunmasının yaygın bir nedeni rapor gövdesi genişliğinin _kullanılabilir sayfa alanını aşmasıdır_.

Rapor gövdesi genişliğini yalnızca **Özellikler** bölmesini kullanarak görüntüleyebilir ve ayarlayabilirsiniz. İlk olarak rapor gövdesinin boş alanında herhangi bir yere tıklayın.

![Resimde rapor gövdesi genişliği özelliğinin vurgulandığı Özellikler bölmesi gösterilir.](media/report-paginated-blank-page/report-body-properties-width.png)

Genişlik değerinin kullanılabilir sayfa genişliğini aşmadığından emin olun. Aşağıdaki formülden yararlanın:

```Report body width <= Report page width - (Left margin + Right margin)```

> [!NOTE]
> Kaldırmak istediğiniz alanda zaten rapor nesneleri bulunuyorsa, rapor gövdesi genişliğini azaltmanız mümkün olmaz. Genişliği azaltmadan önce bunları yeniden konumlandırmalı veya yeniden boyutlandırmalısınız.
>
> Ayrıca yeni nesneler eklediğinizde, mevcut nesneleri yeniden boyutlandırdığınızda veya yeniden konumlandırdığınızda rapor gövdesi genişliği otomatik olarak artar. Rapor tasarımcıları her zaman rapora eklediği nesnelerin konumunu ve boyutunu sığdırmak için gövdeyi genişletir.

## <a name="report-body-height"></a>Rapor gövdesi yüksekliği

Çıkışta boş sayfa bulunmasının bir diğer nedeni de son nesneden sonra rapor gövdesinde fazladan alan bulunmasıdır.

Her zaman gövdenin yüksekliğini azaltarak sondaki alanları kaldırmanızı öneririz.

![Resimde rapor tasarımı gösterilir. Tablix veri bölgesinin altındaki alan vurgulanmış ve gereksiz olarak işaretlenmiştir.](media/report-paginated-blank-page/report-body-remove-trailing-space.png)

## <a name="page-break-options"></a>Sayfa sonu seçenekleri

Her veri bölgesinin ve veri görselleştirmesinin sayfa sonu seçenekleri vardır. Bu seçeneklere söz konusu öğenin özellik sayfasında veya **Özellikler** bölmesinde erişebilirsiniz.

**Şundan sonra sayfa sonu ekle** özelliğinin gerekmedikçe etkinleştirilmediğinden emin olun.

![Resimde tablix Özellikler penceresi gösterilir. "Şundan sonra sayfa sonu ekle" özelliği etkinleştirilmiştir.](media/report-paginated-blank-page/data-region-page-break-option-after.png)

## <a name="consume-container-whitespace"></a>Kapsayıcı Boşluğunu kullanma

Boş sayfa sorunu devam ediyorsa raporun**ConsumeContainerWhitespace** özelliğini devre dışı bırakmayı da deneyebilirsiniz. Bu özellik yalnızca **Özellikler** bölmesinde ayarlanabilir.

![Resimde ConsumeContainerWhitespace özelliğinin vurgulandığı Özellikler bölmesi gösterilir.](media/report-paginated-blank-page/report-properties-consumecontainerwhitespace.png)

Bu özellik varsayılan olarak etkindir. Rapor gövdesi veya dikdörtgen gibi kapsayıcılardaki en küçük boşluğun kullanılıp kullanılmayacağını belirler. Yalnızca içeriğin sağ tarafındaki ve altındaki boşluk bu özellikten etkilenir.

## <a name="printer-paper-size"></a>Yazıcı kağıt boyutu

Son olarak raporu kağıda yazdırıyorsanız yazıcıda doğru kağıdın yüklü olduğundan emin olun. Fiziksel kağıt boyutu [rapor kağıt boyutuyla](#page-setup) eşleşmelidir.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](../paginated-reports/paginated-reports-report-builder-power-bi.md)
- [Power BI sayfalandırılmış raporlarında sayfalandırma](../paginated-reports/paginated-reports-pagination.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)
