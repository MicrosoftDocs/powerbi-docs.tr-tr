---
title: "Power BI yönetici portalı"
description: "Yönetici portalı, kuruluşunuzda Power BI kiracı yönetimine olanak sağlar. Kullanım ölçümleri, Office 365 yönetim merkezine erişim ve ayarlar gibi öğeleri içerir."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/02/2018
ms.author: maghan
ms.openlocfilehash: 36f2b591f53e7d9e930048cdedde114348466147
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-admin-portal"></a>Power BI yönetici portalı

Yönetici portalı, kuruluşunuzda Power BI kiracı yönetimine olanak sağlar. Kullanım ölçümleri, Office 365 yönetim merkezine erişim ve ayarlar gibi öğeleri içerir.

Şirketiniz için Power BI kiracı yönetimi, Power BI yönetici portalı üzerinden gerçekleştirilir. Yönetim portalı, Office 365'te Genel Yönetici olan veya kendilerine Power BI hizmet yöneticisi rolü atanmış tüm kullanıcılar için erişilebilir durumdadır. Power BI hizmet yöneticisi rolü hakkında daha fazla bilgi için bkz. [Power BI yönetici rolünü anlama](service-admin-role.md).

Tüm kullanıcılar dişli simgesinin altında **Yönetici portalını** görür. Yönetici değillerse yalnızca **Premium ayarları** bölümünü ve yönetme hakkına sahip oldukları kapasiteleri görürler.

## <a name="how-to-get-to-the-admin-portal"></a>Yönetici portalına ulaşma

Power BI yönetici portalına erişim elde etmek için hesabınızın Office 365 veya Azure Active Directory'de **Genel Yönetici** olarak işaretlenmesi veya size Power BI hizmet yöneticisi rolünün atanması gerekir. Power BI hizmet yöneticisi rolü hakkında daha fazla bilgi için bkz. [Power BI yönetici rolünü anlama](service-admin-role.md). Power BI yönetici portalına ulaşmak için aşağıdakileri yapın.

1. Power BI hizmetinin sağ üst tarafındaki ayarlar dişli simgesini seçin.
2. **Yönetici portalı**'nı seçin.

![](media/service-admin-portal/powerbi-admin-settings.png)

Portalda beş sekme bulunur. Bunlar aşağıda açıklanmıştır.

