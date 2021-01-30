---
title: Power BI’a geçiş yapmak için dağıtımı planlama
description: Power BI’a geçiş yaparken dağıtımı planlanmaya yönelik kılavuz.
author: peter-myers
ms.author: kfollis
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 08/20/2020
ms.openlocfilehash: f6b781d6b3f87587e7734d5f842a013fd6fb5c19
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99086706"
---
# <a name="plan-deployment-to-migrate-to-power-bi"></a>Power BI’a geçiş yapmak için dağıtımı planlama

Bu makalede, bir Power BI çözümüne ilişkin geçiş işleminin planlanmasını ele alan **2. aşama** açıklanmaktadır.

:::image type="content" source="media/powerbi-migration-planning/migrate-to-powerbi-stage-2.png" alt-text="Bir Power BI geçişinin aşamalarını gösteren görüntü. Bu makalede 2. aşama vurgulanır.":::

> [!NOTE]
> Yukarıdaki grafiğin kapsamlı açıklaması için bkz. [Power BI geçişine genel bakış](powerbi-migration-overview.md).

2\. aşamada, Power BI’a geçiş yapmak için 1. aşamada tanımlanan gereksinimleri kullanılmasına odaklanılır.

2\. aşama, dağıtım işlemine kılavuzluk etmesi amaçlanan birçok belirli kararı çıkış olarak vermeyi amaçlar.

Bu tür kararlaştırma süreçleri, yinelemeli ve doğrusal olmayan işlemlerdir. [Geçiş öncesi adımlarında](powerbi-migration-pre-migration-steps.md) zaten bazı planlamalar yapılmıştı. Kavram kanıtından ([3. aşamada](powerbi-migration-proof-of-concept.md) açıklanmıştır) elde edilen bilgiler, dağıtım planlamasıyla paralel olarak gerçekleşebilir. Dağıtıma ilişkin kararları etkileyen ek bilgiler, çözüm oluşturulurken ([4. aşamada](powerbi-migration-create-validate-content.md) açıklanmıştır) bile ortaya çıkabilir.

> [!IMPORTANT]
> 1-5. aşamalar belirli bir çözüme ilişkin etkinlikleri temsil eder. Bu aşamada, kuruluş/kiracı düzeyinde alınan kararlar ve yapılan etkinlikler işlemi çözüm düzeyinde etkiler. [Power BI geçişine genel bakış](powerbi-migration-overview.md) makalesinde, bu üst düzey planlama etkinliklerinin bazılarına ilişkin bilgiler sunulur. Uygun olduğunda, verimlilik ve tutarlılık elde etmek için kuruluş düzeyindeki kararları uygulayın.

> [!TIP]
> Bu makalede ele alınan konular, standart Power BI uygulama projeleri için de geçerlidir.

## <a name="choose-power-bi-product"></a>Power BI ürünü seçme

Power BI ürününün seçilmesi, alınan ilk kararlardan biridir. [Power BI hizmeti](../fundamentals/power-bi-service-overview.md) veya [Power BI Rapor Sunucusu](../report-server/get-started.md) arasında seçim yapılması gerekir. İçerik yayımlandıktan sonra ekleme, mobil teslimat ve e-posta abonelikleri gibi birçok ek seçenek kullanılabilir olur.

