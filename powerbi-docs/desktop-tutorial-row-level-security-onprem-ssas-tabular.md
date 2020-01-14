---
title: Analysis Services tablolu modeli ile dinamik satır düzeyi güvenlik
description: Analysis Services tablolu modeli ile dinamik satır düzeyi güvenlik
author: selvarms
ms.reviewer: davidi
editor: davidi
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 05/28/2019
ms.author: selvar
LocalizationGroup: Connect to data
ms.openlocfilehash: 09e4a9cc3e6a5c16f23532f0a4589fdcb1906549
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75759532"
---
# <a name="implement-row-level-security-in-an-analysis-services-tabular-model"></a>Analysis Services tablosal modelinde satır düzeyi güvenlik uygulama

Bu öğreticide aşağıdaki adımların üzerinden geçerken örnek bir veri kümesi kullanılarak **Analysis Services Tablolu Modeli**'nde [**satır düzeyi güvenliğin**](service-admin-rls.md) uygulanması ve bunun bir Power BI raporunda kullanılması gösterilir. 

* [**AdventureworksDW2012** veritabanında](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) yeni bir güvenlik tablosu oluşturma
* Gerekli olgu ve boyut tablolarıyla tablolu modeli oluşturma
* Kullanıcı rollerini ve izinlerini tanımlama
* Modeli **Analysis Services tablolu** örneğine dağıtma
* Rapora erişen kullanıcıya göre uyarlanmış veriler gösteren bir Power BI Desktop raporu oluşturma
* Raporu **Power BI hizmetinde** yayımlama
* Raporu temel alan yeni bir pano oluşturma
* Panoyu iş arkadaşlarınızla paylaşma 

Bu öğretici için [**AdventureworksDW2012** veritabanı](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) gereklidir.

## <a name="task-1-create-the-user-security-table-and-define-data-relationship"></a>1\. Görev: Kullanıcı güvenliği tablosunu oluşturma ve veri ilişkisini tanımlama

**SQL Server Analysis Services (SSAS) tablolu** modeliyle satır düzeyi dinamik güvenliğin nasıl tanımlanacağını açıklayan birçok makale bulabilirsiniz. Bizim örneğimiz için [Satır Filtrelerini Kullanarak Dinamik Güvenlik Uygulama](https://docs.microsoft.com/analysis-services/tutorial-tabular-1200/supplemental-lesson-implement-dynamic-security-by-using-row-filters) makalesini kullanın. 

Buradaki adımlar **AdventureworksDW2012** ilişkisel veritabanının kullanılmasını gerektirir.

1. **AdventureworksDW2012** veritabanında aşağıda gösterildiği gibi **DimUserSecurity** tablosunu oluşturun. Tabloyu oluşturmak için [SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) kullanabilirsiniz.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable.png)

2. Tabloyu oluşturup kaydettikten sonra aşağıda gösterildiği gibi **DimUserSecurity** tablosunun **SalesTerritoryID** sütunu ile **DimSalesTerritory** tablosunun **SalesTerritoryKey** sütunu arasında bir ilişki oluşturmanız gerekiyor. 

   **SSMS**'de **DimUserSecurity** tablosuna sağ tıklayın ve **Tasarım**'ı seçin. Ardından **Tablo Tasarımcısı -> İlişkiler...** seçeneğini belirtin. İşiniz bittiğinde tabloyu kaydedin.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_keys.png)

3. Tabloya kullanıcıları ekleyin: **DimUserSecurity** tablosuna sağ tıklayın ve **İlk 200 Satırı Düzenle**'yi seçin. Siz kullanıcıları ekledikten sonra **DimUserSecurity** tablosu sizin kendi kullanıcılarınızla aşağıdakine benzer görünmelidir:
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_users.png)
   
   Sonraki görevlerde bu kullanıcıları göreceksiniz.

4. Ardından kullanıcıyla ilişkilendirilmiş bölgelerin ayrıntılarını gösteren **DimSalesTerritory** tablosunda bir *iç birleşim* gerçekleştirin. Buradaki SQL kodu *iç birleşimi* gerçekleştirir ve resimde tablonun bundan sonra nasıl göründüğü gösterilir.
   
       select b.SalesTerritoryCountry, b.SalesTerritoryRegion, a.EmployeeID, a.FirstName, a.LastName, a.UserName from [dbo].[DimUserSecurity] as a join  [dbo].[DimSalesTerritory] as b on a.[SalesTerritoryID] = b.[SalesTerritoryKey]
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_join_users.png)

   Resimde, **2. Adımda** oluşturulan ilişki sayesinde her satış bölgesinden kimin sorumlu olduğu gösterilir. Örneğin **Jon Doe**'nun **Avustralya**'dan sorumlu olduğunu görebilirsiniz. 

