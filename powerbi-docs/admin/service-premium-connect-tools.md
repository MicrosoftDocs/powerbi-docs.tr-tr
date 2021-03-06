---
title: Power BI'da XMLA uç noktasıyla veri kümesi bağlantısı ve yönetimi
description: İstemci uygulamaları ve araçlarından Power BI Premium veri kümelerine bağlanma işlemi açıklanmaktadır.
author: Minewiskan
ms.author: davidi
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-premium
ms.topic: how-to
ms.date: 1/11/2020
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 3a3a0f44fd9f02942ecc8f6646d219ace649b295
ms.sourcegitcommit: c86ce723d5db16fb960d1731795d84f4654e4b4e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98110775"
---
# <a name="dataset-connectivity-with-the-xmla-endpoint"></a>XMLA uç noktasıyla veri kümesi bağlantısı

1500 ve üzeri uyumluluk düzeyindeki Power BI Premium çalışma alanları ve veri kümeleri, *XMLA uç noktası* kullanarak gem Microsoft’un açık platform bağlantısını hem de üçüncü taraf istemci uygulamalarını ve araçlarını destekler.

## <a name="whats-an-xmla-endpoint"></a>XMLA uç noktası nedir?

Power BI Premium, istemci uygulamalarıyla Power BI çalışma alanınızı ve veri kümelerinizi yöneten altyapı arasında iletişimi sağlamak için [XML for Analysis](/analysis-services/xmla/xml-for-analysis-xmla-reference?view=power-bi-premium-current&preserve-view=true) (XMLA) protokolünü kullanır. Bu iletişimler genellikle XMLA olarak adlandırılan uç noktalar üzerinden gerçekleştirilir. XMLA, Microsoft Analysis Services altyapısı tarafından kullanılan iletişim protokolüyle aynıdır. Bu protokol, yakından bakıldığında Power BI’ın anlamsal modellemesi, yönetim, yaşam döngüsü ve veri yönetimini çalıştırır. XMLA protokolü üzerinden gönderilen veriler tamamen şifrelenir.

Varsayılan olarak, uç noktayı kullanan *salt okunur* bağlantı, bir kapasitedeki **Veri kümeleri iş yükü** için etkindir. Veri görselleştirme uygulamaları ve araçları, salt okunur ile veri kümesi model verilerini, meta verileri, olayları ve şemayı sorgulayabilir. Uç noktayı kullanan *okuma/yazma* işlemleri ek veri kümesi yönetimi, idare, gelişmiş anlam modelleme, hata ayıklama ve izleme sağlanarak etkinleştirilebilir. Okuma/Yazma etkinken Power BI Premium veri kümeleri, Azure Analysis Services ve SQL Server Analysis Services kurumsal düzeyde tablosal modelleme araçları ve işlemleriyle daha fazla eşliğe sahiptir.

