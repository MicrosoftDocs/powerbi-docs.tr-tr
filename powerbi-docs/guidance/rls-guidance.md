---
title: Power BI Desktop’ta satır düzeyi güvenlik (RLS) kılavuzu
description: Power BI Desktop ile veri modellerinizde satır düzeyi güvenliği (RLS) zorunlu kılma kılavuzu.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/18/2020
ms.author: v-pemyer
ms.openlocfilehash: 308e34e5bf70a9999939c99667075b2e468b4df4
ms.sourcegitcommit: eff98b49e794c7c07670dcfb871f43cb06ed9d3a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85095668"
---
# <a name="row-level-security-rls-guidance-in-power-bi-desktop"></a>Power BI Desktop’ta satır düzeyi güvenlik (RLS) kılavuzu

Bu makale, Power BI Desktop'la çalışan veri modelleyicilerine yöneliktir. Veri modellerinizde satır düzeyi güvenliği (RLS) zorunlu kılmaya yönelik iyi tasarım uygulamaları açıklanmaktadır.

RLS’nin _tablo satırlarını_ filtrelediğini kavramak önemlidir. Tablo, sütun veya ölçüler dahil olmak üzere model nesnelerine erişimi kısıtlamak için yapılandırılamaz.

> [!NOTE]
> Bu makalede RLS’nin ne olduğu veya nasıl ayarlanacağı açıklanmaz. Daha fazla bilgi için bkz. [Power BI Desktop için satır düzeyi güvenlik (RLS) ile veri erişimini kısıtlama](../create-reports/desktop-rls.md).
>
> Ayrıca, Azure Analysis Services veya SQL Server Analysis Services ile dışarıda barındırılan modellerle kurulan canlı bağlantılarda RLS’yi zorunlu kılma konusu bu makalede açıklanmaz. Bu durumlarda RLS, Analysis Services tarafından zorunlu kılınır. Power BI çoklu oturum açma (SSO) kullanarak bağlanırsa RLS’yi Analysis Services zorunlu kılar (hesabın yönetici ayrıcalıkları yoksa).

## <a name="create-roles"></a>Rol oluşturma

Birden çok rol oluşturulabilir. Tek bir rapor kullanıcısına gereken izinleri düşünüyorsanız bu kullanıcının birden çok rolün üyesi olduğu bir tasarım yerine, tüm bu izinleri sağlayan tek bir rol oluşturmaya gayret edin. Çünkü bir rapor kullanıcısı, doğrudan kendi kullanıcı hesabını kullanarak veya güvenlik grubu üyeliği tarafından dolaylı yoldan birden çok role eşlenebilir. Birden çok rol eşlemesi, beklenmeyen sonuçlara neden olabilir.

Bir rapor kullanıcısı birden çok role atandığında, RLS filtreleri eklenebilir hale gelir. Bu, rapor kullanıcılarının bu filtrelerin birleşimini gösteren tablo satırlarını görebileceği anlamına gelir. Dahası, bazı senaryolarda rapor kullanıcısının bir tablodaki satırları görmeyeceğini garanti etmek mümkün değildir. Bu nedenle, SQL Server veritabanı nesnelerine (ve diğer izin modellerine) izinler uygulanmadıkça, “bir kez reddedilen her zaman reddedilir” ilkesi de uygulanmaz.

İki rolü olan bir model düşünün: **Çalışanlar** adlı ilk rol, aşağıdaki kural ifadesini kullanarak tüm **Bordro** tablo satırlarına yönelik erişimi kısıtlar:

```dax
FALSE()
```

> [!NOTE]
> Kuralın ifadesi **false** olarak değerlendirilmediğinde kural herhangi bir tablo satırı döndürmez.

Ancak **Yöneticiler** adlı ikinci rol, aşağıdaki kural ifadesini kullanarak tüm **Bordro** tablo satırlarına yönelik erişime izin verir:

```dax
TRUE()
```

Şuna dikkat edin: Bir rapor kullanıcısı her iki rolle de eşlenirse tüm **Maaş** tablosu satırlarını görecektir.

## <a name="optimize-rls"></a>RLS’yi iyileştirme

RLS, her DAX sorgusuna otomatik olarak filtre uygulayarak çalışır ve bu filtrelerin sorgu performansı üzerinde olumsuz bir etkisi olabilir. Bu nedenle, verimli RLS için modelin iyi tasarlanması gerekir. Aşağıdaki makalelerde açıklandığı şekilde, model tasarım kılavuzunu izlemek önemlidir:

- [Yıldız şemasını ve Power BI açısından önemini anlama](star-schema.md)
- [Power BI kılavuz belgelerinde](https://docs.microsoft.com/power-bi/guidance/) bulunan tüm ilişki kılavuzu makaleleri

Genel anlamda, RLS filtrelerini olgu türünde tablolar yerine boyut türünde tablolarda zorunlu kılmak çoğu zaman daha verimlidir. Ayrıca, RLS filtrelerinin diğer model tablolarına yayılmasını sağlamak için iyi tasarlanmış ilişkileri kullanabilirsiniz. Bu nedenle, model ilişkileri aynı sonuca ulaşacağı zaman [LOOKUPVALUE](https://docs.microsoft.com/dax/lookupvalue-function-dax) DAX işlevini kullanmaktan kaçının.

DirectQuery tablolarında RLS filtreleri her zorunlu kılındığında ve diğer DirectQuery tablolarıyla ilişkiler söz konusu olduğunda, kaynak veritabanını iyileştirdiğinizden emin olun. Bu işlem için uygun dizinlerin tasarlanması veya kalıcı olarak hesaplanan sütunların kullanılması gerekebilir. Daha fazla bilgi için bkz. [Power BI Desktop’ta DirectQuery modeli kılavuzu](directquery-model-guidance.md).

### <a name="measure-rls-impact"></a>RLS etkisini ölçme

[Performans Analizi](../create-reports/desktop-performance-analyzer.md)’ni kullanarak Power BI Desktop’taki RLS filtrelerinin performans etkisini ölçebilirsiniz. İlk olarak, RLS zorunlu kılınmadığında rapor görseli sorgu sürelerini belirleyin. Daha sonra, RLS’yi zorunlu kılmak ve sorgu sürelerini belirleyip karşılaştırmak için **Modelleme** şerit sekmesindeki **Farklı Görüntüle** komutunu kullanın.

## <a name="configure-role-mappings"></a>Rol eşlemelerini yapılandırma

Power BI’da yayımlandığında, üyeleri veri kümesi rolleriyle eşlemeniz gerekir. Yalnızca veri kümesi sahipleri veya çalışma alanı yöneticileri roller üye ekleyebilir. Daha fazla bilgi için bkz. [Power BI ile satır düzeyi güvenlik (RLS) (Modelinizde güvenliği yönetme)](../admin/service-admin-rls.md#manage-security-on-your-model).

Üyeler kullanıcı hesapları veya güvenlik grupları olabilir. Mümkün olduğunda, güvenlik gruplarını veri kümesi rollerine eşlemenizi öneririz. Buna Azure Active Directory’deki güvenlik grubu üyeliklerini yönetmek de dahildir. Büyük olasılıkla, görevi ağ yöneticilerinize devreder.

## <a name="validate-roles"></a>Rolleri doğrulama

Modeli doğru şekilde filtrelemesini sağlamak için her bir rolü test edin. Bu işlem, **Modelleme** şerit sekmesindeki **Farklı Görüntüle** komutunu kullanarak kolayca yapılır.

Model [USERNAME](https://docs.microsoft.com/dax/username-function-dax) DAX işlevini kullanarak dinamik kurallara sahip olduğunda, beklenen _ve beklenmeyen_ değerleri test ettiğinizden emin olun. Power BI içeriğini eklerken (özellikle [Uygulama verilere sahiptir](../developer/embedded/embedding.md#embedding-for-your-customers) senaryosu kullanılırken) uygulama mantığı tüm değerleri etkili bir kimlik kullanıcı adı olarak geçirebilir. Mümkün olduğunda, yanlışlıkla veya kötü amaçlı kullanılan değerlerin filtrelerde satır döndürmemesini sağlayın.

Uygulamanın, kullanıcının iş rolünü etkin kullanıcı adı olarak geçirdiği, Power BI Embedded kullandığınız bir örneği ele alın: Bu “Yönetici” veya “Çalışan” olabilir. Yöneticiler tüm satırları görebilir, ancak çalışanlar yalnızca **Tür** sütun değerinin “İç” olduğu satırları görebilir.

Aşağıdaki kural ifadesi tanımlanmıştır:

```dax
IF(
    USERNAME() = "Worker",
    [Type] = "Internal",
    TRUE()
)
```

Bu kural ifadesiyle ilgili sorun, “Çalışan” hariç tüm değerlerin _tüm tablo satırlarını_ döndürmesidir. Yani “Çlışan” gibi yanlışlıkla yazılan bir değer, istenmeyen bir şekilde tüm tablo satırlarını döndürür. Bu nedenle, beklenen her değeri test eden bir ifade yazmak daha güvenlidir. Aşağıdaki iyileştirilmiş kural ifadesinde, beklenmeyen bir değer tabloda hiç satır döndürmemektedir.

```dax
IF(
    USERNAME() = "Worker",
    [Type] = "Internal",
    IF(
        USERNAME() = "Manager",
        TRUE(),
        FALSE()
    )
)
```

## <a name="design-partial-rls"></a>Kısmi RLS tasarlama

Bazen, hesaplamalar için RLS filtreleri tarafından kısıtlanmayan değerler gerekir. Örneğin bir raporda, rapor kullanıcısının satış bölgesinde elde edilen gelirin _elde edilen tüm gelire_ oranının gösterilmesi gerekebilir.

Bir DAX ifadesinin RLS’yi geçersiz kılması mümkün olmasa da (aslında RLS’nin zorunlu kılındığını bile belirleyemez) bir özet model tablosu kullanabilirsiniz. Özet model tablosu “tüm bölgeler” için geliri almak üzere sorgulanır ve RLS filtreleriyle kısıtlanmaz.

Bu tasarım gereksinimini nasıl uygulayabileceğinizi görelim. İlk olarak, aşağıdaki model tasarımını ele alın:

:::image type="content" source="media/rls-guidance/mixed-rls-model.png" alt-text="Model diyagramının bir resmi gösterilir. Aşağıdaki paragraflarda açıklanmıştır.":::

Model dört tablodan oluşur:

- **Salesperson** tablosu, satış personeli başına bir satır depolar. Her satış personelinin e-posta adresinin depolandığı **EmailAddress** sütununu içerir. Bu tablo gizlidir.
- **Satış** tablosu, sipariş başına bir satır depolar. Rapor kullanıcısının bölgesinde elde edilen gelirlerin, tüm bölgelerde elde edilen gelirlere oranını döndürmek üzere tasarlanan **Revenue % All Region** ölçüsünü içerir.
- **Date** tablosu tarih başına bir satır döndürür ve yıl ile ay şeklinde filtreleyip gruplandırmaya olanak verir.
- **SalesRevenueSummary**, hesaplanan bir tablodur. Her sipariş tarihi için toplam geliri depolar. Bu tablo gizlidir.

Aşağıdaki ifadede **SalesRevenueSummary** hesaplanan tablosu tanımlanır:

```dax
SalesRevenueSummary =
SUMMARIZECOLUMNS(
    Sales[OrderDate],
    "RevenueAllRegion", SUM(Sales[Revenue])
)
```

> [!NOTE]
> Aynı tasarım gereksinimini [toplama tablosu](../transform-model/desktop-aggregations.md) da karşılayabilirdi.

**Salesperson** tablosuna aşağıdaki RLS kuralı uygulanır:

```dax
[EmailAddress] = USERNAME()
```

Üç model ilişkisinin her biri, aşağıdaki tabloda açıklanır:

|İlişki|Açıklama|
|---------|---------|
|![Akış çizelgesi sonlandırıcı 1.](media/common/icon-01-red-30x30.png)|**Salesperson** ve **Sales** tabloları arasında çoka çok ilişki vardır. RLS kuralı, [USERNAME](https://docs.microsoft.com/dax/username-function-dax) DAX işlevini kullanarak gizli **Salesperson** tablosunun **EmailAddress** sütununu filtreler. **Region** sütun değeri (rapor kullanıcısı için) **Sales** tablosuna yayılır.|
|![Akış çizelgesi sonlandırıcı 2.](media/common/icon-02-red-30x30.png)|**Date** ve **Sales** tablolarında bire çok ilişkiler vardır.|
|![Akış çizelgesi sonlandırıcı 3.](media/common/icon-03-red-30x30.png)|**Date** ve **SalesRevenueSummary** tabloları arasında bire çok ilişkiler vardır.|

Aşağıdaki ifadede **Revenue % All Region** ölçüsü açıklanır:

```dax
Revenue % All Region =
DIVIDE(
    SUM(Sales[Revenue]),
    SUM(SalesRevenueSummary[RevenueAllRegion])
)
```

> [!NOTE]
> Hassas bilgileri açığa çıkarmaktan kaçınmaya özen gösterin. Bu örnekte yalnızca iki bölge varsa bir rapor kullanıcısının diğer bölge için geliri hesaplaması mümkündür.

## <a name="avoid-using-rls"></a>RLS’yi kullanmaktan kaçınma

İhtiyaç duymadığınız sürece RLS’yi kullanmaktan kaçının. Statik filtreler uygulayan az sayıda basitleştirilmiş RLS kuralınız varsa bunun yerine birden çok veri kümesini yayımlamanız yararlı olabilir. Aynı veri izinlerine sahip her veri kümesi belirli bir rapor kullanıcı kitlesine yönelik veri içerdiğinden, veri kümelerinin hiçbiri rolleri tanımlamaz. Daha sonra, kitle başına bir çalışma alanı oluşturup çalışma alanına veya uygulamaya erişim izinleri atayın.

Örneğin, yalnızca iki satış bölgesi olan bir şirket farklı çalışma alanlarına _her satış bölgesi için_ bir veri kümesi yayımlamaya karar verir. Veri kümeleri RLS’yi zorunlu kılmaz. Ancak, kaynak verilerini filtrelemek için [sorgu parametrelerini](https://docs.microsoft.com/power-query/power-query-query-parameters) kullanırlar. Bu yöntemle, aynı model her çalışma alanında yayımlanır, yalnızca veri kümesi parametre değerleri farklıdır. Satış personellerine yalnızca bir çalışma alanına (veya yayımlanan uygulamaya) erişim atanır.

RLS’den kaçınmanın çeşitli avantajları vardır:

- **İyileştirilmiş sorgu performansı:** Daha az filtreye sahip olduğundan, performansın iyileşmesine yardımcı olabilir.
- **Daha küçük modeller:** Daha fazla model oluştursa da bunlar boyut bakımından daha küçüktür. Özellikle barındırma kapasitesi kaynaklar üzerinde baskı hissediyorsa daha küçük modeller sorgu ve veri yenileme yanıt hızını iyileştirebilir. Ayrıca model boyutlarını, kapasiteniz tarafından uygulanan boyut sınırlarının altında tutmak daha kolaydır. Son olarak, farklı kapasitelerde çalışma alanları oluşturabileceğinizden (veya bunları farklı kapasitelere taşıyabileceğinizden), farklı kapasiteler arasında iş yüklerini dengelemek daha kolaydır.
- **Ek özellikler:** [Web’de yayımlama](../collaborate-share/service-publish-to-web.md) gibi RLS ile çalışmayan Power BI özellikleri kullanılabilir.

Ancak, RLS’den kaçınmanın bazı dezavantajları da vardır:

- **Birden çok çalışma alanı**: Her rapor kullanıcı kitlesi için bir çalışma alanı gerekir. Uygulamalar yayımlandıysa bu, rapor kullanıcı kitlesi başına bir uygulama olduğu anlamına gelir.
- **İçeriğin çoğaltılması:** Rapor ve panoların her bir çalışma alanında oluşturulmaları gerekir. Ayarlayıp sürdürmek için daha fazla çaba ve zaman harcamanız gerekir.
- **Yüksek ayrıcalığa sahip kullanıcılar:** Birden çok rapor kullanıcı kitlesine ait olan yüksek ayrıcalığa sahip kullanıcılar, verilerin birleştirilmiş bir görünümünü göremez. Birden çok raporu (farklı çalışma alanlarından veya uygulamalardan) açmaları gerekir.

## <a name="troubleshoot-rls"></a>RLS sorunlarını giderme

RLS beklenmeyen sonuçlar üretirse aşağıdaki sorunları denetleyin:

- Model tabloları arasında, sütun eşleme ve filtre yönü bakımından hatalı ilişkiler var.
- **Güvenlik filtrelerini her iki yönde de uygula** ilişki özelliği doğru ayarlanmamış. Daha fazla bilgi için bkz. [Çift yönlü ilişki kılavuzu](relationships-bidirectional-filtering.md).
- Tablolar veri içermiyor.
- Tablolara yanlış değerler yüklenmiş.
- Kullanıcı birden çok role eşlenmiş.
- Model, toplama tabloları içeriyor ve RLS kuralları toplamalar ile ayrıntıları tutarlı bir şekilde filtrelemiyor. Daha fazla bilgi için bkz. [Power BI Desktop’ta toplamaları kullanma (toplamalar için RLS)](../transform-model/desktop-aggregations.md#rls-for-aggregations).

Belirli bir kullanıcının hiç veri görmemesi, UPN’lerinin depolanmamasından veya yanlış girilmesinden kaynaklanabilir. Bir ad değişikliğinin sonucu olarak kullanıcı hesabı değiştiyse bu durum bir anda oluşabilir.

> [!TIP]
> Test amacıyla, [USERNAME](https://docs.microsoft.com/dax/username-function-dax) DAX işlevini döndüren bir ölçü ekleyin. Bunu “Ben Kimim?” şeklinde adlandırabilirsiniz. Daha sonra, ölçüyü rapordaki bir kart görseline ekleyip Power BI’da yayımlayın.

Belirli bir kullanıcı tüm verileri görebiliyorsa raporlara doğrudan çalışma alanından erişiyor olabilir veya veri kümesinin sahibi olabilir. RLS yalnızca şu durumlarda zorunlu kılınır:

- Rapor bir uygulamada açıldığında.
- Rapor bir çalışma alanında açıldığında ve kullanıcı [Görüntüleyici rolüyle](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces) eşlendiğinde.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI ile satır düzeyinde güvenlik (RLS)](../admin/service-admin-rls.md)
- [Power BI Desktop için satır düzeyi güvenlik (RLS) ile veri erişimini kısıtlama](../create-reports/desktop-rls.md)
- [Power BI Desktop’ta model ilişkileri](../transform-model/desktop-relationships-understand.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
