---
title: Power BI’a geçiş yapmak için gereksinimleri toplama
description: Power BI’a geçiş yaparken gereksinimlerin toplanması ve önceliklendirilmesine yönelik rehberlik.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: 60a22946ccde642987e748904d0dc7fe636ec700
ms.sourcegitcommit: ffc46032d0771227395cc38be9ec9ff1500eac70
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2020
ms.locfileid: "89401991"
---
# <a name="gather-requirements-to-migrate-to-power-bi"></a>Power BI’a geçiş yapmak için gereksinimleri toplama

Bu makalede, Power BI’a geçiş yaparken içerik oluşturmayı ve bunu doğrulamayı ele alan **1. aşamaya** ilişkin bilgiler sunulur.

:::image type="content" source="media/powerbi-migration-requirements/migrate-to-powerbi-stage-1.png" alt-text="Bir Power BI geçişinin aşamalarını gösteren görüntü. Bu makalede 1. aşama vurgulanır.":::

> [!NOTE]
> Yukarıdaki grafiğin kapsamlı açıklaması için bkz. [Power BI geçişine genel bakış](powerbi-migration-overview.md).

1\. aşamada, Power BI’a geçirilecek ayrı bir çözüm için bilgi toplamaya ve planlama yapmaya odaklanılır.

1\. aşamanın ardından, önceliklendirilmiş ayrıntılı gereksinimler çıkış olarak elde edilir. Ancak, çalışma düzeyinin tam olarak tahmin edilebilmesi için 2. ve 3. aşamadaki ek etkinliklerin tamamlanması gerekir.

> [!IMPORTANT]
> 1-5. aşamalar belirli bir çözüme ilişkin etkinlikleri temsil eder. Bu aşamada, kuruluş/kiracı düzeyinde alınan kararlar ve yapılan etkinlikler işlemi çözüm düzeyinde etkiler. [Power BI geçişine genel bakış](powerbi-migration-overview.md) makalesinde, bu üst düzey planlama etkinliklerinin bazılarına ilişkin bilgiler sunulur. Uygun olduğunda, verimlilik ve tutarlılık elde etmek için kuruluş düzeyindeki kararları uygulayın.

> [!TIP]
> Bu makalede ele alınan konuların çoğu standart Power BI uygulama projeleri için de geçerlidir.

## <a name="compile-requirements"></a>Derleme gereksinimleri

[Geçiş öncesi adımlarında](powerbi-migration-pre-migration-steps.md) derlenen mevcut iş zekası yapıtları envanteri, Power BI’da oluşturulacak yeni çözüme ilişkin gereksinimler için giriş olarak kullanılır. Gereksinim toplama işlemi, mevcut durumu ve raporlar Power BI’da yeniden tasarlanırken kullanıcıların hangi öğelerin değiştirilmesini veya yeniden düzenlenmesini istediğini anlamayı kapsar. [2. aşamadaki](powerbi-migration-planning.md) çözüm dağıtımı planlamasında, [3. aşamadaki](powerbi-migration-proof-of-concept.md) kavram kanıtı oluşturma işleminde ve [4. aşama](powerbi-migration-create-validate-content.md) kapsamındaki üretime hazır çözümü üretirken ayrıntılı gereksinimlerden faydalanılabilir.

### <a name="gather-report-requirements"></a>Rapor gereksinimlerini toplama

Raporlara yönelik eksiksiz ve başvurması kolay bilgiler derleyin:

