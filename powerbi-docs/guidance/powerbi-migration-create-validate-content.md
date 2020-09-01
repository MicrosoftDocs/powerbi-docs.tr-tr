---
title: Power BI’a geçiş yapmak için içerik oluşturma
description: Power BI’a geçiş yaparken içerik oluşturmaya ve doğrulamaya yönelik kılavuz.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: a12a320b061967e9201e3513e504277a9df586b4
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803634"
---
# <a name="createcontenttomigratetopowerbi"></a>Power BI’a geçiş yapmak için içerik oluşturma

Bu makalede, Power BI’a geçiş yaparken içerik oluşturmayı ve bunu doğrulamayı ele alan **4. aşamaya** ilişkin bilgiler sunulur.

:::image type="content" source="media/powerbi-migration-create-validate-content/migrate-to-powerbi-stage-4.png" alt-text="Power BI geçişinin aşamalarını gösteren görüntü. Bu makalede 4. aşama vurgulanır.":::

> [!NOTE]
> Yukarıdaki grafiğin kapsamlı açıklaması için bkz. [Power BI geçişine genel bakış](powerbi-migration-overview.md).

4\. aşamada, kavram kanıtının (POC) üretime hazır bir çözüme dönüştürülmesine ilişkin çalışmaların yapılmasına odaklanılır.

Bu aşamada, çıkış olarak bir geliştirme çalışma alanında doğrulanmış ve üretime dağıtılmaya hazır bir Power BI çözümü elde edilir.

> [!TIP]
> Bu makalede ele alınan konuların çoğu standart Power BI uygulama projeleri için de geçerlidir.

## <a name="create-the-production-solution"></a>Üretim çözümünü oluşturma

Bu noktada, POC’yi gerçekleştiren kişi üretime hazır Power BI çözümünü üretmeye devam edebilir. Ya da, işlemi farklı bir kişi gerçekleştirebilir. Zaman çizelgeleri tehlikeye atılmayacaksa, gelecekte Power BI geliştirmeden sorumlu olacak kişilerin sürece dahil edilmesi iyi sonuçlar verir. Böylece, bu kişiler etkin olarak bilgi edinebilir.

> [!IMPORTANT]
> POC gerçekleştirilen çalışmaları uygun oldukça kullanın.

### <a name="develop-new-import-dataset"></a>Yeni içeri aktarma veri kümesini geliştirme

İhtiyaçlarınızı karşılayacak bir Power BI veri kümesi bulunmuyorsa veya mevcut veri kümesi ihtiyaçlarınızı karşılayacak şekilde geliştirilemiyorsa, yeni bir içeri aktarma veri kümesi oluşturabilirsiniz.

İşlemin en başında verilere ve raporlara yönelik geliştirme işlerinin ayrılması ideal bir çözümdür. [Verileri ve raporları](report-separate-from-model.md) ayırma işlemi, veri modellemesi ve raporların farklı kişilerin sorumluluğunda olduğu durumlarda işlerin ve izinlerin ayrılmasını kolaylaştırır. Daha ölçeklenebilir bir yaklaşım sunar ve verileri yeniden kullanmaya teşvik eder.

Bir içeri aktarma veri kümesinin geliştirilmesiyle ilgili temel etkinlikler şunlardır:

- Bir veya daha fazla veri kaynağından (bir Power BI veri akışı gibi) [veri alma](../connect-data/desktop-quickstart-connect-to-data.md).
- Verileri [şekillendirme, birleştirme ve hazırlama](../connect-data/desktop-shape-and-combine-data.md).
- [Tarih tabloları](../transform-model/desktop-date-tables.md) da dahil olmak üzere [veri kümesi modelini](../transform-model/desktop-modeling-view.md) oluşturma.
- [Model ilişkilerini](../transform-model/desktop-create-and-manage-relationships.md) oluşturma ve doğrulama.
- [Ölçüleri](../transform-model/desktop-measures.md) tanımlama.
- Gerekirse [satır düzeyinde güvenlik](../admin/service-admin-rls.md) ayarlama.
- Eş anlamlıları yapılandırma ve [Soru-Cevap’ı iyileştirme](../natural-language/q-and-a-best-practices.md).
- [Kompozit model](../transform-model/desktop-composite-models.md) veya [toplamalar](../transform-model/desktop-aggregations.md) kullanma gibi veri depolama modlarına ilişkin kararları etkileyen ölçeklenebilirlik, performans ve eşzamanlılık için planlama yapın.

> [!TIP]
> Geliştirme/test/üretim ortamlarınız farklıysa, veri kaynaklarınızı [parametrelendirebilirsiniz](/power-query/power-query-query-parameters). Bu, [5. aşamada](powerbi-migration-deploy-support-monitor.md) açıklanan dağıtım işlemini önemli ölçüde kolaylaştırır.

### <a name="develop-new-reports-and-dashboards"></a>Yeni rapor ve pano geliştirme

