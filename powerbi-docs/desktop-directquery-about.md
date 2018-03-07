---
title: Power BI'da DirectQuery kullanma
description: "Power BI'da DirectQuery kullanmayı anlama"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 572f64cc0e6ba97c62c9a088c60cf3887bacc6ae
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="using-directquery-in-power-bi"></a>Power BI'da DirectQuery kullanma
**Power BI Desktop**'ı veya **Power BI hizmetini** kullanırken her türde farklı veri kaynağına bağlanabilir ve bu veri bağlantılarını farklı şekillerde gerçekleştirebilirsiniz. En çok kullanılan veri alma yöntemi olan *içeri aktarma* seçeneğini kullanarak Power BI'a veri aktarabilir veya **DirectQuery** seçeneğini kullanarak, verilerin bulunduğu özgün kaynak deposuna doğrudan bağlanabilirsiniz. Bu makalede, aşağıdaki konu başlıkları da dahil olmak üzere **DirectQuery** ve özellikleri anlatılmaktadır:

* DirectQuery için farklı bağlantı seçenekleri
* İçeri aktarma yerine DirectQuery kullanmanın tercih edilebileceği durumlara yönelik kılavuz
* DirectQuery kullanmanın dezavantajları
* DirectQuery kullanımına yönelik en iyi uygulama

Kısaca ifade etmek gerekirse içeri aktarma ve DirectQuery kullanmaya yönelik en iyi uygulama şudur:

* Power BI'a veri aktarmak için mümkün olan her durumda **içeri aktarma** seçeneğini kullanmanız gerekir. Böylece Power BI'ın yüksek performanslı sorgu altyapısından faydalanarak yüksek oranda etkileşimli ve tam özellikli bir veri deneyimi elde edebilirsiniz.
* Verileri içeri aktarma seçeneği, hedefinizi karşılamıyorsa **DirectQuery** kullanmayı deneyin. Örneğin, veriler sıklıkla değişiyorsa ve raporların en güncel verileri içermesi gerekiyorsa DirectQuery en iyi seçenek olabilir. Ancak genel olarak, DirectQuery kullanımı yalnızca, temel alınan veri kaynağı tarafından normal toplama sorgusu için etkileşimli sorgu (5 saniyeden kısa) sağlanabildiği ve oluşturulan sorgu yüklemesinin işlenebildiği durumlarda uygundur. Ayrıca, hedeflerinize ulaşabileceğinizden emin olmak için DirectQuery kullanımına yönelik sınırlamaların belirtildiği listeyi de dikkatlice incelemeniz gerekir.

Hem içeri aktarma hem de DirectQuery bağlantı modları için Power BI tarafından sunulan özellikler zamanla geliştirilecektir. Buna, içeri aktarma işleminin daha fazla durumda kullanılabilmesi amacıyla, içeri aktarılan verilerin kullanımında daha çok esneklik sağlamanın yanı sıra DirectQuery kullanımına yönelik dezavantajların bazılarının ortadan kaldırılması da dahildir. İyileştirmelerden bağımsız olarak, temel alınan veri kaynağının performansı DirectQuery kullanımı sırasında dikkate alınması gereken önemli bir nokta olmaya devam edecektir. Temel alınan veri kaynağı yavaşsa bu kaynak için DirectQuery seçeneğinin kullanılması uygun olmaz.