- **Amaç, hedef kitle ve beklenen eylem:** Her rapor için geçerli olan amacı, iş sürecini, hedef kitleyi, analiz iş akışını ve rapor tüketicilerinin gerçekleştirmesini beklediğiniz eylemi belirleyin.
- **Tüketicilerin raporu kullanma şekli:** Mevcut raporun tüketicileriyle görüşerek bu raporun nasıl kullanıldığına ilişkin bilgi edinin. Yeni Power BI sürümünde raporun belirli öğelerinin kaldırılabileceğini veya geliştirilebileceğini öğrenebilirsiniz. Bu işlem zaman alsa da kritik raporlar veya sık kullanılan raporlar için bunu gerçekleştirmeniz önemlidir.
- **Sahip ve konu uzmanı:** Raporun sahibini ve rapor veya veri etki alanıyla ilişkili tüm konu uzmanlarını belirleyin. Bu kişiler, gelecekte Power BI raporunun sahibi olarak belirlenebilir. Tüm belirli değişiklik yönetimi gereksinimlerini (BT tarafından yönetilen ve iş tarafından yönetilen çözümlerin gereksinimleri genelde farklıdır) ve onayları ekleyin. İlerleyen zamanlarda değişiklik yapıldığında bunlara ihtiyaç duyulur.
- **İçerik teslimat yöntemi:** Rapor tüketicisinin içerik teslimatına yönelik beklentilerini netleştirin. İçeriğin isteğe bağlı şekilde, etkileşimli yürütmeyle, özel uygulama içine eklenmiş olarak veya e-posta aboneliği aracılığıyla zamanlamalı olarak teslim edilmesi istenebilir. Uyarı bildirimlerinin tetiklenmesine ilişkin gereksinimler de olabilir.
- **Etkileşim ihtiyaçları:** Filtreler, detaya gitme veya detaylandırma gibi _gerçekten gerekli olan_ ve _fayda sağlayan_ etkileşim gereksinimlerini belirleyin.
- **Veri kaynakları:** Rapor için gereken tüm veri kaynaklarının keşfedildiğinden ve veri gecikme süresine (veri güncelliği) yönelik ihtiyaçların anlaşıldığından emin olun. Geçmiş verilerin, eğilimlerin ve veri anlık görüntüsü gereksinimlerinin veri gereksinimleriyle uyumlu hale getirilmesi için bunları tanımlayın. Kaynak veriler kullanılarak yeni rapora ilişkin veri doğrulaması gerçekleştirilirken veri kaynağı belgelerinden faydalanılabilir.
- **Güvenlik gereksinimleri:** Normal kurumsal güvenliğe yönelik tüm özel durumlar da dahil olmak üzere, izin verilen görüntüleyiciler, izin verilen düzenleyiciler ve satır düzeyi güvenliğe ilişkin tüm ihtiyaçlar gibi tüm güvenlik gereksinimlerini belirleyin. Veri duyarlılığı düzeyine, veri gizliliğine ve mevzuata/uyumluluğa ilişkin tüm ihtiyaçları belgeleyin.
- **Ölçümler, KPI’lar ve iş kuralları:** Mevcut raporda tanımlanan tüm hesaplamaların, KPI’ların ve iş kurallarının veri gereksinimleriyle uyumlu hale getirilmesi için bunları tanımlayıp belgeleyin.
- **Kullanılabilirlik, düzen ve görünüm gereksinimleri:** Veri görselleştirmelerine, gruplandırma ve sıralama gereksinimlerine ve koşullu görünürlüğe ilişkin tüm belirli kullanılabilirlik, düzen ve görünüm gereksinimlerini belirleyin. Mobil cihazlara yönelik teslimat ile ilgili tüm konuları buna dahil edin.
- **Yazdırma ve dışarı aktarmaya ilişkin ihtiyaçlar:** Yazdırma, dışarı aktarma veya mükemmel piksel düzen ile ilgili gereksinimlerin olup olmadığını belirleyin. Bu ihtiyaçlar, en uygun rapor türünün (Power BI, Excel veya sayfalandırılmış rapor gibi) belirlenmesine yardımcı olur. Rapor tüketicilerinin nasıl çalıştıklarına önem verdiğini unutmayın ve onların düşünme tarzlarını değiştirmeye çalışmaktan çekinmeyin. _Değişiklikler_ yerine _geliştirmelere_ ilişkin bilgiler sunun.
- **Riskler veya sorunlar:** Raporlar için diğer teknik veya işlevsel gereksinimlerin olup olmadığını ve bunlarda sunulan bilgilerin herhangi bir risk oluşturup oluşturmadığını belirleyin.
- **Açık sorunlar ve kapsam öğeleri:** İleride gerçekleştirilecek bakım işlemlerini, bilinen sorunları veya ertelenmiş istekleri bu aşamada kapsama ekleyin.

> [!TIP]
> Gereksinimleri _gerekli_ ve _faydalı_ sınıflandırarak bunları derecelendirin. Tüketiciler, yalnızca sürecin başında istekte bulunabildiklerini düşündüklerinden, gereken her şeyin onlara en başında sunulmasını ister. Öncelikleri birden fazla yinelemeyle işlerken kapsamı paydaşlara sunun. Bu, iletişim, karar alma ve bekleyen taahhütlerin izlenmesi gibi süreçlere yardımcı olur.

### <a name="gather-data-requirements"></a>Veri gereksinimleri toplama

Verilerle ilgili şu ayrıntılı bilgileri derleyin:

