---
title: Power BI’da Microsoft Cloud App Security denetimlerini kullanma
description: Microsoft Cloud App Security’yi Power BI ile birlikte kullanmayı öğrenin
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 06/15/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: 8a09de5777332d69332cae6928022e7e99fe689e
ms.sourcegitcommit: 2e81649476d5cb97701f779267be59e393460097
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/02/2021
ms.locfileid: "99422295"
---
# <a name="using-microsoft-cloud-app-security-controls-in-power-bi"></a>Power BI’da Microsoft Cloud App Security denetimlerini kullanma

Power BI ile Cloud App Security’yi kullanarak Power BI raporlarınızı, verilerinizi ve hizmetlerinizi istenmeyen sızıntı veya ihlallerden korumaya yardımcı olabilirsiniz. Cloud App Security, Power BI analizlerinizin güvende olduğundan emin olmaya yardımcı olan Azure Active Directory (Azure AD) içindeki gerçek zamanlı oturum denetimlerini kullanarak kuruluşunuzun verileri için koşullu erişim ilkeleri oluşturabilirsiniz. Bu ilkeler ayarlandıktan sonra yöneticiler kullanıcı erişimini ve etkinliğini izleyebilir, gerçek zamanlı risk analizi gerçekleştirebilir ve etikete özel denetimler belirleyebilir. 

![Cloud App Security denetimler bölmesini kullanma](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-01.png)

Cloud App Security’yi yalnızca Power BI değil, her türlü uygulama ve hizmet için yapılandırabilirsiniz. Power BI verileriniz ve analizlerinizin Cloud App Security korumalarının avantajlarından yararlanması için Cloud App Security’yi Power BI ile çalışacak şekilde yapılandırmanız gerekir. İşleyişi, panosu ve uygulama risk puanları dahil olmak üzere Cloud App Security hakkında daha fazla bilgi için [Cloud App Security](/cloud-app-security/) belgelerine bakın.

## <a name="cloud-app-security-licensing"></a>Cloud App Security lisansı

Power BI ile Cloud App Security’yi kullanmak için, bazıları Power BI dışında ayarlanan ilgili Microsoft güvenlik hizmetlerini kullanmanız ve yapılandırmanız gerekir. Kiracınızda Cloud App Security’yi kullanmak için aşağıdaki [lisanslardan](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE2NXYO) birine sahip olmanız gerekir:
* Microsoft Cloud App Security: Tüm desteklenen uygulamalar, EMS E5 ve Microsoft 365 E5 paketlerinin parçasına yönelik Cloud App Security özelliklerini sağlar.
* Office 365 Cloud App Security: Yalnızca Office 365 E5 paketinin bir parçası olarak Office 365 için Cloud App Security özellikleri sağlar.


## <a name="configure-real-time-controls-for-power-bi-with-cloud-app-security"></a>Cloud App Security Power BI için gerçek zamanlı denetimleri yapılandırma

> [!NOTE]
> * Gerçek zamanlı denetimlerin Cloud App Security avantajlarından yararlanmak için Azure Active Directory Premium P1 lisansı gerekir.

Aşağıdaki bölümlerde, Cloud App Security Power BI için gerçek zamanlı denetimleri yapılandırma adımları açıklanır.

### <a name="set-session-policies-in-azure-ad-required"></a>Azure AD’de oturum ilkelerini ayarlama (gerekli)
Oturum denetimlerini ayarlamak için gereken adımlar, Azure AD ve Cloud App Security portallarında tamamlanır. Azure AD portalında Power BI için bir koşullu erişim ilkesi oluşturup Cloud App Security hizmeti aracılığıyla Power BI kullanılan oturumları yönlendirebilirsiniz. 