## <a name="task-2-create-the-tabular-model-with-facts-and-dimension-tables"></a>2\. Görev: Olgu ve boyut tablolarıyla tablolu modeli oluşturma

1. İlişkisel veri ambarınızı oluşturduktan sonra tablolu modeli tanımlamanız gerekir. Modeli [**SQL Server Veri Araçları'nı (SSDT)** ](https://docs.microsoft.com/sql/ssdt/sql-server-data-tools) kullanarak oluşturursunuz. Daha fazla bilgi için bkz. [Yeni Tablolu Model Projesi Oluşturma](https://msdn.microsoft.com/library/hh231689.aspx).

2. Aşağıda gösterilen şekilde gerekli tüm tabloları modele aktarın.
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/ssdt_model.png)

3. Gerekli tabloları içeri aktardıktan sonra **Okuma** iznine sahip **SalesTerritoryUsers** adlı rolü tanımlamanız gerekir. SQL Server Veri Araçları'nda **Model** menüsünü seçin ve sonra da **Roller**'i seçin. **Rol Yöneticisi** iletişim kutusunda **Yeni**'yi seçin.

4. **Rol Yöneticisi**'nin **Üyeler** sekmesinde **1. Görev, 3. Adım**'da **DimUserSecurity** tablosunda tanımladığınız kullanıcıları ekleyin.
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager.png)

5. Ardından **DimSalesTerritory** ve **DimUserSecurity** tabloları için aşağıda görüntülenen işlevleri **Satır Filtreleri** sekmesinden ekleyin.
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager_complete.png)

6. Bu adımda Windows kullanıcı adının **USERNAME** işlevi tarafından döndürülen kullanıcı adıyla eşleştiği sütun değerlerini döndürmek için **LOOKUPVALUE** işlevini kullanırsınız. Bundan sonra sorguları **LOOKUPVALUE** işlevinin döndürdüğü değerlerinin aynı veya ilişkili tablodaki değerlerle eşleştiği durumlarla sınırlayabilirsiniz. **DAX Filtresi** sütununa aşağıdaki formülü yazın:
   
       =DimSalesTerritory[SalesTerritoryKey]=LOOKUPVALUE(DimUserSecurity[SalesTerritoryID], DimUserSecurity[UserName], USERNAME(), DimUserSecurity[SalesTerritoryID], DimSalesTerritory[SalesTerritoryKey])

    Bu formülde **LOOKUPVALUE** işlevi **DimUserSecurity[SalesTerritoryID]** sütunu için tüm değerleri döndürür ve burada **DimUserSecurity[UserName]** , oturum açmış olan Windows kullanıcı adıyla, **DimUserSecurity[SalesTerritoryID]** ise **DimSalesTerritory[SalesTerritoryKey]** değeriyle aynıdır.
   
    > [!IMPORTANT]
    > Satır düzeyi güvenlik kullanıldığında [USERELATIONSHIP](https://msdn.microsoft.com/query-bi/dax/userelationship-function-dax) DAX işlevinin desteklenmediğine dikkat edin.

   **DimSalesTerritory** içinde gösterilen satırları kısıtlamak için SalesTerritoryKey'in **LOOKUPVALUE** işlevinin döndürdüğü Sales kümesi kullanılır. Yalnızca **SalesTerritoryKey** değerinin **LOOKUPVALUE** işlevi tarafından döndürülen ID değerleri arasında olduğu satırlar görüntülenir.

7. **DimUserSecurity** tablosu için **DAX Filtresi** sütununa aşağıdaki formülü ekleyin:
   
       =FALSE()

    Bu formül tüm sütunların `false` olarak çözümleneceğini belirtir; başka bir deyişle **DimUserSecurity** tablosunun sütunları sorgulanamaz.

8. Şimdi yapmanız gereken modeli işleyip dağıtmaktır. Daha fazla bilgi için [Dağıtım makalesine](https://msdn.microsoft.com/library/hh231693.aspx) bakın.

## <a name="task-3-add-data-sources-within-your-on-premises-data-gateway"></a>3\. Görev: Şirket içi veri ağ geçidinizin içine Veri Kaynaklarını ekleme

Tablolu modeliniz dağıtıldıktan ve kullanıma hazır hale geldikten sonra şirket içi Analysis Services tablolu sunucusuna veri kaynağı bağlantısı eklemeniz gerekir.

1. **Power BI hizmetinin** şirket içi Analysis Services sunucunuza erişmesini sağlamak için ortamınızda yüklenmiş ve yapılandırılmış bir **[şirket içi veri ağ geçidine](service-gateway-onprem.md)** ihtiyacınız vardır.

2. Ağ geçidi doğru şekilde yapılandırıldıktan sonra **Analysis Services** tablolu örneğiniz için bir veri kaynağı bağlantısı oluşturmanız gerekir. Daha fazla bilgi için bkz. [Veri kaynağınızı yönetme - Analysis Services](service-gateway-enterprise-manage-ssas.md).
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_gateway.png)

  Önceki adımı tamamladığınızda ağ geçidi yapılandırılmış ve şirket içi **Analysis Services** veri kaynağınızla etkileşim kurmaya hazır hale gelmiş olur.

## <a name="task-4-create-report-based-on-analysis-services-tabular-model-using-power-bi-desktop"></a>4\. Görev: Power BI Desktop'ı kullanarak Analysis Services tablolu modeline dayanan bir rapor oluşturma

1. **Power BI Desktop** uygulamasını başlatıp **Veri Al > Veritabanı**'nı seçin.

2. Veri kaynakları listesinden **SQL Server Analysis Services Veritabanı**'nı ve ardından **Bağlan**'ı seçin.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata.png)