- **Mevcut sorgular:** Bir [DirectQuery modeli](../connect-data/desktop-use-directquery.md) veya [Bileşik model](../transform-model/desktop-composite-models.md) tarafından kullanılabilecek ya da bir İçeri aktarma modeline dönüştürülebilecek mevcut rapor sorgularının ve saklı yordamların olup olmadığını belirleyin.
- **Veri kaynağı türleri:** Merkezi hale getirilmiş veri kaynakları (kurumsal veri ambarı gibi) ve standartlaştırılmamış veri kaynakları (düz dosyalar veya veri kaynaklarını raporlama için geliştiren Excel dosyaları gibi) da dahil olmak üzere gerekli olan veri kaynağı türlerini derleyin. [Veri ağ geçidi](../connect-data/service-gateway-onprem.md) bağlantısı için veri kaynaklarının konumunun bulunması da önemlidir.
- **Veri yapısı ve temizlemeye yönelik ihtiyaçlar:** Her önkoşul veri kaynağına yönelik veri yapısını ve [veri temizleme](../transform-model/desktop-query-overview.md) etkinliklerinin ne ölçüde gerekli olduğunu belirleyin.
- **Veri tümleştirmesi**: Birden fazla veri kaynağı olduğunda veri tümleştirmesinin nasıl işleneceğini ve [ilişkilerin](../transform-model/desktop-create-and-manage-relationships.md) her model tablosu arasında nasıl tanımlandığını değerlendirin. Modelin basitleştirilmesi ve [boyutunun azaltılması](import-modeling-data-reduction.md) için gereken belirli veri öğelerini tanımlayın.
- **Kabul edilebilir veri gecikmesi:** Her veri kaynağına yönelik veri gecikme süresi ihtiyaçlarını belirleyin. Bu, hangi [veri depolama modunun](../transform-model/desktop-storage-mode.md) kullanılacağına ilişkin kararları etkiler. İçeri aktarma model tabloları için veri yenileme sıklığının da bilinmesi önemlidir.
- **Veri hacmi ve ölçeklenebilirlik:** [Büyük model desteği](../admin/service-premium-large-models.md) ve DirectQuery modellerinin veya [Bileşik modellerin](../transform-model/desktop-composite-models.md) tasarlanmasına ilişkin kararlarda göz önünde bulundurulan veri hacmi beklentilerini değerlendirin. Geçmiş verilere ilişkin önemli noktaların da bilinmesi önemlidir. Büyük veri kümeleri için [artımlı veri yenilemesi](../admin/service-premium-incremental-refresh.md) kurallarının belirlenmesi de önemlidir.
- **Ölçümler, KPI’lar ve iş kuralları:** Ölçümlere, KPI’lara ve iş kurallarına yönelik ihtiyacı değerlendirin. Bunlar, mantığın nereye (veri kümesine veya veri tümleştirme işlemine) uygulanacağı konusunda verilen kararları etkiler.
- **Ana veri ve veri kataloğu:** İlgilenilmesi gereken ana veri sorunlarının olup olmadığını değerlendirin. Kurumsal bir veri kataloğuyla tümleştirme yapmanın bulunabilirliği geliştirme, tanımlara erişme veya kuruluş tarafından kabul gören tutarlı bir terminoloji oluşturma açısından uygun olup olmadığını belirleyin.
- **Güvenlik ve veri gizliliği:** [Satır düzeyi güvenlik](../admin/service-admin-rls.md) gereksinimleri de dahil olmak üzere veri kümelerine yönelik belirli güvenlik veya veri gizliliği hususlarının olup olmadığını belirleyin.
- **Açık sorunlar ve kapsam öğeleri:** Bilinen sorunları, bilinen veri kalitesi kusurlarını, ileride gerçekleştirilecek bakım işlemlerini, veya ertelenmiş istekleri bu aşamada kapsama ekleyin.

> [!IMPORTANT]
> [Paylaşılan veri kümeleriyle](../connect-data/service-datasets-share.md) veri yeniden kullanılabilirliği elde edilebilir. Güvenilirliği göstermek ve bulunabilirliği geliştirmek için bunu isteğe bağlı olarak [sertifikalı](../connect-data/service-datasets-certify.md) yapabilirsiniz. Birden fazla veri kümesindeki yinelenen mantığın azaltılması için [veri akışlarıyla](../transform-model/service-dataflows-overview.md) veri hazırlama yeniden kullanılabilirliği elde edebilirsiniz. Veri akışları, veriler daha az sıklıkta alındığı için kaynak sistemlerin yükünü de önemli ölçüde azaltır. Böylece, birden fazla veri kümesi verileri veri akışından içeri aktarabilir.

