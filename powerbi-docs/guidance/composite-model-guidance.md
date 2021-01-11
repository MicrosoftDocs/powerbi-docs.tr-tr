---
title: Power BI Desktop’ta Bileşik model kılavuzu
description: Bileşik modelleri geliştirme kılavuzu.
author: peter-myers
ms.author: v-pemyer
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 12/24/2019
ms.openlocfilehash: e4ddc487f81835edfdc5ad8a4074a91204ee0336
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97884798"
---
# <a name="composite-model-guidance-in-power-bi-desktop"></a>Power BI Desktop’ta Bileşik model kılavuzu

Bu makale Power BI Bileşik modelleri geliştiren veri modelleyicilerine yöneliktir. Bileşik model kullanım örneklerini açıklar ve size tasarım yönergeleri sağlar. Bu yönergeler özel olarak Bileşik modelin çözümünüze uygun olup olmadığını saptamanıza yardımcı olmak için hazırlanmıştır. Uygunsa, bu makale en iyi modeli tasarlamanıza da yardımcı olacaktır.

> [!NOTE]
> Bileşik modellere giriş konusu bu makalenin kapsamı dışındadır. Bileşik modelleri tam olarak bilmiyorsanız önce [Power BI Desktop’ta bileşik modelleri kullanma](../transform-model/desktop-composite-models.md) makalesini okumanızı öneririz.
>
> Bileşik modeller en az bir DirectQuery kaynağından oluştuğu için [model ilişkilerini](../transform-model/desktop-relationships-understand.md), [DirectQuery modellerini](../connect-data/desktop-directquery-about.md) ve [DirectQuery modeli tasarım yönergelerini](directquery-model-guidance.md) de her yönüyle anlamanız önemlidir.

## <a name="composite-model-use-cases"></a>Bileşik model kullanım örnekleri

Mümkünse, en iyisi modeli İçeri Aktarma modunda geliştirmektir. En fazla tasarım esnekliği ve en iyi performansı bu mod sağlar.

Öte yandan büyük hacimli verilerin veya gerçek zamanlıya yakın verileri raporlamanın getirdiği güçlükler İçeri Aktarma modelleriyle çözülemez. Bu iki durumda da, verilerinizin [DirectQuery modunda desteklenen](../connect-data/power-bi-data-sources.md) tek bir veri kaynağında depolanması koşuluyla DirectQuery modelini göz önüne alabilirsiniz.

Ayrıca aşağıdaki durumlarda Bileşik model geliştirmeyi de düşünebilirsiniz.

- Modeliniz bir DirectQuery modeli olabilir ama performansı artırmak istiyorsunuz. Bileşik modelde, her tablo için uygun depolamanın yapılandırılması yoluyla performans geliştirilebilir. Ayrıca [toplamalar](../transform-model/desktop-aggregations.md) da ekleyebilirsiniz. Bu iyileştirmelerin ikisi de bu makalenin devamında açıklanmaktadır.
- DirectQuery modelini, modele aktarılması gereken ek verilerle birleştirmek istiyorsunuz. İçeri aktarılan veriler farklı bir veri kaynağından veya hesaplanmış tablolardan yükleniyor olabilir.
- İki veya daha çok DirectQuery veri kaynağını tek modelde birleştirmek istiyorsunuz.