3. **Analysis Services** tablolu örneğinizle ilgili bilgileri girip **Canlı bağlan**'ı seçin. Ardından **Tamam**'ı seçin. **Power BI**'da dinamik güvenlik yalnızca **Canlı bağlantı** ile kullanılabilir.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)

4. Dağıtılan modelin **Analysis Services** örneğinde olduğunu görebilirsiniz. İlgili modeli ve ardından **Tamam**'ı seçin.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)

   **Power BI Desktop** uygulamasında tuvalin sağ tarafındaki **Alanlar** bölmesinde kullanılabilir durumdaki tüm alanlar görüntülenir.

5. Sağ taraftaki **Alanlar** bölmesinde **FactInternetSales** tablosundan **SalesAmount** ölçüsünü, **SalesTerritory** tablosundan da **SalesTerritoryRegion** boyutunu seçin.

6. Basit bir rapor oluşturmak istediğimiz için şu anda başka sütun eklemeyeceğiz. Verilerin daha anlamlı bir şekilde gösterilmesi için görselleştirme türünü **Halka grafik** olarak değiştirin.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart.png)

7. Raporunuz hazır olduğunda doğrudan Power BI portalında yayımlayabilirsiniz. **Power BI Desktop** uygulamasının **Giriş** şeridinden **Yayımla**'yı seçin.

## <a name="task-5-create-and-share-a-dashboard"></a>5\. Görev: Pano oluşturma ve yapılandırma

1. Raporu oluşturdunuz ve **Power BI** hizmetinde yayımladınız. Şimdi önceki adımlarda oluşturulan örneği kullanarak model güvenliği senaryosunu gösterebilirsiniz.
   
   Sumit **Sales Manager**  rolünde farklı bölgelerdeki tüm satış verilerini görebilir. Sumit raporu oluşturarak (önceki görev adımlarında oluşturulan rapor) Power BI hizmetinde yayımlar.
   
   Sumit’in raporu yayımlandıktan sonra izleyeceği adım Power BI hizmetinde bu raporu temel alan **TabularDynamicSec** adlı bir pano oluşturmadır. Aşağıdaki resimde Sumit'in tüm satış bölgelerine ait verileri görebildiğine dikkat edin.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart_1.png)

2. Şimdi Sumit panoyu Avustralya bölgesinden sorumlu olan iş arkadaşı Jon Doe ile paylaşır.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/user_jon_doe.png)
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_dashboard.png)

3. Jon Doe **Power BI** hizmetinde oturum açıp Sumit tarafından oluşturulan ve paylaşılan panoyu görüntülediğinde, **yalnızca** kendi bölgesine ait veriler görünür olmalıdır. 
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/dashboard_jon_doe.png)

    Tebrikler! **Power BI hizmeti**, şirket içi **Analysis Services** tablolu modelinde tanımlanan dinamik satır düzeyi güvenliği gösterir. Power BI, sorgu oluşturma amacıyla şirket içi veri kaynağına geçerli Power BI kullanıcısının kimlik bilgilerini göndermek için **EffectiveUserName** özelliğini kullanır.

## <a name="task-6-understand-what-happens-behind-the-scenes"></a>6\. Görev: Arka planda gerçekleşen işlemleri anlama

Bu görevde şirket içi SSAS tablolu örneğinizde bir SQL Server Profiler izi yakalamanız gerektiği için [SQL Profiler](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler) hakkında bilgi sahibi olduğunuz kabul edilir.

