---
title: Power BI için Azure güvenlik temeli
description: Power BI güvenlik temeli, Azure Güvenlik Karşılaştırması'nda belirtilen güvenlik önerilerini uygulamaya yönelik yordamsal rehberlik ve kaynaklar sunar.
author: mbaldwin
ms.author: margoc
ms.service: powerbi
ms.subservice: pbi-security
ms.topic: conceptual
ms.date: 11/20/2020
ms.custom: subject-security-benchmark
ms.openlocfilehash: 04a971aa6d1e584866ff7740676ab35b2e0e17af
ms.sourcegitcommit: f7330dabb9cd8bce90bb2efec3e3273a11578f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99494892"
---
# <a name="azure-security-baseline-for-power-bi"></a>Power BI için Azure güvenlik temeli

Bu güvenlik temeli, [Azure Güvenlik Karşılaştırması 2.0](/azure/security/benchmarks/overview) sürümündeki rehberlik bilgilerini Power BI'a uygular. Azure Güvenlik Karşılaştırması, Azure üzerindeki bulut çözümlerinizin güvenliğini sağlamaya yönelik öneriler sunar. İçerik, Azure Güvenlik Karşılaştırması ile tanımlanan **güvenlik denetimlerine** ve Power BI için geçerli olan rehberlik bilgilerine göre gruplanmıştır. Power BI için geçerli olmayan **denetimler** kapsam dışı bırakılmıştır.

Power BI'ın Azure Güvenlik Karşılaştırması ile tam olarak nasıl eşleştiğini görmek için [tam kapsamlı Power BI güvenlik temeli eşleştirme dosyasını](https://github.com/MicrosoftDocs/SecurityBenchmarks/tree/master/Azure%20Offer%20Security%20Baselines) inceleyin.

## <a name="network-security"></a>Ağ Güvenliği

*Daha fazla bilgi için bkz. [Azure Güvenlik Karşılaştırması: Ağ Güvenliği](/azure/security/benchmarks/security-controls-v2-network-security).*

### <a name="ns-3-establish-private-network-access-to-azure-services"></a>NS-3: Azure hizmetlerine özel ağ erişimi sağlayın

**Rehberlik**: Power BI, kiracınızı Özel bağlantı uç noktasına bağlayıp genel internet erişimini devre dışı bırakma senaryosunu destekler.

- [Power BI’a erişmek için özel bağlantılar](../admin/service-security-private-links.md)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Paylaşılan

## <a name="identity-management"></a>Kimlik Yönetimi

*Daha fazla bilgi için bkz. [Azure Güvenlik Karşılaştırması: Kimlik Yönetimi](/azure/security/benchmarks/security-controls-v2-identity-management).*

### <a name="im-1-standardize-azure-active-directory-as-the-central-identity-and-authentication-system"></a>IM-1: Azure Active Directory'yi standart merkezi kimlik ve kimlik doğrulaması sistemi haline getirin

**Rehberlik**: Power BI, Azure'ın varsayılan kimlik ve erişim yönetimi hizmeti olan Azure Active Directory (Azure AD) ile tümleşik olarak çalışır. Kuruluşunuzun kimlik ve erişim yönetim süreçlerini idare etmek için Azure AD'yi standartlaştırmanız gerekir.

Azure AD'nin güvenliğini sağlamak, kuruluşunuzun güvenlik uygulamalarının yüksek öncelikli bileşenlerinden biri olmalıdır. Azure AD, kimlik güvenliği duruşunu Microsoft'un en iyi deneyim önerilerine göre değerlendirmenize yardımcı olmak için bir kimlik güvenliği puanı sağlar. Bu puanı kullanarak yapılandırmanızın en iyi deneyim önerileriyle ne kadar uyumlu olduğunu görebilir ve güvenlik duruşunuzda geliştirmeler yapabilirsiniz.

Not: Azure AD, dış kimlikleri destekler ve bu sayede Microsoft hesabı olmayan kullanıcılar uygulamalarında ve kaynaklarında dış kimliklerini kullanarak oturum açabilir.