Bir Power BI raporu veya panosu geliştirmeye ilişkin temel etkinlik şunlardır:

- Mevcut bir veri modeliyle kurulan Canlı Bağlantı’yı kullanma veya yeni bir veri modeli oluşturma
- Yeni bir veri modeli oluştururken, model tablolarına yönelik [veri depolama modunu](../transform-model/desktop-storage-mode.md) (İçeri Aktarma, DirectQuery veya Bileşik) belirleyin.
- Gereksinimlerin karşılanması açısından en uygun olan veri görselleştirme aracını belirleyin: Power BI Desktop, Paginated Report Builder veya Excel.
- Raporun iletmesi gereken mesajı iletmek ve raporun yanıtlaması gereken soruları gidermek için [en iyi görselleri](../consumer/end-user-visual-type.md) belirleyin.
- Tüm görsellerde net, kısa ve iş açısından uygun terminolojinin kullanıldığından emin olun.
- Etkileşim gereksinimlerini değerlendirin.
- Canlı Bağlantı kullanırken [raport düzeyinde ölçüleri](../transform-model/desktop-tutorial-create-measures.md) ekleyin.
- Özellikle tüketicilerin önemli ölçümleri izlemek istediği durumlar için Power BI hizmetinde bir [pano](../create-reports/service-dashboards.md) oluşturun.

> [!NOTE]
> Bu kararların çoğu, planlamanın ilk aşamalarında veya teknik POC’de alınır.

## <a name="validate-the-solution"></a>Çözümü doğrulama

Bir Power BI çözümünün doğrulanmasıyla ilişkili dört ana yön bulunur:

1. Veri doğruluğu
2. Güvenlik
3. İşlev
4. Performans

### <a name="validate-data-accuracy"></a>Veri doğruluğunu doğrulama

Geçiş esnasında tek seferlik bir çalışma gerçekleştirerek yeni rapordaki verilerin eski raporda görüntülenenlerle eşleştiğini doğrulamanız gerekir. Ya da, verilerde bir farklılık varsa bunun nedenini açıklayabilmeniz gerekir. Eski çözümde bulunan hataların yeni çözümde giderilmesi sık yaşanan bir durumdur.

Devam eden veri doğrulama çalışmaları kapsamında, yeni raporun genelde özgün kaynak sistem ile karşılıklı olarak denetlenmesi gerekir. Genelde, bu doğrulama her rapor değişikliği yayımlandığında tekrarlanabilir şekilde gerçekleşir.

### <a name="validate-security"></a>Güvenliği doğrulama

Güvenlik doğrulanırken, şu iki noktanın dikkate alınması gerekir:

- Veri izinleri
- Veri kümelerine, raporlara ve panolara erişim

İçeri aktarma veri kümelerinde veri izinleri [satır düzeyinde güvenlik](../admin/service-admin-rls.md) (RLS) tanımlanarak uygulanır. DirectQuery depolama modu kullanıldığında veri izinlerinin kaynak sistem tarafından uygulanması mümkündür ([çoklu oturum açma](../connect-data/service-gateway-sso-overview.md) ile gerçekleştirilebilir).

Power BI içeriğine erişim izni vermenin ana yolları şunlardır:

