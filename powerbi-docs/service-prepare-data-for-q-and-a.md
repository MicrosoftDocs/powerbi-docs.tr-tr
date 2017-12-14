---
title: "Power BI'daki Soru-Cevap özelliğiyle verilerinizin düzgün çalışmasını sağlama"
description: "Power BI'daki Soru-Cevap özelliğiyle verilerinizin düzgün çalışmasını sağlama"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 499c3beca9046af9336de6dfec96994004050986
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="make-your-data-work-well-with-qa-in-power-bi"></a>Power BI'daki Soru-Cevap özelliğiyle verilerinizin düzgün çalışmasını sağlama
Veri modelleri veya Power BI ile kullanılacak Excel çalışma kitapları oluşturuyorsanız bu makaleyi okumaya devam edin.

Yapılandırılmış verilerde arama yapabilmesi ve sorunuza yönelik doğru görselleştirmeyi seçebilmesi, Power BI'daki Soru-Cevap'ın ilgiyle kullanacağınız bir araç olmasını sağlar.   

Soru-Cevap; tablo, aralıklar veya PowerPivot modeli içeren, karşıya yüklenmiş herhangi bir Excel dosyası üzerinde çalışabilir ancak daha fazla iyileştirme ve veri temizleme gerçekleştirdikçe daha güçlü bir Soru-Cevap performansı elde edersiniz. 

## <a name="how-qa-works"></a>Soru-Cevap nasıl çalışır?
Soru-Cevap, verileriniz üzerinde kullanılan, bir dizi temel doğal dil anlama becerisine sahiptir. Excel tablo ve sütun adlarınızın yanı sıra hesaplanmış alan adlarınız için bağlama bağlı anahtar sözcük arama özelliği içerir. Ayrıca yerleşik olarak; verileri filtreleme, sıralama, toplama, gruplandırma ve görüntülemeye yönelik bilgilerle donatılmıştır. 

Örneğin, "Product" (Ürün), "Month" (Ay), "Units Sold" (Satılan Birim Sayısı), "Gross Sales" (Brüt Satışlar) ve "Profit" (Kâr) sütunlarının bulunduğu "Sales" (Satışlar) adlı bir Excel tablosunda, söz konusu varlıklardan herhangi biriyle ilgili sorular sorabilirsiniz.  Satışların ve aylık toplam kârın gösterilmesi, ürünlerin satılan birim sayısına göre sıralanması ve daha nicesi gibi işlemlerin gerçekleştirilmesini isteyebilirsiniz. [Sorabileceğiniz soru türleri](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-1.aspx), [soru şablonu kullanarak sorular sorma](service-q-and-a.md) ve [bir Soru-Cevap sorgusunda belirtebileceğiniz görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md) hakkında daha fazla bilgi edinin.

## <a name="prepare-a-workbook-for-qa"></a>Bir çalışma kitabını Soru-Cevap için hazırlama
Soru-Cevap, verilere özgü soruları cevaplamak için tablo, sütun ve hesaplanmış alan adlarını kullanır; bu nedenle çalışma kitabınızda varlıklara verdiğiniz adlar konusunda dikkatli olmanız gerekir.

Aşağıda, çalışma kitabınızda Soru-Cevap'tan en iyi şekilde yararlanmanıza yönelik birkaç ipucuna göz atabilirsiniz.

* Verilerinizin bir Excel tablosunda bulunduğundan emin olun. Burada, [bir Excel tablosunu nasıl oluşturacağınız](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US) anlatılmıştır.
* Tablo, sütun ve hesaplanmış alanlarınız için İngilizce dilinde anlam ifade eden kelimeler kullanın.
  
  Örneğin, satış verileri içeren bir tablonuz varsa bunu "Sales" olarak adlandırın. "Year" (Yıl), "Product" (Ürün), "Sales Rep" (Satış Temsilcisi) ve "Amount" (Miktar) gibi sütun adları Soru-Cevap ile düzgün bir şekilde çalışır.

> [!NOTE]
> Çalışma kitabınızda Power Pivot veri modeli bulunuyorsa daha da fazla iyileştirme yapabilirsiniz. Doğal dil uzmanlarından oluşan şirket içi ekibimizin kaleme aldığı [Demystifying Power BI Q&A part 2 (Power BI Soru-Cevap'ın gizemini çözme - 2. kısım)](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx) başlıklı blogdan daha fazla bilgi edinebilirsiniz.
> 
> 

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki Soru-Cevap](service-q-and-a.md)  
[Eğitim: Power BI Soru-Cevap'a Giriş](power-bi-visualization-introduction-to-q-and-a.md)  
[Power BI için veri alma](service-get-data.md)  
[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

