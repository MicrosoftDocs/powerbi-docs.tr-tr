---
title: "Power BI Desktop'taki hesaplanan tabloları kullanma"
description: Power BI Desktop'taki hesaplanan tablolar
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: d8ec3de8fc60501f44a76e090d1d35f21fa75f2b
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="using-calculated-tables-in-power-bi-desktop"></a>Power BI Desktop'taki hesaplanan tabloları kullanma
Hesaplanan tabloları kullanarak modele yeni bir tablo ekleyebilirsiniz. Ancak, bir veri kaynağından yeni tablonuzun sütunlarına değer sorgulamak ve yüklemek yerine tablonun değerlerini tanımlayan bir Veri Çözümleme İfadeleri (DAX) formülü oluşturursunuz. Power BI Desktop'ta hesaplanan tabloları oluşturmak için Rapor Görünümü veya Veri Görünümündeki Yeni Tablo özelliğini kullanabilirsiniz.

Çoğu zaman modelinize dışarıdaki veri kaynaklarından veri aktarırsınız. Ancak hesaplanan tabloların sağladığı belirli avantajlar vardır. Hesaplanan tablolar genelde ara hesaplamalar için idealdir ve istediğiniz veriler anlık olarak hesaplanmak yerine modelin bir parçası veya sorgunun bir parçası olarak depolanır.

Sorgunun bir parçası olarak oluşturulan tablolardan farklı olarak Rapor Görünümü veya Veri Görünümünde oluşturulan hesaplanan tablolar, modele önceden yüklemiş olduğunuz verileri temel alır. Örneğin iki tabloyu birleştirmek veya çapraz şekilde bağlamak isteyebilirsiniz.

Normal tablolar gibi hesaplanan tablolar da diğer tablolarla ilişki kurabilir. Hesaplanan tablonuzun sütunlarında veri türleri ve biçimlendirme özellikleri mevcuttur ve bu sütunlar bir veri kategorisine ait olabilir. Sütunlara istediğiniz adı verip diğer alanlar gibi rapor görselleştirmelerine ekleyebilirsiniz. Hesaplanan tablolar, veri çektiği tablolardan birinin yenilenmesi veya herhangi bir şekilde güncelleştirilmesi halinde yeniden hesaplanır.

Hesaplanan tablolar sonuçları hesaplamak için Power BI Desktop'takiler gibi ilişkisel verilerle çalışmak üzere tasarlanmış bir formül dili olan [Veri Çözümleme İfadeleri](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) formüllerini kullanır. DAX, sahip olduğu 200'den fazla işlev, işleç ve yapı ile her türlü veri çözümleme ihtiyacını karşılayacak sonuçları hesaplayan formüller oluşturma konusunda yüksek düzeyli esneklik sunar.

## <a name="lets-look-at-an-example"></a>Bir örneğe göz atalım
Contoso'da proje yöneticisi olan Jeff'in elinde biri Northwest bölgesindeki, diğeri de Southwest bölgesindeki çalışanları içeren iki tablo var. Jeff, iki tabloyu birleştirerek tek bir tablo haline getirmek istiyor.

**NorthwestEmployees**

 ![](media/desktop-calculated-tables/calctables_nwempl.png)

**SoutwestEmployees**

 ![](media/desktop-calculated-tables/calctables_swempl.png)

Bu iki tabloyu hesaplanan tablo ile bir araya getirmek oldukça kolaydır. Jeff, hesaplanan tabloyu hem Rapor Görünümü hem de Veri Görünümünde oluşturabilecek olsa da yeni hesaplanan tablosunu hemen görebileceği için bu işlemi Veri Görünümünde yapmak daha kolay.

Jeff, **Veri Görünümü**'nün **Modelleme** sekmesinde **Yeni Tablo**'ya tıklıyor. Bir formül çubuğu görüntüleniyor.

 ![](media/desktop-calculated-tables/calctables_formulabarempty.png)

Jeff aşağıdaki formülü giriyor:

 ![](media/desktop-calculated-tables/calctables_formulabarformula.png)

Western Region Employees adlı yeni bir tablo oluşturuluyor.

 ![](media/desktop-calculated-tables/calctables_westregionempl.png)

Jeff'in yeni oluşturduğu Western Region Employees tablosu, Alanlar listesinde diğer tablolar gibi görüntüleniyor. Jeff diğer tablolara ilişki oluşturabilir, hesaplanmış sütun ve ölçü ekleyebilir ve bu tablonun alanlarını diğer tablolar gibi raporlara ekleyebilir.

 ![](media/desktop-calculated-tables/calctables_fieldlist.png)

## <a name="functions-for-calculated-tables"></a>Hesaplanan tablolara ilişkin işlevler
Hesaplanan tablolar başka bir tabloya basit başvuru dahil olmak üzere bir tablo döndüren tüm DAX ifadeleriyle tanımlanabilir. Örneğin:

 ![](media/desktop-calculated-tables/calctables_formulabarsimpleformula.png)

Hesaplanan tabloları DAX ifadeleriyle birlikte kullanarak birçok analitik problemi çözebilirsiniz. Burada hesaplanan tablolara yalnızca kısa bir giriş yaptık. Hesaplanan tablolarla çalışmaya başladığınızda işinize yarayabilecek sık kullanılan diğer DAX tablo işlevleri şunlardır:

&lt;TABLE&gt; DISTINCT VALUES CROSSJOIN UNION NATURALINNERJOIN NATURALLEFTOUTERJOIN INTERSECT CALENDAR CALENDARAUTO

Bu işlevler ve tablo döndüren diğer DAX işlevleri hakkında bilgi için bkz. [DAX İşlev Başvurusu](https://msdn.microsoft.com/ee634396.aspx).

