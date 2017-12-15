---
title: "Power BI'da renk biçimlendirmeye ilişkin ipuçları ve püf noktaları"
description: "Power BI'da renk biçimlendirmeye ilişkin ipuçları ve püf noktaları"
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
ms.openlocfilehash: 62df61502a6892b359b29d4f3af5b9bccddb044e
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2017
---
# <a name="tips-and-tricks-for-color-formatting-in-power-bi"></a>Power BI'da renk biçimlendirmeye ilişkin ipuçları ve püf noktaları
Power BI, panolarınızı ve raporlarınızı özelleştirmek için birçok farklı yol sunar. Bu makalede, Power BI görselleştirmelerinizi daha etkileyici ve ilgi çekici bir hale getirip ihtiyaçlarınıza göre özelleştirmenizi sağlayacak birçok ipucu verilmektedir.

İpuçlarını aşağıda bulabilirsiniz. Başka bir ipucu öneriniz mi var? Harika! Bu listeye ekleyip eklemeyeceğimize karar vermemiz için ipucunuzu bizimle paylaşın.

* Tek bir veri noktasının rengini değiştirme
* Bir grafiğin renkleri için sayısal bir değeri temel alma
* Veri noktalarının rengi için bir alan değerini temel alma
* Renk ölçeğinde kullanılan renkleri özelleştirme
* Ayrılan renk ölçeklerini kullanma
* Power BI'da yapılan bir işlemi geri alma

Herhangi bir değişiklik yapmak için, bir raporu düzenliyor olmanız gerekir: **Çalışma Alanım** bölmesinden **Raporunuzu** seçin. Ardından, aşağıda gösterildiği şekilde üst menü alanında **Raporu Düzenle** seçeneğini belirleyin.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_1.png)

**Rapor** tuvalinin sağ tarafında **Görsel Öğeler** bölmesi göründüğünde özelleştirme işlemine başlayabilirsiniz.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_2.png)

## <a name="change-the-color-of-a-single-data-point"></a>Tek bir veri noktasının rengini değiştirme
Bazen belirli bir veri noktasını vurgulamak istersiniz. Örneğin, yeni bir ürünün lansmanı için satış rakamları veya yeni bir programın tanıtımından sonra kalite puanlarındaki artış ile ilgili bir noktanın vurgulanması gerekebilir. Power BI ile rengini değiştirerek belirli bir veri noktasını vurgulayabilirsiniz.

Aşağıdaki görselleştirmede eyaletler, yaşam maliyetine göre sıralanmıştır. 

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_3.png)

Şimdi renk kullanarak, Washington'ın bu sıralı listenin neresinde bulunduğunu hızlıca göstermek istediğinizi düşünün. Uygulamanız gereken adımlar:

**Veri Renkleri** bölümünü genişletin. Aşağıdaki seçeneklerle karşılaşırsınız.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_4.png)

**Tümünü Göster**'i **Açık** olarak ayarlayın. Bu işlemin ardından, görselleştirmedeki tüm veri öğelerine ilişkin renkler görüntüler. Veri noktalarının üzerine geldiğinizde herhangi bir veri noktası üzerinde değişiklik yapabilmeniz için kaydırma etkinleştirilir.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_5.png)

Bu örnekte, **Washington**'ın rengini yeşil olarak değiştirelim. Sayfayı aşağıya kaydırarak **Washington**'ı bulup renk kutusundaki aşağı oku seçtiğimizde renk seçimi penceresi görüntülenir.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_6.png)

Seçtiğinizde, **Washington** veri noktası yeşilin güzel bir tonunda vurgulanır ve belirgin bir şekilde öne çıkar.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_7.png)

Görselleştirme türlerini değiştirip geri dönseniz bile Power BI seçiminizi hatırlar ve **Washington**'ın yeşil renkte kalmasını sağlar.

Birden fazla veri öğesine ilişkin bir veri noktasının rengini de değiştirebilirsiniz. Aşağıdaki görüntüde **Arizona** kırmızı, **Washington** ise hâlâ yeşil renktedir.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_8.png)

Renkleri kullanarak her türlü işlemi gerçekleştirebilirsiniz. Sonraki bölümde, gradyanlara bakacağız.

## <a name="base-the-colors-of-a-chart-on-a-numeric-value"></a>Bir grafiğin renkleri için sayısal bir değeri temel alma
Grafiklerde genellikle renkleri, bir alanın sayısal değerine göre dinamik olarak ayarlama özelliğinden faydalanılır. Bunu yaptığınızda bir çubuğun boyutu için önceden kullanılan değerden farklı bir değer gösterebilir ve tek bir grafta iki değer sunabilirsiniz. Ayrıca bunu, belirli bir değerin üzerindeki (veya altındaki) veri noktalarını vurgulamak için de kullanabilirsiniz. Örneğin, kârlılığın düşük olduğu alanları vurgulamak isteyebilirsiniz.

Aşağıdaki bölümlerde, renk için bir sayısal değeri temel almaya ilişkin farklı yöntemler gösterilmiştir.

## <a name="base-the-color-of-data-points-on-a-value"></a>Veri noktalarının rengi için bir değeri temel alma
Rengi bir değere göre değiştirmek için, renk için temel alınmasını istediğiniz alanı **Alanlar** bölmesindeki **Renk Doygunluğu** alanına sürükleyin. Aşağıdaki görüntüde, **Profit before tax** alanı **Renk Doygunluğu** alanına sürüklenmiştir. Göreceğiniz üzere **Velo**'nun **Gross Sales** değeri daha yüksek olsa da (sütunu daha yüksekte), **Amarilla**'nın **Profit before tax** değeri daha fazladır (sütunundaki renk doygunluğu daha fazla).

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_9.png)

