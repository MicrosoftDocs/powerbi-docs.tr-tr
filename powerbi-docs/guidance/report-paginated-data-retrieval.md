---
title: Sayfalandırılmış raporlar için veri alma kılavuzu
description: Power BI sayfalandırılmış raporları için veri kaynağı ve veri kümesi oluşturma kılavuzu.
author: peter-myers
ms.author: v-pemyer
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 02/16/2020
ms.openlocfilehash: 5869402a1f5147dbd4cea18b426452e115a97911
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96419050"
---
# <a name="data-retrieval-guidance-for-paginated-reports"></a>Sayfalandırılmış raporlar için veri alma kılavuzu

Bu makale Power BI [sayfalandırılmış raporları](../paginated-reports/paginated-reports-report-builder-power-bi.md) tasarlayan rapor yazarlarına yöneliktir. Etkili ve verimli veri alma süreçleri tasarlamanıza yardımcı olacak öneriler sağlar.

## <a name="data-source-types"></a>Veri kaynağı türleri

Sayfalandırılmış raporlar yerel olarak hem ilişkisel hem de analitik veri kaynaklarını destekler. Bu kaynaklar da bulut tabanlı veya şirket içi olmak üzere farklı kategorilere ayrılır. Power BI'ın şirket içinde veya sanal makinede barındırılan şirket içi kaynaklara bağlanabilmesi için bir veri ağ geçidine ihtiyaç vardır. Bulut tabanlı, Power BI'ın internet bağlantısı üzerinden doğrudan bağlanabileceği anlamına gelir.

Veri kaynağı türünü seçme imkanınız varsa (yeni bir proje oluşturuyorsanız) bulut tabanlı veri kaynaklarını kullanmanız önerilir. Özellikle veri kaynaklarının Power BI kiracınızla aynı bölgede bulunması durumunda sayfalandırılmış raporlar bağlantılarında daha düşük ağ gecikme süresi yaşanır. Ayrıca bu kaynaklarla Çoklu Oturum Açma (SSO) ile de bağlantı kurulabilir. Bu sayede raporun kullanıcı kimliği veri akışına aktarılabilir ve kullanıcıya göre satır düzeyi izinler uygulanabilir. SSO şu anda şirket içi veri kaynakları için desteklenmemektedir (bu nedenle SQL Server Analysis Services, kullanıcıya göre satır düzeyi izinler uygulayamaz).

> [!NOTE]
> Şu anda şirket içi veritabanlarına SSO kullanarak bağlanmak mümkün değildir ancak satır düzeyi izinleri uygulayabilirsiniz. Bunun için yerleşik **UserID** bilgisini veri kümesi sorgu parametresine geçirmeniz gerekir. Veri kaynağı, Kullanıcı Asıl Adı (UPN) değerlerini sorgu sonuçlarını doğru olarak filtreleyebilecek şekilde depolamalıdır.
>
> Örneğin her satırda bir satış temsilcisinin kayıtlı olduğu bir **Satış Temsilcisi** tablosuna sahip olduğunuzu düşünün.  Tabloda UPN değerlerinin satış temsilcisinin satış bölgesinin yer aldığı sütunlar mevcut. Sorgu zamanında tablo, rapor kullanıcısının UPN değerine göre filtrelenir ve ayrıca iç birleşim kullanılarak satış verileriyle ilişkilendirilir. Sorgu bu sayede satış verileri satırlarını rapor kullanıcısının satış bölgesine göre etkili bir şekilde filtreler.

### <a name="relational-data-sources"></a>İlişkisel veri kaynakları

İlişkisel veri kaynakları genellikle satış faturaları gibi operasyonel raporlar için uygundur. Bu veri kaynakları ayrıca çok büyük veri kümelerini (10.000 satırdan fazla) alması gereken raporlar için de kullanılabilir. İlişkisel veri kaynakları ayrıca rapor veri kümeleri tarafından yürütülebilecek saklı yordamlar da tanımlayabilir. Saklı yordamlar birçok avantaj sunar:

