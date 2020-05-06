---
title: Power BI Desktop’ta sorguyu kaynağa döndürme kılavuzu
description: Power BI Desktop'ta sorguyu kaynağa döndürmeyi gerçekleştirmeye yönelik kılavuz.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/09/2019
ms.author: v-pemyer
ms.openlocfilehash: e8123bba9f68305e1944dbfb280b5255e4fb9b48
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "75622155"
---
# <a name="query-folding-guidance-in-power-bi-desktop"></a>Power BI Desktop’ta sorguyu kaynağa döndürme kılavuzu

Bu makale Power BI Desktop’ta model geliştiren veri modelleyicilerine yöneliktir. Sorguyu kaynağa döndürmeyi ne zaman ve nasıl gerçekleştireceğinize ilişkin en iyi yöntem yönergelerini sağlar.

_Sorguyu kaynağa döndürme_, bir Power Query sorgusunun kaynak verileri alan ve dönüştüren tek bir sorgu deyimi oluşturma becerisidir. Daha fazla bilgi için bkz. [Power Query sorguyu kaynağa döndürme](/power-query/power-query-folding).

## <a name="guidance"></a>Rehber

Sorguyu kaynağa döndürme yönergeleri model moduna bağlı olarak değişiklik gösterir.

Bir **DirectQuery** veya **İkili** depolama modu tablosunda Power Query sorgusunun kaynağa döndürmeyi gerçekleştirmesi gerekir.

**İçeri Aktarma** tablosunda sorguyu kaynağa döndürmeyi gerçekleştirmek mümkündür. Sorgunun bir ilişkisel kaynağı temel aldığı ve tek bir SELECT deyiminin oluşturulabildiği durumlarda _en iyi veri yenileme performansını_ elde etmek için sorguyu kaynağa döndürmenin gerçekleştiğinden emin olmalısınız. Power Query karma altyapısının dönüştürmeleri işlemesi hala gerekliyse, özellikle büyük veri kümeleri için yapması gereken işi en aza indirmeye çalışmanız gerekir.

Aşağıdaki madde işaretli listede belirli yönergeler verilmektedir.

- **Veri kaynağını mümkün olduğunca fazla işlemle görevlendirin**: Bir Power Query sorgusunun tüm adımları kaynağa döndürülemediğinde, sorguyu kaynağa döndürmeyi önleyen adımı bulma. Mümkün olduğunda, sorguyu kaynağa döndürme işleminde hesaba katılabilmesi için sonraki adımları sıranın başına taşıma. Power Query karma altyapısının, kaynak sorguyu oluşturduğunda sorgu adımlarınızı yeniden sıralamak için yeterince akıllı olabileceğini unutmayın.

    İlişkisel bir veri kaynağı için, sorgu katlamayı engelleyen adım tek bir SELECT deyiminde veya saklı yordamın yordamsal mantığı dahilinde gerçekleştirilebiliyorsa, bir sonraki bölümde açıklandığı gibi yerel bir SQL sorgusu kullanmayı düşünün.

- **Yerel SQL sorgusu kullanma**: Bir Power Query sorgusu ilişkisel bir kaynaktan veri aldığında, bazı kaynaklar için yerel bir SQL sorgusu kullanmak mümkündür. Sorgu aslında saklı yordam yürütmesi dahil olmak üzere herhangi bir geçerli deyim olabilir. Deyim birden çok sonuç kümesi üretirse yalnızca ilki döndürülür. Deyimde parametreler tanımlanabilir ve [Value.NativeQuery](/powerquery-m/value-nativequery) M işlevini kullanmanız önerilir. Bu işlev parametre değerlerini güvenle ve kullanışlı bir şekilde geçirmek için tasarlanmıştır. Power Query karma altyapısının sonraki sorgu adımlarını kaynağa döndüremediğini ve bu nedenle tüm dönüştürme mantığını (veya olabildiğince çoğunu) yerel sorgu deyimine eklemeniz gerektiğini anlamak önemlidir.

    Yerel SQL sorguları kullanırken göz önünde bulundurmanız gereken iki önemli konu vardır:

    - DirectQuery model tablosu için sorgunun bir SELECT deyimi olması gerekir ve Orta Tablo İfadeleri (CTE) veya saklı yordam kullanamaz.
    - Artımlı yenileme yerel SQL sorgusu kullanamaz. Dolayısıyla Power Query karma altyapısını tüm kaynak satırları almaya ve sonra artımlı değişiklikleri belirlemek için filtre uygulamaya zorlayabilir.

    > [!IMPORTANT]
    > Yerel SQL sorgusu, veri almaktan daha fazlasını yapma potansiyeline sahiptir. Verileri değiştiren veya silen deyimler de dahil olmak üzere herhangi bir geçerli deyim yürütülebilir (muhtemelen birden çok kez). Veritabanına erişmek için kullanılan hesabın gerekli veriler üzerinde yalnızca okuma iznine sahip olduğundan emin olmak için en düşük ayrıcalık ilkesini uygulamanız gerekir.

- **Kaynaktaki dönüştürme verilerini hazırlama**: Belirli Power Query sorgu adımlarının kaynağa döndürülemediğini belirlediğinizde, dönüşümleri veri kaynağına uygulamak mümkün olabilir. Dönüştürmeler, kaynak verileri mantıksal olarak dönüştüren bir veritabanı görünümü yazarak gerçekleştirilebilir. Bunun için, Power BI sorgulamadan önce verileri fiziksel olarak hazırlama ve gerçekleştirmeyi de tercih edebilirsiniz. İlişkisel veri ambarı, genellikle kuruluş verilerinin önceden tümleştirilmiş kaynaklarından oluşan hazırlanmış verilerin mükemmel bir örneğidir.

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- Power Query [Sorguyu kaynağa döndürme](/power-query/power-query-folding) kavramı makalesi
- [Power BI Premium’da artımlı yenileme](../service-premium-incremental-refresh.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