> [!NOTE]
> Özellikle veri kümelerinize XMLA uç noktası üzerinden bağlanırken modern çalışma alanı deneyimini kullanmanız önerilir. Klasik çalışma alanlarında veri kümesi oluşturma veya silme gibi işlemler desteklenmez. Klasik çalışma alanlarını modern deneyime yükseltmek için bkz. [Power BI'da klasik çalışma alanlarını yükseltme](../collaborate-share/service-upgrade-workspaces.md).

## <a name="data-modeling-and-management-tools"></a>Veri modelleme ve yönetim araçları

Aşağıda listelenenler Azure Analysis Services ve SQL Server Analysis Services ile kullanılan en yaygın araçlardan bazılarıdır ve artık Power BI Premium veri kümeleri tarafından desteklenir:

**Analysis Services projeleri ile Visual Studio** : SQL Server Veri Araçları (veya **SSDT**) olarak da bilinen bu araçlar, Analysis Services tablosal modellere yönelik kurumsal düzeyde bir model yazma aracıdır. Analysis Services projeleri uzantıları, ücretsiz Topluluk sürümü de dahil olmak üzere tüm Visual Studio 2017 ve üzeri sürümlerde desteklenir. Tablosal modelleri bir Premium çalışma alanına dağıtmak için uzantının 2.9.14 veya üzeri sürümleri gerekir. Premium çalışma alanına dağıtırken model 1500 veya üzeri uyumluluk düzeyinde olmalıdır. XMLA okuma/yazma, veri kümeleri iş yükünde gereklidir. Daha fazla bilgi için bkz. [Analysis Services Araçları](/analysis-services/tools-and-applications-used-in-analysis-services?view=power-bi-premium-current&preserve-view=true).

**SQL Server Management Studio (SSMS)**  : DAX, MDX ve XMLA sorgularını destekler. [Tablosal Model Betik Dilini](/analysis-services/tmsl/tabular-model-scripting-language-tmsl-reference) (TMSL) kullanarak hassas yenileme işlemleri gerçekleştirin ve veri kümesi meta verilerinde betik oluşturun. Sorgu işlemleri için salt okunur bağlantı gerekir. Meta verilerin betiğini oluşturma işlemi için okuma/yazma bağlantısı gerekir. SSMS sürüm **18.8** veya üzeri gerekir.  [Buradan](/sql/ssms/download-sql-server-management-studio-ssms) indirin.

**SQL Server Profiler** : SSMS ile yüklenen bu araç, veri kümesi olayları için izleme ve hata ayıklama desteği sağlar. SQL Server için resmi olarak kullanım dışı bırakılmış olsa da Profiler SSMS’ye eklenmeye, Analysis Services ve Power BI Premium için desteklenmeye devam eder. SQL Server Profiler sürüm **18.8** veya üzeri ile XMLA salt okunur seçeneğinin Premium kapasitede etkinleştirilmiş olması gerekir. Kullanıcı, XMLA uç noktasına bağlanırken veri kümesini ([ilk katalog](#initial-catalog)) belirtmelidir. Daha fazla bilgi için bkz.  [Analysis Services için SQL Server Profiler](/analysis-services/instances/use-sql-server-profiler-to-monitor-analysis-services?view=power-bi-premium-current&preserve-view=true).

**Analysis Services Dağıtım Sihirbazı** : SSMS ile yüklenen bu araç, Visual Studio tarafından yazılan tablosal model projelerinin Analysis Services ve Power BI Premium çalışma alanlarına dağıtılmasını sağlar. Bu araç, etkileşimli olarak veya otomasyon için komut satırından çalıştırılabilir. XMLA okuma/yazma gereklidir. Daha fazla bilgi için bkz. [Analysis Services Dağıtım Sihirbazı](/analysis-services/deployment/deploy-model-solutions-using-the-deployment-wizard?view=power-bi-premium-current&preserve-view=true).

**PowerShell cmdlet’leri** : Analysis Services cmdlet’leri, yenileme işlemleri gibi veri kümesi yönetim görevlerini otomatikleştirmek için kullanılabilir. XMLA okuma/yazma gereklidir. [SqlServer PowerShell modülünün](https://www.powershellgallery.com/packages/SqlServer/) **21.1.18221** veya üzeri bir sürümü gerekir. Az.AnalysisServices modülündeki Azure Analysis Services cmdlet’leri, Power BI Premium için desteklenmez. Daha fazla bilgi için bkz. [Analysis Services PowerShell Başvurusu](/analysis-services/powershell/analysis-services-powershell-reference?view=power-bi-premium-current&preserve-view=true).

**Power BI Report Builder** : Sayfalandırılmış raporlar yazmaya yarayan bir araçtır. Hangi verilerin nereden alınacağını ve nasıl görüntüleneceğini belirten bir rapor tanımı oluşturur. Rapor Oluşturucusu’nda raporunuzun önizlemesini görüntüleyebilir, ardından raporunuzu Power BI hizmetinde yayımlayabilirsiniz. XMLA salt-okunur gereklidir. Daha fazla bilgi için bkz.  [Power BI Report Builder](../paginated-reports/report-builder-power-bi.md).

**Tablo Düzenleyicisi**: Sezgisel ve hafif bir düzenleyici kullanarak tablosal modelleri oluşturmaya, sürdürmeye ve yönetmeye yarayan açık kaynaklı bir araçtır. Tablosal modelinizdeki tüm nesneler hiyerarşik bir görünümde gösterilir. Nesneler, çoklu seçim özellik düzenlemesi ve DAX söz dizimi vurgulaması için görüntüleme klasörleri tarafından düzenlenir. Sorgu işlemleri için XMLA salt okunur gerekir. Meta veri işlemleri için okuma/yazma bağlantısı gerekir. Daha fazla bilgi için bkz. [tabulareditor.github.io](https://tabulareditor.github.io/).

**DAX Studio** : DAX yazma, tanılama, performans ayarlama ve analiz etmeye yönelik açık kaynaklı bir araçtır. Özellikler arasında nesne göz atma, tümleşik izleme, ayrıntılı istatistiklere sahip sorgu yürütme dökümleri, DAX söz dizimi vurgulama ve biçimlendirme yer alır. Sorgu işlemleri için XMLA salt okunur gerekir. Daha fazla bilgi edinmek için bkz.  [daxstudio.org](https://daxstudio.org/).

**ALM Araç Seti**: En çok uygulama yaşam döngüsü yönetimi (ALM) senaryolarında kullanılan, Power BI veri kümeleri için açık kaynaklı bir şema karşılaştırma aracıdır. Ortamlar arasında dağıtım gerçekleştirir ve artımlı yenileme geçmiş verilerini korur. Meta veri dosyalarını, dallarını ve depolarını ayırıp birleştirir. Veri kümeleri arasındaki yaygın tanımları yeniden kullanır. Sorgu işlemleri için salt okunur bağlantı gerekir. Meta veri işlemleri için okuma/yazma bağlantısı gerekir. Daha fazla bilgi için bkz.  [alm-toolkit.com](http://alm-toolkit.com/).

**Microsoft Excel** : Excel PivotTable’lar Power BI veri kümelerindeki özet verileri özetlemek, analiz etmek, bulmak ve sunmak için kullanılan en yaygın araçlardan biridir. Sorgu işlemleri için salt okunur bağlantı gerekir. Office 16.0.11326.10000 veya üzeri bir Tıkla-Çalıştır sürümü gerekir.

**Üçüncü taraf** : Power BI Premium’daki veri kümelerine bağlanabilen, bunları sorgulayıp tüketebilen istemci veri görselleştirme uygulama ve araçlarını içerir. Araçların çoğu MSOLAP istemci kitaplıklarının en son sürümlerini gerektirir ama bazıları ADOMD kullanabilir. Salt okunur veya okuma/yazma XMLA Uç Noktası, işlemlere bağımlıdır.

### <a name="client-libraries"></a>İstemci kitaplıkları

İstemci uygulamaları XMLA uç noktasıyla doğrudan iletişim kurmaz. Bunun yerine, özet düzeyi olarak *istemci kitaplıklarını* kullanırlar. Bunlar, Azure Analysis Services ve SQL Server Analysis Services’a bağlanmak için kullanılan istemci kitaplıkları uygulamalarının aynısıdır. Excel, SQL Server Management Studio (SSMS) ve Visual Studio için Analysis Services projeleri uzantısı gibi Microsoft uygulamaları, üç istemci kitaplığını da yükleyip normal uygulama ve uzantı güncelleştirmeleriyle birlikte bu kitaplıkları da güncelleştirir. Geliştiriciler de özel uygulamalar oluşturmak için istemci kitaplıklarını kullanabilir. Bazı durumlarda, özellikle üçüncü taraf uygulamalar söz konusu olduğunda, uygulamalarla yüklü gelmediyse istemci kitaplıklarının daha yeni sürümlerini yüklemeniz gerekebilir. İstemci kitaplıkları aylık olarak güncelleştirilir. Daha fazla bilgi için bkz.  [Analysis Services’a bağlanmak için istemci kitaplıkları](/azure/analysis-services/analysis-services-data-providers).

## <a name="optimize-datasets-for-write-operations-by-enabling-large-models"></a>Büyük modelleri etkinleştirerek yazma işlemleri için veri kümelerini iyileştirme

Veri kümesi yönetimi için XMLA uç noktasını yazma işlemleriyle birlikte kullanırken, veri kümesini büyük modeller için etkinleştirmeniz önerilir. Bu eylem, yazma işlemlerinin ek yükünü azaltarak onları önemli ölçüde daha hızlı hale getirir. Boyutu 1 GB’tan fazla olan veri kümelerinde (sıkıştırdıktan sonra) bu fark daha da belirgin olabilir. Daha fazla bilgi için bkz. [Power BI Premium’da büyük modeller](service-premium-large-models.md).

## <a name="enable-xmla-read-write"></a>XMLA okuma/yazmayı etkinleştirme

Varsayılan olarak, Premium kapasitede XMLA Uç Noktası özelliği ayarı salt okunurdur. Bu, uygulamaların yalnızca bir veri kümesini sorgulayabileceği anlamına gelir. Uygulamaların yazma işlemlerini gerçekleştirmesi için, XMLA Uç Noktası özelliğinin, okuma/yazma için etkinleştirilmesi gerekir. Bir kapasite için XMLA Uç Noktası özellik ayarı, **Veri kümeleri iş yükünde** yapılandırılır. XMLA Uç Noktası ayarı, kapasiteye atanan *tüm çalışma alanları ve veri kümeleri* için geçerlidir.

### <a name="to-enable-read-write-for-a-capacity"></a>Bir kapasitede okuma/yazma özelliğini etkinleştirmek için:

1. Yönetim portalında **Kapasite ayarları** > **Power BI Premium** > kapasite adını seçin.
2. **İş yüklerini** genişletin. **XMLA Uç Noktası** ayarında **Okuma/Yazma**’yı seçin.

    ![XMLA uç noktasını etkinleştirin](media/service-premium-connect-tools/xmla-endpoint-enable.png)

## <a name="connecting-to-a-premium-workspace"></a>Premium çalışma alanına bağlanma

Kapasiteye atanan çalışma alanlarının URL biçiminde bir bağlantı dizesi vardır. Örneğin:  
`powerbi://api.powerbi.com/v1.0/[tenant name]/[workspace name]`.

Çalışma alanına bağlanan uygulamalar, URL’yi Analysis Services sunucu adında olduğu gibi kullanır. Örneğin,  
`powerbi://api.powerbi.com/v1.0/contoso.com/Sales Workspace`.

Aynı kiracıdaki (B2B olmayan) UPN’ye sahip kullanıcılar, kiracı adını `myorg` ile değiştirebilir. Örneğin,  
`powerbi://api.powerbi.com/v1.0/myorg/Sales Workspace`.

B2B kullanıcılarının kiracı adında kuruluş UPN’lerini belirtmeleri gerekir. Örneğin,  
`powerbi://api.powerbi.com/v1.0/fabrikam.com/Sales Workspace`.

### <a name="to-get-the-workspace-connection-url"></a>Çalışma alanı bağlantı URL’sini almak için:

Çalışma alanında **Ayarlar** > **Premium** > **Çalışma Alanı Bağlantısı** adımlarını izleyip **Kopyala**’yı seçin.

![Çalışma alanı bağlantı dizesi](media/service-premium-connect-tools/xmla-endpoint-workspace-connection.png)

## <a name="connection-requirements"></a>Bağlantı gereksinimleri

### <a name="initial-catalog"></a>İlk katalog

SQL Server Profiler gibi araçlarda çalışma alanınızda bağlantı kurulacak olan veri kümesini (veri tabanını) ifade eden *İlk Katalog* belirtmeniz gerekir. **Sunucuya Bağlan** iletişim kutusunda **Seçenekler** > **Bağlantı Özellikleri** > **Veritabanına bağlan**'ı seçip veri kümesi adını girin.

![SQL Server Profiler'da veri kümesini seçme](media/service-premium-connect-tools/sql-profiler-connection-properties.png)

### <a name="duplicate-workspace-names"></a>Yinelenen çalışma alanı adı

Power BI’daki [Yeni çalışma alanları](../collaborate-share/service-new-workspaces.md) (yeni çalışma alanı deneyimi kullanılarak oluşturulan), yinelenen adlara sahip çalışma alanlarının oluşturulmasına veya yeniden adlandırılmasına izin vermemek için doğrulama işlemi uygular. Geçirilmeyen çalışma alanları yinelenen adlara neden olabilir. Başka bir çalışma alanıyla aynı adı taşıyan bir çalışma alanına bağlanırken şu hatayı alabilirsiniz:

**powerbi://api.powerbi.com/v1.0/[kiracı adı]/[çalışma alanı adı] bağlantısı yapılamıyor.**

Bu sorunu geçici olarak çözmek için, çalışma alanı adına ek olarak ObjectIDGuid değerini de belirtin (bu değer URL'deki çalışma alanı objectID bölümünden kopyalanabilir). objectID değerini bağlantı URL'sine ekleyin. Örneğin,  
“powerbi://api.powerbi.com/v1.0/myorg/Contoso Sales - 9d83d204-82a9-4b36-98f2-a40099093830”.

### <a name="duplicate-dataset-name"></a>Yinelenen veri kümesi adı

Aynı çalışma alanındaki başka bir veri kümesiyle aynı adı taşıyan bir veri kümesine bağlanırken, veri kümesi adının sonuna veri kümesi guid değerini ekleyin. SSMS’de çalışma alanına bağlandığınızda hem veri kümesi adını hem de GUID değerini alabilirsiniz.

### <a name="delay-in-datasets-shown"></a>Veri kümelerinin gecikmeli gösterilmesi

Çalışma alanına bağlandığınızda yeni, silinmiş ve yeniden adlandırılmış veri kümelerindeki değişikliklerin gösterilmesi birkaç dakika kadar sürebilir.

### <a name="unsupported-datasets"></a>Desteklenmeyen veri kümeleri

Aşağıdaki veri kümelerine XMLA uç noktalarından erişilemez. Bu veri kümeleri SSMS’de veya diğer araçlarda çalışma alanının altında görüntülenmez:

- Azure Analysis Services ve SQL Server Analysis Services modeline yönelik bir canlı bağlantıyı temel alan veri kümeleri. 
- Başka bir çalışma alanındaki Power BI veri kümesine yönelik bir canlı bağlantıyı temel alan veri kümeleri. Daha fazla bilgi için bkz. [Çalışma alanları arasında veri kümelerine giriş](../connect-data/service-datasets-across-workspaces.md).
- REST API kullanılarak veri gönderme özelliği olan veri kümeleri.
- Excel çalışma kitabı veri kümeleri.

### <a name="serverworkspace-alias"></a>Sunucu/çalışma alanı diğer adı

Azure Analysis Services hizmetinde desteklenen sunucu adı diğer adları Power BI Premium çalışma alanlarında desteklenmez.

## <a name="security"></a>Güvenlik

XMLA Uç Noktası özelliğinin okuma/yazma özelliği kapasite yöneticisi tarafından etkinleştirilir. Buna ek olarak kiracı düzeyindeki **Şirket içi veri kümeleriyle XMLA uç noktalarına ve Excel'de Çözümle özelliğine izin ver** ayarının da yönetici portalından etkinleştirilmesi gerekir. XMLA Uç Noktasına bağlanacak AIXL dosyaları oluşturmanız gerekiyorsa kiracı düzeyindeki **Canlı bağlantılara izin ver** ayarı da etkinleştirilmelidir. Bu ayarların ikisi de varsayılan olarak etkindir.

**Şirket içi veri kümeleriyle XMLA uç noktalarına ve Excel'de Çözümle özelliğine izin ver** bir tümleştirme ayarıdır.

:::image type="content" source="media/service-premium-connect-tools/allow-xmla-endpoints.png" alt-text="Tümleştirme ayarı: XMLA uç noktalarına izin ver.":::

**Canlı bağlantılara izin ver** bir dışarı aktarma ve paylaşma ayarıdır.

:::image type="content" source="media/service-premium-connect-tools/allow-live-connections.png" alt-text="Dışarı aktarma ve paylaşma ayarı: Canlı bağlantılara izin ver.":::

XMLA uç noktası üzerinden erişim, çalışma alanı/uygulama düzeyine ayarlanan güvenlik grubu üyelerini kabul eder.

Çalışma alanına katkıda bulunanlar ve daha üst düzeydekiler veri kümesine yazma erişimine sahip olduklarından, Analysis Services veritabanı yöneticileriyle eşit haklara sahiptir. Bu kişiler, Visual Studio’dan yeni veri kümeleri dağıtıp SSMS’de TMSL betiklerini yürütebilir.

Sunucu düzeyinde izlemeler ve [EffectiveUserName](/analysis-services/instances/connection-string-properties-analysis-services?view=power-bi-premium-current&preserve-view=true#bkmk_auth) bağlantı/dize özelliğini kullanarak kullanıcıların kimliğine bürünme gibi Analysis Services sunucu yöneticisi izinleri (veritabanı yöneticisi yerine) gerektiren işlemler şu anda Power BI Premium’da desteklenmiyor.

Veri kümesinde [Oluşturma iznine](../connect-data/service-datasets-build-permissions.md) sahip olan diğer kullanıcılar, Analysis Services veritabanı okuyucularıyla eşit haklara sahiptir. Bu kişiler, veri kullanımı ve görselleştirmesi için veri kümelerine bağlanıp göz atabilirler. Satır düzeyi güvenlik (RLS) kuralları kabul edilir ve bu kişiler iç veri kümesi meta verilerini görüntüleyemez.

### <a name="model-roles"></a>Model rolleri

XMLA uç noktasıyla bir veri kümesi için rol tanımı yapılabilir, Azure Active Directory (AAD) kullanıcıları için rol üyeliği tanımlanabilir ve satır düzeyi güvenlik (RLS) filtreleri tanımlanabilir. Power BI’daki model rolleri yalnızca RLS için kullanılır. RLS dışındaki izinleri denetlemek için Power BI güvenlik modelini kullanın.

Visual Studio'da yazılan tablosal model projeleri için gerekli roller, model tasarımcısındaki Rol Yöneticisi kullanılarak tanımlanabilir. Power BI'daki veri kümeleri için gerekli roller SSMS kullanılarak tanımlanabilir, bu şekilde rol nesneleri oluşturulabilir ve rol özellikleri tanımlanabilir. Ancak çoğu durumda rol nesnesi tanımları, TMSL kullanılarak betik haline getirebilir ve bu şekilde [Roller nesnesi](/analysis-services/tmsl/roles-object-tmsl?view=power-bi-premium-current&preserve-view=true) oluşturulabilir veya değiştirilebilir. TMSL betikleri SSMS ile veya [Invoke-ASCmd](/powershell/module/sqlserver/invoke-ascmd?view=sqlserver-ps&preserve-view=true) PowerShell cmdlet'iyle yürütülebilir.

XMLA uç noktası aracılığıyla veri kümesi rolleriyle çalışırken şu sınırlamalar geçerlidir:

- Power BI veri kümeleri için ayarlanabilecek tek *rol* izni, Okuma iznidir. Diğer izinler Power BI güvenlik modeli kullanılarak verilir.
- Veri kümeleri rollerinin var olup olmaması fark etmeksizin, XMLA uç noktası üzerinden okuma erişimi için bir veri kümesine yönelik Oluşturma izni gerekir.
- Nesne düzeyinde güvenlik (OLS) kuralları, şu anda Power BI’da desteklenmiyor.

Daha fazla bilgi için bkz. [Tablosal modellerdeki roller](/analysis-services/tabular-models/roles-ssas-tabular).

### <a name="setting-data-source-credentials"></a>Veri kaynağı kimlik bilgilerini ayarlama

XMLA uç noktası üzerinden belirtilen meta veriler veri kaynaklarına bağlantı oluşturabilir, ancak veri kaynağı kimlik bilgilerini ayarlayamaz. Bunun yerine, Power BI hizmetindeki veri kümesi ayarları sayfasından kimlik bilgileri ayarlanabilir.

### <a name="service-principals"></a>Hizmet sorumluları

Hizmet sorumlusu, katılımsız kaynak ve hizmet düzeyinde işlemler gerçekleştirmek için kiracınızın içinde oluşturduğunuz bir Azure Active Directory uygulama kaydıdır. Bu uygulama adı, uygulama kimliği, kiracı kimliği ve parola olarak istemci gizli anahtarı veya sertifikayla benzersiz türde bir kullanıcı kimliğidir. Power BI Premium, Power BI Embedded ile aynı hizmet sorumlusu işlevini kullanır.

Ayrıca Power BI Premium’da hizmet sorumluları XMLA uç noktasıyla birlikte kullanılarak çalışma alanları sağlama, modelleri dağıtma ve veri kümesini yenileme gibi veri kümesi yönetim görevleri şunlarla otomatik hale getirilebilir:

- PowerShell
- Azure Otomasyonu
- Azure Logic Apps
- Özel istemci uygulamaları

Daha fazla bilgi için bkz. [Hizmet sorumlularıyla Premium çalışma alanı ve veri kümesi görevlerini otomatikleştirme](service-premium-service-principal.md).

## <a name="deploy-model-projects-from-visual-studio-ssdt"></a>Visual Studio’dan model projelerini dağıtma (SSDT)

Visual Studio’daki bir tablosal model projesini Power BI Premium çalışma alanına dağıtmak, Azure veya SQL Server Analysis Services sunucusuna dağıtmakla neredeyse aynıdır. Aralarındaki tek fark, işleme işlemlerinin veri kaynaklarındaki verileri çalışma alanındaki yeni veri kümesine içeri aktarmasını sağlayabilmesi için proje için belirtilen Dağıtım Sunucusu özelliğinde ve veri kaynağı kimlik bilgilerinin nasıl belirlendiğindedir.

Visual Studio’da yazılmış bir tablosal model projesini dağıtmak için, öncelikle projedeki **Dağıtım Sunucusu** özelliğindeki çalışma alanı bağlantı URL’sini ayarlamanız gerekir. Visual Studio’da, **Çözüm Gezgini**’nde projeye sağ tıklayıp **Özellikler**’i seçin. **Sunucu** özelliğinde, çalışma alanı bağlantı URL’sini yapıştırın.

![Dağıtım özelliği](media/service-premium-connect-tools/xmla-endpoint-ssdt-deploy-property.png)

Proje, Dağıtım Sunucusu özelliği belirtildikten sonra dağıtılabilir.

**İlk kez dağıtıldığında**, model.bim öğesindeki meta veriler kullanılarak çalışma alanında bir veri kümesi oluşturulur. Dağıtım işleminin bir parçası olarak, çalışma alanında model verilerinden bir veri kümesi oluşturulduktan sonra, veri kaynaklarından veri kümesine veri yükleme işlemi başarısız olur.

Azure veya SQL Server Analysis Server örneğine dağıtırken veri kaynağı kimlik bilgileri dağıtım işleminin bir parçası olarak istenirken, Premium çalışma alanına dağıtım yapılırken çalışma alanı veri kaynağı kimlik bilgileri, dağıtım işleminin bir parçası olarak belirtilemeyeceği için işlem başarısız olur. Bu işlemde veri kaynağı kimlik bilgileri, ancak meta veri dağıtımı başarılı olduktan ve veri kümesi oluşturulduktan sonra Power BI hizmetinde veri kümesi ayarlarında belirtilir. Çalışma alanında **Veri kümeleri** > **Ayarlar** > **Veri kaynağı kimlik bilgileri** > **Kimlik bilgilerini düzenle**’yi seçin.

![Veri kaynağı kimlik bilgileri](media/service-premium-connect-tools/xmla-endpoint-datasource-credentials.png)

Veri kaynağı kimlik bilgileri belirtildikten sonra Power BI hizmetindeki veri kümesini yenileyebilir, zamanlama yenilemesini yapılandırabilir veya veri kümesine veri yüklemek amacıyla yenilemeyi SQL Server Management Studio’dan işleyebilirsiniz.

Dağıtımın Visual Studio’daki projede belirtilen **İşleme Seçeneği** özelliği gözlemlenir. Ancak, veri kaynağının kimlik bilgileri henüz Power BI hizmetinde belirtilmediyse meta veri dağıtımı başarılı olsa bile, işlem başarısız olur. Dağıtımın bir parçası olarak işleme denemesini önlemek için, özelliği **İşleme** olarak ayarlayabilirsiniz. Ancak yeni veri kümesi için veri kaynağı kimlik bilgileri veri kaynağı ayarlarında belirtildikten sonra, ardışık dağıtım işlemlerinin bir parçası olarak işleme başarılı olacağından, özelliği yeniden **Varsayılan** olarak ayarlamanız önerilir.

## <a name="connect-with-ssms"></a>SSMS ile bağlanma

Bir çalışma alanına bağlanmak için SSMS kullanmak, Azure veya SQL Server Analysis Services sunucusuna bağlanmaya çok benzer. Tek fark, sunucu adında çalışma alanı URL’sini belirtmeniz ve **Active Directory - MFA ile Evrensel** kimlik doğrulamasını kullanmanız gerekir.

### <a name="connect-to-a-workspace-by-using-ssms"></a>SSMS kullanarak çalışma alanına bağlanma

1. SQL Server Management Studio’da **Bağlan** > **Sunucuya Bağlan**’ı seçin.

2. **Sunucu Türü**’nde **Analysis Services**’i seçin. **Sunucu adı**’na çalışma alanı URL’sini girin. **Kimlik Doğrulaması**’nda **Active Directory - MFA ile Evrensel**’i seçin ve **Kullanıcı adı** olarak kurumsal kullanıcı kimliğinizi girin.

    ![SSMS’de sunucuya bağlanma](media/service-premium-connect-tools/xmla-endpoint-connect-server.png)

Bağlandığınızda, çalışma alanı bir Analysis Services sunucusu olarak ve çalışma alanındaki veri kümeleri de veritabanları olarak gösterilir.  

![SSMS](media/service-premium-connect-tools/xmla-endpoint-ssms.png)

SSM’yi betik meta verilerinde kullanma hakkında daha fazla bilgi için bkz. [Analysis Services betikleri oluşturma](/analysis-services/instances/create-analysis-services-scripts-in-management-studio?view=power-bi-premium-current&preserve-view=true) ve [Tablosal Model Betik Dili (TMSL)](/analysis-services/tmsl/tabular-model-scripting-language-tmsl-reference?view=power-bi-premium-current&preserve-view=true).

## <a name="dataset-refresh"></a>Veri kümesi yenilemesi

XMLA uç noktası SSMS kullanarak hassas yenilemenin özellikleri ve TOM kullanarak PowerShell ile otomasyon, [Azure Otomasyonu](/azure/automation/automation-intro) ile [Azure İşlevleri](/azure/azure-functions/functions-overview) gibi çok çeşitli senaryolar sunar. Örneğin, tüm geçmiş verileri yeniden yüklemek zorunda kalmadan, belirli geçmiş bölümlerde [artımlı yineleme](service-premium-incremental-refresh.md) yapabilirsiniz.

Power BI hizmetinde yenilemeyi yapılandırmanın aksine, XMLA uç noktası üzerinden yapılan yenileme işlemleri günlük 48 yenileme işlemiyle sınırlı değildir ve [zamanlanan yenileme zaman aşımı](../connect-data/refresh-troubleshooting-refresh-scenarios.md#scheduled-refresh-timeout) uygulanmaz.

## <a name="dynamic-management-views-dmv"></a>Dinamik Yönetim Görünümleri (DMV)

Analysis Services [DMV’leri](/analysis-services/instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services) veri kümesi meta verilerine, veri kökenine ve kaynak kullanımına yönelik görünürlük sağlar. XMLA uç noktası üzerinden Power BI’da sorgulama yapmak için kullanılan DMV’ler, en fazla veritabanı/yönetici izinleri gerekenlerle sınırlıdır. Örneğin, bazı DMV’ler için Analysis Services sunucu/yönetici izinleri gerektiğinden bunlara erişilemez.

## <a name="power-bi-desktop-authored-datasets"></a>Power BI Desktop’ta yazılan veri kümeleri

### <a name="enhanced-metadata"></a>Gelişmiş meta veriler

Power BI Desktop’ta yazılan ve gelişmiş meta verilere ihtiyaç duyan bir Premium çalışma alanında yayımlanan veri kümelerine yönelik XMLA yazma işlemleri etkindir. Daha fazla bilgi için bkz. [Gelişmiş veri kümesi meta verileri](../connect-data/desktop-enhanced-dataset-metadata.md).

> [!CAUTION]
> Şu anda, Power BI Desktop’ta yazılmış bir veri kümesine yönelik yazma işlemi, bu veri kümesinin PBIX dosyası olarak geri indirilmesini engeller. Özgün PBIX dosyanızı sakladığınızdan emin olun.

### <a name="data-source-declaration"></a>Veri kaynağı bildirimi

Veri kaynaklarına bağlanılıp veriler sorgulanırken Power BI Desktop, satır içi veri kaynağı bildirimi olarak Power Query M ifadelerini kullanır. Power Query M satır içi veri kaynağı bildirimi Power BI Premium çalışma alanlarında desteklenirken, Azure Analysis Services veya SQL Server Analysis Services tarafından desteklenmez. Bunun yerine Visual Studio gibi Analysis Services veri modelleme araçları, meta verileri *yapılandırılmış* ve/veya *sağlayıcı* veri kaynağı bildirimleri kullanarak oluşturur. XMLA uç noktası sayesinde Power BI Premium, yapılandırılmış ve sağlayıcı veri kaynaklarını da destekler. Ancak bu destek, Power BI Desktop modellerinde Power Query M satır içi veri kaynağı bildirimlerinin bir parçası olarak yer almaz. Daha fazla bilgi için bkz. [Sağlayıcıları anlama](/azure/analysis-services/analysis-services-datasource#understanding-providers).

### <a name="power-bi-desktop-in-live-connect-mode"></a>Canlı bağlanma modunda Power BI Desktop

Power BI Desktop canlı bağlantı kullanarak bir Power BI Premium veri kümesine bağlanabilir. Canlı bağlantı kullanıldığında verilerin yerel olarak çoğaltılması gerekmez ve bu da kullanıcılar açısından anlamsal modellerin kullanımını kolaylaştırır. Kullanıcılar iki yolla bağlanabilir:

**Power BI veri kümeleri**’ni ve sonra da rapor oluşturmak için bir veri kümesini seçerek. Kullanıcıların veri kümelerine canlı bağlantı kurması için **önerilen** yöntem budur. Bu yöntem veri kümelerinin onay düzeyini gösteren gelmiş bir bulma deneyimi sağlar. Kullanıcıların çalışma alanı URL’lerini bulması ve bunların kaydını tutması gerekmez. Kullanıcıların veri kümesini bulmak için veri kümesi adını yazması veya aradıkları veri kümesini bulana kadar listeyi kaydırması yeterli olur.

![Veri kümesine canlı bağlantı kurma](media/service-premium-connect-tools/dataset-live-connect.png)

Kullanıcıların bağlanmak için kullanabilecekleri diğer yol **Veri Al** > **Analysis Services**’i seçmek, URL olarak bir Power BI Premium çalışma alanı adı belirtmek, **Canlı bağlan**’ı seçmek ve sonra da Gezgin’de bir veri kümesi belirtmektir. Bu durumda Power BI Desktop veri kümesine canlı bağlanmak için bir Analysis Services veri modeliymiş gibi XMLA uç noktasını kullanır. 

![Analysis Services veri kümesine canlı bağlanma](media/service-premium-connect-tools/as-live-connect.png)

Analysis Services veri modellerine canlı bağlantılı raporları olan ve Power BI premium veri kümelerine geçmek isteyen kuruluşların **Verileri dönüştür** > **Veri kaynağı ayarları**’nda sunucu adı URL’sini değiştirmeleri yeterli olur.

## <a name="audit-logs"></a>Denetim günlükleri

Uygulamalar bir çalışma alanına bağlandığında, XMLA uç noktaları üzerinden erişim Power BI denetim günlüklerine şu işlemlerin altına kaydedilir:

|Kolay işlem adı   |İşlem adı   |
|---------|---------|
|Dış uygulamadan Power BI veri kümesine bağlanıldı      |  ConnectFromExternalApplication        |
|Dış uygulamadan Power BI veri kümesi yenilemesi istendi      | RefreshDatasetFromExternalApplication        |
|Dış uygulamadan Power BI veri kümesi oluşturuldu      |  CreateDatasetFromExternalApplication        |
|Dış uygulamadan Power BI veri kümesi düzenlendi     |  EditDatasetFromExternalApplication        |
|Dış uygulamadan Power BI veri kümesi silindi      |  DeleteDatasetFromExternalApplication        |

Daha fazla bilgi için bkz.  [Power BI’ı denetleme](service-admin-auditing.md).

## <a name="see-also"></a>Ayrıca bkz.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
