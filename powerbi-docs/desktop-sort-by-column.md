---
title: Power BI Desktop'ta sütuna göre sıralama
description: Power BI Desktop'ta sütuna göre sıralama
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 33848bcec8601a4df1ed7ae80bcbfd76fcebe553
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="sort-by-column-in-power-bi-desktop"></a>Power BI Desktop'ta sütuna göre sıralama
**Power BI Desktop** uygulamasında ve **Power BI hizmetinde** farklı veri alanlarına göre sıralayarak bir görselin görüntülenme şeklini değiştirebilirsiniz. Görseli sıralama ölçütünü değiştirerek iletmek istediğiniz bilgileri vurgulayabilir ve görselin belirtmek istediğiniz eğilimi yansıtmasını (veya vurgulamasını) sağlayabilirsiniz.

İster sayısal veriler (satış rakamları gibi) ister metin verileri (eyalet adları gibi) kullanıyor olun, görselleştirmelerinizi dilediğiniz şekilde sıralayabilir ve istediğiniz gibi görünmelerini sağlayabilirsiniz.  **Power BI** sıralama için kullanabileceğiniz birçok seçenek ve hızlı menüler sunmaktadır. Aşağıdaki görüntüde verilen şekilde istediğiniz görselde üç nokta menüsünü (...) seçip **Sıralama Ölçütü**'nü belirledikten sonra sıralama için kullanmak istediğiniz alanı seçebilirsiniz.

![](media/desktop-sort-by-column/sortbycolumn_2.png)

## <a name="more-depth-and-an-example"></a>Daha ayrıntılı bir örnek
Şimdi daha ayrıntılı bir örneği ele alalım ve **Power BI Desktop**'ta nasıl çalıştığına bakalım.

Aşağıdaki görselleştirmede hava koşulları en iyi olan 15 eyalet gösterilmektedir (en çok güneşli gün sayısı, 1 ile 50 arası puanlama, 1 en fazla güneşli güne sahip olmak üzere). Sıralama yapmadan önce görselleştirme aşağıdaki şekilde görünüyor.

![](media/desktop-sort-by-column/sortbycolumn_1.png)

Görsel şu anda **Cost of living** ölçütüne göre sıralanmış ve bunu azalan çubukların rengine açıklamadan bakarak anlayabiliyoruz. Ancak, geçerli sıralama sütununu belirlemenin daha kolay bir yöntemi var, o da görselin sağ üst köşesindeki üç nokta menüsünden (...) ulaşabileceğiniz **Sıralama ölçütü** iletişim kutusu. Üç noktayı seçtiğimizde aşağıdaki seçenekleri görüyoruz:

![](media/desktop-sort-by-column/sortbycolumn_2.png)

Üç noktayı seçtiğinizde açılan menüde dikkat etmeniz gereken birkaç nokta var:

* **Cost of living** ölçütünün yanında sarı çubuk var ve **Cost of living** yazısı kalın
* **Sıralama Ölçütü**'nün yanındaki küçük simgede **Z/A** (Z, A'nın üzerinde) ve aşağı ok görünüyor.

Bu noktaları sonraki iki bölümde ayrıntılı olarak ele alacağız.

## <a name="selecting-which-column-to-use-for-sorting"></a>Sıralama için kullanılacak sütunu seçme
**Sıralama Ölçütü** menüsündeki **Cost of living** girişinin yanında sarı çubuk olduğunu ve bunun görselin sıralama için **Cost of living** sütununu kullandığını gösterdiğini fark ettiniz. Başka bir sütuna göre sıralama yapmak oldukça kolaydır. Tek yapmanız gereken üç noktayı seçerek **Sıralama ölçütü** menüsünü açmak ve ardından başka bir sütun seçmektir. İşte bu kadar kolay.

Aşağıdaki görüntüde sıralama sütunu olarak **Community well-being** sütununu seçtik. Bu sütun, görseldeki çubuklardan değil, çizgilerden biri. **Community well-being** sütununu seçtikten sonra görsel aşağıdaki şekilde görüntülenir.

![](media/desktop-sort-by-column/sortbycolumn_3.png)

Görselin nasıl değiştiğine dikkat edin. Değerler şimdi görselde bulunan eyaletler için en yüksek "Community well-being" değerinden (bu durumda RI - Rhode Island), en düşük değere sahip AZ (Arizona) girişine doğru sıralanmış durumdadır. Grafikte yine en çok güneşli güne sahip 15 eyaletin yer aldığını unutmayın. Tek yaptığımız görseli farklı bir sütuna göre sıralamak.

Peki azalan yerine artan düzende sıralamak istiyorsak ne yapmamız gerekir? Bunun ne kadar kolay olduğunu bir sonraki bölümde görebilirsiniz.

