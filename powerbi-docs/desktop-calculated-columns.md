---
title: Power BI Desktop'taki hesaplanmış sütunları kullanma
description: Power BI Desktop'taki hesaplanmış sütunlar
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 10c6f9f512c1b8c837842247d9dc928e8e065451
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73876626"
---
# <a name="using-calculated-columns-in-power-bi-desktop"></a>Power BI Desktop'taki hesaplanmış sütunları kullanma
Hesaplanmış sütunları kullanarak modelinizdeki tablolara yeni veriler ekleyebilirsiniz. Ancak bir veri kaynağından yeni sütununuza değer sorgulamak ve yüklemek yerine sütunun değerlerini tanımlayan bir Veri Çözümleme İfadeleri (DAX) formülü oluşturursunuz. Power BI Desktop'ta hesaplanmış sütunları oluşturmak için Rapor Görünümündeki Yeni Sütun özelliğini kullanabilirsiniz.

Sorgu Düzenleyicisi'ndeki Özel Sütun Ekle işlevini kullanarak bir sorgunun parçası olarak oluşturulan özel sütunlardan farklı olarak Rapor Görünümü veya Veri Görünümünde oluşturulan hesaplanmış sütunlar, modele önceden yüklemiş olduğunuz verileri temel alır. Örneğin, birbiriyle ilişkili iki farklı tabloda bulunan iki farklı sütundaki değerleri birleştirebilir, ekleme veya alt dizeleri ayıklama işlemi gerçekleştirebilirsiniz.

Oluşturduğunuz hesaplanmış sütunlar, Alanlar listesinde diğer alanlar gibi görüntülenir ancak değerlerinin bir formülün sonucu olduğunu gösteren özel bir simge kullanılır. Sütunlara istediğiniz adı verip diğer alanlar gibi rapor görselleştirmelerine ekleyebilirsiniz.

![](media/desktop-calculated-columns/calccolinpbid_fields.png)

Hesaplanmış sütunlar sonuçları hesaplamak için Power BI Desktop'takiler gibi ilişkisel verilerle çalışmak üzere tasarlanmış bir formül dili olan [Veri Çözümleme İfadeleri](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) formüllerini kullanır. DAX, sahip olduğu 200'den fazla işlev, işleç ve yapı ile her türlü veri çözümleme ihtiyacını karşılayacak sonuçları hesaplayan formüller oluşturma konusunda yüksek düzeyli esneklik sunar. DAX hakkında daha fazla bilgi edinmek için bu makalenin sonundaki daha fazla bilgi bölümüne göz atın.

DAX formülleri Excel formülleriyle benzerdir. Hatta DAX, Excel'deki formüllerin çoğuna sahiptir. Ancak DAX işlevleri, Power BI Desktop'ta olduğu gibi etkileşimli olarak dilimlenmiş veya filtrelenmiş rapor verileriyle birlikte çalışacak şekilde tasarlanmıştır. Bir tablodaki her satır için ayrı bir formül kullanabildiğiniz Excel'den farklı olarak yeni bir sütun için bir DAX formülü oluşturduğunuzda tablodaki tüm satırlar için hesaplama gerçekleştirilir. Sütun değerleri bağlı olduğu veriler ve değerler değiştirildiğinde yeniden hesaplanır.

## <a name="lets-look-at-an-example"></a>Bir örneğe göz atalım
Contoso’da sevkiyat müdürü olan Jeff, farklı şehirlere gönderilen paketlerin sayısını gösteren bir rapor oluşturmak istemektedir. Jeff, şehir ve eyaletler için ayrı alanları bulunan Geography adlı bir tabloya sahiptir. Ancak Jeff, raporlarında Şehir, Eyalet bilgilerinin aynı satırda tek bir değer halinde gösterilmesini istemektedir. Jeff'in mevcut Geography tablosunda istediği gibi bir alan mevcut değildir.

![](media/desktop-calculated-columns/calccolinpbid_cityandstatefields.png)

Ancak Jeff, hesaplanmış sütun kullanarak City sütunundaki şehirleri State sütunundaki eyaletlerle bir araya getirebilir.

Jeff, Geography tablosuna sağ tıklayıp Yeni Sütun'u seçer. Bunun ardından, Jeff formül çubuğuna aşağıdaki DAX formülünü girer:

![](media/desktop-calculated-columns/calccolinpbid_formula.png)

Bu formül CityState adlı yeni bir sütun oluşturup Geography tablosundaki her satır için City sütunundaki değerleri alır, bir virgül koyar ve State sütunundaki değerleri yerleştirir.

Jeff artık istediği alana sahiptir.

![](media/desktop-calculated-columns/calccolinpbid_citystatefield.png)

Jeff, sevkiyatların sayısıyla birlikte artık bunu rapor tuvaline ekleyebilir. Çok hızlı bir şekilde ve en az çaba ile Jeff’in artık, neredeyse tüm görselleştirme türlerine eklenebilen bir City, State alanı var. Jeff, harita görselleştirmesi oluşturulduğunda Power BI Desktop'ın yeni sütunundaki City, State değerlerinin nasıl okuması gerektiğini bildiğini de görüyor.

![](media/desktop-calculated-columns/calccolinpbid_citystatemap.png)

## <a name="learn-more"></a>Daha fazla bilgi
Burada hesaplanmış sütunlara yalnızca kısa bir giriş yaptık. Ayrıntılı bilgi için, örnek bir dosya indirip daha fazla sütun oluşturma konusundaki adım adım yönergeleri uygulayabileceğiniz [Öğretici: Power BI Desktop'ta hesaplanmış sütunlar oluşturma](desktop-tutorial-create-calculated-columns.md) adlı öğreticiyi inceleyebilirsiniz. 

DAX hakkında daha fazla bilgi için bkz. [Power BI Desktop'ta DAX kullanımıyla ilgili temel bilgiler](desktop-quickstart-learn-dax-basics.md).

Sorguların parçası olarak oluşturduğunuz sütunlar hakkında daha fazla bilgi için [Power BI Desktop'taki genel sorgu görevleri](desktop-common-query-tasks.md) makalesinin Özel sütun oluşturma bölümünü inceleyin.  