Bu konu başlığı altında SQL Server Analysis Services değil, Power BI ile DirectQuery kullanımı ele alınmaktadır. DirectQuery aynı zamanda bir **SQL Server Analysis Services** özelliğidir ve aşağıda açıklanan ayrıntıların birçoğu bu hizmetin kullanımı için geçerlidir ancak önemli farklar da mevcuttur. SQL Server Analysis Services ile DirectQuery kullanımı hakkında bilgi için [SQL Server Analysis Services 2016'daki DirectQuery özelliğine yönelik ayrıntılı bilgiye yer verilen teknik incelemeye](http://download.microsoft.com/download/F/6/F/F6FBC1FC-F956-49A1-80CD-2941C3B6E417/DirectQuery%20in%20Analysis%20Services%20-%20Whitepaper.pdf) bakın.  

Bu makalede, raporun **Power BI Desktop**'ta oluşturulduğu durumlarda DirectQuery için önerilen iş akışına odaklanılmakla birlikte, doğrudan **Power BI hizmetine** bağlanma konusuna da değinilmektedir.

## <a name="power-bi-connectivity-modes"></a>Power BI bağlantı modları
Power BI aşağıdakiler de dahil olmak üzere çok sayıda çeşitli veri kaynağına bağlanır:

* Çevrimiçi hizmetler (Salesforce, Dynamics 365 ve diğerleri)
* Veritabanları (SQL Server, Access, Amazon Redshift ve diğerleri)
* Basit dosyalar (Excel, JSON ve diğerleri)
* Diğer veri kaynakları (Spark, Web siteleri, Microsoft Exchange ve diğerleri)

Bu kaynaklar için verileri Power BI'a aktarma seçeneği genellikle kullanılabilir. Bazıları için bağlantı DirectQuery kullanılarak da sağlanabilir. DirectQuery'yi destekleyen kaynakların tam listesi, [DirectQuery tarafından desteklenen Veri Kaynakları](desktop-directquery-data-sources.md) makalesinde açıklanmaktadır. DirectQuery ileride daha çok kaynak için kullanıma sunulacak ve bu süreçte öncelikli olarak, iyi bir etkileşimli sorgu performansı göstermesi beklenen kaynaklara odaklanılacaktır.

**SQL Server Analysis Services** için özel bir durum söz konusudur. SQL Server Analysis Services'e bağlanırken verileri içeri aktarmayı seçebilir veya *canlı bağlantıyı* kullanabilirsiniz.  Canlı bağlantı kullanımı, verilerin içeri aktarılmaması ve görsellerin yenilenmesi için, temel alınan veri kaynağının her zaman sorgulanması açısından DirectQuery ile benzerlik gösterir. Ancak, *canlı bağlantı* diğer birçok açıdan farklı olduğu için farklı bir terim (*DirectQuery* yerine *canlı*) kullanılır.

Verilere bağlanmaya yönelik bu üç seçenek (**içeri aktarma**, **DirectQuery** ve **canlı bağlantı**) aşağıdaki bölümlerde ayrıntılı şekilde açıklanmaktadır.

### <a name="import-connections"></a>İçeri aktarma bağlantıları
**Power BI Desktop**'ta SQL Server gibi bir veri kaynağına bağlanmak için **Veri Al** seçeneği kullanıldığında ve **İçeri Aktar** seçildiğinde, bu bağlantının davranışı şu şekilde olur:

* İlk **Veri Al** deneyimi sırasında, tüm seçili tablo kümeleri veri kümesi döndürecek bir sorguyu tanımlar. (Bu sorgular, veriler yüklenmeden önce filtre uygulama, verileri toplama veya farklı tabloları birleştirme gibi işlemler için düzenlenebilir).
* Yüklemenin ardından, bu sorgular tarafından tanımlanan verilerin tümü Power BI önbelleğine aktarılır.
* **Power BI Desktop**'ta bir görsel oluşturulmasının ardından, içeri aktarılan veriler sorgulanır. Power BI deposu, sorgunun çok hızlı olmasını ve böylece tüm değişikliklerin görsele hemen yansıtılmasını sağlar.
* Temel alınan verilerdeki değişiklikler görsellere yansıtılmaz. Verilerin yeniden içeri aktarılması için *Yenile* seçeneğinin kullanılması gerekir.
* Rapor (.pbix dosyası) **Power BI hizmetinde** yayımlandıktan sonra, bir veri kümesi oluşturulur ve Power BI hizmetine yüklenir.  İçeri aktarılan veriler bu veri kümesine eklenir. Ardından, bu veriler için zamanlanmış yenileme (örneğin, verileri her gün yeniden içeri aktarmak üzere) ayarlanabilir. Özgün veri kaynağının konumuna bağlı olarak bir şirket içi veri ağ geçidinin yapılandırılması gerekebilir.
* Var olan bir raporu **Power BI hizmetinde** açarken veya yeni bir rapor yazarken, etkileşimin sağlanması amacıyla, içeri aktarılan veri tekrar sorgulanır.
* Görseller veya rapor sayfalarının tamamı, pano kutucukları olarak sabitlenebilir. Temel alınan veri kümesi yenilendiğinde kutucuklar da otomatik olarak yenilenir.  

### <a name="directquery-connections"></a>DirectQuery bağlantıları
**Power BI Desktop**'ta bir veri kaynağına bağlanmak için **Veri Al** seçeneği kullanıldığında ve **DirectQuery** seçildiğinde, bu bağlantının davranışı şu şekilde olur:

* İlk **Veri Al** deneyimi sırasında kaynak seçilir. İlişkisel kaynaklar için bu durum, her biri mantıksal olarak veri kümesi döndüren bir sorguyu tanımlayan tablolardan oluşan bir kümenin seçileceği anlamına gelir. SAP BW gibi çok boyutlu kaynaklar için yalnızca kaynak seçilir.
* Ancak, yüklemeden sonra Power BI deposuna aslında hiçbir veri aktarılmaz. Bunun yerine, **Power BI Desktop**'ta bir görsel oluşturulduktan sonra, gerekli verilerin alınması için temel alınan veri kaynağına sorgular gönderilir. Ardından, görselin yenilenme süresi temel alınan veri kaynağının performansına bağlı olur.
* Temel alınan verilerdeki değişiklikler var olan görsellere hemen yansıtılmaz. Her bir görsel için gerekli sorguların yeniden gönderilmesi ve görselin gerektiği şekilde güncelleştirilmesi için Yenile seçeneğinin kullanılması yine de gereklidir.
* Rapor **Power BI hizmetinde** yayımlandıktan sonra, Power BI hizmetinde içeri aktarma işleminde olduğu gibi bir Veri Kümesi oluşturulur. Ancak, bu veri kümesine *hiçbir veri* eklenmez.
* Var olan bir raporu **Power BI hizmetinde** açarken veya yeni bir rapor yazarken gerekli verilerin alınması amacıyla, temel alınan veri kaynağı yeniden sorgulanır. Özgün veri kaynağının konumuna bağlı olarak, verilerin yenilenmiş olması durumunda İçeri Aktarma modunda olduğu gibi, bir şirket içi veri ağ geçidinin yapılandırılması gerekebilir.
* Görseller veya rapor sayfalarının tamamı, Pano kutucukları olarak sabitlenebilir. Kutucuklar, panonun hızlıca açılmasının sağlanması için zamanlanmış şekilde (örneğin, saatte bir) otomatik olarak yenilenir. Bu yenilemenin sıklığı, verilerin hangi sıklıkta değiştiğinin ve en son verilerin gösterilmesinin ne kadar önemli olduğunun yansıtılması amacıyla kontrol edilebilir. Bu nedenle, bir pano açıldığında kutucuklar son yenileme tarihindeki verileri yansıtır ve temel alınan kaynakta yapılan en son değişiklikleri göstermeyebilir. Açık bir panonun güncel olmasının sağlanması amacıyla Yenile seçeneği her zaman kullanılabilir.    

### <a name="live-connections"></a>Canlı bağlantılar
**SQL Server Analysis Services** (SSAS) hizmetine bağlanılırken, seçili veri modelinden veri aktarma veya bu veri modeli ile canlı bağlantı kurma seçeneği sunulur. **İçeri aktarma** seçeneğini belirlerseniz bu dış SSAS kaynağına yönelik bir sorgu tanımlarsınız ve veriler normal şekilde içeri aktarılır. **Canlı bağlantı kurma** seçeneğini belirlerseniz hiçbir sorgu tanımlanmaz ve dış modelin tamamı alan listesinde gösterilir. **DirectQuery** seçildiğinde görseller oluşturulurken dış SSAS kaynağına sorgular gönderilir. Ancak, DirectQuery'nin aksine yeni bir *model* oluşturulması gerekmez. Diğer bir deyişle, yeni hesaplanmış sütun, hiyerarşi, ilişki ve benzeri özelliklerin tanımlanması mümkün değildir. Bunun yerine, doğrudan dış SSAS modeline bağlanırsınız.

Önceki paragrafta açıklanan durum aşağıdaki kaynaklarla bağlantı kurulurken de geçerlidir ancak verileri içeri aktarma seçeneği sunulmaz:

* Power BI veri kümeleri (örneğin, önceden oluşturulmuş ve hizmette yayımlanmış bir Power BI veri kümesine, üzerine yeni bir rapor yazmak amacıyla bağlanılırken)
* Common Data Services

SSAS üzerinden alınan raporların **Power BI hizmetinde** yayımlandıktan sonraki davranışı, şu açılardan DirectQuery raporları ile benzerlik gösterir:

* Var olan bir raporu **Power BI hizmetinde** açarken veya yeni bir rapor yazarken, temel alınan SSAS kaynağı sorgulanır (şirket içi veri ağ geçidi gerekebilir)
* Pano kutucukları bir zamanlamaya göre (örneğin, saatte bir veya tanımlanan sıklıkta) otomatik olarak yenilenir

Ancak, bazı önemli farklar da bulunur. Örneğin, canlı bağlantılar için, raporu açan kullanıcının kimliği her zaman, temel alınan SSAS kaynağına aktarılır.

Bu karşılaştırmalara değindiğimize göre, makalenin geri kalanında yalnızca **DirectQuery**'ye odaklanabiliriz.

## <a name="when-is-directquery-useful"></a>DirectQuery ne zaman fayda sağlar?
Aşağıdaki tabloda, verilerin özgün kaynakta bırakılmasının yararlı kabul edilebileceği durumlar da dahil olmak üzere, DirectQuery ile bağlanmanın özellikle faydalı olabileceği senaryolar açıklanmaktadır. Açıklamaya, belirtilen senaryonun Power BI'da kullanılıp kullanılamayacağı bilgisi de eklenmiştir.

| Sınırlama | Açıklama |
| --- | --- |
| Verilerin sıklıkla değişmesi ve neredeyse "gerçek zamanlı" raporlamanın gerekli olması |İçeri aktarılan verilere sahip modeller en fazla saatte bir kez yenilenebilir. Bu nedenle, veriler sürekli değişiyorsa ve raporlarda son verilerin gösterilmesi gerekiyorsa zamanlanmış yenileme ile İçeri Aktarma seçeneğinin kullanılması bu ihtiyaçları karşılamayabilir. Power BI'a doğrudan veri akışı yapılabileceğini de unutmayın. Ancak, bu durum için desteklenen veri hacimlerine yönelik sınırlamalar mevcuttur. <br/> <br/> Bunun aksine, DirectQuery kullanıldığında bir raporun veya panonun açılmasının ya da yenilenmesinin ardından her zaman kaynaktaki en son veriler gösterilir. Buna ek olarak, pano kutucukları daha sık şekilde (her 15 dakikada bir) güncelleştirilebilir. |
| Verilerin çok büyük olması |Veriler çok büyükse tümünün içeri aktarılması uygun olmaz. Bunun aksine, sorgulama işlemi yerinde gerçekleştiğinden DirectQuery için büyük bir veri aktarımı gerekmez. <br/> <br/> Ancak, büyük veriler, temel alınan kaynakta sorgulama performansının çok yavaş olacağı anlamına da gelebilir. (Bu makaledeki *DirectQuery kullanmanın etkileri* bölümünde bu konuya değinilmiştir.) Ayrıca, verilerin tüm ayrıntılarıyla içeri aktarılması her zaman gerekli değildir. Bunun yerine, veriler içeri aktarma sırasında önceden toplanabilir. (**Sorgu Düzenleyicisi** tam olarak bunun yapılmasını kolaylaştırır.) Uç durumlar söz konusu olduğunda, her bir görsel için tam olarak gerekli olan toplama verileri içeri aktarılabilir. Bu nedenle, büyük veriler için en kolay yaklaşım DirectQuery olsa da, temel alınan kaynağın çok yavaş olduğu durumlarda toplama verilerinin içeri aktarılmasının bir çözüm sunabileceğini göz önünde bulundurun. |
| Temel alınan kaynakta güvenlik kurallarının tanımlanmış olması |Veriler içeri aktarıldığında, Power BI geçerli kullanıcı kimlik bilgilerini (Power BI Desktop'tan) veya zamanlanmış yenileme yapılandırmasında tanımlanan kimlik bilgilerini (Power BI hizmetinden) kullanarak veri kaynağına bağlanır. Bu nedenle, böyle bir rapor yayımlanırken ve paylaşılırken raporun yalnızca söz konusu verileri görme izni olan kullanıcılarla paylaşıldığına veya veri kümesinin parçası olarak Satır Düzeyi Güvenlik tanımlandığına dikkat edilmesi gerekir. <br/> <br/> DirectQuery her zaman, temel alınan kaynağı sorguladığından bunun yapılması ideal olarak temel alınan kaynaktaki güvenliğin uygulanmasını sağlar. Ancak, Power BI temel alınan kaynağa her zaman İçeri Aktarma için kullanılan kimlik bilgileriyle bağlanır. <br/> <br/> Bu nedenle Power BI, rapor kullanıcısının kimliğinin temel alınan kaynaktan geçmesine izin verene kadar DirectQuery, veri kaynağı güvenliği açısından hiçbir avantaj sunmaz. |
| Veri hakimiyeti kısıtlamalarının geçerli olması |Bazı kuruluşların veri hakimiyeti ilkeleri bulunur, böylece veriler kuruluş dışına çıkamaz. İçeri aktarma tabanlı bir çözüm sorunlara neden olabilir. Bunun aksine, DirectQuery ile bu veriler temel alınan kaynakta kalır. <br/> <br/> Ancak, DirectQuery ile dahi görsel düzeydeki bazı veri önbelleklerinin Power BI hizmetinde tutulduğu (zamanlanmış kutucuk yenilemesi nedeniyle) unutulmamalıdır. |
| Temel alınan veri kaynağının, ölçüler içeren bir OLAP kaynağı olması |Temel alınan veri kaynağı *ölçüler* (SAP HANA veya SAP Business Warehouse gibi) içeriyorsa verilerin içeri aktarılması başka sorunlara neden olur. İçeri aktarılan verilerin, sorgu ile tanımlandığı üzere belirli bir toplama düzeyinde olduğu anlamına gelir. Örneğin, Class, Year ve City verilerine göre TotalSales ölçüsü. Ardından, daha yüksek düzeyde bir toplama işlemine ihtiyaç duyan verileri (Year verilerine göre TotalSales gibi) gerektiren bir görsel oluşturulursa toplam değer yeniden hesaplanır. Bu durum eklenebilir ölçüler için (Toplam, Minimum gibi) sorun oluşturmazken, eklenebilir olmayan ölçüler için (Ortalama, Ayrı Say gibi) soruna yol açar. <br/> <br/> Doğru toplama verilerinin (belirli bir görsel için gerektiği şekilde) doğrudan kaynaktan alınmasının kolaylaştırılması amacıyla, sorguların DirectQuery'de olduğu gibi görsel başına gönderilmesi gerekir. <br/> <br/> SAP Business Warehouse (BW) bağlantısında, DirectQuery'nin seçilmesi ölçülerin bu şekilde işlenmesini sağlar. SAP BW desteği [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md) makalesinde ayrıntılı olarak ele alınmaktadır. <br/> <br/> Ancak, şu anda SAP HANA üzerinden DirectQuery, ilişkisel kaynakla aynı şekilde işler ve bu nedenle içeri aktarma deneyimindekine benzer bir davranış sunar. Buna [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md) makalesinde ayrıntılı olarak değinilmiştir. |

Özetlemek gerekirse, Power BI'daki mevcut özellikleri göz önünde bulundurulduğunda DirectQuery, aşağıdaki senaryolarda avantaj sunmaktadır:

* Verilerin sıklıkla değişmesi ve neredeyse "gerçek zamanlı" raporlamanın gerekli olması
* Çok büyük verileri önceden toplama gerekmeden işleme
* Veri hakimiyeti kısıtlamalarının geçerli olması
* Kaynağın, ölçüler içeren çok boyutlu bir kaynak (SAP BW gibi) olması

Önceki listede bulunan ayrıntıların yalnızca Power BI kullanımına yönelik olduğunu unutmayın. Verileri içeri aktarma için dış SQL Server Analysis Services (veya Azure Analysis Services) modelini kullanma ve ardından Power BI kullanarak bu modele bağlanma seçeneği her zaman kullanılabilir. Bu yaklaşım ek beceriler gerektirse de daha iyi bir esneklik sunar. Örneğin, çok daha büyük veri hacimleri içeri aktarılabilir ve verilerin ne sıklıkta yenileneceğine yönelik herhangi bir sınırlama bulunmaz.

## <a name="implications-of-using-directquery"></a>DirectQuery kullanmanın etkileri
Bu bölümde açıklandığı üzere, **DirectQuery** kullanmanın olumsuz etkileri olabilir. Bu sınırlamaların bazıları, kullanılan kaynağa bağlı olarak biraz farklılık gösterebilir. Uygun olduğunda buna değinilecektir ve önemli ölçüde farklılık gösteren kaynaklar ayrı konu başlıkları altında ele alınacaktır.  

### <a name="performance-and-load-on-the-underlying-source"></a>Temel alınan kaynakta performans ve yükleme
**DirectQuery** kullanılırken genel deneyim büyük oranda, temel alınan veri kaynağının performansına bağlıdır. Her bir görselin yenilenmesi (örneğin, bir dilimleyici değeri değiştirildikten sonra) birkaç saniye (5 saniyeden az) sürüyorsa bu deneyimin makul düzeyde olduğu kabul edilir ancak yine de verileri Power BI'a aktarırken almaya alışkın olduğunuz anlık yanıtla karşılaştırdığınızda bu işlemin yavaş ilerlediğini düşünebilirsiniz. Kaynağın yavaşlığı, her bir görselin daha uzun sürede (onlarca saniye) yenilenmesine neden olursa deneyim son derece kötü hale gelir ve hatta sorgular zaman aşımına uğrar.

Temel alınan kaynağın performansının yanı sıra, kaynağa yerleştirilecek (ve performansı etkileyecek olan) yük de dikkatli bir şekilde değerlendirilmelidir. Aşağıda daha ayrıntılı şekilde açıklandığı üzere, paylaşılan bir raporu açan her bir kullanıcı ve düzenli aralıklarla yenilenen her bir pano kutucuğu, temel alınan kaynağa görsel başına en az bir sorgu gönderir. Bunun için, kaynağın böyle bir sorgu yükünü, makul performans göstermeye devam ederken işleyebilmesi gerekir.

### <a name="limited-to-a-single-source"></a>Tek bir kaynakla sınırlı olma
Verileri içeri aktarırken, kurumsal bir SQL Server veritabanındaki bazı verileri, bir Excel dosyasında tutulan bazı yerel verilerle kolayca birleştirme örneğinde olduğu gibi, birden çok kaynaktan alınan veriler tek bir modelde birleştirilebilir. Bu işlem DirectQuery kullanılırken gerçekleştirilemez. Bir kaynak için DirectQuery seçeneği belirlendiğinde yalnızca bu kaynaktaki (tek bir SQL Server veritabanı gibi) veriler kullanılabilir.

### <a name="limited-data-transformations"></a>Veri dönüştürme işlemine yönelik sınırlamalar
Benzer şekilde, **Sorgu Düzenleyicisi**'nde uygulanabilecek veri dönüştürme işlemlerine yönelik sınırlamalar mevcuttur. Veriler içeri aktarıldığında, görsel oluşturmada kullanılmadan önce söz konusu verilerin temizlenmesi ve yeniden şekillendirilmesi için bir dizi kapsamlı dönüştürme işlemi (JSON belgelerini ayrıştırma veya bir sütundan satır hizalamalı bir forma veri özetleme gibi) kolayca uygulanabilir. Bu dönüştürme işlemleri için DirectQuery'de daha fazla sınırlama mevcuttur. İlk olarak, SAP Business Warehouse gibi bir OLAP kaynağına bağlanılırken hiçbir dönüştürme tanımlanamaz ve dış "modelin" tamamı kaynaktan alınır. SQL Server gibi ilişkisel kaynaklarda her sorgu için bir dizi dönüştürme tanımlanabilir, ancak bu dönüştürme işlemleri performans nedeniyle sınırlıdır. Bu tür dönüştürme işlemlerinin veriler yenilendikçe değil, temel alınan kaynağa her sorgu gönderildiğinde uygulanması gerekir. Böylece bu işlem, tek bir yerel sorguya makul şekilde çevrilebilen dönüştürmelerle sınırlıdır. Fazla karmaşık bir dönüştürme kullanmanız durumunda, dönüştürmenin silinmesini veya modelin İçeri Aktarma moduna geçirilmesini belirten bir hata iletisi alırsınız.

Ayrıca, **Veri Al** iletişim kutusundan veya **Sorgu Düzenleyicisi**'nden elde edilen sorgu, görsel için gereken verileri almak üzere oluşturulan ve gönderilen sorgulardaki bir alt seçimde kullanılır. Bu nedenle, Sorgu Düzenleyicisi'nde tanımlanan sorgu, bu bağlamda geçerli olmalıdır. Bu durum tam olarak, Ortak Tablo İfadeleri kullanılarak bir sorgu oluşturulamadığı ve Saklı Yordamların çağrılmadığı anlamına gelir.

### <a name="modelling-limitations"></a>Modelleme sınırlamaları
Bu bağlamda *modelleme* terimi, ham veriler kullanılarak rapor yazılırken verilerin iyileştirilmesi ve zenginleştirilmesi anlamına gelir. Örnekler arasında şunlar yer almaktadır:

* Tablolar arasında ilişki tanımlama
* Yeni hesaplamalar ekleme (hesaplanmış sütunlar ve ölçüler)
* Sütunları ve ölçüleri yeniden adlandırma ve gizleme
* Hiyerarşi tanımlama
* Sütunlar için biçimlendirme, varsayılan özetleme ve sıralama düzeni tanımlama
* Değerleri gruplandırma veya kümeleme

**DirectQuery** kullanılırken bu model zenginleştirmelerinin birçoğu yapılabilir ve daha sonraki kullanımların iyileştirilmesi için ham veriler de zenginleştirilebilir. Ancak, DirectQuery ile bazı modelleme özellikleri kullanılamaz veya sınırlıdır. Sınırlamalar, genellikle performans sorunlarından kaçınmak için uygulanır. Tüm DirectQuery kaynaklarında yaygın olarak görülen sınırlamalar aşağıdaki madde işaretli listede belirtilmiştir. Bu makalenin sonlarında yer alan *Veri kaynağına özgü ayrıntılar* bölümünde açıklandığı üzere, farklı kaynaklar için ek sınırlamalar söz konusu olabilir.

* **Yerleşik tarih hiyerarşisinin olmaması:** Veriler içeri aktarılırken, tüm tarih/tarih saat sütunlarında varsayılan olarak yerleşik bir tarih hiyerarşisi de bulunur. Örneğin, OrderDate sütununu içeren satış siparişleri tablosunu içeri aktarıyorsanız bir görselde OrderDate kullanılırken, kullanılacak uygun düzeyi (Year, Month, Day) seçebilirsiniz. DirectQuery modunda bu yerleşik tarih hiyerarşisi kullanılamaz. Ancak, temel alınan kaynakta Date tablosu bulunuyorsa (birçok veri ambarında yaygın olarak bulunur) DAX Akıllı Zaman Gösterimi işlevlerinin normal şekilde kullanılabileceğini unutmayın.
* **Hesaplanmış sütunlara yönelik sınırlamalar:** Hesaplanmış sütunlar satır içi işlemlerle sınırlıdır; herhangi bir toplama işlevi kullanılmadan yalnızca aynı tablonun diğer sütunlarındaki değerlerine başvurabilir. Buna ek olarak, izin verilen DAX skaler işlevleri (LEFT () gibi), temel alınan kaynağa kolayca gönderilebilecek olanlarla sınırlıdır. Bu nedenle, kaynağın tam olarak hangi özelliklere sahip olduğuna göre değişiklik gösterir. Hesaplanmış bir sütun için DAX yazılırken, desteklenmeyen işlevler otomatik tamamlamada listelenmez ve kullanılırsa hataya neden olur.
* **Üst-alt DAX işlevlerinin desteklenmemesi:** DirectQuery modelinde, genellikle Üst-Alt yapıları (hesaplar grafiği ve çalışan hiyerarşileri gibi) işleyen DAX PATH() işlev ailesini kullanmak mümkün değildir.
* **Ölçüler için sınırlamalar (varsayılan):** Ölçülerde kullanılabilecek DAX işlevleri ve ifadeleri varsayılan olarak sınırlıdır. Burada da, listelenen işlevler otomatik tamamlamada sınırlanır ve geçersiz bir işlev veya ifade kullanılırsa hata oluşur. Bunun nedeni ölçülerin varsayılan olarak, kendi başlarına herhangi bir performans sorunu oluşturması olası olmayan basit ölçülerle sınırlı olmasını sağlamaktır. İleri düzey kullanıcılar **Dosya > Seçenekler**, **Ayarlar > Seçenekler > DirectQuery** ve ardından *DirectQuery modunda kısıtlanmamış ölçümlere izin verin*'i seçerek bu sınırlamayı atlamayı tercih edebilir. Bu seçenek belirlendiğinde, bir ölçü için geçerli olan tüm DAX ifadeleri kullanılabilir. Ancak, kullanıcılar, içeri aktarıldığında iyi performans gösteren bazı ifadelerin, DirectQuery modunda arka uç kaynağa çok yavaş sorgu gönderilmesine neden olabileceğini göz önünde bulundurmalıdır.
  
  * Örneğin, varsayılan olarak:
    
    * Satış tutarını toplayan bir ölçü yazılabilir:
      
          SalesAmount = SUMX(Web_Sales, [ws_sales_price]* [ws_quantity])
    * Tüm Öğeler genelinde SalesAmount ortalaması çıkaran bir ölçü yazılması mümkün *değildir*:
      
          AverageItemSalesAmount = AVERAGEX('Item', [SalesAmount])
    
    Bunun nedeni, çok sayıda öğe bulunması durumunda bu ölçünün düşük bir performansa neden olabileceğidir.
* **Hesaplanmış tabloların desteklenmemesi:** DAX ifadesi kullanarak hesaplanmış tablo tanımlama özelliği, DirectQuery modunda desteklenmez.
* **İlişki filtrelemenin tek bir yönle sınırlı olması:** DirectQuery kullanılırken bir ilişkideki Çapraz Filtre yönü "Her İkisi De" olarak ayarlanamaz. Örneğin, aşağıdaki üç tablo ile her bir Customer[Gender] verisini ve her müşterinin satın aldığı Product[Category] sayısını gösteren bir görsel oluşturulamaz. Bu türde iki yönlü filtreleme kullanımı [bu teknik incelemede ayrıntılı şekilde](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional cross-filtering in Analysis Services 2016 and Power BI.docx) açıklanmıştır. (Yazıda SQL Server Analysis Services bağlamında örnekler sunulmuştur ancak temel noktalar Power BI için de geçerlidir.)
  
  ![](media/desktop-directquery-about/directquery-about_01.png)
  
  Aynı şekilde, sınırlamanın nedeni performansa yönelik etkileridir. Bunun özellikle önemli olduğu uygulamalardan biri de raporun parçası olarak Satır Düzeyi Güvenlik tanımlanırken kullanılmasıdır. Genelde kullanıcılar ve erişmelerine izin verilen varlıklar arasında çoka çok ilişki bulunur ve bunun zorlanması için iki yönlü filtreleme kullanımı gereklidir. Ancak, DirectQuery modelleri için iki yönlü filtreleme kullanımında, performansı kötü etkileyebilecek noktalara dikkat edilmelidir.  
* **Kümelemenin olmaması:** DirectQuery kullanılırken grupları otomatik olarak bulmak için Kümeleme özelliği kullanılamaz

### <a name="reporting-limitations"></a>Raporlama sınırlamaları
DirectQuery modelleri için neredeyse tüm raporlama özellikleri desteklenir. Bu nedenle, temel alınan kaynak uygun düzeyde performans sunduğu sürece aynı görselleştirme kümesi kullanılabilir. Ancak, bir rapor yayımlandıktan sonra **Power BI hizmetinde** sunulan özelliklerin bazılarında önemli sınırlamalar bulunur ve bunlar aşağıda maddeler halinde açıklanmıştır:

* **Hızlı Öngörüler'in desteklenmemesi:** Power BI Hızlı Öngörüler, ilgi çekici olabilecek öngörüleri keşfetmek üzere kapsamlı algoritmalar uygularken veri kümenizin farklı alt kümelerinde arama yapar. Çok yüksek performanslı sorgular gerektiğinden bu özellik, DirectQuery modundaki veri kümelerinde kullanılamaz.
* **Soru-Cevap özelliğinin desteklenmemesi:** Power BI Soru-Cevap, kullanımı kolay, doğal dil özelliklerinden yararlanarak verilerinizi araştırmanızı ve grafikler ile graflar biçiminde cevaplar almanızı sağlar. Ancak bu özellik, DirectQuery kullanan veri kümelerinde şu anda desteklenmiyor.
* **Excel'de Çözümle kullanımının daha düşük performansa neden olma olasılığı:** Bir veri kümesinde "Excel'de Çözümle" özelliğini kullanarak verilerinizi araştırabilirsiniz. Bu, Excel'de Özet Tabloların ve Özet Grafiklerin oluşturulmasını sağlar. DirectQuery kullanan veri kümelerinde bu özellik desteklense de, Power BI'da görsel oluşturmaya kıyasla performans genelde daha yavaş olur. Bu nedenle, senaryolarınız için Excel kullanımı önemliyse DirectQuery kullanıp kullanmayacağınıza karar verirken bu sınırlamayı göz önünde bulundurun.

### <a name="security"></a>Güvenlik
Bu makalede daha önce bahsedildiği üzere, **DirectQuery** kullanan bir rapor **Power BI hizmetinde** yayımlanmasının ardından, temel alınan veri kaynağına bağlanmak için her zaman aynı kimlik bilgilerini kullanır. Bu durumun SQL Server Analysis Services'e yönelik canlı bağlantılar için değil, yalnızca DirectQuery ile ilgili olduğunu unutmayın. Bu nedenle, bir DirectQuery raporunun yayımlanmasının hemen ardından, kullanılacak kullanıcı kimlik bilgilerinin yapılandırılması gerekir. Bu yapılmadan raporun Power BI hizmetinde açılması hataya neden olur.

Kullanıcı kimlik bilgileri sağlandıktan sonra, *raporu açan kullanıcıdan bağımsız olarak* bu kimlik bilgileri kullanılır. Bu bakımdan, verilerin içeri aktarıldığı senaryodakine tamamen benzer bir durum söz konusudur; raporun parçası olarak Satır Düzeyi Güvenlik tanımlanmadığı sürece tüm kullanıcılar aynı verileri görür. Bu nedenle, temel alınan kaynakta tanımlanmış herhangi bir güvenlik kuralı varsa rapor paylaşılırken de aynı dikkat gösterilmelidir.

### <a name="behavior-in-the-power-bi-service"></a>Power BI hizmetindeki davranış
Bu bölümde, öncelikli olarak rapor ve panonun paylaşılacağı kullanıcı sayısı, raporun karmaşıklığı ve raporda Satır Düzeyi Güvenlik tanımlanıp tanımlanmadığı açısından arka uç veri kaynağına uygulanacak yük derecesini anlayabilmek için **DirectQuery** raporunun **Power BI hizmetindeki** davranışı açıklanmaktadır.

#### <a name="reports--opening-interacting-with-editing"></a>Raporlar - açma, etkileşim kurma, düzenleme
Bir rapor açıldığında, o anda görünen sayfadaki tüm görseller yenilenir. Genellikle her bir görsel için, temel alınan veri kaynağına en az bir sorgu gönderilmesi gerekir. Bazı görseller için (örneğin, iki farklı olgu tablosundaki toplam değerleri gösteriyorsa, daha karmaşık bir ölçü içeriyorsa veya Ayrı Say gibi eklenebilir olmayan bir ölçünün toplamını içeriyorsa) birden fazla sorgu gerekebilir. Yeni bir sayfaya taşıma, görsellerin yenilenmesine ve böylece temel alınan kaynak için yeni bir sorgu kümesi oluşmasına neden olur.

Rapordaki kullanıcı etkileşimlerinin her biri, görsellerin yenilenmesine neden olabilir. Örneğin, bir dilimleyicide farklı bir değerin seçilmesi, etkilenen tüm görsellerin yenilenmesi için yeni bir sorgu kümesi gönderilmesini gerektirir. Bir filtre değiştirildiğinde veya diğer görselleri çapraz vurgulamak için bir görsele tıklandığında da aynı durum geçerlidir.  

Aynı şekilde, yeni bir raporu düzenlemek için, istenen görselin son halini oluşturmaya yönelik her adımda sorgular gönderilmesi gerekir.

Aynı sonuçların kısa süre önce elde edilmiş olması durumunda görselin anında yenilenmesi için sonuçlar bir noktaya kadar önbelleğe alınır. Raporun parçası olarak herhangi bir Satır Düzeyi Güvenlik tanımlanmışsa bu önbellekler kullanıcılar arasında paylaşılmaz.

#### <a name="dashboard-refresh"></a>Pano Yenileme
Tek başına görseller veya sayfaların tamamı panoya kutucuk olarak sabitlenebilir. **DirectQuery** veri kümelerini temel alan kutucuklar bir zamanlamaya göre otomatik olarak yenilenir ve bunun sonucunda, arka uç veri kaynağına sorgular gönderilir. Bu durum varsayılan olarak saatte bir gerçekleşir ancak Veri Kümesi ayarlarının parçası olarak haftada bir veya 15 dakikada bir olacak şekilde yapılandırılabilir.

Modelde Satır Düzeyi Güvenlik tanımlanmamışsa bu, her kutucuğun bir kere yenileneceği ve sonuçların tüm kullanıcılar arasında paylaşılacağı anlamına gelir. Satır Düzeyi Güvenlik tanımlanmışsa büyük bir çarpan etkisi oluşur. Temel alınan kaynağa her bir kutucuk için kullanıcı başına ayrı sorgular gönderilmesi gerekir.  

Bu nedenle on kutucuğu olan, 100 kullanıcı ile paylaşılan, Satır Düzeyi Güvenlik ile **DirectQuery** kullanan bir veri kümesinde oluşturulan ve 15 dakikada bir yenilenecek şekilde yapılandırılan bir pano için arka uç kaynağa 15 dakikada bir en az 1000 sorgu gönderilir.

Bu nedenle, Satır Düzeyi Güvenlik kullanımına ve yenileme zamanlaması yapılandırmasına dikkat edilmelidir.

#### <a name="timeouts"></a>Zaman aşımları
**Power BI hizmetinde** her sorgu için dört dakikalık bir zaman aşımı uygulanır ve daha uzun süren sorgular başarısız olur. Daha önce belirtildiği üzere, DirectQuery'nin etkileşimli denebilecek düzeyde sorgu performansı sunan kaynaklarda kullanılması önerilir. Bu sınırlamanın amacı, aşırı uzun yürütme sürelerinden kaynaklanabilecek sorunları önlemektir.

### <a name="other-implications"></a>Diğer etkiler
**DirectQuery** kullanmanın diğer genel etkilerinden bazılarını aşağıda bulabilirsiniz:

* **Veriler değiştiğinde güncel verilerin gösterilmesi için Yenile seçeneğinin kullanılması gerekliliği:** Önbellek kullanımı nedeniyle görselde en güncel veriler gösterilmeyebilir. Örneğin, bir görselde bir önceki günün işlemleri gösteriliyor olabilir. Ardından, bir dilimleyicinin değiştirilmesiyle veriler, yeni yapılanlar da dahil olmak üzere son iki güne ait işlemler gösterilecek şekilde yenilenebilir. Dilimleyicinin özgün değerine döndürülmesi, daha önce alınan önbellek değerinin yeniden gösterilmesine neden olur ve yeni yapılan işlemler gösterilmez.
  
  Yenile seçeneği belirlendiğinde önbellekler temizlenir ve en güncel verilerin gösterilmesi için sayfadaki tüm görseller yenilenir.
* **Veriler değiştiğinde görseller arasında tutarlılık olmama olasılığı:** Aynı sayfadaki veya farklı sayfalardaki değişik görseller farklı zamanlarda yenilenebilir. Bu nedenle, temel alınan kaynaktaki veriler değiştiğinde, veriler her bir görselde tam olarak aynı zamanda gösterilmeyebilir. Bazen tek bir görsel için bazen birden fazla sorgu gerektiğinden (örneğin, ayrıntıları ve toplamları elde etmek için) aslında tek bir görselde bile tutarlılık garantisi yoktur. Tutarlılığın sağlanması için, herhangi bir görsel yenilendiğinde tüm görsellerin yenilenme ek yükü ile birlikte, temel alınan veri kaynağında Anlık Görüntü Yalıtımı gibi ek yük getirecek özelliklerin kullanılması gerekir.
  
  Sayfadaki tüm görsellerin yenilenmesi için Yenile seçeneğinin belirlenmesi ile bu sorun büyük ölçüde azaltılabilir. İçeri Aktarma modu kullanılırken de verilerin birden fazla tablodan içeri aktarılması durumunda aynı tutarlılık garantisi sorunu yaşanır.
* **Power BI Desktop'ta meta veri değişikliklerinin yansıtılması için yenileme gerekliliği:** Bir rapor yayımlandıktan sonra, Yenile seçeneği belirlendiğinde rapordaki görseller yenilenir. Temel alınan kaynağın şemasının değişmesi durumunda bu değişiklikler, alan listesindeki mevcut alanlar değiştirilecek şekilde otomatik olarak uygulanmaz. Bu nedenle, temel alınan kaynaktan tablo veya sütun kaldırılmışsa yenileme işleminin ardından sorgu hatası oluşabilir. Rapor Power BI Desktop'ta açıldıktan sonra Yenile seçeneği belirlendiğinde modeldeki alanlar, değişiklikleri yansıtacak şekilde güncelleştirilir.
* **Bir sorgunun döndürebileceği satır sayısının bir milyon ile sınırlı olması:** Temel alınan kaynağa yönelik tek bir sorgu için, döndürülebilecek satır sayısı bir milyon ile sınırlıdır. Bunun genellikle uygulamada bir etkisi yoktur ve görseller bu kadar çok noktayı görüntülemez. Ancak, Power BI'ın gönderilen sorguları tamamen iyileştirmediği durumlarda ve sınırı aşan bazı ara sonuçlar istendiğinde bu sınır ile karşılaşılabilir. Bu sınır aynı zamanda, bir görsel oluşturulurken daha makul bir son durumun elde edilmesi için de uygulanabilir. Örneğin, bir filtre uygulanmadığı sürece, 1 milyondan fazla müşteri olması durumunda Customer ve TotalSalesQuantity sütunlarının eklenmesi bu sınıra ulaşılmasına neden olur.
  
  "Dış veri kaynağında gerçekleştirilen bir sorguya ilişkin sonuç kümesi, izin verilen maksimum boyutu ('1000000' satır) aştı" hata iletisi döndürülür.
* **İçeri aktarma modundan DirectQuery moduna geçilememesi:** Genel olarak, DirectQuery modundaki bir model, içeri aktarma modunda kullanılmak üzere değiştirilebilse de gerekli tüm verilerin içeri aktarılması gerektiği unutulmamalıdır. Ayrıca, (temelde DirectQuery modunda desteklenmeyen özellikler nedeniyle) önceki moda geri dönülemez. Dış ölçüleri tamamen farklı ele aldıklarından, SAP BW gibi çok boyutlu kaynaklara ait DirectQuery modelleri için de DirectQuery modundan içeri aktarma moduna geçiş yapılamaz.

## <a name="directquery-in-the-power-bi-service"></a>Power BI hizmetinde DirectQuery
**Power BI Desktop**'ta tüm kaynaklar desteklenir. Ayrıca, bazı kaynaklar doğrudan **Power BI hizmetinden** kullanılabilir. Örneğin, bir işletme kullanıcısı Salesforce'taki verilerine bağlanmak için Power BI'ı kullanabilir ve **Power BI Desktop**'ı kullanmadan anında bir pano elde edebilir.

DirectQuery özellikli kaynakların yalnızca ikisi hizmette doğrudan kullanılabilir:

* Spark
* Azure SQL Veri Ambarı

Ancak, bu iki kaynak üzerinde gerçekleştirilecek herhangi bir **DirectQuery** kullanımının **Power BI Desktop**'tan başlatılması önemle önerilir. Bunun nedeni, bağlantının başlangıçta **Power BI hizmetinden** gerçekleştirilmesi halinde birçok önemli sınırlamanın uygulanacak olmasıdır. Power BI hizmetinden basit bir başlangıç yapılsa da elde edilen raporun zenginleştirilmesine yönelik sınırlamalar mevcuttur. Örneğin, daha sonra herhangi bir hesaplama oluşturulamaz, birçok analitik özellik kullanılamaz ve hatta meta veriler, temel alınan şemadaki değişiklikler yansıtılacak şekilde yenilenemez.   

## <a name="guidance-for-using-directquery-successfully"></a>DirectQuery'yi başarılı bir şekilde kullanma kılavuzu
Bu bölümde, **DirectQuery**'yi başarılı bir şekilde kullanmaya ilişkin üst düzey bir rehberlik sağlanmaktadır. Rehberlik için, DirectQuery'nin bu makalede açıklanan etkilerinden yola çıkılmıştır.

### <a name="backend-data-source-performance"></a>Arka uç veri kaynağı performansı
Basit görsellerin makul bir sürede yenilenebileceğinin doğrulanması önemle önerilir. Makul bir etkileşim deneyiminin sunulması için bu işlemin 5 saniye içinde gerçekleşmesi gerekir. Görsellerin yenilenmesi 30 saniyeden uzun sürüyorsa rapor yayımlandıktan sonra büyük olasılıkla daha fazla sorun ortaya çıkar ve çözüm kullanılamaz hale gelir.

Sorguların yavaş olması durumunda ilk olarak, temel alınan kaynağa gönderilen sorguların ve gözlemlenen sorgu performansına ilişkin nedenlerin incelenmesi gerekir. Bu konu başlığında, olası tüm temel alınan kaynaklarda veritabanı iyileştirmesine yönelik en iyi uygulamalar kapsamlı olarak ele alınmamıştır ancak çoğu durumda geçerli olan standart veritabanı uygulamalarına değinilmiştir:

* Tamsayı sütunlarını temel alan ilişkiler genellikle, diğer veri türlerini içeren sütunları temel alan birleşimlere göre daha iyi performans gösterir
* Uygun dizinler oluşturulmalıdır. Bu da genellikle, destekleyen kaynaklarda (SQL Server gibi) sütun deposu dizinlerinin kullanılacağı anlamına gelir.
* Kaynaktaki gerekli tüm istatistikler güncelleştirilmelidir

### <a name="model-design-guidance"></a>Model Tasarım Kılavuzu
Model tanımlarken aşağıdakileri göz önünde bulundurun:

* **Sorgu Düzenleyicisi'nde karmaşık sorgular kullanmayın.** Sorgu Düzenleyicisi'nde tanımlanan sorgu tek bir SQL sorgusuna dönüştürülür. Bu sorgu, bu tabloya gönderilen tüm sorguların alt seçimlerine eklenir. Bu sorgu karmaşıksa gönderilen her bir sorguda performans sorunlarına neden olabilir. Bir adım kümesine ilişkin asıl SQL sorgusunu elde etmek için Sorgu Düzenleyicisi'nde son adımı seçip bağlam menüsünde *Yerel Sorguyu Görüntüle* seçeneğini belirleyebilirsiniz.
* **Ölçüleri basit tutun.** Ölçülerin en azından başlangıçta basit toplamalarla sınırlanması önerilir. Tatmin edici bir performans elde edildiğinde, her biri için performansa dikkat ederek daha kapsamlı ölçüler tanımlanabilir.
* **Hesaplanmış sütunlarda ilişki kullanmayın.** Bu durum daha çok birden fazla sütun birleştirme işleminin gerekli olduğu veritabanları için geçerlidir. Power BI şu anda FK/PK olarak birden fazla sütunu temel alan ilişkilere izin vermiyor. Sık uygulanan geçici çözüm, hesaplanmış bir sütun kullanılarak sütunların birleştirilmesi ve birleşimde bunun temel alınmasıdır. Bu geçici çözüm verilerin içeri aktarıldığı senaryoda makul olsa da **DirectQuery** durumunda bir ifade üzerinde birleştirmeye neden olur. Bu da genellikle dizin kullanılmasını önler ve düşük performansa neden olur. Tek geçici çözüm, temel alınan veritabanında birden çok sütunu tek bir sütun haline getirmektir.
* **Benzersiz tanımlayıcı sütunlarında ilişki kullanmayın.** Power BI, benzersiz tanımlayıcı veri türünü yerel olarak desteklemez. Bu nedenle, benzersiz tanımlayıcı türünde sütunlar arasında bir ilişki tanımlanması sonucunda, birleşim içeren (Tür Değiştirme işlemi de gerçekleşir) bir sorgu elde edilir. Bu da genellikle düşük performansa neden olur. Bu durum özellikle iyileştirilene kadar tek geçici çözüm, temel alınan veritabanında bulunan alternatif türdeki sütunların gerçekleştirilmesidir.
* **İlişkilerdeki *to* sütununu gizleyin.** İlişkilerdeki *to* sütunu, (genellikle *to* tablosundaki birincil anahtar) gizlenmelidir, böylece alan listesinde görünmez ve görsellerde kullanılamaz. Genellikle ilişkilerin temel aldığı sütunlar *sistem sütunlarıdır* (örneğin, bir veri ambarındaki vekil anahtarlar) ve bu sütunların gizlenmesi iyi bir uygulamadır. Sütunun anlamlı olması durumunda, görünür olan ve birincil anahtara eşit, basit bir ifade içeren bir hesaplanmış sütun ekleyin. Örnek:
  
      ProductKey_PK   (Destination of a relationship, hidden)
      ProductKey (= [ProductKey_PK],   visible)
      ProductName
      ...
  
  Bunu yapmanın nedeni, bir görselin birincil anahtar sütunu içermesi durumunda gerçekleşebilecek bir performans sorununu önlemektir.
* **Tüm hesaplanmış sütun ve veri türü değişikliklerini inceleyin.** Bu özelliklerin kullanılması her zaman zararlı değildir. Temel alınan kaynağa, sütunlara yönelik basit başvurular yerine ifadeler içeren sorguların gönderilmesine neden olur. Bu da dizinlerin kullanılamamasına neden olabilir.  
* **İlişkilerde iki yönlü çapraz filtreleme (önizleme) kullanmayın.**
* ***Bilgi tutarlılığı varsay* ayarını deneyin.** İlişkilerdeki *Bilgi Tutarlılığı Varsay* ayarı, sorguların OUTER JOIN yerine INNER JOIN deyimleri kullanmasını sağlar. Bu genellikle sorgu performansını iyileştirse de veri kaynağının ayrıntılarına bağlıdır.
* **Sorgu Düzenleyicisi'nde göreli veri filtreleme kullanmayın.** Sorgu Düzenleyicisi'nde göreli veri filtreleme tanımlanabilir. Örneğin, tarihi son 14 gün olan satırları filtreleme.
  
  ![](media/desktop-directquery-about/directquery-about_02.png)
  
  Ancak bu, sabit tarihli (sorgunun yazıldığı tarih gibi) bir filtreye dönüştürülür. Bu, yerel sorgu görüntülendiğinde görülebilir.
  
  ![](media/desktop-directquery-about/directquery-about_03.png)
  
  İstenen durum tam olarak bu değildir. Filtrenin, raporun yürütüldüğü tarih temel alınarak uygulanmasını sağlamak için filtreyi raporda bir Rapor Filtresi olarak uygulayın. Şu anda bu işlemi, kaç gün geçtiğini hesaplayan bir hesaplanmış sütun oluşturup (DAX DATE() işlevini kullanarak) hesaplanmış sütunu bir filtrede kullanarak gerçekleştirebilirsiniz.

### <a name="report-design-guidance"></a>Rapor Tasarım Kılavuzu
DirectQuery bağlantısı kullanarak bir rapor oluştururken aşağıdaki yönergelere uyun:

* **Sorgu Azaltma seçenekleri kullanımını göz önünde bulundurun:** Power BI, raporda daha az sorgu gönderme ve sonucunda elde edilen sorguların yürütülmesi çok uzun sürdüğü için kötü bir deneyime yol açacak belirli etkileşimleri devre dışı bırakma seçenekleri sağlar. **Power BI Desktop**’ta bu seçeneklere erişmek için **Dosya > Seçenekler ve ayarlar > Seçenekler**’e gidip **Sorgu azaltma**’yı seçin. 

   ![](media/desktop-directquery-about/directquery-about_03b.png)

    **Sorgu azaltma** seçeneğindeki kutu seçimlerinin belirlenmesi, raporunuzun tamamında çapraz vurgulamayı devre dışı bırakmanıza olanak tanır. Ayrıca, dilimleyiciler ve/veya filtre seçimleri için bir *Uygula* düğmesinin görünmesini sağlayabilir ve bunu kullanarak herhangi birini uygulamaksızın birçok dilimleyici ve filtre seçimi yapabilirsiniz. Bu sayede, dilimleyicideki **Uygula** düğmesi seçilene kadar hiçbir sorgu gönderilmez. Daha sonra seçimleriniz kullanılarak veriler filtrelenir.

    Bu seçenekler hem siz **Power BI Desktop**’ta raporunuzla etkileşim kurarken hem de kullanıcılar **Power BI hizmetinde** raporu kullanırken raporunuzda geçerli olur.

* **Öncelikle filtreleri uygulayın:** Bir görsel oluştururken ilk olarak her zaman, uygulanabilen filtreleri uygulayın. Örneğin, TotalSalesAmount ve ProductName öğelerini sürükleyip belirli bir yıla göre filtrelemek yerine, Yıl filtresini en başta uygulayın. Bunun nedeni, görsel oluşturma işleminin her adımında sorgu gönderilecek olmasıdır. İlk sorgu tamamlanmadan başka bir değişiklik yapılabilse de, temel alınan kaynakta yine de gereksiz yük oluşur. Filtreler erken uygulandığında, bu ara sorgular genellikle daha az yüke neden olur. Ayrıca, filtrelerin erken uygulanmaması, yukarıda belirtilen 1 milyon satır sınırına ulaşılmasına neden olabilir.
* **Sayfadaki görsel sayısını sınırlayın:** Bir sayfa açıldığında (veya sayfa düzeyi dilimleyici ya da filtre değiştiğinde) sayfadaki tüm görseller yenilenir. Ayrıca, paralel olarak gönderilen sorgu sayısına yönelik bir sınır da mevcuttur. Görsel sayısı arttıkça bazı görseller seri olarak yenilenir ve tüm sayfanın yenilenmesi için gereken süre artar. Bu nedenle, tek bir sayfadaki görsel sayısının sınırlanması ve bunun yerine sade içeriklere sahip daha fazla sayıda sayfa oluşturulması önerilir.
* **Görseller arasındaki etkileşimi devre dışı bırakma seçeneğini göz önünde bulundurun:** Varsayılan olarak bir rapor sayfasındaki görselleştirmeler, sayfadaki diğer görselleştirmeleri çapraz filtrelemek ve çapraz vurgulamak için kullanılabilir. Örneğin, pasta grafiğinde "1999" seçildiğinde, sütun grafiği "1999" değerine ilişkin satış kategorisini göstermek üzere vurgulanır.                                                                  
  
  ![](media/desktop-directquery-about/directquery-about_04.png)
  
  DirectQuery'de bu tür çapraz filtreleme ve çapraz vurgulama işlemleri için, temel alınan kaynağa sorgu gönderilmesi gerekir. Bu nedenle, kullanıcıların seçimlerine yanıt verilmesi normalden uzun sürerse etkileşim devre dışı bırakılmalıdır. Ancak, bu etkileşim raporun tamamı için (yukarıda *sorgu azaltma seçenekleri* için açıklandığı gibi) veya [bu makalede](service-reports-visual-interactions.md) açıklandığı gibi tek tek olay temelinde kapatılabilir.

Yukarıdaki öneri listesine ek olarak, aşağıdaki raporlama özelliklerinin her birinin performans sorunlarına neden olabileceğini unutmayın:

* **Ölçü filtreleri:** Ölçü içeren görsellerdeki (veya sütunların toplamları) ölçülerde filtre bulunabilir. Örneğin, aşağıdaki görselde Kategoriye göre SalesAmount değeri gösterilmektedir ancak yalnızca 20 milyondan yüksek satışa sahip Kategoriler dahil edilmiştir.
  
  ![](media/desktop-directquery-about/directquery-about_05.png)
  
  Bunun sonucunda, temel alınan kaynağa iki sorgu gönderilir:
  
  * İlk sorgu, koşulu karşılayan (Satış > 20 milyon) Kategorileri alır
  * İkinci sorgu, WHERE yan tümcesinde koşulu karşılayan Kategoriler de dahil olmak üzere, görsel için gereken verileri alır.  
  
  Bu örnekte olduğu gibi, yüzlerce veya binlerce kategori olduğunda genellikle düzgün bir performans sergilenir. Kategori sayısı çok daha fazla olduğunda performans düşebilir ve daha önce bahsedilen bir milyon satır sınırı nedeniyle, koşulu karşılayan kategoriler bir milyondan fazlaysa sorgu başarısız olur.
* **Üst N filtreleri:** Bir ölçüye göre sıralanan en Üstteki (veya Alttaki) N değeri filtrelemek için (örneğin, yukarıdaki görselde yalnızca en Üst sırada yer alan 10 kategorinin görüntülenmesi) gelişmiş filtreler tanımlanabilir. Bunun sonucunda da temel alınan kaynağa iki sorgu gönderilir. Ancak, ilk sorgu temel alınan kaynaktan tüm kategorileri döndürür ve döndürülen sonuçlara dayalı olarak Üst N belirlenir. Söz konusu sütunun kardinalitesine bağlı olarak performans sorunları oluşabilir veya 1 milyon satır sınırı nedeniyle sorgu başarısız olabilir.
* **Ortanca:** Genellikle tüm toplamalar (Toplam, Ayrı Say ve diğerleri) temel alınan kaynağa gönderilir. Ancak, bu toplama işlemi, temel alınan kaynak tarafından genel olarak desteklenmediğinden bu durum Ortanca için geçerli değildir. Böyle durumlarda ayrıntı verileri, temel alınan kaynaktan alınır ve döndürülen sonuçlardan Ortanca hesaplanır. Bu, ortancanın az sayıda sonuç üzerinden hesaplandığında durumlarda makul bir işlemdir ancak kardinalite yüksek olduğunda performans sorunları oluşur veya 1 milyon satır sınırı nedeniyle sorgu başarısız olur.  Örneğin, Ortanca Ülke Nüfusu makul olurken Ortanca Satış Fiyatı olmayabilir.
* **Gelişmiş metin filtreleri ("şunu içerir" ve benzeri):** Bir metin sütununu filtrelerken, gelişmiş filtreleme özelliği sayesinde "şunu içerir" ve "ile başlar" gibi filtreler sağlanır. Bu filtreler, bazı veri kaynakları için performansın düşmesine neden olabilir. Özellikle, gerçekten tam bir eşleşmenin ("şudur" veya "şu değildir") gerekli olduğu durumlarda varsayılan "şunu içerir" filtresi kullanılmamalıdır. Sonuçlar aynı olsa da asıl verilere bağlı olarak, dizin kullanımı nedeniyle performans büyük ölçüde farklı olabilir.
* **Dilimleyicilerde çoklu seçim:** Dilimleyiciler, varsayılan olarak yalnızca tek bir seçim yapılmasına olanak sağlar. Kullanıcı, dilimleyicide bir dizi öğe (örneğin, ilgilendiği on ürünü) seçerken her yeni seçimde arka uç kaynağa sorgular gönderileceğinden filtrelerde çoklu seçime izin verilmesi bazı performans sorunlarına neden olabilir. Kullanıcı, sorgu tamamlanmadan önce bir sonraki öğeyi seçebilse de bu durum temel alınan kaynakta ek yüke neden olur.

* **Görsellerdeki toplamları kapatmayı göz önünde bulundurun:** Varsayılan olarak, tablo ve matrislerde toplamlar ve alt toplamlar görüntülenir. Çoğu durumda, bu toplam değerlerinin alınması için temel kaynağa ayrı sorgular gönderilmelidir. Bu, *DistinctCount* toplaması kullanılan her durumda veya SAP BW ve SAP HANA üzerinden DirectQuery kullanılan tüm durumlarda geçerlidir. Bu tür toplamlar gerekli değilse kapatılmalıdır (**Biçimlendir** bölmesi kullanılarak). 

### <a name="diagnosing-performance-issues"></a>Performans sorunlarını tanılama
Bu bölümde performans sorunlarının nasıl tanılanacağı ve raporların iyileştirilebilmesi için ayrıntılı bilginin nasıl alınacağı açıklanmaktadır.

Performans sorunlarının tanılanmasına, **Power BI hizmeti** yerine **Power BI Desktop**'ta başlanması önemle önerilir. Performans sorunları genellikle, temel alınan kaynağın performans düzeyine bağlıdır ve bunlar, **Power BI Desktop**'ın çok daha yalıtılmış ortamında daha kolay şekilde belirlenir ve tanılanır. Bu ortamda öncelikle belirli bileşenler (Power BI ağ geçidi gibi) ortadan kaldırılır. Araştırma sırasında yalnızca, performans sorunlarının Power BI Desktop'tan kaynaklanmadığı belirlenirse Power BI hizmetindeki raporun ayrıntılarına odaklanılmalıdır.

Benzer şekilde, sayfada bulunan birçok görsel yerine öncelikle tek bir görseldeki sorunların giderilmesi önerilir.

Bu adımların (bu bölümün önceki paragraflarında bulunanlar) uygulandığını ve **Power BI Desktop**'taki bir sayfada yine de yavaş olan tek bir görselimiz olduğunu varsayalım. Power BI Desktop tarafından, temel alınan kaynağa gönderilen sorguların belirlenmesi için, bu kaynaktan yayınlanan izleme/tanılama bilgileri görüntülenebilir. Bu izleme dosyaları, sorgunun nasıl yürütüldüğüne ve nasıl iyileştirilebileceğine yönelik ayrıntılar hakkında faydalı bilgiler içerebilir.

Ayrıca, sonraki bölümlerde açıklandığı üzere, kaynaktan bu tür izleme dosyalarının gelmemesi durumunda bile Power BI tarafından gönderilen sorguları, yürütme süreleriyle birlikte görüntüleyebilirsiniz.

#### <a name="determining-the-queries-sent-by-power-bi-desktop"></a>Power BI Desktop tarafından gönderilen sorguları belirleme
Varsayılan olarak, **Power BI Desktop** belirli bir oturum sırasındaki olayları FlightRecorderCurrent.trc adlı bir izleme dosyasına kaydeder.

Bazı **DirectQuery** kaynakları için bu günlük, temel alınan veri kaynağına gönderilen tüm sorguları içerir. (Diğer DirectQuery kaynakları daha sonra eklenecektir.) Günlüğe sorgu gönderen kaynaklar aşağıda belirtilmiştir:

* SQL Server
* Azure SQL Veritabanı
* Azure SQL Veri Ambarı
* Oracle
* Teradata
* SAP HANA

Geçerli kullanıcı için izleme dosyası **AppData** klasöründe bulunur:

    \<User>\AppData\Local\Microsoft\Power BI Desktop\AnalysisServicesWorkspaces

Bu klasöre kolayca ulaşmak için: **Power BI Desktop**'ta **Dosya > Seçenekler ve ayalar > Seçenekler**'i ve ardından **Tanılama**'yı seçin. Aşağıdaki iletişim kutusu penceresi görünür:

![](media/desktop-directquery-about/directquery-about_06.png)

*Tanılama Seçenekleri* bölümündeki **İzleme klasörünü aç** bağlantısını seçtiğinizde aşağıdaki klasör açılır:

    \<User>\AppData\Local\Microsoft\Power BI Desktop\Traces

Bu klasörün üst klasörüne gidildiğinde *AnalysisServicesWorkspaces* klasörünü içeren klasör görüntülenir. Bu klasör, açık olan her bir **Power BI Desktop** örneği için bir çalışma alanı alt klasörü içerir. Bu alt klasörler, *AnalysisServicesWorkspace2058279583* örneğinde olduğu gibi bir tamsayı sonekiyle adlandırılır.

Bu klasörün içinde, geçerli Power BI oturumuna ilişkin FlightRecorderCurrent.trc izleme dosyasını içeren *\Data* alt klasörü bulunur. İlişkili Power BI Desktop oturumu sona erdiğinde ilgili çalışma alanı klasörü silinir.

İzleme dosyaları, **SQL Server Management Studio** ile birlikte ücretsiz indirilebilen **SQL Server Profiler** aracı kullanılarak okunabilir. [Bu sayfadan](https://msdn.microsoft.com/library/mt238290.aspx) edinebilirsiniz.

**SQL Server Management Studio**'yu indirip yükledikten sonra, **SQL Server Profiler**'ı çalıştırın.

![](media/desktop-directquery-about/directquery-about_07.png)

İzleme dosyasını açmak için şu adımları uygulayın:

1. **SQL Server Profiler**'da **Dosya > Aç > İzleme dosyası**'nı seçin
2. Şu anda açık olan Power BI oturumu için izleme dosyasının yolunu girin. Örnek:
   
         C:\Users\<user>\AppData\Local\Microsoft\Power BI Desktop\AnalysisServicesWorkspaces\AnalysisServicesWorkspace2058279583\Data
3. FlightRecorderCurrent.trc dosyasını açın

Geçerli oturumun tüm etkinlikleri görüntülenir. Aşağıda olay gruplarını vurgulayan, açıklama eklenmiş bir örnek verilmiştir. Her bir grup şunları içerir:

* Kullanıcı arabirimi tarafından oluşturulan (örneğin, bir görselden veya kullanıcı arabirimi filtresinde bir değerler listesi doldurarak) DAX sorgusunun başını ve sonunu temsil eden bir *Sorgu Başlangıç* ve *Sorgu Bitiş* olayı
* DAX sorgusunu değerlendirme işleminin parçası olarak, temel alınan veri kaynağına gönderilen bir sorguyu temsil eden bir veya daha çok *DirectQuery Başlangıç* ve *DirectQuery Bitiş* olay çifti.

Birden fazla DAX sorgusunun paralel olarak yürütülebileceğini unutmayın. Böylece, farklı gruplardan olaylar araya eklenebilir. ActivityID değeri, hangi olayların aynı gruba dahil olduğunu belirlemek için kullanılabilir.

![](media/desktop-directquery-about/directquery-about_08.png)

İlgili diğer sütunlar şunlardır:

* **TextData:** Olayın metinsel ayrıntıları. "Sorgu Başlangıç/Bitiş" olayları için DAX sorgusudur. "DirectQuery Başlangıç/Bitiş" olayları için, temel alınan kaynağa gönderilen SQL sorgusudur. Seçili olan olay için TextData, en alttaki bölümde de gösterilir.
* **EndTime:** Olayın tamamlandığı zaman.
* **Duration:** DAX veya SQL sorgusunu yürütmek için gereken süre (milisaniye cinsinden).
* **Error:** Hata oluşup oluşmadığını belirtir. (Hata durumunda olay kırmızı renkte gösterilir.)

Yukarıdaki görüntüde, daha çok ilgi çeken sütunların kolayca görülebilmesi için az ilgi çeken sütunların daraltıldığına dikkat edin.

Olası bir performans sorununun tanılanmasına yardımcı olmak üzere izleme dosyası yakalama işleminde önerilen yaklaşım şu şekildedir:

* Tek bir **Power BI Desktop** oturumu açın (birden çok çalışma alanı klasörünün oluşturacağı karışıklığı önlemek için)
* **Power BI Desktop**'ta ilgili eylemleri gerçekleştirin. İlgili olayların izleme dosyasına aktarıldığından emin olmak için birkaç eylem daha gerçekleştirin.
* Önceki bir bölümde açıklanan şekilde, **SQL Server Profiler**'ı açın ve izleme dosyasını inceleyin. **Power BI Desktop**'ı kapattığınızda izleme dosyasının silineceğini unutmayın. Ayrıca, Power BI Desktop'ta yapılan ek eylemler hemen görünmez. Yeni olayların görünmesi için izleme dosyasının kapatılıp yeniden açılması gerekir.
* İzleme dosyasının kolayca yorumlanabilmesi için tek tek oturumları makul şekilde kısa (yüzlerce değil on saniyelik eylemler) tutun (izleme dosyasının boyutunda sınır olduğundan, çok uzun oturumlarda erken olayların bırakılma riski olur).

#### <a name="understanding-the-form-of-query-sent-by-power-bi-desktop"></a>Power BI Desktop tarafından gönderilen sorgu yapısını anlama
**Power BI Desktop** tarafından oluşturulan ve gönderilen sorguların genel biçimi, başvurulan tabloların her biri için alt seçimler kullanır ve bunlarda alt seçim, **Sorgu Düzenleyicisi**'nde tanımlanan sorgu ile tanımlanır. Örneğin, aşağıdaki TPC-DS tablolarının SQL Server'da olduğunu varsayalım:

![](media/desktop-directquery-about/directquery-about_09.png)

Şu sorguyu inceleyin:

![](media/desktop-directquery-about/directquery-about_10.png)

Bu sorgu şu görseli oluşturur:

![](media/desktop-directquery-about/directquery-about_11.png)

Bu görsel yenilendiğinde, sonraki paragrafın altında gösterilen SQL sorgusu oluşturulur. Gördüğünüz üzere Web Sales, Item ve Date_dim için üç alt seçim bulunur ve görsel tarafından yalnızca dört sütuna başvurulmasına rağmen bunların her biri, ilgili tablodaki tüm sütunları döndürür. Alt seçimlerdeki (gölgeli) bu sorgular, tam olarak, **Sorgu Düzenleyicisi**'nde tanımlanan sorguların sonucudur. Alt seçimlerin bu şekilde kullanılmasının, şu ana kadar DirectQuery için desteklenen veri kaynakları için performans üzerinde herhangi etkisi ile karşılaşılmadı. SQL Server gibi veri kaynakları, diğer sütunlara yönelik başvuruları iyileştirir.

Power BI'ın bu deseni kullanma nedenlerinden biri, kullanılan SQL sorgusunun doğrudan çözümleyici tarafından sağlanabilmesi ve yeniden yazma girişimi olmaksızın "sağlandığı gibi" kullanılmasıdır.

![](media/desktop-directquery-about/directquery-about_12.png)

## <a name="next-steps"></a>Sonraki adımlar
Bu makalede, **DirectQuery**'nin tüm veri kaynaklarında sık kullanılan özellikleri açıklanmaktadır. Farklı kaynaklar için belirli ayrıntılar söz konusudur. Belirli kaynakların ele alındığı şu konu başlıklarına göz atın:

* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)

**DirectQuery** hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [DirectQuery tarafından desteklenen Veri Kaynakları](desktop-directquery-data-sources.md)

