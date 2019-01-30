---
title: Power BI yönetici portalı
description: Yönetici portalı, kuruluşunuzda Power BI kiracı yönetimine olanak sağlar. Kullanım ölçümleri, Office 365 yönetim merkezine erişim ve ayarlar gibi öğeleri içerir.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/30/2018
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 2f7d43649079f63fe18bfb4316557c2b5322f204
ms.sourcegitcommit: 2954de034f5e1be655dd02cc756ff34f126d3034
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55234474"
---
# <a name="administering-power-bi-in-the-admin-portal"></a>Yönetim portalında Power BI’ı yönetme

Yönetici portalı kuruluşunuz için bir Power BI *kiracısını* yönetmenize olanak sağlar. Portalda kullanım ölçümleri, Office 365 yönetim merkezine erişim ve ayarlar gibi öğeler yer alır.

Tam yönetici portalı, Office 365’te Genel Yönetici olan veya kendilerine Power BI hizmeti yöneticisi rolü atanmış tüm kullanıcılar için erişilebilir durumdadır. Bu rollerden birinde değilseniz portalda yalnızca **Kapasite ayarlarını** görürsünüz. Power BI hizmet yöneticisi rolü ile ilgili daha fazla bilgi için bkz. [Power BI yönetici rolünü anlama](service-admin-role.md).

## <a name="how-to-get-to-the-admin-portal"></a>Yönetici portalına ulaşma

Power BI yönetici portalına erişim elde etmek için hesabınızın Office 365 veya Azure Active Directory'de **Genel Yönetici** olarak işaretlenmesi veya size Power BI hizmet yöneticisi rolünün atanması gerekir. Power BI hizmet yöneticisi rolü hakkında daha fazla bilgi için bkz. [Power BI yönetici rolünü anlama](service-admin-role.md). Power BI yönetici portalına ulaşmak için aşağıdakileri yapın.

1. Power BI hizmetinin sağ üst tarafındaki ayarlar dişli simgesini seçin.

1. **Yönetici portalı**’nı seçin.

    ![Yönetici portalı ayarları](media/service-admin-portal/powerbi-admin-settings.png)

Portalda yedi sekme vardır. Bu makalenin kalan bölümünde bu sekmelerden her biriyle ilgili bilgiler sağlanır.

![Yönetici portalı gezintisi](media/service-admin-portal/powerbi-admin-landing-page.png)

