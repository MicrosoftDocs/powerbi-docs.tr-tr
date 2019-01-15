---
title: Power BI Desktop'ta sorgulara genel bakış
description: Power BI Desktop'ta sorgulara genel bakış
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 85429f76159854bf5eb4e2dc671b2d2bc1521dbf
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277055"
---
# <a name="query-overview-in-power-bi-desktop"></a>Power BI Desktop'ta sorgulara genel bakış
**Power BI Desktop** ile veri dünyasına bağlanabilir, ilgi çekici ve temel nitelikte raporlar oluşturabilir ve çalışmanızı başkalarıyla paylaşabilirsiniz. Bu kişiler de çalışmanızı temel alıp kendi iş zekası çalışmalarını geliştirir.

Power BI Desktop'ta üç görünüm vardır:

* **Rapor** görünümü: İstediğiniz gibi görünen, birden çok sayfa içeren ve başka kullanıcılarla paylaşabileceğiniz ilgi çekici görselleştirmeler elde etmek için oluşturduğunuz sorguları kullanabilirsiniz
* **Veri** görünümü: Raporunuzdaki verileri, veri modeli biçiminde görebilir; ölçüler ekleyebilir, yeni sütunlar oluşturabilir ve ilişkileri yönetebilirsiniz
* **İlişkiler** görünümü: Veri modelinizde oluşturulan ilişkilerin grafik gösterimini elde edebilir ve bunları, gereken şekilde yönetebilir veya değiştirebilirsiniz.

Bu görünümlere, Power BI Desktop'ın sol tarafındaki üç simgeden birini seçerek erişebilirsiniz. Aşağıdaki görüntüde Rapor görünümü seçilmiştir ve bu seçim, simgenin yan tarafındaki sarı şerit ile belirtilmiştir.  

![](media/desktop-query-overview/queryoverview_viewicons.png)

Power BI Desktop ile birlikte sunulan **Sorgu Düzenleyicisi**'ni kullanarak bir veya daha çok veri kaynağına bağlanabilir, verileri ihtiyaçlarınızı karşılayacak biçimde şekillendirip dönüştürebilir ve ilgili modeli Power BI Desktop'a yükleyebilirsiniz.

Bu belgede, **Sorgu Düzenleyicisi**'nde verilerle çalışmaya yönelik bir genel bakış sağlanmıştır. Öğrenecekleriniz elbette bunlarla sınırlı değil. Desteklenen veri türleri, verilere bağlanma, verileri şekillendirme, ilişki oluşturma ve çalışmaya başlama hakkında ayrıntılı yönergeler içeren bağlantıları bu belgenin sonunda bulabilirsiniz.

Öncelikle **Sorgu Düzenleyicisi**'ni tanıyalım.

## <a name="the-query-editor"></a>Sorgu Düzenleyicisi
**Sorgu Düzenleyicisi**'ne ulaşmak için Power BI Desktop'ın **Giriş** sekmesinde **Sorguları Düzenle**'yi seçin.  

![](media/desktop-query-overview/queryoverview_queryview.png)

Hiçbir veri bağlantısı olmadığında **Sorgu Düzenleyicisi** veri almaya hazır, boş bir bölme olarak görünür.  

![](media/desktop-query-overview/queryoverview_blankpane.png)

Bir sorgu yüklendikten sonra **Sorgu Düzenleyicisi** daha ilgi çekici hale gelir. Aşağıdaki Web veri kaynağına bağlanırsak **Sorgu Düzenleyicisi**, verilerle ilgili bilgileri yükler ve verileri şekillendirmeye başlayabilirsiniz.

