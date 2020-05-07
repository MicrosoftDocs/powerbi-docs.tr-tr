---
title: Power BI Premium'u satın alma
description: Power BI Premium'u nasıl satın alabileceğinizi ve kuruluşunuzun tamamı için içerik erişimini nasıl sağlayabileceğinizi öğrenin.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/13/2020
LocalizationGroup: Premium
ms.openlocfilehash: aed0d1e4dec6f6efe49dd39cd5b6fc60f8977e44
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "79488626"
---
# <a name="how-to-purchase-power-bi-premium"></a>Power BI Premium'u satın alma

Bu makalede kuruluşunuz için Power BI Premium kapasitesini satın alma adımları anlatılmaktadır. Makalede iki senaryo açıklanır:

- Tipik üretim senaryolarında P SKU'larını kullanma. P SKU'ları için aylık veya yıllık taahhüt gerekir ve aylık faturalama yapılır.

- Test senaryolarında ve P SKU'larını satın almak için gereken izinleriniz (Microsoft 365 Genel Yöneticisi rolü veya Faturalama Yöneticisi rolü) olmadığında A SKU'larını kullanma. A SKU'ları için zaman taahhütü gerekmez ve bu saatlik olarak faturalandırılır. A SKU'larını [Azure portalında](https://portal.azure.com) satın alırsınız.

Power BI Premium hakkında daha fazla bilgi için bkz. [Power BI Premium nedir?](service-premium-what-is.md). Geçerli fiyatlandırma ve planlama bilgileri için bkz. [Power BI fiyatlandırma sayfası](https://powerbi.microsoft.com/pricing/) ve [Power BI Premium hesaplayıcısı](https://powerbi.microsoft.com/calculator/). Kuruluşunuzda Power BI Premium sürümü kullanılsa da içerik oluşturucularının [Power BI Pro lisansına](service-admin-purchasing-power-bi-pro.md) sahip olması gerekir. Kuruluşunuz için en az bir Power BI Pro lisansı satın aldığınızdan emin olun. A SKU'larıyla, içerik kullanan _tüm kullanıcılara_ da Pro lisansları gerekir.

> [!NOTE]
> Premium aboneliğinizin süresi dolarsa kapasitenize 30 gün boyunca tam erişim sağlayabilirsiniz. Bu sürenin sonunda içeriğiniz paylaşılan kapasiteye dönüştürülür. 1 GB üzerindeki modeller paylaşılan kapasitede desteklenmez.

## <a name="purchase-p-skus-for-typical-production-scenarios"></a>Tipik üretim senaryolarında P SKU'larını kullanma

Power BI Premium P1 SKU'su yapılandırılmış yeni bir kiracı oluşturabilir veya mevcut kuruluş için Power BI Premium kapasitesi satın alabilirsiniz. Her iki durumda da gerekirse daha sonra kapasite ekleyebilirsiniz.

### <a name="create-a-new-tenant-with-power-bi-premium-p1"></a>Power BI Premium P1 ile yeni kiracı oluşturma

Mevcut kiracınız yoksa ve yeni bir kiracı oluşturmak istiyorsanız aynı anda Power BI Premium sürümünü de satın alabilirsiniz. Aşağıdaki bağlantı yeni bir kiracı oluşturma işlemi sırasında size yardımcı olacak ve Power BI Premium: [Power BI Premium P1 teklifini](https://signup.microsoft.com/Signup?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1) satın almanızı sağlayacaktır. Kiracınızı oluşturduğunuzda otomatik olarak kiracının Microsoft 365 Genel Yönetici rolüne atanmış olursunuz.

Kapasiteyi satın aldıktan sonra [kapasiteleri yönetmeyi](service-admin-premium-manage.md#manage-capacity) ve kapasiteye [çalışma alanları atamayı](service-admin-premium-manage.md#assign-a-workspace-to-a-capacity) öğrenin.

### <a name="purchase-a-power-bi-premium-capacity-for-an-existing-organization"></a>Mevcut kuruluşlar için bir Power BI Premium kapasitesi satın alma

Mevcut bir kuruluşunuz (kiracı) varsa abonelik ve lisans satın almak için Microsoft 365 Genel Yöneticisi veya Faturalama Yöneticisi rolünde olmanız gerekir. Daha fazla bilgi için bkz. [Microsoft 365 yönetici rolleri hakkında](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

Premium kapasite satın almak için bu adımları izleyin.

1. Power BI hizmetinden Microsoft 365 uygulama seçiciyi ve ardından **Yönetici**'yi seçin.

    ![Microsoft 365 uygulama seçici](media/service-admin-premium-purchase/o365-app-picker.png)

    Alternatif olarak Microsoft 365 yönetim merkezini de ziyaret edebilirsiniz.

1. **Faturalama** > **Hizmet satın alın**'ı seçin.

1. **Diğer planlar** bölümünde Power BI Premium fırsatlarını bulun. Bu fırsatlar P1-P3 arası, EM3 ve P1 (aylık) şeklinde olacaktır.

1. Üç nokta ( **. . .** ) simgesinin üzerine gelip **Hemen satın alın**'ı seçin.

    ![Şimdi satın alın](media/service-admin-premium-purchase/premium-purchase.png)

1. Satın alma işlemini tamamlamak için adımları uygulayın.

Satın alma işlemini tamamladıktan sonra **Hizmetleri satın alın** sayfasında satın alınan ve etkinleştirilen öğeler gösterilir.

![Power BI Premium'u satın aldınız](media/service-admin-premium-purchase/premium-purchased.png)

Kapasiteyi satın aldıktan sonra [kapasiteleri yönetmeyi](service-admin-premium-manage.md#manage-capacity) ve kapasiteye [çalışma alanları atamayı](service-admin-premium-manage.md#assign-a-workspace-to-a-capacity) öğrenin.

### <a name="purchase-additional-capacities"></a>Ek kapasite satın alma

Bir kapasiteye sahip olduğunuza göre ihtiyaçlarınız arttıkça daha fazla kapasite ekleyebilirsiniz. Kuruluşunuzda farklı Premium kapasite SKU'larını (P1-P3) bir arada kullanabilirsiniz. Farklı SKU'lar farklı kaynak özellikleri sunar.

1. Microsoft 365 yönetim merkezinde **Faturalama** > **Hizmet satın alın**’ı seçin.

1. Daha fazlasını satın almak istediğiniz Power BI Premium öğesini **Diğer planlar**'ın altında bulun.

1. **Diğer seçenekler** (...) simgesinin üzerine gelip **Lisans miktarını değiştir** seçeneğini belirleyin.

    ![Lisans miktarını değiştir](media/service-admin-premium-purchase/premium-purchase-more.png)

1. Bu öğe için sahip olmak istediğiniz örnek sayısını değiştirin. İşlemi tamamladıktan sonra **Gönder**'i seçin.

   > [!IMPORTANT]
   > **Gönder**'i seçtiğinizde kayıtlı kredi kartından çekim yapılır.

Ardından **Hizmet satın alın** sayfasında sahip olduğunuz örnek sayısı gösterilir. Power BI yönetici portalının **Kapasite ayarları** bölümünde, kullanılabilir sanal çekirdek sayısı, yeni satın alınan kapasiteyi gösterir.

![Power BI Premium kapasitesi için kullanılabilir sanal çekirdekler](media/service-admin-premium-purchase/premium-capacities.png)

### <a name="cancel-your-subscription"></a>Aboneliğinizi iptal etme

Aboneliğinizi Microsoft 365 yönetim merkezinden iptal edebilirsiniz. Premium aboneliğiniz iptal etmek için aşağıdaki işlemleri gerçekleştirin.

1. Microsoft 365 yönetim merkezine göz atın.

1. **Faturalama** > **Abonelikler**'i seçin.

1. Listeden Power BI Premium aboneliğinizi seçin.

1. **Diğer eylemler** > **Aboneliği iptal et**’i seçin.

1. **Aboneliği iptal et** sayfasında [erken sonlandırma ücreti](https://support.office.com/article/early-termination-fees-6487d4de-401a-466f-8bc3-c0beb5cc40d3) ödemeniz gerekip gerekmediği belirtilir. Bu sayfada aboneliğe ait verilerin silineceği zamanı da görebilirsiniz.

1. Bilgileri okuyun ve devam etmek istiyorsanız **Aboneliği iptal et**'i seçin.

#### <a name="when-canceling-or-your-license-expires"></a>İptal ettiğinizde veya lisansınızın süresi dolduğunda

Premium aboneliğinizi iptal ettiğinizde veya kapasite lisansınızın süresi dolduğunda, iptal veya lisans süre sonu tarihini izleyen 30 günlük bir süre boyunca Premium kapasitelerinize erişmeye devam edebilirsiniz. Bu 30 günün sonunda artık Premium kapasitelerinize veya bunların içerdiği çalışma alanlarına erişemezsiniz.

## <a name="purchase-a-skus-for-testing-and-other-scenarios"></a>Testler ve diğer senaryolar için A SKU'ları satın alma

A SKU'ları Azure Power BI Embedded hizmeti aracılığıyla kullanıma sunulur. A SKU'larını aşağıdaki yöntemlerle kullanabilirsiniz:

- Üçüncü taraf uygulamalarında Power BI eklemeyi etkinleştirin. Daha fazla bilgi için bkz. [Power BI Embedded](developer/embedded/azure-pbie-what-is-power-bi-embedded.md).

- P SKU'su satın almadan önce Premium işlevselliğini test edin.

- P SKU'larını kullanan üretim ortamının yanında geliştirme ve test ortamları da oluşturun.

- Microsoft 365 Genel Yöneticisi veya Faturalama Yöneticisi rolünde olmasanız bile Power BI Premium satın alın.

> [!NOTE]
> A4 veya daha yüksek bir SKU satın alırsanız sınırsız içerik paylaşımı dışında tüm Premium özelliklerden yararlanabilirsiniz. A SKU'larıyla, içerik kullanan _tüm kullanıcılara_ Pro lisansları gerekir.

Azure portalında A SKU'ları satın almak için şu adımları izleyin:

1. En azından Power BI'da kapasite yöneticisi izinlerine sahip olan bir hesapla [Azure portalında](https://portal.azure.com) oturum açın.

1. _Power BI Embedded_ için arama yapın ve arama sonuçlarında hizmeti seçin.

    ![Azure portalı araması](media/service-admin-premium-purchase/azure-portal-search.png)

1. **Power BI Embedded Oluştur**'u seçin.

    ![Power BI Embedded Oluştur](media/service-admin-premium-purchase/create-power-bi-embedded.png)

1. **Power BI Embedded** oluşturma ekranında aşağıdaki bilgileri belirtin:

    - İçinde Power BI Embedded hizmetinin oluşturulacağı **Abonelik**.

    - İçinde hizmeti içeren kaynak grubunun oluşturulacağı fiziksel **Konum**. Daha iyi bir performans için, bu konumun Power BI için Azure Active Directory kiracınızın konumuna yakın olması gerekir.

    - Kullanılacak mevcut **Kaynak grubu** veya örnekte gösterildiği gibi yeni bir kaynak grubu oluşturun.

    - **Power BI kapasite yöneticisi**. Kapasite yöneticisi Azure AD kiracınızda üye kullanıcı veya hizmet sorumlusu olması gerekir.

    ![Abonelik ve kaynak grubu](media/service-admin-premium-purchase/subscription-resource-group.png)

1. Power BI Premium'un tüm özelliklerini (sınırsız paylaşım dışında) kullanmak istiyorsanız en az A4 SKU'suna ihtiyacınız vardır. **Boyutu değiştir**'i seçin.

    ![Kapasite boyutunu değiştir](media/service-admin-premium-purchase/change-capacity-size.png)

1. P1, P2 ve P3'e karşılık gelen A4, A5 veya A6 kapasite boyutunu seçin.

    ![A3 kapasitesini seçme](media/service-admin-premium-purchase/select-a3-capacity.png)

1. **Gözden Geçir + Oluştur**'u seçin, belirttiğiniz seçenekleri gözden geçirin, sonra da **Oluştur**'u seçin.

    ![Kaynak oluşturma](media/service-admin-premium-purchase/create-resource.png)

1. Dağıtımın tamamlanması birkaç dakika sürebilir. Hazır olduğunda **Kaynağa git**'i seçin.

    ![Dağıtım tamamlandı](media/service-admin-premium-purchase/deployment-complete.png)

1. Yönetim ekranında hizmeti yönetmek için size sağlanan seçenekleri gözden geçirin; bunlar arasında kullanmadığınız sırada hizmeti duraklatma seçeneği de yer alır.

    ![Kapasiteyi yönetme](media/service-admin-premium-purchase/manage-capacity.png)

Kapasiteyi satın aldıktan sonra [kapasiteleri yönetmeyi](service-admin-premium-manage.md#manage-capacity) ve kapasiteye [çalışma alanları atamayı](service-admin-premium-manage.md#assign-a-workspace-to-a-capacity) öğrenin.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium’da kapasiteleri yapılandırma ve yönetme](service-admin-premium-manage.md)\
[Power BI fiyatlandırma sayfası](https://powerbi.microsoft.com/pricing/)\
[Power BI Premium hesaplayıcısı](https://powerbi.microsoft.com/calculator/)\
[Power BI Premium hakkında SSS](service-premium-faq.md)\
[Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama) teknik incelemesi](https://aka.ms/pbienterprisedeploy)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
