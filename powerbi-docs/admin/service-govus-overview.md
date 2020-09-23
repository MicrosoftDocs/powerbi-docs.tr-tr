---
title: ABD kamu müşterileri için Power BI - Genel Bakış
description: ABD Kamu müşterileri Microsoft 365 kamu planlarına bir Power BI Pro aboneliği ekleyebilir. Bu hizmet açıklamasında özelliğe kaydolmayı ve özellik kullanılabilirliğini gözden geçirmeyi öğrenin.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/02/2020
ms.author: kfollis
ms.custom: licensing support
LocalizationGroup: Get started
ms.openlocfilehash: 948e0260f13aa243a45ba5bdf6fe59c9699d47a0
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90855116"
---
# <a name="power-bi-for-us-government-customers"></a>ABD kamu müşterileri için Power BI

Bu makale Microsoft 365 Kamu planı kapsamında Power BI dağıtımı yapan ABD kamu müşterilerine yöneliktir. Kamu planları ABD uyumluluk ve güvenlik standartlarına uyması gereken kuruluşların benzersiz gereksinimlerine yönelik tasarlanmıştır. ABD kamu müşterileri için tasarlanmış Power BI hizmeti, Power BI hizmetinin ticari sürümünden farklıdır. Bu özellik farklılıkları ve beceriler aşağıdaki bölümlerde açıklanmıştır.

## <a name="add-power-bi-to-your-microsoft-365-government-plan"></a>Microsoft 365 Kamu planınıza Power BI ekleme

