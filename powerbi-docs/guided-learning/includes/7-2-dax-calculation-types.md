---
ms.openlocfilehash: 0296512b59baf828dd284088e0109af819aee261
ms.sourcegitcommit: 66b1a0c74b8a7dcb33a2f8570fb67bce2401a895
ms.contentlocale: tr-TR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84562084"
---
DAX kullanarak oluşturabileceğiniz iki temel hesaplama vardır:

* **hesaplanmış sütunlar**
* **ölçüler**

Bunlardan birinin oluşturulmasına ilişkin ayrıntılara girmeden önce, tablolar ve sütunlar için **hesaplanmış sütunlar** veya **ölçüler** oluştururken kullanacağınız DAX söz dizimi hakkında yeterli düzeyde bilgi sahibi olmanız faydalı olacaktır.

## <a name="dax-table-and-column-name-syntax"></a>DAX tablo ve sütun adı söz dizimi
İster yeni bir sütun ister ölçü oluşturuyor olun DAX'taki tablo adlarının genel biçimini bilmeniz önemlidir:

    'Table Name'[ColumnName]

Tablo adında (yukarıda gösterildiği gibi) boşluklar varsa tablo adının başındaki ve sonundaki tek tırnaklar zorunludur. Tablo adında boşluk yoksa tek tırnaklar çıkarılabilir, böylece söz dizimi aşağıdaki gibi görünür:

    TableName[ColumnName]

Aşağıdaki görüntüde, Power BI'da oluşturulmakta olan bir DAX formülü bulunmaktadır:

![](media/7-2-dax-calculation-types/dax-calc-types_1.png)

Ayrıca tablo adını tamamen çıkarıp yalnızca sütun adını da kullanabilirsiniz ancak bu, net işlevlerin (ve sonuç olarak net bir DAX kodunun) yazılması açısından en uygun yöntem değildir. Sütun adları her zaman köşeli ayraç içermelidir.

En iyi sonuçları almak için aşağıdaki yöntemlerin *her zaman* uygulanması gerekir:

* Tablo adlarına boşluk koymama
* Tablo adını formüllere her zaman ekleme (DAX, tablo adını çıkarmanıza olanak sağlasa bile)

## <a name="creating-calculated-columns"></a>Hesaplanmış sütun oluşturma
**Hesaplanmış sütunlar**, değer üzerinde dilimleme veya filtreleme yapmak istediğinizde ya da tablonuzdaki her satır için hesaplamaya ihtiyaç duymanız durumunda fayda sağlar.

Power BI Desktop'ta, **Modelleme** sekmesinden **Yeni Sütun**'u seçerek, hesaplanmış sütunlar oluşturabilirsiniz. Yeni sütunun oluşturulduğunu görebileceğiniz ve **Formül Çubuğu**'nun doldurulup DAX formülünüz için hazır hale geleceği **Veri** görünümünde (**Rapor** veya **İlişkiler** görünümü yerine) olmanız önerilir.

![](media/7-2-dax-calculation-types/dax-calc-types_2a.png)

**Yeni Sütun** düğmesini seçmenizin ardından **Formül Çubuğu**, basit bir sütun adıyla (formülünüze uyacak şekilde değiştirebilirsiniz) ve **=** işleciyle doldurulur ve yeni sütun, veri kılavuzunda aşağıdaki resimde gösterildiği gibi görünür.

![](media/7-2-dax-calculation-types/dax-calc-types_3.png)

Hesaplanmış bir sütun için gerekli öğeler şunlardır:

* yeni bir sütun adı
* en az bir işlev veya ifade

Hesaplanmış sütun formülünüzde bir tabloya veya sütuna başvuruyorsanız tabloda bir satırı belirtmeniz gerekmez; Power BI her hesaplama için geçerli satıra ilişkin sütunu hesaplar.

## <a name="creating-measures"></a>Ölçü oluşturma
Yüzde veya oran hesaplıyorsanız ya da karmaşık toplamalar gerçekleştirmeniz gerekiyorsa **ölçü** kullanın. DAX formülü kullanarak ölçü oluşturmak için **Modelleme** sekmesinden **Yeni Ölçü** düğmesini seçin. Tekrar belirtmek gerekirse, **Formül Çubuğu**'nu gösterdiğinden ve DAX formülünüzü yazmayı kolaylaştırdığından Power BI Desktop'ın **Veri** görünümünde olmak en iyisidir.

![](media/7-2-dax-calculation-types/dax-calc-types_4.png)

**Ölçüleri** kullandığınızda **Alanlar** bölmesinde ölçünün adıyla yeni bir ölçü simgesinin göründüğünü fark edersiniz. **Formül Çubuğu** tekrar DAX formülünüzün adıyla (bu kez ölçünüzle birlikte) doldurulur.

![](media/7-2-dax-calculation-types/dax-calc-types_5.png)

Ölçüler ve hesaplanmış sütunlar için gerekli öğeler aynıdır:

* yeni bir ölçü adı
* en az bir işlev veya ifade

> Video içeriğini sağladığı için [SQLBI'dan Alberto Ferrari](https://www.sqlbi.com/learning-dax)'ye teşekkür ederiz
> 
> 

