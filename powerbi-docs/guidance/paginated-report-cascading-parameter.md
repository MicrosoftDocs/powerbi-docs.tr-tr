---
title: Sayfalandırılmış raporlarda basamaklı parametreleri kullanma
description: Basamaklı parametreleri kullanarak sayfalandırılmış raporlar tasarlama yönergeleri.
author: peter-myers
ms.author: kfollis
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 01/14/2020
ms.openlocfilehash: 826c43d67d76f1f53f2bf9b45e519469b9e71c75
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99087718"
---
# <a name="use-cascading-parameters-in-paginated-reports"></a>Sayfalandırılmış raporlarda basamaklı parametreleri kullanma

Bu makale Power BI [sayfalandırılmış raporları](../paginated-reports/paginated-reports-report-builder-power-bi.md) tasarlayan rapor yazarlarına yöneliktir. Basamaklı parametreler tasarlama senaryoları sağlar. Basamaklı parametreler, bağımlılıkları olan rapor parametreleridir. Rapor kullanıcısı parametre değeri (veya değerleri) seçtiğinde, bu başka bir parametrenin kullanılabilir değerlerini ayarlamak için kullanılır.

> [!NOTE]
> Basamaklı parametrelere giriş bilgileri ve bunların nasıl yapılandırılacağı bu makalenin kapsamına alınmamıştır. Basamaklı parametreleri tam olarak bilmiyorsanız, önce [Rapora Basamaklı Parametreler Ekleme (Report Builder ve SSRS)](/sql/reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs) makalesini okumanızı öneririz.

## <a name="design-scenarios"></a>Tasarım senaryoları

Basamaklı parametreleri kullanmaya yönelik iki tasarım senaryosu vardır. Bunlar, aşağıdaki işlemleri yapmak için etkili bir şekilde kullanılabilir:

- _Büyük öğe kümelerini_ filtreleme
- _Uygun_ öğeleri gösterme

### <a name="example-database"></a>Örnek veritabanı

Bu makalede gösterilen örneklerde Azure SQL Veritabanı temel alınmıştır. Veritabanında satış işlemleri kaydedilmiştir ve veritabanı bayilerin, ürünlerin ve satış siparişlerinin depolandığı çeşitli tablolar içerir.

**Reseller** (Bayi) adlı tabloda her bayi için bir kayıt depolanır ve bu tablo binlerce kayıt içerir. **Reseller** tablosunda şu sütunlar bulunur:

- ResellerCode (tamsayı)
- ResellerName
- Ülke-Bölge
- State-Province
- Şehir
- PostalCode

**Sales** (Satışlar) adlı da bir tablo vardır. Satış siparişi kayıtlarını depolar ve **Reseller Code** sütununda **Reseller** tablosuyla arasında yabancı anahtar ilişkisi bulunur.

### <a name="example-requirement"></a>Örnek gereksinimi

Reseller Profile (Bayi Profili) raporu geliştirme gereksinimi vardır. Rapor tek bir bayinin bilgilerini görüntüleyecek şekilde tasarlanmalıdır. Rapor kullanıcısının bayi kodunu girmesi uygun bir yöntem değildir çünkü bu koda nadiren ezbere bilirler.

## <a name="filter-large-sets-of-items"></a>Büyük öğe kümelerini filtreleme

Bayiler gibi büyük miktarlardaki kullanılabilir öğeleri sınırlandırmanıza yardımcı olması için şu üç örneği gözden geçirelim. Bunlar:

