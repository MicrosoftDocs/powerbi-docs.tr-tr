---
title: ABD kamu müşterileri için Power BI - Genel Bakış
description: ABD Kamu müşterileri Microsoft 365 kamu planlarına bir Power BI Pro aboneliği ekleyebilir. Bu hizmet açıklamasında özelliğe kaydolmayı, bağlanmayı ve özellik kullanılabilirliğini gözden geçirmeyi öğrenin.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/17/2020
ms.author: kfollis
ms.custom: licensing support
LocalizationGroup: Get started
ms.openlocfilehash: 8fa83bfc0dc19e4c60094b0ee3c26eb8f7bab12d
ms.sourcegitcommit: 5240990f998851c4854eb565de681099264c5a61
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94718903"
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


## <a name="sign-in-to-power-bi-for-us-government"></a>Power BI for US Government oturumu açma

Kamu kullanıcılarının Power BI'a bağlanmak için kullanmaları gereken URL, ticari kullanıcılarınkinden farklıdır. Power BI’da oturum açmak için aşağıdaki URL’leri kullanın:

| Ticari sürüm  | GCC  | GCC High | DoD |
| --- | --- | --- | --- |
| [https://app.powerbi.com/](https://app.powerbi.com) |[https://app.powerbigov.us](https://app.powerbigov.us) | [https://app.high.powerbigov.us](https://app.high.powerbigov.us) | [https://app.mil.powerbigov.us](https://app.mil.powerbigov.us) |

Hesabınız birden fazla bulutta ayarlanmış olabilir. Hesabınız bu şekilde ayarlanmışsa Power BI Desktop’ta oturum açtığınızda hangi buluta bağlanacağınızı seçebilirsiniz.

## <a name="allow-connections-to-power-bi"></a>Power BI bağlantılarına izin verme

Power BI hizmetini kullanmak için internet üzerindeki gerekli uç noktalarla bağlantı kurulmasına izin vermeniz gerekir. Ağınız, Power BI ve diğer bağımlı hizmetler arasında iletişim kurulabilmesi için bu hedeflere erişim sağlanabiliyor olması gerekir.

Aşağıdaki tabloda genel site kullanımı için Power BI hizmeti bağlantısını etkinleştirmek üzere izin verilenler listenize eklemeniz gereken uç noktalar listelenmiştir. Bu uç noktalar, ABD Kamu bulutuna özeldir. Power BI hizmetlerinin listelenen uç noktaları için yalnızca 443 numaralı TCP bağlantı noktasının açılması gerekir. Veri alma, pano ve rapor tümleştirmesi, Power BI görselleri ve diğer isteğe bağlı hizmetler ile ilgili uç noktalar, ABD Kamu bulutuna özel değildir. Bu URL'leri de izin verilenler listenize eklemek için bkz. [Power BI URL'lerini izin verilenler listenize ekleme](power-bi-whitelist-urls.md).

Power BI'ın kimlik doğrulaması, kimlik ve yönetim özellikleri, Microsoft 365 hizmetlerini kullanır. Denetim günlüklerini görüntülemek için de Microsoft 365'e bağlanmanız gerekir. Bu hizmetlerin uç noktalarını belirlemek için aşağıdaki Microsoft 365 tümleştirme tablosunu inceleyin.

### <a name="power-bi-urls-for-general-site-usage"></a>Genel site kullanımına yönelik Power BI URL'leri

