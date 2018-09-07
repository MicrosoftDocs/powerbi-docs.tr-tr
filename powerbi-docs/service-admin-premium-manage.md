---
title: Power BI Premium ve Power BI Embedded'da kapasiteleri yönetme
description: Power BI Premium'u nasıl yönetebileceğinizi ve kuruluşunuzun tamamı için içerik erişimini nasıl sağlayabileceğinizi öğrenin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/10/2017
ms.author: mblythe
LocalizationGroup: Premium
ms.openlocfilehash: 5da624f92093111c1996d9b1c5080cd58a906a45
ms.sourcegitcommit: 2bdcb9e9959302a35ee90a145e4ff832a02aacb9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43250785"
---
# <a name="manage-capacities-within-power-bi-premium-and-power-bi-embedded"></a>Power BI Premium ve Power BI Embedded'da kapasiteleri yönetme
İçeriğiniz için ayrılmış kaynaklar sağlayan Power BI Premium ve Power BI Embedded kapasitelerini nasıl yönetebileceğinizi öğrenin.

![Power BI kapasite ayarları ekranı](media/service-admin-premium-manage/premium-capacity-management.png)

Kapasite, Power BI Premium ve Power BI Embedded tekliflerinin merkezindedir.

## <a name="what-is-capacity"></a>Kapasite nedir?
Kapasite, yalnızca sizin kullanmanız için ayrılmış kaynak kümesidir. Kapasiteye sahip olmak kuruluşunuzdaki kullanıcılar için lisans satın almak zorunda kalmadan onlara pano, rapor ve veri kümesi yayımlamanıza olanak sağlar. Ayrıca kapasitede barındırılan içerikler için güvenilir ve tutarlı performansı garanti eder.

Kapasite son kullanıcılarınız için tamamen şeffaftır. Power BI'ı veya uygulamanızı her zamanki gibi kullanmaya devam ederler. İçeriğin bir kısmının (veya tamamının) ayrılmış kapasitenizde barındırıldığını fark etmelerine neden olacak bir değişiklikle karşılaşmazlar. Kullanıcılarınız için her şey tam olarak eskisi gibi çalışır.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

Daha fazla bilgi için bkz. [Power BI Premium nedir?](service-premium.md).

### <a name="capacity-admins"></a>Kapasite yöneticileri
> [!NOTE]
> Power BI Embedded kapasitesine ilişkin kapasite yöneticileri Microsoft Azure portalında tanımlanır.

Bir kapasiteye kapasite yöneticisi olarak atandığınızda kapasite üzerinde tam kontrole ve kapasitenin yönetim özelliklerine sahip olursunuz. Power BI yönetici portalından daha fazla kapasite yöneticisi (yalnızca Power BI Premium) ekleyebilir veya kullanıcılara kapasite atama izinleri verebilirsiniz. Bir kapasiteye çalışma alanlarını toplu olarak atayabilir ve kapasitedeki kullanım ölçümlerini görüntüleyebilirsiniz.

Her kapasitenin kendisine ait yöneticileri vardır. Bir kapasiteye kapasite yöneticisi tanımlamak bu yöneticilere kuruluşunuzdaki tüm kapasitelere erişim yetkisi vermez. Kapasite yöneticileri; kullanım ölçümleri, denetim günlükleri veya kiracı ayarları gibi tüm Power BI yönetici alanlarına varsayılan olarak erişim sahibi olmaz. Ayrıca kapasite yöneticileri, yeni kapasite ayarlama veya mevcut kapasitelerin SKU'sunu değiştirme iznine de sahip değildir. Yalnızca Genel yöneticiler veya Power BI hizmet yöneticileri bu öğelere erişebilir.

Tüm Office 365 Genel yöneticileri ve Power BI yöneticileri otomatik olarak hem Power BI Premium hem de Power BI Embedded kapasitesinin kapasite yöneticileridir.

## <a name="purchase-capacity"></a>Kapasite satın alma
Ayrılmış kapasiteden yararlanmak için Office 365 yönetim merkezinde Power BI Premium aboneliği satın almanız veya Microsoft Azure portalında Power BI Embedded kaynağı oluşturmanız gerekir. Daha fazla bilgi için aşağıdaki başlıklara bakın:

* **Power BI Premium:** [Power BI Premium'u satın alma](service-admin-premium-purchase.md)
* **Power BI Embedded:** [Azure portalında Power BI Embedded kapasitesi oluşturma](https://docs.microsoft.com/en-us/azure/power-bi-embedded/create-capacity)

Power BI Premium SKU satın aldığınızda, kiracınız çalışan kapasitelerde kullanmak için uygun sayıda sanal çekirdek edinir. Örneğin, Power BI Premium P3 SKU satın almak kiracıya 32 sanal çekirdek sağlar.

> [!NOTE]
> Aboneliğinizin sona ermesinin ardından 30 gün boyunca tam erişiminiz sürer, ancak bu süre dolduğunda içeriğiniz paylaşılan kapasiteye döner. 1 GB’tan küçük olan modeller normal bir paylaşılan lisansla desteklenmez.


## <a name="manage-capacity"></a>Kapasiteyi yönetme
Office 365'te kapasite düğümleri satın aldıktan sonra yeni bir kapasite ayarlamanız gerekir. Bu işlem [Power BI yönetici portalı](service-admin-portal.md) aracılığıyla gerçekleştirilir. Yönetici portalında **Kapasite ayarları** adlı bir bölüm bulunur. Bu, kuruluşunuz için Power BI Premium kapasitelerini yöneteceğiniz yerdir.

![Yönetici portalındaki kapasite ayarları](media/service-admin-premium-manage/admin-portal-premium.png)

**Kapasite ayarları**'nı seçtiğinizde, varsayılan olarak Power BI Premium'un seçili olduğu kapasite yönetimi ekranına yönlendirilirsiniz.

### <a name="setting-up-a-new-capacity-power-bi-premium"></a>Yeni kapasite ayarlama (Power BI Premium)
Sanal çekirdek sayısı, kapasite oluşturmak için kullanılan miktarın yanı sıra sonraki kapasite oluşturma işlemleri için kullanılabilecek miktarı da gösterir. Kuruluşunuz için kullanılabilir sanal çekirdek miktarı, satın aldığınız Premium SKU'lara bağlıdır. Örneğin, bir P3 ve bir P2 satın alındığında 48 çekirdek kullanılabilirken, P3 satın alındığında 32, P2 satın alındığında ise 16 çekirdek sunulur.

![Power BI Premium için kullanılan ve kullanılabilir sanal çekirdekler](media/service-admin-premium-manage/admin-portal-v-cores.png)

Kullanılabilir sanal çekirdekleriniz varsa aşağıdakileri yaparak yeni kapasitenizi ayarlayın.

1. **Yeni kapasite ayarlama** seçeneğini belirleyin.
2. Kapasitenize bir **ad** verin.
3. Bu kapasitenin kapasite yöneticisini tanımlayın.

    Kapasite yöneticilerinin Power BI yöneticisi veya Office 365 Genel yöneticisi olması gerekmez. Daha fazla bilgi için bkz. [Power BI Premium kapasite yöneticileri](#capacity-admins)
4. Kapasite boyutunuzu seçin. Mevcut seçenekler, sahip olduğunuz kullanılabilir sanal çekirdek sayısına bağlıdır. Kullanabildiğiniz sayıdan daha fazlasını gerektiren bir seçeneği belirleyemezsiniz.

    ![Kullanılabilir Premium kapasite boyutları](media/service-admin-premium-manage/premium-capacity-size.png)
5. **Ayarla** seçeneğini belirleyin.

    ![Yeni kapasitesi ayarlama](media/service-admin-premium-manage/set-up-capacity.png)

Kapasite yöneticilerinin yanı sıra Power BI yöneticileri ve Office 365 Genel Yöneticileri, yönetici portalında listelenen kapasiteyi görür.

### <a name="capacity-settings"></a>Güvenlik ayarları
Premium kapasite yönetimi ekranında, eylemler bölümündeki **dişli simgesini (ayarlar)** seçebilirsiniz. Bu, bir kapasiteyi yeniden adlandırmanıza veya silmenize olanak sağlar. Ayrıca hizmet yöneticilerinin kim olduğunu, SKU'yu/kapasite boyutunu ve kapasitenin bulunduğu bölgeyi de gösterir.

![Kapasite yönetimi alanındaki kapasite eylemleri](media/service-admin-premium-manage/capacity-actions.png)

![Güvenlik ayarları](media/service-admin-premium-manage/capacity-settings.png)

![Power BI Premium'da kapasite ayarları için sil ve uygula düğmeleri](media/service-admin-premium-manage/capacity-settings-delete.png)

> [!NOTE]
> Power BI Embedded kapasite ayarları Microsoft Azure portalında yönetilir.

### <a name="change-capacity-size-power-bi-premium"></a>Kapasite boyutunu değiştirme (Power BI Premium)
Power BI yöneticileri ve Office 365 Genel yöneticileri Power BI Premium kapasite boyutunu **Kapasite boyutunu değiştirme** seçeneğini belirleyerek değiştirir. Power BI yöneticisi veya Office 365 Genel yöneticisi olmayan kapasite yöneticileri bu seçeneğe sahip olmaz.

![Power BI Premium kapasite boyutunu değiştirme](media/service-admin-premium-manage/change-capacity-size.png)

**Kapasite boyutunu değiştirme** ekranı, kullanılabilir kaynaklarınız varsa kapasite boyutunuzu yükseltmenize veya eski sürümü yüklemenize olanak tanır. Gereken sayıda sanal çekirdeğe sahip oldukları sürece yöneticiler düğüm oluşturabilir, düğümleri yeniden boyutlandırabilir ve silebilir.

P SKU'lar EM SKU'lara düşürülebilir. Devre dışı bırakılan seçeneklerin üzerine geldiğinizde bir açıklamayla karşılaşırsınız.

![Power BI Premium kapasite boyutunu değiştirme açılan listesi](media/service-admin-premium-manage/change-capacity-size2.png)

### <a name="capacity-assignment"></a>Kapasite atama
Bir kapasite adını seçerek söz konusu kapasiteyi yönetebilirsiniz. Bu işlem sizi kapasite yönetimi ekranına yönlendirir.

![Kapasite atama ekranına gitmek için kapasite adını seçme](media/service-admin-premium-manage/capacity-assignment.png)

Kapasiteye hiçbir çalışma alanı atanmadıysa **Çalışma alanları atama** olanağı sunan bir ileti görürsünüz.

#### <a name="user-permissions"></a>Kullanıcı izinleri
Power BI Premium kapasiteleri için ek **Kapasite yöneticileri** atayabilirsiniz. Ayrıca **kapasite atama izinlerine** sahip olacak kullanıcılar da atayabilirsiniz. Atama izinleri bulunan kullanıcılar, söz konusu çalışma alanının yöneticisi olmaları halinde kapasiteye uygulama çalışma alanı atayabilir. Bu kapasiteye kişisel Çalışma Alanlarını (*Çalışma Alanım*) da atayabilirler. Atama izinlerine sahip kullanıcılar yönetici portalına erişemez.

> [!NOTE]
> Power BI Embedded kapasitesi için kapasite yöneticileri Microsoft Azure portalında atanır.
>
>

![](media/service-admin-premium-manage/capacity-user-permissions.png)

![](media/service-admin-premium-manage/capacity-user-permissions2.png)

## <a name="assign-a-workspace-to-a-capacity"></a>Bir kapasiteye çalışma alanı atama
Bir kapasiteye çalışma alanı atayabilmenin birkaç yolu vardır.

### <a name="capacity-management-in-admin-portal"></a>Yönetici portalındaki kapasite yönetimi
Kapasite yöneticilerinin yanı sıra Power BI yöneticileri ve Office 365 genel yöneticileri, yönetici portalının premium kapasite yönetimi bölümünde toplu olarak çalışma alanları atayabilir. Bir kapasiteyi yönetirken, çalışma alanları atamanızı sağlayan **Çalışma Alanları** bölümünü görürsünüz.

![Kapasite yönetiminin çalışma alanı atama alanı](media/service-admin-premium-manage/capacity-manage-workspaces.png)

1. **Çalışma alanları atama** seçeneğini belirleyin. Bu seçenek birden fazla yerde bulunur ve hepsi aynı görevi gerçekleştirir.
2. **Tüm kuruluşun çalışma alanları** veya **Kullanıcılara göre belirli çalışma alanları** seçeneğini belirleyin.

   | Seçim | Açıklama |
   | --- | --- |
   | **Tüm kuruluşun çalışma alanları** |Tüm kuruluşun çalışma alanlarını Premium kapasiteye atamak kuruluşunuzdaki tüm Uygulama Çalışma Alanları'nı ve Çalışma Alanım adlı kişisel alanları bu Premium kapasiteye atar. Ayrıca mevcut ve gelecekteki tüm kullanıcılar bu kapasiteye çalışma alanlarını ayrı ayrı yeniden atama iznine sahip olur. |
   | **Kullanıcılara göre belirli çalışma alanları** |Çalışma alanlarını kullanıcıya veya gruba göre atadığınızda, söz konusu kullanıcıların sahip olduğu tüm çalışma alanları, kullanıcının kişisel çalışma alanı da dahil olmak üzere, Premium kapasiteye atanır. Söz konusu kullanıcılar çalışma alanı atama izinlerini otomatik olarak alır.<br>Buna, farklı bir kapasiteye atanmış olan çalışma alanları da dahildir. |
3. **Uygula** seçeneğini belirleyin.

Bu seçenek, bir kapasiteye belirli çalışma alanları atamanıza olanak sağlamaz.

### <a name="app-workspace-settings"></a>Uygulama çalışma alanı ayarları
Söz konusu çalışma alanının ayarlarından Premium kapasiteye uygulama çalışma alanı da atayabilirsiniz. Bir premium kapasiteye uygulama çalışma alanı atamak için şunları yapın.

Bir çalışma alanını kapasiteye taşımak için söz konusu çalışma alanının yönetici izinlerinin yanı sıra bu kapasiteye ilişkin kapasite atama izinlerine de sahip olmanız gerekir. Çalışma alanı yöneticilerinin bir çalışma alanını Premium kapasiteden istedikleri zaman kaldırabileceğini unutmayın.

1. **Üç nokta (...)** simgesini ve **Çalışma alanını düzenle**'yi seçerek uygulama çalışma alanını düzenleyin.

    ![Üç nokta bağlam menüsünden çalışma alanı düzenleme](media/service-admin-premium-manage/edit-app-workspace.png)
2. **Çalışma alanını düzenle** alanında **Gelişmiş** seçeneğini genişletin.
3. Herhangi bir kapasite için size kapasite atama izinleri verildiyse bu çalışma alanında **Premium**'u etkinleştirme seçeneğine sahip olursunuz.
4. Bu Uygulama çalışma alanını atamak istediğiniz kapasiteyi seçin.

    ![Kapasite seçimi açılan listesi](media/service-admin-premium-manage/app-workspace-advanced.png)
5. **Kaydet**'i seçin.

Kaydedildikten sonra çalışma alanı ve tüm içerikleri, son kullanıcılar için herhangi bir deneyim kesintisi olmaksızın Premium kapasiteye taşınır.


## <a name="monitor-capacity-usage"></a>Kapasite kullanımı izleme

Power BI, kapasite kullanımını izlemek için bir uygulama sunmaktadır. Daha fazla bilgi için bkz. [Kuruluşunuzdaki Power BI Premium kapasitelerini izleme](service-admin-premium-monitor-capacity.md).

## <a name="what-premium-looks-like-for-users"></a>Premium, kullanıcılara nasıl görünür?
Çoğunlukla kullanıcıların Premium kapasitede olduklarını bilmelerine bile gerek yoktur. Panoları ve raporları normal şekilde çalışmaya devam eder. Görsel bir ipucu olarak, Premium kapasitedeki çalışma alanlarının yanında bir baklava simgesi görürsünüz.

![Baklava simgesi görünen çalışma alanı Premium kapasite tarafından yedeklenir](media/service-admin-premium-manage/premium-workspace.png)

## <a name="power-bi-report-server-product-key"></a>Power BI Rapor Sunucusu ürün anahtarı
Power BI yönetici portalının **Kapasite ayarları** sekmesinde Power BI Rapor Sunucusu ürün anahtarınıza erişebilirsiniz. Bu yalnızca Genel Yöneticiler veya Power BI hizmeti yönetici rolüne atanan kullanıcılar için ve Power BI Premium SKU satın aldıysanız kullanılabilir.

![Kapasite ayarlarındaki Power BI Rapor Sunucusu anahtarı](media/service-admin-premium-manage/pbirs-product-key.png)

**Power BI Rapor Sunucusu anahtarı**'nı seçtiğinizde ürün anahtarınızı içeren bir iletişim kutusu görüntülenir. Ürün anahtarınızı kopyalayıp yükleme esnasında kullanabilirsiniz.

![Power BI Rapor Sunucusu ürün anahtarı](media/service-admin-premium-manage/pbirs-product-key-dialog.png)

Daha fazla bilgi için bkz. [Power BI Rapor Sunucusu'nu yükleme](report-server/install-report-server.md).

## <a name="next-steps"></a>Sonraki adımlar
Yayımlanan uygulamaları kullanıcılarla paylaşma. Daha fazla bilgi için bkz. [Power BI'da uygulama oluşturma ve dağıtma](service-create-distribute-apps.md).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