* [Kullanım ölçümleri](#usage-metrics)
* [Kullanıcılar](#users)
* [Denetim günlükleri](#audit-logs)
* [Kiracı ayarları](#tenant-settings)
* [Premium ayarları](#premium-settings)
* [Ekleme kodları](#embed-codes)
* [Kuruluş görselleri](#organization-visuals)

## <a name="usage-metrics"></a>Kullanım ölçümleri

**Kullanım ölçümleri** kuruluşunuz için Power BI kullanımını izlemenizi sağlar. Ayrıca kuruluşunuz için Power BI'da en etkin olan kullanıcıları ve grupları görme olanağı da sunar.

> [!NOTE]
> Panoya ilk kez eriştiğinizde veya panoyu görüntülemeniz üzerinden uzun bir süre geçtikten sonra panoyu tekrar ziyaret ettiğinizde, biz panoyu yüklerken büyük olasılıkla bir yükleme ekranıyla karşılaşırsınız.

Pano yüklendikten sonra iki kutucuk bölümü görürsünüz. İlk bölüm, farklı kullanıcılar hakkındaki kullanım verilerini, ikinci bölüm ise kuruluşunuzdaki gruplara yönelik benzer bilgileri içerir.

Aşağıda, her kutucukta görebileceklerinize ilişkin bir döküm verilmiştir:

* Kullanıcı çalışma alanındaki tüm panoların, raporların ve veri kümelerinin ayrı sayımı
  
    ![Panoların, raporların, veri kümelerinin ayrı sayımı](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* Erişebilen kullanıcıların sayısına göre en fazla kullanılan pano. Örneğin, 3 kullanıcıyla paylaştığınız bir pano varsa ve bu panoyu iki farklı kullanıcının bağlı olduğu bir içerik paketine de eklediyseniz, panonun sayımı 6 (1 + 3 + 2) şeklinde olur
  
    ![En çok kullanılan panolar](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* Kullanıcıların bağlı olduğu en popüler içerikler. Bu, kullanıcıların Veri Al işlemiyle ulaşabileceği herhangi bir şey (SaaS içerik paketleri, Kurumsal içerik paketleri, dosyalar veya veritabanları) olabilir.
  
    ![En çok kullanılan paketler](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* En fazla panoya sahip (hem kendi oluşturdukları hem de kendileriyle paylaşılan panolar) kullanıcılarınızın bir görünümü.
  
    ![En etkin kullanıcılar - panolar](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* En fazla rapora sahip kullanıcılarınızın bir görünümü
  
    ![En etkin kullanıcılar - raporlar](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

İkinci bölüm aynı türde bilgileri grup temelinde gösterir. Bu, kuruluşunuzdaki en etkin grupları ve bu grupların kullandığı içerik türünü öğrenmenize olanak tanır.

Bu bilgilerle kişilerin kuruluşunuzdaki Power BI’ı nasıl kullandığına ilişkin gerçek içgörüler elde edebilir ve kuruluşunuzda oldukça etkin olan bu kullanıcıları ve grupları tanıyabilirsiniz.

## <a name="users"></a>Kullanıcılar

Power BI kullanıcılarını, gruplarını ve yöneticilerini Office 365 yönetim merkezinde yönetirsiniz. **Kullanıcılar** sekmesi, kiracınız için yönetim merkezine bağlantı sağlar.

![O365 Yönetim Merkezi'ne git](media/service-admin-portal/powerbi-admin-manage-users.png)

## <a name="audit-logs"></a>Denetim günlükleri

Power BI denetim günlüklerini Office 365 Güvenlik ve Uyumluluk merkezinde yönetirsiniz. **Denetim günlükleri** sekmesi, kiracınız için Güvenlik ve Uyumluluk merkezine bağlantı sağlar. [Daha fazla bilgi](service-admin-auditing.md)

Denetim günlüklerini kullanmak için [**İç etkinlik denetimi ve uyumluluk için denetim günlükleri oluşturun**](#create-audit-logs-for-internal-activity-auditing-and-compliance) ayarının etkinleştirilmiş olduğundan emin olun.

## <a name="tenant-settings"></a>Kiracı ayarları

**Kiracı ayarları** sekmesi, kuruluşunuzun kullanımına sunulan özellikler üzerinde çok ayrıntılı bir denetime olanak tanır. Gizli verilerle ilgili endişeleriniz varsa, sunduğumuz belirli özellikler kuruluşunuz için uygun olmayabilir veya belirli bir özelliğin yalnızca belirli bir grubun kullanımına sunulmasını isteyebilirsiniz.

Aşağıdaki resimde **Kiracı ayarları** sekmesinin ilk iki bölümü gösterilir.

![Kiracı ayarları](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> Ayar değişikliğinin kiracınızdaki herkes için geçerlilik kazanması 10 dakika kadar sürebilir.

Ayarlar üç duruma sahip olabilir:

* **Tüm kuruluş için devre dışı bırakıldı**: Kuruluşunuzda kimse bu özelliği kullanamaz.

    ![Tümü devre dışı ayarı](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

* **Tüm kuruluş için etkinleştirildi**: Kuruluşunuzdaki herkes bu özelliği kullanabilir.

    ![Tümü etkin ayarı](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

* **Kuruluşun bir alt kümesi için etkinleştirildi**: Kuruluşunuzdaki kullanıcıların veya grupların belirli bir alt kümesi bu özelliği kullanabilir.

    Özelliği, belirli bir kullanıcı grubunu hariç tutarak tüm kuruluşunuz için etkinleştirebilirsiniz.

    ![Alt küme etkin ayarı](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

    Ayrıca özelliği yalnızca belirli bir kullanıcı grubu için etkinleştirip başka bir kullanıcı grubu için devre dışı bırakabilirsiniz. Bu yaklaşımın kullanılması, izin verilen grupta olsalar bile belirli kullanıcıların özelliğe erişmemesini sağlar.

    ![Hariç tutarak etkinleştirme ayarı](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

Aşağıdaki bölümlerde kiracı ayarlarının farklı türleri için genel bakışa yer verilmiştir.

## <a name="workspace-settings"></a>Çalışma alanı ayarları

### <a name="create-workspaces-preview"></a>Çalışma alanı oluşturma (önizleme)

Kuruluştaki kullanıcılar uygulama çalışma alanı oluşturarak pano, rapor ve diğer içerikler üzerinde işbirliği yapabilir. [Daha fazla bilgi](service-create-the-new-workspaces.md)

## <a name="export-and-sharing-settings"></a>Dışarı aktarma ve paylaşım ayarları

### <a name="share-content-to-external-users"></a>Dış kullanıcılarla içerik paylaşma

Kuruluştaki kullanıcılar, kuruluş dışındaki kullanıcılarla pano paylaşabilir. [Daha fazla bilgi](service-share-dashboards.md#share-a-dashboard-or-report-with-people-outside-your-organization)

![Dış kullanıcılar ayarı](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

Aşağıdaki resimde bir dış kullanıcıyla paylaştığınızda görünen ileti gösterilir.

![Dış kullanıcıyla paylaşma](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Web'de yayımla

Kuruluştaki kullanıcılar web'de rapor yayımlayabilir. [Daha fazla bilgi](service-publish-to-web.md)

Aşağıdaki resimde **Web’de yayımla** ayarı etkinleştirildiğinde raporun **Dosya** menüsü gösterilir.

![Web’de yayımla ayarı](media/service-admin-portal/powerbi-admin-publish-to-web.png)

Kullanıcılar **Web’de yayımla** ayarına göre kullanıcı arabiriminde farklı seçeneklerle karşılaşır.

|Öne çıkan özelliği |Tüm kuruluş için etkindir |Tüm kuruluş için devre dışıdır |Belirli güvenlik grupları   |
|---------|---------|---------|---------|
|Rapora ilişkin **Dosya** menüsündeki **Web'de yayımla** seçeneği.|Tüm kullanıcılar için etkindir|Herkes için görünmez|Yalnızca yetkili kullanıcılar veya gruplar için görünür.|
|**Ayarlar** bölümündeki **Ekleme kodlarını yönet** seçeneği|Tüm kullanıcılar için etkindir|Tüm kullanıcılar için etkindir|Tüm kullanıcılar için etkindir<br><br>* **Sil** seçeneği yalnızca yetkili kullanıcılar veya gruplar için görünür.<br>* **Kod al** seçeneği tüm kullanıcılar için etkindir.|
|Yönetici portalındaki **Ekleme kodları** seçeneği|Durum olarak şunlardan biri görüntülenir:<br>* Etkin<br>* Desteklenmiyor<br>* Engellendi|Durum **Devre dışı** görünür|Durum olarak şunlardan biri görüntülenir:<br>* Etkin<br>* Desteklenmiyor<br>* Engellendi<br><br>Bir kullanıcı, kiracı ayarına göre yetkilendirilmemişse durum, **İhlal edildi** olarak görüntülenir.|
|Mevcut yayımlanmış raporlar|Tümü etkindir|Tümü devre dışıdır|Raporlar tüm kullanıcılar için görünür olmaya devam eder.|

### <a name="export-data"></a>Verileri dışarı aktar

Kuruluştaki kullanıcılar, bir kutucuktaki veya görselleştirmedeki verileri dışarı aktarabilir. [Daha fazla bilgi](visuals/power-bi-visualization-export-data.md)

Aşağıdaki resimde kutucuktaki verileri dışarı aktarma seçeneği gösterilir.

![Bir kutucuktaki verileri dışarı aktarma](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> **Verileri dışarı aktar** seçeneğinin devre dışı bırakılması, kullanıcıların **Excel'de Çözümle** özelliğini ve Power BI hizmeti canlı bağlantısını kullanmasını da önler.

### <a name="export-reports-as-powerpoint-presentations"></a>Raporları PowerPoint sunumları olarak dışarı aktarma

Kuruluştaki kullanıcılar Power BI raporlarını PowerPoint dosyaları olarak dışarı aktarabilir. [Daha fazla bilgi](consumer/end-user-powerpoint.md)

Aşağıdaki resimde **Raporları PowerPoint sunuları olarak dışarı aktar** ayarı etkinleştirildiğinde raporun **Dosya** menüsü gösterilir.

![Raporları PowerPoint sunumları olarak dışarı aktarma](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Panoları ve raporları paylaşma

Kuruluştaki kullanıcılar panoları ve raporları yazdırabilir. [Daha fazla bilgi](consumer/end-user-print.md)

Aşağıdaki görüntüde panoya yazdırma seçeneği gösterilmiştir.

![Panoyu yazdır](media/service-admin-portal/powerbi-admin-print-dashboard.png)

Aşağıdaki görüntüde **Panoları ve raporları yazdırın** ayarı etkinleştirildiğinde raporun **Dosya** menüsü gösterilmiştir.

![Rapor yazdırma](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-and-app-settings"></a>İçerik paketi ve uygulama ayarları

### <a name="publish-content-packs-and-apps-to-the-entire-organization"></a>Kuruluşun tamamına içerik paketi ve uygulama yayımlanması devre dışı bırakıldı

Kuruluştaki kullanıcılar, belirli gruplar yerine kuruluşun tamamına içerik paketleri ve uygulamalar yayımlayabilir. [Daha fazla bilgi](service-organizational-content-pack-manage-update-delete.md)

Aşağıdaki görüntüde içerik paketi oluşturma sırasında **Tüm kuruluşum** seçeneği gösterilmiştir.

![Kuruluşa içerik paketi yayımlama](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs-and-apps"></a>Kuruluş için şablon içerik paketleri ve uygulamalar oluşturun

Kuruluştaki kullanıcılar Power BI Desktop'ta oluşturulan veri kümelerini kullanan içerik paketi şablonları oluşturabilir. [Daha fazla bilgi](template-content-pack-authoring.md)

### <a name="push-apps-to-end-users"></a>Son kullanıcılara uygulama gönderme

Kullanıcılar AppSource'tan yüklemeye gerek kalmadan uygulamaları son kullanıcılarla doğrudan paylaşabilir. [Daha fazla bilgi](service-create-distribute-apps.md)

## <a name="integration-settings"></a>Tümleştirme ayarları

### <a name="ask-questions-about-data-using-cortana"></a>Cortana'yı kullanarak veriler hakkında soru sorma

Kuruluştaki kullanıcılar Cortana'yı kullanarak verileri hakkında sorular sorabilir. [Daha fazla bilgi](service-cortana-enable.md)

> [!NOTE]
> Bu ayar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Şirket içi veri kümeleriyle Excel'de Çözümle özelliğini kullanma

Kuruluştaki kullanıcılar Excel'i kullanarak şirket içi Power BI veri kümelerini görüntüleyebilir ve bunlarla etkileşime geçebilir. [Daha fazla bilgi](service-analyze-in-excel.md)

> [!NOTE]
> **Verileri dışarı aktar** seçeneğinin devre dışı bırakılması, kullanıcıların **Excel'de Çözümle** özelliğini kullanmasını da engeller.

### <a name="use-arcgis-maps-for-power-bi"></a>ArcGIS Maps for Power BI kullanma

Kuruluştaki kullanıcılar, Esri tarafından sağlanan ArcGIS Maps for Power BI kullanılabilir. [Daha fazla bilgi](visuals/power-bi-visualization-arcgis.md)

### <a name="use-global-search-for-power-bi-preview"></a>Power BI için genel aramayı kullanma (Önizleme)

Kuruluşunuzdaki kullanıcılar, Azure Search kullanan dış arama özelliklerinden yararlanabilir. Örneğin, kullanıcılar Cortana’yı kullanarak Power BI panolarındaki ve raporlarındaki önemli bilgileri doğrudan alabilir. [Daha fazla bilgi](service-cortana-intro.md)

## <a name="custom-visuals-settings"></a>Özel görsel ayarları

### <a name="enable-custom-visuals-for-the-entire-organization"></a>Kuruluşun tamamı için özel görsel öğeleri etkinleştirme

Kuruluştaki kullanıcılar özel görsel öğelerle etkileşime geçebilir ve bunları paylaşabilir. [Daha fazla bilgi](power-bi-custom-visuals.md)

> [!NOTE]
> Bu ayar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

## <a name="r-visuals-settings"></a>R görseli ayarları

### <a name="interact-with-and-share-r-visuals"></a>R görselleriyle etkileşim kur ve bunları paylaş

Kuruluştaki kullanıcılar R betikleri ile oluşturulan görsellerle etkileşime geçebilir ve bunları paylaşabilir. [Daha fazla bilgi](visuals/service-r-visuals.md)

> [!NOTE]
> Bu ayar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

## <a name="audit-and-usage-settings"></a>Denetim ve kullanım ayarları

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>İç etkinlik denetimi ve uyumluluk için denetim günlükleri oluştur

Kuruluştaki kullanıcılar, Power BI'da kuruluştaki diğer kullanıcılar tarafından gerçekleştirilen eylemleri izlemek için denetim özelliğini kullanabilir. [Daha fazla bilgi](service-admin-auditing.md)

Denetim günlüğü girişlerinin kaydedilmesi için bu ayarın etkinleştirilmesi gerekir. Denetimin etkinleştirilmesi ile denetim verilerinin görüntülenebilmesi arasında 48 saate kadar gecikme olabilir. Verileri hemen göremiyorsanız denetim günlüklerini daha sonra denetleyin. Denetim günlüklerini görüntüleme izni alma ile günlüklere erişebilme arasında da benzer bir gecikme olabilir.

> [!NOTE]
> Bu ayar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

### <a name="usage-metrics-for-content-creators"></a>İçerik oluşturucuları için kullanım ölçümleri

Kuruluştaki kullanıcılar oluşturdukları pano ve raporlar için kullanım ölçümlerini görebilir. [Daha fazla bilgi](service-usage-metrics.md)

### <a name="per-user-data-in-usage-metrics-for-content-creators"></a>İçerik oluşturucuları için kullanım ölçümlerinde kullanıcı başına veriler

İçerik oluşturucuları için kullanım ölçümleri, içeriğe erişen kullanıcıların görünen adlarını ve e-posta adreslerini açığa çıkarır. [Daha fazla bilgi](service-usage-metrics.md)

Varsayılan olarak, kullanım ölçümleri için kullanıcı başına veriler etkinleştirilir ve içerik oluşturucunun hesap bilgileri ölçüm raporuna eklenir. Kullanıcılardan bazıları veya tümü için bu bilgilerin eklenmesini istemezsiniz, belirtilen güvenlik grupları veya kuruluşun tamamı için özelliği devre dışı bırakın. Bu durumda hesap bilgileri raporda *Adsız* olarak gösterilir.

## <a name="dashboard-settings"></a>Pano ayarları

### <a name="data-classification-for-dashboards"></a>Panolar için veri sınıflandırması

Kuruluştaki kullanıcılar, pano güvenlik düzeyleri belirten sınıflandırmalarla panoları etiketleyebilir. [Daha fazla bilgi](service-data-classification.md)

> [!NOTE]
> Bu ayar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

## <a name="developer-settings"></a>Geliştirici ayarları

### <a name="embed-content-in-apps"></a>Uygulamalara içerik ekleme

Kuruluştaki kullanıcılar Hizmet Olarak Yazılım (SaaS) uygulamalarına Power BI panoları ve raporları ekleyebilir. Bu ayarın devre dışı bırakılması; kullanıcıların, uygulamalarına Power BI içeriği eklemek için REST API'lerini kullanabilmesini önler. [Daha fazla bilgi](developer/embedding.md)

## <a name="workspaces-and-import-settings"></a>Çalışma alanları ve içeri aktarma ayarları

### <a name="author-content-in-workspaces"></a>Çalışma alanlarında yazar içeriği

Kuruluştaki kullanıcılar veri ve yazar içeriğine bağlanmak için çalışma alanlarına erişebilir. [Daha fazla bilgi](service-create-the-new-workspaces.md)

### <a name="import-data-into-power-bi"></a>Power BI'a veri aktarma

Kuruluştaki kullanıcılar Power BI Desktop'tan rapor yayımlama, Power BI rapor dosyalarını karşıya yükleme ve doğrudan hizmetten verilere bağlanma gibi hizmete veri aktarma işlemleri gerçekleştirebilir. [Daha fazla bilgi](desktop-upload-desktop-files.md)

## <a name="dataflow-settings-preview"></a>Veri akışı ayarları (önizleme)

### <a name="create-and-use-dataflows-preview"></a>Veri akışları oluşturma ve kullanma (önizleme)

Kuruluştaki kullanıcılar veri akışları oluşturabilir ve kullanabilir. Veri akışlarına yönelik bir genel bakış için bkz. [Power BI’da self servis veri hazırlığı (Önizleme)](service-dataflows-overview.md). Premium kapasitede veri akışlarını etkinleştirmek için bkz. [İş yüklerini yapılandırma](service-admin-premium-manage.md#configure-workloads).

> [!NOTE]
> Bu ayar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

## <a name="capacity-settings"></a>Güvenlik ayarları

### <a name="power-bi-premium"></a>Power BI Premium

**Power BI Premium** sekmesi, kuruluşunuz için satın alınan Power BI Premium kapasitelerini (EM veya P SKU) yönetmenize olanak tanır. Kuruluşunuzdaki tüm kullanıcılar **Power BI Premium** sekmesini görebilir ancak yalnızca *Kapasite yöneticisi* olarak atanan veya atama izinlerine sahip kullanıcılar sekme içeriğini görebilir. Bir kullanıcı, izinlerden herhangi birine sahip olmaması durumunda aşağıdaki ileti görüntülenir.

![Premium ayarlarına erişim yok](media/service-admin-portal/premium-settings-no-access.png)

Premium ayarlarını yönetme hakkında daha fazla bilgi için bkz. [Power BI Premium'u yönetme](service-admin-premium-manage.md).

### <a name="power-bi-embedded"></a>Power BI Embedded

**Power BI Embedded** sekmesi, müşteriniz için satın aldığınız Power BI Embedded (A SKU) kapasitelerini görüntülemenizi sağlar. A SKU'ları yalnızca Azure'dan satın alabileceğiniz için [Power BI Embedded kapasitelerini yönetmek için](developer/azure-pbie-create-capacity.md) **Azure portalı** kullanabilirsiniz.

Power BI Embedded (A SKU) ayarlarını yönetme hakkında daha fazla bilgi için bkz. [Power BI Embedded nedir?](developer/azure-pbie-what-is-power-bi-embedded.md)

## <a name="embed-codes"></a>Ekleme kodları

Bir yönetici olarak, kiracınız için oluşturulan ekleme kodlarını görüntüleyebilirsiniz. Ayrıca kodları iptal edebilir veya silebilirsiniz. [Daha fazla bilgi](service-publish-to-web.md)

![Power BI yönetici portalındaki ekleme kodları](media/service-admin-portal/embed-codes.png)

## <a name="organizational-visuals"></a>Kuruluş görselleri

**Kuruluş görselleri** sekmesi, kuruluşunuzda özel görseller dağıtmanızı ve bunları yönetmenizi sağlar. Kuruluş görsellerini kullanarak kuruluşunuzda kolayca özel görseller dağıtabilirsiniz. Rapor yazarları Power BI Desktop'ta bu görselleri bulabilir ve raporlarına aktarabilir. [Daha fazla bilgi](power-bi-custom-visuals-organization.md)

> [!WARNING]
> Özel görseller güvenlik veya gizlilik riski taşıyan kodlar içerebileceğinden, özel görseli kuruluş deponuza dağıtmadan önce görselin yazarına ve kaynağına güvendiğinizden emin olun.

Aşağıdaki görüntüde, bir kuruluş deposunda dağıtılmış olan tüm özel görseller gösterilmiştir.

![Kuruluş yöneticisi görseli](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>Yeni özel görsel ekleme

Listeye yeni bir özel görsel eklemek için aşağıdaki adımları izleyin. 

1. Sağ taraftaki bölmede **Özel görsel ekle**'yi seçin.

    ![Özel görsel formu](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

1. **Özel görsel ekle** formunu doldurun:

    * **Bir .pbiviz dosyası seçin** (gerekli): Karşıya yüklemek üzere bir özel görsel dosyasını seçin. Yalnızca sürümü tutulan API özel görselleri desteklenir (bunun ne anlama geldiğini buradan öğrenebilirsiniz).

    Bir özel görseli karşıya yüklemeden önce görselin kuruluşunuzun standartlarına uygun olduğundan emin olmak için görseli güvenlik ve gizlilik bakımından gözden geçirmeniz gerekir.

    * **Özel görselinizi adlandırın** (gerekli): Power BI Desktop kullanıcılarının görselin ne işe yaradığını anlayabilmesi için görsele kısa bir başlık verin

    * **Simge**: Power BI Desktop kullanıcı arabiriminde gösterilen simge dosyası.

    * **Açıklama**: Kullanıcıya daha fazla bağlam bilgisi ve eğitim sağlanması için görselin kısa bir açıklaması

1. Karşıya yükleme isteğini başlatmak için **Ekle**'yi seçin. İşlem başarılı olursa yeni öğeyi listede görürsünüz. Başarısız olursa, uygun bir hata iletisi alabilirsiniz

### <a name="delete-a-custom-visual-from-the-list"></a>Özel bir görseli listeden silme

Bir görseli kalıcı olarak silmek için depoda görsele ait çöp kutusu simgesini seçin.

> [!IMPORTANT]
> Silme işlemi geri alınamaz. Görsel silindikten hemen sonra mevcut raporlarda gösterilmemeye başlar. Aynı görseli yeniden yükleseniz dahi silinmiş olanın yerini almaz. Ancak kullanıcılar yeni görseli yeniden içeri aktararak raporlarındaki örneği yenisiyle değiştirebilir.

### <a name="disable-a-custom-visual-in-the-list"></a>Özel bir görseli listeden devre dışı bırakma

Kuruluş deposundaki bir görseli devre dışı bırakmak için dişli simgesini seçin. **Erişim** bölümünde özel görseli devre dışı bırakın.

Devre dışı bıraktığınız görseller var olan raporlarda işlenmez ve aşağıdaki hata iletisi görüntülenir.

*Bu özel görsel artık kullanılamıyor. Ayrıntılar için lütfen yöneticinizle iletişime geçin.*

Ancak yer işaretlerine eklenmiş olan görseller çalışmaya devam eder.

Güncelleştirmeler veya yönetici tarafından gerçekleştirilen değişikliklerden sonra Power BI Desktop kullanıcılarının güncelleştirmeleri görmek için uygulamayı yeniden başlatması veya Power BI hizmeti için tarayıcıyı yenilemesi gerekir.

### <a name="update-a-visual"></a>Karşıya görsel yükleme

Kuruluş deposundaki bir görseli güncelleştirmek için dişli simgesini seçin. Görselin yeni sürümüne göz atın ve karşıya yükleyin.

Görsel Kimliğinin değişmediğinden emin olun. Yeni dosya, kuruluşunuz genelinde tüm raporların önceki dosyasının yerini alır. Ancak görselin yeni sürümü, görselin önceki sürümünün kullanımını veya veri yapısını bozabilirse, önceki sürümü değiştirmeyin. Bunun yerine, görselin yeni sürümü için yeni bir liste oluşturmanız gerekir. Örneğin, yeni listelenen görselin başlığına yeni bir sürüm numarası (X.X sürümü) ekleyin. Böylece bunun güncelleştirilmiş sürüm numarasına sahip aynı görsel olduğu açıkça görülmektedir; bu nedenle mevcut raporların işlevi bozulmaz. Görsel Kimliğinin değişmediğinden emin olun. Daha sonra kullanıcılar, Power BI Desktop’tan kuruluş deposuna bir sonraki girişlerinde yeni sürümü içeri aktarabilir ve bunu yaptıklarında rapordaki mevcut sürümün değiştirilmesini isteyip istemedikleri sorulur.

Daha fazla bilgi edinmek için [kurumsal özel görseller hakkında sık sorulan sorular](https://docs.microsoft.com/en-us/power-bi/power-bi-custom-visuals-faq#organizational-custom-visuals) bağlantısını ziyaret edin

## <a name="dataflow-storage-preview"></a>Veri akışı depolama (önizleme)

Varsayılan olarak, Power BI ile kullanılan veriler, Power BI tarafından sağlanan iç depolama alanında depolanır. Veri akışları ve Azure Data Lake Storage 2. Nesil (ADLS 2. Nesil) tümleştirmesi ile, kuruluşunuzun Azure Data Lake Storage 2. Nesil hesabında veri akışlarınızı depolayabilirsiniz. Daha fazla bilgi için bkz. [Veri akışları ve Azure Data Lake tümleştirmesi (Önizleme)](service-dataflows-azure-data-lake-integration.md)

## <a name="workspaces-preview"></a>Çalışma alanları (önizleme)

Bir yönetici olarak, kiracınızda bulunan çalışma alanlarını görebilirsiniz. Çalışma alanları listesini filtreleyebilir, sıralayabilir ve her çalışma alanının ayrıntılarını görüntüleyebilirsiniz. Tablo sütunlarının, çalışma alanları için [Power BI yönetimi Rest API](/rest/api/power-bi/admin) tarafından döndürülen özelliklere karşılık geldiğini unutmayın. Kişisel çalışma alanları **PersonalGroup** türünde, eski çalışma alanları **Group** türünde ve modern çalışma alanları da **Workspace** türündedir. Daha fazla bilgi için bkz. [Power BI'da yeni çalışma alanları oluşturma (önizleme)](service-create-the-new-workspaces.md).

![Çalışma alanları listesi](media/service-admin-portal/workspaces-list.png)

## <a name="next-steps"></a>Sonraki adımlar

[Kuruluşunuzda BI'ı yönetme](service-admin-administering-power-bi-in-your-organization.md)  [Power BI yönetici rolünü anlama](service-admin-role.md)  
[Kuruluşunuzda Power BI'ı denetleme](service-admin-auditing.md)  
[Power BI Premium'u yönetme](service-admin-premium-manage.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
