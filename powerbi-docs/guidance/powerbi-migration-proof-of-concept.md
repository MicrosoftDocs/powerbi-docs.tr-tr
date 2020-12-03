---
title: Power BI’a geçiş yapmak için kavram kanıtı yönetme
description: Power BI’a geçiş yaparken kavram kanıtının yönetilmesine yönelik kılavuz.
author: peter-myers
ms.author: v-pemyer
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 08/20/2020
ms.openlocfilehash: 77174da7fd47470974a292ba98f6b50c268b04fd
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96419142"
---
# <a name="conduct-proof-of-concept-to-migrate-to-power-bi"></a>Power BI’a geçiş yapmak için kavram kanıtı yönetme

Bu makalede, kavram kanıtı yönetme işlemini içeren **3. aşama** açıklanır. İşlem ile, Power BI geçişi sırasında riskin azaltılması ve bilinmeyenlerin ele alınması gibi süreçlerin olabildiğince erken tamamlama amaçlanır.

:::image type="content" source="media/powerbi-migration-proof-of-concept/migrate-to-powerbi-stage-3.png" alt-text="Power BI geçişinin aşamalarını gösteren görüntü. Bu makalede 3. aşama vurgulanır.":::

> [!NOTE]
> Yukarıdaki grafiğin kapsamlı açıklaması için bkz. [Power BI geçişine genel bakış](powerbi-migration-overview.md).

3\. aşamada, bilinmeyenlerin ele alınmasına ve risklerin olabildiğince erken azaltılmasına odaklanılır. Bir teknik POC, varsayımların doğrulanmasına yardımcı olur. Bu, çözüm dağıtımı planlamasının ([2. aşamada açıklanmıştır](powerbi-migration-planning.md)) yanı sıra yinelemeli olarak yapılabilir.

Bu aşamada, dar kapsamlı olan, ilk açık soruları ele alan ve [4. aşamadaki](powerbi-migration-create-validate-content.md) üretime hazır hale getirme işlemleri için hazır olan bir Power BI çözümü çıkış olarak elde edilir.

> [!IMPORTANT]
> POC’nin tek kullanımlık bir çalışma olması amaçlanmaz. Bunun, üretime hazır çözüme ilişkin bir erken yineleme olmasını beklenir. Kuruluşunuzda, bu etkinliği prototip, pilot, örnek, hızlı başlangıç veya en sade ürün (MVP) olarak adlandırabilirsiniz. POC yönetme işlemi her zaman gerekmez ve işlem resmi olmayan yöntemlerle de gerçekleştirilebilir.

> [!TIP]
> Bu makalede ele alınan konuların çoğu standart Power BI uygulama projeleri için de geçerlidir. Kuruluşunuz Power BI ile daha fazla deneyim kazandıkça, POC yönetme ihtiyacı azalır. Ancak, Power BI’ın hızlı yayınlama temposu ve sürekli olarak sunulan yeni özellikler nedeniyle düzenli olarak öğrenme amaçlı teknik POC’ler yönetebilirsiniz.

## <a name="set-poc-goals-and-scope"></a>POC hedeflerini ve kapsamı ayarlama

POC gerçekleştirirken aşağıdaki hedeflere odaklanın:

- Bir özelliğin çalışma şekline ilişkin varsayımları doğrulayın.
- Power BI’ın ve eski iş zekası platformunun çalışma şekli arasındaki farklara ilişkin bilgi edinin.
- Bazı gereksinimlere ilişkin ilk bilgileri konu uzmanlarıyla doğrulayın.
- Veri yapısı, ilişkiler, veri türleri veya veri değerleriyle ilgili tüm sorunları anlamak ve belirlemek için gerçek verileri içeren küçük bir veri kümesi oluşturun.
- Model hesaplamaları tarafından kullanılan [DAX söz dizimi](/dax/) ifadeleriyle deneme yapın ve bunları doğrulayın.
- (Ağ geçidi olarak kullanılacaksa) Bir ağ geçidi kullanarak veri kaynağı bağlantısını test edin.
- (Ağ geçidi olarak kullanılacaksa) Bir ağ geçidi kullanarak veri yenilemesini test edin.
- Uygun olduğunda, satır düzeyi güvenlik de dahil olmak üzere güvenlik yapılandırmalarını doğrulayın.
- Düzene ve görünüme ilişkin kararlar alıp bunları deneyin.
- Power BI hizmetinin tüm işlevlerinin beklendiği gibi çalıştığını doğrulayın.

POC’nin kapsamı, bilinmeyenlerin ne olduğuna veya iş arkadaşlarınızla hangi hedeflerin doğrulanması gerektiğine bağlıdır. Karmaşıklığı azaltmak için POC’nin kapsamını olabildiğince daraltın.

Genelde, geçişlerde başlangıç niteliğinde bir çözüm mevcut olduğu için gereksinimler iyi bilinir. Ancak, yapılacak geliştirmelerin kapsamına veya mevcut Power BI becerilerine bağlı olarak POC’den değer elde edilebilir. Buna ek olarak, tüketici geri bildirimlerini temel alarak hızla prototip oluşturma (özellikle geliştirme yapıldıysa), gereksinimlerin hızla belirlenmesi açısından uygun olabilir.