- Parametre ekleme
- Programlama mantığının kapsüllenerek daha karmaşık veri hazırlama özelliklerinin kullanılmasının sağlanması (geçici tablolar, imleçler veya skaler kullanıcı tanımlı işlevler gibi)
- Geliştirilmiş bakım olanakları sayesinde saklı yordam mantığının kolayca güncelleştirilebilmesi. Bazı durumlarda sayfalandırılmış raporları değiştirme ve yeniden yayımlama ihtiyacı olmadan gerçekleştirilebilir (sütun adlarının ve veri türlerinin aynı kalması koşuluyla).
- Yürütme planları yeniden kullanım için önbelleğe alındığından daha iyi performans
- Saklı yordamların farklı raporlarda yeniden kullanılabilmesi

Power BI Report Builder'da ilişkisel sorgu tasarımcısını kullanarak bir sorgu ifadesini grafiksel olarak oluşturabilirsiniz (yalnızca Microsoft veri kaynakları için).

### <a name="analytic-data-sources"></a>Analitik veri kaynakları

Analitik veri kaynakları hem operasyonel hem de analitik raporlar için uygundur ve çok büyük veri hacimlerinde bile hızlı özetlenmiş sorgu sonuçları sunabilir. Model ölçüleri ve KPI'ler, karmaşık iş kurallarını kapsülleyerek verileri özetleyebilir. Ancak bu veri kaynakları çok büyük veri kümelerini (10.000 satırdan fazla) alması gereken raporlar için uygun değildir.

Power BI Report Builder'da iki sorgu tasarımcısı vardır: Analysis Services DAX sorgusu tasarımcısı ve Analysis Services MDX sorgusu tasarımcısı. Bu tasarımcılar Power BI veri kümesi veri kaynaklarıyla veya herhangi bir SQL Server Analysis Services veya Azure Analysis Services modeliyle (tablosal veya çok boyutlu) kullanılabilir.

Sorgu ihtiyaçlarınızın tamamını karşılıyorsa DAX sorgusu tasarımcısını kullanmanız önerilir. Model, ihtiyacınız olan ölçüleri tanımlamıyorsa sorgu moduna geçmeniz gerekir. Bu modda ifade ekleyerek sorgu deyimini özelleştirebilirsiniz (özetleme elde etmek için).

MDX sorgusu tasarımcısı için modelinizin ölçü içermesi gerekir. Tasarımcı, DAX sorgusu tasarımcısı tarafından desteklenmeyen iki özelliğe sahiptir. Özellikle şunları yapmanızı sağlar:

- Sorgu düzeyinde hesaplanan üye tanımlama (MDX ile).
- Veri bölgelerini, ayrıntılı olmayan gruplarda [sunucu toplamaları](/sql/reporting-services/report-design/report-builder-functions-aggregate-function) isteğinde bulunacak şekilde yapılandırma. Raporunuzun yarı eklemeli veya eklemeli olmayan ölçülerin (akıllı zaman gösterimi hesaplamaları veya ayrı sayımlar gibi) özetlerini sunması gerekiyorsa, düşük düzey ayrıntıya sahip satırları almak ve özetleme hesaplamalarını rapora yaptırmak yerine sunucu toplamalarını kullanmak daha verimli olacaktır.

## <a name="query-result-size"></a>Sorgu sonucu boyutu

Genellikle yalnızca raporunuz için ihtiyaç duyulan verileri almanız önerilir. Bu nedenle raporun ihtiyaç duymadığı sütunları veya raporları almayın.

Satırları sınırlamak için her zaman en kısıtlayıcı filtreleri uygulamanız ve toplama sorguları tanımlamanız gerekir. Toplama sorguları, kaynaktaki verileri gruplayıp özetler ve ayrıntı düzeyi düşük sonuçlar alır. Örneğin, raporunuzun satış temsilcileri tarafından yapılan satışların özetini sunması gerektiğini düşünün. Tüm satış siparişi satırlarını almak yerine satış temsilcisine göre gruplar oluşturan ve her bir grubun satışlarını özetleyen bir veri kümesi sorgusu oluşturabilirsiniz.

## <a name="expression-based-fields"></a>İfade tabanlı alanlar