|  Amaç | Hedef |
| ---- | ----- |
| Arka uç API’leri | **GCC**: api.powerbigov.us |
| | **GCC-High**: api.high.powerbigov.us |
| | **DoD**: api.mil.powerbi.gov.us |
| Arka uç API’leri | **GCC**: *analysis.usgovcloudapi.net |
| | **GCC High**: *.high.analysis.usgovcloudapi.net |
| | **DoD**: *.mil.analysis.usgovcloudapi.net |
| Arka uç API’leri | **Tümü**: *.pbidedicated.usgovcloudapi.net |
| Content Delivery Network (CDN) | **GCC**: gov.content.powerapps.us |
| | **GCC High**: high.content.powerapps.us |
| | **DoD**: mil.content.powerapps.us |
| Microsoft 365 tümleştirmesi | **GCC**: [Dünya genelindeki uç noktalar](/microsoft-365/enterprise/urls-and-ip-address-ranges) |
| | **GCC High**: [ABD Hükümeti GCC High uç noktaları](/microsoft-365/enterprise/microsoft-365-u-s-government-gcc-high-endpoints) |
| | **DoD**: [ABD Hükümeti DoD uç noktaları](/microsoft-365/enterprise/microsoft-365-u-s-government-dod-endpoints) |
| Portal |**GCC**: *.powerbigov.us |
| | **GCC-High**: *.high.powerbigov.us |
| | **DoD**: *.mil.powerbigov.us |
| Hizmet telemetrisi | **Tümü**: dc.services.visualstudio.us |
| Bilgilendirme iletileri (isteğe bağlı) | **Tümü**: dynmsg.modpim.com |
| NPS anketleri (isteğe bağlı) | **Tümü**: nps.onyx.azure.net |

## <a name="connect-government-and-global-azure-cloud-services"></a>Kamuya özgü ve genel Azure bulut hizmetleri arasında bağlantı kurma

Azure birden çok buluta dağıtılmıştır. Varsayılan olara buluta özgü bir örneğin bağlantısını açarken güvenlik duvarı kurallarını etkinleştirebilirsiniz ama bulutlar arası ağ farklıdır.  Genel buluttaki hizmetlerle Government Community Cloud’daki hizmetler arasında iletişim kurmak için belirli güvenlik duvarı kurallarını yapılandırmanız gerekir. Örneğin Power BI’ın kamu bulut dağıtımından bir SQL veritabanının genel bulut örneklerine erişmek istiyorsanız, SQL veritabanında bir güvenlik duvarı kuralına ihtiyacınız vardır. Aşağıdaki veri merkezlerinde Azure Kamu Bulutu’na bağlantılara izin vermek için SQL veritabanında belirli güvenlik duvarı kurallarını yapılandırın:

* USGov Iowa
* USGov Virginia
* USGov Texas
* USGov Arizona
* Doğu US DoD
* Orta US DoD

