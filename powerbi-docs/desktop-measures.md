---
title: Power BI Desktop'taki ölçüleri kullanma
description: Power BI Desktop'taki ölçüler
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 3246f13291b3dd46f60db9403b1b69029c65a513
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34289522"
---
# <a name="measures-in-power-bi-desktop"></a>Power BI Desktop'taki ölçüler
**Power BI Desktop**, birkaç tıklamayla verilerinizle ilgili öngörüler oluşturmanıza yardımcı olur. Ancak bazen bu veriler en önemli soruların yanıtlarına ulaşmak için ihtiyacınız olan her şeyi sunmaz. Ölçüler bu noktada size yardımcı olabilir.

Ölçüler toplamlar, ortalamalar, minimum veya maksimum değerler, sayımlar veya DAX formülü kullanarak oluşturabileceğiniz daha gelişmiş hesaplamalar gibi en sık kullanılan veri çözümlemelerinde kullanılır. Ölçülerin hesaplanan sonuçları raporunuzdaki etkileşime göre sürekli değişerek, güncel verileri hızlı ve dinamik bir şekilde keşfetmenizi sağlar. Şimdi bu yöntemlere daha yakından bakalım.

## <a name="understanding-measures"></a>Ölçüleri anlama
**Power BI Desktop**'ta ölçüler, **Rapor Görünümü** veya **Veri Görünümü**'nde oluşturulur ve kullanılır. Kendi oluşturduğunuz ölçüler, Alanlar listesinde yanında hesap makinesi simgesiyle görüntülenir. Ölçülere istediğiniz adı verip bunları tıpkı diğer alanlar gibi yeni veya mevcut görselleştirmelere ekleyebilirsiniz.

![](media/desktop-measures/measuresinpbid_measinfieldlist.png)

> [!NOTE]
> İletişim kutularından seçebileceğiniz kullanıma hazır ölçüler olan **hızlı ölçüler** de ilginizi çekebilir. Hızlı ölçüleri kullanarak hızlıca ölçü oluşturabilir, ayrıca bunları oluşturan DAX formüllerini inceleyerek DAX söz dizimini öğrenebilirsiniz. Şu makaleyi inceleyin: [hızlı ölçüler](desktop-quick-measures.md).
> 
> 

## <a name="data-analysis-expressions"></a>Veri Çözümleme İfadeleri
Ölçüler, bir ifade formülünün sonucunu hesaplar. Kendi ölçülerinizi oluştururken [Veri Çözümleme İfadeleri](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) formül dilini kullanırsınız. DAX, sahip olduğu 200'den fazla işlev, işleç ve yapı ile her türlü veri çözümleme ihtiyacı için sonuçları hesaplayacak ölçüler oluşturma konusunda yüksek esneklik sunar.

DAX formülleri Excel formülleriyle oldukça benzerdir. DAX ile DATE, SUM ve LEFT gibi Excel işlevlerini bile kullanabilirsiniz. Ancak DAX işlevleri, Power BI Desktop'takiler gibi ilişkisel verilerle çalışacak şekilde tasarlanmıştır.

## <a name="lets-look-at-an-example"></a>Bir örneğe göz atalım
Jan, Contoso'da satış yöneticisi olarak çalışmaktadır. Bir sonraki mali yıl için bayi satış tahminlerini sunması istenmektedir. Tahmin için önceki yılın satış rakamlarını temel alarak sonraki altı ayda yapılması planlanan promosyonlar nedeniyle yıllık yüzde altı artış uygulamak istemektedir.

Tahminleri rapor haline getirmek için önceki yılın satış verilerini Power BI Desktop'a aktarır. Reseller Sales tablosundaki SalesAmount alanını bulur. İçeri aktardığı veriler yalnızca önceki yılın satış rakamlarını içerdiği için SalesAmount alanının adını Last Years Sales olarak değiştirir. Ardından Last Years Sales alanını rapor tuvaline sürükler. Alan için, önceki yılın bayi satışlarının toplamı olarak tek bir değerin gösterildiği bir grafik görselleştirmesi oluşturulur.

Ardından, hesaplama belirtmemiş olmasına rağmen otomatik bir hesaplama yapıldığını fark eder. Power BI Desktop, Last Years Sales alanındaki tüm değerleri toplayarak bir ölçü oluşturmuştur.

Ancak Jan'ın yüzde 6'lık artışa ulaşmak için, önceki yılın satışlarının 1,06 ile çarpılmış hali olan gelecek yılın satış tahminlerini hesaplamak üzere bir ölçü oluşturması gerekmektedir. Bu hesaplama için kendi ölçüsünü oluşturması gerekir. Yeni Ölçü özelliğini kullanarak yeni bir ölçü oluşturup şu DAX formülünü girer:

    Projected Sales = SUM('Sales'[Last Years Sales])*1.06

Ardından, yeni oluşturduğu Projected Sales ölçüsünü grafiğe sürükler.

![](media/desktop-measures/measuresinpbid_lastyearsales.png)

Jan hızlı ve kolay bir şekilde tahmini satışları hesaplamış oldu. Diğer alanları raporuna ekleyip belirli bayileri filtreleyerek tahminleriyle ilgili daha fazla çözümleme gerçekleştirebilir.

## <a name="learn-more"></a>Daha fazla bilgi
Burada ölçülerle ilgili özet bilgilere yer verdik ancak kendi ölçülerinizi oluşturmayı öğrenmek için faydalanabileceğiniz birçok farklı kaynak mevcuttur. Ayrıntılı bilgi için, örnek bir dosya indirip daha fazla ölçü oluşturma konusundaki adım adım yönergeleri uygulayabileceğiniz [Eğitim: Power BI Desktop'ta kendi ölçülerinizi oluşturma](desktop-tutorial-create-measures.md) başlıklı eğitimi inceleyebilirsiniz.  

DAX hakkında daha ayrıntılı bilgi edinmek için [Power BI Desktop'ta DAX kullanımıyla ilgili temel bilgiler](desktop-quickstart-learn-dax-basics.md) makalesine göz atabilirsiniz. [Veri Çözümleme İfadeleri Başvurusu](https://msdn.microsoft.com/library/gg413422.aspx)'nda işlevler, söz dizimi, işleçler ve adlandırma stilleri hakkında ayrıntılı makaleler yer almaktadır. DAX, birkaç yıldır Excel'deki Power Pivot özelliğinde ve SQL Server Analysis Services uygulamasında kullanılmakta olduğundan başka birçok faydalı kaynak da mevcuttur. BI topluluğunun önde gelen üyelerinin DAX bilgilerini paylaştığı [DAX Resource Center Wiki](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx) sayfasını ziyaret etmeyi unutmayın.



