---
title: Power BI'da XMLA uç nokta bağlantı sorunlarını giderme
description: Power BI Premium’da XMLA uç noktası üzerinden kurulan bağlantı sorunlarının nasıl giderilebileceği açıklanmaktadır.
author: minewiskan
ms.author: owend
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: troubleshooting
ms.date: 10/20/2020
ms.custom: seodec18, css_fy20Q4
LocalizationGroup: Premium
ms.openlocfilehash: 5426c91f2ab0c4de1f9f2bc335ac21ea3a90c0e2
ms.sourcegitcommit: 132b3f6ba6d2b1948ddc15969d64cf629f7fb280
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94483685"
---
# <a name="troubleshoot-xmla-endpoint-connectivity"></a>XMLA uç nokta bağlantı sorunlarını giderme

Power BI Premium’daki XMLA uç noktaları, Power BI veri kümelerine erişmek için yerel Analysis Services bağlantı protokolünü kullanır. Bu nedenle, XMLA uç noktasında sorun giderme işlemi, tipik bir Analysis Services bağlantısında sorun giderme işlemiyle neredeyse aynıdır. Ancak, Power BI’a özgü bağımlılıklarla ilgili bazı farklar vardır.

## <a name="before-you-begin"></a>Başlamadan önce

XMLA uç nokta senaryosunda sorun gidermeden önce, [XMLA uç noktasıyla veri kümesi bağlantısı](service-premium-connect-tools.md) makalesinde ele alınan temel bilgileri gözden geçirdiğinizden emin olun. En yaygın XMLA uç noktası kullanım örneklerine bu makalede değinilmektedir. [Ağ geçidiyle ilgili sorunları giderme - Power BI](../connect-data/service-gateway-onprem-tshoot.md) ve [Excel’de Analiz ile ilgili sorun giderme](../collaborate-share/desktop-troubleshooting-analyze-in-excel.md) gibi diğer Power BI sorun giderme kılavuzları da yardımcı olabilir.

## <a name="enabling-the-xmla-endpoint"></a>XMLA uç noktasını etkinleştirme

XMLA uç noktası hem Power BI Premium hem de Power BI Embedded kapasitelerinde etkinleştirilebilir. Yalnızca 2,5 GB belleğe sahip A1 kapasitesi gibi daha küçük kapasitelerde, XMLA Uç Noktasını **Okuma/Yazma**’ya ayarlayıp **Uygula**’yı seçerken Kapasite ayarlarında hatayla karşılaşabilirsiniz. “İş yükü ayarlarınızla ilgili bir sorun oluştu. Kısa bir süre sonra tekrar deneyin.” hatası gösterilir.

Deneyebileceğiniz birkaç şey aşağıda verilmiştir:

- Veri Akışları gibi, kapasitedeki diğer hizmetlerin bellek tüketimini en fazla %40 olacak şekilde sınırlayın veya gereksiz hizmetleri tamamen devre dışı bırakın.  
- Kapasiteyi daha büyük bir SKU’ya yükseltin. Örneğin, kapasiteyi A1’den A3’e yükseltmek, Veri Akışları’nı devre dışı bırakmak zorunda kalmadan bu yapılandırma sorununu çözebilir.