1. Oturum, kullanıcı (Jon Doe) Power BI hizmetindeki panoya eriştiği anda başlatılır. **salesterritoryusers** rolünün **<EffectiveUserName>jondoe@moonneo.com</EffectiveUserName>** olan geçerli kullanıcı adıyla aynı anda geçerli hale geldiğini görebilirsiniz
   
       <PropertyList><Catalog>DefinedSalesTabular</Catalog><Timeout>600</Timeout><Content>SchemaData</Content><Format>Tabular</Format><AxisFormat>TupleFormat</AxisFormat><BeginRange>-1</BeginRange><EndRange>-1</EndRange><ShowHiddenCubes>false</ShowHiddenCubes><VisualMode>0</VisualMode><DbpropMsmdFlattened2>true</DbpropMsmdFlattened2><SspropInitAppName>PowerBI</SspropInitAppName><SecuredCellValue>0</SecuredCellValue><ImpactAnalysis>false</ImpactAnalysis><SQLQueryMode>Calculated</SQLQueryMode><ClientProcessID>6408</ClientProcessID><Cube>Model</Cube><ReturnCellProperties>true</ReturnCellProperties><CommitTimeout>0</CommitTimeout><ForceCommitTimeout>0</ForceCommitTimeout><ExecutionMode>Execute</ExecutionMode><RealTimeOlap>false</RealTimeOlap><MdxMissingMemberMode>Default</MdxMissingMemberMode><DisablePrefetchFacts>false</DisablePrefetchFacts><UpdateIsolationLevel>2</UpdateIsolationLevel><DbpropMsmdOptimizeResponse>0</DbpropMsmdOptimizeResponse><ResponseEncoding>Default</ResponseEncoding><DirectQueryMode>Default</DirectQueryMode><DbpropMsmdActivityID>4ea2a372-dd2f-4edd-a8ca-1b909b4165b5</DbpropMsmdActivityID><DbpropMsmdRequestID>2313cf77-b881-015d-e6da-eda9846d42db</DbpropMsmdRequestID><LocaleIdentifier>1033</LocaleIdentifier><EffectiveUserName>jondoe@moonneo.com</EffectiveUserName></PropertyList>

2. Analysis Services, geçerli kullanıcı adı isteğine göre yerel Active Directory örneğini sorguladıktan sonra isteği gerçek moonneo/jondoe kimlik bilgisine dönüştürür. **Analysis Services** kimlik bilgilerini aldıktan sonra, kullanıcının görüntüleme ve erişme izni olan verileri döndürür.

3. Panoda daha fazla etkinlik gerçekleştirilirse, örneğin Jon Doe panodan bağlantılı rapora giderse SQL Profiler içinde Analysis Services tablolu modeline DAX sorgusu olarak gönderilen belirli bir sorgu olduğunu görebilirsiniz.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/profiler1.png)

4. Ayrıca, rapor verilerini yerleştirmek için aşağıdaki DAX sorgusunun da yürütüldüğünü görebilirsiniz.
   
   ```
   EVALUATE
     ROW(
       "SumEmployeeKey", CALCULATE(SUM(Employee[EmployeeKey]))
     )
   
   <PropertyList xmlns="urn:schemas-microsoft-com:xml-analysis">``
             <Catalog>DefinedSalesTabular</Catalog>
             <Cube>Model</Cube>
             <SspropInitAppName>PowerBI</SspropInitAppName>
             <EffectiveUserName>jondoe@moonneo.com</EffectiveUserName>
             <LocaleIdentifier>1033</LocaleIdentifier>
             <ClientProcessID>6408</ClientProcessID>
             <Format>Tabular</Format>
             <Content>SchemaData</Content>
             <Timeout>600</Timeout>
             <DbpropMsmdRequestID>8510d758-f07b-a025-8fb3-a0540189ff79</DbpropMsmdRequestID>
             <DbPropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbPropMsmdActivityID>
             <ReturnCellProperties>true</ReturnCellProperties>
             <DbpropMsmdFlattened2>true</DbpropMsmdFlattened2>
             <DbpropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbpropMsmdActivityID>
           </PropertyList>
   ```

## <a name="considerations"></a>Önemli noktalar

* Power BI'da şirket içi satır düzeyi güvenlik yalnızca Canlı Bağlantı ile kullanılabilir.

* Model işlendikten sonra veriler üzerinde yapılan değişiklikler, Power BI hizmetinden **Canlı Bağlantı** aracılığıyla rapora erişen kullanıcılara anında yansıtılır.

