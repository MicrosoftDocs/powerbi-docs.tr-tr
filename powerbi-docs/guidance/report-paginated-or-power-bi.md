---
title: Power BI’daki sayfalandırılmış raporları kullanma zamanı
description: Power BI sayfalandırılmış raporlarını kullanma zamanı hakkında kılavuz.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 01/04/2020
ms.author: v-pemyer
ms.openlocfilehash: 3838c0b487be7faace2e58dd706aa7d172841215
ms.sourcegitcommit: b59ec11a4a0a3d5be2e4d91548d637d31b3491f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78290510"
---
# <a name="when-to-use-paginated-reports-in-power-bi"></a>Power BI’daki sayfalandırılmış raporları kullanma zamanı

Bu makale Power BI için rapor tasarlayan rapor yazarlarına yöneliktir. [Power BI sayfalandırılmış raporlarını](../paginated-reports-report-builder-power-bi.md) hangi durumlarda tercih etmeniz gerektiğini anlamanıza yardımcı olacak öneriler sunmaktadır.

> [!NOTE]
> Power BI sayfalandırılmış raporların yayımlanması için Power BI Premium aboneliğine ihtiyaç vardır. Raporlar yalnızca [Sayfalandırılmış Raporlar iş yükünün etkinleştirilmiş olduğu](../service-admin-premium-workloads.md#paginated-reports) ayrılmış kapasite üzerindeki bir çalışma alanında işlenir.

Power BI sayfalandırılmış raporları **yazdırma** veya **PDF oluşturma** için iyileştirilmiştir. Bu raporlar ayrıca üst düzeyde biçimlendirilmiş mükemmel rapor düzenleri sunar. Bu nedenle sayfalandırılmış raporlar, satış faturaları gibi operasyonel raporlar için idealdir.

Diğer taraftan Power BI raporları, **araştırma ve etkileşim** için iyileştirilmiştir. Bu raporlar ayrıca verilerinizi geniş kapsamlı ve ultra modern görseller kullanarak sunmanızı sağlayabilir. Bu nedenle Power BI raporları, rapor kullanıcılarınızın verileri keşfedip ilişkileri ve düzenleri analiz raporları araştırabileceği analiz raporları için idealdir.

Aşağıdaki durumlarda Power BI sayfalandırılmış raporlarını kullanmanız önerilir:

- Raporun yazdırılması veya PDF belgesine dönüştürülmesi gerektiğini biliyorsanız.
- Veri kılavuzu düzenlerinin genişleme ve taşma imkanı varsa. Power BI raporundaki tablolar veya matrisler, tüm verileri görüntüleyecek şekilde dinamik olarak boyutlandırılamaz. Bunun için kaydırma çubukları görüntülenir. Ancak raporun yazdırılması durumunda görünmeyen verilere ulaşmak için kaydırma yapmak mümkün olmayacaktır.
- Power BI sayfalandırılmış özellikleri ve becerileri işinizi kolaylaştırır. Bu raporun ilerleyen bölümlerinde birçok benzer rapor senaryosuna yer verilmiştir.

## <a name="legacy-reports"></a>Eski raporlar

Elinizde SQL Server Reporting Services (SSRS) [Rapor Tanım Dili (RDL)](/sql/reporting-services/reports/report-definition-language-ssrs) raporları varsa bunları [Power BI raporları](../consumer/end-user-reports.md) olarak yeniden geliştirebilir veya sayfalandırılmış raporlar olarak Power BI'a geçirebilirsiniz. Daha fazla bilgi için bkz. [SQL Server Reporting Services raporlarını Power BI’a geçirme](migrate-ssrs-reports-to-power-bi.md).

Bir Power BI çalışma alanında yayımlanan sayfalandırılmış raporlar, Power BI raporlarıyla birlikte kullanılabilir. Bu raporlar [Power BI uygulamaları](../service-create-distribute-apps.md) kullanılarak kolayca dağıtılabilir.

SSRS raporlarını geçirmek yerine sıfırdan geliştirmeniz önerilir. Bu durum özellikle analitik deneyimler sunmaya yönelik raporlar için geçerlidir. Bu gibi durumlarda Power BI raporları genellikle daha iyi bir rapor kullanıcısı deneyimi sunacaktır.

## <a name="paginated-report-scenarios"></a>Sayfalandırılmış rapor senaryoları

Power BI sayfalandırılmış raporu geliştirmeyi tercih edebileceğiniz birçok cazip senaryo vardır. Bunların çoğu, Power BI raporları tarafından desteklenmeyen özellikler veya becerilerdir.

- **Yazdırma için hazır**: Sayfalandırılmış raporlar yazdırma veya PDF oluşturma için iyileştirilmiştir. Veri bölgeleri gerektiğinde genişletilerek birden fazla sayfaya kontrollü bir şekilde taşırılabilir. Rapor düzenlerinde kenar boşluklarını, sayfa üst bilgilerini ve alt bilgilerini ayarlayabilirsiniz.
- **İşleme biçimleri**: Power BI, sayfalandırılmış raporları farklı biçimlerde işleyebilir. Bu biçimler Microsoft Excel, Microsoft Word, Microsoft PowerPoint, PDF, CSV, XML ve MHTML biçimleridir. (MHTML biçimi, Power BI hizmeti tarafından raporları işlemek için kullanılır.) Rapor kullanıcılarınız, raporu istedikleri biçimde dışarı aktarabilir.
- **Hassas düzen**: Yüksek düzeyde biçimli, kusursuz düzenler tasarlayabilir, inç veya santimetre düzeyinde istediğiniz boyutu ve konumu yapılandırabilirsiniz.
- **Dinamik düzen**: Birçok rapor özelliğini VB.NET ifadelerini kullanacak şekilde ayarlayarak yüksek oranda dinamik düzenler oluşturabilirsiniz. İfadeler birçok temel .NET Framework kitaplığına erişim sağlayabilir.
- **İşleme özgü düzen**: İfadeler kullanarak rapor düzenini uygulanan işleme biçimine göre değiştirebilirsiniz. Örneğin raporun PDF gibi etkileşimli olmayan bir biçim kullanılarak işlenmesi durumunda görünürlüğü açma/kapatma (detaya gitmek ve detaydan çıkmak için) özelliğini devre dışı bırakılmasını sağlayabilirsiniz.
- **Yerel sorgular**: Bunun için öncelikle bir Power BI veri kümesi geliştirmenize gerek yoktur. [Desteklenen tüm veri kaynakları](../paginated-reports-data-sources.md) için yerel sorgular yazabilirsiniz (veya saklı yordamları kullanabilirsiniz). Sorgulara parametre eklenebilir.
- **Grafik sorgu tasarımcıları**: Power BI Report Builder'da veri kümesi sorgularınızı yazmanıza ve test etmenize yardımcı olacak grafik sorgu tasarımcıları vardır.
- **Statik veri kümeleri**: Bir veri kümesi tanımlayabilir ve rapor tanımınıza doğrudan veri girişi yapabilirsiniz. Bu seçenek özellikle tanıtım amaçlı kullanımlar veya kavram kanıtı sunmak için kullanışlıdır.
- **Veri tümleştirmesi**: Farklı veri kaynaklarında veya statik veri kümelerinde yer alan verileri birleştirebilirsiniz. Bunun için VB.NET ifadelerini kullanarak özel alanlar oluşturmanız gerekir.
- **Parametre ekleme**: Veri tabanlı ve basamaklı parametreler dahil olmak üzere yüksek oranda özelleştirilebilen parametre deneyimleri tasarlayabilirsiniz. Ayrıca parametreler için varsayılan değerler de belirleyebilirsiniz. Bu deneyimler, rapor kullanıcılarınızın uygun filtreleri hızlı bir şekilde ayarlamasına yardımcı olabilir. Ayrıca parametrelerin rapor verilerini filtrelemesi gerekmez. Durum senaryolarını desteklemek veya dinamik filtreleme ya da stil oluşturma için kullanılabilir.
- **Görüntü verileri**: Raporunuz, veri kaynağında ikili biçimde depolanan görüntüleri işleyebilir.
- **Özel kod**: Raporunuzda VB.NET işlevlerinden oluşan kod bloklarını geliştirebilir ve bunları istediğiniz rapor ifadesinde kullanabilirsiniz.
- **Alt raporlar**: Diğer Power BI sayfalandırılmış raporlarını (aynı çalışma alanında bulunan) raporunuza katıştırabilirsiniz.
- **Esnek veri kılavuzları**: Tablix veri bölgesini kullanarak kılavuz düzenleri üzerinde ayrıntılı denetim sahibi olursunuz. İç içe geçmiş ve bitişik gruplar dahil olmak üzere karmaşık düzenler de desteklenir. Birden fazla sayfaya yazdırıldığında üst bilgileri yineleyecek şekilde de yapılandırılabilir. Ayrıca alt raporlar veya veri çubukları, mini grafikler ve göstergeler dahil olmak üzere diğer görselleştirmeler de katıştırılabilir.
- **Uzamsal veri türleri**: Harita veri bölgesi, [SQL Server uzamsal veri türlerini](/sql/relational-databases/spatial/spatial-data-sql-server) görselleştirebilir. Bu sayede GEOGRAPHY ve GEOMETRY veri türleri ile noktalar, çizgiler veya çokgenler görselleştirilebilir. Ayrıca ESRI şekil dosyalarında tanımlanan çokgenler de görselleştirilebilir.
- **Modern ölçerler**: KPI değerlerini ve durumunu göstermek için radyal ve doğrusal ölçerler kullanılabilir. Bunlar kılavuz veri bölgelerine de katıştırılarak gruplar içinde tekrarlanabilir.
- **HTML işleme**: HTML olarak depolanan zengin biçimlendirilmiş metinleri görüntüleyebilirsiniz.
- **Adres mektup birleştirme**: Metin kutusu yer tutucularını kullanarak metne veri değerleri ekleyebilirsiniz. Bu sayede adres mektup birleştirme raporu oluşturabilirsiniz.
- **Etkileşim özellikleri**: Etkileşimli özellikler arasında görünürlüğü açma/kapatma (detaya gitmek ve detaydan çıkmak için), bağlantılar, etkileşimli sıralama ve araç ipuçları bulunur. Ayrıca Power BI raporlarına veya diğer Power BI sayfalandırılmış raporlarına giden bağlantılar da ekleyebilirsiniz. Bağlantılar aynı raporun farklı noktalarına da gidebilir.
- **Abonelikler**: Power BI sayfalandırılmış raporları, raporların desteklenen biçimlerden birinde eklendiği e-postalar halinde belirli bir zamanda gönderebilir.
- **Kullanıcıya özel düzenler**: Raporu açan kimliği doğrulanmış kullanıcıya göre ayarlanan dinamik rapor düzenleri oluşturabilirsiniz. Raporu verileri farklı şekilde filtreleyecek, veri bölgelerini veya görselleştirmeleri gizleyecek, farklı biçimler uygulayacak veya kullanıcıya özgü parametre varsayılanlarını ayarlayacak şekilde tasarlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](../paginated-reports-report-builder-power-bi.md)
- [SQL Server Reporting Services raporlarını Power BI’a geçirme](migrate-ssrs-reports-to-power-bi.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