Cloud App Security, bir ters ara sunucu mimarisi kullanarak çalışır ve Power BI kullanıcı etkinliğini gerçek zamanlı olarak izlemek için Azure AD koşullu erişimiyle tümleşiktir. Aşağıdaki adımlar, işlemi anlamanıza yardımcı olmak için verilmiştir ve aşağıdaki adımların her birinde bağlantısı verilen içerikte ayrıntılı adım adım yönergeler sunulmaktadır. İşlemin tamamını açıklayan bu [Cloud App Security makalesini](/cloud-app-security/proxy-deployment-aad) de okuyabilirsiniz.

1.  [Azure AD koşullu erişim testi ilkesi oluşturma](/cloud-app-security/proxy-deployment-aad#add-azure-ad)
2.  [İlke kapsamındaki bir kullanıcıyı kullanarak her bir uygulamada oturum açma](/cloud-app-security/proxy-deployment-aad#sign-in-scoped)
3.  [Uygulamaların erişim ve oturum denetimlerini kullanacak şekilde yapılandırıldığını doğrulama](/cloud-app-security/proxy-deployment-aad#portal)
4.  [Dağıtımı test etme](/cloud-app-security/proxy-deployment-aad#step-4-test-the-deployment)

Oturum ilkelerini ayarlama işlemi, [Oturum ilkeleri](/cloud-app-security/session-policy-aad) makalesinde ayrıntılı olarak açıklanmıştır. 

### <a name="set-anomaly-detection-policies-to-monitor-power-bi-activities-recommended"></a>Power BI etkinliklerini izlemek için anomali algılama ilkelerini ayarlama (önerilir)
Yalnızca ilkeye dahil etmek ve ilkeden dışlamak istediğiniz kullanıcılar ve gruplar için geçerli olacak şekilde bağımsız kapsamlı olabilecek anomali Power BI algılama ilkeleri tanımlayabilirsiniz. [Daha fazla bilgi edinin](/cloud-app-security/anomaly-detection-policy#scope-anomaly-detection-policies).

Cloud App Security, Power BI için iki ayrılmış iki yerleşik algılamaya sahiptir. [Ayrıntılı bilgi için bu belgenin ilerleyen kısımlarındaki bölüme bakın](#built-in-cloud-app-security-detections-for-power-bi).

### <a name="use-microsoft-information-protection-sensitivity-labels-recommended"></a>Microsoft Information Protection duyarlılık etiketlerini kullanma (önerilir)

Duyarlılık etiketleri, kuruluşunuzdaki kullanıcıların kuruluşunuzun dışındaki iş ortaklarıyla işbirliği yapabilmesi yaparken gizli içerik ve veriler konusunda dikkatli ve bilinçli olmaya devam etmesi için gizli içerikleri sınıflandırmanızı sağlar ve korumaya yardımcı olur. 

Power BI için duyarlılık etiketlerini kullanma işlemiyle ilgili ayrıntılı bilgiler veren [Power BI’da duyarlılık etiketleri](service-security-sensitivity-label-overview.md) makalesini okuyun. [Duyarlılık etiketlerini temel alan bir Power BI ilkesi örneği](#example) için aşağıya bakın.

## <a name="custom-policies-to-alert-on-suspicious-user-activity-in-power-bi"></a>Power BI şüpheli Kullanıcı etkinliğine uyarı vermek için özel ilkeler

Cloud App Security etkinlik ilkesi, yöneticilerin kendi özel kurallarını tanımlamasına olanak sağlar. Bu, norm göre farklılık gösteren Kullanıcı davranışının algılanmasına yardımcı olur ve hatta çok tehlikeli gibi görünse de otomatik olarak üzerinde işlem yapar. Örneğin:

* **Çok büyük duyarlılık etiketi kaldırma.** Örneğin: duyarlılık etiketleri, bir zaman penceresinde 5 dakikadan kısa bir süre içinde tek bir kullanıcı tarafından kaldırıldığında beni uyar.

* **Duyarlılık etiketi düşürme düzeyini şifreleme.** Örneğin: ' çok gizli ' duyarlılık etiketi olan bir rapor artık ' Public ' olarak sınıflandırıldığında beni uyar.

> [!NOTE]
> * Power BI yapıtların ve duyarlılık etiketlerinin benzersiz tanımlayıcıları (kimlikler) [Power BI REST API 'leri](/rest/api/power-bi/)kullanılarak bulunabilir. Bkz. [veri kümeleri edinme](/rest/api/power-bi/datasets/getdatasets) veya [rapor edinme](/rest/api/power-bi/reports/getreports).


Özel etkinlik ilkeleri Cloud App Security portalında yapılandırılır. [Daha fazla bilgi edinin](/cloud-app-security/user-activity-policies). 

## <a name="built-in-cloud-app-security-detections-for-power-bi"></a>Power BI için yerleşik Cloud App Security algılamaları

Cloud App Security algılamaları, yöneticilerin izlenen bir uygulamanın belirli etkinliklerini izlemesini sağlar. Power BI için şu anda iki tane ayrılmış ve yerleşik Cloud App Security algılaması vardır: 

* **Şüpheli paylaşım** – bir kullanıcı bilinmeyen (kuruluşa dışından) bir e-posta ile hassas bir raporu paylaştığında algılar. Hassas rapor, duyarlılık etiketi **YALNIZCA ŞİRKET İÇİ** olarak ayarlanmış bir rapordur. 

* **Raporların toplu paylaşımı**: Bir kullanıcı tek oturumda çok sayıda farklı rapor paylaştığında algılar.

Bu algılamaların ayarları Cloud App Security portalında yapılandırılır. [Daha fazla bilgi edinin](/cloud-app-security/anomaly-detection-policy#unusual-activities-by-user). 

## <a name="power-bi-admin-role-in-cloud-app-security"></a>Cloud App Security’de Power BI yönetici rolü

Power BI ile Cloud App Security kullanılırken Power BI yöneticileri için yeni bir rol oluşturulur. [Cloud App Security portalında](https://portal.cloudappsecurity.com/) Power BI yöneticisi olarak oturum açtığınızda, Power-BI ile ilgili verilere, uyarılara, risk altındaki kullanıcılara, etkinlik günlüklerine ve diğer bilgilere erişiminiz sınırlıdır.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar 
Power BI ile Cloud App Security kullanımı, kullanıcı oturumlarını ve etkinliklerini izleyen algılamalarla birlikte kuruluşunuzun içerik ve verilerinin güvenliğini sağlamaya yardımcı olmak için tasarlanmıştır. Power BI ile Cloud App Security kullanırken aklınızda tutmanız gereken bazı noktalar ve sınırlamalar vardır:

* Cloud App Security yalnızca Excel, PowerPoint ve PDF dosyalarında çalışabilir.
* Power BI için oturum ilkelerinizde duyarlılık etiketleri özelliklerini kullanmak istiyorsanız, bir Azure Information Protection Premium P1 veya Premium P2 lisansına sahip olmanız gerekir. Microsoft Azure Information Protection tek başına ya da Microsoft lisanslama paketlerinden biri aracılığıyla satın alınabilir. Ayrıntılı bilgi için [Azure Information Protection fiyatlandırmasına](https://azure.microsoft.com/pricing/details/information-protection/) bakın. Ayrıca, duyarlılık etiketlerinin Power BI varlıklarınıza uygulanmış olması gerekir.
* Oturum denetimi her işletim sistemi üzerinde, her platforma her tarayıcı için kullanılabilir. Internet Explorer 11, Microsoft Edge (en son), Google Chrome (en son), Mozilla Firefox (en son) veya Apple Safari (en son) kullanmanızı öneririz. Power BI genel API çağrıları ve tarayıcı tabanlı olmayan diğer oturumlar, Cloud App Security oturum denetiminin bir parçası olarak desteklenmez. [Ek ayrıntıları görüntüleyin](/cloud-app-security/proxy-intro-aad#supported-apps-and-clients).

> [!CAUTION]
> * Oturum ilkesinde, "Eylem" bölümündeki "koru" özelliği yalnızca öğede bir etiket yoksa çalışır. Zaten bir etiket varsa "koru" eylemi uygulanmaz; Power BI’de bir öğeye zaten uygulanmış olan mevcut bir etiketi geçersiz kılamazsınız.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Power BI ile Cloud App Security kullanarak yeni bir oturum ilkesi oluşturmayı göstermektedir.

İlk olarak yeni bir oturum ilkesi oluşturun. **Cloud App Security** portalında soldaki menüden **İlkeler**’i seçin.

![Yeni oturum ilkesi oluşturma](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-02.png)

Görüntülenen pencerede **İlke oluştur** açılır listesini seçin.

![İlke oluştur’u seçme](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-03.png)

Açılan listedeki seçenekler listesinden **Oturum ilkesi**'ni seçin.

![Oturum ilkesi seçme](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-04.png)

Görüntülenen pencerede oturum ilkesini oluşturun. Numaralandırılmış adımlarda aşağıdaki görüntünün ayarları açıklanır.

  1. **İlke şablonu** açılır penceresinde *Şablon yok*'u seçin.
  2. **İlke adı** kutusunda oturum ilkeniz için ilgili bir ad belirtin.
  3. **Oturum denetim türü** için *Denetim dosyası indirildi (DLP ile)* seçeneğini belirleyin.

      **Etkinlik kaynağı** bölümünde ilgili engelleme ilkelerini seçin. Yönetilmeyen ve uyumlu olmayan cihazların engellenmesini öneririz. Oturum Power BI’da olduğunda indirmeleri engellemeyi seçin.

        ![İndirmeleri engellemeye yönelik oturum ilkesi oluşturun.](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-05.png)

        Sayfayı aşağı kaydırdığınızda daha fazla seçenek görürsünüz. Aşağıdaki görüntüde, ek örneklerle birlikte bu seçenekler gösterilmektedir. 

  4. *Gizlilik etiketi*’ni *son derece gizli* olarak veya kuruluşunuza en uygun seçenek olarak belirleyin.
  5. **Denetleme yöntemi**’ni *hiçbiri* olarak değiştirin.
  6. İhtiyaçlarınıza uyan **Engelle** seçeneğini belirleyin.
  7. Böyle bir eylem için uyarı oluşturduğunuzdan emin olun.

        ![Oturum ilkesi ayarlarını seçin.](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-06.png)

        

  8. Son olarak, oturum ilkesini oluşturmak için **Oluştur** düğmesini seçtiğinizden emin olun.

        ![Oturum ilkesini oluşturun.](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-07.png)

## <a name="next-steps"></a>Sonraki adımlar
Bu makalede Cloud App Security’nin Power BI için veri ve içerik korumalarını nasıl sağlayabileceği açıklanmıştır. Power BI için Veri Koruma ve onu etkinleştiren Azure hizmetleri için destekleyici içerikleri açıklayan aşağıdaki makaleler de ilginizi çekebilir.

* [Power BI'daki duyarlılık etiketlerine genel bakış](service-security-sensitivity-label-overview.md)
* [Power BI’da duyarlılık etiketlerini etkinleştirme](service-security-enable-data-sensitivity-labels.md)
* [Power BI'da duyarlılık etiketlerini uygulama](service-security-apply-data-sensitivity-labels.md)

Aşağıdaki Azure ve güvenlik makaleleri de ilginizi çekebilir:

* [Microsoft Cloud App Security Koşullu Erişim Uygulama Denetimi ile uygulamaları koruma](/cloud-app-security/proxy-intro-aad)
* [Öne çıkan uygulamalar için Koşullu Erişim Uygulama Denetimi dağıtma](/cloud-app-security/proxy-deployment-aad)
* [Oturum ilkeleri](/cloud-app-security/session-policy-aad)
* [Duyarlılık etiketlerine genel bakış](/microsoft-365/compliance/sensitivity-labels)
* [Veri koruma ölçümleri raporu](service-security-data-protection-metrics-report.md)
