---
title: İstemci uygulamaları ve Araçları (Önizleme) ile Power BI Premium veri kümelerine bağlanma
description: Power BI Premium'daki veri kümeleri için istemci uygulamaları ve araçları nasıl bağlanacağı açıklanır.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 05/20/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 063f43cb2345ccb3d1fec5c414100beb8ccde451
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65941515"
---
# <a name="connect-to-datasets-with-client-applications-and-tools-preview"></a>İstemci uygulamaları ve Araçları (Önizleme) ile veri kümelerine bağlanma

Power BI Premium çalışma alanları ve veri kümeleri desteği *salt okunur* bağlantıları Microsoft ve üçüncü taraf istemci uygulamaları ve araçları. 

> [!NOTE]
> Bu makalede, yalnızca Power BI Premium çalışma alanları ve veri kümeleri için salt okunur bağlantı tanıtmak için tasarlanmıştır. Bunu *değil* programlama, belirli araçları ve uygulamaları, mimari ve çalışma alanı ve veri kümesi yönetimi hakkında ayrıntılı bilgi sağlamayı amaçlar. Burada açıklanan konular, Analysis Services tablosal model veritabanı mimarisi ve yönetim düz bir anlayış gerektirir.

## <a name="protocol"></a>Protokol

Power BI Premium kullanan [analiz için XML](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference) istemci uygulamaları ve veri kümeleri ve çalışma alanları yöneten altyapısı arasında iletişim için (XMLA) protokolü. Bu iletişimler ne genellikle XMLA bitiş noktası adlandırılan ' dir. XMLA, Power BI'ın anlam modelleme, idare, yaşam döngüsü ve Veri Yönetimi çalıştıran altyapı altında Microsoft Analysis Services altyapısı tarafından kullanılan aynı iletişim protokolüdür. 

İstemci uygulama ve araçların büyük çoğunluğu açıkça iletişim kurmaz altyapı XMLA uç noktaları kullanarak. Bunun yerine, bunlar istemci uygulaması ve XMLA kullanarak iletişim kurar altyapısı arasında bir aracı olarak MSOLAP ADOMD ve ÇYN gibi istemci kitaplıkları kullanın.


## <a name="supported-tools"></a>Desteklenen araçları

Bu araçlar, Power BI Premium çalışma alanları ve veri kümeleri için yalnızca okuma erişimi destekler:

**SQL Server Management Studio (SSMS)** -destekler DAX, MDX, XMLA ve Announcing sorgular. Sürüm 18.0 gerektirir. İndirme [burada](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms). 

**SQL Server Profiler** -SSMS 18.0 (Önizleme) ile dahil, bu aracı sunucu olayları hata ayıklama ve izleme sağlar. Yakalama ve her olay hakkında veri bir dosya veya daha sonra çözümlemek için tabloya kaydedin. SQL Server için resmi olarak kullanım dışı olsa da Profiler SSMS'de eklenmesi devam eder ve Analysis Services ve artık, Power BI Premium için desteklenen kalır. Daha fazla bilgi için bkz. [SQL Server Profiler](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler).