* [Kullanım ölçümleri](#usage-metrics)
* [Kullanıcılar](#users)
* [Denetim günlükleri](#audit-logs)
* [Kiracı ayarları](#tenant-settings)
* [Premium ayarları](#premium-settings)
* [Ekleme kodları](#embed-codes)

![](media/service-admin-portal/powerbi-admin-landing-page.png)

## <a name="usage-metrics"></a>Kullanım ölçümleri
Yönetici portalındaki ilk sekme **Kullanım ölçümleri**'dir. Kullanım ölçümleri raporu, kuruluşunuz için Power BI'daki kullanımı izleyebilmenizi sağlar. Ayrıca kuruluşunuz için Power BI'da en etkin olan kullanıcıları ve grupları görme olanağı da sunar.

> [!NOTE]
> Panoya ilk kez eriştiğinizde veya panoyu görüntülemeniz üzerinden uzun bir süre geçtikten sonra panoyu tekrar ziyaret ettiğinizde, biz panoyu yüklerken büyük olasılıkla bir yükleme ekranıyla karşılaşırsınız.

Pano yüklendikten sonra iki kutucuk bölümü görürsünüz. İlk bölüm, farklı kullanıcılar hakkındaki kullanım verilerini, ikinci bölüm ise kuruluşunuzdaki gruplara yönelik benzer bilgileri içerir.

Aşağıda, her kutucukta neler göreceğinize ilişkin bir döküm verilmiştir:

* Kullanıcı çalışma alanındaki tüm panoların, raporların ve veri kümelerinin ayrı sayımı
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* Erişebilen kullanıcıların sayısına göre en fazla kullanılan pano. Örneğin, 3 kullanıcıyla paylaştığınız bir pano varsa ve bu panoyu iki farklı kullanıcının bağlı olduğu bir içerik paketine de eklediyseniz panonun sayımı 6 (1 + 3 + 2) şeklinde olur
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* Kullanıcıların bağlı olduğu en popüler içerikler. Bu, kullanıcıların Veri Al işlemiyle ulaşabileceği herhangi bir şey (SaaS içerik paketleri, Kurumsal içerik paketleri, dosyalar veya veritabanları) olabilir.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* En fazla panoya sahip (hem kendi oluşturdukları hem de kendileriyle paylaşılan panolar) kullanıcılarınızın bir görünümü.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* En fazla rapora sahip kullanıcılarınızın bir görünümü
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

İkinci bölüm aynı türde bilgileri grup temelinde gösterir. Bu, kuruluşunuzdaki en etkin grupları ve bu grupların kullandığı bilgi türünü öğrenmenize olanak tanır.

Bu bilgilerle kişilerin kuruluşunuzdaki Power BI'ı nasıl kullandığına ilişkin gerçek öngörüler elde edebilir ve kuruluşunuzda oldukça etkin olan bu kullanıcıları ve grupları tanıyabilirsiniz.

## <a name="users"></a>Kullanıcılar

Yönetici portalındaki ikinci sekme **Kullanıcıları Yönet**'tir. Power BI için kullanıcı yönetimi Office 365 yönetim merkezinde gerçekleştirilir; bu nedenle bu bölüm, Office 365'te kullanıcıları, yöneticileri ve grupları yönetme alanına hızlıca ulaşmanıza olanak tanır.

![](media/service-admin-portal/powerbi-admin-manage-users.png)

**O365 Yönetim Merkezi'ne git** seçeneğine tıkladığınızda, doğrudan kiracınızın kullanıcılarını yönetebileceğiniz Office 365 yönetim merkezi giriş sayfasına yönlendirilirsiniz.

![](media/service-admin-portal/powerbi-admin-o365-admin-center.png)

## <a name="audit-logs"></a>Denetim günlükleri

Yönetici portalındaki üçüncü sekme **Denetim günlükleri**'dir. Günlükler Office 365 Güvenlik ve Uyumluluk Merkezi'nde yer alır. Bu bölüm, Office 365'te bu alana hızlıca erişmenizi sağlar. 

Denetim günlükleri hakkında daha fazla bilgi için bkz. [Kuruluşunuzda Power BI'ı denetleme](service-admin-auditing.md)

## <a name="tenant-settings"></a>Kiracı ayarları

Yönetici portalındaki üçüncü sekme **Kiracı ayarları**'dır. Kiracı ayarları, kuruluşunuzda hangi özelliklerin kullanılabildiğiyle ilgili olarak size daha fazla denetim verir. Gizli verilerle ilgili endişeleriniz varsa, sunduğumuz bazı özellikler kuruluşunuz için uygun olmayabilir veya belirli bir özelliğin yalnızca belirli bir grubun kullanımına sunulmasını isteyebilirsiniz. Bu durumda, söz konusu seçeneği kiracınızda kapatabilirsiniz.

![](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> Ayarın kiracınızdaki herkes için geçerli olması 10 dakika kadar sürebilir.

Ayarlar, seçimlerinize bağlı olarak üç duruma sahip olabilir.

### <a name="disabled-for-the-entire-organization"></a>Tüm kuruluş için devre dışı bırakıldı

Bir özelliği devre dışı bırakabilir ve kullanıcıların kullanamayacağı hale getirebilirsiniz.

![](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

### <a name="enabled-for-the-entire-organization"></a>Tüm kuruluş için etkinleştirildi

Bir özelliği kuruluşun tamamı için etkinleştirebilirsiniz; bu, tüm kullanıcıların bu özelliğe erişmesine olanak tanır.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

### <a name="enabled-for-a-subset-of-the-organization"></a>Kuruluşun bir alt kümesi için etkinleştirildi

Bir özelliği kuruluşunuzun belirli bir kısmı için de etkinleştirebilirsiniz. Bu, birkaç farklı şekilde gerçekleşebilir. Özelliği, belirli bir kullanıcı grubunu hariç tutarak tüm kuruluşunuz için etkinleştirebilirsiniz.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

Ayrıca özelliği yalnızca belirli bir kullanıcı grubu için etkinleştirip başka bir kullanıcı grubu için devre dışı bırakabilirsiniz. Bu, izin verilen grupta olsalar dahi belirli kullanıcıların özelliğe erişmemesini sağlar.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

## <a name="export-and-sharing-settings"></a>Dışarı aktarma ve paylaşım ayarları

### <a name="share-content-to-external-users"></a>Dış kullanıcılarla içerik paylaşma

Kuruluştaki kullanıcılar, kuruluş dışındaki kullanıcılarla pano paylaşabilir.

![](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Web'de yayımlama

Kuruluştaki kullanıcılar web'de rapor yayımlayabilir. [Daha fazla bilgi](service-publish-to-web.md)

![](media/service-admin-portal/powerbi-admin-publish-to-web.png)

Kullanıcılar, web'de yayımlama ayarına göre kullanıcı arabiriminde farklı seçeneklerle karşılaşır.

|Öne çıkan özelliği |Tüm kuruluş için etkindir |Tüm kuruluş için devre dışıdır |Belirli güvenlik grupları   |
|---------|---------|---------|---------|
|Rapora ilişkin **Dosya** menüsündeki **Web'de yayımla** seçeneği.|Tüm kullanıcılar için etkindir|Hiçbir kullanıcı için görünmez|Yalnızca yetkili kullanıcılar veya gruplar için görünür.|
|**Ayarlar** bölümündeki **Ekleme kodlarını yönet** seçeneği|Tüm kullanıcılar için etkindir|Tüm kullanıcılar için etkindir|Tüm kullanıcılar için etkindir<br><br>* **Sil** seçeneği yalnızca yetkili kullanıcılar veya gruplar için görünür.<br>* **Kod al** seçeneği tüm kullanıcılar için etkindir.|
|Yönetici portalındaki **Ekleme kodları** seçeneği|Durum olarak şunlardan biri görüntülenir:<br>* Etkin<br>* Desteklenmiyor<br>* Engellendi|Durum olarak **Devre dışı** görüntülenir|Durum olarak şunlardan biri görüntülenir:<br>* Etkin<br>* Desteklenmiyor<br>* Engellendi<br><br>Bir kullanıcı, kiracı ayarına göre yetkilendirilmemişse durum, **İhlal edildi** olarak görüntülenir.|
|Mevcut yayımlanmış raporlar|Tümü etkindir|Tümü devre dışıdır|Raporlar tüm kullanıcılar için görünür olmaya devam eder.|

### <a name="export-data"></a>Verileri dışarı aktarma

Kuruluştaki kullanıcılar, bir kutucuktaki veya görselleştirmedeki verileri dışarı aktarabilir. [Daha fazla bilgi](power-bi-visualization-export-data.md)

![](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> **Verileri dışarı aktar** seçeneğinin devre dışı bırakılması, kullanıcıların **Excel'de Çözümle** özelliğini ve Power BI hizmeti canlı bağlantısını kullanmasını da önler.

### <a name="export-reports-as-powerpoint-presentations"></a>Raporları PowerPoint sunumları olarak dışarı aktarma

Kuruluştaki kullanıcılar Power BI raporlarını PowerPoint dosyaları olarak dışarı aktarabilir. [Daha fazla bilgi](service-publish-to-powerpoint.md)

![](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Panoları ve raporları paylaşma

Kuruluştaki kullanıcılar panoları ve raporları yazdırabilir. [Daha fazla bilgi](service-print.md)

![](media/service-admin-portal/powerbi-admin-print-dashboard.png)

![](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-settings"></a>İçerik paketi ayarları

### <a name="publish-content-packs-to-the-entire-organization"></a>İçerik paketlerini kuruluş genelinde yayımlama

Kuruluştaki kullanıcılar içerik paketlerini kuruluşun tamamında yayımlayabilir.

![](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs"></a>Kurumsal içerik paketi şablonu oluşturma

Kuruluştaki kullanıcılar Power BI Desktop'taki bir veri kaynağı üzerinde oluşturulan veri kümelerini kullanan içerik paketi şablonları oluşturabilir.

## <a name="integration-settings"></a>Tümleştirme ayarları

### <a name="ask-questions-about-data-using-cortana"></a>Cortana'yı kullanarak veriler hakkında soru sorma
Kuruluştaki kullanıcılar Cortana'yı kullanarak verileri hakkında sorular sorabilir.

> [!NOTE]
> Bu ayarlar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Şirket içi veri kümeleriyle Excel'de Çözümle özelliğini kullanma
Kuruluştaki kullanıcılar Excel'i kullanarak şirket içi Power BI veri kümelerini görüntüleyebilir ve bunlarla etkileşime geçebilir. [Daha fazla bilgi ](service-analyze-in-excel.md)

> [!NOTE]
> **Verileri dışarı aktar** seçeneğinin devre dışı bırakılması, kullanıcıların **Excel'de Çözümle** özelliğini kullanmasını da engeller.

### <a name="user-arcgis-maps-for-power-bi-preview"></a>ArcGIS Maps for Power BI'ı (Önizleme) kullanma

Kuruluştaki kullanıcılar Esri tarafından sağlanan ArcGIS Maps for Power BI'ı (Önizleme) kullanabilir. [Daha fazla bilgi](power-bi-visualization-arcgis.md)


## <a name="custom-visuals-settings"></a>Özel görsel ayarları
### <a name="enable-custom-visuals-for-the-entire-organization"></a>Kuruluşun tamamı için özel görsel öğeleri etkinleştirme
Kuruluştaki kullanıcılar özel görsel öğelerle etkileşime geçebilir ve bunları paylaşabilir. [Daha fazla bilgi](power-bi-custom-visuals.md)

![Özel görsel ayarları](media/service-admin-portal/powerbi-admin-custom-visuals.png)

> [!NOTE]
> Bu ayar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

## <a name="r-visuals-settings"></a>R görseli ayarları

### <a name="interact-with-an-dshare-r-visuals"></a>R görselleriyle etkileşime geçme ve bunları paylaşma

Kuruluştaki kullanıcılar R betikleri ile oluşturulan görsellerle etkileşime geçebilir ve bunları paylaşabilir. [Daha fazla bilgi](service-r-visuals.md)

> [!NOTE]
> Bu ayarlar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

## <a name="audit-settings"></a>Denetim ayarları

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>İç etkinlik denetimi ve uyumluluk için denetim günlükleri oluşturma

Kuruluştaki kullanıcılar, Power BI'da kuruluştaki diğer kullanıcılar tarafından gerçekleştirilen eylemleri izlemek için denetim özelliğini kullanabilir. [Daha fazla bilgi](service-admin-auditing.md)

Denetim günlüğü girişlerinin kaydedilmesi için bu ayarın etkinleştirilmesi gerekir.

> [!NOTE]
> Bu ayarlar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

## <a name="dashboard-settings"></a>Pano ayarları

### <a name="data-classification-for-dashboards"></a>Panolar için veri sınıflandırması

Kuruluştaki kullanıcılar, pano güvenlik düzeyleri belirten sınıflandırmalarla panoları etiketleyebilir. [Daha fazla bilgi](service-data-classification.md)

> [!NOTE]
> Bu ayarlar kuruluş genelinde geçerli olur ve belirli gruplarla sınırlanamaz.

## <a name="developer-settings"></a>Geliştirici ayarları

### <a name="embed-content-in-apps"></a>Uygulamalara içerik ekleme

Kuruluştaki kullanıcılar Hizmet Olarak Yazılım (SaaS) uygulamalarına Power BI panoları ve raporları ekleyebilir. Bu ayarın devre dışı bırakılması; kullanıcıların, uygulamalarına Power BI içeriği eklemek için REST API'lerini kullanabilmesini önler.

## <a name="premium-settings"></a>Premium ayarları

Premium ayarları sekmesi, kuruluşunuz için satın alınan Power BI Premium kapasitesini yönetmenize olanak tanır. Kuruluşunuzdaki tüm kullanıcılar Premium ayarları sekmesini görür ancak yalnızca **Kapasite yöneticisi** olarak atanan veya atama izinlerine sahip kullanıcılar sekme içeriğini görebilir. Bir kullanıcı, izinlerden herhangi birine sahip olmaması durumunda aşağıdaki iletiyle karşılaşır.

![](media/service-admin-portal/premium-settings-no-access.png "Premium ayarlarına erişim yok")

Premium ayarlarını yönetme hakkında daha fazla bilgi için bkz. [Power BI Premium'u yönetme](service-admin-premium-manage.md).

## <a name="embed-codes"></a>Ekleme kodları

![Power BI yönetici portalındaki ekleme kodları](media/service-admin-portal/embed-codes.png)

Bir yönetici olarak, kiracınız için oluşturulan ekleme kodlarını görüntüleyebilirsiniz. Raporu görüntüleme ve ekleme kodunu silerek söz konusu kodu iptal etme eylemlerini gerçekleştirebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI yönetici rolünü anlama](service-admin-role.md)  
[Kuruluşunuzda Power BI'ı denetleme](service-admin-auditing.md)  
[Power BI Premium'u yönetme](service-admin-premium-manage.md)  
[Kuruluşunuzda Power BI'ı yönetme](service-admin-administering-power-bi-in-your-organization.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)