Rapor veri kümesini ifadeleri temel alan alanlarla genişletebilirsiniz. Örneğin veri kümenizde müşterinin adı ve soyadı bulunuyorsa bu iki alanı birleştirerek müşterinin tam adını oluşturan bir alan eklemek isteyebilirsiniz. Bu hesaplamayı gerçekleştirmek için iki seçeneğiniz vardır. Seçenekleriniz şunlardır:

- Bir ifadeyi temel alan veri kümesi alanı olan bir _hesaplanmış alan_ oluşturabilirsiniz.
- Bir ifadeyi doğrudan veri kümesi sorgusuna ekleyebilir (veri kaynağınızın yerel dilini kullanarak) ve normal bir veri kümesi alanı elde edebilirsiniz.

Mümkün olduğunda ikinci seçeneği kullanmanız önerilir. İfadeleri doğrudan veri kümesi sorgunuza eklemenin sağladığı iki avantaj vardır:

- Veri kaynağınız, ifadeyi Power BI'dan daha verimli bir şekilde değerlendirmek üzere iyileştirilmiş olabilir (özellikle ilişkisel veritabanlarında).
- Power BI'ın raporu oluşturmadan önce hesaplanan alanları gerçekleştirmesine gerek olmadığından rapor performansı artar. Veri kümelerinin çok sayıda satır alması durumunda hesaplanan alanlar rapor oluşturma süresini önemli ölçüde uzatabilir.

## <a name="field-names"></a>Alan adları

Bir veri kümesi oluşturduğunuzda, alanları otomatik olarak sorgu sütunlarına göre adlandırılır. Bu adlar, kolay akılda kalan veya sezgisel adlar olmayabilir. Ayrıca kaynak sorgu sütunu adlarında Rapor Tanım Dili (RDL) nesne tanımlayıcılarında kullanılması yasaklanmış olan karakterler (boşluk ve simgeler gibi) bulunabilir. Bu durumda yasaklanmış karakterler, alt çizgi (_) karakteriyle değiştirilir.

Öncelikle tüm alan adlarının kolay anlaşılır, kısa ancak anlamlı olduğundan emin olmanız önerilir. Adları değiştirmek isterseniz bu işlemi rapor düzenini başlatmadan _önce_ gerçekleştirmeniz önerilir. Bunun nedeni, yeniden adlandırılan alanların bu değişiklikleri rapor düzeninizde kullanılan ifadelere yansıtmamasıdır. Rapor düzenini başlattıktan sonra alanları yeniden adlandırmaya karar verirseniz bozulan tüm ifadeleri bulmanız ve güncelleştirmeniz gerekir.

## <a name="filter-vs-parameter"></a>Filtre ile parametre karşılaştırması

Sayfalandırılmış rapor tasarımlarınızda muhtemelen rapor parametreleri bulunacaktır. Rapor parametreleri genellikle rapor kullanıcınızın raporu filtrelemesine imkan tanımak için kullanılır. Sayfalandırılmış rapor yazarı olarak raporu iki şekilde filtreleyebilirsiniz. Bir rapor parametresini şu bileşenlerle eşleyebilirsiniz:

- Veri kümesi _filtresi_: Bu durumda rapordaki parametre değerleri, veri kümesi tarafından alınmış olan verileri filtrelemek için kullanılır.
- Veri kümesi _parametresi_: Bu durumda rapordaki parametre değerleri, veri kaynağına gönderilen yerel sorguya eklenir.

> [!NOTE]
> Tüm rapor veri kümeleri, _son kullanımlarının sonrasında_ 10 dakikaya kadar _oturum tabanlı_ olarak önbelleğe alınır. Veri kümesi; yeni parametre değerleri göndermek (filtreleme), raporu farklı bir biçimde oluşturmak veya görünürlüğü değiştirmek ya da sıralama yapmak gibi rapor tasarımıyla etkileşimde bulunmak için yeniden kullanılabilir.