## <a name="identify-improvement-opportunities"></a>Geliştirme fırsatlarını tanımlama

Çoğu durumda, bazı değişiklikler ve iyileştirmeler yapılır. Bire bir geçiş genelde yeniden düzenleme veya geliştirme işlemlerinin yapılmasını gerektirir. Şu üç türde geliştirmeyi yapmayı düşünebilirsiniz:

- **Raporların birleştirilmesi:** Filtreler, yer işaretleri veya kişiselleştirme gibi teknikler kullanılarak benzer raporlar birleştirilebilir. Daha esnek olan daha az sayıda raporun olması, rapor tüketicilerinin deneyimini önemli ölçüde geliştirebilir. Rapor tüketicilerine daha fazla esneklik sunmak ve kendi görselleştirmelerini oluşturmalarına imkan tanımak için [Soru-Cevap (doğal dil sorgulama)](../natural-language/q-and-a-best-practices.md) özelliğine yönelik veri kümelerini iyileştirmeyi düşünebilirsiniz.
- **Verimlilik geliştirmeleri:** Gereksinimler toplanırken geliştirmeler tanımlanabilir. Örneğin, analistler sayıları el ile derlerken veya bir iş akışı kolaylaştırılabildiğinde. [Power Query](../transform-model/desktop-query-overview.md) el ile gerçekleştirilen mevcut etkinliklerin değiştirilmesinde önemli bir rol oynayabilir. İş analistleri, verilerin düzenli olarak temizlenmesi ve hazırlanması için sürekli olarak aynı etkinlikleri gerçekleştiriyorsa, Power Query veri hazırlama adımlarıyla önemli ölçüde zaman tasarrufu elde edilebilir ve hatalar azaltılabilir.
- **Veri modelinin merkezi hale getirilmesi:** Yetkili ve onaylı veri kümeleri, yönetilen self servis iş zekasının temelini oluşturur. Bu durumlarda, veriler bir kez yönetilir ve analistlere bu verileri kullanarak raporlama ve analize yönelik ihtiyaçları karşılama esnekliği sunulur.

> [!NOTE]
> Veri modellerinin merkezi hale getirilmesi hakkında daha fazla bilgi edinmek için bkz. [çekirdekte disiplin](center-of-excellence-microsoft-business-intelligence-transformation.md#discipline-at-the-core) ve [uç birimde esneklik](center-of-excellence-microsoft-business-intelligence-transformation.md#flexibility-at-the-edge).

## <a name="prioritize-and-assess-complexity"></a>Karmaşıklığa öncelik verme ve bunu değerlendirme

Bu noktada, özel gereksinimleri olabilen ilk envanter kullanılabilir. İlk iş zekası yapıtı kümesinin önceliği geçişe hazır olarak belirlenirken, raporların ve verilerin de hem toplu hem de ayrı şekilde değerlendirilmesi gerekir.

Aşağıda belirtilenler gibi yüksek öncelikli raporları belirleme:

- İşletmeye önemli değer katan raporlar.
- Sık yürütülen raporlar.
- Üst düzey yöneticilerin ihtiyaç duyduğu raporlar.
- Karmaşıklığı makul düzeyde olan raporlar (ilk geçiş yinelemelerinde başarı şansının artırılması için).

Aşağıda belirtilenler gibi yüksek öncelikli verileri tanımlayın:

- Kritik veri öğelerini içeren veriler.
- Birçok kullanım örneği tarafından kullanılan ortak kurumsal veriler.
- Raporlarda ve birçok rapor yazarı tarafından yeniden kullanılmak üzere yeni bir veri kümesi oluşturmak için kullanılabilecek veriler.
- Karmaşıklığı makul düzeyde olan veriler (ilk geçiş yinelemelerinde başarı şansının artırılması için).

## <a name="next-steps"></a>Sonraki adımlar

[Bu Power BI geçişi serisinin sonraki makalesinde](powerbi-migration-planning.md), tek bir Power çözümü için geçişin planlanmasını ele alan 2. aşamaya ilişkin bilgiler sunulur.

Diğer faydalı kaynakları da inceleyebilirsiniz:

- [Microsoft’un BI dönüşümü](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [Power BI kuruluş dağıtımı planlama teknik incelemesi](https://aka.ms/PBIEnterpriseDeploymentWP)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)

Deneyimli Power BI iş ortakları, kuruluşunuzun başarıyla geçiş yapmasına yardımcı olabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.