**DAX Studio** - açık kaynaklı topluluk aracı yürütme ve DAX çözümleme için Analysis Services karşı sorgular. Sürüm 2.8.2 gerektirir veya üzeri. Daha fazla bilgi için bkz. [daxstudio.org](https://daxstudio.org/).

**Excel PivotTable'ları** -Tıkla-Çalıştır Office 16.0.11326.10000 veya yukarıda sürümü gereklidir.

**Üçüncü taraf** - istemci veri görselleştirme uygulamaları ve bağlanabilir araçları, sorgu içerir ve Power BI Premium veri kümelerini kullanma. Çoğu araçları MSOLAP istemci kitaplıkları'nın son sürümlerini gerektirir, ancak bazı ADOMD kullanabilir.

## <a name="client-libraries"></a>İstemci kitaplıkları

İstemci kitaplıkları, istemci uygulama ve araçların Power BI Premium çalışma alanına bağlanmak için gereklidir. Analysis Services'a bağlanmak için kullanılan aynı istemci kitaplıkları da Power BI Premium'da desteklenir. Excel, SQL Server Management Studio (SSMS) ve SQL Server veri Araçları (SSDT) gibi Microsoft istemci uygulamaları, istemci kitaplıklarının üçünü yükleyin ve bunları birlikte normal uygulama güncelleştirmeleri güncelleştirin. Bazı durumlarda, üçüncü taraf uygulamaları ve araçları, özellikle birlikte, istemci kitaplıklarının yeni sürümleri yüklemeniz gerekebilir. İstemci kitaplıkları aylık güncelleştirilir. Daha fazla bilgi için bkz. [Analysis Services'e bağlanmak için istemci kitaplıkları](https://docs.microsoft.com/azure/analysis-services/analysis-services-data-providers).

## <a name="connecting-to-a-premium-workspace"></a>Premium çalışma alanına bağlanma

Premium ayrılmış kapasite için atanmış olan çalışma alanları bağlanabilirsiniz. Ayrılmış bir kapasiteye atanmış olan çalışma alanları URL biçiminde bir bağlantı dizesi var. 

Çalışma alanı bağlantı dizesini Power BI'da ulaşmak için **çalışma alanı ayarlarını**, **Premium** sekmesinde **çalışma bağlantı**, tıklayın **kopyalayın**.

![Çalışma alanı bağlantı dizesi](media/service-premium-connect-tools/connect-tools-workspace-connection.png)

Çalışma alanı bağlantıları işlevmiş gibi bir Analysis Services sunucu adı bir çalışma alanı için şu URL biçimi kullanın:   
`powerbi://api.powerbi.com/v1.0/[tenant name]/[workspace name]` 

Örneğin, `powerbi://api.powerbi.com/v1.0/contoso.com/Sales Workspace`
> [!NOTE]
> `[workspace name]` hassas bir durumdur ve boşluk içerebilir. 

### <a name="to-connect-in-ssms"></a>SSMS bağlanma

İçinde **sunucuya Bağlan** > **sunucu türü**seçin **Analysis Services**. İçinde **sunucu adı**, URL'yi girin. İçinde **kimlik doğrulaması**seçin **Active Directory - MFA desteğiyle Evrensel**ve ardından **kullanıcı adı**, kuruluş kullanıcı kimliğinizi girin 

Bağlandığınızda, çalışma alanı bir Analysis Services sunucusu olarak gösterilir ve çalışma alanlarındaki veri kümeleri veritabanları gösterilir.  

![SSMS](media/service-premium-connect-tools/connect-tools-ssms.png)

### <a name="initial-catalog"></a>İlk katalog

SQL Server Profiler gibi bazı araçlar belirtmeniz gerekebilir bir *Initial Catalog*. Çalışma alanınızda bir veri kümesi (veritabanı) belirtin. İçinde **sunucuya Bağlan**, tıklayın **seçenekleri**. İçinde **sunucuya Bağlan** iletişim, **bağlantı özellikleri** sekmesinde **veritabanına bağlan**, veri kümesi adı girin.

### <a name="duplicate-workspace-name"></a>Yinelenen çalışma alanı adı

Başka bir çalışma alanında aynı ada sahip bir çalışma alanına bağlanırken, şu hatayla karşılaşabilirsiniz: **[Kiracı adı] powerbi://api.powerbi.com/V1.0/ için bağlantı kurulamıyor / [çalışma alanı adı].**

Çalışma alanı adına ek olarak bu hataya çevresinde almak için çalışma alanı objectID, URL'dan kopyalanabilir Objectıdguid belirtin. ObjectID bağlantı URL'si sonuna ekleyin. Örneğin, 'powerbi://api.powerbi.com/v1.0/myorg/Contoso satış - 9d83d204-82a9-4b36-98f2-a40099093830'

### <a name="duplicate-dataset-name"></a>Yinelenen bir veri kümesi adı

Başka bir veri kümesi aynı çalışma alanında aynı ada sahip bir veri kümesi bağlanırken, veri kümesi GUID için veri kümesi adı ekleyin. Her iki veri kümesi adı alabilirsiniz *ve* SSMS çalışma alanına bağlı olduğunda GUID. 

### <a name="delay-in-datasets-shown"></a>Gösterilen veri kümelerinde gecikme

Bir çalışma alanına bağlanırken değişiklikler yeni, silinen ve yeniden adlandırılan veri kümelerinden görünmesi 5 dakika sürebilir. 

### <a name="unsupported-datasets"></a>Desteklenmeyen veri kümeleri

Aşağıdaki veri kümelerinde XMLA uç noktaları kullanarak erişilebilir değil. Bu veri kümelerini *yapmamayı* SSMS veya başka araçlar çalışma alanı altında görünür: 

- Bir Analysis Services modellerine yönelik canlı bağlantı veri kümeleri. 
- Veri kümeleri ile REST API kullanarak veri gönderme.
- Excel çalışma kitabı veri kümeleri. 

Aşağıdaki veri kümelerini Power BI hizmetinde desteklenmez:   

- Bir Power BI veri kümesine canlı bağlantı veri kümeleri.

## <a name="audit-logs"></a>Denetim günlükleri 

İstemci uygulama ve araçların bir çalışma alanına bağlanırken, Power BI denetim günlüklerinde altında XMLA uç noktalarla erişimi kaydedilir **GetWorkspaces** işlemi. Daha fazla bilgi için bkz. [Power BI denetim](service-admin-auditing.md).

## <a name="see-also"></a>Ayrıca bkz.

[Analiz Hizmetleri başvuruları](https://docs.microsoft.com/bi-reference/#pivot=home&panel=home-all)   
[SQL Server Management Studio](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-ssms)   
[SQL Server Analysis Services tablo Protokolü](https://docs.microsoft.com/openspecs/sql_server_protocols/ms-ssas-t/b98ed40e-c27a-4988-ab2d-c9c904fe13cf)   
[Dinamik Yönetim görünümlerini (Dmv'ler)](https://docs.microsoft.com/sql/analysis-services/instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services)   


Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