ABD kamu bulutu IP aralıklarını almak için [Azure IP Aralıkları ve Hizmet Etiketleri – ABD Kamu Bulutu](https://www.microsoft.com/download/details.aspx?id=57063) dosyasını indirin. Hem Power BI hem de Power Query aralıkları listelenmiştir.

Microsoft Azure Kamu bulutu hizmetleri hakkında daha fazla bilgi için [Azure Kamu belgelerini](/azure/azure-government/) inceleyin.

SQL veritabanlarına özgü güvenlik duvarı ayarları için bkz. [IP güvenlik duvarı kurallarını oluşturma ve yönetme](/azure/sql-database/sql-database-firewall-configure#create-and-manage-ip-firewall-rules).

## <a name="power-bi-feature-availability"></a>Power BI özellik kullanılabilirliği

Kamu bulutu müşterilerinin gereksinimlerini karşılamak için, kamu planlarıyla ticari planlar arasında bazı farklılıklar vardır. Hedefimiz, tüm özellikleri kamu bulutlarında 30 günlük genel kullanılabilirlik süresi içinde kullanılabilir hale getirmektir. Bazı durumlarda temel bağımlılıklar bir özelliği kullanıma sunmamızı engeller.

Aşağıdaki tabloda, belirli bir kamu ortamında bulunmayan özellikler listelenmiştir. Sürüm planlanıyorsa tahmini kullanılabilirlik zamanı da belirtilmiştir:

|Öne çıkan özelliği |GCC |GCC High |DoD|
|------|------|------|------|
|[Kamu bulutu ve ticari bulut arasında Azure B2B İşbirliği](service-admin-azure-ad-b2b.md)<sup>1</sup>|![kullanılabilir](../media/yes.png)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|
|[Power BI web bölümünü kullanarak SharePoint Online’a ekleme](/sharepoint/dev/spfx/web-parts/overview-client-side-web-parts)|![kullanılabilir](../media/yes.png)|![Kullanılabilir](../media/yes.png)|![kullanılamaz](../media/no.png)|
|[Veri odaklı uyarılar için Power Automate bağlantısı](../connect-data/power-bi-data-sources.md)|![kullanılabilir](../media/yes.png)|![kullanılabilir](../media/yes.png)|![kullanılamaz](../media/no.png)|
|[Teams’de Power BI sekmesi](../collaborate-share/service-collaborate-microsoft-teams.md)<sup>2</sup>|![kullanılabilir](../media/yes.png)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|
|[Büyük modeller](service-premium-large-models.md) | Ç4 2020 |Ç4 2020| ![kullanılamaz](../media/no.png) |
|[Veri akışları - SQL İşlem altyapısı iyileştirmesi](../transform-model/dataflows/dataflows-premium-features.md) | Ç4 2020 |Ç4 2020| ![kullanılamaz](../media/no.png) |
|[Veri akışları - Doğrudan Sorgu](../transform-model/dataflows/dataflows-configure-consume.md) | Ç4 2020 |Ç4 2020|![kullanılamaz](../media/no.png)|
|[Veri Koruması (MIP etiketleri)](service-security-sensitivity-label-overview.md)|Ç4 2020|Ç4 2020 |Ç4 2020|
|[Şablon uygulamaları](../connect-data/service-template-apps-overview.md)<sup>3</sup>|Ç4 2020 |Ç4 2020| Ç4 2020|
|[Özel Görseller](../developer/visuals/power-bi-custom-visuals.md)<sup>3</sup>|Ç4 2020 |Ç4 2020| Ç4 2020|
|[Azure Akış Analizi](/azure/stream-analytics/stream-analytics-power-bi-dashboard)| Ç4 2020|Ç4 2020|Ç4 2020|
|[Çağrı Kalitesi Veri Bağlayıcısı](/microsoftteams/cqd-power-bi-connector)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|
|[Kendi Depolama Alanını Getir (Azure Data Lake 2. Nesil)](../transform-model/dataflows/dataflows-azure-data-lake-storage-integration.md)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|
|[QR Kodu oluşturma](../create-reports/service-create-qr-code-for-tile.md)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|![kullanılamaz](../media/no.png)|

<sup>1</sup> B2B İşbirliği GCC için sunulur. Ancak, dış kullanıcıya bu ortamda bir lisans verilmesi gerekir. Ticari bulut lisansları GCC’de geçerli değildir. ABD Kamu için B2B İşbirliğine ilişkin bilinen sınırlamalar hakkında daha fazla bilgi edinmek için bkz. [Azure Kamu ile genel Azure karşılaştırması](/azure/azure-government/compare-azure-government-global-azure#azure-active-directory-premium-p1-and-p2)

<sup>2</sup> GCC için Teams’de Power BI deneyimi sınırlıdır, yalnızca klasik çalışma alanları için çalışır ve [Power BI içeriğini Microsoft Teams’e ekleme](../collaborate-share/service-embed-report-microsoft-teams.md) bölümünde açıklanan gelişmiş işlevleri içermez.

<sup>3</sup> Yayınlanan Şablon Uygulamaları ve Özel Görseller işlevleri, resmi bulutlarla sınırlı olacaktır. Belirli sınırlamalar hakkında daha fazla bilgi, yayın sırasında yayımlanacaktır.

## <a name="next-steps"></a>Sonraki adımlar

* [ABD kamu için Power BI'a kaydolma](service-govus-signup.md)
* [Microsoft Power Apps US Government](/power-platform/admin/powerapps-us-government)
* [Power Automate US Government](/power-automate/us-govt)
* [Power BI US Government Demosu](https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government)
