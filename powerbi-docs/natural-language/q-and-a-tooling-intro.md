---
title: Power BI Soru-Cevap eğitimi için Soru-Cevap araçlarına giriş (önizleme)
description: Power BI Soru-Cevap araçlarına giriş
author: mohaali
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/17/2019
ms.author: mohaali
ms.openlocfilehash: 17d0a68782f34c09286be5ebe020668a15061ee4
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874949"
---
# <a name="intro-to-qa-tooling-to-train-power-bi-qa-preview"></a>Power BI Soru-Cevap eğitimi için Soru-Cevap araçlarına giriş (önizleme)

Power BI Soru-Cevap *araçları* ile kullanıcılarınızın doğal dil deneyimini iyileştirebilirsiniz. Tasarımcı veya yönetici olarak, doğal dil altyapısıyla etkileşime geçerek üç alanda geliştirmeler yaparsınız: 

- Kullanıcılarınızın sorduğu soruları gözden geçirmek.
- Soru-Cevap’a soruları anlamayı öğretmek.
- Soru-Cevap’a öğrettiğiniz terimleri yönetmek.

Bu ayrılmış araç özelliklerine ek olarak Power BI Desktop’taki **Modelleme** sekmesinde daha fazla seçenek sunulur:  

- Eş anlamlılar
- Satır etiketleri
- Soru-Cevap’tan gizle
- Dil şemasını yapılandırma (gelişmiş)

## <a name="get-started-with-qa-tooling"></a>Soru-Cevap araçlarını kullanmaya başlama

Soru-Cevap araçları yalnızca Power BI Desktop’ta kullanılabilir ve şu anda yalnızca içeri aktarma modunu desteklemektedir.

1. Power BI Desktop’ı açın ve Soru-Cevap’ı kullanarak bir görsel oluşturun. 
2. Görselin köşesinden dişli simgesini seçin. 

    ![Soru-Cevap görseli dişli simgesi](media/qna-visual-gear.png)

    Başlarken sayfası açılır.  

    ![Soru-Cevap Kullanmaya başlama](media/qna-tooling-dialog.png)

### <a name="review-questions"></a>Soruları gözden geçirme

Kiracınız için Power BI hizmetinde kullanılmakta olan veri kümelerinin bir listesini görmek için **Soruları inceleyin**’i seçin. **Soruları inceleyin** sayfası ayrıca veri kümesi sahibini, çalışma alanını ve son yenileme tarihini gösterir. Buradan bir veri kümesi seçerek kullanıcıların sorduğu soruları görebilirsiniz. Veriler tanınmayan sözcükleri de gösterir. Burada gösterilen tüm veriler son 28 güne aittir.

![Soru-Cevap sorularını inceleme](media/qna-tooling-review-questions.png)

### <a name="teach-qa"></a>Soru-Cevap’a öğretme

**Soru-Cevap Öğretimi** bölümünü kullanarak Soru-Cevap’ı sözcükleri tanıması için eğitebilirsiniz. Başlamak için, Soru-Cevap’ın tanımadığı bir veya daha fazla sözcüğü içeren bir soru yazın. Soru-Cevap ilgili terimin tanımını sorar. Sözcüğün temsil ettiği anlama karşılık gelen bir filtre veya alan adı girin. Bundan sonra Soru-Cevap özgün soruyu yeniden yorumlar. Sonuçlardan memnunsanız girişinizi kaydedebilirsiniz. Daha fazla bilgi edinmek için bkz. [Soru-Cevap Öğretimi](q-and-a-tooling-teach-q-and-a.md)

![Soru-Cevap öğretimi eşanlamlı önizlemesi](media/qna-tooling-teach-fixpreview.png)

### <a name="manage-terms"></a>Terimleri yönetme

Soru-Cevap Öğretimi bölümünde kaydettiğiniz her şey burada gösterilir, böylece tanımladığınız terimleri inceleyebilir veya silebilirsiniz. Şu anda mevcut bir tanımı düzenlemeniz mümkün değildir; bu yüzden bir terimi tanımlamak için silip yeniden oluşturmanız gerekir.

![Soru-Cevap ile Terimleri yönetme](media/qna-manage-terms.png)