Mimariye ilişkin konular hakkında daha fazla bilgi edinmek için [Power BI kuruluş dağıtımı teknik incelemesinin](https://aka.ms/PBIEnterpriseDeploymentWP) **3. bölümüne** bakın.

> [!CAUTION]
> Bir dosya sisteminde depolanan Power BI Desktop dosyalarını kullanmak istiyorsanız, bunun en uygun yaklaşım olmadığını da göz önünde bulundurmanız gerekir. Power BI hizmetini (veya Power BI Rapor Sunucusunu) kullanarak güvenlik, içerik dağıtımı ve işbirliğine ilişkin önemli avantajlar elde edersiniz. Etkinlik denetleme ve izleme özelliği de Power BI hizmeti tarafından sunulur.

## <a name="decide-on-workspace-management-approach"></a>Çalışma alanı yönetimi yaklaşımını belirleme

[Çalışma alanları](../collaborate-share/service-new-workspaces.md) Power BI hizmetine ilişkin temel bir kavram olduğundan, çalışma alanı yönetimi planlama sürecinde önemli bir adımdır. Sorulacak sorular şunlardır:

- Bu yeni çözüm için yeni bir çalışma alanı gerekiyor mu?
- Geliştirme, test etme ve üretim gibi özelliklerin sunulması için ayrı çalışma alanları gerekecek mi?
- Veri ve raporlar için ayrı çalışma alanları mı kullanılacak yoksa tek bir çalışma alanı yeterli olur mu? Ayrı veri kümelerinin kullanılması, özellikle veri kümelerinin güvenli hale getirilmesi açısından birçok avantaj sunar. Bunlar, gerektiğinde raporları paylaşan kullanıcılardan ayrı olarak yönetilebilir.
- Çalışma alanına yönelik güvenlik gereksinimleri nelerdir? [Çalışma alanı rollerinin](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces) planlanmasını etkiler. İçerik tüketicileri bir uygulamayı kullanılacaksa, [uygulamaya yönelik izinler](../collaborate-share/service-create-distribute-apps.md#publish-your-app) çalışma alanından ayrı olarak yönetilir. Uygulama görüntüleyicilerine yönelik farklı izinler ile raporların veya panoların salt okuma tüketicilerine yönelik güvenlik gereksinimleri daha esnek şekilde karşılanır.
- Yeni içeriğin güvenli hale getirilmesi için mevcut gruplar kullanılabilir mi? Hem Azure Active Directory hem de Microsoft 365 grupları desteklenir. Grupların kullanımı mevcut işlemlerle uyumlu hale getirildiğinde, ayrı kullanıcılara atama yönteminden daha kolay bir izin yönetimi elde edilir.
- Dış konuk kullanıcılarla ilişkili güvenlik hususları var mı? [Konuk kullanıcı erişimini](../admin/service-admin-azure-ad-b2b.md) yapılandırmak için Azure Active Directory yöneticiniz ve Power BI yöneticinizle birlikte çalışmanız gerekebilir.

> [!TIP]
> Belirli bir iş etkinliği veya proje için çalışma alanı oluşturabilirsiniz. Çalışma alanlarını, kurumsal yapınızı (her departman için bir çalışma alanı gibi) temel alarak yapılandırarak başlayabilirsiniz. Ancak, bu yaklaşım benimsendiğinde kapsamın çok geniş olması gibi durumlar sık görülür.

## <a name="determine-how-content-will-be-consumed"></a>İçeriğin nasıl kullanılacağını belirleme

Bir çözümün tüketicilerinin rapor ve panolara ilişkin görüntüleme tercihlerini anlamanız faydalı olur. Sorulacak sorular şunlardır:

- İçeriğin tüketicilere sunulması için en uygun yöntem tek bir çalışma alanında bulunan raporları ve panoları içeren bir [Power BI uygulaması](../consumer/end-user-apps.md) mı olur? Ya da, içerik görüntüleyicilerine bir çalışma alanına doğrudan erişim sunulması yeterli olur mu?
- Bazı raporlar ve panolar [Teams](../collaborate-share/service-embed-report-microsoft-teams.md), [SharePoint Online](../collaborate-share/service-embed-report-spo.md) veya [bir güvenli portal ya da web sitesi](../collaborate-share/service-embed-secure.md) gibi farklı yere eklenecek mi?
- Tüketiciler, içeriğe [mobil cihazlar](../consumer/mobile/mobile-apps-for-mobile-devices.md) aracılığıyla mı erişecek? Küçük form faktörü cihazlarına rapor sunma gereksinimler, [rapor tasarımına ilişkin bazı kararları](../create-reports/desktop-create-phone-report.md) etkiler.

## <a name="decide-if-other-content-may-be-created"></a>Başka içerik oluşturulup oluşturulamayacağını belirleme

Tüketicilerin yeni içerik oluşturmasına izin vermeye ilişkin bazı önemli kararların (aşağıdakiler gibi) alınması gerekir:

- Tüketicilerin yayımlanan veri kümesinden yeni rapor oluşturmasına izin verilecek mi? Bu özellik, bir kullanıcıya veri kümesi [oluşturma izni](../connect-data/service-datasets-build-permissions.md) verilerek etkinleştirilebilir.
- Bir raporu özelleştirmek isteyen tüketicilere raporun bir[kopyasını kaydetme](../connect-data/service-datasets-copy-reports.md) ve bunu ihtiyaçlar doğrultusunda kişiselleştirme olanağı sunulur mu?

> [!CAUTION]
> Faydalı bir özellik olan _Kopyasını kaydetme_ özelliğinin bazı grafikleri veya üst bilgi/alt bilgi iletilerini içeren raporlarda dikkatli kullanılması gerekir. Logolar, simgeler ve metin biçimindeki iletiler genelde markalama gereksinimleri veya mevzuata uyumluluk ile ilişkilendirildiğinden, bunların nasıl teslim edildiğinin ve dağıtıldığının dikkatle denetlenmesi gerekir. _Kopyasını kaydet_ özelliği kullanılıyorsa ve yeni yazar özgün grafikleri veya üst bilgi/alt bilgi iletilerini değiştirmediyse, raporu kimin oluşturduğuna ilişkin karmaşıklık oluşabilir. Bu, markalamanın anlamının kısmen kaybolmasına de neden olabilir.

## <a name="evaluate-needs-for-premium-capacity"></a>Premium kapasiteye yönelik ihtiyacı değerlendirme

Bir çalışma alanı [Premium kapasitede](../admin/service-premium-what-is.md) depolandığında ek özellikler sunulur. Premium kapasiteli çalışma alanlarını kullanarak şu avantajları elde edersiniz:

- Power BI Pro lisansı olmayan tüketiciler içeriğe erişebilir.
- Büyük veri kümelerine yönelik destek elde edilir.
- Daha sık veri yenilemesine yönelik destek elde edilir.
- Veri akışlarının tam özellik kümesini kullanma desteği elde edilir.
- Dağıtım işlem hatlarını ve XMLA uç noktasını da içeren kurumsal özellikler elde edilir.
- Sayfalandırılmış raporlara yönelik destek (iş yükü etkinleştirildiğinde).

## <a name="determine-data-acquisition-method"></a>Veri alma yöntemini belirleme

Bir rapor için gereken veriler çeşitli kararları etkileyebilir. Sorulacak sorular şunlardır:

- Mevcut bir Power BI [paylaşılan veri kümesi](../connect-data/service-datasets-share.md) kullanılabilir mi? Ya da, bu çözüm için yeni bir Power BI veri kümesinin oluşturulması mı daha uygun olur?
- Ek ihtiyaçların karşılanması için mevcut bir paylaşılan veri kümesinin yeni verilerle veya önlemlerle artırılması gerekir mi?
- Hangi [veri depolama modu](../transform-model/desktop-storage-mode.md) en uygunu olur? İçeri aktarma, DirectQuery, Bileşik veya Canlı Bağlantı gibi seçenekler bulunur.
- Sorgu performansının artırılması için [toplamaların](../transform-model/desktop-aggregations.md) kullanılması gerekir mi?
- Bir [veri akışının](../transform-model/dataflows/dataflows-introduction-self-service.md) oluşturulması fayda sağlayıp çok sayıda veri kümesi için kaynak işlevi görebilir mi?
- Yeni bir [ağ geçidi veri kaynağının](../connect-data/service-gateway-data-sources.md) kaydedilmesi gerekir mi?

## <a name="decide-where-original-content-will-be-stored"></a>Özgün içeriğin nerede depolanacağını belirleme

Hedef dağıtım hedefini planlamaya ek olarak, özgün (veya kaynak) içeriğin nerede depolanacağının planlanması da önemlidir:

- Özgün Power BI Desktop (.pbix) dosyalarının depolanması için onaylanmış bir konum belirtin. Yalnızca içeriği düzenleyen kişiler bu konumu kullanabilir. Bunun, Power BI hizmetinde yapılan güvenlik ayarlarıyla uyumlu olması gerekir.
- Sürüm oluşturma geçmişini veya kaynak denetimini içeren özgün Power BI Desktop dosyaları için bir konumu kullanın. Sürüm oluşturma, içerik yazarının gerekirse dosya sürümünü önceki bir sürüme geri çevirmesine olanak tanır. OneDrive İş veya SharePoint bu amaç için uygundur.
- Düz dosyalar veya Excel dosyaları gibi merkezi hale getirilmemiş kaynak verilerinin depolanması için onaylanmış bir konum belirtin. Bunun, tüm veri kümesi yazarlarının hatasız erişebildiği ve düzenli olarak yedeklenen bir yol olması gerekir.
- Power BI hizmetinden dışarı aktarılan içerik için onaylanmış bir konum belirtin. Bu işlemle, Power BI’da tanımlanan güvenlik ayarlarının yanlışlıkla aşılmaması amaçlanır.

> [!IMPORTANT]
> Özgün Power BI Desktop dosyalarının içeri aktarılan verileri içerdiği durumlarda bu dosyalar için korunan bir konum belirtilmesi oldukça önemlidir.

## <a name="assess-the-level-of-effort"></a>Çalışma düzeyini değerlendirme

[1. aşamada](powerbi-migration-requirements.md) açıklanan gereksinimler ve çözüm dağıtımı planlama işlemi yeterli düzeyde bilgi sunuyorsa çalışma düzeyi değerlendirilebilir. Bunun ardından, görevleri, zaman çizelgesini ve sorumluluğu içeren bir proje planı oluşturulabilir.

> [!TIP]
> Çoğu organizasyonun en büyük harcamalarından birisi işgücü maliyetleridir (maaşlar ve ücretler). Doğru tahmin edilmesi zor olsa da, üretkenlik geliştirmeleri yüksek yatırım getirisi (ROI) sunar.

## <a name="next-steps"></a>Sonraki adımlar

[Bu Power BI geçişi serisinin sonraki makalesinde](powerbi-migration-proof-of-concept.md), Power BI geçişi sırasında riskin azaltılması ve bilinmeyenlerin ele alınması gibi süreçlerin olabildiğince erken tamamlanmasını ele alan 3. aşamaya ilişkin bilgiler sunulur.

Diğer faydalı kaynakları da inceleyebilirsiniz:

- [Microsoft’un BI dönüşümü](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [Power BI kuruluş dağıtımı planlama teknik incelemesi](https://aka.ms/PBIEnterpriseDeploymentWP)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)

Deneyimli Power BI iş ortakları, kuruluşunuzun başarıyla geçiş yapmasına yardımcı olabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.