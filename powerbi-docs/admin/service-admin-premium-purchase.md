---
title: Power BI Premium'u satın alma
description: Power BI Premium'u nasıl satın alabileceğinizi ve kuruluşunuzun tamamı için içerik erişimini nasıl sağlayabileceğinizi öğrenin.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-premium
ms.topic: how-to
ms.date: 01/28/2021
LocalizationGroup: Premium
ms.openlocfilehash: c4e50f7fa0c8f3313b3e7e58001ae33d8c327d85
ms.sourcegitcommit: 7ed995eed0fd6e718748accf87bae384211cd95d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2021
ms.locfileid: "99043149"
---
# <a name="how-to-purchase-power-bi-premium"></a>Power BI Premium'u satın alma

Bu makalede kuruluşunuz için Power BI Premium kapasitesini satın alma adımları anlatılmaktadır. Makalede aşağıdaki senaryo ele alınmaktadır:

- Tipik üretim senaryolarında P SKU'larını kullanma. P SKU'ları için aylık veya yıllık taahhüt gerekir ve aylık faturalama yapılır.

Power BI Premium hakkında daha fazla bilgi için bkz. [Power BI Premium nedir?](service-premium-what-is.md). Geçerli fiyatlandırma ve planlama bilgileri için [Power BI fiyatlandırma sayfasına](https://powerbi.microsoft.com/pricing/)bakın. Kuruluşunuzda Power BI Premium sürümü kullanılsa da içerik oluşturucularının [Power BI Pro lisansına](service-admin-purchasing-power-bi-pro.md) sahip olması gerekir. Kuruluşunuz için en az bir Power BI Pro lisansı satın aldığınızdan emin olun. A SKU'larıyla, içerik kullanan _tüm kullanıcılara_ da Pro lisansları gerekir.

> [!NOTE]
> Premium aboneliğinizin süresi dolarsa kapasitenize 30 gün boyunca tam erişim sağlayabilirsiniz. Bu sürenin sonunda içeriğiniz paylaşılan kapasiteye dönüştürülür. 1 GB üzerindeki modeller paylaşılan kapasitede desteklenmez.

> [!NOTE]
> Yakın zamanda Power BI Premium, şu anda önizleme aşamasında olan **Premium 2. Nesil** adlı yeni bir Premium sürümünü kullanıma sundu. Premium 2. Nesil, Premium kapasitelerinin yönetimini basitleştirecek ve yönetim yükünü azaltacak. Daha fazla bilgi için bkz. [Power BI Premium 2. Nesil (önizleme)](service-premium-what-is.md#power-bi-premium-generation-2-preview).

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

Test ve diğer amaçlar için, saatlik olarak Premium kapasite sağlayan A SKU’larını da satın alabilirsiniz. Daha fazla bilgi ve adımlar için bkz. [Test için Power BI Premium’u satın alma](service-admin-premium-testing.md).

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium’da kapasiteleri yapılandırma ve yönetme](service-admin-premium-manage.md)\
[Power BI fiyatlandırma sayfası](https://powerbi.microsoft.com/pricing/)\
[Power BI Premium hakkında SSS](service-premium-faq.md)\
[Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama) teknik incelemesi](https://aka.ms/pbienterprisedeploy)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

Power BI, aşağıdaki iyileştirmelerle Power BI Premium deneyimini geliştiren bir önizleme teklifi olarak Power BI Premium 2. Nesil’i kullanıma sundu:
* Performans
* Kullanıcı başına lisanslama
* Daha yüksek ölçek
* İyileştirilmiş ölçümler
* Otomatik ölçeklendirme
* Azaltılmış yönetim yükü

Power BI Premium 2. Nesil hakkında daha fazla bilgi için bkz. [Power BI Premium 2. Nesil (önizleme)](service-premium-what-is.md#power-bi-premium-generation-2-preview).