---
title: Power BI’a geçişe hazırlanma
description: Power BI’a geçiş yaparken uygulanan geçiş öncesi adımlara yönelik rehberlik.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: 9a5ed3d2a4798332de2394e1ad5be6fdbdb6eeae
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803614"
---
# <a name="prepare-to-migrate-to-power-bi"></a>Power BI’a geçişe hazırlanma

Bu makalede, Power BI geçişi öncesinde göz önünde bulundurulan eylemler açıklanır.

:::image type="content" source="media/powerbi-migration-pre-migration-steps/migrate-to-powerbi-pre-migration-steps.png" alt-text="Power BI geçişinin aşamalarını gösteren görüntü. Bu makalede geçiş öncesi adımları vurgulanır.":::

> [!NOTE]
> Yukarıdaki grafiğin kapsamlı açıklaması için bkz. [Power BI geçişine genel bakış](powerbi-migration-overview.md).

Geçiş öncesi adımları, beş geçiş aşaması uygulanmadan önce gerçekleştirilen ve hazırlanma açısından önemli olan ön planlamaya odaklanır. Geçiş öncesi adımların çoğu bir kez uygulanır. Ancak, büyük kuruluşlarda bazı kısımların her iş birimi veya departman alanı için yinelenmesi gerekebilir.

Geçiş öncesi adımlardan ilk idare modeli, ilk yüksek düzey dağıtım planlaması ve geçirilecek rapor ve verilerin envanteri gibi çıkışlar elde edilir. Ayrı çözümlerin geçirilmesine yönelik çalışmanın düzeyinin tam olarak tahmin edilebilmesi için 1, 2 ve 3. aşama kapsamındaki etkinliklerden elde edilen bilgilere ihtiyaç duyulur.

> [!TIP]
> Bu makalede ele alınan konuların çoğu standart Power BI uygulama projeleri için de geçerlidir.

## <a name="create-costbenefit-analysis-and-evaluation"></a>Maliyet/avantaj analizi ve değerlendirmesi oluşturma

İlk değerlendirme sırasında şunların elde edilmesi önemlidir:

- Belirli bir istenen geleceğe yönelik duruma erişilmesi için iş durumunun ve iş zekası stratejisinin netleştirilmesi.
- Başarının ne anlama geldiğini ve geçiş girişimine ilişkin ilerleme ve başarı düzeyinin nasıl ölçüldüğünü belirleme.
- Maliyet tahminleri ve yatırım getirisi (ROI) hesaplaması sonuçları.
- Kapsamı küçük ve karmaşıklık düzeyi düşük olan bazı üretken Power BI girişimlerine yönelik başarılı sonuçlar.

## <a name="identify-stakeholders-and-executive-support"></a>Paydaşları ve yönetim desteğini tanımlama

Paydaşlar tanımlanırken şu önemli noktalara dikkat edilmesi gerekir:

- İş durumunda ve iş zekası stratejisinde paydaşlara uyum sağlama.
- Tüm iş birimlerinin temsilcilerini (bu birimlerin içerikleri daha sonra geçirilecek olsa bile) sürece dahil etme ve onların motivasyonlarını ve endişelerini anlama.
- Power BI şampiyonlarını sürece erken dahil etme.
- Paydaşlarla bir iletişim planı oluşturup bunu sürdürün.

> [!TIP]
> Çok sık iletişim kurduğunuzdan endişe duymaya başladıysanız, iletişim muhtemelen uygun düzeydedir.

## <a name="generate-initial-governance-model"></a>İlk idare modelini oluşturma

Bir Power BI uygulamasının başında ele alınması gereken konular şunlardır:

- Power BI’ın benimsenmesine yönelik belirli hedefler ve Power BI’ın kuruluşun genel iş zekası stratejisindeki konumu.
- Power BI yöneticisi rolünün özellikle merkezi olmayan kuruluşlarda nasıl yönetileceğini kararlaştırma.
- Güvenilir veri elde etmeye ilişkin ilkeler: yetkili veri kaynaklarının kullanılması, veri kalitesi sorunlarının giderilmesi ve tutarlı terminoloji ve ortak tanımların kullanılması.
- İç ve dış kullanıcılara içerik sunulması ve veri kaynaklarına, veri modellerine ve raporlara yönelik güvenlik ve veri gizliliği stratejisi belirleme.
- İç ve dış uyumluluk, düzenleme ve denetim gereksinimlerin nasıl karşılanacağını belirleme.

> [!IMPORTANT]
> En etkili yönetim modelleri, kullanıcıyı güçlendirmeyi ve bunu gerekli düzeyde denetim sunarak dengelemeyi amaçlar. Daha fazla bilgi edinmek için bkz. [çekirdekte disiplin](center-of-excellence-microsoft-business-intelligence-transformation.md#discipline-at-the-core) ve [uç birimde esneklik](center-of-excellence-microsoft-business-intelligence-transformation.md#flexibility-at-the-edge).

## <a name="conduct-initial-deployment-planning"></a>İlk dağıtım planlamasını gerçekleştirme

İlk dağıtım planlaması, kuruluşun Power BI uygulamasına yönelik standartların, ilkelerin ve tercihlerin tanımlanmasını içerir.

[2. aşamanın](powerbi-migration-planning.md) çözüm düzeyinde dağıtım planlamasına başvurduğunu unutmayın. 2\. aşamadaki etkinliklerde kuruluş düzeyinde alınan kararlara mümkün olduğunca uyum sağlanması gerekir.

Bir Power BI uygulamasının başında ele alınması gereken bazı önemli konular şunlardır:

- [Power BI kiracı yöneticisi ayarlarına](admin-tenant-settings.md) ilişkin kararlar (belgelenmesi gerekir).
- [Çalışma alanı yönetimine](../collaborate-share/service-new-workspaces.md) ilişkin kararlar (belgelenmesi gerekir).
- Uygulamalar, çalışma alanları, paylaşma, abonelikler ve içerik ekleme gibi veri ve [içerik dağıtım yöntemlerine](../collaborate-share/service-how-to-collaborate-distribute-dashboards-reports.md) ilişkin noktalar ve tercihler.
- İçeri aktarma modu, DirectQuery modu ve iki modun bir [Bileşik modelde](composite-model-guidance.md) birleştirilmesi gibi [veri kümesi modlarına](../connect-data/service-dataset-modes-understand.md) ilişkin tercihler.
- [Verilerin ve erişimin güvenliğini sağlama](../admin/service-admin-power-bi-security.md).
- Yeniden kullanılabilirlik için [paylaşılan veri kümeleriyle](../connect-data/service-datasets-share.md) çalışma.
- Yetkili ve güvenilir verilerin kullanımını öne çıkarmak için [veri sertifikasyonu](../connect-data/service-datasets-certify.md) uygulama.
- Farklı kullanım durumları veya iş birimleri için Power BI raporları, Excel raporları veya sayfalandırılmış raporlar gibi farklı [rapor türlerini](../create-reports/index.yml) kullanma.
- Merkezi hale getirilmiş iş zekası yapıtlarının ve işletme tarafından yönetilen iş zekası yapıtlarının yönetilmesi için yönetim yaklaşımlarını değiştirme.
- Tüketicilere, veri modelleyicilerine, rapor yazarlarına ve yöneticilere yönelik eğitim planları.
- [Power BI Desktop şablonlarını](../create-reports/desktop-templates.md), [özel görselleri](https://powerbi.microsoft.com/blog/how-to-govern-power-bi-visuals-inside-your-organization/) ve belgelenmiş rapor tasarımı standartlarını kullanarak içerik yazarlarına destek sunma.
- Yeni lisans isteme, yeni ağ geçidi veri kaynakları ekleme, ağ geçidi veri kaynaklarına erişim izni elde etme, yeni çalışma alanları isteme, çalışma alanı izinlerine ilişkin değişiklikler ve düzenli olarak karşılaşılabilen diğer ortak gereksinimler gibi kullanıcı gereksinimlerinin yönetilmesine yönelik yordamlar ve işlemler.

> [!IMPORTANT]
> Dağıtım planlaması, yinelemeli bir işlemdir. Kuruluşunuzun Power BI deneyimi arttıkça ve Power BI geliştikçe dağıtıma ilişkin kararlar da gelişir. Bu süreçte alınan kararlar, geçiş işleminin [2. aşamasında](powerbi-migration-planning.md) ele alınan çözüm düzeyinde dağıtım planlamasında kullanılır.

## <a name="establish-initial-architecture"></a>İlk mimariyi oluşturma

[İş zekası çözüm mimariniz](center-of-excellence-business-intelligence-solution-architecture.md) zamanla gelişir ve olgunlaşır. Hemen tamamlanması gereken Power BI kurulum görevleri şunlardır:

- Power BI kiracı kurulumu ve Azure Active Directory tümleştirmesi.
- [Power BI yöneticilerini](../admin/service-admin-role.md) tanımlama.
- İlk [kullanıcı lisanslarını](../admin/service-admin-licensing-organization.md) temin etme ve atama.
- [Power BI kiracı yöneticisi ayarlarını](admin-tenant-settings.md) yapılandırma ve gözden geçirme.
- [Çalışma alanı rolleri](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces) kurulumu ve Azure Active Directory güvenlik gruplarına ve kullanıcılarına erişim atama.
- İlk [veri ağ geçidi](../connect-data/service-gateway-deployment-guidance.md) kümesini yapılandırma ve bunu düzenli olarak güncelleştirmeye yönelik bir plan belirleme.
- İlk [Premium kapasite lisansını](../admin/service-admin-premium-purchase.md) (varsa) temin etme.
- [Premium kapasite iş yüklerini](../admin/service-admin-premium-workloads.md) yapılandırma ve bunların sürekli olarak yönetilmesine yönelik bir plan belirleme.

## <a name="define-success-criteria-for-migration"></a>Geçiş için başarı ölçütlerini tanımlama

İlk görev, ayrı bir çözüm geçirilirken, geçiş işleminin başarılı olduğunu belirlemeye yönelik etkenleri anlamadır. Şu soruları sorabilirsiniz:

- **Bu geçişe yönelik belirli motivasyonlar ve amaçlar nelerdir?** Daha fazla bilgi için bkz. [Power BI geçişine genel bakış (Geçiş nedenlerini dikkate alma)](powerbi-migration-overview.md#consider-migration-reasons). Bu makalede, Power BI’a geçiş yapmaya yönelik en sık rastlanan nedenler açıklanır. Amaçlarınızın kesinlikle kuruluş düzeyinde belirtilmesi gerekir. Bunun yanı sıra, eski bir iş zekası çözümünün geçirilmesi önemli maliyet tasarrufu sunarken farklı bir iş zekası çözümünün geçirilmesiyle iş akışı iyileştirme avantajları elde edilebilir.
- **Bu geçişe yönelik beklenen maliyet/avantaj veya yatırım getirisi nedir?** Maliyet, daha fazla özelliğin sunulması, karmaşıklığın azalması ve çevikliğin artması gibi noktalara ilişkin beklentilerin net olarak anlaşılması, başarının ölçülmesine yardımcı olur. Bu, geçiş işlemi sırasında alınan kararlara destek olan yönlendirici ilkeleri sağlayabilir.
- **Başarının ölçülmesi için hangi anahtar performans göstergeleri (KPI) kullanılacak?** Aşağıdaki liste bazı örnek KPI’ları gösterir:
    - Eski iş zekası platformundan işlenen raporların sayısı (aydan aya azalan düzende).
    - Power BI’dan işlenen raporların sayısı (aydan aya artan düzende).
    - Power BI rapor tüketicilerinin sayısı (çeyrekten çeyreğe artan düzende).
    - Hedef tarihe kadar üretime geçirilen raporların yüzdesi.
    - Yıldan yıla lisans maliyetindeki azalma.

> [!TIP]
> [Power BI etkinlik günlüğü](../admin/service-admin-auditing.md), KPI ilerlemesini ölçmeye yönelik bir kaynak olarak kullanılabilir.

## <a name="prepare-inventory-of-existing-reports"></a>Mevcut raporların envanterini hazırlama

Eski iş zekası platformunda bulunan raporların envanterinin hazırlanması, mevcut olan öğelerin belirlenmesi açısından önemli bir adımdır. Bu adımda elde edilen sonuç, geçiş çalışması düzeyi değerlendirilirken giriş olarak kullanılabilir. Envanter hazırlamaya ilişkin etkinlikler şunları içerebilir:

1. **Rapor envanteri:** Geçiş adayı olan rapor ve panoların listesini derleyin.
2. **Veri kaynağı envanteri:** Mevcut raporların eriştiği tüm veri kaynaklarının listesini derleyin. Bunun hem kurumsal hem de kişisel ve departmana ilişkin veri kaynaklarını içermesi gerekir. Bu işlem ile BT departmanın bilmediği veri kaynakları ortaya çıkarılabilir. Bu, genelde _gölge BT_ olarak adlandırılır.
3. **Denetim günlüğü:** Kullanım desenlerini anlamak ve önceliklendirme işlemine yardımcı olmak için eski iş zekası platformunun denetim günlüğünden veri alın. Denetim günlüğünden elde edilen bilgiler şunlardır:
    - Her rapora ilişkin haftalık/aylık/çeyreklik ortalama yürütme sayısı.
    - Rapor başına haftalık/aylık/çeyreklik ortalama tüketici sayısı.
    - Her raporun tüketicileri, özellikle yöneticiler tarafından kullanılan raporlar.
    - Her rapora ilişkin en son yürütme tarihi.

> [!NOTE]
> Çoğu durumda, içerik Power BI’a olduğu gibi geçirilmez. Geçiş, veri mimarisinin yeniden tasarlanmasına ve/veya rapor teslimatının geliştirilmesine ilişkin bir fırsat sunar. Rapor envanteri derleme, hangi yeniden düzenleme işlemlerinin gerektiğini değerlendirmeniz için nelerin mevcut olduğunu anlama açısından önem taşır. Bu serinin diğer makalelerinde, olası geliştirmeler daha ayrıntılı şekilde ele alınır.

## <a name="explore-automation-options"></a>Otomasyon seçeneklerini keşfetme

Bir Power BI dönüştürme işlemi uçtan uca otomatikleştirilemez.

Bunu sizin için yapabilecek bir araca sahip olduktan sonra mevcut ve rapor envanterini derleme işlemini otomatikleştirebilirsiniz. Geçiş işleminin bazı bölümlerinde (mevcut envanterin derlenmesi gibi) kullanılacak otomasyonun belirlenmesi, sahip olduğunuz araçlara büyük ölçüde bağlıdır.

## <a name="next-steps"></a>Sonraki adımlar

[Bu Power BI geçişi serisinin sonraki makalesinde](powerbi-migration-requirements.md), Power BI’a geçiş yaparken gereksinimleri toplamayı ve bunları önceliklendirmeyi alan 1. aşamaya ilişkin bilgiler sunulur.

Diğer faydalı kaynakları da inceleyebilirsiniz:

- [Microsoft’un BI dönüşümü](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [Power BI kuruluş dağıtımı planlama teknik incelemesi](https://aka.ms/PBIEnterpriseDeploymentWP)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)

Deneyimli Power BI iş ortakları, kuruluşunuzun başarıyla geçiş yapmasına yardımcı olabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.
