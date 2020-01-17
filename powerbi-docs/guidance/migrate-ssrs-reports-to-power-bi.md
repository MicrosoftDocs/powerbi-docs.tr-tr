---
title: SQL Server Reporting Services raporlarını Power BI’a geçirme
description: SQL Server Reporting Services (SSRS) raporlarınızı Power BI'a geçirmenize yardımcı olacak bilgiler.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/03/2020
ms.author: v-pemyer
ms.openlocfilehash: b1ce8644decb758775c0bbff87df7975a64692a2
ms.sourcegitcommit: 801d2baa944469a5b79cf591eb8afd18ca4e00b1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75886125"
---
# <a name="migrate-sql-server-reporting-services-reports-to-power-bi"></a>SQL Server Reporting Services raporlarını Power BI’a geçirme

Bu makale, SQL Server Reporting Services (SSRS) rapor yazarlarına ve Power BI yöneticilerine yöneliktir. [Rapor Tanım Dili (RDL)](/sql/reporting-services/reports/report-definition-language-ssrs) ile yazılmış raporlarınızı Power BI'a geçirme konusunda yardımcı olacak bilgiler sağlanmaktadır.

> [!NOTE]
> Yalnızca RDL raporları geçirilebilir. RDL raporları Power BI'da _sayfalandırılmış raporlar_ olarak adlandırılır.

Bu kılavuz dört aşamaya ayrılmıştır. Raporlarınızı geçirmeden önce makalenin tamamını okumanız önerilir.