## <a name="customize-the-colors-used-in-the-color-scale"></a>Renk ölçeğinde kullanılan renkleri özelleştirme
Renk ölçeğinde kullanılan renkleri de özelleştirebilirsiniz. **Veri Renkleri**'ni genişlettiğinizde, verilerinizi görselleştirmek için kullanılan bir renk gradyanı görürsünüz. Varsayılan olarak, verilerinizdeki en düşük değer en az doygun renkle, en yüksek değer ise en doygun renkle eşlenir.

Renk aralığı, **Minimum** ve **Maksimum** renk değerleri arasındaki renk yelpazesini görüntüleyen bir gradyan çubukta gösterilir. **Minimum** değer rengi solda, **Maksimum** değer rengi ise sağdadır.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_10.png)

Ölçeği, farklı bir renk aralığı kullanmak üzere değiştirmek için **Minimum** veya **Maksimum** seçeneklerinin yanındaki renk açılan listesini seçip bir renk belirleyin. Aşağıdaki görüntüde, **Maksimum** seçeneğine ilişkin renk siyah olarak değiştirilmiştir. Gradyan çubukta ise **Minimum** ve **Maksimum** arasındaki yeni renk yelpazesi gösterilmektedir.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_11.png)

Değerlerin bu renklerle nasıl eşleneceğini de değiştirebilirsiniz. Aşağıdaki görüntüde, **Minimum** ve **Maksimum** değerlerine ilişkin renkler sırasıyla turuncu ve yeşil olarak ayarlanmıştır.

İlk görüntüde, grafikteki çubukların, çubukta gösterilen gradyanı nasıl yansıttığına dikkat edin; en yüksek değer yeşil, en düşük değer ise turuncudur. Ayrıca, bu değerler arasındaki her çubuk renk yelpazesinde bulunan, yeşil ve turuncu arasındaki tonlarla renklendirilmiştir.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_12.png)

Şimdi, **Minimum** ve **Maksimum** renk seçicileri altında bulunan **Minimum** ve **Maksimum** değer kutularına (aşağıda gösterilmiştir) sayısal değer girdiğimizde ne olacağını görelim. **Minimum**'u 20.000.000 ve **Maksimum**'u 20.000.000 olarak ayarlayalım.

Bu değerler ayarlandığında, grafikte **Minimum**'un altında veya **Maksimum**'un üzerindeki değerler için artık gradyan uygulanmaz. **Maksimum** değerin üzerinde bir değere sahip tüm çubuklar yeşil, **Minimum** değerin altında bir değere sahip tüm çubuklar ise kırmızı renkte gösterilir.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_13.png)

## <a name="use-diverging-color-scales"></a>Ayrılan renk ölçeklerini kullanma
Bazı durumlarda, verilerinizde doğal olarak ayrılan bir ölçek olabilir. Örneğin, sıcaklık aralığının donma noktasında doğal bir merkez noktası, kârlılık puanının ise doğal bir orta noktası (sıfır) mevcuttur.

Ayrılan renk ölçeklerini kullanmak için **Ayrılan** kaydırıcısını **Açık** konumuna getirin. **Ayrılan** kaydırıcısı etkinleştirildiğinde, aşağıdaki görüntüde gösterildiği gibi **Orta** adlı ek bir renk seçici ve değer kutusu görünür.

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_14.png)

**Ayrılan** kaydırıcısı etkinleştirildiğinde **Minimum**, **Maksimum** ve **Orta** seçenekleri için renkleri ayrı olarak ayarlayabilirsiniz. Aşağıdaki görüntüde **Orta** değer kutusu bir olarak ayarlanmıştır, bu yüzden değeri birin üzerinde olan çubuklar yeşil bir gradyan tonuna sahipken, birin altında bulunan çubuklar kırmızı tondadır.

## <a name="how-to-undo-in-power-bi"></a>Power BI'da yapılan bir işlemi geri alma
Diğer birçok Microsoft hizmeti ve yazılımı gibi Power BI da son komutunuzu geri almanız için kolay bir yol sunar. Örneğin, bir veya bir dizi veri noktasının rengini değiştirdiniz ve görselleştirmede ortaya çıkan rengi beğenmediniz. Önceden hangi rengin seçili olduğunu hatırlamıyorsunuz ancak eski renge geri dönmek istiyorsunuz!

Son eyleminizi veya son birkaç eyleminizi **geri almak** için tüm yapmanız gereken:

- CTRL+Z tuş bileşimini kullanın

## <a name="feedback"></a>Geri bildirim
Paylaşmak istediğiniz bir ipucu var mı? Bu listeye ekleyip eklemeyeceğimize karar vermemiz için lütfen ipucunuzu bizimle paylaşın.

>[!NOTE]
>**Biçim** simgesi seçiliyken kullanılabilen bu renk, eksen özelleştirmeleri ve ilgili özelleştirmeler Power BI Desktop'ta da kullanılabilir.

## <a name="next-steps"></a>Sonraki adımlar
[Renk biçimlendirme ve eksen özelliklerini kullanmaya başlama](service-getting-started-with-color-formatting-and-axis-properties.md)

