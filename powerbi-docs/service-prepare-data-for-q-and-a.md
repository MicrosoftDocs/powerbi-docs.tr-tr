---
title: Excel verilerinizin Power BI'daki Soru-Cevap özelliğiyle düzgün çalışmasını sağlama
description: Verilerinizin Power BI'daki Soru-Cevap özelliğiyle düzgün çalışmasını sağlama
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 627a94097d4235f39414c1165ac8cbbc806508a3
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/31/2019
ms.locfileid: "55430079"
---
# <a name="how-to-make-your-excel-data-work-well-with-qa-in-power-bi"></a>Excel verilerinizin Power BI'daki Soru-Cevap özelliğiyle düzgün çalışmasını sağlama
Veri modelleri veya Power BI ile kullanılacak Excel çalışma kitapları oluşturuyorsanız bu makaleyi okumaya devam edin.

Yapılandırılmış verilerde arama yapabilmesi ve sorunuza yönelik doğru görselleştirmeyi seçebilmesi, Power BI'daki Soru-Cevap'ın ilgiyle kullanacağınız bir araç olmasını sağlar.   

Soru-Cevap; tablo, aralıklar veya PowerPivot modeli içeren, karşıya yüklenmiş herhangi bir Excel dosyası üzerinde çalışabilir ancak daha fazla iyileştirme ve veri temizleme gerçekleştirdikçe daha güçlü bir Soru-Cevap performansı elde edersiniz.  Veri kümenize dayalı raporlar ve panolar paylaşmayı planlıyorsanız, iş arkadaşlarınızın zorlanmadan sorular sorup kaliteli cevaplar almasını istersiniz.

### <a name="how-qa-works-with-excel"></a>Soru-Cevap özelliği Excel ile nasıl kullanılır?
Soru-Cevap, verileriniz üzerinde kullanılan, bir dizi temel doğal dil anlama becerisine sahiptir. Excel tablo ve sütun adlarınızın yanı sıra hesaplanmış alan adlarınız için bağlama bağlı anahtar sözcük arama özelliği içerir. Ayrıca verileri filtreleme, sıralama, toplama, gruplandırma ve görüntülemeye yönelik yerleşik bilgilerle donatılmıştır. 

Örneğin, "Product" (Ürün), "Month" (Ay), "Units Sold" (Satılan Birim Sayısı), "Gross Sales" (Brüt Satışlar) ve "Profit" (Kâr) sütunlarının bulunduğu "Sales" (Satışlar) adlı bir Excel tablosunda, söz konusu varlıklardan herhangi biriyle ilgili sorular sorabilirsiniz.  Satışların ve aylık toplam kârın gösterilmesi, ürünlerin satılan birim sayısına göre sıralanması ve daha nicesi gibi işlemlerin gerçekleştirilmesini isteyebilirsiniz. [Sorabileceğiniz soru türleri](consumer/end-user-q-and-a.md) ve [bir Soru-Cevap sorgusunda belirtebileceğiniz görselleştirme türleri](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md) hakkında daha fazla bilgi edinin.

### <a name="prepare-an-excel-dataset-for-qa"></a>Bir Excel veri kümesini Soru-Cevap için hazır hale getirme
Soru-Cevap, verilere özgü soruları cevaplamak için tablo, sütun ve hesaplanmış alan adlarını kullanır; bu nedenle çalışma kitabınızda varlıklara verdiğiniz adlar konusunda dikkatli olmanız gerekir.

Aşağıda, çalışma kitabınızda Soru-Cevap'tan en iyi şekilde yararlanmanıza yönelik birkaç ipucuna göz atabilirsiniz.

* Verilerinizin bir Excel tablosunda bulunduğundan emin olun. Burada, [bir Excel tablosunu nasıl oluşturacağınız](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664) anlatılmıştır.
* Tablo, sütun ve hesaplanmış alanlarınız için doğal konuşma dilinde anlam ifade eden adlar kullanın.
  
  Örneğin, satış verileri içeren bir tablonuz varsa bunu "Sales" olarak adlandırın. "Year" (Yıl), "Product" (Ürün), "Sales Rep" (Satış Temsilcisi) ve "Amount" (Miktar) gibi sütun adları Soru-Cevap ile düzgün bir şekilde çalışır.

* Çalışma kitabınızda Power Pivot veri modeli bulunuyorsa daha da fazla iyileştirme yapabilirsiniz. Doğal dil uzmanlarından oluşan şirket içi ekibimizin kaleme aldığı [Demystifying Power BI Q&A part 2 (Power BI Soru-Cevap'ın gizemini çözme - 2. kısım)](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx) başlıklı blogdan daha fazla bilgi edinebilirsiniz.

* Veri kümesini Power BI Desktop'ta açın, yeni sütunlar ve hesaplanmış ölçüler oluşturun, benzersiz değerler elde etmek için alanları birleştirin, verileri türe göre (ör. tarihler, dizeler, coğrafya, görüntüler, URL'ler) sınıflandırın ve daha pek çok işlem gerçekleştirin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki Soru-Cevap](consumer/end-user-q-and-a.md) özelliğine geri dönün  
[Şirket içi veri kümelerini Soru-Cevap için hazır hale getirme](service-q-and-a-direct-query.md)   
[Hızlı Başlangıç: Soru-Cevap](power-bi-visualization-introduction-to-q-and-a.md)  
[Power BI için veri alma](service-get-data.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