> [!NOTE]
> Bileşik modeller Canlı Bağlantı kaynaklarını veya DirectQuery analitik veritabanı kaynaklarını birleştiremez. Canlı Bağlantı kaynakları [harici olarak barındırılan modeller](../connect-data/service-datasets-understand.md#external-hosted-models) ve Power BI veri kümeleridir. DirectQuery analitik veritabanı kaynakları SAP Business Warehouse ve SAP HANA’dır.

## <a name="optimize-model-design"></a>Model tasarımını iyileştirme

Bileşik model, tablo [depolama modları](../transform-model/desktop-storage-mode.md) yapılandırılarak ve [toplamalar](../transform-model/desktop-aggregations.md) eklenerek iyileştirilebilir.

### <a name="table-storage-mode"></a>Tablo depolama modu

Bileşik modelde her tablo için depolama modunu yapılandırabilirsiniz (hesaplanmış tablolar dışında):

- **DirectQuery**: Büyük hacimli verileri temsil eden veya gerçek zamanlıya yakın sonuçlar vermesi gereken tablolar için bu modu ayarlamanızı öneririz. Veriler hiçbir zaman bu tablolara içeri aktarılmayacaktır. Genellikle bu tablolar olgu türünde, özetleme için kullanılan tablolar olacaktır.
- **İçeri Aktarma**: Filtreleme ve gruplandırma için kullanılan, boyut türündeki tablolar için bu modu ayarlamanızı öneririz. Aslında DirectQuery modunda desteklenmeyen kaynaklara dayalı tablolar için tek seçenek budur. Hesaplanmış tablolar her zaman İçeri Aktarma tablolarıdır.
- **İkili**: Aynı kaynaktan DirectQuery olgu türündeki tablolarıyla birlikte sorgulanma olasılıkları olduğunda, boyut türündeki tablolar için bu modu ayarlamanızı öneririz.

Power BI’ın Bileşik modeli sorguladığı çeşitli olası senaryolar vardır:

- **Yalnızca İçeri Aktarma tablolarını veya İkili tabloları sorgular**: Tüm veriler model önbelleğinden veriler alınır. Mümkün olan en hızlı performansı getirir. Bu senaryo, filtreler veya dilimleyici görselleri tarafından sorgulanan boyut türündeki tablolarda yaygındır.
- **Aynı kaynaktan İkili tabloları veya DirectQuery tablolarını sorgular**: Tüm veriler DirectQuery kaynağına bir veya birden çok yerel sorgu gönderilerek alınır. Özellikle kaynak tablolarda uygun dizinler mevcut olduğunda mümkün olan en hızlı performansı getirir. Bu senaryo, İkili boyut türündeki tablolarla ve DirectQuery olgu türündeki tablolarıyla ilgili sorgularda yaygındır. Bu sorgular _kaynak grubu içinde_ çalıştırılır, bu nedenle birebir veya bire çok ilişkilerin tümü [normal ilişkiler](../transform-model/desktop-relationships-understand.md#regular-relationships) olarak değerlendirilir.
- **Tüm diğer sorgular**: Bu sorgular kaynak grupları arasında ilişkileri içerir. Bunun nedeni İçeri Aktarma tablosunun bir DirectQuery tablosuyla ilgili olması veya İkili tablonun farklı kaynaktan bir DirectQuery tablosuyla ilgili olmasıdır (bu durumda İçeri Aktarma tablosu gibi davranır). Tüm ilişkiler [sınırlı ilişki](../transform-model/desktop-relationships-understand.md#limited-relationships) olarak değerlendirilir. Ayrıca DirectQuery olmayan tablolara uygulanan gruplandırmaların DirectQuery kaynağına sanal tablo olarak gönderilmesi gerektiği anlamına da gelir. Bu durumda yerel sorgu, özellikle de büyük gruplandırma kümeleri için verimsiz olabilir. Ayrıca yerel sorguda hassas verileri ortaya çıkarma olasılığı vardır.

Özetle şunları yapmanızı öneririz:

- Bileşik modelin doğru çözüm olup olmadığını dikkatle düşünün; farklı veri kaynaklarını model düzeyinde tümleştirmeye olanak tanır ama sonuçları olabilecek tasarım karmaşıklıkları da getirir
- Tablo büyük hacimli verilerin depolandığı olgu türünde bir tablo olduğunda depolama modunu **DirectQuery** olarak ayarlayın
- Tablo boyut türünde bir tablo olduğunda depolama modunu **İkili** olarak ayarlayın; aynı kaynak temelinde **DirectQuery** olgu türündeki tablolarıyla birlikte sorgulanacaktır
- İkili tabloların (ve tüm bağımlı hesaplanmış tabloların) model önbelleğini kaynak veritabanlarıyla eşitlenmiş durumda tutmak için uygun yenileme sıklıkları yapılandırın
- Veri kaynakları arasında (model önbelleği dahil) veri bütünlüğünü korumaya çalışın. Sınırlı ilişkiler, ilgili sütun değerleri eşleşmediğinde satırları ortadan kaldırır
- Verimli birleştirme, filtreleme ve gruplandırma işlemleri için uygun dizinlerle DirectQuery veri kaynaklarını iyileştirin
- Yerel sorguda araya girilme riski varsa İçeri Aktarma veya İkili tablolara hassas verileri yüklemeyin; daha fazla bilgi için bkz. [Power BI Desktop’ta bileşik modelleri kullanma (Güvenlik üzerindeki etkileri)](../transform-model/desktop-composite-models.md#security-implications)

### <a name="aggregations"></a>Toplamalar

Bileşik modelinizde DirectQuery tablolarına toplamalar ekleyebilirsiniz. Toplamalar modelde önbelleğe alınır ve dolayısıyla İçeri Aktarma tabloları gibi davranır (ama bir model tablosu gibi kullanılamazlar). Amaçları “daha ayrıntılı” sorguların performansını geliştirmektir. Daha fazla bilgi için bkz. [Power BI Desktop'taki Toplamalar](../transform-model/desktop-aggregations.md).

Toplama tablosunda temel bir kurala uyulmasını öneririz: Satır sayısı, en fazla temel tablonun 10’da biri kadar olmalıdır. Örneğin temel tabloda 1 milyar satır depolanıyorsa, toplama tablosu 100 milyon satırı aşmamalıdır. Bu kural toplama tablosunu oluşturma ve koruma maliyetine göre uygun bir performans kazanımı elde edilmesini sağlar.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Desktop’ta bileşik modeller kullanma](../transform-model/desktop-composite-models.md)
- [Power BI Desktop’ta model ilişkileri](../transform-model/desktop-relationships-understand.md)
- [Power BI Desktop’ta DirectQuery modelleri](../connect-data/desktop-directquery-about.md)
- [Power BI Desktop'ta DirectQuery'yi kullanma](../connect-data/desktop-use-directquery.md)
- [Power BI Desktop’ta DirectQuery modeli sorunlarını giderme](../connect-data/desktop-directquery-troubleshoot.md)
- [Power BI veri kaynakları](../connect-data/power-bi-data-sources.md)
- [Power BI Desktop’ta depolama Modu](../transform-model/desktop-storage-mode.md)
- [Power BI Desktop’ta toplamalar](../transform-model/desktop-aggregations.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)
