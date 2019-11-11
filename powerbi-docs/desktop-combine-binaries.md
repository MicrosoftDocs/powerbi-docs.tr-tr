---
title: Power BI Desktop’ta dosyaları (ikili değerleri) birleştirme
description: Power BI Desktop’ta dosya (ikili değerleri) veri kaynaklarını kolayca birleştirme
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 03a6e044a55613d40a1cf195d6a0ad3b44a9f012
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73876544"
---
# <a name="combine-files-binaries-in-power-bi-desktop"></a>Power BI Desktop’ta dosyaları (ikili değerleri) birleştirme
Aynı şemaya sahip birden fazla dosyayı tek bir mantıksal tablo olarak birleştirmek, **Power BI Desktop**'a veri aktarmaya yönelik güçlü bir yaklaşımdır. Bu makalede açıklandığı gibi, bu kullanışlı ve popüler yaklaşım çok daha kullanışlı ve kapsamlı hale getirilmiştir.

Aynı klasörde bulunan dosyaları birleştirme işlemine başlamak için **Veri Al > Dosya > Klasör**’ü seçin.

![](media/desktop-combine-binaries/combine-binaries_1.png)


## <a name="combine-files-behavior"></a>Dosya birleştirme davranışı
**Sorgu Düzenleyicisi** **Giriş** şeridi sekmesinden **dosyaları birleştir**’i seçerek **dosyaları (ikili) birleştirebilirsiniz**.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

**Dosyaları birleştir** dönüştürme işlemi aşağıdaki gibi davranır:

* **Dosyaları birleştir** dönüştürme işlemi, her bir giriş dosyasını çözümler ve kullanılacak doğru dosya biçimini (*metin* veya *Excel çalışma kitabı* ya da *JSON* dosyası gibi) belirler.
* Dönüştürme işlemi, ilk dosyadan belirli bir nesneyi (örneğin, ayıklanacak bir *Excel çalışma kitabı*) seçmenize olanak sağlar.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* **Dosyaları birleştir** işlemi daha sonra otomatik olarak aşağıdaki sorguları gerçekleştirir:
  
  * Tek bir dosyada gerekli tüm ayıklama adımlarını gerçekleştirecek örnek bir sorgu oluşturulur.
  * Dosya/ikili değer girişini *örnek sorgu* olarak parametreleştiren bir *işlev sorgusu* oluşturulur. Örnek sorgu ve işlev sorgusu bağlantılı hale getirilir. Böylece, örnek sorguda yapılan değişiklikler işlev sorgusunda da geçerli olur.
  * *İşlev sorgusu*, giriş ikili değerlerinin bulunduğu özgün sorguya (örneğin, *Klasör* sorgusu) uygulanır. Böylece, her bir satırdaki ikili değer girişleri için işlev sorgusu uygulanır ve ayıklanan veriler, üst düzey sütunlar olarak genişletilir.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

> [!NOTE]
> Bir Excel çalışma kitabındaki seçiminizin kapsamı, ikili dosyaları birleştirme davranışını etkiler. Örneğin, belirli bir çalışma sayfasını seçerek çalışma sayfasını birleştirebilir veya tam dosyayı birleştirmek için kökü seçebilirsiniz. Bir klasörün seçilmesi o klasörde bulunan dosyaları birleştirir. 


**Dosyaları birleştir** seçeneğinin davranış biçimiyle, aynı dosya türüne ve yapısına (örneğin, aynı sütunlarda bulunmaları) sahip oldukları sürece belirli bir klasördeki tüm dosyaları kolayca birleştirebilirsiniz.

Ayrıca, otomatik olarak oluşturulan *örnek sorguyu* değiştirerek başka dönüştürme ve ayıklama adımlarını da kolayca uygulayabilirsiniz. Bunun için ek *işlev sorgusu* adımlarını değiştirmeniz veya yeni adımlar oluşturmanız gerekmez. *Örnek sorgu* üzerindeki tüm değişiklikler, bağlantılı *işlev sorgusunda* otomatik olarak oluşturulur.

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta CSV dosyalarına bağlanma](desktop-connect-csv.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   

