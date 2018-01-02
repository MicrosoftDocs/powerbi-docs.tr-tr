---
title: "Power BI Desktop'ta ikili değerleri birleştirme"
description: "Power BI Desktop'ta ikili veri kaynaklarını kolayca birleştirin"
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: d0c4f3afb7b8b103dfa59a982b067bbad24251fb
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2017
---
# <a name="combine-binaries-in-power-bi-desktop"></a>Power BI Desktop'ta ikili değerleri birleştirme
Aynı şemaya sahip birden fazla dosyayı tek bir mantıksal tablo olarak birleştirmek, **Power BI Desktop**'a veri aktarmaya yönelik güçlü bir yaklaşımdır. Bu kullanışlı ve popüler yaklaşım, **Power BI Desktop**'ın Kasım 2016 sürümü (ve sonraki sürümler) ile birlikte çok daha kullanışlı ve kapsamlı hale geldi. Ayrıntıları bu makalede bulabilirsiniz.

Aynı klasörde bulunan ikili değerleri birleştirme işlemine başlamak için **Veri Al > Dosya > Klasör**'ü seçin.

![](media/desktop-combine-binaries/combine-binaries_1.png)

## <a name="previous-combine-binaries-behavior"></a>Güncelleştirme öncesinde ikili değerleri birleştirme davranışı
**Power BI Desktop**'ın Kasım 2016 sürümünden önce, **İkili değerleri birleştir** dönüştürme işlemiyle belirli dosya türlerini birleştirebiliyordunuz ancak bazı sınırlamalar söz konusuydu:

* Tek dosyalarda dönüştürme işleminin gerçekleştirilebilmesi için dosyaların tek bir tabloda birleştirilmesi gerekiyordu. Benzer şekilde, genellikle dosyaları birleştirmeniz ve düzenleme işleminin bir parçası olarak satırları filtreleyip *başlık değerlerini* dışarıda bırakmanız gerekiyordu.
* **İkili değerleri birleştir** dönüştürme işlemi yalnızca *metin* veya *CSV* dosyalarında kullanılabiliyor; Excel çalışma kitapları ve JSON dosyaları gibi şu anda desteklenen diğer dosya biçimlerinde kullanılamıyordu.

Müşterilerimiz **İkili değerleri birleştir** işleminin daha kullanışlı hale getirilmesini istediğinden bu dönüştürme deneyimi iyileştirildi.

## <a name="current-combine-binaries-behavior"></a>Güncelleştirme sonrasında ikili değerleri birleştirme davranışı
**Power BI Desktop** artık **İkili değerleri birleştir** işlemini çok daha etkin bir şekilde gerçekleştiriyor. Bu işleme, **Sorgu Düzenleyicisi**'nin **Giriş** şeridi sekmesinde veya ilgili sütunda **İkili değerleri birleştir** seçeneğini belirleyerek başlarsınız.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

**İkili değerleri birleştir** dönüştürme işleminin geçerli davranışı:

* **İkili değerleri birleştir** dönüştürme işlemi, her bir giriş dosyasını çözümler ve kullanılacak doğru dosya biçimini (*metin*, *Excel çalışma kitabı* veya *JSON* dosyası gibi) belirler.
* Dönüştürme işlemi, ilk dosyadan belirli bir nesneyi (örneğin, ayıklanacak bir *Excel çalışma kitabı*) seçmenize olanak sağlar.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* Ardından, **İkili değerleri birleştir** seçeneğiyle otomatik olarak şu işlemler gerçekleştirilir:
  
  * Tek bir dosyada gerekli tüm ayıklama adımlarını gerçekleştirecek örnek bir sorgu oluşturulur.
  * Dosya/ikili değer girişini *örnek sorgu* olarak parametreleştiren bir *işlev sorgusu* oluşturulur. Örnek sorgu ve işlev sorgusu bağlantılı hale getirilir. Böylece, örnek sorguda yapılan değişiklikler işlev sorgusunda da geçerli olur.
  * *İşlev sorgusu*, giriş ikili değerlerinin bulunduğu özgün sorguya (örneğin, *Klasör* sorgusu) uygulanır. Böylece, her bir satırdaki ikili değer girişleri için işlev sorgusu uygulanır ve ayıklanan veriler, üst düzey sütunlar olarak genişletilir.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

**İkili değerleri birleştir** seçeneğinin yeni davranış biçimiyle, aynı dosya türüne ve yapısına (örneğin, aynı sütunlarda bulunmaları) sahip oldukları sürece belirli bir klasördeki tüm ikili değerleri kolayca birleştirebilirsiniz.

Ayrıca, otomatik olarak oluşturulan *örnek sorguyu* değiştirerek başka dönüştürme ve ayıklama adımlarını da kolayca uygulayabilirsiniz. Bunun için *işlev sorgusu* adımlarını değiştirmeniz veya yeni adımlar oluşturmanız gerekmez; *örnek sorguda* yapılan tüm değişiklikler bağlantılı *işlev sorgusunda* otomatik olarak geçerli olur.

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md)
* [Power BI Desktop'taki veri kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta CSV dosyalarına bağlanma](desktop-connect-csv.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   