## <a name="other-qa-settings"></a>Diğer Soru-Cevap ayarları

### <a name="bulk-synonyms"></a>Toplu eş anlamlılar

Power BI Desktop **Modelleme** sekmesinde Soru-Cevap deneyimini geliştirmeye yönelik daha fazla seçenek bulunur. 

1. Power BI Desktop'ta Modelleme görünümünü seçin.

2. Bir alan veya tablo seçerek **Özellikler** bölmesini görüntüleyin.  Bu bölme, tuvalin sağ tarafında gösterilir ve birkaç Soru-Cevap eylemini listeler. Seçeneklerden biri **Eş anlamlılar**’dır. **Eş anlamlılar** kutusunda, seçtiğiniz tablo veya alan için hızlıca alternatifler tanımlayabilirsiniz. Ayrıca, Araçlar iletişim kutusunun **Soru-Cevap Öğretimi** bölümünde eş anlamlıları tanımlayabilirsiniz ancak bir tablodaki çok sayıda alan için eş anlamlıları genellikle burada daha hızlı tanımlarsınız.

    ![Soru-Cevap Modelleme bölmesi eş anlamlılar](media/qna-modelling-pane-synonyms.png)

3. Tek bir alana ait birden çok eş anlamlı tanımlamak için, bir sonraki eş anlamlıyı göstermek üzere virgül kullanın.

### <a name="hide-from-qa"></a>Soru-Cevap’tan gizle

Ayrıca alanları ve tabloları Soru-Cevap sonuçlarında görünmeyecek şekilde gizleyebilirsiniz. 

1. Power BI Desktop'ta Modelleme görünümünü seçin.

2. Bir alan veya tablo seçerek **Özellikler** bölmesini görüntüleyin ve **Gizli** seçeneğini **Açık** duruma getirin.

    Soru-Cevap bu ayara uyar ve alanın Soru-Cevap tarafından tanınmamasını sağlar. Örneğin, aynı ada sahip alanların gereksiz yinelenmesini önlemek için Kimlik alanlarını ve yabancı anahtarları gizlemek isteyebilirsiniz. Alanı gizleseniz bile Soru-Cevap dışındaki görsellerde Power BI Desktop ile kullanabilirsiniz.

### <a name="set-a-row-label"></a>Satır etiketi ayarlama

Satır etiketi, bir tablodaki tek bir satırı en iyi tanımlayan sütunu (veya *alanı*) tanımlamanıza olanak tanır. Örneğin, 'Müşteri' adlı bir tablo için satır etiketi genellikle 'Görünen Ad' olur. Bu ekstra meta veriyi sağlamak, kullanıcılar 'Müşteriye göre satışları göster' yazdığında Soru-Cevap’ın daha faydalı bir görsel çizmesine olanak tanır. 'Müşteri'yi tablo olarak işleme almak yerine 'Görünen Ad'ı kullanabilir ve her bir müşterinin satışını gösteren bir çubuk grafik gösterebilir. Satır etiketini yalnızca Modelleme görünümünde ayarlayabilirsiniz. 

1. Power BI Desktop'ta Modelleme görünümünü seçin.

2. Bir tablo seçerek **Özellikler** bölmesini görüntüleyin.

3. **Satır etiketi** kutusunda bir alan seçin.

## <a name="configure-the-linguistic-schema-advanced"></a>Dil şemasını yapılandırma (gelişmiş)

Power BI’da, Soru-Cevap içindeki doğal dil altyapısını, temel alınan doğal dil sonuçlarının puanlamasını ve ağırlıklandırılmasını değiştirmek de dahil olmak üzere tamamen eğitip geliştirebilirsiniz. Nasıl yapılacağını öğrenmek için bkz. [Soru-Cevap dil şemasını düzenleme ve ifade ekleme](q-and-a-tooling-advanced.md).

## <a name="next-steps"></a>Sonraki adımlar

Doğal dil altyapısını iyileştirmeye yönelik birkaç en iyi yöntem vardır. Daha fazla bilgi için aşağıdaki makaleyi inceleyin:

* [Soru-Cevap ile En İyi Yöntemler](q-and-a-best-practices.md)