Raporu yıla göre filtreleyen tek bir rapor parametresine sahip olan bir satış raporunu düşünün. Bu durumda veri kümesi, _tüm yıllara_ ait satışları alır. Bunun nedeni, rapor parametresinin veri kümesi filtreleriyle eşlenmesidir. Rapor, veri kümesi verilerinin bir alt kümesi olan istenen yıla ait verileri görüntüler. Rapor kullanıcısı, rapor parametresini farklı bir yıl olarak değiştirip raporu görüntülediğinde Power BI'ın kaynaktan veri alması gerekmez. Bunun yerine önbelleğe alınmış olan veri kümesine farklı bir filtre uygular. Önbelleğe alınan veri kümelerinde filtreleme işlemi çok hızlı yapılabilir.

Şimdi farklı bir rapor tasarımını ele alalım. Bu kez rapor tasarımı, satış yılı rapor parametresini bir veri kümesi parametresine eşlemiştir. Bu örnekte Power BI, yıl değerini yerel sorguya ekler ve veri kümesi yalnızca ilgili yıla ait verileri alır. Rapor kullanıcısı, satış yılı rapor parametresini değiştirdiğinde ve raporu görüntülediğinde, veri kümesi ilgili yılın sonuçlarını içeren yeni bir sorgu sonucu alır.

İki tasarım yaklaşımı da rapor verilerinizi filtrelemenizi sağlar ve ikisi de rapor tasarımlarınızda kullanışlı olabilir. Ancak iyileştirilmiş bir tasarım elde etmek için beklenen veri hacmi, verilerin geçiciliği ve rapor kullanıcılarınızın tahmin edilen davranışları dikkate alınmalıdır.

Veri kümesi satırlarının farklı alt kümelerinin çok kez yeniden kullanılmasını beklediğiniz durumlarda _veri kümesi filtreleme_ seçeneğini kullanmanız önerilir (yeni veri alınmayacağı için oluşturma süresinden tasarruf etmiş olursunuz). Bu senaryoda büyük bir veri kümesini alma maliyetinin yeniden kullanılma sayısı nedeniyle göze alınabileceğini kabul etmiş olursunuz. Bu nedenle bu senaryo, oluşturması zaman alan sorgular için faydalıdır. Ancak büyük veri kümelerini kullanıcılara göre önbelleğe almak performansı ve kapasite aktarım hızını olumsuz yönde etkileyebileceğinden dikkatli hareket etmeniz gerekir.

Veri kümesi satırlarının farklı alt kümeleri için istekte bulunulmayacağını düşünüyorsanız veya filtrelenecek veri kümesi satırı sayısı çok büyük (ve önbelleğe almak için verimsiz) ise _veri kümesi parametre ekleme_ seçeneğini kullanmanız önerilir. Veri deponuz geçici ise bu tasarım yaklaşımı oldukça kullanışlı olacaktır. Bu durumda her bir rapor parametresi değeri değiştirildiğinde güncel veriler alınacaktır.

## <a name="non-native-data-sources"></a>Yerel olmayan veri kaynakları

[Sayfalandırılmış raporlar tarafından yerel olarak desteklenmeyen](../paginated-reports/paginated-reports-data-sources.md) veri kaynaklarını temel alan sayfalandırılmış raporlar geliştirmeniz gerekiyorsa öncelikle bir Power BI Desktop veri modeli geliştirebilirsiniz. Bu sayede 100'den fazla [Power BI veri kaynağına](../connect-data/power-bi-data-sources.md) bağlanabilirsiniz. Power BI hizmeti yayımlandıktan sonra Power BI veri kümesine bağlanan bir sayfalandırılmış rapor geliştirebilirsiniz.

## <a name="data-integration"></a>Veri tümleştirmesi

Birden çok veri kaynağında bulunan verileri birleştirmeniz gerekiyorsa iki seçeneğiniz vardır:

- **Rapor veri kümelerini birleştirme**: Veri kaynakları [sayfalandırılmış raporlar tarafından yerel olarak destekleniyorsa](../paginated-reports/paginated-reports-data-sources.md), [Lookup](/sql/reporting-services/report-design/report-builder-functions-lookup-function) veya [LookupSet](/sql/reporting-services/report-design/report-builder-functions-lookupset-function) Report Builder işlevlerini kullanan hesaplanan alanlar oluşturabilirsiniz.
- **Power BI Desktop modeli geliştirme**: Çoğu durumda Power BI Desktop'ta bir veri modeli geliştirmeniz daha verimli olacaktır. Power Query ile [desteklenen veri kaynaklarını](../connect-data/power-bi-data-sources.md) temel alan sorguları birleştirebilirsiniz. Power BI hizmeti yayımlandıktan sonra Power BI veri kümesine bağlanan bir sayfalandırılmış rapor geliştirebilirsiniz.

