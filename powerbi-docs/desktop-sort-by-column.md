---
title: Power BI Desktop'ta sütuna göre sıralama
description: Power BI Desktop'ta sütuna göre sıralama
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 42bd263f09acb8739830ac6e2280e7d5d0f86228
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34482096"
---
# <a name="sort-by-column-in-power-bi-desktop"></a>Power BI Desktop'ta sütuna göre sıralama
**Power BI Desktop** uygulamasında ve **Power BI hizmetinde** farklı veri alanlarına göre sıralayarak bir görselin görüntülenme şeklini değiştirebilirsiniz. Görseli sıralama ölçütünü değiştirerek iletmek istediğiniz bilgileri vurgulayabilir ve görselin bu eğilimi yansıtmasını (veya vurgulamasını) sağlayabilirsiniz.

İster sayısal veriler (satış rakamları gibi) ister metin verileri (eyalet adları gibi) kullanıyor olun, görselleştirmelerinizi istediğiniz şekilde sıralayabilir ve istediğiniz gibi görünmelerini sağlayabilirsiniz.  **Power BI** sıralama için kullanabileceğiniz birçok seçenek ve hızlı menüler sunmaktadır. Aşağıdaki görüntüde verilen şekilde istediğiniz görselde üç nokta menüsünü (...) seçip sıralama için kullanmak istediğiniz alanı seçebilirsiniz.

![Diğer seçenekler menüsü](media/desktop-sort-by-column/sortbycolumn_2.png)

## <a name="more-depth-and-an-example"></a>Daha ayrıntılı bir örnek
Şimdi daha ayrıntılı bir örneği ele alalım ve **Power BI Desktop**'ta nasıl çalıştığına bakalım.

Aşağıdaki görselleştirmede üretici adına göre maliyetler, miktarlar ve tutarlar gösterilmiştir. Daha ayrıntılı sıralama yapmadan önce görselleştirme aşağıdaki şekilde görünür.

![İlk görselleştirme](media/desktop-sort-by-column/sortbycolumn_1.png)

Görsel şu anda **SalesQuantity** ölçütüne göre sıralanmış ve bunu artan çubukların rengine açıklamadan bakarak anlayabiliyoruz. Ancak, geçerli sıralama sütununu belirlemenin daha kolay bir yöntemi var, o da görselin sağ üst köşesindeki üç nokta menüsü (...). Üç noktayı seçtiğimizde aşağıdaki seçenekleri görüyoruz:

![Diğer seçenekler menüsü](media/desktop-sort-by-column/sortbycolumn_2.png)

* Geçerli sıralama alanı **SalesQuantity**’dir ve **SalesQuantity’ye Göre Sırala** alanının kalın yazı tipinde olması ve sarı bir çubuk içermesi ile gösterilir. 

* Geçerli sıralama yönü, küçük simge **A/Z** (A, Z’den önce) ve aşağı ok ile gösterildiği gibi en küçükten en büyüğe şeklindedir.

Sonraki iki bölümde sıralama alanına ve yönüne birbirinden bağımsız olarak bakacağız.

## <a name="selecting-which-column-to-use-for-sorting"></a>Sıralama için kullanılacak sütunu seçme
**Diğer Seçenekler** menüsündeki **Sort By SalesQuantity** seçeneğinin yanında bulunan ve görselin **SalesQuantity** sütunu tarafından sıralandığını gösteren sarı çubuğu fark ettiniz. Başka bir sütuna göre sıralama yapmak oldukça kolaydır. Tek yapmanız gereken üç noktayı seçerek üç nokta menüsünü açmak ve ardından başka bir sütun seçmektir.

Aşağıdaki görüntüde sıralama sütunu olarak *DiscountAmount* sütununu seçtik. Bu sütun, görseldeki çubuklardan değil, çizgilerden biri. **Sort By DiscountAmount** sütununu seçtikten sonra görsel aşağıdaki şekilde görüntülenir.

![Sort by DiscoutAmount](media/desktop-sort-by-column/sortbycolumn_3.png)

Görselin nasıl değiştiğine dikkat edin. Değerler artık bu görsel Fabrikam Inc. şirketindeki en yüksek DiscountAmount değerinden en düşük değere sahip Northwind Traders şirketine doğru sıralanır. 

Peki azalan yerine artan düzende sıralamak istiyorsak ne yapmamız gerekir? Bunun ne kadar kolay olduğunu bir sonraki bölümde görebilirsiniz.