- [İlgili sütunlara göre filtreleme](#filter-by-related-columns)
- [Gruplandırma sütununa göre filtreleme](#filter-by-a-grouping-column)
- [Arama düzenine göre filtreleme](#filter-by-search-pattern)

### <a name="filter-by-related-columns"></a>İlgili sütunlara göre filtreleme

Bu örnekte rapor kullanıcısı beş rapor parametresiyle etkileşimli çalışır. Country-Region, State-Province, City ve Postal Code değerlerini seçmesi gerekir. Ardından son bir parametre söz konusu coğrafi konumda bulunan bayileri listeler.

![İlgili sütunlara göre filtrelemeyi gösteren Power BI sayfalandırılmış rapor parametrelerinin ekran görüntüsü.](media/paginated-report-cascading-parameter/filter-by-related-columns-example.png)

Basamaklı parametreleri şu şekilde geliştirebilirsiniz:

1. Doğru sırada yerleştirilmiş beş rapor parametresi oluşturun.
2. Aşağıdaki sorgu deyimini kullanarak ayrı ülke-bölge (Country-Region) değerlerini alan **CountryRegion** veri kümesini oluşturun:

    ```sql
    SELECT DISTINCT
      [Country-Region]
    FROM
      [Reseller]
    ORDER BY
      [Country-Region]
    ```

3. Aşağıdaki sorgu deyimini kullanarak, seçilen ülke-bölge için ayrı eyalet-il (State-Province) değerlerini alan **StateProvince** veri kümesini oluşturun:

    ```sql
    SELECT DISTINCT
      [State-Province]
    FROM
      [Reseller]
    WHERE
      [Country-Region] = @CountryRegion
    ORDER BY
      [State-Province]
    ```

4. Aşağıdaki sorgu deyimini kullanarak, seçilen ülke-bölge ve eyalet-il için ayrı şehir (City) değerlerini alan **City** veri kümesini oluşturun:

    ```sql
    SELECT DISTINCT
      [City]
    FROM
      [Reseller]
    WHERE
      [Country-Region] = @CountryRegion
      AND [State-Province] = @StateProvince
    ORDER BY
      [City]
    ```

5. Bu düzenle devam ederek **PostalCode** veri kümesini de oluşturun.
6. Aşağıdaki sorgu deyimini kullanarak, seçilen coğrafi değerler için tüm bayileri alan **Reseller** veri kümesini oluşturun:

    ```sql
    SELECT
      [ResellerCode],
      [ResellerName]
    FROM
      [Reseller]
    WHERE
      [Country-Region] = @CountryRegion
      AND [State-Province] = @StateProvince
      AND [City] = @City
      AND [PostalCode] = @PostalCode
    ORDER BY
      [ResellerName]
    ```

7. İlki dışındaki her veri kümesi, sorgu parametrelerini ilgili rapor parametrelerine eşler.

> [!NOTE]
> Bu örneklerde gösterilen tüm sorgu parametreleri (önünde @ simgesi bulunan parametreler) SELECT deyimlerinin içine eklenebilir veya saklı yordamlara geçirilebilir.
>
> Genel olarak saklı yordamların kullanılması daha iyi bir tasarım yaklaşımıdır. Çünkü saklı yordamların sorgu planları daha hızlı yürütülmesi için önbelleğe alınmıştır ve gerektiğinde daha ileri düzey bir mantık geliştirmenize olanak tanır. Öte yandan bunlar şu anda ağ geçidi ilişkisel veri kaynaklarında, yani SQL Server, Oracle ve Teradata’da desteklenmemektedir.
>
> Son olarak, her zaman verimli bir veri alma işlemini destekleyecek uygun dizinlerin mevcut olduğundan emin olmalısınız. Aksi takdirde rapor parametreleriniz yavaş doldurulabilir ve veritabanı aşırı yüklenebilir. SQL Server dizini hakkında daha fazla bilgi için bkz. [SQL Server Dizin Mimarisi ve Tasarım Kılavuzu](/sql/relational-databases/sql-server-index-design-guide).

### <a name="filter-by-a-grouping-column"></a>Gruplandırma sütununa göre filtreleme

Bu örnekte rapor kullanıcısı bayi adının ilk harfini seçmek için bir rapor parametresiyle etkileşimli çalışır. Sonra ikinci bir parametre adı seçili harfle başlayan bayileri listeler.

![Gruplandırma sütununa göre filtrelemeyi gösteren Power BI sayfalandırılmış rapor parametrelerinin ekran görüntüsü.](media/paginated-report-cascading-parameter/filter-by-grouping-column-example.png)

Basamaklı parametreleri şu şekilde geliştirebilirsiniz:

1. Doğru sırada yerleştirilmiş **ReportGroup** ve **Reseller** rapor parametrelerini oluşturun.
2. Aşağıdaki sorgu deyimini kullanarak, tüm bayiler tarafından kullanılan ilk harfleri almak için **ReportGroup** veri kümesini oluşturun:

    ```sql
    SELECT DISTINCT
      LEFT([ResellerName], 1) AS [ReportGroup]
    FROM
      [Reseller]
    ORDER BY
      [ReportGroup]
    ```

3. Aşağıdaki sorgu deyimini kullanarak, adı seçilen harfle başlayan tüm bayileri almak için **Reseller** veri kümesini oluşturun:

    ```sql
    SELECT
      [ResellerCode],
      [ResellerName]
    FROM
      [Reseller]
    WHERE
      LEFT([ResellerName], 1) = @ReportGroup
    ORDER BY
      [ResellerName]
    ```

4. **Reseller** veri kümesinin sorgu parametresini buna karşılık gelen rapor parametresiyle eşleyin.

**Reseller** tablosuna gruplandırma sütununu eklemek daha verimli bir yöntemdir. Kalıcı olduğunda ve dizine alındığında en iyi sonucu verir. Daha fazla bilgi için bkz. [Tabloda Hesaplanan Sütunları Belirtme](/sql/relational-databases/tables/specify-computed-columns-in-a-table).

```sql
ALTER TABLE [Reseller]
ADD [ReportGroup] AS LEFT([ResellerName], 1) PERSISTED
```

Bu teknik daha da yüksek bir potansiyele sahiptir. Bayileri _önceden tanımlanmış harf bantlarına_ göre filtrelemek için yeni bir gruplandırma sütunu ekleyen aşağıdaki betiğe bakın. Bu betik ayrıca rapor parametrelerine gereken verileri verimli bir şekilde almak için bir dizin oluşturur.

```sql
ALTER TABLE [Reseller]
ADD [ReportGroup2] AS CASE
  WHEN [ResellerName] LIKE '[A-C]%' THEN 'A-C'
  WHEN [ResellerName] LIKE '[D-H]%' THEN 'D-H'
  WHEN [ResellerName] LIKE '[I-M]%' THEN 'I-M'
  WHEN [ResellerName] LIKE '[N-S]%' THEN 'N-S'
  WHEN [ResellerName] LIKE '[T-Z]%' THEN 'T-Z'
  ELSE '[Other]'
END PERSISTED
GO

CREATE NONCLUSTERED INDEX [Reseller_ReportGroup2]
ON [Reseller] ([ReportGroup2]) INCLUDE ([ResellerCode], [ResellerName])
GO
```

### <a name="filter-by-search-pattern"></a>Arama düzenine göre filtreleme

Bu örnekte rapor kullanıcısı arama düzeni girmek için bir rapor parametresiyle etkileşimli çalışır. Sonra ikinci bir parametre adı bu düzeni içeren bayileri listeler.

![Arama desenine göre filtrelemeyi gösteren Power BI sayfalandırılmış rapor parametrelerinin ekran görüntüsü.](media/paginated-report-cascading-parameter/filter-by-search-pattern-example.png)

Basamaklı parametreleri şu şekilde geliştirebilirsiniz:

1. Doğru sırada yerleştirilmiş **Search** ve **Reseller** rapor parametrelerini oluşturun.
2. Aşağıdaki sorgu deyimini kullanarak, arama metnini içeren tüm bayileri almak için **Reseller** veri kümesini oluşturun:

    ```sql
    SELECT
      [ResellerCode],
      [ResellerName]
    FROM
      [Reseller]
    WHERE
      [ResellerName] LIKE '%' + @Search + '%'
    ORDER BY
      [ResellerName]
    ```

3. **Reseller** veri kümesinin sorgu parametresini buna karşılık gelen rapor parametresiyle eşleyin.

> [!TIP]
> Bu tasarım üzerinde geliştirmeler yaparak rapor kullanıcılarınıza daha fazla denetim sağlayabilirsiniz. Bu tasarım kendi düzen eşleştirme değerlerini tanımlamalarına izin verir. Örneğin, "red%" arama değeri adları “red” karakterleriyle _başlayan_ bayileri listeler.
>
> Daha fazla bilgi için bkz. [LIKE (Transact-SQL)](/sql/t-sql/language-elements/like-transact-sql#using-the--wildcard-character).

Rapor kullanıcılarına kendi düzenlerini tanımlama olanağını nasıl sağlayacağınız aşağıda gösterilmiştir.

```sql
WHERE
  [ResellerName] LIKE @Search
```

Bununla birlikte veritabanı uzmanı olmayan birçok kullanıcı yüzde (%) joker karakterini bilmez. Bunun yerine yıldız (*) karakterine alışkınlardır. WHERE yan tümcesini değiştirerek bu karakteri kullanmalarını sağlayabilirsiniz.

```sql
WHERE
  [ResellerName] LIKE SUBSTITUTE(@Search, '%', '*')
```

## <a name="present-relevant-items"></a>Uygun öğeleri gösterme

Bu senaryoda kullanılabilir değerleri sınırlandırmak için olgu verilerini kullanabilirsiniz. Rapor kullanıcılarına etkinliğin kaydedildiği öğeler gösterilir.

Bu örnekte rapor kullanıcısı üç rapor parametresiyle etkileşimli çalışır. İlk ikisi satış siparişi tarihlerinin tarih aralığını ayarlar. Sonra üçüncü parametre, söz konusu tarih aralığında siparişlerin oluşturulmuş olduğu bayileri listeler.

![Üç rapor parametresini gösteren Power BI sayfalandırılmış rapor parametrelerinin ekran görüntüsü: Start Order Date, End Order Date ve Reseller.](media/paginated-report-cascading-parameter/filter-relevant-items-example.png)

Basamaklı parametreleri şu şekilde geliştirebilirsiniz:

1. Doğru sırada yerleştirilmiş **OrderDateStart**, **OrderDateEnd** ve **Reseller** rapor parametrelerini oluşturun.
2. Aşağıdaki sorgu deyimini kullanarak, tarih aralığında sipariş oluşturmuş tüm bayileri alan **Reseller** veri kümesini oluşturun:

    ```sql
    SELECT DISTINCT
      [r].[ResellerCode],
      [r].[ResellerName]
    FROM
      [Reseller] AS [r]
    INNER JOIN [Sales] AS [s]
      ON [s].[ResellerCode] = [r].[ResellerCode]
    WHERE
      [s].[OrderDate] >= @OrderDateStart
      AND [s].[OrderDate] < DATEADD(DAY, 1, @OrderDateEnd)
    ORDER BY
      [r].[ResellerName]
    ```

## <a name="recommendations"></a>Öneriler

Raporlarınızı mümkün olduğunca basamaklı parametrelerle tasarlamanızı öneririz. Çünkü:

- Bunlar rapor kullanıcılarınız için sezgisel ve kullanışlı deneyimler sağlar
- Bunlar kullanılabilir değerlerin daha küçük kümelerini aldıklarından verimlidir

Aşağıdakileri yaparak veri kaynaklarını iyileştirdiğinizden emin olun:

- Mümkün olduğunca saklı yordamları kullanın
- Verileri verimli bir şekilde alabilmek için uygun dizinleri ekleyin
- Pahalı sorgu zamanı değerlendirmelerinden kaçınmak için sütun değerlerini, hatta satırları ortaya çıkarın

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Report Builder’da rapor parametreleri](../paginated-reports/report-builder-parameters.md)
- [Rapora Basamaklı Parametreler Ekleme (Report Builder ve SSRS)](/sql/reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)