## <a name="sql-server-complex-data-types"></a>SQL Server karmaşık veri türleri

SQL Server bir şirket içi veri kaynağı olduğundan, Power BI bağlantısı ağ geçidi üzerinden kurulmalıdır. Ancak ağ geçidi, karmaşık veri türlerine ait verilerin alınmasını desteklemez. Karmaşık veri türleri, GEOMETRY ve GEOGRAPHY [uzamsal veri türleri](/sql/relational-databases/spatial/spatial-data-sql-server) ve [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) gibi yerleşik türlerdir. Bunların arasında ayrıca Microsoft .NET Framework ortak dil çalışma zamanı (CLR) içindeki bir derlemenin sınıfı aracılığıyla uygulanmış olan kullanıcı tanımlı türler de bulunabilir.

Uzamsal verilerin ve analizlerin harita görselleştirmesinde çizilmesi için SQL Server uzamsal verilerine ihtiyaç vardır. Bu nedenle veri kaynağı olarak SQL Server'ı kullandığınızda harita görselleştirmesiyle çalışmanız mümkün değildir. Veri kaynağınız Azure SQL Veritabanı olduğunda çalışacaktır çünkü bu durumda Power BI bağlantı kurmak için ağ geçidi kullanmaz.

## <a name="data-related-images"></a>Verilerle ilgili görüntüler

Rapor düzeninize logo veya resim eklemek için görüntüler kullanabilirsiniz. Görüntüler, rapor veri kümesi tarafından alınan satırlarla ilgili olduğunda iki seçeneğiniz vardır:

- Görüntü verileri de veri kaynağınızdan alınabilir (tabloda depolanıyorsa).
- Görüntülerin web sunucunuzda depolanması durumunda dinamik bir ifade kullanarak görüntü URL yolunu oluşturabilirsiniz.

Daha fazla bilgi ve öneriler için bkz. [Sayfalandırılmış raporlar için görüntü kılavuzu](report-paginated-image.md).

## <a name="redundant-data-retrieval"></a>Gereksiz veri alma

Raporunuz, gereksiz veriler alabilir. Bu durum, veri kümesi sorgusundaki alanları sildiğinizde veya raporda kullanılmayan veri kümeleri bulunduğunda ortaya çıkabilir. Bu gibi durumlar veri kaynaklarınızda, ağınızda ve Power BI kapasitesi kaynaklarında gereksiz yük oluşturacağından kaçınmaya çalışın.

### <a name="deleted-query-fields"></a>Silinen sorgu alanları

**Veri Kümesi Özellikleri** penceresinin **Alanlar** sayfasında veri kümesi _sorgu alanlarını_ silebilirsiniz (sorgu alanları, veri kümesi sorgusu tarafından alınan sütunlarla eşlenir). Ancak Report Builder, ilgili sütunları veri kümesi sorgusundan kaldırmaz.

Veri kümenizdeki sorgu alanlarını silmeniz gerekiyorsa ilgili sütunları veri kümesi sorgusundan kaldırmanız önerilir. Report Builder, gereksiz tüm sorgu alanlarını otomatik olarak kaldırır. Sorgu alanlarını silerseniz veri kümesi sorgu deyimini de değiştirerek sütunları kaldırdığınızdan emin olun.

### <a name="unused-datasets"></a>Kullanılmayan veri kümeleri

Bir rapor çalıştırıldığında, rapor nesnelerine bağlı olup olmadıklarına bakılmaksızın tüm veri kümeleri değerlendirilir. Bu nedenle raporu yayımlamadan önce test veya geliştirme amaçlı veri kümelerini kaldırdığınızdan emin olun.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI sayfalandırılmış raporları için desteklenen veri kaynakları](../paginated-reports/paginated-reports-data-sources.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