Power BI ABD kamu aboneliğini alabilmek ve kullanıcılara lisans atayabilmek için önce bir Microsoft 365 Kamu planına kaydolmalısınız. Kuruluşunuzun zaten Microsoft 365 Kamu planı varsa, [Kamu müşterileri için Power BI Pro aboneliği satın alma](#buy-a-power-bi-pro-subscription-for-government-customers) bölümüne atlayın.

### <a name="enroll-in-a-microsoft-365-government-plan"></a>Microsoft 365 Kamu planına kaydolma

Yeni bir müşteriyseniz Microsoft 365 Kamu planına kaydolmadan önce kuruluşunuzun uygunluğunu doğrulamanız gerekir.  Başlangıç olarak [Microsoft 365 Kamu uygunluk doğrulama formunu](https://www.microsoft.com/microsoft-365/government/eligibility-validation) tamamlayın. Kuruluşunuza doğru planı seçtiğinizden emin olmak için [Microsoft 365 ABD Kamu hizmet açıklamalarına](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) başvurun.

> [!NOTE]
> Power BI’ı zaten ticari bir ortama dağıttıysanız ve ABD kamu bulutuna geçmek istiyorsanız, Microsoft 365 Kamu planınıza yeni bir Power BI Pro aboneliği eklemeniz gerekir. Ardından ticari verileri ABD kamu için Power BI hizmetine çoğaltın, kullanıcı hesaplarından ticari lisans atamalarını kaldırın ve sonra kullanıcı hesaplarına Power BI Pro kamu lisansı atayın.
>
>
### <a name="buy-a-power-bi-pro-subscription-for-government-customers"></a>Kamu müşterileri için Power BI Pro aboneliği satın alma

Microsoft 365’i dağıttıktan sonra bir Power BI Pro aboneliği ekleyebilirsiniz. Power BI Pro kamu hizmetini satın almak için [ABD kamu kuruluşunuzu kaydetme](service-govus-signup.md) konusundaki adım adım yönergeleri izleyin. Power BI’ı kullanması gereken tüm kullanıcılara yetecek kadar lisans satın alın ve bu lisansları tek tek kullanıcı hesaplarına atayın.

> [!IMPORTANT]
> Power BI US Government, *Ücretsiz* lisans olarak sağlanmaz. Kamu topluluk bulutuna erişebilmeleri için her kullanıcıya bir *Pro* lisansı atanmalıdır. Bir kullanıcı hesabına Ücretsiz lisans atandıysa, bu kullanıcı yalnızca ticari buluta erişim yetkisine sahip olur; kimlik doğrulaması ve erişim sorunlarıyla karşılaşır. Power BI Premium’u satın aldıysanız, kullanıcı erişimini etkinleştirmek için Pro lisansları atamanız gerekmez.  Kuruluştaki kullanıcılar, Premium kapasitede yayımlandığı sürece kendileriyle paylaşılan raporlara erişebilir. Lisans türleri arasındaki farkları gözden geçirmek için bkz. [Lisans türüne göre Power BI hizmeti özellikleri](../fundamentals/service-features-license-type.md).
>

## <a name="government-cloud-instances"></a>Kamu bulutu örnekleri

Microsoft 365 çeşitli uyumluluk gereksinimlerini karşılamak için kamu kuruluşlarına farklı ortamlar sağlar. Ortamlar hakkında daha fazla bilgi için şu sayfalara bakın:

* Federal yönetim, eyalet yönetimi ve yerel yönetim için tasarlanan [Microsoft 365 Government Community Cloud (GCC)](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).

* [Microsoft 365 Government Community Cloud (GCC High)](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc-high-and-dod) federal kurumlar, savunma sektörü, havacılık sektörü ve denetimli sınıflandırılmamış bilgiler bulunduran diğer kuruluşlar için tasarlanmıştır. Bu ortam ulusal güvenlik kuruluşlarına ve Uluslararası Silah Trafiği Yönetmeliği (ITAR) verilerinin veya Savunma Federal İktisap Yönetmeliği Ekleri (DFARS) gereksinimlerinin söz konusu olduğu şirketlere uygundur.

* [Microsoft 365 DoD ortamı](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc-high-and-dod) özel olarak ABD Savunma Bakanlığı için tasarlanmıştır.

## <a name="connect-to-power-bi-for-us-government"></a>ABD kamu için Power BI’a bağlanma

Kamu kullanıcılarının Power BI'a bağlanmak için kullanmaları gereken URL, ticari kullanıcılarınkinden farklıdır. Power BI’da oturum açmak için aşağıdaki URL’leri kullanın:

| Ticari sürüm  | GCC  | GCC High | DoD |
| --- | --- | --- | --- |
| [https://app.powerbi.com/](https://app.powerbi.com) |[https://app.powerbigov.us](https://app.powerbigov.us) | [https://app.high.powerbigov.us](https://app.high.powerbigov.us) | [https://app.mil.powerbigov.us](https://app.mil.powerbigov.us) |

Hesabınız birden fazla bulutta ayarlanmış olabilir. Hesabınız bu şekilde ayarlanmışsa Power BI Desktop’ta oturum açtığınızda hangi buluta bağlanacağınızı seçebilirsiniz.

## <a name="connect-government-and-global-azure-cloud-services"></a>Kamuya özgü ve genel Azure bulut hizmetleri arasında bağlantı kurma

Azure birden çok buluta dağıtılmıştır. Varsayılan olara buluta özgü bir örneğin bağlantısını açarken güvenlik duvarı kurallarını etkinleştirebilirsiniz ama bulutlar arası ağ farklıdır.  Genel buluttaki hizmetlerle Government Community Cloud’daki hizmetler arasında iletişim kurmak için belirli güvenlik duvarı kurallarını yapılandırmanız gerekir. Örneğin Power BI’ın kamu bulut dağıtımından bir SQL veritabanının genel bulut örneklerine erişmek istiyorsanız, SQL veritabanında bir güvenlik duvarı kuralına ihtiyacınız vardır. Aşağıdaki veri merkezlerinde Azure Kamu Bulutu’na bağlantılara izin vermek için SQL veritabanında belirli güvenlik duvarı kurallarını yapılandırın:

* USGov Iowa
* USGov Virginia
* USGov Texas
* USGov Arizona

Genel bulutta IP alanları kullanılabilir. ABD kamu bulutu IP aralıklarını almak için [Azure IP Aralıkları ve Hizmet Etiketleri – ABD Kamu Bulutu](https://www.microsoft.com/download/details.aspx?id=57063) dosyasını indirin.

SQL veritabanlarına özgü güvenlik duvarı ayarları için bkz. [IP güvenlik duvarı kurallarını oluşturma ve yönetme](/azure/sql-database/sql-database-firewall-configure#create-and-manage-ip-firewall-rules).

## <a name="power-bi-feature-availability"></a>Power BI özellik kullanılabilirliği

Kamu bulutu müşterilerinin gereksinimlerini karşılamak için, kamu planlarıyla ticari planlar arasında bazı farklılıklar vardır. Hedefimiz, tüm özellikleri kamu bulutlarında 30 günlük genel kullanılabilirlik süresi içinde kullanılabilir hale getirmektir. Bazı durumlarda temel bağımlılıklar bir özelliği kullanıma sunmamızı engeller.

Aşağıdaki tabloda, belirli bir kamu ortamında bulunmayan özellikler ve sürüm planlanıyorsa tahmini kullanılabilirlik zamanı listelenmektedir:

|Öne çıkan özelliği |GCC |GCC High |DoD|
|------|------|------|------|
|[Kamu bulutu ve ticari bulut arasında Azure B2B İşbirliği](service-admin-azure-ad-b2b.md)<sup>1</sup>|![kullanılabilir](../media/yes.png)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|
|[Power BI web bölümünü kullanarak SharePoint Online’a ekleme](/esharepoint/dev/spfx/web-parts/overview-client-side-web-parts)|![kullanılabilir](../media/yes.png)|![Kullanılabilir](../media/yes.png)|![kullanılamaz](../media/no.png)|
|[Veri odaklı uyarılar için Power Automate bağlantısı](../connect-data/power-bi-data-sources.md)|![kullanılabilir](../media/yes.png)|![kullanılabilir](../media/yes.png)|![kullanılamaz](../media/no.png)|
|[Teams’de Power BI sekmesi](../collaborate-share/service-collaborate-microsoft-teams.md)<sup>2</sup>|![kullanılabilir](../media/yes.png)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|
|[Kapasite Ölçümleri](../admin/service-admin-premium-monitor-portal.md)|Ç3 2020 |Ç3 2020|Ç3 2020|
|[Büyük modeller](service-premium-large-models.md) | Ç4 2020 |Ç4 2020| ![kullanılamaz](../media/no.png) |
|[Veri akışları - SQL İşlem altyapısı iyileştirmesi](../transform-model/service-dataflows-enhanced-compute-engine.md) | Ç4 2020 |Ç4 2020| ![kullanılamaz](../media/no.png) |
|[Veri akışları - Doğrudan Sorgu](../transform-model/service-dataflows-directquery.md) | Ç4 2020 |Ç4 2020|![kullanılamaz](../media/no.png)|
|[Hizmet kesintisi bildirimleri](service-premium-large-models.md)|Ç4 2020 |Ç4 2020|Ç4 2020|
|[Veri Koruması (MIP etiketleri)](service-security-sensitivity-label-overview.md)|Ç4 2020|Ç4 2020 |Ç4 2020|
|[Şablon uygulamaları](../connect-data/service-template-apps-overview.md)<sup>3</sup>|Ç4 2020 |Ç4 2020| Ç4 2020|
|[Özel Görseller](../developer/visuals/power-bi-custom-visuals.md)<sup>3</sup>|Ç4 2020 |Ç4 2020| Ç4 2020|
|[QR Kodu oluşturma](../create-reports/service-create-qr-code-for-tile.md)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|

<sup>1</sup> B2B İşbirliği GCC için sunulur. Ancak, dış kullanıcıya bu ortamda bir lisans verilmesi gerekir. Ticari bulut lisansları GCC’de geçerli değildir. ABD Kamu için B2B İşbirliğine ilişkin bilinen sınırlamalar hakkında daha fazla bilgi edinmek için bkz. [Azure Kamu ile genel Azure karşılaştırması](/azure/azure-government/compare-azure-government-global-azure#azure-active-directory-premium-p1-and-p2)

<sup>2</sup> GCC için Teams’de Power BI deneyimi sınırlıdır, yalnızca klasik çalışma alanları için çalışır ve [Power BI içeriğini Microsoft Teams’e ekleme](../collaborate-share/service-embed-report-microsoft-teams.md) bölümünde açıklanan gelişmiş işlevleri içermez.

<sup>3</sup> Yayınlanan Şablon Uygulamaları ve Özel Görseller işlevleri, resmi bulutlarla sınırlı olacaktır. Belirli sınırlamalar hakkında daha fazla bilgi, yayın sırasında yayımlanacaktır.

## <a name="next-steps"></a>Sonraki adımlar

* [ABD kamu için Power BI'a kaydolma](service-govus-signup.md)
* [Microsoft Power Apps US Government](/power-platform/admin/powerapps-us-government)
* [Power Automate US Government](/power-automate/us-govt)
* [Power BI US Government Demosu](https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government)