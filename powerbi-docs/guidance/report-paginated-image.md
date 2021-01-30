---
title: Sayfalandırılmış raporlar için görüntü kullanım kılavuzu
description: Power BI sayfalandırılmış raporlarında görüntü kullanma hakkında kılavuz.
author: peter-myers
ms.author: kfollis
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 02/16/2020
ms.openlocfilehash: f83894561f8592d5e679a08773459f14a9d6fa1c
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99087764"
---
# <a name="image-use-guidance-for-paginated-reports"></a>Sayfalandırılmış raporlar için görüntü kullanım kılavuzu

Bu makale Power BI [sayfalandırılmış raporları](../paginated-reports/paginated-reports-report-builder-power-bi.md) tasarlayan rapor yazarlarına yöneliktir. Görüntülerle çalışırken öneriler sunar. Rapor düzenlerindeki görüntüler genellikle şirket logosu veya resimler gibi grafik öğeleri görüntüleyebilir.

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

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](../paginated-reports/paginated-reports-report-builder-power-bi.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
