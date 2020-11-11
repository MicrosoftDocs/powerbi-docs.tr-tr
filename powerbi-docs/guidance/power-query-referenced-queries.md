---
title: Power Query sorgularına başvurma
description: Power Query sorgularına başvurma kılavuzu.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/30/2019
ms.author: v-pemyer
ms.openlocfilehash: 9e3ae90363ade08d7600a4ebbd032ef5778257e2
ms.sourcegitcommit: 37bd34053557089c4fbf0e05f78e959609966561
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94397013"
---
# <a name="referencing-power-query-queries"></a>Power Query sorgularına başvurma

Bu makale, Power BI Desktop'la çalışan veri modelleyicilerine yöneliktir. Diğer sorgulara başvuran Power Query sorguları tanımlarken size rehberlik sağlar.

Bunun anlamını netleştirelim: _Sorgu ikinci bir sorguya başvurduğunda, ikinci sorgudaki adımlar birinci sorgunun adımlarıyla birleştirilmiş gibi olur ve birinci sorgunun adımlarından önce çalıştırılır._

Çeşitli sorguları düşünün: **Query1** veri kaynağı olarak bir web hizmetini kullanır ve yükü devre dışı bırakılır. **Query2** , **Query3** ve **Query4** 'ün hepsi **Query1** 'e başvurur ve çıkışları veri modeline yüklenir.

![Önceki paragrafta açıklanan sorguların görüntülendiği Sorgu Bağımlılıkları görünümünü gösteren diyagram.](media/power-query-referenced-queries/query-dependencies-web-service.png)

Veri modeli yenilendiğinde genellikle Power Query'nin **Query1** sonucunu aldığı ve bunun başvurulan sorgular tarafından yeniden kullanıldığı varsayılır. Bu yanlış bir varsayımdır. Aslında Power Query **Query2** , **Query3** ve **Query4** 'ü ayrı ayrı yürütür.

**Query2** 'nin içinde **Query1** adımlarının eklendiğini düşünebilirsiniz. **Query3** ve **Query4** için de aynı durum geçerlidir. Aşağıdaki diyagramda sorguların nasıl yürütüldüğü daha net gösterilmiştir.

![Sorgu Bağımlılıkları görünümünün Query 2, Query 3 ve Query 4’ü görüntülediği değiştirilmiş sürümünü gösteren diyagram.](media/power-query-referenced-queries/query-dependencies-web-service-concept.png)

**Query1** üç kez yürütülür. Birden çok yürütme, veri yenilemenin yavaşlaması sonucunu verir ve veri kaynağını olumsuz etkiler.

**Query1** 'de [Table.Buffer](/powerquery-m/table-buffer) işlevinin kullanılması ek veri alımını ortadan kaldırmaz. Bu işlev bir tabloyu arabelleğe alır. Arabelleğe alınmış tablo da yalnızca ayrı sorgu yürütmesinde kullanılabilir. Dolayısıyla örnekte **Query2** yürütülürken **Query1** arabelleğe alınırsa, arabelleğe alınan veriler **Query3** ve **Query4** yürütülürken kullanılamaz. Bunlar da verileri iki kez daha arabelleğe alır. (Bu sonuç aslında performans üzerindeki olumsuz etkiyi artırır çünkü başvuruda bulunan her sorgu tabloyu arabelleğe alacaktır.)

> [!NOTE]
> Power Query önbellek mimarisi karmaşıktır ve bu makalenin konusu değildir. Power Query bir veri kaynağından alınan verileri önbelleğe alabilir. Öte yandan sorguyu yürütürken veri kaynağından verileri birden çok kez alabilir.

## <a name="recommendations"></a>Öneriler

Genel olarak sorgulara başvururken sorgular arasında mantığın yinelenmesinden kaçınmanızı öneririz. Bununla birlikte, bu makalede açıklandığı gibi bu tasarım yaklaşımı veri yenilemelerinin yavaşlamasına katkıda bulunabilir ve veri kaynaklarına fazla yük getirebilir.

Bunun yerine [veri akışı](../transform-model/dataflows/dataflows-introduction-self-service.md) oluşturmanızı öneririz. Veri akışının kullanılması veri yenileme süresini geliştirebilir ve veri kaynaklarınız üzerindeki etkiyi azaltabilir.

Veri akışını, kaynak verileri ve dönüştürmeleri kapsülleyecek şekilde tasarlayabilirsiniz. Veri akışı Power BI hizmetinde kalıcı bir veri deposu olduğundan, veri alma işlemi hızlı olur. Dolayısıyla sorgulara başvurular veri akışı için birden çok istekle sonuçlansa bile veri yenileme süreleri gelişebilir.

Örnekte, **Query1** bir veri akışı varlığı olarak yeniden tasarlanırsa **Query2** , **Query3** ve **Query4** bunu veri kaynağı olarak kullanabilir. Bu tasarımla, **Query1** 'in kaynağı olan varlık tek bir kez değerlendirilir.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI’da self servis veri hazırlığı](../transform-model/dataflows/dataflows-introduction-self-service.md)
- [Power BI'da veri akışlarını oluşturma ve kullanma](../transform-model/dataflows/dataflows-create.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)