- [Azure Active Directory'deki kiracılar](/azure/active-directory/develop/single-and-multi-tenant-apps)

- [Azure AD örneği oluşturma ve yapılandırma](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

- [Uygulama için dış kimlik sağlayıcılarını kullanma](/azure/active-directory/b2b/identity-providers)

- [Azure Active Directory'deki kimlik güvenliği puanı nedir?](/azure/active-directory/fundamentals/identity-secure-score)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="im-2-manage-application-identities-securely-and-automatically"></a>IM-2: Uygulama kimliklerini güvenli ve otomatik bir şekilde yönetin

**Rehberlik**: Power BI ve Power BI Embedded, Hizmet Sorumlusu kullanımını destekler. Şifreleme veya Power BI erişimi için kullanılan Hizmet Sorumlusu kimlik bilgilerini bir anahtar kasasında depolayın, kasaya uygun erişim ilkelerini atayın ve erişim izinlerini düzenli olarak gözden geçirin.

Hizmet sorumlularıyla Premium çalışma alanı ve veri kümesi görevlerini otomatikleştirme https://docs.microsoft.com/power-bi/admin/service-premium-service-principal

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="im-3-use-azure-ad-single-sign-on-sso-for-application-access"></a>IM-3: Uygulama erişimi için Azure AD çoklu oturum açma (SSO) özelliğini kullanın

**Rehberlik**: Power BI; Azure kaynaklarına, bulut uygulamalarına ve şirket içi uygulamalara yönelik kimlik ve erişim yönetimi sağlamak için Azure Active Directory'yi kullanır. Buna çalışanlar gibi kuruluş kimliklerinin yanı sıra iş ortakları, satıcılar ve tedarikçiler gibi dış kimlikler de dahildir. Bu seçenek, kuruluşunuzun şirket içi ortamda ve bulutta bulunan verilerini ve kaynaklarını yönetip bunlara güvenli erişim sağlamak için çoklu oturum açma (SSO) özelliğinin kullanılmasını sağlar. Tüm kullanıcılarınızı, uygulamalarınızı ve cihazlarınızı Azure AD'ye bağlayarak sorunsuz ve güvenli erişimin yanı sıra daha fazla görünürlük ve denetim elde edebilirsiniz.

- [Azure AD ile uygulamalar için SSO yaklaşımını anlama](/azure/active-directory/manage-apps/what-is-single-sign-on)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="im-4-use-strong-authentication-controls-for-all-azure-active-directory-based-access"></a>IM-4: Tüm Azure Active Directory tabanlı erişim girişimleri için güçlü kimlik doğrulaması denetimleri kullanın

**Rehberlik**: Power BI çok faktörlü kimlik doğrulaması (MFA) ve güçlü parolasız yöntemler aracılığıyla güçlü kimlik doğrulaması denetimlerini destekleyen Azure AD ile tümleşik bir şekilde çalışır.
- Çok faktörlü kimlik doğrulaması: Azure AD çok faktörlü kimlik doğrulaması özelliğini etkinleştirin ve çok faktörlü kimlik doğrulaması ayarlarınızla ilgili en iyi deneyimlere yönelik Azure Güvenlik Merkezi Kimlik ve Erişim Yönetimi önerilerini izleyin. Çok faktörlü kimlik doğrulaması tüm kullanıcılara, yalnızca belirli kullanıcılara veya oturum açma koşullarıyla risk faktörlerine göre kullanıcı düzeyinde uygulanabilir.
- Parolasız kimlik doğrulaması: Üç farklı parolasız kimlik doğrulaması seçeneği vardır: İş İçin Windows Hello, Microsoft Authenticator uygulaması ve akıllı kart gibi şirket içi kimlik doğrulama yöntemleri.

Yöneticiler ve ayrıcalıklı kullanıcılar için en üst düzey güçlü kimlik doğrulaması yöntemlerinin kullanıldığından emin olun ve diğer kullanıcılar için de uygun güçlü kimlik doğrulaması ilkesini kullanıma alın.

Not: Çok faktörlü kimlik doğrulaması yalnızca Azure AD'de etkinleştirilen kullanıcı hesaplarına uygulanabilir. Power BI Hizmet Sorumluları, çok faktörlü kimlik doğrulaması kullanımını desteklemez.

- [Azure'da çok faktörlü kimlik doğrulamasını etkinleştirme](/azure/active-directory/authentication/howto-mfa-getstarted)

- [Azure Active Directory için parolasız kimlik doğrulaması seçeneklerine giriş](/azure/active-directory/authentication/concept-authentication-passwordless)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="im-5-monitor-and-alert-on-account-anomalies"></a>IM-5: Hesap anomalilerini izleyin ve uyarı oluşturun

**Rehberlik**: Microsoft Cloud App Security'de yalnızca dahil etmek istediğiniz kullanıcılar ve gruplar için geçerli olacak şekilde bağımsız kapsama sahip olabilecek anomali algılama ilkeleri tanımlayın. Bu anomali algılama ilkeleri, Power BI'a erişen ve bu hizmeti kullanan kullanıcılarla ilgili davranış anomalilerinin algılanmasına ve izlenmesine yardımcı olabilir.

- [Power BI’da Microsoft Cloud App Security denetimlerini kullanma](../admin/service-security-using-microsoft-cloud-app-security-controls.md)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="im-6-restrict-azure-resource-access-based-on-conditions"></a>IM-6: Azure kaynaklarına erişimi koşullara göre kısıtlayın

**Rehberlik**: Power BI, kullanıcı tanımlı koşullara göre daha ayrıntılı erişim denetimi sağlama amacıyla Azure AD koşullu erişim özelliğini destekler. Örneğin belirli IP aralıklarından oturum açmak isteyen kullanıcıların çok faktörlü kimlik doğrulaması kullanmasını zorunlu kılabilirsiniz. Ayrıntılı kimlik doğrulaması oturumu yönetim ilkesi farklı kullanım örneklerinde de kullanılabilir.

- [Azure'da koşullu erişime genel bakış](/azure/active-directory/conditional-access/overview)

- [Yaygın koşullu erişim ilkeleri](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

- [Koşullu erişimle kimlik doğrulama oturumu yönetimini yapılandırma](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)

- [Power BI’da Microsoft Cloud App Security denetimlerini kullanma](../admin/service-security-using-microsoft-cloud-app-security-controls.md)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="im-7-eliminate-unintended-credential-exposure"></a>IM-7: Kimlik bilgilerinin istenmeden açığa çıkma olasılığını ortadan kaldırın

**Rehberlik**: Power BI Embedded uygulamalarında kod içindeki kimlik bilgilerini tanımlamak için Kimlik Bilgisi Tarayıcısı kullanmanız önerilir. Kimlik Bilgisi Tarayıcısı ayrıca bulunan kimlik bilgilerinin Azure Key Vault gibi daha güvenlik konumlara aktarılmasını sağlar.

Şifreleme veya Power BI erişimi için kullanılan şifreleme anahtarlarını veya Hizmet Sorumlusu kimlik bilgilerini bir anahtar kasasında depolayın, kasaya uygun erişim ilkelerini atayın ve erişim izinlerini düzenli olarak gözden geçirin.
 
GitHub için yerel gizli dizi tarama özelliğini kullanarak kod içindeki kimlik bilgilerini veya diğer gizli dizileri bulabilirsiniz.

- [Power BI için kendi anahtarını getir şifrelemesi](../admin/service-encryption-byok.md)

 
Kimlik bilgilerini ayarlama
- [Tarayıcı](https://secdevtools.azurewebsites.net/helpcredscan.html) 

- [GitHub'da gizli dizi tarama](https://docs.github.com/github/administering-a-repository/about-secret-scanning)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Paylaşılan

## <a name="privileged-access"></a>Ayrıcalıklı Erişim

*Daha fazla bilgi için bkz. [Azure Güvenlik Karşılaştırması: Ayrıcalıklı Erişim](/azure/security/benchmarks/security-controls-v2-privileged-access).*

### <a name="pa-1-protect-and-limit-highly-privileged-users"></a>PA-1: Yüksek ayrıcalıklı kullanıcıları koruyun ve sınırlayın

**Rehberlik**: Riski azaltmak ve en düşük ayrıcalık prensibini uygulamak için sınırlı sayıda kullanıcıyı Power BI yöneticisi olarak atamanız önerilir. Bu ayrıcalıklı izinlere sahip kullanıcılar, kuruluşa ait tüm yönetim özelliklerine erişebilir ve bunları değiştirebilir. Genel yöneticiler, Microsoft 365 veya Azure Active Directory aracılığıyla Power BI hizmeti için de örtük yönetici haklarına sahiptir.

Power BI'daki yüksek ayrıcalıklı hesaplar şunlardır:
- Genel yönetici
- Faturalama yöneticisi
- Lisans yöneticisi
- Kullanıcı yöneticisi
- Power BI yöneticisi
- Power BI Premium Kapasitesi yöneticisi
- Power BI Embedded Kapasitesi yöneticisi

Power BI, koşullu erişim ilkelerini etkinleştirmek ve Power BI'da kullanılan oturumları Cloud App Security hizmeti aracılığıyla yönlendirmek için Azure AD oturum ilkelerini destekler.

M365 ayrıcalıklı erişim yönetimini kullanarak Power BI yönetici hesapları için tam zamanında (JIT) ayrıcalıklı erişimi etkinleştirin.

- [Power BI ile ilgili yönetici rolleri](../admin/service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi)

- [M365 Ayrıcalıklı Erişim Yönetimi](/microsoft-365/compliance/privileged-access-management-overview?view=o365-worldwide&preserve-view=true)

- [Power BI’daki Cloud App Security denetimleri](../admin/service-security-using-microsoft-cloud-app-security-controls.md)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="pa-2-restrict-administrative-access-to-business-critical-systems"></a>PA-2: İş açısından kritik sistemlere yönetici erişimini kısıtlayın

**Rehberlik**: Power BI'a yükseltilmiş erişim sahibi olan yüksek ayrıcalıklı hesap veya rol sayısını sınırlayın.

[Buradaki](/microsoft-365/compliance/privileged-access-management-overview?view=o365-worldwide&preserve-view=true) M365 ayrıcalıklı erişim yönetimi rehberliğini kullanarak tam zamanında (JIT) ayrıcalıklı erişim sağlayabilirsiniz.

[Buradaki](https://aka.ms/PBIEnterpriseDeploymentWP) Power BI Kuruluş Dağıtımı belgesinin 183. sayfasında daha fazla bilgiye ulaşabilirsiniz.

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="pa-3-review-and-reconcile-user-access-regularly"></a>PA-3: Kullanıcı erişimini düzenli olarak gözden geçirin ve mutabık kılın

**Rehberlik**: Power BI hizmeti yöneticisi olarak, Power BI etkinlik günlüğüne dayalı özel raporları kullanarak tüm Power BI kaynakları için kiracı düzeyinde kullanımı analiz edebilirsiniz. REST API veya PowerShell cmdlet'i kullanarak etkinlikleri indirebilirsiniz. Ayrıca etkinlik verilerini tarih aralığına, kullanıcıya ve etkinlik türüne göre filtreleyebilirsiniz.

Power BI etkinlik günlüğüne erişmek için şu gereksinimleri karşılamanız gerekir:
- Genel yönetici veya Power BI hizmeti yöneticisi olmalısınız.
- [Power BI Yönetim cmdlet'lerini](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt) yerel olarak yüklediniz veya Azure Cloud Shell'de Power BI Yönetim cmdlet'lerini kullandınız.

Bu gereksinimler karşılandıktan sonra Power BI içindeki kullanıcı etkinliğini izlemek için aşağıdaki rehberliği izleyebilirsiniz:

- [Power BI'daki kullanıcı etkinliğini izleme](../admin/service-admin-auditing.md)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="pa-4-set-up-emergency-access-in-azure-ad"></a>PA-4: Azure AD'de acil durum erişimini ayarlayın

**Rehberlik**: Power BI, kaynak yönetimi açısından Azure Active Directory ve M365 ile tümleşik olarak çalışır. M365 kiracınızın veya Azure AD kuruluşunuzun yanlışlıkla kilitlenmesini önlemek için normal yönetici hesapları kullanılamadığında erişim için kullanabileceğiniz bir acil durum erişim hesabı ayarlayın. Acil durum erişim hesapları genellikle yüksek ayrıcalığa sahiptir ve herhangi bir kişiye atanmamalıdır. Acil durum erişim hesaplarının kullanım alanı, normal yönetici hesaplarının kullanılamadığı acil veya "camı kırın" senaryolarıyla sınırlıdır.

Acil durum erişim hesaplarının kimlik bilgilerinin (parola, sertifika veya akıllı kart) güvenli bir şekilde saklandığından ve yalnızca acil bir durumda bunları kullanma yetkisine sahip olan kullanıcılar tarafından bilindiğinden emin olmanız gerekir.

- [Azure AD'deki acil durum erişim hesaplarını yönetme](/azure/active-directory/users-groups-roles/directory-emergency-access)

- [M365 hesaplarınızı koruma](/microsoft-365/campaigns/m365-campaigns-protect-admin-accounts)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="pa-6-use-privileged-access-workstations"></a>PA-6: Ayrıcalıklı erişim iş istasyonlarını kullanın

**Rehberlik**: Güvenli ve yalıtılmış iş istasyonları yöneticiler, geliştiriciler ve kritik hizmet operatörleri gibi hassas rollerin güvenliği açısından kritik öneme sahiptir. Power BI yönetimiyle ilgili görevler için yüksek güvenlikli kullanıcı iş istasyonlarını ve/veya Azure Bastion hizmetini kullanın. Yönetim görevlerine yönelik güvenli ve yönetilen bir kullanıcı iş istasyonu dağıtmak için Azure Active Directory, Microsoft Defender Gelişmiş Tehdit Koruması (ATP) ve/veya Microsoft Intune hizmetlerini kullanın. Güvenli iş istasyonları güçlü kimlik doğrulaması, yazılım ve donanım temelleri, kısıtlı mantıksal erişim ve ağ erişimi gibi güvenli yapılandırma özelliklerinin uygulanması için merkezi olarak yönetilebilir.

Ayrıcalıklı erişimi anlama
- [İş istasyonları](https://4sysops.com/archives/understand-the-microsoft-privileged-access-workstation-paw-security-model/)

- [Ayrıcalıklı erişim iş istasyonu dağıtma](/azure/active-directory/devices/howto-azure-managed-workstation)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

## <a name="data-protection"></a>Veri Koruma

*Daha fazla bilgi için bkz. [Azure Güvenlik Karşılaştırması: Veri Koruma](/azure/security/benchmarks/security-controls-v2-data-protection).*

### <a name="dp-1-discovery-classify-and-label-sensitive-data"></a>DP-1: Hassas verileri bulun, sınıflandırın ve etiketleyin

**Rehberlik**: Hassas içeriklerinizi yetkisiz veri erişimi ve sızıntılara karşı korumak için rapor, pano, veri kümesi ve veri akışlarınızda Microsoft Information Protection duyarlılık etiketlerini kullanın.

Microsoft Information Protection duyarlılık etiketlerini kullanarak Power BI hizmetindeki raporlarınızı, panolarınızı, veri kümelerinizi ve veri akışlarınızı sınıflandırabilir ve etiketleyebilirsiniz. Bu sayede Power BI hizmetinden Excel'e, PowerPoint'e ve PDF dosyalarına aktarılan hassas içeriklerinizi yetkisiz veri erişimine ve sızıntılara karşı koruyabilirsiniz.

- [Power BI'da duyarlılık etiketlerini uygulama](../admin/service-security-apply-data-sensitivity-labels.md)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="dp-2-protect-sensitive-data"></a>DP-2: Hassas verileri koruyun

**Rehberlik**: Power BI, hassas veri koruması için Microsoft Information Protection duyarlılık etiketleriyle tümleşik olarak çalışır. Ayrıntılı bilgi için bkz. [Power BI'daki Microsoft Information Protection duyarlılık etiketleri](../admin/service-security-sensitivity-label-overview.md)

Power BI, hizmet kullanıcılarının bekleyen veriler için kendi anahtarlarını getirmelerine olanak tanır. Ayrıntılı bilgi için bkz. [Power BI için kendi anahtarını getir şifrelemesi](../admin/service-encryption-byok.md)

Müşteriler, veri kaynaklarını şirket içi ortamda tutup şirket içi veri ağ geçidiyle DirectQuery veya Live Connect hizmetlerini kullanarak bulut hizmetine sunulan veri miktarını en aza indirebilir. Ayrıntılı bilgi için bkz. [Şirket içi veri ağ geçidi nedir?](/data-integration/gateway/service-gateway-onprem)

Power BI, satır düzeyi güvenlik desteği sunar. Ayrıntılı bilgi için bkz. [Power BI ile satır düzeyi güvenlik (RLS)](../admin/service-admin-rls.md). Satır düzeyi güvenliğin DirectQuery veri kaynaklarına dahi uygulanabileceğini unutmayın. Bu durumda PBIX dosyası, güvenlik sağlayan ara sunucu görevi görür.

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="dp-3-monitor-for-unauthorized-transfer-of-sensitive-data"></a>DP-3: Yetkisiz hassas veri aktarımını izleyin

**Rehberlik**: Bu denetim, Power BI için Microsoft Cloud App Security desteği kullanılarak kısmen sağlanabilir.

Power BI ile Cloud App Security’yi kullanarak Power BI raporlarınızı, verilerinizi ve hizmetlerinizi istenmeyen sızıntı veya ihlallerden korumaya yardımcı olabilirsiniz. Cloud App Security sayesinde, Azure Active Directory’deki (Azure AD) gerçek zamanlı oturum denetimlerini kullanarak kuruluşunuzun verileri için Power BI analizlerinin güvenli olmasına yardımcı olacak koşullu erişim ilkeleri oluşturabilirsiniz. Bu ilkeler ayarlandıktan sonra yöneticiler kullanıcı erişimini ve etkinliğini izleyebilir, gerçek zamanlı risk analizi gerçekleştirebilir ve etikete özel denetimler belirleyebilir.

Kullanma
- [Power BI'daki Microsoft Cloud App Security denetimleri](../admin/service-security-using-microsoft-cloud-app-security-controls.md)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="dp-4-encrypt-sensitive-information-in-transit"></a>DP-4: Hassas bilgileri aktarım sırasında şifreleyin

**Rehberlik**: HTTP trafiği için Power BI kaynaklarınıza bağlanan istemcilerin ve veri kaynaklarının TLS v1.2 veya üzeri ile anlaşabildiğinden emin olun.

- [TLS sürümü kullanımını zorlama](../admin/service-admin-power-bi-security.md#enforcing-tls-version-usage)

- [TLS güvenliği hakkında bilgi](/security/engineering/solving-tls1-problem)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="dp-5-encrypt-sensitive-data-at-rest"></a>DP-5: Bekleyen hassas verileri şifreleyin

**Rehberlik**: Power BI bekleyen ve işlenmekte olan verileri şifreler. Varsayılan olarak Power BI verilerinizi şifrelemek için Microsoft tarafından yönetilen anahtarları kullanır. Kuruluşlar, rapor görüntülerinden Premium kapasitelere içeri aktarılan veri kümelerine, Power BI’daki bekleyen kullanıcı içeriklerini şifrelemek için kendi anahtarlarını kullanmayı tercih edebilir.

- [Power BI'da kendi anahtarını getir senaryosunu kullanma](../admin/service-encryption-byok.md)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Paylaşılan

## <a name="asset-management"></a>Varlık Yönetimi

*Daha fazla bilgi için bkz. [Azure Güvenlik Karşılaştırması: Varlık Yönetimi](/azure/security/benchmarks/security-controls-v2-asset-management).*

### <a name="am-1-ensure-security-team-has-visibility-into-risks-for-assets"></a>AM-1: Güvenlik ekibinin varlıklarla ilgili riskleri görebildiğinden emin olun

**Rehberlik**: Güvenlik ekibinizin Power BI varlıklarınızla ilgili riskleri görebildiğinden emin olmak için Azure Sentinel'i ve Power BI Office Denetim günlüklerinizi kullanın.

- [Office 365 günlüklerini Azure Sentinel'e bağlama](/azure/sentinel/connect-office-365)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="am-2-ensure-security-team-has-access-to-asset-inventory-and-metadata"></a>AM-2: Güvenlik ekibinin varlık envanterine ve meta verilerine erişebildiğinden emin olun

**Rehberlik**: Güvenlik ekiplerinin Power BI Embedded kaynaklarının sürekli güncelleştirilen envanterine erişim sahibi olduğundan emin olun. Güvenlik ekipleri genellikle kuruluşlarının ortaya çıkabilecek risklerden olası etkilenme durumunu değerlendirmek ve sürekli güvenlik geliştirmelerine yönelik giriş sağlamak için bu envantere ihtiyaç duyar. 

Azure Kaynak Grafı, aboneliklerinizdeki tüm Power BI Embedded kaynaklarını sorgulayabilir ve bulabilir.  

Azure'daki etiketleri ve diğer meta verileri (ad, açıklama ve kategori) kullanarak varlıkları kuruluşunuzun sınıflandırma uygulamalarına göre mantıksal olarak düzenleyin.  

- [Azure Kaynak Grafı Gezgini ile sorgu oluşturma](/azure/governance/resource-graph/first-query-portal)

- [Kaynak adlandırma ve etiketleme kararı kılavuzu](/azure/cloud-adoption-framework/decision-guides/resource-tagging/?toc=%2fazure%2fazure-resource-manager%2fmanagement%2ftoc.json)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="am-3-use-only-approved-azure-services"></a>AM-3: Yalnızca onaylı Azure hizmetlerini kullanın

**Rehberlik**: Power BI, Power BI Embedded için Azure Resource Manager tabanlı dağıtımları destekler. Azure İlkesi ile özel bir ilke tanımı kullanarak kaynak kısıtlayabilirsiniz.

Kullanıcılarınızın ortamınızda sağlayabileceği hizmetleri denetlemek ve kısıtlamak için Azure İlkesi'ni kullanın. Abonelikler içindeki kaynakları sorgulamak ve bulmak için Azure Kaynak Grafı'nı kullanın. Ayrıca Azure İzleyici'yi kullanarak onaylanmamış hizmetler algılandığında uyarı tetikleme amacıyla kurallar oluşturabilirsiniz.

- [Azure İlkesi'ni yapılandırma ve yönetme](/azure/governance/policy/tutorials/create-and-manage)

Belirli bir kaynak türünü reddetme
- [Azure İlkesi](/azure/governance/policy/samples/built-in-policies#general)

Azure ile sorgu oluşturma
- [Kaynak Grafı Gezgini](/azure/governance/resource-graph/first-query-portal)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

## <a name="logging-and-threat-detection"></a>Günlüğe Kaydetme ve Tehdit Algılama

*Daha fazla bilgi için bkz. [Azure Güvenlik Karşılaştırması: Günlüğe Kaydetme ve Tehdit Algılama](/azure/security/benchmarks/security-controls-v2-logging-threat-detection).*

### <a name="lt-2-enable-threat-detection-for-azure-identity-and-access-management"></a>LT-2: Azure kimlik ve erişim yönetimi için tehdit algılamayı etkinleştirin

**Rehberlik**: Power BI günlüklerini SIEM çözümünüze ileterek özel tehdit algılama senaryoları oluşturabilirsiniz. Ayrıca [buradaki](../admin/service-security-using-microsoft-cloud-app-security-controls.md) kılavuzu kullanarak Power BI'daki Microsoft Cloud App Security (MCAS) denetimlerinden faydalanabilir, bu sayede anomali algılamayı etkinleştirebilirsiniz.

- [Power BI'da kullanıcı etkinliklerini izleme](../admin/service-admin-auditing.md)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="lt-3-enable-logging-for-azure-network-activities"></a>LT-3: Azure ağ etkinlikleri için günlüğe kaydetmeyi etkinleştirin

**Rehberlik**: Power BI, tam olarak yönetilen bir SaaS teklifidir ve temel alınan ağ yapılandırması ile günlüğe kaydetme görevleri Microsoft'un sorumluluğundadır. Özel Bağlantıları kullanan müşterilere yönelik günlüğe kaydetme ve izleme yapılandırması sunulur.

- [Özel Bağlantı ile günlüğe kaydetme ve izleme](/azure/private-link/private-link-overview#logging-and-monitoring)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Paylaşılan

### <a name="lt-4-enable-logging-for-azure-resources"></a>LT-4: Azure kaynakları için günlüğe kaydetmeyi etkinleştirin

**Rehberlik**: Power BI'la kullanıcı etkinliğini izlemek için iki seçeneğiniz vardır: Power BI etkinlik günlüğü ve birleşik denetim günlüğü. Bu günlüklerin her ikisi de Power BI denetim verilerinin eksiksiz bir kopyasını içerir ancak aşağıda özetlendiği gibi bazı önemli farklılıklar vardır.
 
Birleşik Denetim Günlüğü:

 
- Power BI denetim olaylarına ek olarak SharePoint Online, Exchange Online, Dynamics 365 ve diğer hizmetlerden olayları içerir.

 
- Yalnızca genel yöneticiler ve denetçiler gibi Yalnızca Görüntülenebilir Denetim Günlükleri ve Denetim Günlükleri izinleri olan kullanıcılar erişebilir.

 
- Genel yöneticiler ve denetçiler Microsoft 365 Güvenlik Merkezi'ni ve Microsoft 365 Uyumluluk Merkezi'ni kullanarak birleşik denetim günlüğünde arama yapabilir.

 
- Genel yöneticiler ve denetçiler Microsoft 365 Yönetim API’lerini ve cmdlet’leri kullanarak denetim günlüğü girişlerini indirebilir.

 
- Denetim verilerini 90 gün süreyle tutar.

 
- Kiracı farklı bir Azure bölgesine taşınsa bile denetim verilerini korur.
 
Power BI Etkinlik Günlüğü:

 
- Yalnızca Power BI denetim olaylarını içerir.

 
 
- Genel yöneticilerin ve Power BI hizmeti yöneticilerinin erişimi vardır.

 
- Henüz etkinlik günlüğünde arama yapmaya yönelik kullanıcı arabirimi yoktur.

 
- Genel yöneticiler ve Power BI hizmeti yöneticileri Power BI REST API'sini ve yönetim cmdlet'ini kullanarak etkinlik günlüğü girdilerini indirebilir.

 
- Etkinlik verilerini 30 gün süreyle tutar.

 
- Kiracı farklı bir Azure bölgesine taşındığında etkinlik verilerini korumaz.

- [Power BI Denetim Verileri](../admin/service-admin-auditing.md#operations-available-in-the-audit-and-activity-logs)

- [Power BI Etkinlik Günlüğü](../admin/service-admin-auditing.md#use-the-activity-log)

- [Power BI Denetim Günlüğü](../admin/service-admin-auditing.md#use-the-audit-log)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Paylaşılan

### <a name="lt-5-centralize-security-log-management-and-analysis"></a>LT-5: Güvenlik günlüğü yönetim ve analiz süreçlerini merkezileştirin

**Rehberlik**: Power BI, günlükleri iki konumda merkezileştirir: Power BI etkinlik günlüğü ve birleşik denetim günlüğü. Bu günlüklerin her ikisi de Power BI denetim verilerinin eksiksiz bir kopyasını içerir ancak aşağıda özetlendiği gibi bazı önemli farklılıklar vardır.
 

Birleşik Denetim Günlüğü:

- Power BI denetim olaylarına ek olarak SharePoint Online, Exchange Online, Dynamics 365 ve diğer hizmetlerden olayları içerir.

- Yalnızca genel yöneticiler ve denetçiler gibi Yalnızca Görüntülenebilir Denetim Günlükleri ve Denetim Günlükleri izinleri olan kullanıcılar erişebilir.

- Genel yöneticiler ve denetçiler Microsoft 365 Güvenlik Merkezi'ni ve Microsoft 365 Uyumluluk Merkezi'ni kullanarak birleşik denetim günlüğünde arama yapabilir.

- Genel yöneticiler ve denetçiler Microsoft 365 Yönetim API’lerini ve cmdlet’leri kullanarak denetim günlüğü girişlerini indirebilir.

- Denetim verilerini 90 gün süreyle tutar.

- Kiracı farklı bir Azure bölgesine taşınsa bile denetim verilerini korur.

 

Power BI Etkinlik Günlüğü:

- Yalnızca Power BI denetim olaylarını içerir.

- Genel yöneticilerin ve Power BI hizmeti yöneticilerinin erişimi vardır.

- Henüz etkinlik günlüğünde arama yapmaya yönelik kullanıcı arabirimi yoktur.

- Genel yöneticiler ve Power BI hizmeti yöneticileri Power BI REST API'sini ve yönetim cmdlet'ini kullanarak etkinlik günlüğü girdilerini indirebilir.

- Etkinlik verilerini 30 gün süreyle tutar.

- Kiracı farklı bir Azure bölgesine taşındığında etkinlik verilerini korumaz.

- [Power BI Denetim Verileri](../admin/service-admin-auditing.md#operations-available-in-the-audit-and-activity-logs)

- [Power BI Etkinlik Günlüğü](../admin/service-admin-auditing.md#use-the-activity-log)

- [Power BI Denetim Günlüğü](../admin/service-admin-auditing.md#use-the-audit-log)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="lt-6-configure-log-storage-retention"></a>LT-6: Günlük depolama alanının saklama süresini yapılandırın

**Rehberlik**: Office denetim günlüklerine yönelik depolama alanı saklama süresini uyumluluk, düzenleme ve iş gereksinimleriniz doğrultusunda yapılandırın.

- [Office Denetim Günlüğü Saklama İlkeleri](/microsoft-365/compliance/audit-log-retention-policies)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

## <a name="incident-response"></a>Olay Yanıtı

*Daha fazla bilgi için bkz. [Azure Güvenlik Karşılaştırması: Olay Yanıtı](/azure/security/benchmarks/security-controls-v2-incident-response).*

### <a name="ir-1-preparation--update-incident-response-process-for-azure"></a>IR-1: Hazırlık: Azure için olay yanıtı sürecini güncelleştirin

**Rehberlik**: Kuruluşunuzda güvenlik olaylarına yanıt vermeye yönelik süreçler bulunduğundan, bu süreçlerin Azure için güncelleştirildiğinden ve hazır olduğunuzdan emin olmak için bu süreçlerin düzenli olarak uygulandığından emin olun.

- [Güvenliği kuruluş genelinde uygulama](/azure/cloud-adoption-framework/security/security-top-10#4-process-update-incident-response-ir-processes-for-cloud)

- [Olay yanıtı başvuru kılavuzu](/microsoft-365/downloads/IR-Reference-Guide.pdf)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="ir-2-preparation--setup-incident-notification"></a>IR-2: Hazırlık: Olay bildirimini ayarlayın

**Rehberlik**: Azure Güvenlik Merkezi'nde güvenlik olayı iletişim bilgilerini ayarlayın. Microsoft, Microsoft Güvenlik Yanıt Merkezi'nin (MSRC) verilerinize kanuna aykırı veya yetkisiz erişim sağlanmasını keşfetmesi durumunda sizinle iletişime geçmek için bu iletişim bilgilerini kullanır. İsterseniz farklı Azure hizmetlerindeki olay uyarılarını ve bildirimlerini olay yanıt gereksinimlerinize göre özelleştirebilirsiniz. 

- [Azure Güvenlik Merkezi güvenlik ilgili kişisini ayarlama](/azure/security-center/security-center-provide-security-contact-details)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="ir-3-detection-and-analysis--create-incidents-based-on-high-quality-alerts"></a>IR-3: Algılama ve analiz: Yüksek kaliteli uyarıları temel alan olaylar oluşturun

**Rehberlik**: Yüksek kaliteli uyarılar oluşturmaya ve uyarıların kalitesini ölçmeye yönelik bir sürece sahip olduğunuzdan emin olun. Bu sayede önceki olaylardan dersler çıkarabilir ve analistler için uyarıları önceliklendirebilirsiniz. Bu sayede hatalı pozitif sonuçlarla zaman kaybetmelerini önlemiş olursunuz.

Microsoft Cloud App Security'de Power BI ile ilgili uyarıları izleyin. Yüksek kaliteli uyarılar önceki olaylardan alınan dersler, doğrulanmış topluluk kaynakları ve farklı sinyal kaynaklarını birleştirip bağlantı oluşturarak uyarı oluşturmaya ve temizlemeye yönelik araçlar kullanılarak geliştirilebilir.

- [Cloud App Security'deki uyarıları izleme](/cloud-app-security/monitor-alerts)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="ir-4-detection-and-analysis--investigate-an-incident"></a>IR-4: Algılama ve analiz: Olay araştırması

**Rehberlik**: Kuruluşunuz için bir olay yanıt kılavuzu oluşturun. Sistemlerinizin olay yanıt özelliklerini test etmek için düzenli alıştırmalar yapın. Zayıf noktaları ve açıkları belirleyip planı gerektiği şekilde gözden geçirin.

Tüm personelin rollerine ek olarak algılama aşamasından olay sonrası gözden geçirme aşamasına kadar tüm olay işleme/yönetim aşamalarını tanımlayan yazılı olay yanıt planları bulunduğundan emin olun.

- [Microsoft Tehdit Koruması'nda olaylara genel bakış](/microsoft-365/security/mtp/incidents-overview)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="ir-5-detection-and-analysis--prioritize-incidents"></a>IR-5: Algılama ve analiz: Olayları önceliklendirin

**Rehberlik**: Uyarı önem derecesine ve varlık duyarlığına göre analistlere öncelikli olarak odaklanmaları gereken olaylar hakkında bağlam bilgisi sağlayın. 

 
Microsoft Tehdit Koruması, bağıntı analizi gerçekleştirir ve farklı ürünlerdeki tüm uyarıları ve araştırmaları tek bir olay altında toplar. Microsoft Tehdit Koruması ayrıca tüm varlıklar ve ürünler genelinde sahip olduğu uçtan uca görünürlük sayesinde ancak kötü amaçlı olarak tanımlanabilecek etkinliklerle ilgili benzersiz uyarıları da tetikler. Microsoft Tehdit Koruması bu şekilde daha geniş kapsamlı bir saldırı hikayesi oluşturarak güvenlik operasyonları analistlerinin kuruluş genelindeki karmaşık tehditleri anlamasını ve gidermesini sağlar.

- [Microsoft Tehdit Koruması'nda olayları önceliklendirme](/microsoft-365/security/mtp/incident-queue?view=o365-worldwide&preserve-view=true)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="ir-6-containment-eradication-and-recovery--automate-the-incident-handling"></a>IR-6: Kapsama, ortadan kaldırma ve kurtarma: Olay işleme sürecini otomatikleştirin

**Rehberlik**: Yanıt süresini kısaltmak ve analistlerin yükünü hafifletmek için el ile yapılan yinelenen görevleri otomatikleştirin. El ile gerçekleştirilen görevlerin yürütülmesi daha uzun sürer ve olay yanıt sürecini yavaşlatarak analistlerin işleyebileceği olay sayısını azaltır. El ile gerçekleştirilen görevler ayrıca analistlerin daha çabuk yorulmasına neden olarak insan kaynaklı hatalar nedeniyle sürecin uzamasına neden olur ve analistin karmaşık görevlere etkili bir şekilde odaklanmasını engeller.  
 
Gelen güvenlik uyarılarına yanıt olarak araştırma ve düzeltme süreçlerini otomatik olarak tetiklemek için Microsoft Tehdit Koruması'ndaki iş akışı otomasyon özelliklerini kullanın. 
 
- [Microsoft Tehdit Koruması'ndaki otomatik araştırma ve yanıt özellikleri](/microsoft-365/security/mtp/mtp-autoir)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

## <a name="posture-and-vulnerability-management"></a>Duruş ve Güvenlik Açığı Yönetimi

*Daha fazla bilgi için bkz. [Azure Güvenlik Karşılaştırması: Duruş ve Güvenlik Açığı Yönetimi](/azure/security/benchmarks/security-controls-v2-posture-vulnerability-management).*

### <a name="pv-1-establish-secure-configurations-for-azure-services"></a>PV-1: Azure hizmetleri için güvenli yapılandırmalar oluşturun 

**Rehberlik**: Power BI hizmetinizi kuruluşunuza ve güvenlik duruşunuza uygun ayarlarla yapılandırın. Hizmet ve içerik erişimine ek olarak çalışma alanı ve uygulama güvenliği ayarları dikkatli bir şekilde incelenmelidir. Power BI Kuruluş Dağıtımı teknik incelemesinin Power BI Güvenliği ve Veri Koruma bölümüne bakın.

- [Kuruluş Dağıtımı Teknik İncelemesi](https://aka.ms/PBIEnterpriseDeploymentWP)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="pv-2-sustain-secure-configurations-for-azure-services"></a>PV-2: Azure hizmetleri için güvenli yapılandırmaların sürekliliğini sağlayın

**Rehberlik**: Power BI yönetimi REST API'lerini kullanarak Power BI örneğinizi izleyin.

- [Power BI yönetimi REST API'leri](/rest/api/power-bi/admin)

- [Power BI kuruluş dağıtımı teknik incelemesi](https://aka.ms/PBIEnterpriseDeploymentWP)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="pv-8-conduct-regular-attack-simulation"></a>PV-8: Düzenli aralıklarla saldırı simülasyonları yapın

**Rehberlik**: Gerektiğinde Azure kaynaklarınızda sızma testi veya kırmızı takım etkinlikleri gerçekleştirerek tüm kritik güvenlik bulgularının düzeltilmesini sağlayın.

Sızma testlerinizin Microsoft ilkelerini ihlal etmediğinden emin olmak için Microsoft Bulut Sızma Testi Etkileşim Kuralları'na uygun hareket edin. Microsoft tarafından yönetilen bulut altyapısına, hizmetlere ve uygulamalara yönelik kırmızı takım ve canlı site sızma testi gerçekleştirmek için Microsoft'un stratejisini ve yürütme sürecini kullanın.

- [Azure'da sızma testi yapma](/azure/security/fundamentals/pen-testing)

- [Sızma Testi Etkileşim Kuralları](https://www.microsoft.com/msrc/pentest-rules-of-engagement?rtc=1)

- [Microsoft Bulut ile Kırmızı Takım Oluşturma](https://gallery.technet.microsoft.com/Cloud-Red-Teaming-b837392e)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Paylaşılan

## <a name="backup-and-recovery"></a>Yedekleme ve Kurtarma

*Daha fazla bilgi için bkz. [Azure Güvenlik Karşılaştırması: Yedekleme ve Kurtarma](/azure/security/benchmarks/security-controls-v2-backup-recovery).*

### <a name="br-3-validate-all-backups-including-customer-managed-keys"></a>BR-3: Müşteri tarafından yönetilen anahtarlar dahil olmak üzere tüm yedeklemeleri doğrulayın

**Rehberlik**: Power BI'ın Kendi Anahtarını Getir (BYOK) özelliğini kullanıyorsanız müşteri tarafından yönetilen anahtarlarınıza erişebildiğinizi ve bunları geri yükleyebildiğinizi düzenli olarak doğrulamanız gerekir.

- [Power BI'da KAG](../admin/service-encryption-byok.md)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="br-4-mitigate-risk-of-lost-keys"></a>BR-4: Kayıp anahtar riskini azaltma

**Rehberlik**: Power BI'ın Kendi Anahtarını Getir (BYOK) özelliğini kullanıyorsanız müşteri tarafından yönetilen anahtarlarınızı denetleyen anahtar kasasının aşağıdaki Power BI'da KAG belgesine uygun şekilde yapılandırıldığından emin olmanız gerekir. Anahtarları yanlışlıkla veya kötü amaçlı olarak silinmeye karşı korumak için Azure Key Vault'ta geçici silme ve temizleme koruması özelliklerini etkinleştirin.

- [Power BI'da KAG](../admin/service-encryption-byok.md)

- [Key Vault'ta geçici silme ve temizleme koruması özelliklerini etkinleştirme](/azure/storage/blobs/storage-blob-soft-delete?tabs=azure-portal)

Ağ geçidi anahtar kaynakları için aşağıdaki ağ geçidi kurtarma anahtarı belgelerindeki yönlendirmeleri izlediğinizden emin olun.

- [Şirket içi veri ağ geçidi kurtarma anahtarı](/data-integration/gateway/service-gateway-recovery-key)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

## <a name="governance-and-strategy"></a>İdare ve Strateji

*Daha fazla bilgi için bkz. [Azure Güvenlik Karşılaştırması: İdare ve Strateji](/azure/security/benchmarks/security-controls-v2-governance-strategy).*

### <a name="gs-1-define-asset-management-and-data-protection-strategy"></a>GS-1: Varlık yönetimi ve veri koruma stratejisi tanımlayın 

**Rehberlik**: Sistemlerin ve verilerin sürekli izlenmesine ve korunmasına yönelik net bir strateji belgelendirdiğinizden ve paylaştığınızdan emin olun. İş açısından kritik verilerin ve sistemlerin bulma, değerlendirme, koruma ve izleme süreçleri için öncelik belirleyin. 

Bu strateji kapsamında aşağıdaki öğeler için rehberlik, ilkeler ve standartlar belgelenmiş olmalıdır: 

-   İş risklerine göre veri sınıflandırma standardı

-   Riskler ve varlık envanteriyle ilgili güvenlik kuruluşu görünürlüğü 

-   Güvenlik kuruluşunun kullanılmasını onayladığı Azure hizmetleri 

-   Varlıkların yaşam döngüsü boyunca güvenliği

-   Kuruluşun veri sınıflandırmasına uygun gerekli erişim denetimi stratejisi

-   Yerel Azure ve üçüncü taraf veri koruma özelliklerinin kullanılması

-   Taşıma durumundaki ve bekleyen veriler için şifreleme gereksinimleri

-   Uygun şifreleme standartları

Daha fazla bilgi için aşağıdaki başvuruları inceleyin:
- [Azure Güvenlik Mimarisi Önerileri: Depolama, veri ve şifreleme](/azure/architecture/framework/security/storage-data-encryption?amp;bc=%2fsecurity%2fcompass%2fbreadcrumb%2ftoc.json&toc=%2fsecurity%2fcompass%2ftoc.json)

- [Azure Güvenliği Temelleri: Azure'da veri güvenliği, şifreleme ve depolama](/azure/security/fundamentals/encryption-overview)

- [Bulut Benimseme Çerçevesi: Azure'da veri güvenliği ve şifreleme için en iyi deneyimler](/azure/security/fundamentals/data-encryption-best-practices?amp;bc=%2fazure%2fcloud-adoption-framework%2f_bread%2ftoc.json&toc=%2fazure%2fcloud-adoption-framework%2ftoc.json)

- [Azure Güvenlik Karşılaştırması: Varlık yönetimi](/azure/security/benchmarks/security-controls-v2-asset-management)

- [Azure Güvenlik Karşılaştırması: Veri koruma](/azure/security/benchmarks/security-controls-v2-data-protection)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="gs-2-define-enterprise-segmentation-strategy"></a>GS-2: Kurumsal segmentasyon stratejisini tanımlayın 

**Rehberlik**: Kimlik, ağ, uygulama, abonelik, yönetim grubu ve diğer denetimleri kullanarak varlık erişimi segmentasyonuna yönelik kuruluş genelinde kullanılacak bir strateji belirleyin.

Güvenlik ayrımı gereksinimiyle birbirleriyle iletişim kurma ve verilere erişme gereksinimine sahip olan sistemlerin günlük çalışmasını etkinleştirme gereksinimi arasında bir denge kurun.

Segmentasyon stratejisinin ağ güvenliği, kimlik ve erişim modelleri, uygulama izinleri/erişim modelleri ve insanlar tarafından gerçekleştirilen süreç denetimleri gibi farklı denetim türlerinde tutarlı bir şekilde uygulandığından emin olun.

- [Azure için segmentasyon stratejisi rehberi (video)](/security/compass/microsoft-security-compass-introduction#azure-components-and-reference-model-2151)

- [Azure için segmentasyon stratejisi rehberi (belge)](/security/compass/governance#enterprise-segmentation-strategy)

- [Ağ segmentasyonunu kurumsal segmentasyon stratejisiyle uyumlu hale getirme](/security/compass/network-security-containment#align-network-segmentation-with-enterprise-segmentation-strategy)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="gs-3-define-security-posture-management-strategy"></a>GS-3: Güvenlik duruşu yönetim stratejisini tanımlayın

**Rehberlik**: Varlıklarınız ve içinde bulundukları ortamla ilgili riskleri sürekli olarak ölçün ve ortadan kaldırın. Yayımlanmış uygulamalar, ağ giriş ve çıkış noktaları, kullanıcı ve yönetici uç noktaları gibi değeri yüksek varlıkları ve kullanıma açık olan saldırı yüzeylerini önceliklendirin.

- [Azure Güvenlik Karşılaştırması: Duruş ve güvenlik açığı yönetimi](/azure/security/benchmarks/security-controls-v2-posture-vulnerability-management)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="gs-4-align-organization-roles-responsibilities-and-accountabilities"></a>GS-4: Kuruluş genelindeki rolleri, sorumlulukları ve hesap verilebilirlik durumlarını uyumlu hale getirin

**Rehberlik**: Güvenlik kuruluşunuzdaki roller ve sorumluluklar için net bir strateji oluşturup bunu belgelendirdiğinizden ve paylaştığınızdan emin olun. Güvenlik kararları için net bir hesap verilebilirlik süreci oluşturmayı önceliklendirin, herkesi paylaşılan sorumluluk modeli hakkında eğitin ve teknik ekiplere bulut ortamının güvenliğini sağlamaya yönelik eğitimler verin.

- [Azure Güvenliği En İyi Deneyimi 1 - İnsanlar: Ekipleri Bulut Güvenliği Yolculuğu Hakkında Eğitin](/azure/cloud-adoption-framework/security/security-top-10#1-people-educate-teams-about-the-cloud-security-journey)

- [Azure Güvenliği En İyi Deneyimi 2 - İnsanlar: Ekipleri Bulut Güvenliği Teknolojileri Hakkında Eğitin](/azure/cloud-adoption-framework/security/security-top-10#2-people-educate-teams-on-cloud-security-technology)

- [Azure Güvenliği En İyi Deneyimi 3 - Süreç: Bulut Güvenliği Kararları için Hesap Verilebilirlik Ataması Yapın](/azure/cloud-adoption-framework/security/security-top-10#4-process-update-incident-response-ir-processes-for-cloud)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="gs-5-define-network-security-strategy"></a>GS-5: Ağ güvenlik stratejisini tanımlayın

**Rehberlik**: Kuruluşunuzun genel güvenlik erişimi denetimi stratejisi kapsamında Azure ağ güvenliği için bir yaklaşım belirleyin.  

Bu strateji kapsamında aşağıdaki öğeler için rehberlik, ilkeler ve standartlar belgelenmiş olmalıdır: 

-   Merkezi ağ yönetimi ve güvenlik sorumluluğu

-   Kurumsal segmentasyon stratejisiyle uyumlu sanal ağ segmentasyon modeli

-   Farklı tehdit ve saldırı senaryolarına yönelik düzeltme stratejisi

-   İnternet uç düğümü ile giriş ve çıkış stratejisi

-   Hibrit bulut ve şirket içi bağlantı stratejisi

-   Güncel ağ güvenliği yapıtları (ağ diyagramları, başvuru amaçlı ağ mimarisi vb.)

Daha fazla bilgi için aşağıdaki başvuruları inceleyin:
- [Azure Güvenliği En İyi Deneyimi 11 - Mimari. Tek ve birleşik güvenlik stratejisi](/azure/cloud-adoption-framework/security/security-top-10#11-architecture-establish-a-single-unified-security-strategy)

- [Azure Güvenlik Karşılaştırması: Ağ Güvenliği](/azure/security/benchmarks/security-controls-v2-network-security)

- [Azure ile ağ güvenliğine genel bakış](/azure/security/fundamentals/network-overview)

- [Kurumsal ağ mimarisi stratejisi](/azure/cloud-adoption-framework/ready/enterprise-scale/architecture)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="gs-6-define-identity-and-privileged-access-strategy"></a>GS-6: Kimlik ve ayrıcalıklı erişim stratejisini tanımlayın

**Rehberlik**: Kuruluşunuzun genel güvenlik erişimi denetimi stratejisi kapsamında Azure kimlik ve ayrıcalıklı erişim yaklaşımları belirleyin.  

Bu strateji kapsamında aşağıdaki öğeler için rehberlik, ilkeler ve standartlar belgelenmiş olmalıdır: 

-   Merkezi bir kimlik ve kimlik doğrulaması sistemi ile diğer iç ve dış kimlik sistemleriyle olan bağlantısı

-   Farklı kullanım örneklerine ve koşullara yönelik güçlü kimlik doğrulama yöntemleri

-   Yüksek ayrıcalıklı kullanıcıların korunması

-   Kullanıcı etkinlikleri için anomali izleme ve işleme  

-   Kullanıcı kimliği ve erişim gözden geçirmesi ile uzlaştırma süreci

Daha fazla bilgi için aşağıdaki başvuruları inceleyin:

- [Azure Güvenlik Karşılaştırması: Kimlik yönetimi](/azure/security/benchmarks/security-controls-v2-identity-management)

- [Azure Güvenlik Karşılaştırması: Ayrıcalıklı erişim](/azure/security/benchmarks/security-controls-v2-privileged-access)

- [Azure Güvenliği En İyi Deneyimi 11 - Mimari. Tek ve birleşik güvenlik stratejisi](/azure/cloud-adoption-framework/security/security-top-10#11-architecture-establish-a-single-unified-security-strategy)

- [Azure'da kimlik yönetim güvenliğine genel bakış](/azure/security/fundamentals/identity-management-overview)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

### <a name="gs-7-define-logging-and-threat-response-strategy"></a>GS-7: Günlüğe kaydetme ve tehdit yanıtı stratejisi tanımlayın

**Rehberlik**: Uyumluluk gereksinimleri kapsamında tehditleri hızlı bir şekilde algılamak ve düzeltmek için bir günlüğe kaydetme ve tehdit yanıtı stratejisi oluşturun. Tümleştirme ve el ile gerçekleştirilen adımlar yerine tehditlere odaklanabilmeleri için analistlere yüksek kaliteli uyarılar ve sorunsuz deneyimler sunmayı önceliklendirin. 

Bu strateji kapsamında aşağıdaki öğeler için rehberlik, ilkeler ve standartlar belgelenmiş olmalıdır: 

-   Güvenlik operasyonları (SecOps) organizasyonunun rolü ve sorumlulukları 

-   NIST veya diğer sektör çerçeveleriyle uyumlu iyi tanımlanmış bir olay yanıt süreci 

-   Tehdit algılama, olay yanıtı ve uyumluluk gereksinimlerini karşılamak için günlük yakalama ve saklama

-   SIEM, yerel Azure özellikleri ve diğer kaynaklar aracılığıyla merkezi görünürlük ve bilgi bağıntısı 

-   Planı müşterilerinize, tedarikçilerinize ve diğer proje katılımcılarına iletme ve onları bilgilendirme

-   Günlüğe kaydetme ve tehdit algılama, adli araştırma, saldırı önleme ve ortadan kaldırma gibi olay işleme adımları için yerel Azure ve üçüncü taraf platformları kullanma

-   Olayları ve çıkarılan dersler ile kanıt koruma gibi olay sonrası etkinlikleri işlemeye yönelik süreçler

Daha fazla bilgi için aşağıdaki başvuruları inceleyin:

- [Azure Güvenlik Karşılaştırması: Günlüğe kaydetme ve tehdit algılama](/azure/security/benchmarks/security-controls-v2-logging-threat-detection)

- [Azure Güvenlik Karşılaştırması: Olay yanıtı](/azure/security/benchmarks/security-controls-v2-incident-response)

- [Azure Güvenliği En İyi Deneyimi 4 - Süreç. Bulut için Olay Yanıt Sürecini Güncelleştirme](/azure/cloud-adoption-framework/security/security-top-10#4-process-update-incident-response-ir-processes-for-cloud)

- [Azure Benimseme Çerçevesi, günlüğe kaydetme ve raporlama kararı rehberi](/azure/cloud-adoption-framework/decision-guides/logging-and-reporting/)

- [Azure ile kurumsal ölçek, yönetim ve izleme](/azure/cloud-adoption-framework/ready/enterprise-scale/management-and-monitoring)

**Azure Güvenlik Merkezi ile izleme**: Uygulanamaz

**Sorumluluk**: Müşteri

## <a name="next-steps"></a>Sonraki adımlar

- Bkz. [Azure Güvenlik Karşılaştırması 2.0 sürümüne genel bakış](/azure/security/benchmarks/overview)
- [Azure güvenlik temelleri](/azure/security/benchmarks/security-baselines-overview) hakkında daha fazla bilgi edinin