> [!IMPORTANT]
> POC’nin yalnızca bir tane veri alt kümesini veya sınırlı görselleri içerdiği durumlarda bile işlemin baştan sona kadar sürdürülmesi önemlidir. Farklı bir deyişle, Power BI Desktop’taki geliştirme aşamasında Power BI hizmetinde bir geliştirme çalışma alanına dağıtma. Bu, POC hedeflerini tam olarak gerçekleştirmenin tek yoludur. Bu, özellikle çoklu oturum açma ile DirectQuery veri kümesine erişme gibi daha önce kullanılmayan kritik işlevlerin Power BI hizmeti tarafından sunulmasını gerektiren durumlarda geçerli olur. POC işlemi sırasında, çalışmalarınızı emin olmadığınız veya diğer kişilerle doğrulanması gereken yönlere odaklanın.

## <a name="handle-differences-in-power-bi"></a>Power BI’da farklılıkları işleme

Power BI, _model tabanlı araç_ veya _rapor tabanlı araç_ olarak kullanılabilir. Model tabanlı çözüm için veri modeli oluşturulur. Rapor tabanlı çözüm, önceden dağıtılmış bir veri modeline bağlanır.

Power BI, sunduğu üstün esneklik ile geçiş öncesinde kullanılan eski iş zekası platformundan temel anlamda farklı olabilir.

### <a name="consider-redesigning-the-data-architecture"></a>Veri mimarisini yeniden tasarlamayı değerlendirme

Kendi anlam katmanı olan eski bir iş zekası platformundan geçiş yapıyorsanız, bir içeri aktarma veri kümesi oluşturma iyi bir seçenek olabilir. Power BI [yıldız şeması](star-schema.md) tablo tasarımıyla en iyi şekilde çalışır. Bu nedenle, eski anlam katmanı yıldız şeması tasarımıyla yapılmadıysa, Power BI’dan tam olarak yararlanmak için bazı tasarım değişiklikleri yapmanız gerekebilir. Yıldız şeması tasarım ilkeleriyle (ilişkiler, yaygın olarak kullanılan ölçüler ve kullanıcı dostu kurumsal terminoloji de dahil olmak üzere) uyumlu olan bir anlam katmanının tanımlanması, self servis rapor yazarları için mükemmel bir başlangıç noktası sunar.

Raporların SQL sorgularını veya depolanmış yordamları kullanarak ilişkisel veri kaynaklarına başvurduğu eski bir iş zekası platformundan geçiş yapıyorsanız ve Power BI’ı [DirectQuery modunda](../connect-data/desktop-use-directquery.md) kullanmayı düşünüyorsanız, neredeyse bire bir veri modeli geçişi elde edebilirsiniz.

> [!CAUTION]
> Tek bir içeri aktarılan tabloyu içeren çok sayıda Power BI Desktop dosyasının oluşturulması, genelde tasarımın uygun olmadığını gösterir. Böyle bir durumla karşılaşırsanız, [yıldız şeması](star-schema.md) tasarımı kullanılarak oluşturulan [paylaşılan veri kümeleriyle](../connect-data/service-datasets-across-workspaces.md) daha iyi sonuçlar elde edilip edilemeyeceğinizi araştırın.

### <a name="decide-how-to-handle-dashboard-conversions"></a>Pano dönüştürmelerinin nasıl işleneceğini belirleme

İş zekası sektöründe, önemli ölçümleri tek bir sayfada gösteren görsel koleksiyonuna pano adı verilir. Ancak, Power BI’da panolar yalnızca Power BI hizmetinde oluşturulabilen belirli bir görselleştirme özelliğini temsil eder. Bir panoyu eski bir iş zekası platformundan geçirirken iki seçeneğiniz bulunur:

1. Eski pano, bir Power BI _raporu_ olarak yeniden oluşturulabilir. Çoğu rapor Power BI Desktop ile oluşturulur. Alternatif seçenek olarak, sayfalandırılmış raporlar ve Excel raporları da kullanılabilir.
2. Eski pano, bir Power BI _panosu_ olarak yeniden oluşturulabilir. [Panolar](../fundamentals/service-basic-concepts.md#dashboards), Power BI hizmetiyle sunulan bir görselleştirme özelliğidir. Pano görselleri genelde bir veya daha fazla rapordan, Soru-Cevap’tan ya da Hızlı İçgörüler özelliğinden elde edilen görsellerin sabitlenmesiyle oluşturulur.

> [!TIP]
> Panolar bir Power BI içeriği türü olduğu için rapor veya pano adında _pano_ sözcüğünü kullanmayın.

### <a name="focus-on-the-big-picture-when-recreating-visuals"></a>Görselleri yeniden oluştururken büyük resme odaklanın

Her iş zekası aracının güçlü yönleri ve odak noktaları bulunur. Bu nedenle, eski bir iş zekası platformunda gerek duyulan rapor görsellerinin yakın eşdeğerleri Power BI’da bulunmayabilir.

Rapor görsellerini yeniden oluştururken, raporun ele aldığı önemli iş sorularına odaklanın. Böylece, her görselin tasarımının tamamen aynı şekilde çoğaltılmasına yönelik ihtiyaç ortadan kaldırılır. Geçirilen raporların tutarlı olması içerik tüketicilerini memnun etse de küçük ayrıntılar üzerinde tartışarak zaman kaybetmemeniz önemlidir.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI geçişi serisinin sonraki makalesinde](powerbi-migration-create-validate-content.md), Power BI’a geçiş yaparken içerik oluşturmayı ve bunu doğrulamayı ele alan 4. aşama hakkında bilgi edineceksiniz.

Diğer faydalı kaynakları da inceleyebilirsiniz:

- [Microsoft’un BI dönüşümü](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [Power BI kuruluş dağıtımı planlama teknik incelemesi](https://aka.ms/PBIEnterpriseDeploymentWP)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)

Deneyimli Power BI iş ortakları, kuruluşunuzun başarıyla geçiş yapmasına yardımcı olabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.
