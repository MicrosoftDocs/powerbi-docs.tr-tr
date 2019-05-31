---
title: Power BI Desktop'ta rapor öğesi performansını incelemek için Performans Çözümleyicisi'ni kullanın
description: Nasıl görsel ve rapor öğeleri kaynak kullanımı ve yanıt hızı bakımından gerçekleştiriyorsanız kullanıma Bul
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1851e0a55bf01073a6591f64de43830a72eca89b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65854425"
---
# <a name="use-performance-analyzer-to-examine-report-element-performance"></a>Rapor öğesi performansını incelemek için Performans Çözümleyicisi'ni kullanın

İçinde **Power BI Desktop** bulabilirsiniz nasıl her biri, görsellerin ve DAX formülleri gibi rapor öğelerinizin yapmakta olduğunuz giden. Kullanarak **Performans Çözümleyicisi**görebilirsiniz ve kayıt günlüklerini nasıl her rapor öğelerinizin gerçekleştiren kullanıcılar bunlarla etkileşim kurduğunuzda ölçün ve performanslarını hangi yönlerini çoğu (ya da en az) kaynak yoğunluğu olan.

![Performans Çözümleyicisi](media/desktop-performance-analyzer/performance-analyzer-01.png)

Performans Çözümleyicisi inceler ve başlatabilir, Kullanıcı etkileşimlerine güncelleştiriliyor veya tüm görsellerin yenilenmesi için gereken süreyi görüntüler ve görüntülemek, detaya gitme veya sonuçlarını dışarı aktarma için bilgiler sunulmuştur. Performans Çözümleyicisi raporlarınızı performansını etkileyen görselleri belirleyip etkisi nedenini belirlemenize yardımcı olabilir.

## <a name="displaying-the-performance-analyzer-pane"></a>Performans Çözümleyicisi bölmesini görüntüleme

İçinde **Power BI Desktop** seçin **görünümü** Şerit. İçinde **Göster** alanının **görünümü** seçebileceğiniz onay kutusunun yanındaki Şerit **Performans Çözümleyicisi** Performans Çözümleyicisi bölmesini görüntülemek için.

