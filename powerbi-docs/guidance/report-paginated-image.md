---
title: Sayfalandırılmış raporlar için görüntü kullanım kılavuzu
description: Power BI sayfalandırılmış raporlarında görüntü kullanma hakkında kılavuz.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 02/16/2020
ms.author: v-pemyer
ms.openlocfilehash: 09fd2197cca31e083c0242b187d7e242244235eb
ms.sourcegitcommit: b22a9a43f61ed7fc0ced1924eec71b2534ac63f3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77530384"
---
# <a name="image-use-guidance-for-paginated-reports"></a>Sayfalandırılmış raporlar için görüntü kullanım kılavuzu

Bu makale Power BI [sayfalandırılmış raporları](../paginated-reports-report-builder-power-bi.md) tasarlayan rapor yazarlarına yöneliktir. Görüntülerle çalışırken öneriler sunar. Rapor düzenlerindeki görüntüler genellikle şirket logosu veya resimler gibi grafik öğeleri görüntüleyebilir.

Görüntüler üç farklı konumda depolanabilir:

- Raporun içinde (eklenmiş)
- Web sunucusunda
- Bir veri kümesi tarafından alınabilecek şekilde bir veritabanında

Bu öğeleri rapor düzenlerinizde farklı senaryolarda kullanabilirsiniz:

- Serbest logo veya resim
- Veri satırlarıyla ilişkili resimler
- Belirli rapor öğeleri için arka plan:
  - Rapor gövdesi
  - Metin Kutusu
  - Dikdörtgen
  - Tablix veri bölgesi (tablo, matris veya liste)

## <a name="suggestions"></a>Öneriler

Profesyonel rapor düzenleri, bakım kolaylığı ve iyileştirilmiş rapor performansı elde etmek için aşağıdaki önerileri dikkate alın:

- **Mümkün olan en küçük boyutu kullanın**: Küçük ancak yine de net ve keskin görüntüler hazırlamanız önerilir. Kalite ile boyut arasında bir denge yakalamanız gerekir. Görüntü dosyasının boyutunu küçültmek için bir grafik düzenleyicisi (MS Paint gibi) kullanın.
- **Eklenmiş görüntülerden kaçının**: Eklenmiş görüntüler rapor dosyası boyutunu artırabilir ve rapor oluşturma süresinin uzamasına neden olabilir. Eklenmiş görüntüler ayrıca çok sayıda rapor görüntüsünü güncelleştirmeniz gerektiğinde (örneğin şirketinizin logosu değiştiğinde) bakım konusunda sıkıntı yaşamanıza neden olabilir.
- **Web sunucusu depolama alanı kullanın**: Görüntülerin web sunucusunda depolanması iyi bir seçenektir. Bu seçenek özellikle şirket web sitesinde bulunan şirket logosunu almak için kullanılabilir. Ancak rapor kullanıcılarınızın raporlara ağınızın dışından erişmesi gerekiyorsa dikkatli olmanız gerekir. Bu durumda görüntülere internet üzerinden erişim sağlanabildiğinden emin olun.

    Verilerinizle ilgili görüntülerin (satış temsilcilerinizin resimleri gibi) adlarını, rapor ifadesinin görüntü URL'sinin yolunu dinamik olarak oluşturmasını sağlayacak şekilde belirleyin. Örneğin satış temsilcilerinin resimlerini adlandırmak için her birinin personel numarasını kullanabilirsiniz. Rapor veri kümesinin çalışan numarasını alması durumunda tam görüntü URL'si yolunu oluşturacak bir ifade yazabilirsiniz.
- **Veritabanı depolama alanını kullanın**: İlişkisel bir veritabanı görüntü verilerini depoladığında görüntü verilerini doğrudan veritabanı tablolarından almak (özellikle veriler çok büyük değilse) mantıklı olacaktır.
- **Uygun arka plan görüntüleri**: Arka plan görüntüleri kullanmaya karar verirseniz rapor verilerini inceleyen rapor kullanıcısının dikkatini dağıtmamaya özen göstermeniz gerekir. 

    Ayrıca _filigran stilindeki görüntüleri_ kullandığınızdan emin olun. Filigran stilindeki görüntüler genellikle saydam arka plana (veya rapor tarafından kullanılan arka plan rengine) sahiptir. Ayrıca bu görüntülerde soluk renkler kullanılır. Filigran stilindeki görüntülere örnek olarak şirket logosu veya "Taslak" ya da "Gizli" gibi duyarlılık etiketleri verilebilir.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](../paginated-reports-report-builder-power-bi.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)