## <a name="selecting-the-sort-order---smallest-to-largest-largest-to-smallest"></a>Sıralama düzenini seçme: en küçükten en büyüğe, en büyükten en küçüğe
Önceki görüntüde bulunan **Seçenekler** menüsüne yakından baktığımızda **Sort by DiscountAmount** menüsünün yanındaki simgede **Z/A** (Z, A'nın üzerinde) simgesinin olduğunu görebiliriz. Göz atın:

![En büyükten en küçüğe sıralama](media/desktop-sort-by-column/sortbycolumn_4.png)

**Z/A** görüntülendiğinde görsel seçilen sütundaki en büyük değerden en küçük değere göre sıralama gerçekleştirir. Bunu değiştirmek mi istiyorsunuz? Hiç sorun değil. Tek yapmanız gereken **Z/A** simgesine dokunmak veya tıklamaktır. Bunu yaptığınızda görselin sıralaması **A/Z** olarak değişir (seçilen sütuna göre) ve en küçükten en büyük değere doğru sıralama yapılır.

Burada aynı görselin **Sort By DiscountAmount** menüsündeki **Z/A** simgesine dokunularak sıralamasının değiştirilmiş halini görüyorsunuz. Northwind Traders şirketinin şu anda listedeki ilk üretici, Fabrikam Inc. şirketinin ise son üretici (önceki sıralamanın tersi) olduğuna dikkat edin.

![En küçükten en büyüğe sırala](media/desktop-sort-by-column/sortbycolumn_5.png)

Görselde yer alan herhangi bir sütuna göre sıralama yapabilirsiniz. Sıralama sütunu olarak, SalesQuantity sıralama ölçütünü **Sort By SalesQuantity** ile birlikte kolayca seçerek en çok satışı yapan üreticileri ilk önce gösterebilir ve ilgili üreticiye nasıl uygulandıklarına bakılmaksızın görseldeki diğer sütunları tutabilirsiniz. Bu ayarların uygulandığı görseli aşağıda görebilirsiniz.

![Sort by SalesQuantity](media/desktop-sort-by-column/sortbycolumn_6.png)

## <a name="sort-using-the-sort-by-column-button"></a>Sütuna Göre Sırala düğmesiyle sıralama
Verilerinizi sıralamak için kullanabileceğiniz bir diğer yöntem de **Modelleme** şeridindeki **Sütuna Göre Sırala** düğmesidir.

![Sütuna Göre Sırala düğmesi](media/desktop-sort-by-column/sortbycolumn_8.png)

Bu işlevi kullanmak için **Alanlar** bölmesinden bir sütun seçmeniz ve ardından görselin nasıl (hangi sütuna göre) sıralanacağını belirlemek için **Sütuna Göre Sırala** düğmesini seçmeniz gerekir. **Sütuna Göre Sırala** düğmesini etkinleştirmek için sıralamada kullanmak istediğiniz sütunu (alanı) **Alanlar** bölmesinden seçmeniz gerekir. Aksi halde düğme devre dışı olacaktır.

Sık kullanılan örneklerden birine göz atalım: Yılın aylarına ait verileriniz var ve bunları kronolojik olarak sıralamak istiyorsunuz. Aşağıdaki adımlarda bunu nasıl yapacağınız gösterilmektedir.

1. Öncelikle görselin seçili olduğuna ancak **Alanlar** bölmesinde bir sütun seçimi yapılmadığı için **Sütuna Göre Sırala** düğmesinin devre dışı (gri renkte) olduğuna dikkat edin.
   
   ![Etkin olmayan Sütuna Göre Sırala düğmesi](media/desktop-sort-by-column/sortbycolumn_9.png)

2. Sıralamada kullanmak istediğimiz sütunu **Alanlar** bölmesinden seçtikten sonra **Sütuna Göre Sırala** düğmesi etkin hale gelir.
   
   ![Etkin Sütuna Göre Sırala düğmesi](media/desktop-sort-by-column/sortbycolumn_10.png)
3. Şimdi görsel seçili durumdayken *MonthOfYear* sütununu (varsayılan *MonthName* sütunu yerine) seçtiğimizde görsel istediğimiz şekilde yılın aylarına göre sıralanır.
   
   ![Sütuna Göre Sırala menüsü](media/desktop-sort-by-column/sortbycolumn_11.png)

İşte bu kadar. **Alanlar** bölmesinden bir sütun seçmezseniz **Sütuna Göre Sırala** düğmesinin etkin hale gelmeyeceğini unutmayın.

## <a name="getting-back-to-default-column-for-sorting"></a>Varsayılan sıralama sütununa dönme
Sıralama için istediğiniz sütunu kullanabilirsiniz ancak bazen görselin varsayılan sıralama sütununa dönmesini isteyebilirsiniz. Hiç sorun değil. Sıralama sütunu seçilmiş bir görselde (önceki bölümlerde öğrendiğimiz gibi üç nokta menüsünde sıralama sütununun yanında sarı çubuk bulunur) **Diğer Seçenekler** menüsünü açıp varsayılan sütunu tekrar seçerek görselleştirmenin varsayılan sıralama sütununa dönmesini sağlayabilirsiniz.

Örneğin, önceki grafiğimiz şu şekilde görünür:

![İlk görselleştirme](media/desktop-sort-by-column/sortbycolumn_6.png)

Menüye gidip **SalesQuantity** sütununu yeniden seçtiğimizde görsel aşağıdaki görüntüde olduğu gibi **Manufacturer** sütununa göre alfabetik şekilde sıralanır.

![Varsayılan sıralama düzeni](media/desktop-sort-by-column/sortbycolumn_7.png)

Görsellerinizi sıralamak için kullanabileceğiniz seçenekler sayesinde istediğiniz grafiği veya görüntüyü oluşturmak oldukça kolaydır.