![Görünüm şeridinden Performans Çözümleyicisi'ni seçin](media/desktop-performance-analyzer/performance-analyzer-02.png)

Sonra Performans Çözümleyicisi'ni rapor tuvalinin sağ kendi bölmesinde görüntülenir.

## <a name="using-performance-analyzer"></a>Performans Çözümleyicisi'ni kullanma

Performans Çözümleyicisi ölçüler, çalışan bir sorgu sonuçları herhangi bir kullanıcı etkileşimi sonucunda başlatılan rapor öğeleri güncelleştirmek için işleme süresi (zaman oluşturmak veya bir görseli güncelleştirmek için de dahil olmak üzere) gereklidir. Örneğin, bir Dilimleyici ayarlama yeni ayarların sonucunda güncelleştirilmesi gereken etkilenen görseller ve bir sorgu için veri modeli, gönderilecek değişiklik Dilimleyici visual gerektirir. 

Performans Çözümleyicisi'ni kaydetmeye başlamak için basitçe seçin **kaydetmeye başlayın**

![Kaydı Başlat](media/desktop-performance-analyzer/performance-analyzer-03.png)

Raporda tüm eylemleri görüntülenir ve günlüğe Performans Çözümleyicisi bölmesinde, sırayla görselin Power BI tarafından yüklenir. Örneğin, kullanıcıların yenilemek için uzun zaman alıyor söylediğiniz bir raporunuz varsa belki de. Veya belirli bir rapordaki görsellerde bulunan kaydırıcıyı ayarlandığında görüntülenecek uzun sürebilir. Performans Çözümleyicisi'ni hangi görselin sorunlu olduğunu ve hangi yönlerini görsel tanımlayan işlemek için uzun süreli sürüyor söyleyebilirsiniz. 

Kayıt başlattıktan sonra **kaydetmeye başlayın** düğmesi gri çıkış (etkin olmayan, kaydı önceden başladığınızı olduğundan) ve **Durdur** düğmesi etkin olduğu. 

Performans Çözümleyicisi toplar ve gerçek zamanlı performans ölçüm bilgilerini görüntüler. Her zaman bir görsele tıklayın bir Dilimleyiciyi taşıyın ya da başka şekilde, etkileşimli Performans Çözümleyicisi alt bölmede hemen performans sonuçlarını görüntüler.

Bölmesinde görüntülenebilecek olandan daha fazla bilgi için ek bilgiler gitmek için bir kaydırma çubuğu görünür.

Her bir bölüm tanımlayıcısı bölmesinde günlük girişlerini başlatan eylemi açıklayan, etkileşen. Aşağıdaki görüntüde, kullanıcıların bir Dilimleyici değiştiğini etkileşimi oluştu.

![Etkileşim türüne bağlı olarak bölümlerde](media/desktop-performance-analyzer/performance-analyzer-04.png)

Aşağıdaki kategorileri görevleri tamamlamak için harcadığı sürenin (süre) her görselin günlük bilgileri içerir:

* **DAX sorgusu** -DAX sorgusu gerekli olursa, sonuçları döndürmek Analysis Services yanı sıra, sorgu gönderme görsel arasındaki zamanı budur.
* **Görselle** -tüm web görüntüler veya coğrafi kodlama almak için gereken süre de dahil olmak üzere ekranda çizim yapmak görsel için gereken süre. 
* **Diğer** -görsel sorguları hazırlama, diğer görseller için bekleyen veya başka bir arka plan işleme gerçekleştirmek için gereken süre.

![Günlük bilgilerini öğeleri](media/desktop-performance-analyzer/performance-analyzer-06.png)

Performans Çözümleyicisi ile ölçmek istediğiniz rapor öğeleri etkileşim kurulabilen sonra seçebileceğiniz **Durdur** düğmesi. Performans bilgilerini kalır bölmesinde seçtikten sonra **Durdur** , analiz etmek.

Performans Çözümleyicisi bölmesinde bilgiyi temizlemek için seçin **Temizle**. Tüm bilgiler silinir ve seçtiğinizde kaydedilmez **Temizle**. Günlüklerde bilgilerini kaydetme hakkında bilgi edinmek için sonraki bölüme bakın. 

## <a name="refreshing-visuals"></a>Görsellerin

Seçebileceğiniz **Yenile görselleri** Performans Çözümleyicisi bölmesinde raporun geçerli sayfadaki tüm görsellerin yenileyin ve böylece Performans Çözümleyicisi'ni tüm görseller hakkında bilgi toplayın.

Tek başına görseller de yenileyebilirsiniz. Performans Çözümleyicisi kaydederken seçebileceğiniz **bu görseli Yenile** bu görsellerin yenilenmesi için her görselin sağ üst köşede bulunan ve performans bilgilerini yakalayın.

![tek bir görsel Yenile](media/desktop-performance-analyzer/performance-analyzer-07.png)

## <a name="saving-performance-information"></a>Performans bilgileri kaydediliyor

Performans Çözümleyicisi oluşturan bir raporu bilgilerini seçerek kaydedebilirsiniz **dışarı** düğmesi. Seçme **dışarı** Performans Çözümleyicisi bölmesinden bilgileri içeren bir .json dosyası oluşturur. 

![Performans Çözümleyicisi için günlük dosyasına kaydedin](media/desktop-performance-analyzer/performance-analyzer-05.png)


## <a name="next-steps"></a>Sonraki adımlar
**Power BI Desktop** ve Power BI Desktop'la çalışmaya başlama hakkında daha fazla bilgi için aşağıdaki makalelere başvurun.

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop ile Sorgulara Genel Bakış](desktop-query-overview.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'taki Verilere Bağlanma](desktop-connect-to-data.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki Genel Sorgu Görevleri](desktop-common-query-tasks.md)   