[*http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx*](http://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx)

Veri bağlantısı oluşturulduktan sonra **Sorgu Düzenleyicisi** aşağıdaki gibi görünür:

1. Sorgudaki verilerle etkileşim kurabilmeniz için şeritteki birçok düğmenin etkinleştirildiğini görürsünüz
2. Sol bölmede sorgular listelenir; bu sorguları seçebilir, görüntüleyebilir ve şekillendirebilirsiniz
3. Ortadaki bölmede, seçilen sorgudaki veriler görüntülenir ve bu veriler şekillendirilebilir
4. Sorgunun özelliklerinin ve uygulanan adımların listelendiği **Sorgu Ayarları** penceresi görünür  
   
   ![](media/desktop-query-overview/queryoverview_withdataconnection.png)

Bu dört alanın (şerit, sorgular bölmesi, veri görünümü ve Sorgu Ayarları bölmesi) her birini aşağıdaki bölümlerde ele alacağız.

## <a name="the-query-ribbon"></a>Sorgu şeridi
**Sorgu Düzenleyicisi**'ndeki şerit **Giriş**, **Dönüştür**, **Sütun Ekle** ve **Görünüm** olmak üzere dört sekmeden oluşur.

**Giriş** sekmesinde, tüm sorguların ilk adımı olarak kullanılan **Veri Al** düğmesi de dahil olmak üzere sık kullanılan sorgu görevlerini bulabilirsiniz. Aşağıdaki görüntüde **Giriş** şeridi gösterilmektedir.  

![](media/desktop-query-overview/queryoverview_ribbon.png)

Verilere bağlanmak ve sorgu oluşturma işlemine başlamak için **Veri Al** düğmesini seçin. En yaygın veri kaynaklarının listelendiği bir menü belirir.  

![](media/desktop-query-overview/queryoverview_getdatamenu.png)

Mevcut veri kaynakları hakkında daha fazla bilgi için bkz. **Veri Kaynakları**. Örnekler ve adımlar da dahil olmak üzere verilere bağlanma hakkında bilgi edinmek için bkz. **Verilere Bağlanma**.

**Dönüştür** sekmesinde; sütun ekleme veya kaldırma, veri türlerini değiştirme, sütunları bölme ve diğer veri tabanlı görevler gibi sık kullanılan veri dönüştürme görevlerine erişebilirsiniz. Aşağıdaki görüntüde **Dönüştür** sekmesi gösterilmektedir.  

![](media/desktop-query-overview/queryoverview_transformribbon.png)

Örnekler de dahil olmak üzere veri dönüştürme hakkında daha fazla bilgi edinmek için bkz. **Verileri Birleştirme ve Şekillendirme**.

**Sütun Ekle** sekmesinde; sütun ekleme, sütun verilerini biçimlendirme ve özel sütunlar ekleme ile ilişkili ek görevler bulunur. Aşağıdaki görüntüde **Sütun Ekle** sekmesi gösterilmektedir.  

![](media/desktop-query-overview/queryoverview_addcolumnribbon.png)

Şeritteki **Görünüm** sekmesi, belirli bölmelerin veya pencerelerin görüntülenip görüntülenmeyeceğini belirlemek için kullanılır. Gelişmiş Düzenleyici'yi görüntülemek için de kullanılır. Aşağıdaki görüntüde **Görünüm** sekmesi gösterilmektedir.  

![](media/desktop-query-overview/queryoverview_viewribbon.png)

Şeritte sunulan görevlerin birçoğunu, orta bölmede bir sütuna veya diğer verilere sağ tıklayarak da kullanabileceğinizi unutmayın.

## <a name="the-left-pane"></a>Sol bölme
Sol bölmede, etkin sorgu sayısının yanı sıra sorgunun adı görüntülenir. Sol bölmede bir sorguyu seçtiğinizde bu sorgunun verileri orta bölmede görüntülenir ve orta bölmede verileri ihtiyaçlarınıza göre şekillendirip dönüştürebilirsiniz. Aşağıdaki görüntüde, birden fazla sorgu içeren sol bölme gösterilmektedir.  

![](media/desktop-query-overview/queryoverview_theleftpane.png)

## <a name="the-center-data-pane"></a>Orta bölme (veri bölmesi)
Orta bölmede (veya Veri bölmesinde) seçilen sorgudaki tarihler görüntülenir. Sorgu görünümündeki çalışmanın büyük kısmı burada gerçekleşir.

Aşağıdaki görüntüde, daha önce kurulan Web veri bağlantısı görüntülenmektedir. **Overall score** sütunu seçilmiştir ve kullanılabilir menü öğelerinin gösterilmesi için bu sütunun başlığına sağ tıklanmıştır. Sağ tıklandığında görüntülenen menü öğelerinin birçoğunun, şerit sekmelerindeki düğmelerle aynı olduğu görülmektedir.  

![](media/desktop-query-overview/queryoverview_thecenterpane.png)

Sağ tıklandığında görüntülenen menü öğelerinden birini (veya şeritteki bir düğmeyi) seçtiğinizde Sorgu, ilgili adımı verilere uygular ve sorgunun parçası olarak kaydeder. Sonraki bölümde açıklandığı üzere, adımlar sıralı şekilde **Sorgu Ayarları**'nda kaydedilir.  

## <a name="the-query-settings-pane"></a>Sorgu Ayarları bölmesi
**Sorgu Ayarları** bölmesi, sorgu ile ilişkili tüm adımların görüntülendiği yerdir. Örneğin, aşağıdaki görüntüde; **Sorgu Ayarları** bölmesinin **Uygulanan Adımlar** bölümünde, **Overall score** sütununun türünü değiştirdiğimiz gösterilmektedir.

![](media/desktop-query-overview/queryoverview_querysettingspane.png)

Sorguda uygulanan ek şekillendirme adımları, **Uygulanan Adımlar** bölümünde kaydedilir.

Temel alınan verilerin *değiştirilmediğini* bilmek önemlidir. Sorgu Düzenleyicisi, veri görünümünü ayarlayıp şekillendirir ve temel alınan verilerle kurulan herhangi bir etkileşim, ilgili verilerin Sorgu Düzenleyicisi tarafından şekillendirilen ve değiştirilen hali temel alınarak gerçekleştirilir.

**Sorgu Ayarları** bölmesinde adımları istediğiniz şekilde yeniden adlandırabilir, silebilir veya yeniden sıralayabilirsiniz. Bunun için **Uygulanan Adımlar** bölümünde adıma sağ tıklayın ve görünen menüde seçim yapın. Tüm sorgu adımları, **Uygulanan Adımlar** bölmesinde görünen sırada gerçekleştirilir.

![](media/desktop-query-overview/queryoverview_querysettings_rename.png)

## <a name="the-advanced-editor"></a>Gelişmiş Düzenleyici
Sorgu Düzenleyicisi'nin her adımda oluşturduğu kodu görmek veya kendi şekillendirme kodunuzu oluşturmak isterseniz **Gelişmiş Düzenleyici**'yi kullanabilirsiniz. Gelişmiş düzenleyiciyi başlatmak için şeritte **Görünüm**'ü ve ardından **Gelişmiş Düzenleyici**'yi seçin. Var olan sorgu kodunu gösteren bir pencere görünür.  
![](media/desktop-query-overview/queryoverview_advancededitor.png)

**Gelişmiş Düzenleyici** penceresinde kodu doğrudan düzenleyebilirsiniz. Pencereyi kapatmak için **Bitti** veya **İptal** düğmesini seçin.  

## <a name="saving-your-work"></a>Çalışmanızı kaydetme
Sorgunuz istediğiniz gibi olduğunda Sorgu Düzenleyicisi'nin, değişiklikleri Power BI Desktop'taki veri modelinde uygulamasını sağladıktan sonra Sorgu Düzenleyicisi'ni kapatabilirsiniz. Bunu yapmak için Sorgu Düzenleyicisi'nin **Dosya** menüsünden **Kapat & Uygula**'yı seçin.  
![](media/desktop-query-overview/queryoverview_closenload.png)

Power BI Desktop, ilerleme kaydedildiğinde durumu görüntülemek için bir iletişim kutusu sunar.  
![](media/desktop-query-overview/queryoverview_loading.png)

Sorgunuz istediğiniz gibi olduğunda veya çalışmanızın kaydedildiğinden emin olmak istediğinizde Power BI Desktop, çalışmanızı .pbix dosyası biçiminde kaydedebilir.

Çalışmanızı kaydetmek için aşağıdaki görüntüde gösterildiği üzere, **Dosya \> Kaydet**'i (veya **Dosya \> Farklı Kaydet**) seçin.  
![](media/desktop-query-overview/queryoverview_savework.png)

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop ile yapabileceğiniz çok şey var. Özellikler hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'taki Verilere Bağlanma](desktop-connect-to-data.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki Genel Sorgu Görevleri](desktop-common-query-tasks.md)   