1. [Başlamadan önce](#before-you-start)
1. [Geçiş öncesi aşama](#pre-migration-stage)
1. [Geçiş aşaması](#migration-stage)
1. [Geçiş sonrası aşama](#post-migration-stage)

Geçiş işlemini SRSS sunucularınızda kesinti yaşamadan ve rapor kullanıcılarınıza engel olmadan tamamlayabilirsiniz. Verileri veya raporları kaldırmanıza gerek olmadığını anlamanız önemlidir. Başka bir deyişle yeni ortama geçmeye hazır olana kadar mevcut ortamınızı kullanmaya devam edebilirsiniz.

## <a name="before-you-start"></a>Başlamadan önce

Geçiş işlemine başlamadan önce ortamınızın belirli önkoşulları karşıladığını doğrulamanız gerekir. Bu önkoşulları açıklayacak ve bu süreçte size yardımcı olacak bir geçiş aracını tanıtacağız.

### <a name="preparing-for-migration"></a>Geçiş için hazırlanma

Raporlarınızı Power BI'a geçirmeye hazırlanırken yapmanız gereken ilk şey, kuruluşunuzun [Power BI Premium](../service-premium-what-is.md) aboneliği olduğundan emin olmaktır. Power BI sayfalandırılmış raporlarınızı barındırmak ve çalıştırmak için bu aboneliğe sahip olmanız gerekir.

### <a name="supported-versions"></a>Desteklenen sürümler

Şirket içinde veya Azure gibi bulut sağlayıcılarda barındırılan Sanal Makineler üzerinde çalışan SSRS örneklerini geçirebilirsiniz. 

Aşağıdaki listede Power BI'a geçiş için desteklenen SQL Server sürümleri yer almaktadır:

> [!div class="checklist"]
> * SQL Server 2012
> * SQL Server 2014
> * SQL Server 2016
> * SQL Server 2017
> * SQL Server 2019

Power BI Rapor Sunucusu'ndan da geçiş yapabilirsiniz.

### <a name="migration-tool"></a>Geçiş aracı

Raporlarınızı hazırlama ve geçirme aşamalarında [RDL Migration Tool](https://github.com/microsoft/RdlMigration)'dan yardım almanızı öneririz. Bu araç, Microsoft tarafından müşterilerin SSRS sunucularındaki RDL raporlarını Power BI'a geçirmelerine yardımcı olma amacıyla geliştirilmiştir. GitHub üzerinden sunulan bu araçla birlikte geçiş senaryosunun tüm aşamalarını kapsayan belgeler de sunulmaktadır.

Araç şu görevleri otomatikleştirir:

* [Desteklenmeyen veri kaynaklarını](../paginated-reports-data-sources.md) ve [desteklenmeyen rapor özelliklerini](../paginated-reports-faq.md#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi) denetler
* _Paylaşılan_ kaynakları _katıştırılmış_ kaynaklara dönüştürür:
  * Paylaşılan **veri kaynakları**, katıştırılmış veri kaynakları olur
  * Paylaşılan **veri kümeleri**, katıştırılmış veri kümeleri olur
* Raporları (denetimleri geçenleri), belirtilen Power BI çalışma alanında (Premium kapasitede) sayfalandırılmış raporlar olarak yayımlar.

Mevcut raporlarınızı değiştirmez veya kaldırmaz. Araç, işlemleri tamamladıktan sonra gerçekleştirilen tüm eylemlerin (başarılı ve başarısız) yer aldığı bir özet oluşturur.

Microsoft, bu aracı ilerleyen dönemlerde geliştirebilir. Topluluğun da katkıda bulunması ve geliştirilmesine yardımcı olması mutlulukla karşılanacaktır.

## <a name="pre-migration-stage"></a>Geçiş öncesi aşama

Kuruluşunuzun önkoşulları karşıladığını doğruladıktan sonra _Geçiş öncesi_ aşamayı başlatabilirsiniz. Bu aşama, üç bölümden oluşur:

1. Bul
1. Değerlendirme
1. Hazırlama

### <a name="discover"></a>Bul

_Bul_ bölümünün hedefi, mevcut SSRS örneklerinizi tanımlamaktır. Bu işlem kapsamında ağınız taranır ve kuruluşunuzdaki tüm SQL Server örnekleri tanımlanır.

[Microsoft Değerlendirme ve Planlama Araç Seti](https://www.microsoft.com/download/details.aspx?id=7826)'ni de kullanabilirsiniz. "MAP Araç Seti" olarak bilinen bu uygulama SQL Server örneklerinizi, sürümlerini ve yüklü özellikleri bulur ve raporlar. Geçiş planlama sürecinizi kolaylaştırabilecek güçlü bir envanter, değerlendirme ve raporlama aracıdır.

### <a name="assess"></a>Değerlendirme

SSRS örneklerinizi bulduktan sonra geçeceğiniz _Değerlendirme_ bölümünün amacı, geçirilemeyecek olan SSRS raporlarını veya sunucu öğelerini anlamaktır.

SSRS sunucularınızdan Power BI'a yalnızca RDL raporlar geçirilebilir. Geçirilen RDL raporları, Power BI sayfalandırılmış raporlarına dönüştürülecektir.

Ancak aşağıdaki SSRS öğeleri Power BI'a geçirilemez:

* Paylaşılan veri kaynakları <sup>1</sup>
* Paylaşılan veri kümeleri <sup>1</sup>
* Görüntü dosyaları gibi kaynaklar
* KPI'ler (SSRS 2016 veya üzeri - yalnızca Enterprise Edition)
* Mobil raporlar (SSRS 2016 veya üzeri - yalnızca Enterprise Edition)
* Rapor modelleri (kullanım dışı)
* Rapor bölümleri (kullanım dışı)

<sup>1</sup> [RDL Migration Tool](https://github.com/microsoft/RdlMigration), desteklenen veri kaynaklarını kullanan paylaşılan veri kaynaklarını ve paylaşılan veri kümelerini otomatik olarak dönüştürür.

[Henüz Power BI sayfalandırılmış raporları tarafından desteklenmeyen](../paginated-reports-faq.md#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi) özellikleri kullanan RDL raporlarınızı, [Power BI raporları](../consumer/end-user-reports.md) olarak yeniden geliştirmeyi planlayabilirsiniz. Geçirebildiğiniz RDL raporlarınızı da mümkün olması halinde modernleştirerek Power BI raporu haline getirmeniz önerilir.

Power BI sayfalandırılmış raporları genellikle **yazdırma** veya **PDF oluşturma** için iyileştirilmiştir. Power BI raporları, **araştırma ve etkileşim** için iyileştirilmiştir. Daha fazla bilgi için bkz. [Power BI’daki sayfalandırılmış raporları kullanma zamanı](report-paginated-or-power-bi.md).

### <a name="prepare"></a>Hazırlama

_Hazırlama_ bölümünün amacı, tüm bileşenleri hazır hale getirmektir. Bu bölümde Power BI ortamı ayarlanır, raporlarınızın güvenliğini sağlama ve onları yayımlama konusunda planlama yapılır ve geçirilemeyecek olan SSRS öğelerinin yeniden geliştirilmesiyle ilgili fikirler üretilir.

1. Power BI Premium kapasitenizde [Sayfalandırılmış Raporlar iş yükünün](../service-admin-premium-workloads.md#paginated-reports) etkinleştirilmiş durumda ve yeterli belleğe sahip olduğundan emin olun.
1. Rapor [veri kaynaklarınızın](../paginated-reports-data-sources.md) desteklendiğini doğrulayın ve şirket içi veri kaynaklarına bağlanmak için bir [Power BI Ağ Geçidi](../service-gateway-onprem.md) ayarlayın.
1. [Power BI çalışma alanları ve çalışma alanı rolleri](../service-new-workspaces.md) sayfasını inceleyerek Power BI güvenliği hakkında bilgi edinin ve [SSRS klasörlerinizi ve izinlerinizi nasıl yeniden oluşturabileceğinizi](/sql/reporting-services/security/secure-folders) planlayın.
1. Power BI paylaşımı hakkında bilgi edinin ve [Power BI uygulamalarını](../service-create-distribute-apps.md) yayımlayarak içeriğinizi nasıl dağıtacağınızı planlayın.
1. SSRS paylaşılan veri kaynaklarınızın yerine [paylaşılan Power BI veri kümelerini](../service-datasets-build-permissions.md) kullanmayı değerlendirin.
1. [Power BI Desktop](../desktop-what-is-desktop.md)'ı kullanarak mobil cihazlar için iyileştirilmiş raporlar geliştirin ve mümkünse SSRS mobil raporlarınızın ve KPI'lerin yerine [Power KPI özel görseli](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083?tab=Overview) kullanın.
1. Rapor yazarlarınızın [Power BI Report Builder](../report-builder-power-bi.md) uygulamasını yüklediğinden ve yeni sürümlerin kuruluşunuzda kolayca dağıtılabileceğinden emin olun.

## <a name="migration-stage"></a>Geçiş aşaması

Power BI ortamınızı ve raporlarınızı hazırladıktan sonra _Geçiş_ aşamasıyla devam edebilirsiniz.

İki geçiş seçeneği vardır: _el ile_ ve _otomatik_. El ile geçiş, az sayıda rapor veya geçiş öncesinde üzerinde değişiklik yapılması gereken raporlar için uygundur. Otomatik geçiş, çok sayıda raporu geçirmek için uygundur.

### <a name="manual-migration"></a>El ile geçiş

SSRS örneğine ve Power BI çalışma alanına erişim izni olan herkes raporları el ile Power BI'a geçirebilir. İzlenmesi gereken adımlar şunlardır:

1. Geçirmek istediğiniz raporların bulunduğu SSRS portalını açın.
1. Her bir raporun tanımını indirin ve .rdl dosyalarını yerel ortamda kaydedin.
1. Power BI Report Builder uygulamasının _en son sürümünü_ açın ve Azure AD kimlik bilgilerinizi kullanarak Power BI hizmetine bağlanın.
1. Raporları Power BI Report Builder'ı kullanarak teker teker açın ve şu işlemleri gerçekleştirin:
   1. Tüm veri kaynaklarının ve veri kümelerinin rapor tanımına eklenmiş olduğunu ve bunların [desteklenen veri kaynakları](../paginated-reports-data-sources.md) olduğunu doğrulayın.
   1. Raporun önizlemesini yaparak doğru şekilde oluşturulduğundan emin olun.
   1. _Farklı Kaydet_'i ve ardından _Power BI hizmeti_'ni seçin.
   1. Raporu içerecek olan çalışma alanını seçin.
   1. Raporun kaydedildiğini doğrulayın. Rapor tasarımınızda henüz desteklenmeyen özellikler varsa kaydetme eylemi başarısız olur. Nedenler size bildirilir. Bu durumda rapor tasarımınızı düzenledikten sonra kaydetmeyi yeniden denemeniz gerekir.

### <a name="automated-migration"></a>Otomatik geçiş

Otomatik geçiş için iki seçenek vardır. Şunu kullanabilirsiniz:

* RDL Migration Tool
* SSRS ve Power BI için genel kullanıma açık API'ler

[RDL Migration Tool](#migration-tool) bu makalenin önceki bölümlerinde açıklanmıştır.

Dilerseniz genel kullanıma açık SSRS ve Power BI API'lerini kullanarak da içeriğinizin otomatik olarak geçirilmesini sağlayabilirsiniz. RDL Migration Tool da bu API'leri kullanır ancak gereksinimlerinize uygun özel bir araç geliştirme imkanı da sunulmuştur.

API'ler hakkında daha fazla bilgi için bkz.

* [Power BI Rest API Başvurusu](../developer/rest-api-reference.md)
* [SQL Server Reporting Services REST API'leri](/sql/reporting-services/developer/rest-api)

## <a name="post-migration-stage"></a>Geçiş sonrası aşama

Geçişi başarıyla tamamladıktan sonra _Geçiş sonrası_ aşamayla devam edebilirsiniz. Bu aşamada geçiş sonrası görevleri tamamlayarak her şeyin doğru ve verimli bir şekilde çalıştığından emin olmanız gerekir.

### <a name="configure-data-sources"></a>Veri kaynaklarını yapılandırma

Raporlar Power BI'a geçirildikten sonra veri kaynaklarının doğru şekilde ayarlandığından emin olmanız gerekir. Bunun için ağ geçidi veri kaynaklarına atama yapmanız ve [veri kaynağı kimlik bilgilerini güvenli bir şekilde depolamanız](../paginated-reports-data-sources.md#azure-sql-database-authentication) gerekebilir. Bu eylemler RDL Migration Tool tarafından gerçekleştirilmez.

### <a name="review-report-performance"></a>Rapor performansını gözden geçirme

Mümkün olan en iyi rapor kullanıcısı deneyimini sunmak için aşağıdaki eylemleri mutlaka tamamlamanız önerilir:

1. Raporları [Power BI tarafından desteklenen tarayıcıların](../power-bi-browsers.md) hepsinde test ederek raporun düzgün şekilde işlendiğini onaylayın.
1. Testler yaparak SSRS ve Power BI ortamlarındaki rapor işleme sürelerini karşılaştırın. Power BI raporlarının kabul edilebilir bir süre içinde işlenip işlenmediğini denetleyin.
1. Power BI raporları yetersiz bellek nedeniyle işlenemiyorsa [Power BI Premium kapasitesine ek kaynak](../service-admin-premium-workloads.md#paginated-reports) ayırın.
1. İşlenmesi uzun süren raporların, Power BI tarafından rapor kullanıcılarına [rapor eki bulunan e-posta abonelikleri](../consumer/paginated-reports-subscriptions.md) şeklinde gönderilmesini sağlayabilirsiniz.
1. Power BI veri kümelerini temel alan Power BI raporları için model tasarımlarını gözden geçerek tam olarak iyileştirilmiş olduklarından emin olun.

### <a name="reconcile-issues"></a>Sorunları giderin

Geçiş sonrası aşama, sorunların giderilmesi ve performans ile ilgili durumların çözülmesi açısından kritik öneme sahiptir. Sayfalandırılmış raporlar iş yükünün kapasiteye eklenmesi, sayfalandırılmış raporlar ve kapasitede depolanan _diğer içerikler_ için performansın düşmesine neden olabilir.

Anlama ve çözme adımları dahil olmak üzere bu sorunlar hakkında daha fazla bilgi için şu makalelere bakın:

* [Premium kapasiteleri iyileştirme](../service-premium-capacity-optimize.md)
* [Uygulama içinden Premium kapasiteleri izleme](../service-admin-premium-monitor-capacity.md)

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](../paginated-reports-report-builder-power-bi.md)
* Guy in a cube videosu: [Power BI’daki sayfalandırılmış raporlara giriş](https://www.youtube.com/watch?v=wfqn45XNK3M)
* [Power BI’daki sayfalandırılmış raporları kullanma zamanı](report-paginated-or-power-bi.md)
* [Power BI’daki sayfalandırılmış raporlar: SSS](../paginated-reports-faq.md)
* [Power BI Premium hakkında SSS](../service-premium-faq.md)
* [RDL Migration Tool](https://github.com/microsoft/RdlMigration)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
* Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)

Power BI iş ortakları, kuruluşunuzun geçiş sürecini başarılı bir şekilde atlatmasına yardımcı olabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.