- [Çalışma alanı rolleri](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces) (içerik düzenleyicileri ve görüntüleyicileri için).
- Paketlenmiş bir çalışma alanı içeriği kümesine uygulanan [uygulama izinleri](../collaborate-share/service-create-distribute-apps.md#publish-your-app) (görüntüleyiciler için).
- Bir raporu veya panoyu [paylaşma](../collaborate-share/service-share-dashboards.md) (görüntüleyiciler için).

> [!TIP]
> İçerik yazarlarına etkili güvenlik yönetimine ilişkin eğitim sunmanızı öneririz. Güçlü test, denetim ve izleme özelliklerinin bulunması da önemlidir.

### <a name="validate-functionality"></a>İşlev doğrulama

Bu aşamada, alan adları, biçimlendirme, sıralama ve varsayılan özetleme davranışı gibi veri kümesi ayrıntıları yeniden denetlenir. [Dilimleyiciler](../visuals/power-bi-visualization-slicers.md), [detaya gitme](../consumer/end-user-drill.md), [detaylandırma](../create-reports/desktop-drillthrough.md), [ifadeler](../create-reports/desktop-conditional-format-visual-titles.md), [düğmeler](../create-reports/desktop-buttons.md) veya [yer işaretleri](../create-reports/desktop-bookmarks.md) gibi etkileşimli rapor özelliklerinin de doğrulanması gerekir.

Geliştirme işlemi sırasında, Power BI çözümünün Power BI hizmetinde bulunan bir geliştirme çalışma alanında düzenli olarak yayımlanması gerekir. Özel görsellerin işlenmesi gibi tüm işlevlerin hizmette beklenen şekilde çalıştığını doğrulayın. Şimdi daha fazla test yapacağız. [Zamanlanmış yenilemeyi](../connect-data/refresh-scheduled-refresh.md), [Soru-Cevap](../consumer/end-user-q-and-a.md)’ı ve raporların ve panoların bir [mobil cihazda](../consumer/mobile/mobile-apps-for-mobile-devices.md) nasıl göründüğünü test edin.

### <a name="validate-performance"></a>Performansı doğrulama

Power BI çözümünün performansı kullanıcı deneyimi açısından önemlidir. Çoğu raporun görselleri 10 saniyeden daha kısa sürede sunması gerekir. Raporlarınız daha uzun sürede yükleniyorsa, gecikmelere nelerin neden olduğunu inceleyin. Rapor performansının Power BI Desktop’ın yanı sıra Power BI hizmetinde de düzenli olarak değerlendirilmesi gerekir.

Çoğu performans sorunu [DAX’in (Veri Analizi İfadeleri)](../transform-model/desktop-quickstart-learn-dax-basics.md) yetersiz düzeyde olmasından, veri kümesi tasarımının kötü olmasından veya rapor tasarımının yetersiz olmasından kaynaklanır (örneğin, bir sayfada çok fazla sayıda görselin işlenmesi). Ağ, veri ağ geçidinin aşırı yüklenmesi veya Premium kapasiteye ilişkin yapılandırma gibi teknik ortam sorunları da performans sorunlarına neden olabilir. Daha fazla bilgi için bkz. [Power BI için iyileştirme kılavuzu](power-bi-optimization.md) ve [Power BI’da rapor performansı sorunlarını giderme](report-performance-troubleshoot.md).

## <a name="document-the-solution"></a>Çözümü belgeleme

Power BI çözümleri için faydalı olan iki ana belge türü bulunur:

- Veri kümesi belgeleri
- Rapor belgeleri

Belgeler, hedef kitlenin en kolay erişebileceği konumlarda depolanabilir. Yaygın olarak kullanılan seçenekler şunlardır:

- **Bir SharePoint sitesinde:** Mükemmeliyet Merkeziniz veya şirket içindeki bir Power BI topluluğu sitesi için bir SharePoint sitesi bulunabilir.
- **Bir uygulamada:** Tüketiciyi daha fazla bilgiye yönlendirmek için bir Power BI uygulaması yayımlanırken URL’ler yapılandırılabilir.
- **Ayrı Power BI Desktop dosyalarında:** Tablo ve sütunlar gibi model öğeleri bir açıklamayı tanımlayabilir. Rapor yazarken bu açıklamalar araç ipucu olarak **Alanlar** bölmesinde görüntülenir.

> [!TIP]
> Power BI ile ilişkili belgelere yönelik merkez olarak kullanılacak bir site oluşturursanız, [Yardım Alın menüsünü bunun URL konumuyla özelleştirmeyi](../admin/service-admin-portal.md#publish-get-help-information) düşünebilirsiniz.

### <a name="create-dataset-documentation"></a>Veri kümesi belgeleri oluşturma

Veri kümesi belgeleri, gelecekte veri kümesini yönetecek olan kullanıcılara yöneliktir. Şunların eklenmesi faydalı olur:

- Alınan tasarıma ilişkin kararlar ve sebepleri.
- Veri kümelerinin sahibi ve bunu koruyan ve belgelendiren kişiler.
- Veri yenileme gereksinimleri.
- Veri kümelerinde tanımlanan özel iş kuralları.
- Belirli veri kümesi güvenliği veya veri gizliliği gereksinimleri.
- Geleceğe yönelik bakım ihtiyaçları.
- Bilinen açık sorunlar veya ertelenmiş kapsam öğeleri.

Veri kümesinde zamanla oluşan en önemli değişiklikleri özetleyen bir değişiklik günlüğü de oluşturabilirsiniz.

### <a name="create-report-documentation"></a>Rapor belgeleri oluşturma

Genelde rapor tüketicilerine yönelik bir adım adım yönerge olarak yapılandırılan rapor belgeleri, tüketicilerin rapor ve panolarınızdan daha fazla değer elde etmesine yardımcı olabilir. Kısa bir öğretici video genelde iyi sonuç verir.

Raporunuzun gizli bir sayfasına ek rapor belgeleri ekleyebilirsiniz. Bu, tasarıma ilişkin kararları ve bir değişiklik günlüğünü içerebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Bu Power BI geçişi serisinin sonraki makalesi](powerbi-migration-deploy-support-monitor.md), Power BI’a geçiş yaparken içerik dağıtmayı, bunu desteklemeyi ve izlemeyi ele alan 5. aşamaya ilişkin bilgileri içerir.

Diğer faydalı kaynakları da inceleyebilirsiniz:

- [Microsoft’un BI dönüşümü](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [Power BI kuruluş dağıtımı planlama teknik incelemesi](https://aka.ms/PBIEnterpriseDeploymentWP)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)

Deneyimli Power BI iş ortakları, kuruluşunuzun başarıyla geçiş yapmasına yardımcı olabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.