Power BI Yönetim Portalı’nda kiracı düzeyinde [Dışarı aktarma ayarlarını](service-premium-connect-tools.md#security) etkinleştirmeniz gerektiğini de unutmayın. Bu ayar, Excel’de Analiz özelliği için de gereklidir.

## <a name="establishing-a-client-connection"></a>İstemci bağlantısı oluşturma

XMLA uç noktasını etkinleştirdikten sonra, kapasitedeki bir çalışma alanına yönelik bağlantıyı test etmeniz faydalı olabilir. Daha fazla bilgi için bkz. [Premium çalışma alanına bağlanma](service-premium-connect-tools.md#connecting-to-a-premium-workspace). Ayrıca, geçerli XMLA bağlantı sınırlamaları hakkında yardımcı olacak ipuçları ve bilgiler için [Bağlantı gereksinimleri](service-premium-connect-tools.md#connection-requirements) bölümünü okuduğunuzdan emin olun.

### <a name="connecting-with-a-service-principal"></a>Hizmet sorumlusu ile bağlanma

Hizmet sorumlularının Power BI API’lerini kullanmasına izin veren kiracı ayarlarını etkinleştirdiyseniz [Hizmet sorumlularını etkinleştirme](service-premium-service-principal.md#enable-service-principals) makalesinde açıklandığı gibi, hizmet sorumlusu kullanarak bir XMLA uç noktasına bağlanabilirsiniz. Hizmet sorumlusunun çalışma alanında veya veri kümesi düzeyinde normal kullanıcılarla aynı erişim izni düzeyine sahip olması gerektiğini unutmayın.

Hizmet sorumlusu kullanmak için, bağlantı dizesinde uygulama kimlik bilgilerini aşağıdaki gibi belirttiğinizden emin olun:

- `User ID=<app:appid@tenantid>`
- `Password=<application secret>`

Örnek:

`Data Source=powerbi://api.powerbi.com/v1.0/myorg/Contoso;Initial Catalog=PowerBI_Dataset;User ID=app:91ab91bb-6b32-4f6d-8bbc-97a0f9f8906b@19373176-316e-4dc7-834c-328902628ad4;Password=6drX...;`

Aşağıdaki hata iletisini alırsanız:

“Eksik hesap bilgilerinden dolayı veri kümesine bağlanılamıyor. Hizmet sorumluları için, lütfen kiracı kimliğini uygulama kimliğiyle birlikte app:\<appId>@\<tenantId> biçimini kullanarak belirttiğinizden emin olup tekrar deneyin.”

Kiracı kimliğini ile uygulama kimliğini doğru biçimi kullanarak belirttiğinizden emin olun.

Ayrıca, kiracı kimliği olmadan uygulama kimliğini belirtmeniz de geçerli olacaktır. Ancak bu durumda, veri kaynağı URL’sindeki `myorg` diğer adını gerçek kiracı kimliğiyle değiştirmeniz gerekir. Daha sonra Power BI, hizmet sorumlusunu doğru kiracıda bulabilir. Ancak en iyi uygulama olarak, `myorg` diğer adını kullanın ve kiracı kimliğini Kullanıcı Kimliği parametresindeki uygulama kimliğiyle birlikte belirtin.

### <a name="connecting-with-azure-active-directory-b2b"></a>Azure Active Directory B2B ile bağlanma

Power BI’daki Azure Active Directory (Azure AD) işletmeden işletmeye (B2B) desteği sayesinde, dış kullanıcılara XMLA uç noktası üzerinden veri kümelerine erişim verebilirsiniz. Power BI Yönetim portalında [Dış kullanıcılarla içerik paylaşma](service-admin-portal.md#export-and-sharing-settings) ayarının etkinleştirildiğinden emin olun. Daha fazla bilgi için bkz. [Azure AD B2B ile Power BI içeriklerini dış konuk kullanıcılara dağıtma](service-admin-azure-ad-b2b.md).

## <a name="deploying-a-dataset"></a>Veri kümesi dağıtma

Visual Studio’daki (SSDT) bir tablosal model projesini, Azure Analysis Services’a dağıtmaya çok benzer şekilde bir Power BI Premium çalışma alanına dağıtabilirsiniz. Ancak bir Power BI Premium çalışma alanına dağıtırken birkaç konuyu daha dikkate almanız gerekir. XMLA uç noktasıyla veri kümesi bağlantısı makalesindeki [Visual Studio’dan model projelerini dağıtma (SSDT)](service-premium-connect-tools.md#deploy-model-projects-from-visual-studio-ssdt) bölümünü gözden geçirdiğinizden emin olun.

### <a name="deploying-a-new-model"></a>Yeni model dağıtma

Varsayılan yapılandırmada Visual Studio, veri kaynaklarındaki verileri veri kümesine yüklemek için modeli dağıtım işleminin bir parçası olarak işlemeyi dener. [Visual Studio’dan model projelerini dağıtma (SSDT)](service-premium-connect-tools.md#deploy-model-projects-from-visual-studio-ssdt) bölümünde bahsedildiği gibi, veri kaynağı kimlik bilgileri dağıtım işleminin bir parçası olarak belirtilemediğinden bu işlem başarısız olabilir. Bunun yerine, veri kaynağınıza ait kimlik bilgileri mevcut veri kümelerinizden biri için zaten tanımlanmadıysa Power BI kullanıcı arabirimini kullanarak (**Veri kümeleri** > **Ayarlar** > **Veri kaynağı kimlik bilgileri** > **Kimlik bilgilerini düzenle**) veri kümesi ayarlarında veri kaynağı kimlik bilgilerini belirtmeniz gerekir. Veri kaynağı kimlik bilgileri tanımlandığında, meta veri dağıtımı başarılı olduktan ve veri kümesi oluşturulduktan sonra Power BI, kimlik bilgilerini herhangi bir yeni veri kümesi için bu veri kaynağına otomatik olarak uygulayabilir.

Power BI yeni veri kümenizi veri kaynağı kimlik bilgilerine bağlayamazsa “Veri tabanı işlenemiyor. Neden: Değişiklikler sunucuya kaydedilemedi.” hatasını “DMTS_DatasourceHasNoCredentialError” hata kodu ile birlikte alırsınız (aşağıda gösterilmiştir):

:::image type="content" source="media/troubleshoot-xmla-endpoint/deploy-refresh-error.png" alt-text="Model dağıtım hatası":::

İşleme hatasından kaçınmak için **Dağıtım seçenekleri** > **İşleme Seçenekleri** ayarını aşağıda gösterildiği gibi **İşleme** olarak ayarlayın. Daha sonra Visual Studio yalnızca meta verileri dağıtır. Daha sonra veri kaynağı kimlik bilgilerini yapılandırabilir ve Power BI kullanıcı arabirimindeki veri kümesi için **Şimdi yenile** seçeneğine tıklayabilirsiniz. İşleme sorunlarını giderme hakkında bilgi için bu makalenin devamındaki [Veri kümesini yenileme](#refreshing-a-dataset) bölümüne bakın.

:::image type="content" source="media/troubleshoot-xmla-endpoint/do-not-process.png" alt-text="İşleme seçeneği":::

### <a name="new-project-from-an-existing-dataset"></a>Mevcut bir veri kümesinden yeni proje

Power BI Premium çalışma alanındaki bir veri kümesinden meta verileri içeri aktararak Visual Studio’da yeni bir tablosal proje oluşturma işlemi desteklenmez. Ancak, SQL Server Management Studio kullanarak veri kümesine bağlanabilir, meta verileri betikleştirebilir ve sonra diğer tablosal projelerde yeniden kullanabilirsiniz.

## <a name="migrating-a-dataset-to-power-bi"></a>Power BI’a veri kümesi geçirme

Tablosal modeller için 1500 (veya üzeri) uyumluluk düzeyi belirtmeniz önerilir. Bu uyumluluk düzeyi, çoğu özelliği ve veri kaynağı türünü destekler. Daha sonraki uyumluluk düzeyleri, daha önceki düzeylerle geriye dönük olacak şekilde uyumludur.

### <a name="supported-data-providers"></a>Desteklenen veri kaynakları

1500 uyumluluk düzeyinde Power BI aşağıdaki veri kaynağı türlerini destekler:

- Sağlayıcı veri kaynakları (model meta verilerindeki bağlantı dizesiyle eski).
- Yapılandırılmış veri kaynakları (1400 uyumluluk düzeyiyle tanıtılan).
- Veri kaynaklarının satır içi M bildirimleri (Power BI Desktop bildirir).

Visual Studio’nun İçeri aktarma veri akışı sırasında varsayılan olarak oluşturduğu yapılandırılmamış veri kaynaklarını kullanmanız önerilir. Ancak, sağlayıcı veri kaynağı kullanan mevcut bir modeli Power BI’a geçirmeyi planlıyorsanız bu kaynağın desteklenen bir veri sağlayıcısını kullandığından emin olun. Özellikle, SQL Server ve diğer üçüncü taraf ODBC sürücüleri için Microsoft OLE DB Sürücüsü. SQL Server için OLE DB Sürücüsü’nde veri kaynağı tanımını SQL Server için .NET Framework Veri Sağlayıcısı’yla değiştirmeniz gerekir. Power BI hizmetinde kullanılamayan üçüncü taraf ODBC sürücüleri için bunun yerine yapılandırılmış veri kaynağı tanımıyla değiştirmeniz gerekir.

SQL Server için .NET Framework Veri Sağlayıcısı’na sahip SQL Server veri kaynağı tanımlarınızdaki güncel olmayan SQL Server için Microsoft OLE DB Sürücüsü’nü de (SQLNCLI11) değiştirmeniz önerilir.

Aşağıdaki tabloda, SQL Server için OLE DB Sürücüsü’nde karşılık gelen bağlantı dizesiyle değiştirilen bir SQL Server için .NET Framework Veri Sağlayıcısı bağlantı dizesi örneği gösterilmektedir.

|SQL Server için OLE DB Sürücüsü  |SQL Server için .NET Framework Veri Sağlayıcısı   |
|---------|---------|
|`Provider=SQLNCLI11;Data Source=sqldb.database.windows.net;Initial Catalog=AdventureWorksDW;Trusted_Connection=yes;`    |   `Data Source=sqldb.database.windows.net;Initial Catalog=AdventureWorksDW2016;Integrated Security=SSPI;Encrypt=true;TrustServerCertificate=false`       |

### <a name="cross-referencing-partition-sources"></a>Çapraz başvuru bölüm kaynakları

Birden çok veri kaynağı türü olduğu gibi, bir tablosal modelin verileri tabloda içeri aktarmak amacıyla içerebileceği birden çok bölüm kaynağı türü vardır. Özellikle bir bölüm, bir sorgu bölümü kaynağını veya M bölüm kaynağını kullanabilir. Bu bölüm kaynak türleri sırasıyla sağlayıcı veri kaynaklarına veya yapılandırılmış veri kaynaklarına başvurabilir. Azure Analysis Services’daki tablosal modeller bu çeşitli veri kaynağı ve bölüm türlerine çapraz olarak başvurmayı desteklerken Power BI, daha katı bir ilişki uygular. Sorgu bölümü kaynaklarının sağlayıcı veri kaynaklarına, M bölüm kaynaklarının ise yapılandırılmış veri kaynaklarına başvurması gerekir. Diğer birleşimler Power BI’da desteklenmez. Çapraz başvuru yapan bir veri kümesini geçirmek istiyorsanız desteklenen yapılandırmalar aşağıdaki tabloda açıklanmaktadır:  

|Veri kaynağı   |Bölüm kaynağı   |Yorumlar   |XMLA uç noktası ile Power BI Premium’da desteklenir   |
|---------|---------|---------|---------|
|Sağlayıcı veri kaynağı      |   Sorgu bölümü kaynağı      |   AS altyapısı, veri kaynağına erişmek için kartuş tabanlı bağlantı yığınını kullanır.       |     Evet     |
|Sağlayıcı veri kaynağı      |   M bölüm kaynağı       |   AS altyapısı, sağlayıcı veri kaynağını genel yapılandırılmış veri kaynağına çevirir ve sonra verileri içeri aktarmak için Karma altyapısını kullanır.       |    Hayır     |
|Yapılandırılmış veri kaynağı      |     Sorgu bölümü kaynağı     |    AS altyapısı, bölüm kaynağındaki yerel sorguyu bir M ifadesine sarmalar ve sonra verileri içeri aktarmak için Karma altyapısını kullanır.      |    Hayır     |
|Yapılandırılmış veri kaynağı      |    M bölüm kaynağı      |     AS altyapısı, Karma altyapısını verileri içeri aktarmak için kullanır.     |   Evet      |

## <a name="refreshing-a-dataset"></a>Veri kümesini yenileme

XMLA uç noktaları, hem tablosal modellere hem de Power BI Desktop’ta oluşturulan veri kümelerine karşı yenileme işlemleri gerçekleştirmenize olanak verir. İkincisini desteklemek için Gelişmiş depolama biçimi ayarını belirttiğinizden emin olun. Bu ayar, XMLA uç noktasını kullanarak işleme veya diğer okuma/yazma işlemlerini gerçekleştirmek istiyorsanız gereklidir. Power BI Desktop’ta Önizleme özellikleri bölümünde ayarı bulabilirsiniz. Ayarladıktan sonra PBIX çözümünüzü yeniden Power BI Premium çalışma alanınızda yayımlayın.  

Gelişmiş meta veriler olmadan bir modele karşı XMLA uç noktası aracılığıyla yenileme işlemi gerçekleştirirseniz Power BI aşağıdaki hatayı döndürür: “İşlem, yalnızca 'DefaultPowerBIDataSourceVersion' özelliği Power BI Premium'da 'PowerBI_V3' olarak ayarlanmış modelde desteklenir.”

### <a name="data-sources-and-impersonation"></a>Veri kaynakları ve kimliğe bürünme

Sağlayıcı veri kaynakları için tanımlayabileceğiniz kimliğe bürünme ayarları Power BI için uygun değildir. Power BI, veri kaynağı kimlik bilgilerini yönetmek için veri kümesi ayarlarına bağlı farklı bir mekanizma kullanır. Bu nedenle, bir Sağlayıcı Veri Kaynağı oluşturuyorsanız **Hizmet Hesabı** seçtiğinizden emin olun.

:::image type="content" source="media/troubleshoot-xmla-endpoint/impersonate-services-account.png" alt-text="Hizmet hesabı kimliğine bürünme":::

### <a name="fine-grained-processing"></a>Ayrıntılı işleme

Power BI’da zamanlanmış veya isteğe bağlı bir yenileme işlemini tetiklerken Power BI genellikle veri kümesinin tamamını yeniler. Çoğu durumda, yenilemeleri daha seçici bir şekilde gerçekleştirmek daha verimlidir. Ayrıntılı işleme görevlerini aşağıda gösterildiği şekilde SQL Server Management Studio’da (SSMS) veya üçüncü taraf araçlarını ya da betiklerini kullanarak gerçekleştirebilirsiniz.

:::image type="content" source="media/troubleshoot-xmla-endpoint/process-tables.png" alt-text="SSMS’de tabloları işleme":::

### <a name="overrides-in-refresh-tmsl-command"></a>TMSL Yenileme komutunda geçersiz kılmalar

[Yenileme komutundaki (TMSL)](/analysis-services/tmsl/refresh-command-tmsl) geçersiz kılmalar kullanıcıların yenileme işlemi için sorgu tanımının veya veri kaynağı tanımının farklı bölümlerini seçmesine olanak tanır. Şu anda Power BI Premium'da **geçersiz kılmalar desteklenmez**. "Power BI Premium'da sıradışı bağlamaya izin verilmez. Ek bilgi için ürün bilgilerinde 'XMLA okuma/yazma desteği' konusuna bakın." hatası döndürülür.

## <a name="see-also"></a>Ayrıca bkz.

[XMLA uç noktasıyla veri kümesi bağlantısı](service-premium-connect-tools.md)  
[Hizmet sorumlularıyla Premium çalışma alanı ve veri kümesi görevlerini otomatikleştirme](service-premium-service-principal.md)  
[Excel'de Çözümleme sorunlarını giderme](../collaborate-share/desktop-troubleshooting-analyze-in-excel.md)  
[Tablolu model çözümü dağıtımı](/analysis-services/deployment/tabular-model-solution-deployment?view=power-bi-premium-current&preserve-view=true)