## <a name="selecting-the-sort-order---smallest-to-largest-largest-to-smallest"></a>Sıralama düzenini seçme: en küçükten en büyüğe, en büyükten en küçüğe
Önceki görüntüde bulunan **Sıralama Ölçütü** menüsüne yakından baktığımızda **Sıralama Ölçütü** menüsünün yanındaki simgede **Z/A** (Z, A'nın üzerinde) simgesinin olduğunu görebiliriz. Göz atın:

![](media/desktop-sort-by-column/sortbycolumn_4.png)

**Z/A** görüntülendiğinde görsel seçilen sütundaki en büyük değerden en küçük değere göre sıralama gerçekleştirir. Bunu değiştirmek mi istiyorsunuz? Hiç sorun değil. Tek yapmanız gereken **Z/A** simgesine dokunmak veya tıklamaktır. Bunu yaptığınızda görselin sıralaması **A/Z** olarak değişir (seçilen sütuna göre) ve en küçükten en büyük değere doğru sıralama yapılır.

Burada aynı görselin **Sıralama Ölçütü** menüsündeki **Z/A** simgesine dokunularak sıralamasının değiştirilmiş halini görüyorsunuz. Artık yukarıdaki sıralamanın tam tersine listedeki ilk eyaletin AZ (Arizona), son eyaletin de RI (Rhode Island) olduğunu görebilirsiniz.

![](media/desktop-sort-by-column/sortbycolumn_5.png)

Görseldeki herhangi bir sütuna göre sıralama yapabilirsiniz. Sıralama sütunu olarak Weather sütununu belirleyip **Sıralama Ölçütü** menüsünden **Z/A** simgesini seçerek en çok güneşli güne sahip olan eyaletleri (en yüksek değer - Weather, veri modelinde güneşli gün sayısını göstermektedir) gösterebilir ve görseldeki diğer sütunların aynı kalmasını sağlayabiliriz. Bu ayarların uygulandığı görseli aşağıda görebilirsiniz.

![](media/desktop-sort-by-column/sortbycolumn_6.png)

## <a name="sort-using-the-sort-by-column-button"></a>Sütuna Göre Sırala düğmesiyle sıralama
Verilerinizi sıralamak için kullanabileceğiniz bir diğer yöntem de **Modelleme** şeridindeki **Sütuna Göre Sırala** düğmesidir.

![](media/desktop-sort-by-column/sortbycolumn_8.png)

Bu işlevi kullanmak için **Alanlar** bölmesinden bir sütun seçmeniz ve ardından görselin nasıl (hangi sütuna göre) sıralanacağını belirlemek için **Sütuna Göre Sırala** düğmesini seçmeniz gerekir. **Sütuna Göre Sırala** düğmesini etkinleştirmek için sıralamada kullanmak istediğiniz sütunu (alanı) **Alanlar** bölmesinden seçmeniz gerekir. Aksi halde düğme devre dışı olacaktır.

Sık kullanılan örneklerden birine göz atalım: Haftanın günlerine ait verileriniz var ve bunları kronolojik olarak sıralamak istiyorsunuz. Aşağıdaki adımlarda bunu nasıl yapacağınız gösterilmektedir.

1. Öncelikle görselin seçili olduğuna ancak **Alanlar** bölmesinde bir sütun seçimi yapılmadığı için **Sütuna Göre Sırala** düğmesinin devre dışı (gri renkte) olduğuna dikkat edin.
   
   ![](media/desktop-sort-by-column/sortbycolumn_9a.png)
2. Sıralamada kullanmak istediğimiz sütunu **Alanlar** bölmesinden seçtikten sonra **Sütuna Göre Sırala** düğmesi etkin hale gelir.
   
   ![](media/desktop-sort-by-column/sortbycolumn_10.png)
3. Şimdi görsel seçili durumdayken *Day of Week* sütununu (varsayılan *Name of Day* sütunu yerine) seçtiğimizde görsel istediğimiz şekilde haftanın günlerine göre sıralanır.
   
   ![](media/desktop-sort-by-column/sortbycolumn_11.png)

İşte bu kadar. **Alanlar** bölmesinden bir sütun seçmezseniz **Sütuna Göre Sırala** düğmesinin etkin hale gelmeyeceğini unutmayın.

## <a name="getting-back-to-default-column-for-sorting"></a>Varsayılan sıralama sütununa dönme
Sıralama için istediğiniz sütunu kullanabilirsiniz ancak bazen görselin varsayılan sıralama sütununa dönmesini isteyebilirsiniz. Hiç sorun değil. Sıralama sütunu seçilmiş bir görselde (önceki bölümlerde öğrendiğimiz gibi **Sıralama Ölçütü** menüsünde sıralama sütununun yanında sarı çubuk bulunur) **Sıralama Ölçütü** menüsünü açıp varsayılan sütunu tekrar seçerek görselleştirmenin varsayılan sıralama sütununa dönmesini sağlayabilirsiniz.

Örneğin, önceki grafiğimiz şu şekilde görünür:

![](media/desktop-sort-by-column/sortbycolumn_6.png)

Menüye gidip **Weather** sütununu yeniden seçtiğimizde görsel aşağıdaki görüntüde olduğu gibi **State Code** sütununa göre alfabetik şekilde sıralanır.

![](media/desktop-sort-by-column/sortbycolumn_7.png)

Görsellerinizi sıralamak için kullanabileceğiniz seçenekler sayesinde istediğiniz grafiği veya görüntüyü oluşturmak oldukça kolaydır.

